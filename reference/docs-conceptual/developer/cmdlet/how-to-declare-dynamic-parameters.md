---
title: 동적 매개 변수를 선언 하는 방법 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db04f1df-def5-4456-8869-336024cda723
caps.latest.revision: 8
ms.openlocfilehash: a9c530cdc66302eb6b3d9d2b284eeb486c3b2ba9
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364422"
---
# <a name="how-to-declare-dynamic-parameters"></a><span data-ttu-id="942c4-102">동적 매개 변수를 선언하는 방법</span><span class="sxs-lookup"><span data-stu-id="942c4-102">How to Declare Dynamic Parameters</span></span>

<span data-ttu-id="942c4-103">이 예에서는 런타임에 cmdlet에 추가 되는 동적 매개 변수를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="942c4-103">This example shows how to define dynamic parameters that are added to the cmdlet at runtime.</span></span> <span data-ttu-id="942c4-104">이 예에서는 사용자가 `Employee` 스위치 매개 변수를 지정할 때마다 `Department` 매개 변수가 cmdlet에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="942c4-104">In this example, the `Department` parameter is added to the cmdlet whenever the user specifies the `Employee` switch parameter.</span></span> <span data-ttu-id="942c4-105">동적 매개 변수에 대 한 자세한 내용은 [Cmdlet 동적 매개 변수](./cmdlet-dynamic-parameters.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="942c4-105">For more information about dynamic parameters, see [Cmdlet Dynamic Parameters](./cmdlet-dynamic-parameters.md).</span></span>

## <a name="to-define-dynamic-parameters"></a><span data-ttu-id="942c4-106">동적 매개 변수를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="942c4-106">To define dynamic parameters</span></span>

1. <span data-ttu-id="942c4-107">Cmdlet 클래스 선언에서 표시 된 대로 [Idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters) 인터페이스를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="942c4-107">In the cmdlet class declaration, add the [System.Management.Automation.Idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters) interface as shown.</span></span>

   ```csharp
   public class SendGreetingCommand : Cmdlet, IDynamicParameters
   ```

2. <span data-ttu-id="942c4-108">[Idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters) 메서드를 호출 합니다 .이 메서드는 동적 매개 변수가 정의 된 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="942c4-108">Call the [System.Management.Automation.Idynamicparameters.Getdynamicparameters\*](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters) method, which returns the object in which the dynamic parameters are defined.</span></span> <span data-ttu-id="942c4-109">이 예제에서는 `Employee` 매개 변수가 지정 될 때 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="942c4-109">In this example, the method is called when the `Employee` parameter is specified.</span></span>

   ```csharp
   public object GetDynamicParameters()
   {
       if (employee)
       {
         context= new SendGreetingCommandDynamicParameters();
         return context;
       }
       return null;
   }
   private SendGreetingCommandDynamicParameters context;
   ```

3. <span data-ttu-id="942c4-110">추가할 동적 매개 변수를 정의 하는 클래스를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="942c4-110">Declare a class that defines the dynamic parameters to be added.</span></span> <span data-ttu-id="942c4-111">정적 cmdlet 매개 변수를 선언 하는 데 사용 된 특성을 사용 하 여 동적 매개 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="942c4-111">You can use the attributes that you used to declare the static cmdlet parameters to declare the dynamic parameters.</span></span>

   ```csharp
   public class SendGreetingCommandDynamicParameters
   {
     [Parameter]
     [ValidateSet ("Marketing", "Sales", "Development")]
     public string Department
     {
       get { return department; }
       set { department = value; }
     }
     private string department;
   }
   ```

## <a name="example"></a><span data-ttu-id="942c4-112">예제</span><span class="sxs-lookup"><span data-stu-id="942c4-112">Example</span></span>

<span data-ttu-id="942c4-113">이 예에서는 사용자가 `Employee` 매개 변수를 지정할 때마다 `Department` 매개 변수가 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="942c4-113">In this example, the `Department` parameter is added whenever the user specifies the `Employee` parameter.</span></span> <span data-ttu-id="942c4-114">@No__t-0 매개 변수는 선택적 매개 변수 이며, ValidateSet 특성을 사용 하 여 허용 되는 인수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="942c4-114">The `Department` parameter is an optional parameter, and the ValidateSet attribute is used to specify the allowed arguments.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Management.Automation;     // PowerShell assembly.

namespace SendGreeting
{
  // Declare the cmdlet class that supports the
  // IDynamicParameters interface.
  [Cmdlet(VerbsCommunications.Send, "Greeting")]
  public class SendGreetingCommand : Cmdlet, IDynamicParameters
  {
    // Declare the parameters for the cmdlet.
    [Parameter(Mandatory = true)]
    public string Name
    {
      get { return name; }
      set { name = value; }
    }
    private string name;

    [Parameter]
    [Alias ("FTE")]
    public SwitchParameter Employee
    {
      get { return employee; }
      set { employee = value; }
    }
    private Boolean employee;

    // Implement GetDynamicParameters to
    // retrieve the dynamic parameter.
    public object GetDynamicParameters()
    {
      if (employee)
      {
        context= new SendGreetingCommandDynamicParameters();
        return context;
      }
      return null;
   }
   private SendGreetingCommandDynamicParameters context;

    // Overide the ProcessRecord method to process the
    // supplied user name and write out a greeting to
    // the user by calling the WriteObject method.
    protected override void ProcessRecord()
    {
      WriteObject("Hello " + name + "! ");
      if (employee)
      {
        WriteObject("Department: " + context.Department);
      }
    }
  }

  // Define the dynamic parameters to be added
  public class SendGreetingCommandDynamicParameters
  {
    [Parameter]
    [ValidateSet ("Marketing", "Sales", "Development")]
    public string Department
    {
      get { return department; }
      set { department = value; }
    }
    private string department;
  }
}
```

## <a name="see-also"></a><span data-ttu-id="942c4-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="942c4-115">See Also</span></span>

[<span data-ttu-id="942c4-116">Runtimedefinedparameterdictionary.</span><span class="sxs-lookup"><span data-stu-id="942c4-116">System.Management.Automation.Runtimedefinedparameterdictionary</span></span>](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)

[<span data-ttu-id="942c4-117">Idynamicparameters. Getdynamicparameters \*</span><span class="sxs-lookup"><span data-stu-id="942c4-117">System.Management.Automation.Idynamicparameters.Getdynamicparameters\*</span></span>](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)

[<span data-ttu-id="942c4-118">Cmdlet 동적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="942c4-118">Cmdlet Dynamic Parameters</span></span>](./cmdlet-dynamic-parameters.md)

[<span data-ttu-id="942c4-119">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="942c4-119">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)