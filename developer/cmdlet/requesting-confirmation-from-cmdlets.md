---
title: Cmdlet에서 확인을 요청 합니다. | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ConfirmImpact [PowerShell Programmer's Guide], described
- ShouldContinue [PowerShell Programmer's Guide], described
- user feedback [PowerShell Programmer's Guide], requesting
- ShouldProcess [PowerShell Programmer's Guide], described
- ConfirmPreference [PowerShell Programmer's Guide], described
ms.assetid: 37d6e87f-57b7-40bd-b645-392cf0b6e88e
caps.latest.revision: 13
ms.openlocfilehash: ec441831f5e3231a44c9875d1b6d2bf6280a6965
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853399"
---
# <a name="requesting-confirmation-from-cmdlets"></a><span data-ttu-id="fce3f-102">Cmdlet에서 확인 요청</span><span class="sxs-lookup"><span data-stu-id="fce3f-102">Requesting Confirmation from Cmdlets</span></span>

<span data-ttu-id="fce3f-103">Cmdlet은 Windows PowerShell 환경 외부에서 시스템 변경 작업을 수행 될 때 확인을 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-103">Cmdlets should request confirmation when they are about to make a change to the system that is outside of the Windows PowerShell environment.</span></span> <span data-ttu-id="fce3f-104">예를 들어, 사용자 계정을 추가 하거나 프로세스를 중지 하려고 cmdlet 인 경우 진행 하기 전에 cmdlet을 확인 하는 사용자를 요구 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-104">For example, if a cmdlet is about to add a user account or stop a process, the cmdlet should require confirmation from the user before it proceeds.</span></span> <span data-ttu-id="fce3f-105">반면, cmdlet 변경 되기 직전에 Windows PowerShell 변수를 cmdlet 확인이 필요 하도록 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-105">In contrast, if a cmdlet is about to change a Windows PowerShell variable, the cmdlet does not need to require confirmation.</span></span>

<span data-ttu-id="fce3f-106">확인을 요청 하기 위해 cmdlet 나타내야 확인 요청을 지원 하 고 호출 해야 합니다 [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 고 [ System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) (선택 사항) 방법 확인 요청 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-106">In order to make a confirmation request, the cmdlet must indicate that it supports confirmation requests, and it must call the [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) (optional) methods to display a confirmation request message.</span></span>

## <a name="supporting-confirmation-requests"></a><span data-ttu-id="fce3f-107">확인 요청 지원</span><span class="sxs-lookup"><span data-stu-id="fce3f-107">Supporting Confirmation Requests</span></span>

<span data-ttu-id="fce3f-108">확인 요청을 지원 하려면 cmdlet을 설정 해야 합니다 `SupportsShouldProcess` cmdlet은 특성의 매개 변수 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-108">To support confirmation requests, the cmdlet must set the `SupportsShouldProcess` parameter of the Cmdlet attribute to `true`.</span></span> <span data-ttu-id="fce3f-109">이 통해 합니다 `Confirm` 고 `WhatIf` Windows PowerShell에서 제공 하는 cmdlet 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-109">This enables the `Confirm` and `WhatIf` cmdlet parameters that are provided by Windows PowerShell.</span></span> <span data-ttu-id="fce3f-110">`Confirm` 확인 요청을 표시 되는지 여부를 매개 변수로 사용자를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-110">The `Confirm` parameter allows the user to control whether the confirmation request is displayed.</span></span> <span data-ttu-id="fce3f-111">`WhatIf` 매개 변수 cmdlet은 메시지를 표시 하거나 해당 작업을 수행 해야 하는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-111">The `WhatIf` parameter allows the user to determine whether the cmdlet should display a message or perform its action.</span></span> <span data-ttu-id="fce3f-112">수동으로 추가 하지 마십시오 합니다 `Confirm` 및 `WhatIf` cmdlet 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-112">Do not manually add the `Confirm` and `WhatIf` parameters to a cmdlet.</span></span>

<span data-ttu-id="fce3f-113">다음 예제에서는 확인 요청을 지 원하는 Cmdlet 특성 선언을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-113">The following example shows a Cmdlet attribute declaration that supports confirmation requests.</span></span>

```csharp
[Cmdlet(VerbsDiagnostic.Test, "RequestConfirmationTemplate1",
        SupportsShouldProcess = true)]
```

## <a name="calling-the-confirmation-request-methods"></a><span data-ttu-id="fce3f-114">확인 요청 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-114">Calling the Confirmation request methods</span></span>

<span data-ttu-id="fce3f-115">Cmdlet 코드에서 호출 된 [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 시스템을 변경 하는 작업을 수행 하기 전에 메서드.</span><span class="sxs-lookup"><span data-stu-id="fce3f-115">In the cmdlet code, call the [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method before the operation that changes the system is performed.</span></span> <span data-ttu-id="fce3f-116">경우 호출의 값을 반환 하므로 cmdlet 설계 `false`, 작업이 수행 되지 않습니다 및 cmdlet에서 다음 작업을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-116">Design the cmdlet so that if the call returns a value of `false`, the operation is not performed, and the cmdlet processes the next operation.</span></span>

## <a name="calling-the-shouldcontinue-method"></a><span data-ttu-id="fce3f-117">ShouldContinue 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-117">Calling the ShouldContinue Method</span></span>

<span data-ttu-id="fce3f-118">대부분의 cmdlet 확인만 사용 하 여 요청을 [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 메서드.</span><span class="sxs-lookup"><span data-stu-id="fce3f-118">Most cmdlets request confirmation using only the [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method.</span></span> <span data-ttu-id="fce3f-119">그러나 일부 경우에는 추가 확인이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-119">However, some cases might require additional confirmation.</span></span> <span data-ttu-id="fce3f-120">이러한 경우에 대 한 보완 합니다 [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 에 대 한 호출을 사용 하 여 호출 합니다 [System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) 메서드.</span><span class="sxs-lookup"><span data-stu-id="fce3f-120">For these cases, supplement the [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call with a call to the [System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method.</span></span> <span data-ttu-id="fce3f-121">Cmdlet 또는 공급자의 범위 보다 세부적인 제어를 허용 하는이 **모두 예** 확인 프롬프트에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-121">This allows the cmdlet or provider to more finely control the scope of the **Yes to all** response to the confirmation prompt.</span></span>

<span data-ttu-id="fce3f-122">Cmdlet을 호출 하는 경우는 [System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) 메서드인 cmdlet도 제공 해야 합니다는 `Force` 스위치 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-122">If a cmdlet calls the [System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method, the cmdlet must also provide a `Force` switch parameter.</span></span> <span data-ttu-id="fce3f-123">사용자 지정 하는 경우 `Force` cmdlet을 계속 호출 해야 사용자가 cmdlet를 호출 하면 [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)에 대 한 호출을 무시 해야 하지만 [ System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)합니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-123">If the user specifies `Force` when the user invokes the cmdlet, the cmdlet should still call [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess), but it should bypass the call to [System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span></span>

<span data-ttu-id="fce3f-124">[System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) 사용자 없습니다 묻는 비 대화형 환경에서 호출 될 때 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-124">[System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) will throw an exception when it is called from a non-interactive environment where the user cannot be prompted.</span></span> <span data-ttu-id="fce3f-125">추가 된 `Force` 매개 변수 확인 비 대화형 환경에서 호출 될 때 명령이 수행 여전히 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-125">Adding a `Force` parameter ensures that the command can still be performed when it is invoked in a non-interactive environment.</span></span>

<span data-ttu-id="fce3f-126">다음 예제에서는 호출 하는 방법을 보여 줍니다 [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 하 고 [System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)합니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-126">The following example shows how to call [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span></span>

```csharp
if (ShouldProcess (...) )
{
  if (Force || ShouldContinue(...))
  {
     // Add code that performs the operation.
  }
}
```

<span data-ttu-id="fce3f-127">동작을 [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 호출 cmdlet가 호출 되는 환경에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-127">The behavior of a [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call can vary depending on the environment in which the cmdlet is invoked.</span></span> <span data-ttu-id="fce3f-128">이전 지침을 사용 하 여 cmdlet은 호스트 환경에 관계 없이 다른 cmdlet과 일관 되 게 작동 하는지 확인 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-128">Using the previous guidelines will help ensure that the cmdlet behaves consistently with other cmdlets, regardless of the host environment.</span></span>

<span data-ttu-id="fce3f-129">호출의 예는 [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 메서드를 참조 하십시오 [요청 확인 하는 방법을](./how-to-request-confirmations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-129">For an example of calling the [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method, see [How to Request Confirmations](./how-to-request-confirmations.md).</span></span>

## <a name="specify-the-impact-level"></a><span data-ttu-id="fce3f-130">영향 수준을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-130">Specify the Impact Level</span></span>

<span data-ttu-id="fce3f-131">Cmdlet를 만들 때 변경의 영향 수준 (심각도)를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-131">When you create the cmdlet, specify the impact level (the severity) of the change.</span></span> <span data-ttu-id="fce3f-132">이 위해 값을 설정 합니다 `ConfirmImpact` 높음, 중간 또는 낮음 Cmdlet 특성의 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-132">To do this, set the value of the `ConfirmImpact` parameter of the Cmdlet attribute to High, Medium, or Low.</span></span> <span data-ttu-id="fce3f-133">에 대 한 값을 지정할 수 있습니다 `ConfirmImpact` 만 지정 하는 경우도 `SupportsShouldProcess` cmdlet에 대 한 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-133">You can specify a value for `ConfirmImpact` only when you also specify the `SupportsShouldProcess` parameter for the cmdlet.</span></span>

<span data-ttu-id="fce3f-134">대부분의 cmdlet에 대 한 필요가 없습니다를 명시적으로 지정 `ConfirmImpact`합니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-134">For most cmdlets, you do not have to explicitly specify `ConfirmImpact`.</span></span>  <span data-ttu-id="fce3f-135">대신 사용 중간은 매개 변수의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-135">Instead, use the default setting of the parameter, which is Medium.</span></span> <span data-ttu-id="fce3f-136">설정한 경우 `ConfirmImpact` 높음으로 작업이 기본적으로 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-136">If you set `ConfirmImpact` to High, the operation will be confirmed by default.</span></span> <span data-ttu-id="fce3f-137">하드 디스크 볼륨을 다시 포맷 하는 등 항상 중단 작업의 경우이 설정은 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-137">Reserve this setting for highly disruptive actions, such as reformatting a hard-disk volume.</span></span>

## <a name="calling-non-confirmation-methods"></a><span data-ttu-id="fce3f-138">확인 되지 않은 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="fce3f-138">Calling Non-Confirmation Methods</span></span>

<span data-ttu-id="fce3f-139">Cmdlet 또는 공급자는 메시지를 전송 해야 하지만 확인을 요청 하지, 다음 세 가지 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-139">If the cmdlet or provider must send a message but not request confirmation, it can call the following three methods.</span></span> <span data-ttu-id="fce3f-140">사용 하지 않도록 합니다 [System.Management.Automation.Cmdlet.Writeobject\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) 때문에 이러한 유형의 메시지를 전송 하는 방법 [System.Management.Automation.Cmdlet.Writeobject\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) 출력은 혼합 cmdlet 또는 공급자의 표준 출력에 스크립트 작성을 어렵게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-140">Avoid using the [System.Management.Automation.Cmdlet.Writeobject\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) method to send messages of these types because [System.Management.Automation.Cmdlet.Writeobject\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) output is intermingled with the normal output of your cmdlet or provider, which makes script writing difficult.</span></span>

- <span data-ttu-id="fce3f-141">사용자를 주의 하 고 작업을 계속 하는 cmdlet 또는 공급자를 호출할 수 있습니다 합니다 [System.Management.Automation.Cmdlet.Writewarning\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) 메서드.</span><span class="sxs-lookup"><span data-stu-id="fce3f-141">To caution the user and continue with the operation, the cmdlet or provider can call the [System.Management.Automation.Cmdlet.Writewarning\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) method.</span></span>

- <span data-ttu-id="fce3f-142">사용자를 사용 하 여 검색할 수 있는 추가 정보를 제공 하는 `Verbose` 매개 변수, cmdlet 또는 공급자를 호출할 수는 [System.Management.Automation.Cmdlet.Writeverbose\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) 메서드.</span><span class="sxs-lookup"><span data-stu-id="fce3f-142">To provide additional information that the user can retrieve using the `Verbose` parameter, the cmdlet or provider can call the [System.Management.Automation.Cmdlet.Writeverbose\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) method.</span></span>

- <span data-ttu-id="fce3f-143">제품 지원이 필요 하거나 다른 개발자를 위한 디버깅 수준 세부 정보를 제공, cmdlet 또는 공급자를 호출할 수 있습니다 합니다 [System.Management.Automation.Cmdlet.Writedebug\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) 메서드.</span><span class="sxs-lookup"><span data-stu-id="fce3f-143">To provide debugging-level detail for other developers or for product support, the cmdlet or provider can call the [System.Management.Automation.Cmdlet.Writedebug\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) method.</span></span> <span data-ttu-id="fce3f-144">사용 하 여이 정보를 검색할 수는 `Debug` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="fce3f-144">The user can retrieve this information using the `Debug` parameter.</span></span>

<span data-ttu-id="fce3f-145">Cmdlet 및 공급자의 경우 Windows PowerShell의 외부 시스템을 변경 하는 작업을 수행 하기 전에 확인을 요청에 다음 메서드를 호출 하는 먼저:</span><span class="sxs-lookup"><span data-stu-id="fce3f-145">Cmdlets and providers first call the following methods to request confirmation before they attempt to perform an operation that changes a system outside of Windows PowerShell:</span></span>

- [<span data-ttu-id="fce3f-146">System.Management.Automation.Cmdlet.Shouldprocess</span><span class="sxs-lookup"><span data-stu-id="fce3f-146">System.Management.Automation.Cmdlet.Shouldprocess</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)

- [<span data-ttu-id="fce3f-147">System.Management.Automation.Provider.Cmdletprovider.Shouldprocess</span><span class="sxs-lookup"><span data-stu-id="fce3f-147">System.Management.Automation.Provider.Cmdletprovider.Shouldprocess</span></span>](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)

<span data-ttu-id="fce3f-148">호출 하 여 그렇게 합니다 [System.Management.Automation.Cmdlet.Shouldprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 사용자 명령을 호출 하는 방식에 따라 작업을 확인 하 라는 메시지는 메서드.</span><span class="sxs-lookup"><span data-stu-id="fce3f-148">They do so by calling the [System.Management.Automation.Cmdlet.Shouldprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method, which prompts the user to confirm the operation based on how the user invoked the command.</span></span>

## <a name="see-also"></a><span data-ttu-id="fce3f-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fce3f-149">See Also</span></span>

<span data-ttu-id="fce3f-150">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)(Windows PowerShell Cmdlet 작성)</span><span class="sxs-lookup"><span data-stu-id="fce3f-150">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>