---
title: 서식 지정 데이터 로드 및 내보내기 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a48de31-7961-4b0e-b58b-93466e38370b
caps.latest.revision: 6
ms.openlocfilehash: 5c5168ffd74c15066b914ad1b39d9ead947c5e7f
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365122"
---
# <a name="loading-and-exporting-formatting-data"></a><span data-ttu-id="48835-102">형식 지정 데이터 로드 및 내보내기</span><span class="sxs-lookup"><span data-stu-id="48835-102">Loading and Exporting Formatting Data</span></span>

<span data-ttu-id="48835-103">서식 파일을 만든 후에는 현재 세션으로 파일을 로드 하 여 세션의 형식 데이터를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48835-103">Once you have created your formatting file, you need to update the format data of the session by loading your files into the current session.</span></span> <span data-ttu-id="48835-104">Windows PowerShell에서 제공 하는 형식 지정 파일은 현재 세션을 열 때 등록 된 스냅인에 의해 로드 됩니다. 현재 세션의 형식 데이터가 업데이트 되 면 Windows PowerShell은 해당 데이터를 사용 하 여 로드 된 서식 지정 파일에 정의 된 뷰와 관련 된 .NET 개체를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="48835-104">(The formatting files provided by Windows PowerShell are loaded by snap-ins that are registered when the current session is opened.) Once the format data of the current session is updated, Windows PowerShell uses that data to display the .NET objects associated with the views defined in the loaded formatting files.</span></span> <span data-ttu-id="48835-105">현재 세션으로 로드할 수 있는 형식 지정 파일의 수에는 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="48835-105">There is no limit to the number of formatting files that you can load into the current session.</span></span> <span data-ttu-id="48835-106">형식 지정 데이터를 업데이트 하는 것 외에도 현재 세션의 형식 데이터를 서식 파일에 다시 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48835-106">In addition to updating the formatting data, you can export the format data in the current session back to a formatting file.</span></span>

## <a name="loading-format-data"></a><span data-ttu-id="48835-107">서식 데이터 로드</span><span class="sxs-lookup"><span data-stu-id="48835-107">Loading format data</span></span>

<span data-ttu-id="48835-108">다음 메서드를 사용 하 여 형식 지정 파일을 현재 세션으로 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48835-108">Formatting files can be loaded into the current session using the following methods:</span></span>

- <span data-ttu-id="48835-109">명령줄에서 현재 세션으로 서식 파일을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48835-109">You can import the formatting file into the current session from the command line.</span></span> <span data-ttu-id="48835-110">다음 절차에서 설명 하는 것 처럼 [업데이트 FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="48835-110">Use the [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet as described in the following procedure.</span></span>

