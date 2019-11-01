---
title: ValidateCount 특성 선언 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes, ValidateCount
- ValidateCount attribute, described
- ValidateCount attribute
ms.assetid: 516af1ef-2c2e-408d-84bc-865f5bccf761
caps.latest.revision: 11
ms.openlocfilehash: ffc45f6b80a2b7ed22f27d083d042b1de7f353f6
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369232"
---
# <a name="validatecount-attribute-declaration"></a><span data-ttu-id="5f8a4-102">ValidateCount 특성 선언</span><span class="sxs-lookup"><span data-stu-id="5f8a4-102">ValidateCount Attribute Declaration</span></span>

<span data-ttu-id="5f8a4-103">ValidateCount 특성은 cmdlet 매개 변수에 허용 되는 인수의 최소 및 최대 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8a4-103">The ValidateCount attribute specifies the minimum and maximum number of arguments allowed for a cmdlet parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="5f8a4-104">구문</span><span class="sxs-lookup"><span data-stu-id="5f8a4-104">Syntax</span></span>

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="5f8a4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5f8a4-105">Parameters</span></span>

<span data-ttu-id="5f8a4-106">`MinLength` ([System.object][])이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8a4-106">`MinLength` ([System.Int32][]) Required.</span></span> <span data-ttu-id="5f8a4-107">인수의 최소 개수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8a4-107">Specifies the minimum number of arguments.</span></span>

<span data-ttu-id="5f8a4-108">`MaxLength` ([System.object][])이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8a4-108">`MaxLength`([System.Int32][]) Required.</span></span> <span data-ttu-id="5f8a4-109">최대 인수 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8a4-109">Specifies the maximum number of arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="5f8a4-110">설명</span><span class="sxs-lookup"><span data-stu-id="5f8a4-110">Remarks</span></span>

- <span data-ttu-id="5f8a4-111">이 특성을 선언 하는 방법에 대 한 자세한 내용은 [인수 수의 유효성을 검사][]하는 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f8a4-111">For more information about how to declare this attribute, see [How to Validate an Argument Count][].</span></span>

- <span data-ttu-id="5f8a4-112">이 특성이 호출 되지 않으면 해당 cmdlet 매개 변수에 원하는 수의 인수가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8a4-112">When this attribute is not invoked, the corresponding cmdlet parameter can have any number of arguments.</span></span>

- <span data-ttu-id="5f8a4-113">Windows PowerShell 런타임은 다음과 같은 경우에 오류를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8a4-113">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

    - <span data-ttu-id="5f8a4-114">@No__t-0 및 `MaxLength` 특성 매개 변수는 [system.object][]형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="5f8a4-114">The `MinLength` and `MaxLength` attribute parameters are not of type [System.Int32][].</span></span>

    - <span data-ttu-id="5f8a4-115">@No__t-0 특성 매개 변수의 값이 `MinLength` 특성 매개 변수의 값 보다 작은 경우</span><span class="sxs-lookup"><span data-stu-id="5f8a4-115">The value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

- <span data-ttu-id="5f8a4-116">ValidateCount 특성은 [ValidateCountAttribute.][] 클래스에 의해 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f8a4-116">The ValidateCount attribute is defined by the [System.Management.Automation.ValidateCountAttribute][] class.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f8a4-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f8a4-117">See Also</span></span>

<span data-ttu-id="5f8a4-118">[ValidateCountAttribute.][]</span><span class="sxs-lookup"><span data-stu-id="5f8a4-118">[System.Management.Automation.ValidateCountAttribute][]</span></span>

<span data-ttu-id="5f8a4-119">[인수 수의 유효성을 검사][]</span><span class="sxs-lookup"><span data-stu-id="5f8a4-119">[How to Validate an Argument Count][]</span></span>

<span data-ttu-id="5f8a4-120">[Writing a Windows PowerShell Cmdlet][](Windows PowerShell Cmdlet 작성)</span><span class="sxs-lookup"><span data-stu-id="5f8a4-120">[Writing a Windows PowerShell Cmdlet][]</span></span>

[인수 수의 유효성을 검사]: how-to-validate-an-argument-count.md
[How to Validate an Argument Count]: how-to-validate-an-argument-count.md
[Writing a Windows PowerShell Cmdlet]: writing-a-windows-powershell-cmdlet.md(Windows PowerShell Cmdlet 작성)

[System.object]: /dotnet/api/System.Int32
[System.Int32]: /dotnet/api/System.Int32
[ValidateCountAttribute.]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
[System.Management.Automation.ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute