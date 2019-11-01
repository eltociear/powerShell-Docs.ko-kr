---
title: 이 listcontrol (형식)에 대 한 ItemSelectionCondition의 ScriptBlock 요소 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c929a6df-d050-416a-9de0-e913dd5a035c
caps.latest.revision: 8
ms.openlocfilehash: a0768a9c1ac66cd9dcf1848c4b031ccbc722b4c2
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362102"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="89da7-102">ListControl의 ItemSelectionCondition에 대한 ScriptBlock 요소(형식)</span><span class="sxs-lookup"><span data-stu-id="89da7-102">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="89da7-103">조건을 트리거하는 스크립트를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="89da7-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="89da7-104">이 스크립트를 `true`으로 평가 하면 조건이 충족 되 고 목록 항목이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89da7-104">When this script is evaluated to `true`, the condition is met, and the list item is used.</span></span> <span data-ttu-id="89da7-105">이 요소는 목록 뷰를 정의할 때 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89da7-105">This element is used when defining a list view.</span></span>

<span data-ttu-id="89da7-106">Configuration 요소 (Format) ViewDefinitions 요소 (format) View 요소 (format)이 listcontrol Element (format) ListEntries 요소에 대 한이 listcontrol (format) ListEntry 요소 ListEntries의이 listcontrol (Format) ListItems 요소 ListItems에 대 한이 listcontrol (format) ListItem 요소의 경우이 listcontrol (format)의 ListItem 요소에 대 한 itemselectioncondition 요소이 listcontrol의 ItemSelectionCondition (형식)</span><span class="sxs-lookup"><span data-stu-id="89da7-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for List Control (Format) ItemSelectionCondition Element for ListItem for ListControl (Format) ScriptBlock Element for ItemSelectionCondition for ListControl  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="89da7-107">구문</span><span class="sxs-lookup"><span data-stu-id="89da7-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="89da7-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="89da7-108">Attributes and Elements</span></span>

<span data-ttu-id="89da7-109">다음 섹션에서는 `ScriptBlock` 요소의 특성, 자식 요소 및 부모 요소에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="89da7-109">The following sections describe attributes, child elements, and the parent elements of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="89da7-110">특성</span><span class="sxs-lookup"><span data-stu-id="89da7-110">Attributes</span></span>

<span data-ttu-id="89da7-111">없음</span><span class="sxs-lookup"><span data-stu-id="89da7-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="89da7-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="89da7-112">Child Elements</span></span>

<span data-ttu-id="89da7-113">없음</span><span class="sxs-lookup"><span data-stu-id="89da7-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="89da7-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="89da7-114">Parent Elements</span></span>

|<span data-ttu-id="89da7-115">요소</span><span class="sxs-lookup"><span data-stu-id="89da7-115">Element</span></span>|<span data-ttu-id="89da7-116">설명</span><span class="sxs-lookup"><span data-stu-id="89da7-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="89da7-117">이 listcontrol의 ListItem에 대 한 ItemSelectionCondition 요소 (형식)</span><span class="sxs-lookup"><span data-stu-id="89da7-117">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="89da7-118">이 목록 항목을 사용 하기 위해 있어야 하는 조건을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="89da7-118">Defines the condition that must exist for this list item to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="89da7-119">텍스트 값</span><span class="sxs-lookup"><span data-stu-id="89da7-119">Text Value</span></span>

<span data-ttu-id="89da7-120">평가 되는 스크립트를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="89da7-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="89da7-121">설명</span><span class="sxs-lookup"><span data-stu-id="89da7-121">Remarks</span></span>

<span data-ttu-id="89da7-122">이 요소를 사용 하는 경우 선택 조건을 정의할 때 `PropertyName` 요소를 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89da7-122">If this element is used, you cannot specify the `PropertyName` element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="89da7-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="89da7-123">See Also</span></span>

[<span data-ttu-id="89da7-124">PowerShell 서식 파일 작성</span><span class="sxs-lookup"><span data-stu-id="89da7-124">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)