- <span data-ttu-id="48835-111">서식 파일을 참조 하는 모듈 매니페스트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48835-111">You can create a module manifest that references your formatting file.</span></span> <span data-ttu-id="48835-112">모듈을 사용 하 여 배포용으로 서식 지정 파일을 패키지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48835-112">Modules allow you to package you formatting files for distribution.</span></span> <span data-ttu-id="48835-113">[New-modulemanifest](/powershell/module/Microsoft.PowerShell.Core/New-ModuleManifest) cmdlet을 사용 하 여 매니페스트를 만들고 [import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet을 사용 하 여 모듈을 현재 세션으로 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="48835-113">Use the [New-ModuleManifest](/powershell/module/Microsoft.PowerShell.Core/New-ModuleManifest) cmdlet to create the manifest, and the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet to load the module into the current session.</span></span> <span data-ttu-id="48835-114">모듈에 대 한 자세한 내용은 [Windows PowerShell 모듈 작성](../module/writing-a-windows-powershell-module.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="48835-114">For more information about modules, see [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).</span></span>

- <span data-ttu-id="48835-115">서식 파일을 참조 하는 스냅인을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48835-115">You can create a snap-in that references your formatting file.</span></span> <span data-ttu-id="48835-116">[Add-pssnapin](/dotnet/api/System.Management.Automation.PSSnapIn.Formats) 를 사용 하 여 형식 지정 파일을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="48835-116">Use the [System.Management.Automation.PSSnapIn.Formats](/dotnet/api/System.Management.Automation.PSSnapIn.Formats) to reference your formatting files.</span></span> <span data-ttu-id="48835-117">Cmdlet을 패키지 하는 데 모듈을 사용 하 고 배포를 위해 관련 형식 지정 및 형식 파일을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="48835-117">It is strongly encouraged to use modules to package cmdlets, and any associated formatting and types files for distribution.</span></span> <span data-ttu-id="48835-118">모듈에 대 한 자세한 내용은 [Windows PowerShell 모듈 작성](../module/writing-a-windows-powershell-module.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="48835-118">For more information about modules, see [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).</span></span>

- <span data-ttu-id="48835-119">명령을 프로그래밍 방식으로 호출 하는 경우 명령이 실행 되는 runspace의 초기 세션 상태에 서식 파일 항목을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48835-119">If you are invoking commands programmatically, you can add a formatting file entry to the initial session state of the runspace where the commands are run.</span></span> <span data-ttu-id="48835-120">형식 지정 파일을 추가 하는 데 사용 되는 .NET 형식에 대 한 자세한 내용은 Runspace를 참조 하세요. [ Displayproperty = Fullname](/dotnet/api/System.Management.Automation.Runspaces.SessionStateFormatEntry) 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="48835-120">For more information about .NET type used to add the formatting file, see the [System.Management.Automation.Runspaces.Sessionstateformatentry?Displayproperty=Fullname](/dotnet/api/System.Management.Automation.Runspaces.SessionStateFormatEntry) class.</span></span>

<span data-ttu-id="48835-121">서식 파일이 로드 되 면 Windows PowerShell에서 명령줄에 개체를 표시할 때 사용할 뷰를 결정 하는 데 사용 하는 내부 목록에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48835-121">When a formatting file is loaded, it is added to an internal list that Windows PowerShell uses to determine which view to use when displaying objects at the command line.</span></span> <span data-ttu-id="48835-122">서식 파일 앞에 서식 파일을 추가 하거나 목록의 끝에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48835-122">You can prepend your formatting file to the beginning of the list, or you can append it to the end of the list.</span></span> <span data-ttu-id="48835-123">Windows PowerShell core cmdlet에서 반환 되는 개체를 변경 하려는 경우와 같이 기존 보기가 정의 된 개체에 대 한 뷰를 정의 하는 형식 지정 파일을 로드 하는 경우 서식 파일을이 목록에 추가 하는 것이 중요 합니다.  표시할지.</span><span class="sxs-lookup"><span data-stu-id="48835-123">Knowing where your formatting file is added to this list is important if you are loading formatting file that defines a view for an object that has an existing view defined, such as when you want to change how an object that is returned by a Windows PowerShell core cmdlet is displayed.</span></span> <span data-ttu-id="48835-124">개체에 대 한 유일한 뷰를 정의 하는 서식 파일을 로드 하는 경우 앞에서 설명한 방법 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48835-124">If you are loading a formatting file that defines the only view for an object, you can use any of the methods described previously.</span></span>  <span data-ttu-id="48835-125">개체에 대 한 다른 뷰를 정의 하는 서식 파일을 로드 하는 경우에는 [업데이트 FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet을 사용 하 고 파일 앞에 파일을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48835-125">If you are loading a formatting file that defines another view for an object, you must use the [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet and prepend your file to the beginning of the list.</span></span>

## <a name="storing-your-formatting-file"></a><span data-ttu-id="48835-126">서식 파일 저장</span><span class="sxs-lookup"><span data-stu-id="48835-126">Storing Your Formatting File</span></span>

<span data-ttu-id="48835-127">포맷 파일이 디스크에 저장 되는 위치에 대 한 요구 사항은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="48835-127">There is no requirement for where your formatting files are stored on disk.</span></span> <span data-ttu-id="48835-128">그러나 다음 폴더에 저장 하는 것이 좋습니다. `user\documents\windowspowershell\`</span><span class="sxs-lookup"><span data-stu-id="48835-128">However, it is strongly suggested that you store them in the following folder: `user\documents\windowspowershell\`</span></span>

#### <a name="loading-a-format-file-using-import-formatdata"></a><span data-ttu-id="48835-129">Formatformatdata를 사용 하 여 서식 파일 로드</span><span class="sxs-lookup"><span data-stu-id="48835-129">Loading a format file using Import-FormatData</span></span>

1. <span data-ttu-id="48835-130">포맷 파일을 디스크에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="48835-130">Store your formatting file to disk.</span></span>

2. <span data-ttu-id="48835-131">다음 명령 중 하나를 사용 하 여 [업데이트 FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="48835-131">Run the [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet using one of the following commands.</span></span>

   <span data-ttu-id="48835-132">목록 앞에 서식 파일을 추가 하려면이 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="48835-132">To add your formatting file to the front of the list use this command.</span></span> <span data-ttu-id="48835-133">개체 표시 방법을 변경 하는 경우이 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="48835-133">Use this command if you are changing how an object is displayed.</span></span>

   ```powershell
   Update-FormatData -PrependPath PathToFormattingFile
   ```

   <span data-ttu-id="48835-134">형식 지정 파일을 목록의 끝에 추가 하려면이 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="48835-134">To add your formatting file to the end of the list use this command.</span></span>

   ```powershell
   Update-FormatData -AppendPath PathToFormattingFile
   ```

   <span data-ttu-id="48835-135">[업데이트-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet을 사용 하 여 파일을 추가한 후에는 세션이 열려 있는 동안 목록에서 파일을 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="48835-135">Once you have added a file using the [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) cmdlet, you cannot remove the file from the list while the session is open.</span></span> <span data-ttu-id="48835-136">목록에서 서식 파일을 제거 하려면 세션을 닫아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48835-136">You must close the session to remove the formatting file from the list.</span></span>

## <a name="exporting-format-data"></a><span data-ttu-id="48835-137">서식 데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="48835-137">Exporting format data</span></span>

<span data-ttu-id="48835-138">여기에 섹션 본문을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="48835-138">Insert section body here.</span></span>