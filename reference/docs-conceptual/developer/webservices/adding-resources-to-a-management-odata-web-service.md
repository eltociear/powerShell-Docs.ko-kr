---
title: 관리 OData 웹 서비스에 리소스 추가 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e620bf6d-76be-47b0-a7a8-f43418f30c60
caps.latest.revision: 6
ms.openlocfilehash: b81a32b867795ae51c3f5308c2f82c31ed2747fa
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72359822"
---
# <a name="adding-resources-to-a-management-odata-web-service"></a>관리 OData 웹 서비스에 리소스 추가

이 예제에서는 관리 OData 스키마 디자이너를 사용 하 여 기존 관리 OData 웹 서비스에 리소스를 추가 하는 방법을 보여 줍니다. [PswsRoleBasedPlugins](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a) 샘플은 프로세스 및 서버 리소스를 노출 하는 웹 서비스를 만듭니다. 이 예제에서는 웹 서비스에 VM (가상 컴퓨터) 리소스를 추가 합니다.

## <a name="prerequisites"></a>전제 조건

이 항목에서는 [Windows PowerShell 웹 서비스 만들기](./creating-a-management-odata-web-service.md)에 설명 된 대로 [PswsRoleBasedPlugins](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a) 샘플을 다운로드 하 여 설치 하 고 [관리 OData 스키마 디자이너](https://marketplace.visualstudio.com/items?itemName=jlisc0.ManagementODataSchemaDesigner)를 다운로드 하 여 설치 했다고 가정 합니다. 또한이 항목에서는 관리 Odata 끝점을 설정 하는 컴퓨터에 Hyper-v Windows PowerShell 모듈이 설치 되어 있다고 가정 합니다.

## <a name="adding-vm-as-a-resource-to-the-web-service"></a>웹 서비스에 리소스로 VM 추가

첫 번째 단계는 기존 관리 OData 끝점에서 스키마 디자이너로 스키마를 가져오는 것입니다. 다음 절차에서는이 작업을 수행 하는 방법을 설명 합니다.

#### <a name="importing-an-existing-schema-into-the-schema-designer"></a>스키마 디자이너로 기존 스키마 가져오기

1. 관리 OData 스키마 디자이너를 엽니다.

2. **파일** 메뉴에서 **파일** 을 선택 합니다. **새로 만들기** **파일**. **새 파일** 대화 상자가 나타납니다.

3. **관리 OData 모델**을 클릭 한 다음 **열기**를 클릭 합니다.

4. 주 창을 마우스 오른쪽 단추로 클릭 하 고 **스키마 파일** 을 클릭 합니다. **가져오기**. **열기** 대화 상자가 나타납니다.

5. [PswsRoleBasedPlugins](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a) 샘플에 대 한 관리 OData 웹 서비스를 설정한 폴더로 이동 합니다. 해당 샘플과 함께 제공 된 Windows PowerShell 스크립트를 사용 하 여 스크립트를 수정 하지 않고 끝점을 설정 하면 해당 폴더는 **C:\inetpub\wwwroot\Modata**됩니다. Schema .mof를 선택 하 고 **열기**를 클릭 합니다.

   이 시점에서 텍스트 편집기에서 스키마 .mof 및 스키마 .xml 파일을 열고 프로세스 및 서비스 리소스에 대 한 매핑을 포함 하 고 있는지 확인 합니다. Schema .mof 파일은 DTMF ( [Distributed Management Task Force](https://www.dmtf.org/) ) Mof (Managed Object) 표준을 사용 합니다. Schema .xml 파일은 [리소스 매핑 스키마](./resource-mapping-schema.md)에 설명 된 xml 스키마를 사용 합니다.

   다음 절차에서는의 Hyper-v cmdlet을 스키마 모델로 가져오는 방법을 설명 합니다.

#### <a name="importing-cmdlets-into-the-schema"></a>Cmdlet을 스키마로 가져오기

1. 스키마 디자이너 창의 빈 영역을 마우스 오른쪽 단추로 클릭 하 고 **Cmdlet 가져오기**를 클릭 합니다. **Cmdlet 가져오기 마법사** 대화 상자가 나타납니다.

2. **로컬 컴퓨터** 가 선택 되어 있는지 확인 하 고 **다음**을 클릭 합니다.

3. 설치 된 Windows PowerShell 모듈이 선택 되어 있는지 확인 하 고 드롭다운 목록에서 Hyper-v를 선택 합니다. **다음**을 클릭합니다. 클릭 하 여 **다음**.

4. **Cmdlet 명사** 목록에서 **VM**을 선택 합니다. **다음**을 클릭합니다.

5. 이 예에서는 cmdlet을 사용 하 여 Get 및 Delete 명령만 바인딩합니다. **만들기** 및 **업데이트** 확인란의 선택을 취소 하 고 **가져오기** 및 **삭제** 확인란을 선택 했는지 확인 합니다. **GET**에 `Get-VM` cmdlet을 선택 하 고 `Remove-VM` Cmdlet을 **삭제**하도록 선택 해야 합니다.

6. VM cmdlet에 대 한 메타 데이터는 출력 유형을 지정 하지 않으므로 cmdlet을 실행 하 여 출력 유형을 지정 해야 합니다. **출력 유형 제공** 을 선택 하 고 **cmdlet 실행**을 클릭 합니다. **Cmdlet 실행** 대화 상자가 나타납니다. **실행**을 클릭합니다. **CLR 유형** 상자는 `VirtualMachine` 유형으로 채워집니다. **확인**을 클릭 한 후 **다음**을 클릭 합니다.

7. 기본적으로 VirtualMachine 개체의 모든 속성이 선택 됩니다. 웹 서비스에서이 리소스를 요청할 때 반환 되는 데이터의 일부로 원하지 않는 속성은 모두 지울 수 있습니다. 클릭 하 여 **다음**.

8. 키로 사용할 속성을 하나 이상 선택 해야 합니다. 목록에서 **이름** 을 선택 하 고 **다음**을 클릭 합니다.

9. 다음 창에서는 관리 OData 리소스의 속성을 기본 cmdlet의 속성에 매핑할 수 있습니다. 마법사는 기본적으로 동일한 이름의 속성을 매핑합니다. 예를 들어 리소스의 `ComputerName` 속성은 cmdlet의 `ComputerName` 속성에 매핑됩니다.  이를 통해 웹 서비스에 대 한 요청에서 `ComputerName` 속성을 지정 하 고 지정 하는 값을 `Get-VM` cmdlet으로 전달할 수 있습니다. `Id` 및 `Name`도 기본적으로 매핑됩니다.

   10. **다음**을 클릭 한 다음 **마침**을 클릭 합니다.

       이제 VM 리소스가 스키마 디자이너 창에 표시 됩니다. 리소스와 연결 된 속성 및 작업을 검토할 수 있습니다. 다음에는 업데이트 된 스키마 파일을 웹 서비스의 가상 디렉터리로 내보냅니다.

#### <a name="exporting-schema-files-from-the-schema-designer"></a>스키마 디자이너에서 스키마 파일 내보내기

1. 스키마 디자이너 창의 빈 영역을 마우스 오른쪽 단추로 클릭 하 고 **스키마 파일** 을 클릭 합니다. **내보내기**. 다른 **이름으로 저장** 대화 상자가 나타납니다.

2. MOF 파일을 가져온 디렉터리와 동일한 디렉터리로 이동 합니다. 파일의 이름을 원래 MOF 파일 (기본적으로 Schema .mof)와 동일 하 게 이름을로 하 고 **저장**을 클릭 합니다. 기존 파일을 덮어쓸 것인지 확인 합니다.

   **다른 이름으로 저장** 대화 상자에는 명시적으로 명시 되어 있지 않지만 스키마와 스키마 .xml 파일이 모두 바뀝니다.

## <a name="next-steps"></a>다음 단계

관리 OData 웹 서비스에서 새 VM 리소스에 액세스 하기 전에 [역할 기반 권한 부여 구성](./configuring-role-based-authorization.md)에 설명 된 대로 Hyper-v Windows PowerShell 모듈에 대 한 액세스를 허용 하도록 RbacConfiguration 파일을 업데이트 해야 합니다. 또한 웹 서비스를 다시 시작 해야 합니다.