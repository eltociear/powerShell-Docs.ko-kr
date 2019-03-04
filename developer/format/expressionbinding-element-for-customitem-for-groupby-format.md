---
title: GroupBy (형식)에 대 한 CustomItem ExpressionBinding 요소 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5eae5088-7605-4ef2-a703-faf3e5a5fc94
caps.latest.revision: 8
ms.openlocfilehash: 4714bfd1530585aa80aabc010b86d25bf0c7f9c4
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854929"
---
# <a name="expressionbinding-element-for-customitem-for-groupby-format"></a><span data-ttu-id="ef2e3-102">GroupBy의 CustomItem에 대한 ExpressionBinding 요소(형식)</span><span class="sxs-lookup"><span data-stu-id="ef2e3-102">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="ef2e3-103">컨트롤에 표시 되는 데이터를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef2e3-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="ef2e3-104">이 요소는 새 개체 그룹에 표시 되는 방식을 정의 하는 경우에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef2e3-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="ef2e3-105">구성 요소 (형식) ViewDefinitions 요소 (형식) 보기 (형식) GroupBy 요소 CustomControl GroupBy (형식) CustomEntry 요소에 대 한 GroupBy (형식) CustomEntries 요소에 대 한 보기 (형식) CustomControl 요소에 대 한 CustomControl CustomEntry GroupBy (형식)에 대 한 CustomItem ExpressionBinding 요소 GroupBy (형식)에 대 한 GroupBy (형식) CustomItem 요소에</span><span class="sxs-lookup"><span data-stu-id="ef2e3-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ef2e3-106">구문</span><span class="sxs-lookup"><span data-stu-id="ef2e3-106">Syntax</span></span>

```xml
<ExpressionBinding>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameofCommonCustomControl</CustomControlName>
  <EnumerateCollection/>
  <ItemSelectionCondition>...</ItemSelectionCondition>
  <PropertyName>Nameof.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate></ScriptBlock>
</ExpressionBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ef2e3-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ef2e3-107">Attributes and Elements</span></span>

<span data-ttu-id="ef2e3-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에는 `ExpressionBinding` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ef2e3-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ef2e3-109">특성</span><span class="sxs-lookup"><span data-stu-id="ef2e3-109">Attributes</span></span>

<span data-ttu-id="ef2e3-110">없음</span><span class="sxs-lookup"><span data-stu-id="ef2e3-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ef2e3-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ef2e3-111">Child Elements</span></span>

|<span data-ttu-id="ef2e3-112">요소</span><span class="sxs-lookup"><span data-stu-id="ef2e3-112">Element</span></span>|<span data-ttu-id="ef2e3-113">설명</span><span class="sxs-lookup"><span data-stu-id="ef2e3-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="ef2e3-114">선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ef2e3-114">Optional element.</span></span><br /><br /> <span data-ttu-id="ef2e3-115">이 컨트롤에서 사용 되는 컨트롤을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef2e3-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="ef2e3-116">GroupBy (형식)에 대 한 ExpressionBinding에 대 한 CustomControlName 요소</span><span class="sxs-lookup"><span data-stu-id="ef2e3-116">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="ef2e3-117">선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ef2e3-117">Optional element.</span></span><br /><br /> <span data-ttu-id="ef2e3-118">공용 컨트롤에서 뷰 컨트롤의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ef2e3-118">Specifies the name of a common control or a view control.</span></span>|
|<span data-ttu-id="ef2e3-119">[GroupBy (형식)에 대 한 ExpressionBinding에 대 한 EnumerateCollection 요소](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)GroupBy (형식)에 대 한 ExpressionBinding에 대 한 EnumerateCollection 요소</span><span class="sxs-lookup"><span data-stu-id="ef2e3-119">[EnumerateCollection Element for ExpressionBinding for GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>|<span data-ttu-id="ef2e3-120">선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ef2e3-120">Optional element.</span></span><br /><br /> <span data-ttu-id="ef2e3-121">지정한 컬렉션의 요소는 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef2e3-121">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="ef2e3-122">GroupBy (형식)에 대 한 ExpressionBinding에 대 한 ItemSelectionCondition 요소</span><span class="sxs-lookup"><span data-stu-id="ef2e3-122">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="ef2e3-123">선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ef2e3-123">Optional element.</span></span><br /><br /> <span data-ttu-id="ef2e3-124">이 컨트롤을 사용할 수 있어야 하는 조건을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef2e3-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="ef2e3-125">GroupBy (형식)에 대 한 ExpressionBinding에 대 한 PropertyName 요소</span><span class="sxs-lookup"><span data-stu-id="ef2e3-125">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="ef2e3-126">선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ef2e3-126">Optional element.</span></span><br /><br /> <span data-ttu-id="ef2e3-127">컨트롤에서 해당 값이 표시.NET 속성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef2e3-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="ef2e3-128">GroupBy (형식)에 대 한 ExpressionBinding에 대 한 ScriptBlock 요소</span><span class="sxs-lookup"><span data-stu-id="ef2e3-128">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="ef2e3-129">선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ef2e3-129">Optional element.</span></span><br /><br /> <span data-ttu-id="ef2e3-130">컨트롤에서 해당 값이 표시 하는 스크립트를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef2e3-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ef2e3-131">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ef2e3-131">Parent Elements</span></span>

|<span data-ttu-id="ef2e3-132">요소</span><span class="sxs-lookup"><span data-stu-id="ef2e3-132">Element</span></span>|<span data-ttu-id="ef2e3-133">설명</span><span class="sxs-lookup"><span data-stu-id="ef2e3-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ef2e3-134">GroupBy (형식)에 대 한 CustomEntry CustomItem 요소</span><span class="sxs-lookup"><span data-stu-id="ef2e3-134">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="ef2e3-135">사용자 지정 컨트롤 보기에 의해 표시 되는 데이터 및 표시 되는 방식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef2e3-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="see-also"></a><span data-ttu-id="ef2e3-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef2e3-136">See Also</span></span>

[<span data-ttu-id="ef2e3-137">GroupBy (형식)에 대 한 ExpressionBinding에 대 한 CustomControlName 요소</span><span class="sxs-lookup"><span data-stu-id="ef2e3-137">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="ef2e3-138">GroupBy (형식)에 대 한 ExpressionBinding에 대 한 EnumerateCollection 요소</span><span class="sxs-lookup"><span data-stu-id="ef2e3-138">EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="ef2e3-139">GroupBy (형식)에 대 한 ExpressionBinding에 대 한 ItemSelectionCondition 요소</span><span class="sxs-lookup"><span data-stu-id="ef2e3-139">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="ef2e3-140">GroupBy (형식)에 대 한 ExpressionBinding에 대 한 PropertyName 요소</span><span class="sxs-lookup"><span data-stu-id="ef2e3-140">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="ef2e3-141">GroupBy (형식)에 대 한 ExpressionBinding에 대 한 ScriptBlock 요소</span><span class="sxs-lookup"><span data-stu-id="ef2e3-141">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="ef2e3-142">GroupBy (형식)에 대 한 CustomEntry CustomItem 요소</span><span class="sxs-lookup"><span data-stu-id="ef2e3-142">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="ef2e3-143">서식 파일을 PowerShell 작성</span><span class="sxs-lookup"><span data-stu-id="ef2e3-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)