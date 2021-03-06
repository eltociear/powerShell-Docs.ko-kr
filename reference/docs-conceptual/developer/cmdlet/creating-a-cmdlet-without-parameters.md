---
title: 매개 변수를 사용 하지 않고 Cmdlet 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- cmdlets [PowerShell Programmers Guide], creating
- cmdlets [PowerShell Programmers Guide], basic cmdlet
ms.assetid: 54236ef3-82db-45f8-9114-1ecb7ff65d3e
caps.latest.revision: 8
ms.openlocfilehash: af41c2c9855310d047404114a07b27180a7aa8fc
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74415679"
---
# <a name="creating-a-cmdlet-without-parameters"></a>매개 변수 없이 Cmdlet 만들기

이 섹션에서는 매개 변수를 사용 하지 않고 로컬 컴퓨터에서 정보를 검색 한 다음 파이프라인에 정보를 기록 하는 cmdlet을 만드는 방법을 설명 합니다. 여기에 설명 된 cmdlet은 로컬 컴퓨터의 프로세스에 대 한 정보를 검색 한 다음 명령줄에 해당 정보를 표시 하는 cmdlet입니다.

> [!NOTE]
> Cmdlet을 작성할 때 Windows PowerShell® 참조 어셈블리가 디스크에 다운로드 됩니다 (기본적으로 C:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\v1.0). GAC (전역 어셈블리 캐시)에 설치 되지 않습니다.

## <a name="naming-the-cmdlet"></a>Cmdlet 이름 지정

Cmdlet 이름은 cmdlet이 수행 하는 동작을 나타내는 동사와 cmdlet이 작동 하는 항목을 나타내는 명사로 구성 됩니다. 이 샘플 실행 cmdlet은 프로세스 개체를 검색 하기 때문에 [Verbscommon](/dotnet/api/System.Management.Automation.VerbsCommon) 열거에 의해 정의 된 동사 "Get"을 사용 하 고, cmdlet이 프로세스 항목에서 작동 함을 나타내는 명사 "Proc"를 사용 합니다.

Cmdlet의 이름을 지정할 때는 다음 문자를 사용 하지 마세요. #, () {} [] &-/\ $; : "' < > &#124; ? @ ` .

### <a name="choosing-a-noun"></a>명사 선택

특정 명사를 선택 해야 합니다. 제품 이름의 축약 된 버전이 포함 된 단 수 명사를 사용 하는 것이 가장 좋습니다. 이 유형의 cmdlet 이름 예는 "`Get-SQLServer`"입니다.

### <a name="choosing-a-verb"></a>동사 선택

승인 된 cmdlet 동사 이름 집합의 동사를 사용 해야 합니다. 승인 된 cmdlet 동사에 대 한 자세한 내용은 [Cmdlet 동사 이름](./approved-verbs-for-windows-powershell-commands.md)을 참조 하세요.

## <a name="defining-the-cmdlet-class"></a>Cmdlet 클래스 정의

Cmdlet 이름을 선택한 후에는 cmdlet을 구현 하는 .NET 클래스를 정의 합니다. 다음은이 샘플의 Get-help cmdlet에 대 한 클래스 정의입니다.

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

클래스 정의의 이전에는 `[Cmdlet(verb, noun, ...)]`구문을 사용 하 여이 클래스를 cmdlet으로 식별 하는 데 사용 [됩니다.](/dotnet/api/System.Management.Automation.CmdletAttribute) 이는 모든 cmdlet에 대해 유일 하 게 필요한 특성이 며 Windows PowerShell 런타임에서 올바르게 호출할 수 있습니다. 필요한 경우 특성 키워드를 설정 하 여 클래스를 추가로 선언할 수 있습니다. 샘플 GetProcCommand 클래스에 대 한 특성 선언은 Get Proc cmdlet에 대 한 명사 및 verb 이름만 선언 합니다.

> [!NOTE]
> 모든 Windows PowerShell 특성 클래스에 대해 설정할 수 있는 키워드는 특성 클래스의 속성에 해당 합니다.

