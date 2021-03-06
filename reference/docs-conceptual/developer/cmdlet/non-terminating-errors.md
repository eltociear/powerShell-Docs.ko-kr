---
title: 종료 되지 않는 오류 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 468dabd6-bfeb-448d-8e09-0996db516edd
caps.latest.revision: 8
ms.openlocfilehash: 5f804756e0e3e867832f15f50967fd6987f160a5
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369602"
---
# <a name="non-terminating-errors"></a>종료되지 않는 오류

이 항목에서는 종료 되지 않는 오류를 보고 하는 데 사용 되는 방법에 대해 설명 합니다. 또한 cmdlet 내에서 메서드를 호출 하는 방법을 설명 합니다.

종료 되지 않는 오류가 발생 하면 cmdlet은 [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) 메서드를 호출 하 여이 오류를 보고 해야 합니다. Cmdlet에서 종료 되지 않는 오류를 보고 하는 경우 cmdlet은이 입력 개체와 추가로 들어오는 파이프라인 개체에서 계속 작동할 수 있습니다. Cmdlet이 [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) 메서드를 호출 하는 경우 cmdlet은 종료 되지 않는 오류를 발생 시킨 조건을 설명 하는 오류 레코드를 작성할 수 있습니다. 오류 레코드에 대 한 자세한 내용은 [Windows PowerShell 오류 레코드](./windows-powershell-error-records.md)를 참조 하십시오.

Cmdlet은 입력 처리 메서드 내에서 필요에 따라 [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) 를 호출할 수 있습니다. Cmdlet은 [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) 또는 [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) 입력 처리 방법을 부른 스레드에서만 [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)를 호출할 수 있습니다. 다른 스레드에서 [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) 를 호출 하지 마세요. 대신는 주 스레드로 다시 오류를 전달 합니다.

## <a name="see-also"></a>참고 항목

[WriteError입니다.](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[System.object를 처리 합니다.](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[ProcessRecord입니다.](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[System.object..](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[Windows PowerShell 오류 레코드](./windows-powershell-error-records.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)(Windows PowerShell Cmdlet 작성)
