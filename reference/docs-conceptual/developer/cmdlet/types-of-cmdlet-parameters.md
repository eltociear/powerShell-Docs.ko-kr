---
title: Cmdlet 매개 변수의 유형 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6602730d-3892-4656-80c7-7bca2d14337f
caps.latest.revision: 14
ms.openlocfilehash: f5781c0c03aca41d01a44598a9a8c00d6d21d2fd
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369312"
---
# <a name="types-of-cmdlet-parameters"></a>Cmdlet 매개 변수 형식

이 항목에서는 cmdlet에서 선언할 수 있는 여러 가지 형식의 매개 변수를 설명 합니다. Cmdlet 매개 변수는 위치, 명명 됨, 필수, 선택적 또는 스위치 매개 변수가 될 수 있습니다.

## <a name="positional-and-named-parameters"></a>위치 및 명명 된 매개 변수

모든 cmdlet 매개 변수는 명명 된 매개 변수 또는 위치 매개 변수입니다. 명명 된 매개 변수를 사용 하려면 cmdlet을 호출할 때 매개 변수 이름과 인수를 입력 해야 합니다. 위치 매개 변수는 상대 순서로 인수를 입력 해야 합니다. 그런 다음 첫 번째 명명 되지 않은 인수를 첫 번째 위치 매개 변수에 매핑합니다. 시스템은 두 번째 명명 되지 않은 인수를 두 번째 명명 되지 않은 매개 변수에 매핑합니다. 기본적으로 모든 cmdlet 매개 변수는 명명 된 매개 변수입니다.

명명 된 매개 변수를 정의 하려면 다음 매개 변수 선언에 표시 된 것 처럼 **매개 변수** 특성 선언에서 `Position` 키워드를 생략 합니다.

```csharp
[Parameter(ValueFromPipeline=true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

위치 매개 변수를 정의 하려면 매개 변수 특성 선언에 `Position` 키워드를 추가 하 고 위치를 지정 합니다. 다음 샘플에서 `UserName` 매개 변수는 위치가 0 인 위치 매개 변수로 선언 됩니다. 즉, 호출의 첫 번째 인수는이 매개 변수에 자동으로 바인딩됩니다.

```csharp
[Parameter(Position = 0)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

> [!NOTE]
> Cmdlet이 실행 될 때 사용자가 매개 변수 이름을 입력 하지 않아도 되도록 가장 많이 사용 되는 매개 변수를 위치 매개 변수로 선언 하는 것이 좋습니다.

위치 및 명명 된 매개 변수는 단일 인수 또는 쉼표로 구분 된 여러 인수를 허용 합니다. 매개 변수가 문자열 배열과 같은 컬렉션을 허용 하는 경우에만 여러 인수를 사용할 수 있습니다. 동일한 cmdlet에서 위치 및 명명 된 매개 변수를 혼합할 수 있습니다. 이 경우 시스템은 명명 된 인수를 먼저 검색 한 다음 나머지 명명 되지 않은 인수를 위치 매개 변수에 매핑하려고 시도 합니다.

다음 명령은 `Get-Command` cmdlet의 매개 변수에 대 한 단일 인수와 여러 인수를 지정할 수 있는 여러 가지 방법을 보여 줍니다. 마지막 두 샘플에서 `Name` 매개 변수는 위치 매개 변수로 정의 되므로 **이름을** 지정할 필요가 없습니다.

```powershell
Get-Command -Name get-service
Get-Command -Name get-service,set-service
Get-Command get-service
Get-Command get-service,set-service
```

## <a name="mandatory-and-optional-parameters"></a>필수 및 선택적 매개 변수

Cmdlet 매개 변수를 필수 또는 선택적 매개 변수로 정의할 수도 있습니다. Windows PowerShell 런타임이 cmdlet을 호출 하기 전에 필수 매개 변수를 지정 해야 합니다.  기본적으로 매개 변수는 선택 사항으로 정의 됩니다.

필수 매개 변수를 정의 하려면 다음 매개 변수 선언에 표시 된 것 처럼 매개 변수 특성 선언에 `Mandatory` 키워드를 추가 하 고 `true`로 설정 합니다.

```csharp
[Parameter(Position = 0, Mandatory = true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

선택적 매개 변수를 정의 하려면 다음 매개 변수 선언에 표시 된 것 처럼 **매개 변수** 특성 선언에서 `Mandatory` 키워드를 생략 합니다.

```csharp
[Parameter(Position = 0)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

## <a name="switch-parameters"></a>스위치 매개 변수

Windows PowerShell은 cmdlet을 호출할 때 매개 변수가 지정 되지 않은 경우 해당 값이 `false` 자동으로 설정 되는 매개 변수를 정의할 수 있도록 하는 [system.web. switchparameter](/dotnet/api/System.Management.Automation.SwitchParameter) 형식을 제공 합니다. 가능 하면 부울 매개 변수 대신 스위치 매개 변수를 사용 합니다.

다음 샘플을 참조 하세요. 기본적으로 여러 Windows PowerShell cmdlet은 출력 개체를 파이프라인 아래로 전달 하지 않습니다. 그러나 이러한 cmdlet에는 기본 동작을 재정의 하는 `PassThru` 스위치 매개 변수가 있습니다. 이러한 cmdlet을 호출할 때 `PassThru` 매개 변수를 지정 하면 cmdlet이 출력 개체를 파이프라인에 반환 합니다.

호출에 매개 변수가 지정 되지 않은 경우 매개 변수가 `true`의 기본값을 갖도록 하려면 매개 변수의 의미를 반대로 하는 것이 좋습니다. 샘플의 경우 매개 변수 특성을 `true`부울 값으로 설정 하는 대신 속성을 [system.object](/dotnet/api/System.Management.Automation.SwitchParameter) 로 선언한 다음 매개 변수의 기본값을 `false`로 설정 합니다.

스위치 매개 변수를 정의 하려면 다음 샘플과 같이 속성을 [System.object 매개 변수](/dotnet/api/System.Management.Automation.SwitchParameter) 형식으로 선언 합니다.

```csharp
[Parameter(Position = 1)]
public SwitchParameter GoodBye
{
  get { return goodbye; }
  set { goodbye = value; }
}
private bool goodbye;
```

매개 변수가 지정 될 때 매개 변수를 사용 하도록 하려면 입력 처리 메서드 중 하나에서 다음 구조체를 사용 합니다.

```csharp
protected override void ProcessRecord()
{
  WriteObject("Switch parameter test: " + userName + ".");
  if(goodbye)
  {
    WriteObject(" Goodbye!");
  }
} // End ProcessRecord
```

## <a name="see-also"></a>참고 항목

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)(Windows PowerShell Cmdlet 작성)