Cmdlet의 클래스 이름을 지정할 때는 클래스 이름에 cmdlet 이름을 반영 하는 것이 좋습니다. 이렇게 하려면 "VerbNounCommand" 형식을 사용 하 고 cmdlet 이름에 사용 되는 동사 및 명사로 "Verb" 및 "명사"를 바꿉니다. 위의 클래스 정의에 표시 된 것 처럼 샘플 Get Proc cmdlet은 GetProcCommand 라는 클래스를 정의 합니다 .이 클래스는 [system.object](/dotnet/api/System.Management.Automation.Cmdlet) 기본 클래스에서 파생 됩니다.

> [!IMPORTANT]
> Windows PowerShell 런타임에 액세스 하는 cmdlet을 직접 정의 하려면 .NET 클래스가 [PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) 기본 클래스에서 파생 되어야 합니다. 이 클래스에 대 한 자세한 내용은 [매개 변수 집합을 정의 하는 Cmdlet 만들기](./adding-parameter-sets-to-a-cmdlet.md)를 참조 하세요.

> [!NOTE]
> Cmdlet에 대 한 클래스는 명시적으로 public으로 표시 되어야 합니다. Public으로 표시 되지 않은 클래스는 기본적으로 내부로 표시 되 고 Windows PowerShell 런타임에는 검색 되지 않습니다.

