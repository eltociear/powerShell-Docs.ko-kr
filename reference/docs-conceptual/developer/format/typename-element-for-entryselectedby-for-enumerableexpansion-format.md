---
title: EnumerableExpansion (형식)에 대 한 EntrySelectedBy의 TypeName 요소 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0506928-db92-4ec4-855f-6f3592a383ae
caps.latest.revision: 6
ms.openlocfilehash: 5ead806d956ebbef95eeffc42bb39ef784208017
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361752"
---
# <a name="typename-element-for-entryselectedby-for-enumerableexpansion-format"></a>EnumerableExpansion의 EntrySelectedBy에 대한 TypeName 요소(형식)

이 정의에 의해 확장 되는 .NET 형식을 지정 합니다. 이 요소는 기본 설정을 정의할 때 사용 됩니다.

Configuration 요소 (Format) DefaultSettings 요소 (format) EnumerableExpansions element (format) enumerableexpansions 요소 (format) Entry Selectedby 요소에 대 한 EnumerableExpansion (형식)

## <a name="syntax"></a>구문

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a>특성 및 요소

다음 섹션에서는 특성, 자식 요소 및 `TypeName` 요소의 부모 요소에 대해 설명 합니다.

### <a name="attributes"></a>특성

없음

### <a name="child-elements"></a>자식 요소

없음

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|[EnumerableExpansion (형식)에 대 한 EntrySelectedBy 요소](./entryselectedby-element-for-enumerableexpansion-format.md)|이 정의를 사용 하는 .NET 형식 또는이 정의를 사용 하기 위해 존재 해야 하는 조건을 정의 합니다.|

## <a name="text-value"></a>텍스트 값

`System.IO.DirectoryInfo`와 같은 .NET 형식의 정규화 된 이름을 지정 합니다.

## <a name="remarks"></a>설명

## <a name="see-also"></a>참고 항목

[EnumerableExpansion (형식)에 대 한 EntrySelectedBy 요소](./entryselectedby-element-for-enumerableexpansion-format.md)

[PowerShell 서식 파일 작성](./writing-a-powershell-formatting-file.md)
