---
title: GroupBy (형식)에 대 한 ItemSelectionCondition의 ScriptBlock 요소 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58d25835-4636-4c58-9f6c-0332b9318051
caps.latest.revision: 6
ms.openlocfilehash: 4045196e306e766cd805b3e7ae31bfcb3de184ee
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364832"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-groupby-format"></a>GroupBy의 ItemSelectionCondition에 대한 ScriptBlock 요소(형식)

조건을 트리거하는 스크립트를 지정 합니다. 이 스크립트가 `true`평가 되 면 조건이 충족 되 고 컨트롤이 사용 됩니다. 이 요소는 새 개체 그룹이 표시 되는 방법을 정의 하는 데 사용 됩니다.

Configuration 요소 (Format) ViewDefinitions 요소 (format) View 요소 (format)의 groupby 요소 (groupby (format) CustomEntries 요소에 대 한 CustomControl 요소에 대 한 groupby (format) Customentries 요소에 대 한 CustomControl Groupby (format) CustomItem 요소에 대 한 CustomControl에 대 한 customitem 요소에 대 한 customitem에 대 한 CustomItem에 대 한 CustomItem에 대 한 요소를 GroupBy (형식)에 대 한 ItemSelectionCondition

## <a name="syntax"></a>구문

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>특성 및 요소

다음 섹션에서는 특성, 자식 요소 및 `ScriptBlock` 요소의 부모 요소에 대해 설명 합니다.

### <a name="attributes"></a>특성

없음

### <a name="child-elements"></a>자식 요소

없음

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|[GroupBy (형식)에 대 한 ExpressionBinding의 ItemSelectionCondition 요소](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|이 컨트롤을 사용 하기 위해 있어야 하는 조건을 정의 합니다.|

## <a name="text-value"></a>텍스트 값

평가 되는 스크립트를 지정 합니다.

## <a name="remarks"></a>설명

이 요소를 사용 하는 경우 선택 조건을 정의할 때 [PropertyName](./propertyname-element-for-itemselectioncondition-for-groupby-format.md) 요소를 지정할 수 없습니다.

## <a name="see-also"></a>참고 항목

[GroupBy (형식)에 대 한 ExpressionBinding의 ItemSelectionCondition 요소](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[GroupBy (형식)에 대 한 ItemSelectionCondition의 PropertyName 요소](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)

[PowerShell 서식 파일 작성](./writing-a-powershell-formatting-file.md)
