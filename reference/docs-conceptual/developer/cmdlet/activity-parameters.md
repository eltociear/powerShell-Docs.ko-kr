---
title: 활동 매개 변수 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e4e0cf6-19e0-44b8-8b40-d6f6075276cf
caps.latest.revision: 5
ms.openlocfilehash: 489d8bcdabe904d6a3d2bc6cdb9d7e23d09cbef2
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364642"
---
# <a name="activity-parameters"></a>활동 매개 변수

다음 표에서는 작업 매개 변수의 권장 이름 및 기능을 보여 줍니다.

|매개 변수|기능|
|---|---|
|**추가**<br>데이터 형식: SwitchParameter|매개 변수가 지정 된 경우 사용자가 리소스의 끝에 콘텐츠를 추가할 수 있도록이 매개 변수를 구현 합니다.|
|**CaseSensitive**<br>데이터 형식: SwitchParameter|이 매개 변수를 구현 하 여 사용자가 매개 변수를 지정할 때 대/소문자 구분을 요구할 수 있도록 합니다.|
|**Command**<br>데이터 형식: 문자열|사용자가 실행할 명령 문자열을 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**CompatibleVersion**<br>데이터 형식: System.object 개체|이 매개 변수를 구현 하 여 사용자가 이전 버전과의 호환성을 위해 cmdlet이 호환 되어야 하는 의미 체계를 지정할 수 있도록 합니다.|
|**압축**<br>데이터 형식: SwitchParameter|매개 변수를 지정할 때 데이터 압축이 사용 되도록이 매개 변수를 구현 합니다.|
|**압축**<br>데이터 형식: 키워드|사용자가 데이터 압축에 사용할 알고리즘을 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**주기가**<br>데이터 형식: SwitchParameter|매개 변수가 지정 될 때 사용자가 cmdlet을 종료할 때까지 데이터를 처리 하도록이 매개 변수를 구현 합니다. 매개 변수를 지정 하지 않으면 cmdlet이 미리 정의 된 양의 데이터를 처리 한 다음 작업을 종료 합니다.|
|**만들기**<br>데이터 형식: SwitchParameter|이 매개 변수를 구현 하 여 매개 변수를 지정할 때 리소스가 아직 없는 경우이를 만들도록 지정 합니다.|
|**Delete**<br>데이터 형식: SwitchParameter|매개 변수가 지정 된 경우 cmdlet이 작업을 완료 했을 때 리소스가 삭제 되도록이 매개 변수를 구현 합니다.|
|**방전**<br>데이터 형식: SwitchParameter|매개 변수가 지정 된 경우 cmdlet이 새 데이터를 처리 하기 전에 처리 중인 작업 항목이 처리 됨을 나타내려면이 매개 변수를 구현 합니다. 매개 변수를 지정 하지 않으면 작업 항목이 즉시 처리 됩니다.|
|**Erase**<br>데이터 형식: Int32|사용자가 리소스를 삭제 하기 전에 삭제 되는 횟수를 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**ErrorLevel**<br>데이터 형식: Int32|사용자가 보고할 오류 수준을 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**제외**<br>데이터 형식: String []|사용자가 활동에서 항목을 제외할 수 있도록이 매개 변수를 구현 합니다. 입력 필터를 사용 하는 방법에 대 한 자세한 내용은 [입력 필터 매개 변수](input-filter-parameters.md)를 참조 하세요.|
|**Assert**<br>데이터 형식: 키워드|이 매개 변수를 구현 하 여 사용자가 cmdlet 작업을 수행할 리소스를 선택 하는 필터를 지정할 수 있도록 합니다. 입력 필터를 사용 하는 방법에 대 한 자세한 내용은 [입력 필터 매개 변수](./input-filter-parameters.md)를 참조 하세요.|
|**따르세요**<br>데이터 형식: SwitchParameter|매개 변수가 지정 된 경우 진행률이 추적 되도록이 매개 변수를 구현 합니다.|
|**설정**<br>데이터 형식: SwitchParameter|매개 변수를 지정할 때 제한이 발생 하더라도 사용자가 작업을 수행할 수 있음을 나타내려면이 매개 변수를 구현 합니다. 매개 변수는 보안이 손상 되는 것을 허용 하지 않습니다. 예를 들어이 매개 변수를 사용 하면 사용자가 읽기 전용 파일을 덮어쓸 수 있습니다.|
|**포함**<br>데이터 형식: String []|사용자가 활동에 항목을 포함할 수 있도록이 매개 변수를 구현 합니다. 입력 필터를 사용 하는 방법에 대 한 자세한 내용은 [입력 필터 매개 변수](input-filter-parameters.md)를 참조 하세요.|
|**증분**<br>데이터 형식: SwitchParameter|이 매개 변수를 구현 하 여 매개 변수가 지정 될 때 처리가 증분 수행 됨을 표시 합니다. 예를 들어이 매개 변수를 통해 사용자는 마지막 백업 이후에만 파일을 백업 하는 증분 백업을 수행할 수 있습니다.|
|**InputObject**<br>데이터 형식: Object|Cmdlet이 다른 cmdlet의 입력을 사용 하는 경우이 매개 변수를 구현 합니다. **InputObject** 매개 변수를 정의할 때 **매개 변수** 특성을 선언할 때 항상 **ValueFromPipeline** 키워드를 지정 합니다. 입력 필터를 사용 하는 방법에 대 한 자세한 내용은 [입력 필터 매개 변수](./input-filter-parameters.md)를 참조 하세요.|
|**Insert**<br>데이터 형식: SwitchParameter|매개 변수가 지정 된 경우 cmdlet이 항목을 삽입 하도록이 매개 변수를 구현 합니다.|
|**대화형**<br>데이터 형식: SwitchParameter|매개 변수가 지정 된 경우 cmdlet이 사용자와 대화형으로 작동 하도록이 매개 변수를 구현 합니다.|
|**간격**<br>데이터 형식: 해시 테이블|사용자가 값을 포함 하는 키워드의 해시 테이블을 지정할 수 있도록이 매개 변수를 구현 합니다. 다음 예에서는 **Interval** 매개 변수에 대 한 샘플 값을 보여 줍니다. `-interval @{ResumeScan=15; Retry=3}`.|
|**Log**<br>데이터 형식: SwitchParameter|매개 변수가 지정 된 경우이 매개 변수를 구현 하 여 cmdlet의 동작을 감사 합니다.|
|**NoClobber**<br>데이터 형식: SwitchParameter|매개 변수를 지정할 때 리소스를 덮어쓰지 않도록이 매개 변수를 구현 합니다. 이 매개 변수는 일반적으로 새 개체를 만드는 cmdlet에 적용 되므로 이름이 같은 기존 개체를 덮어쓸 수 없습니다.|
|**되었음을**<br>데이터 형식: SwitchParameter|매개 변수를 지정할 때 작업이 완료 되었다는 알림이 사용자에 게 표시 되도록이 매개 변수를 구현 합니다.|
|**NotifyAddress**<br>데이터 형식: 전자 메일 주소|**알림 매개 변수가** 지정 된 경우 사용자가 알림을 보내는 데 사용할 전자 메일 주소를 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**Overwrite**<br>데이터 형식: SwitchParameter|매개 변수가 지정 된 경우 cmdlet이 기존 데이터를 덮어쓰도록이 매개 변수를 구현 합니다.|
|**프롬프트**<br>데이터 형식: 문자열|사용자가 cmdlet에 대 한 프롬프트를 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**자동**<br>데이터 형식: SwitchParameter|매개 변수가 지정 된 경우 cmdlet이 작업 중에 사용자 피드백을 표시 하지 않도록 하려면이 매개 변수를 구현 합니다.|
|**Recurse**<br>데이터 형식: SwitchParameter|매개 변수가 지정 된 경우 cmdlet이 리소스에 대 한 작업을 재귀적으로 수행 하도록이 매개 변수를 구현 합니다.|
|**Repair**<br>데이터 형식: SwitchParameter|매개 변수가 지정 된 경우 cmdlet이 손상 된 상태에서 무언가를 수정 하려고 시도 하도록이 매개 변수를 구현 합니다.|
|**RepairString**<br>데이터 형식: 문자열|사용자가 **Repair** 매개 변수를 지정할 때 사용할 문자열을 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**Retry**<br>데이터 형식: Int32|사용자가 cmdlet에서 작업을 시도 하는 횟수를 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**Select**<br>데이터 형식: 키워드 배열|사용자가 항목 형식의 배열을 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**Stream**<br>데이터 형식: SwitchParameter|매개 변수가 지정 된 경우 사용자가 파이프라인을 통해 여러 출력 개체를 스트리밍할 수 있도록이 매개 변수를 구현 합니다.|
|**Strict**<br>데이터 형식: SwitchParameter|이 매개 변수를 구현 하 여 매개 변수가 지정 된 경우 모든 오류가 종료 오류로 처리 되도록 합니다.|
|**TempLocation**<br>데이터 형식: 문자열|이 매개 변수를 구현 하 여 사용자가 cmdlet 작업 중에 사용 되는 임시 데이터의 위치를 지정할 수 있도록 합니다.|
|**Timeout**<br>데이터 형식: Int32|사용자가 제한 시간 간격 (밀리초)을 지정할 수 있도록이 매개 변수를 구현 합니다.|
|**잘라내야**<br>데이터 형식: SwitchParameter|매개 변수가 지정 된 경우 cmdlet에서 해당 작업을 잘라내는이 매개 변수를 구현 합니다. 매개 변수를 지정 하지 않으면 cmdlet이 다른 작업을 수행 합니다.|
|**확인**<br>데이터 형식: SwitchParameter|Cmdlet에서 매개 변수를 지정할 때 동작이 발생 했는지 여부를 확인 하도록이 매개 변수를 구현 합니다.|
|**Wait**<br>데이터 형식: SwitchParameter|매개 변수가 지정 되 면 계속 하기 전에 cmdlet이 사용자 입력을 대기 하도록이 매개 변수를 구현 합니다.
|**WaitTime**<br>데이터 형식: Int32|**대기** 매개 변수가 지정 된 경우 사용자가 cmdlet이 사용자 입력을 대기 하는 기간 (초)을 지정할 수 있도록이 매개 변수를 구현 합니다.|

## <a name="see-also"></a>참고 항목

[Cmdlet 매개 변수](./cmdlet-parameters.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)(Windows PowerShell Cmdlet 작성)

[Windows PowerShell SDK](../windows-powershell-reference.md)
