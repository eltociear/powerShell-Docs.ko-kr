---
title: Cmdlet 집합 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bcf0739e-920e-4dd8-afca-2c6d6927bc2a
caps.latest.revision: 10
ms.openlocfilehash: ef3b5bab5dcafc578397bcb4f071776bbdeaced1
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365772"
---
# <a name="cmdlet-sets"></a><span data-ttu-id="be981-102">Cmdlet 집합</span><span class="sxs-lookup"><span data-stu-id="be981-102">Cmdlet Sets</span></span>

<span data-ttu-id="be981-103">Cmdlet을 디자인할 때 동일한 데이터에 대해 여러 작업을 수행 해야 하는 경우가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be981-103">When you design your cmdlets, you might encounter cases in which you need to perform several actions on the same piece of data.</span></span> <span data-ttu-id="be981-104">예를 들어 데이터를 가져오거나 설정 하거나 프로세스를 시작 및 중지 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be981-104">For example, you might need to get and set data or start and stop a process.</span></span> <span data-ttu-id="be981-105">각 작업을 수행 하는 별도의 cmdlet을 만들어야 하지만, cmdlet 디자인은 개별 cmdlet에 대 한 클래스가 파생 되는 기본 클래스를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be981-105">Although you will need to create separate cmdlets to perform each action, your cmdlet design should include a base class from which the classes for the individual cmdlets are derived.</span></span>

<span data-ttu-id="be981-106">기본 클래스를 구현할 때는 다음 사항을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be981-106">Keep the following things in mind when implementing a base class.</span></span>

- <span data-ttu-id="be981-107">기본 클래스의 모든 파생 된 cmdlet에서 사용 하는 일반 매개 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="be981-107">Declare any common parameters used by all the derived cmdlets in the base class.</span></span>

- <span data-ttu-id="be981-108">Cmdlet 관련 매개 변수를 적절 한 cmdlet 클래스에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="be981-108">Add cmdlet-specific parameters to the appropriate cmdlet class.</span></span>

- <span data-ttu-id="be981-109">기본 클래스에서 적절 한 입력 처리 메서드를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="be981-109">Override the appropriate input processing method in the base class.</span></span>

- <span data-ttu-id="be981-110">모든 cmdlet 클래스에서 [system.object](/dotnet/api/System.Management.Automation.CmdletAttribute) 특성을 선언 하지만 기본 클래스에는 선언 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be981-110">Declare the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute on all cmdlet classes, but do not declare it on the base class.</span></span>

- <span data-ttu-id="be981-111">이름 및 설명이 cmdlet 집합을 반영 하는 [add-pssnapin](/dotnet/api/System.Management.Automation.PSSnapIn) 또는 [Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) 클래스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="be981-111">Implement a [System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn) or [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) class whose name and description reflects the set of cmdlets.</span></span>

## <a name="example"></a><span data-ttu-id="be981-112">예제</span><span class="sxs-lookup"><span data-stu-id="be981-112">Example</span></span>

<span data-ttu-id="be981-113">다음 예제에서는 동일한 기본 클래스에서 파생 되는 동일한 기본 클래스에서 파생 되는 기본 클래스를 구현 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="be981-113">The following example shows the implementation of a base class that is used by Get-Proc and Stop-Proc cmdlet that derive from the same base class.</span></span>

```csharp
using System;
using System.Diagnostics;
using System.Management.Automation;             //Windows PowerShell namespace.

namespace Microsoft.Samples.PowerShell.Commands
{

  #region ProcessCommands

  /// <summary>
  /// This class implements a Stop-Proc cmdlet. The parameters
  /// for this cmdlet are defined by the BaseProcCommand class.
  /// </summary>
  [Cmdlet(VerbsLifecycle.Stop, "Proc", SupportsShouldProcess = true)]
  public class StopProcCommand : BaseProcCommand
  {
    public override void ProcessObject(Process process)
    {
      if (ShouldProcess(process.ProcessName, "Stop-Proc"))
      {
        process.Kill();
      }
    }
  }

  /// <summary>
  /// This class implements a Get-Proc cmdlet. The parameters
  /// for this cmdlet are defined by the BaseProcCommand class.
  /// </summary>

  [Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : BaseProcCommand
  {
    public override void ProcessObject(Process process)
    {
      WriteObject(process);
    }
  }

  /// <summary>
  /// This class is the base class that defines the common
  /// functionality used by the Get-Proc and Stop-Proc
  /// cmdlets.
  /// </summary>
  public class BaseProcCommand : Cmdlet
  {
    #region Parameters

    // Defines the Name parameter that is used to
    // specify a process by its name.
    [Parameter(
               Position = 0,
               Mandatory = true,
               ValueFromPipeline = true,
               ValueFromPipelineByPropertyName = true
    )]
    public string[] Name
    {
      get { return processNames; }
      set { processNames = value; }
    }
    private string[] processNames;

    // Defines the Exclude parameter that is used to
    // specify which processes should be excluded when
    // the cmdlet performs its action.
    [Parameter()]
    public string[] Exclude
    {
      get { return excludeNames; }
      set { excludeNames = value; }
    }
    private string[] excludeNames = new string[0];
    #endregion Parameters

    public virtual void ProcessObject(Process process)
    {
      throw new NotImplementedException("This method should be overridden.");
    }

    #region Cmdlet Overrides
    // <summary>
    // For each of the requested process names, retrieve and write
    // the associated processes.
    // </summary>
    protected override void ProcessRecord()
    {
      // Set up the wildcard characters used in resolving
      // the process names.
      WildcardOptions options = WildcardOptions.IgnoreCase |
                                WildcardOptions.Compiled;

      WildcardPattern[] include = new WildcardPattern[Name.Length];
      for (int i = 0; i < Name.Length; i++)
      {
        include[i] = new WildcardPattern(Name[i], options);
      }

      WildcardPattern[] exclude = new WildcardPattern[Exclude.Length];
      for (int i = 0; i < Exclude.Length; i++)
      {
        exclude[i] = new WildcardPattern(Exclude[i], options);
      }

      foreach (Process p in Process.GetProcesses())
      {
        foreach (WildcardPattern wIn in include)
        {
          if (wIn.IsMatch(p.ProcessName))
          {
            bool processThisOne = true;
            foreach (WildcardPattern wOut in exclude)
            {
              if (wOut.IsMatch(p.ProcessName))
              {
                processThisOne = false;
                break;
              }
            }
            if (processThisOne)
            {
              ProcessObject(p);
            }
            break;
          }
        }
      }
    }
    #endregion Cmdlet Overrides
  }
    #endregion ProcessCommands
}
```

## <a name="see-also"></a><span data-ttu-id="be981-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="be981-114">See Also</span></span>

<span data-ttu-id="be981-115">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)(Windows PowerShell Cmdlet 작성)</span><span class="sxs-lookup"><span data-stu-id="be981-115">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>