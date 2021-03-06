---
title: 선택 집합 정의 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00dbb5ee-93d4-4914-a082-ef4d8b236b5c
caps.latest.revision: 16
ms.openlocfilehash: 596212f2e64401a751cf3dca0ee7d60b80912c00
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368852"
---
# <a name="defining-selection-sets"></a>선택 영역 집합 정의

여러 뷰와 컨트롤을 만들 때 선택 집합으로 참조 되는 개체 집합을 정의할 수 있습니다. 선택 집합을 사용 하면 각 뷰나 컨트롤에 대해 반복적으로 정의 하지 않고도 개체를 한 번 정의할 수 있습니다. 일반적으로 선택 집합은 관련 된 .NET 개체 집합이 있는 경우 사용 됩니다. 예를 들어 `FileSystem` 서식 파일 (types.ps1xml)은 여러 뷰에서 사용 하는 파일 시스템 형식의 선택 집합을 정의 합니다.

## <a name="where-selection-sets-are-defined-and-referenced"></a>선택 집합이 정의 되 고 참조 되는 위치

서식 파일에 정의 된 모든 뷰와 컨트롤에서 사용할 수 있는 공통 데이터의 일부로 선택 집합을 정의 합니다. 다음 예에서는 세 개의 선택 집합을 정의 하는 방법을 보여 줍니다.

```xml
<Configuration>
  <SelectionSets>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
  </SelectionSets>
</Configuration>
```

다음과 같은 방법으로 선택 집합을 참조할 수 있습니다.

- 각 뷰에는 뷰를 사용 하 여 표시 되는 개체를 정의 하는 `ViewSelectedBy` 요소가 있습니다. `ViewSelectedBy` 요소에는 뷰의 모든 정의에 사용 되는 선택 집합을 지정 하는 `SelectionSetName` 자식 요소가 있습니다. 뷰에서 참조할 수 있는 선택 집합 수에는 제한이 없습니다.

- 뷰나 컨트롤의 각 정의에서 `EntrySelectedBy` 요소는 해당 정의를 사용 하 여 표시 되는 개체를 정의 합니다. 일반적으로 뷰 또는 컨트롤에는 정의가 하나만 있으므로 `ViewSelectedBy` 요소에 의해 개체가 정의 됩니다. 정의의 `EntrySelectedBy` 요소에는 선택 집합을 지정 하는 `SelectionSetName` 자식 요소가 있습니다. 정의에 대 한 선택 집합을 지정 하는 경우 `EntrySelectedBy` 요소의 다른 자식 요소를 지정할 수 없습니다.

- 뷰나 컨트롤의 각 정의에서 `SelectionCondition` 요소를 사용 하 여 정의를 사용 하는 경우에 대 한 조건을 지정할 수 있습니다. `SelectionCondition` 요소에는 조건을 트리거하는 선택 집합을 지정 하는 `SelectionSetName` 자식 요소가 있습니다. 선택 집합에 정의 된 개체가 표시 될 때 조건이 트리거됩니다. 이러한 조건을 설정 하는 방법에 대 한 자세한 내용은 [데이터 표시 시기에 대 한 조건 정의](./defining-conditions-for-displaying-data.md)를 참조 하세요.

## <a name="selection-set-example"></a>선택 집합 예제

다음 예제에서는 Windows PowerShell에서 제공 하는 `FileSystem` 서식 파일에서 직접 가져온 선택 집합을 보여 줍니다. 다른 Windows PowerShell 형식 지정 파일에 대 한 자세한 내용은 [Windows Powershell 형식 지정 파일](./powershell-formatting-files.md)을 참조 하세요.

```xml
<SelectionSets>
  <SelectionSet>
    <Name>FileSystemTypes</Name>
    <Types>
     <TypeName>System.IO.DirectoryInfo</TypeName>
     <TypeName>System.IO.FileInfo</TypeName>
     <TypeName>Deserialized.System.IO.DirectoryInfo</TypeName>
     <TypeName>Deserialized.System.IO.FileInfo</TypeName>
    </Types>
  </SelectionSet>
</SelectionSets>
```

이전 선택 집합은 테이블 뷰의 `ViewSelectedBy` 요소에서 참조 됩니다.