Windows PowerShell은 cmdlet 클래스에 대해 [Microsoft. powershell](/dotnet/api/Microsoft.PowerShell.Commands) 네임 스페이스를 사용 합니다. API 네임 스페이스의 Commands 네임 스페이스에 cmdlet 클래스를 추가 하는 것이 좋습니다 (예: xxx. p. p. p. s.

## <a name="overriding-an-input-processing-method"></a>입력 처리 메서드 재정의

[System.object](/dotnet/api/System.Management.Automation.Cmdlet) 클래스는 세 가지 주요 입력 처리 메서드를 제공 합니다 .이 중 하나는 Cmdlet에서 재정의 해야 합니다. Windows PowerShell에서 레코드를 처리 하는 방법에 대 한 자세한 내용은 [Windows powershell의 작동 방식](/previous-versions//ms714658(v=vs.85))을 참조 하세요.

모든 형식의 입력에 대해 Windows PowerShell 런타임은 처리를 사용 하기 위해 [system.object](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) 를 호출 합니다. Cmdlet에서 일부 전처리 또는 설치를 수행 해야 하는 경우이 메서드를 재정의 하 여이 작업을 수행할 수 있습니다.

> [!NOTE]
> Windows PowerShell은 "record" 라는 용어를 사용 하 여 cmdlet이 호출 될 때 제공 되는 매개 변수 값 집합을 설명 합니다.

Cmdlet이 파이프라인 입력을 허용 하는 경우 [ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) 메서드를 재정의 하 고 필요에 따라 [system.object](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) 를 재정의 해야 합니다. 예를 들어, cmdlet은 [ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) 를 사용 하 여 모든 입력을 수집한 다음 `Sort-Object` cmdlet이 수행 하는 것 처럼 한 번에 하나의 요소 대신 전체 입력에서 작동 하는 경우 두 메서드를 재정의할 수 있습니다.

Cmdlet이 파이프라인 입력을 사용 하지 않는 경우에는 [system.object](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) 를 재정의 해야 합니다. 이 메서드는 정렬 cmdlet의 경우와 같이 한 번에 하나의 요소에 대해 실행 될 수 [없는 경우에](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) 는이 메서드를 사용 하는 것이 일반적입니다.

이 Get-Proc cmdlet 샘플은 파이프라인 입력을 수신해야 하므로, [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) 메서드를 재정의 하고, [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) 및 [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)를 기본 구현에 사용합니다. [ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) 재정의는 프로세스를 검색 하 고 [WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) 메서드를 사용 하 여이를 명령줄에 기록 합니다.

```csharp
protected override void ProcessRecord()
{
  // Get the current processes
  Process[] processes = Process.GetProcesses();

  // Write the processes to the pipeline making them available
  // to the next cmdlet. The second parameter of this call tells
  // PowerShell to enumerate the array, and send one process at a
  // time to the pipeline.
  WriteObject(processes, true);
}
```

```vb
Protected Overrides Sub ProcessRecord()

    '/ Get the current processes.
    Dim processes As Process()
    processes = Process.GetProcesses()

    '/ Write the processes to the pipeline making them available
    '/ to the next cmdlet. The second parameter of this call tells
    '/ PowerShell to enumerate the array, and send one process at a
    '/ time to the pipeline.
    WriteObject(processes, True)

End Sub 'ProcessRecord
```

#### <a name="things-to-remember-about-input-processing"></a>입력 처리에 대해 기억할 사항

- 입력의 기본 소스는 명령줄에서 사용자가 제공 하는 명시적 개체 (예: 문자열)입니다. 자세한 내용은 [명령줄 입력을 처리 하는 Cmdlet 만들기](./adding-parameters-that-process-command-line-input.md)를 참조 하세요.

- 입력 처리 메서드는 파이프라인의 업스트림 cmdlet 출력 개체에서 입력을 받을 수도 있습니다. 자세한 내용은 [파이프라인을 만들어 파이프라인 입력 처리를](./adding-parameters-that-process-pipeline-input.md)참조 하세요. Cmdlet은 명령줄 및 파이프라인 원본 조합에서 입력을 받을 수 있습니다.

- 다운스트림 cmdlet은 오랜 시간 동안 반환 되지 않을 수도 있고 그렇지 않을 수도 있습니다. 이러한 이유로, cmdlet의 입력 처리 메서드는 [WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)를 호출 하는 동안 잠금을 유지 하면 안 됩니다. 특히 범위가 cmdlet 인스턴스 이상으로 확장 됩니다.

> [!IMPORTANT]
> Cmdlet은 [system.web. Writeline *](/dotnet/api/System.Console.WriteLine) 또는 이와 동등한 것을 호출 하면 안 됩니다.

- Cmdlet에는 처리가 완료 될 때 정리 하는 개체 변수가 있을 수 [있습니다. 예](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) 를 들어, [ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)에서 파일 핸들을 열고이를 사용 하기 위해 핸들을 열어 둘 수 있습니다. Windows PowerShell 런타임은 개체 정리를 수행 해야 하는 항상 [system.object](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) 를 호출 하는 것은 아닙니다.

예를 들어 cmdlet을 중간에 취소 하거나 cmdlet의 일부에서 종료 오류가 발생 하는 경우에는 [system.object](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) 를 호출할 수 없습니다. 따라서 개체 정리를 필요로 하는 cmdlet은 종료자를 비롯 [한 전체 system.string](/dotnet/api/System.IDisposable) 패턴을 구현 해야 합니다. 이렇게 하면 런타임에서 처리가 끝날 때 [system.object](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) 와 [system.object](/dotnet/api/System.IDisposable.Dispose) 를 모두 호출할 수 있습니다.

## <a name="code-sample"></a>코드 예제

전체 C# 샘플 코드는 [GetProcessSample01 샘플](./getprocesssample01-sample.md)을 참조 하세요.

## <a name="defining-object-types-and-formatting"></a>개체 형식 및 서식 정의

Windows PowerShell은 .NET 개체를 사용 하 여 cmdlet 간에 정보를 전달 합니다. 따라서 cmdlet은 자체 형식을 정의 해야 할 수도 있고, 다른 cmdlet에서 제공 하는 기존 형식을 cmdlet에서 확장 해야 할 수도 있습니다. 새 형식을 정의 하거나 기존 형식을 확장 하는 방법에 대 한 자세한 내용은 [개체 형식 확장 및 서식 지정](/previous-versions//ms714665(v=vs.85))을 참조 하세요.

## <a name="building-the-cmdlet"></a>Cmdlet 빌드

Cmdlet을 구현한 후 Windows PowerShell 스냅인을 통해 Windows PowerShell에 등록 해야 합니다. Cmdlet을 등록 하는 방법에 대 한 자세한 내용은 [cmdlet, 공급자 및 호스트 응용 프로그램을 등록 하는 방법](/previous-versions//ms714644(v=vs.85))을 참조 하세요.

## <a name="testing-the-cmdlet"></a>Cmdlet 테스트

Windows PowerShell을 사용 하 여 cmdlet을 등록 한 경우 명령줄에서 실행 하 여 테스트할 수 있습니다. 샘플 실행 cmdlet에 대 한 코드는 작지만 Windows PowerShell 런타임과 기존 .NET 개체를 계속 사용 하므로 유용 하 게 사용할 수 있습니다. 이를 테스트 하 여 실행 가능한 프로세스와 해당 출력을 사용할 수 있는 방법을 더 잘 이해할 수 있습니다. 명령줄에서 cmdlet을 사용 하는 방법에 대 한 자세한 내용은 [Windows PowerShell 시작](/powershell/scripting/getting-started/getting-started-with-windows-powershell)을 참조 하세요.

1. Windows PowerShell을 시작 하 고 컴퓨터에서 실행 중인 현재 프로세스를 가져옵니다.

    ```powershell
    get-proc
    ```

    다음 출력이 표시됩니다.

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id   ProcessName
    -------  ------  -----  -----  -----  ------  --   ----------
    254      7       7664   12048  66     173.75  1200  QCTRAY
    32       2       1372   2628   31       0.04  1860  DLG
    271      6       1216   3688   33       0.03  3816  lg
    27       2       560    1920   24       0.01  1768  TpScrex
    ...
    ```

2. 더 쉽게 조작을 위해 변수를 cmdlet 결과에 할당 합니다.

    ```powershell
    $p=get-proc
    ```

3. 프로세스 수를 가져옵니다.

    ```powershell
    $p.length
    ```

    다음 출력이 표시됩니다.

    ```output
    63
    ```

4. 특정 프로세스를 검색 합니다.

    ```powershell
    $p[6]
    ```

    다음 출력이 표시됩니다.

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id    ProcessName
    -------  ------  -----  -----  -----  ------  --    -----------
    1033     3       2400   3336   35     0.53    1588  rundll32
    ```

5. 이 프로세스의 시작 시간을 가져옵니다.

    ```powershell
    $p[6].starttime
    ```

    다음 출력이 표시됩니다.

    ```output
    Tuesday, July 26, 2005 9:34:15 AM
    ```

    ```powershell
    $p[6].starttime.dayofyear
    ```

    ```output
    207
    ```

6. 핸들 수가 500 보다 큰 프로세스를 가져오고 결과를 정렬 합니다.

    ```powershell
    $p | Where-Object {$_.HandleCount -gt 500 } | Sort-Object HandleCount
    ```

    다음 출력이 표시됩니다.

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id   ProcessName
    -------  ------  -----  -----  -----  ------  --   ----------
    568      14      2164   4972   39     5.55    824  svchost
    716       7      2080   5332   28    25.38    468  csrss
    761      21      33060  56608  440  393.56    3300 WINWORD
    791      71      7412   4540   59     3.31    492  winlogon
    ...
    ```

7. `Get-Member` cmdlet을 사용 하 여 각 프로세스에 사용할 수 있는 속성을 나열 합니다.

    ```powershell
    $p | Get-Member -MemberType property
    ```

    ```output
        TypeName: System.Diagnostics.Process
    ```

    다음 출력이 표시됩니다.

    ```output
    Name                     MemberType Definition
    ----                     ---------- ----------
    BasePriority             Property   System.Int32 BasePriority {get;}
    Container                Property   System.ComponentModel.IContainer Conta...
    EnableRaisingEvents      Property   System.Boolean EnableRaisingEvents {ge...
    ...
    ```

## <a name="see-also"></a>참고 항목

[명령줄 입력을 처리 하는 Cmdlet 만들기](./adding-parameters-that-process-command-line-input.md)

[파이프라인을 만들어 파이프라인 입력 처리](./adding-parameters-that-process-pipeline-input.md)

[Windows PowerShell Cmdlet을 만드는 방법](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

[개체 형식 및 서식 확장](/previous-versions//ms714665(v=vs.85))

[Windows PowerShell 작동 방법](/previous-versions//ms714658(v=vs.85))

[Cmdlet, 공급자 및 호스트 응용 프로그램을 등록 하는 방법](/previous-versions//ms714644(v=vs.85))

[Windows PowerShell 참조](../windows-powershell-reference.md)

[Cmdlet 샘플](./cmdlet-samples.md)
