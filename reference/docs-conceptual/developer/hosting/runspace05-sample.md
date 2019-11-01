---
title: Runspace05 샘플 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1685cfc4-b32c-4bed-b221-e0c4482db955
caps.latest.revision: 9
ms.openlocfilehash: eb227b5fa5e91f59b6fc99981ff5affca1cf63fd
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360882"
---
# <a name="runspace05-sample"></a><span data-ttu-id="1bfb9-102">Runspace05 샘플</span><span class="sxs-lookup"><span data-stu-id="1bfb9-102">Runspace05 Sample</span></span>

<span data-ttu-id="1bfb9-103">이 샘플에서는 [runspace](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) 개체에 스냅인을 추가 하 여 runspace를 열 때 스냅인의 cmdlet을 사용할 수 있도록 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1bfb9-103">This sample shows how to add a snap-in to an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object so that the cmdlet of the snap-in is available when the runspace is opened.</span></span> <span data-ttu-id="1bfb9-104">이 스냅인은 GetProcessSample01 개체를 사용 하 여 동기적으로 실행 되는 Get Proc cmdlet ( [샘플](../cmdlet/getprocesssample01-sample.md)에서 정의 됨)을 제공 [합니다.](/dotnet/api/system.management.automation.powershell)</span><span class="sxs-lookup"><span data-stu-id="1bfb9-104">The snap-in provides a Get-Proc cmdlet (defined by the [GetProcessSample01 Sample](../cmdlet/getprocesssample01-sample.md)) that is run synchronously by using a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

## <a name="requirements"></a><span data-ttu-id="1bfb9-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1bfb9-105">Requirements</span></span>

<span data-ttu-id="1bfb9-106">이 샘플에는 Windows PowerShell 2.0이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bfb9-106">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="1bfb9-107">보여</span><span class="sxs-lookup"><span data-stu-id="1bfb9-107">Demonstrates</span></span>

<span data-ttu-id="1bfb9-108">이 샘플에서는 다음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1bfb9-108">This sample demonstrates the following.</span></span>

- <span data-ttu-id="1bfb9-109">[Runspace Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1bfb9-109">Creating an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

- <span data-ttu-id="1bfb9-110">[Runspace Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) 개체에 스냅인을 추가 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="1bfb9-110">Adding the snap-in to the [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

- <span data-ttu-id="1bfb9-111">Initialsessionstate 개체를 사용 하는 [runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) 개체 만들기. [runspace](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) 개체를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bfb9-111">Creating a [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) object that uses the [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

- <span data-ttu-id="1bfb9-112">Runspace를 사용 하는 [system.web. Powershell](/dotnet/api/system.management.automation.powershell) 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1bfb9-112">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object that uses the runspace.</span></span>

- <span data-ttu-id="1bfb9-113">스냅인의 in-proc cmdlet을 [system.object](/dotnet/api/system.management.automation.powershell) 의 파이프라인에 추가 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="1bfb9-113">Adding the snap-in's get-proc cmdlet to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="1bfb9-114">동기적으로 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bfb9-114">Running the command synchronously.</span></span>

- <span data-ttu-id="1bfb9-115">명령에 의해 반환 되는 [system.web. PSObject](/dotnet/api/System.Management.Automation.PSObject) 개체에서 속성을 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bfb9-115">Extracting properties from the [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects returned by the command.</span></span>

## <a name="example"></a><span data-ttu-id="1bfb9-116">예제</span><span class="sxs-lookup"><span data-stu-id="1bfb9-116">Example</span></span>

<span data-ttu-id="1bfb9-117">이 샘플은 Initialsessionstate 개체를 사용 하 여 runspace를 열 때 사용할 수 있는 요소를 정의 하는 runspace를 만듭니다 [runspace](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) .</span><span class="sxs-lookup"><span data-stu-id="1bfb9-117">This sample creates a runspace that uses an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object to define the elements that are available when the runspace is opened.</span></span> <span data-ttu-id="1bfb9-118">이 샘플에서는 Get Proc cmdlet을 정의 하는 스냅인이 초기 세션 상태에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bfb9-118">In this sample, a snap-in that defines a Get-Proc cmdlet is added to the initial session state.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections.ObjectModel;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace05
  {
    /// <summary>
    /// This sample shows how to define an initial session state that is
    /// used when creating a runspace. The sample invokes a command from
    /// a Windows PowerShell snap-in that is present in the console file.
    /// </summary>
    /// <param name="args">The parameter is not used.</param>
    /// <remarks>
    /// This sample assumes that user has coppied the GetProcessSample01.dll
    /// that is produced by the GetProcessSample01 sample to the current
    /// directory.
    /// This sample demonstrates the following:
    /// 1. Creating a default initial session state.
    /// 2. Adding a snap-in to the initial session state.
    /// 3. Creating a runspace that uses the initial session state.
    /// 4. Creating a PowerShell object that uses the runspace.
    /// 5. Adding the snap-in's get-proc cmdlet to the PowerShell object.
    /// 6. Using PSObject objects to extract and display properties from
    ///    the objects returned by the cmdlet.
    /// </remarks>
    private static void Main(string[] args)
    {
      // Create the default initial session state. The default initial
      // session state contains all the elements provided by Windows
      // PowerShell.
      InitialSessionState iss = InitialSessionState.CreateDefault();
      PSSnapInException warning;
      iss.ImportPSSnapIn("GetProcPSSnapIn01", out warning);

      // Create a runspace. Notice that no PSHost object is supplied to the
      // CreateRunspace method so the default host is used. See the Host
      // samples for more information on creating your own custom host.
      using (Runspace myRunSpace = RunspaceFactory.CreateRunspace(iss))
      {
        myRunSpace.Open();

        // Create a PowerShell object.
        using (PowerShell powershell = PowerShell.Create())
        {
          // Add the snap-in cmdlet and specify the runspace.
          powershell.AddCommand("GetProcPSSnapIn01\\get-proc");
          powershell.Runspace = myRunSpace;

          // Run the cmdlet synchronously.
          Collection<PSObject> results = powershell.Invoke();

          Console.WriteLine("Process              HandleCount");
          Console.WriteLine("--------------------------------");

          // Display the results.
          foreach (PSObject result in results)
          {
            Console.WriteLine(
                              "{0,-20} {1}",
                              result.Members["ProcessName"].Value,
                              result.Members["HandleCount"].Value);
          }
        }

        // Close the runspace to release any resources.
        myRunSpace.Close();
      }
      System.Console.WriteLine("Hit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="1bfb9-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1bfb9-119">See Also</span></span>

[<span data-ttu-id="1bfb9-120">Windows PowerShell 호스트 응용 프로그램 작성</span><span class="sxs-lookup"><span data-stu-id="1bfb9-120">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)