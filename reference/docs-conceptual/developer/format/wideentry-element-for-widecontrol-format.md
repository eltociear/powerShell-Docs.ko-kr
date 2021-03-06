---
title: WideControl에 대 한 WideEntry 요소 (형식) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 014763cb-7716-4931-899c-8375b5d7a3dd
caps.latest.revision: 15
ms.openlocfilehash: d1d13b5c3436871053353814293d9163ea13c7fb
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367902"
---
# <a name="wideentry-element-for-widecontrol-format"></a>WideControl에 대한 WideEntry 요소(형식)

넓은 뷰의 정의를 제공 합니다.

Configuration 요소 (Format) ViewDefinitions 요소 (format) View 요소 (format) WideControl Element (format) WideEntries Element (format) WideEntry 요소 (Format)

## <a name="syntax"></a>구문

```xml
<WideEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <WideItem>...</WideItem>
</WideEntry>
```

## <a name="attributes-and-elements"></a>특성 및 요소

다음 섹션에서는 특성, 자식 요소 및 `WideEntry` 요소의 부모 요소에 대해 설명 합니다. 단일 `WideItem` 자식 요소를 지정 해야 합니다.

### <a name="attributes"></a>특성

없음

### <a name="child-elements"></a>자식 요소

|요소|설명|
|-------------|-----------------|
|[WideEntry (형식)에 대 한 EntrySelectedBy 요소](./entryselectedby-element-for-wideentry-format.md)|선택적 요소입니다.<br /><br /> 이 정의를 사용 하기 위해 존재 해야 하는 조건 또는이 광범위 한 항목 정의를 사용 하는 .NET 형식을 정의 합니다.|
|[WideItem 요소 (Format)](./wideitem-element-for-widecontrol-format.md)|필수적 요소입니다.<br /><br /> 값이 표시 되는 속성 또는 스크립트를 정의 합니다.|

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|[WideEntries 요소 (Format)](./wideentries-element-for-widecontrol-format.md)|넓은 뷰의 정의를 제공 합니다.|

## <a name="remarks"></a>설명

넓은 보기는 각 개체에 대 한 단일 속성 값 또는 스크립트 값을 표시 하는 목록 형식입니다. 다른 보기 유형과 달리 각 뷰 정의에는 item 요소를 하나만 지정할 수 있습니다. 넓은 보기의 다른 구성 요소에 대 한 자세한 내용은 [넓은 뷰 만들기](./creating-a-wide-view.md)를 참조 하세요.

## <a name="example"></a>예제

다음 예제에서는 단일 `WideItem` 요소를 정의 하는 `WideEntry` 요소를 보여 줍니다. `WideItem` 요소는 값이 뷰에 표시 되는 속성을 정의 합니다.

```xml
<WideEntries>
  <WideEntry>
    <WideItem>
      <PropertyName>ProcessName</PropertyName>
    </WideItem>
  </WideEntry>
</WideEntries>

```

넓은 보기의 전체 예제는 [넓은 뷰 (기본)](./wide-view-basic.md)를 참조 하세요.

## <a name="see-also"></a>참고 항목

[넓은 뷰 만들기](./creating-a-wide-view.md)

[WideEntry에 대 한 SelectionCondition 요소 (형식)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[WideEntry에 대 한 SelectionSetName 요소 (형식)](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[WideEntry에 대 한 TypeName 요소 (Format)](./typename-element-for-entryselectedby-for-wideentry-format.md)

[WideEntries 요소 (Format)](./wideentries-element-for-widecontrol-format.md)

[WideItem 요소 (Format)](./wideitem-element-for-widecontrol-format.md)

[PowerShell 서식 파일 작성](./writing-a-powershell-formatting-file.md)
