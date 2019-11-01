---
title: 구성에 대 한 컨트롤 Customitem의 CustomItem 요소 (형식) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73fb11ee-0ebd-477a-ac36-acdfbb32e70d
caps.latest.revision: 7
ms.openlocfilehash: bd0cb69770817ec215ddb1862a43a838baddefcf
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364032"
---
# <a name="customitem-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="99908-102">Configuration에 대한 Controls의 CustomEntry에 대한 CustomItem 요소(형식)</span><span class="sxs-lookup"><span data-stu-id="99908-102">CustomItem Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="99908-103">컨트롤에 표시 되는 데이터와 표시 방법을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="99908-103">Defines what data is displayed by the control and how it is displayed.</span></span> <span data-ttu-id="99908-104">이 요소는 서식 파일의 모든 뷰에서 사용할 수 있는 공용 컨트롤을 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99908-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="99908-105">구성 요소 (format) 컨트롤 요소의 구성 (format) CustomControl 요소에 대 한 Control 요소 구성의 CustomControl에 대 한 구성 (형식) CustomEntries 요소 Format) 구성에 대 한 컨트롤의 CustomEntry 요소에 대 한 CustomControl에 대 한 CustomEntry 요소 구성 (Format) Customentry 요소</span><span class="sxs-lookup"><span data-stu-id="99908-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration</span></span>

## <a name="syntax"></a><span data-ttu-id="99908-106">구문</span><span class="sxs-lookup"><span data-stu-id="99908-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...</Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="99908-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="99908-107">Attributes and Elements</span></span>

<span data-ttu-id="99908-108">다음 섹션에서는 `CustomItem` 요소의 특성, 자식 요소 및 부모 요소에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="99908-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span> <span data-ttu-id="99908-109">자세한 내용은 설명 부분을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="99908-109">For more information, see Remarks.</span></span>

### <a name="attributes"></a><span data-ttu-id="99908-110">특성</span><span class="sxs-lookup"><span data-stu-id="99908-110">Attributes</span></span>

<span data-ttu-id="99908-111">없음</span><span class="sxs-lookup"><span data-stu-id="99908-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="99908-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="99908-112">Child Elements</span></span>

|<span data-ttu-id="99908-113">요소</span><span class="sxs-lookup"><span data-stu-id="99908-113">Element</span></span>|<span data-ttu-id="99908-114">설명</span><span class="sxs-lookup"><span data-stu-id="99908-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="99908-115">구성에 대 한 컨트롤 CustomItem의 ExpressionBinding 요소 (형식)</span><span class="sxs-lookup"><span data-stu-id="99908-115">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="99908-116">선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="99908-116">Optional element.</span></span><br /><br /> <span data-ttu-id="99908-117">컨트롤에 표시 되는 데이터를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="99908-117">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="99908-118">구성에 대 한 컨트롤의 CustomItem에 대 한 Frame 요소 (형식)</span><span class="sxs-lookup"><span data-stu-id="99908-118">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="99908-119">선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="99908-119">Optional element.</span></span><br /><br /> <span data-ttu-id="99908-120">데이터를 왼쪽 또는 오른쪽으로 이동 하는 것과 같이 데이터를 표시 하는 방법을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="99908-120">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|
|[<span data-ttu-id="99908-121">구성에 대 한 컨트롤 CustomItem의 줄 바꿈 요소 (형식)</span><span class="sxs-lookup"><span data-stu-id="99908-121">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="99908-122">선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="99908-122">Optional element.</span></span><br /><br /> <span data-ttu-id="99908-123">컨트롤의 표시에 빈 줄을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="99908-123">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="99908-124">구성에 대 한 컨트롤의 CustomItem에 대 한 텍스트 요소 (형식)</span><span class="sxs-lookup"><span data-stu-id="99908-124">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="99908-125">선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="99908-125">Optional element.</span></span><br /><br /> <span data-ttu-id="99908-126">괄호 또는 대괄호와 같은 텍스트를 컨트롤의 표시에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="99908-126">Adds text, such as parentheses or brackets, to the display of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="99908-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="99908-127">Parent Elements</span></span>

|<span data-ttu-id="99908-128">요소</span><span class="sxs-lookup"><span data-stu-id="99908-128">Element</span></span>|<span data-ttu-id="99908-129">설명</span><span class="sxs-lookup"><span data-stu-id="99908-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="99908-130">구성에 대 한 CustomControl의 CustomEntry 요소 (형식)</span><span class="sxs-lookup"><span data-stu-id="99908-130">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="99908-131">컨트롤의 정의를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="99908-131">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="99908-132">설명</span><span class="sxs-lookup"><span data-stu-id="99908-132">Remarks</span></span>

<span data-ttu-id="99908-133">@No__t-0 요소의 자식 요소를 지정할 때는 다음 사항을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99908-133">When specifying the child elements of the `CustomItem` element, keep the following in mind:</span></span>

- <span data-ttu-id="99908-134">자식 요소는 `ExpressionBinding`, `NewLine`, `Text` 및 `Frame` 순서로 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99908-134">The child elements must be added in the following sequence: `ExpressionBinding`, `NewLine`, `Text`, and `Frame`.</span></span>

- <span data-ttu-id="99908-135">지정할 수 있는 시퀀스 수에 대 한 최대 제한은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="99908-135">There is no maximum limit to the number of sequences that you can specify.</span></span>

- <span data-ttu-id="99908-136">각 시퀀스에서 사용할 수 있는 `ExpressionBinding` 요소 수에 대 한 최대 제한은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="99908-136">In each sequence, there is no maximum limit to the number of `ExpressionBinding` elements that you can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="99908-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99908-137">See Also</span></span>

[<span data-ttu-id="99908-138">구성에 대 한 컨트롤 CustomItem의 ExpressionBinding 요소 (형식)</span><span class="sxs-lookup"><span data-stu-id="99908-138">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="99908-139">구성에 대 한 컨트롤의 CustomItem에 대 한 Frame 요소 (형식)</span><span class="sxs-lookup"><span data-stu-id="99908-139">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="99908-140">구성에 대 한 컨트롤 CustomItem의 줄 바꿈 요소 (형식)</span><span class="sxs-lookup"><span data-stu-id="99908-140">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="99908-141">구성에 대 한 컨트롤의 CustomItem에 대 한 텍스트 요소 (형식)</span><span class="sxs-lookup"><span data-stu-id="99908-141">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="99908-142">PowerShell 서식 파일 작성</span><span class="sxs-lookup"><span data-stu-id="99908-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)