```xml
<ViewDefinitions>
  <View>
    <Name>Files</Name>
    <ViewSelectedBy>
      <SelectionSetName>FileSystemTypes</SelectionSetName>
    </ViewSelectedBy>
    <TableControl>...</TableControl>
  </View>
</ViewDefinitions>

```

## <a name="xml-elements"></a>XML 요소

 정의할 수 있는 선택 집합 수에는 제한이 없습니다. 다음 XML 요소를 사용 하 여 선택 집합을 만들 수 있습니다.

- [Selectionsets](./selectionsets-element-format.md) 요소는 서식 파일의 뷰 및 컨트롤에서 참조 하는 .net 개체 집합을 정의 합니다.

- [Selectionset](./selectionset-element-format.md) 요소는 단일 .net 개체 집합을 정의 합니다.

- [Name](./name-element-for-selectionset-format.md) 요소는 선택 집합을 참조 하는 데 사용 되는 이름을 지정 합니다.

- [Types](./types-element-for-selectionset-format.md) 요소는 선택 집합의 개체에 대 한 .net 유형을 지정 합니다. 형식 지정 파일 내에서 개체는 .NET 형식으로 지정 됩니다.

 다음 XML 요소를 사용 하 여 선택 집합을 지정 합니다.

- 다음 요소는 뷰의 모든 정의에 사용할 선택 집합을 지정 합니다.

    - [ViewSelectedBy (형식)에 대 한 SelectionSetName 요소](./selectionsetname-element-for-viewselectedby-format.md)

    - [GroupBy (형식)에 대 한 EntrySelectedBy의 SelectionSetName 요소](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

- 다음 요소는 단일 뷰 정의에서 사용 되는 선택 집합을 지정 합니다.

    - [이 listcontrol (형식)에 대 한 EntrySelectedBy의 SelectionSetName 요소](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

    - [TableControl (형식)에 대 한 EntrySelectedBy의 SelectionSetName 요소](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

    - [WideControl (형식)에 대 한 EntrySelectedBy의 SelectionSetName 요소](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

    - [CustomControl for View (Format)에 대 한 EntrySelectedBy의 SelectionSetName 요소](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

- 다음 요소는 공용 및 뷰 컨트롤 정의에서 사용 되는 선택 집합을 지정 합니다.

    - [View의 컨트롤에 대 한 EntrySelectedBy의 SelectionSetName 요소 (형식)](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)

    - [구성 (형식)의 컨트롤에 대 한 EntrySelectedBy의 SelectionSetName 요소](./selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format.md)

- 다음 요소는 확장할 개체를 정의할 때 사용 되는 선택 집합을 지정 합니다.

    - [EnumerableExpansion (형식)에 대 한 EntrySelectedBy의 SelectionSetName 요소](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

- 다음 요소는 선택 조건에 사용 되는 선택 집합을 지정 합니다.

    - [구성에 대 한 컨트롤의 SelectionCondition에 대 한 SelectionSetName 요소 (형식)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

    - [View 컨트롤의 SelectionCondition에 대 한 SelectionSetName 요소 (형식)](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

    - [CustomControl에 대 한 SelectionCondition의 SelectionSetName 요소 (형식)](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

    - [EnumerableExpansion (Format)에 대해 EntrySelectedBy의 SelectionCondition에 대 한 SelectionSetName 요소](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

    - [ListEntry (형식)에 대 한 EntrySelectedBy의 SelectionCondition에 대 한 SelectionSetName 요소](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)

    - [TableControl (형식)에 대 한 EntrySelectedBy의 SelectionCondition에 대 한 SelectionSetName 요소](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

    - [WideEntry (형식)에 대 한 EntrySelectedBy의 SelectionCondition에 대 한 SelectionSetName 요소](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

    - [GroupBy (Format)의 SelectionCondition에 대 한 SelectionSetName 요소](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)

## <a name="see-also"></a>참고 항목

[SelectionSets](./selectionsets-element-format.md)

[SelectionSet](./selectionset-element-format.md)

[이름](./name-element-for-selectionset-format.md)

[유형](./types-element-for-selectionset-format.md)

[PowerShell 서식 파일](./powershell-formatting-files.md)

[데이터가 표시 되는 시점에 대 한 조건 정의](./defining-conditions-for-displaying-data.md)

[PowerShell 서식 지정 및 형식 파일 작성](./writing-a-powershell-formatting-file.md)
