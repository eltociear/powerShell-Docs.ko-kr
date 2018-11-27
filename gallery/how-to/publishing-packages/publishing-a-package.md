---
ms.date: 06/12/2017
contributor: JKeithB
keywords: gallery,powershell,cmdlet,psgallery
title: 항목 만들기 및 게시
ms.openlocfilehash: ced892b558b81c3ef9575b5a01e74932515b412a
ms.sourcegitcommit: 98b7cfd8ad5718efa8e320526ca76c3cc4141d78
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50003783"
---
# <a name="creating-and-publishing-an-item"></a><span data-ttu-id="8ae50-103">항목 만들기 및 게시</span><span class="sxs-lookup"><span data-stu-id="8ae50-103">Creating and publishing an item</span></span>

<span data-ttu-id="8ae50-104">PowerShell 갤러리에서는 안정적인 PoweRShell 모듈, 스크립트 및 DSC 리소스를 게시하여 광범위한 PowerShell 사용자 커뮤니티와 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-104">The PowerShell Gallery is the place to publish and share stable PowerShell modules, scripts, and DSC resources with the broader PowerShell user community.</span></span>

<span data-ttu-id="8ae50-105">이 문서에서는 스크립트나 모듈을 준비하고 PowerShell 갤러리에 게시하는 방법과 중요한 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-105">This article covers the mechanics and important steps for preparing a script or module, and publishing it to the PowerShell Gallery.</span></span>
<span data-ttu-id="8ae50-106">[게시 지침](/powershell/gallery/concepts/publishing-guidelines)을 검토하여 게시하는 항목을 보다 많은 PowerShell 갤러리 사용자들이 활용할 수 있도록 하는 방법을 파악하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-106">We strongly encourage that you review the [Publishing Guidelines](/powershell/gallery/concepts/publishing-guidelines) to understand how to ensure that the items you publish will be more widely accepted by PowerShell Gallery users.</span></span>

<span data-ttu-id="8ae50-107">PowerShell 갤러리에 항목을 게시하기 위한 최소 요구 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-107">The minimum requirements to publish an item to the PowerShell Gallery are:</span></span>

- <span data-ttu-id="8ae50-108">PowerShell 갤러리 계정 및 계정에 연결된 API 키가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-108">Have a PowerShell Gallery account, and the API Key associated with it</span></span>
- <span data-ttu-id="8ae50-109">항목에 필수 메타데이터가 포함되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-109">Ensure Required Metadata is in your item</span></span>
- <span data-ttu-id="8ae50-110">사전 유효성 검사 도구를 사용하여 항목을 게시할 준비가 되었는지를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-110">Use the pre-validation tools to ensure your item is ready to publish</span></span>
- <span data-ttu-id="8ae50-111">Publish-Module 및 Publish-Script 명령을 사용하여 PowerShell 갤러리에 항목을 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-111">Publish the item to the PowerShell Gallery using the Publish-Module and Publish-Script commands</span></span>
- <span data-ttu-id="8ae50-112">항목에 대한 문의 사항이나 문제 제기에 응답해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-112">Responding to questions or concerns about your item</span></span>

<span data-ttu-id="8ae50-113">PowerShell 갤러리에서는 PowerShell 모듈 및 PowerShell 스크립트를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-113">The PowerShell Gallery accepts PowerShell modules and PowerShell scripts.</span></span>
<span data-ttu-id="8ae50-114">여기서 스크립트란 대규모 모듈의 일부분이 아니라 단일 파일인 PowerShell 스크립트를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-114">When we refer to scripts, we mean a PowerShell script that is a single file, and not part of a larger module.</span></span>

## <a name="powershell-gallery-account-and-api-key"></a><span data-ttu-id="8ae50-115">PowerShell 갤러리 계정 및 API 키</span><span class="sxs-lookup"><span data-stu-id="8ae50-115">PowerShell Gallery Account and API Key</span></span>

<span data-ttu-id="8ae50-116">PowerShell 갤러리 계정을 설정하는 방법은 [PowerShell 갤러리 계정 만들기](/powershell/gallery/how-to/publishing-packages/creating-an-account)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ae50-116">See [Creating a PowerShell Gallery Account](/powershell/gallery/how-to/publishing-packages/creating-an-account) for how to set up your PowerShell Gallery account.</span></span>

<span data-ttu-id="8ae50-117">계정을 만들면 항목을 게시하는 데 필요한 API 키를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-117">Once you have created an account, you can get the API Key needed to publish an item.</span></span>
<span data-ttu-id="8ae50-118">계정으로 로그인하고 나면 PowerShell 갤러리 페이지 위쪽에 "등록"이 아닌 사용자 이름이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-118">After you sign in with the account, your username will be displayed at the top of the PowerShell Gallery pages instead of Register.</span></span>
<span data-ttu-id="8ae50-119">사용자 이름을 클릭하면 내 계정 페이지로 이동하게 되며, 이 페이지에서 API 키를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-119">Clicking on your username will take you to the My Account page, where you will find the API Key.</span></span>

<span data-ttu-id="8ae50-120">참고: API 키는 로그인 및 암호와 마찬가지로 안전하게 취급해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-120">Note: The API Key must be treated as securely as your login and password.</span></span>
<span data-ttu-id="8ae50-121">이 키를 사용하면 사용자를 비롯하여 누구나 PowerShell 갤러리에서 소유한 항목을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-121">With this key you, or anyone else, can update any item you own in the PowerShell Gallery.</span></span>
<span data-ttu-id="8ae50-122">따라서 키를 정기적으로 업데이트하는 것이 좋습니다. 내 계정 페이지에서 키 다시 설정을 사용하여 키를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-122">We recommend updating the key regularly, which can be done using Reset Key on your My Account page.</span></span>

## <a name="required-metadata-for-items-published-to-the-powershell-gallery"></a><span data-ttu-id="8ae50-123">PowerShell 갤러리에 게시하는 항목의 필수 메타데이터</span><span class="sxs-lookup"><span data-stu-id="8ae50-123">Required Metadata for Items Published to the PowerShell Gallery</span></span>

<span data-ttu-id="8ae50-124">PowerShell 갤러리에서는 스크립트 또는 모듈 매니페스트에 포함된 메타데이터 필드에서 가져온 정보를 갤러리 사용자에게 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-124">The PowerShell Gallery provides information to gallery users drawn from metadata fields that are included in the script or module manifest.</span></span>
<span data-ttu-id="8ae50-125">따라서 PowerShell 갤러리에 게시할 항목을 만들거나 수정할 때는 항목 매니페스트에서 제공되는 정보에 대한 몇 가지 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-125">Creating or modifying items for publication to the PowerShell Gallery has a small set of requirements for information supplied in the item manifest.</span></span>
<span data-ttu-id="8ae50-126">[게시 지침](/powershell/gallery/concepts/publishing-guidelines)의 항목 메타데이터 섹션을 검토하여 항목 사용자에게 가장 적절한 정보를 제공하는 방법을 파악하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-126">We strongly encourage that you review the Item Metadata section of the [Publishing Guidelines](/powershell/gallery/concepts/publishing-guidelines) to learn how to provide the best information to users with your items.</span></span>

<span data-ttu-id="8ae50-127">[New-ModuleManifest](/powershell/module/microsoft.powershell.core/new-modulemanifest) 및 [New-ScriptFileInfo](/powershell/module/PowerShellGet/New-ScriptFileInfo) cmdlet이 매니페스트 템플릿을 자동으로 생성하며, 모든 매니페스트 요소는 자리 표시자로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-127">The [New-ModuleManifest](/powershell/module/microsoft.powershell.core/new-modulemanifest) and [New-ScriptFileInfo](/powershell/module/PowerShellGet/New-ScriptFileInfo) cmdlets will create the manifest template for you, with placeholders for all the manifest elements.</span></span>

<span data-ttu-id="8ae50-128">이 두 매니페스트에는 게시에 중요한 두 섹션, 즉 PrivateData의 PSData 영역과 기본 키 데이터가 있습니다. PowerShell 모듈 매니페스트의 기본 키 데이터는 PrivateData 섹션을 제외한 모든 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-128">Both manifests have two sections that are important for publishing, the Primary Key Data and PSData area of PrivateData The primary key data in a PowerShell module manifest is everything outside of the PrivateData section.</span></span>
<span data-ttu-id="8ae50-129">기본 키 집합은 사용 중인 PowerShell 버전과 연결되며, 정의되지 않은 키는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-129">The set of primary keys is tied to the version of PowerShell in use, and undefined are not supported.</span></span>
<span data-ttu-id="8ae50-130">PrivateData의 경우에는 새 키를 추가할 수 있으므로 PowerShell 갤러리와 관련된 요소는 PSData에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-130">PrivateData supports adding new keys, so the elements specific to the PowerShell Gallery are in PSData.</span></span>


<span data-ttu-id="8ae50-131">PowerShell 갤러리에 게시하는 항목에 대해 입력해야 하는 가장 중요한 매니페스트 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-131">Manifest elements that are most important to fill in for item you publish to the PowerShell Gallery are:</span></span>

- <span data-ttu-id="8ae50-132">스크립트 또는 모듈 이름 - 스크립트의 경우 .PS1, 모듈의 경우 .PSD1의 이름에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-132">Script or Module Name - Those are drawn from the names of the .PS1 for a script, or the .PSD1 for a module.</span></span>
- <span data-ttu-id="8ae50-133">버전 - 필수 기본 키이며 SemVer 지침의 형식을 따라야 합니다(자세한 내용은 모범 사례 참조).</span><span class="sxs-lookup"><span data-stu-id="8ae50-133">Version - this is a required primary key, format should follow SemVer guidelines (see Best Practices for details)</span></span>
- <span data-ttu-id="8ae50-134">작성자 - 필수 기본 키이며 항목과 연결할 이름을 포함합니다(아래의 작성자 및 소유자 참조).</span><span class="sxs-lookup"><span data-stu-id="8ae50-134">Author - this is a required primary key, and contains the name to be associated with the item (see Authors and Owners, below)</span></span>
- <span data-ttu-id="8ae50-135">설명 - 항목이 수행하는 작업과 항목 사용을 위한 요구 사항을 간략하게 설명하는 데 사용되는 필수 기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-135">Description - this is a required primary key, used to briefly explain what this item does and any requirements for using it</span></span>
- <span data-ttu-id="8ae50-136">ProjectURI - 항목 개발을 수행하는 Github 리포지토리 또는 유사한 위치의 링크를 제공하는 PSData의 URI 필드로, 포함하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-136">ProjectURI - this is a strongly recommended URI field in PSData that provides a link to a Github repo or similar location where you do development on the item</span></span>

<span data-ttu-id="8ae50-137">PowerShell 갤러리 항목의 작성자와 소유자는 서로 관련된 개념이지만 항상 일치하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-137">Authors and Owners of PowerShell Gallery items are related concepts, but do not always match.</span></span>
<span data-ttu-id="8ae50-138">항목 소유자는 항목 유지 관리 권한이 있는 PowerShell 갤러리 계정을 소유한 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-138">Item Owners are users with PowerShell Gallery accounts that have permission to maintain the item.</span></span> <span data-ttu-id="8ae50-139">항목을 업데이트할 수 있는 소유자가 여러 명일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-139">There may be many Owners who can update any item.</span></span>
<span data-ttu-id="8ae50-140">소유자는 PowerShell 갤러리에서만 사용 가능하며 시스템 간에 항목을 복사하면 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-140">The Owner is only available from the PowerShell Gallery, and is lost if the item is copied from one system to another.</span></span>
<span data-ttu-id="8ae50-141">작성자는 매니페스트 데이터에서 기본적으로 제공되는 문자열이므로 항상 항목의 일부분입니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-141">Author is a string that is built into the manifest data, so it is always part of the item.</span></span>
<span data-ttu-id="8ae50-142">Microsoft 제품의 항목에 대한 권장 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-142">The recommendations for items from Microsoft products are:</span></span>

- <span data-ttu-id="8ae50-143">소유자를 여러 명 지정하고 한 명 이상의 이름을 항목 제작 팀 이름으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-143">Have multiple owners, with at least one being the name of the team that produces the item;</span></span>
- <span data-ttu-id="8ae50-144">작성자는 Azure SDK 팀 등 잘 알려진 팀 이름이나 Microsoft Corporation으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-144">Have the Author be a well-known team name (such as Azure SDK Team), or Microsoft Corporation.</span></span>


## <a name="pre-validate-your-item"></a><span data-ttu-id="8ae50-145">항목 사전 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="8ae50-145">Pre-Validate Your Item</span></span>

<span data-ttu-id="8ae50-146">항목을 PowerShell 갤러리에 게시하기 전에 코드에 대해 아래의 몇 가지 도구를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-146">There are a few tools you need to run against your code before publishing your item to the PowerShell Gallery:</span></span>

- <span data-ttu-id="8ae50-147">[PowerShell 스크립트 분석기](https://www.powershellgallery.com/packages/PSScriptAnalyzer/)(PowerShell 갤러리에 있음)</span><span class="sxs-lookup"><span data-stu-id="8ae50-147">[PowerShell Script Analyzer](https://www.powershellgallery.com/packages/PSScriptAnalyzer/), which is in the PowerShell Gallery</span></span>
- <span data-ttu-id="8ae50-148">모듈의 경우 Test-ModuleManifest(PowerShell의 일부분)</span><span class="sxs-lookup"><span data-stu-id="8ae50-148">For modules, Test-ModuleManifest which is part of PowerShell</span></span>
- <span data-ttu-id="8ae50-149">스크립트의 경우 Test-ScriptFileInfo(PowerShellGet과 함께 제공됨)</span><span class="sxs-lookup"><span data-stu-id="8ae50-149">For scripts, Test-ScriptFileInfo which comes with PowerShell Get</span></span>

<span data-ttu-id="8ae50-150">[PowerShell 스크립트 분석기](https://www.powershellgallery.com/packages/PSScriptAnalyzer/)는 코드를 검사하여 기본적인 PowerShell 코딩 지침을 충족하는지를 확인하는 정적 코드 분석 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-150">[PowerShell Script Analyzer](https://www.powershellgallery.com/packages/PSScriptAnalyzer/) is a static code analysis tool that will scan your code to ensure it meets basic PowerShell coding guidelines.</span></span> <span data-ttu-id="8ae50-151">이 도구는 코드에서 흔히 발생하는 중요한 문제를 파악하므로 개발 중에 정기적으로 실행하여 항목이 게시할 수 있는 상태인지를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-151">This tool will identify common and critical issues in your code, and should be run regularly during development to help you get your item ready to publish.</span></span>
<span data-ttu-id="8ae50-152">PowerShell 스크립트 분석기는 오류, 경고 및 정보로 식별된 문제 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-152">PowerShell Script Analyzer will provide list of issues identified as Errors, Warning, and Information.</span></span>
<span data-ttu-id="8ae50-153">모든 오류는 항목을 PowerShell 갤러리에 게시하기 전에 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-153">All errors must be addressed before you publish to the PowerShell Gallery.</span></span> <span data-ttu-id="8ae50-154">경고는 검토해야 하며 대다수는 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-154">Warnings need to be reviewed, and most should be addressed.</span></span>
<span data-ttu-id="8ae50-155">PowerShell 갤러리에서 항목을 게시하거나 업데이트할 때마다 PowerShell 스크립트 분석기가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-155">PowerShell Script Analyzer is run every time an item is published or updated in the PowerShell Gallery.</span></span>
<span data-ttu-id="8ae50-156">그런 후에 갤러리 운영 팀이 확인된 오류 해결을 위해 항목 소유자에게 연락을 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-156">The Gallery Operations team will contact item owners to address errors that are found.</span></span>

<span data-ttu-id="8ae50-157">항목의 매니페스트 정보를 PowerShell 갤러리 인프라에서 읽을 수 없는 경우에는 항목을 게시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-157">If the manifest information in your item cannot be read by the PowerShell Gallery infrastructure, you will not be able to publish.</span></span>
<span data-ttu-id="8ae50-158">[Test-ModuleManifest](/powershell/module/microsoft.powershell.core/test-modulemanifest)는 설치 시 모듈을 사용할 수 없게 만드는 일반적인 문제를 찾아냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-158">[Test-ModuleManifest](/powershell/module/microsoft.powershell.core/test-modulemanifest) will catch common problems that would cause the module to not be usable when it is installed.</span></span> <span data-ttu-id="8ae50-159">모든 모듈을 PowerShell 갤러리에 게시하기 전에 이 cmdlet을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-159">It must be run for every module prior to publishing it to the PowerShell Gallery.</span></span>

<span data-ttu-id="8ae50-160">마찬가지로 [Test-ScriptFileInfo](/powershell/module/PowerShellGet/test-scriptfileinfo)는 스크립트의 메타데이터 유효성을 검사합니다. 모듈과 별도로 게시하는 모든 스크립트를 PowerShell 갤러리에 게시하기 전에 이 cmdlet을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-160">Likewise, [Test-ScriptFileInfo](/powershell/module/PowerShellGet/test-scriptfileinfo) validates the metadata in a script, and must be run on every script (published separate from a module) prior to publishing it to the Powershell Gallery.</span></span>


## <a name="publishing-items"></a><span data-ttu-id="8ae50-161">항목 게시</span><span class="sxs-lookup"><span data-stu-id="8ae50-161">Publishing Items</span></span>

<span data-ttu-id="8ae50-162">PowerShell 갤러리에 항목을 게시하려면 [Publish-Script](/powershell/module/PowerShellGet/publish-script) 또는 [Publish-Module](/powershell/module/PowerShellGet/publish-module)을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-162">You must use the [Publish-Script](/powershell/module/PowerShellGet/publish-script) or [Publish-Module](/powershell/module/PowerShellGet/publish-module) to publish items to the PowerShell Gallery.</span></span>
<span data-ttu-id="8ae50-163">이 두 명령에는 다음 항목이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-163">These commands both require</span></span>

- <span data-ttu-id="8ae50-164">게시할 항목의 경로.</span><span class="sxs-lookup"><span data-stu-id="8ae50-164">The path to the item you will publish.</span></span> <span data-ttu-id="8ae50-165">모듈의 경우 모듈 이름이 지정된 폴더를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-165">For a module, use the folder named for your module.</span></span> <span data-ttu-id="8ae50-166">같은 모듈의 여러 버전이 포함된 폴더를 지정하는 경우에는 RequiredVersion을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-166">If you specify a folder that contains multiple versions of the same module, you must specify RequiredVersion.</span></span>
- <span data-ttu-id="8ae50-167">Nuget API 키.</span><span class="sxs-lookup"><span data-stu-id="8ae50-167">A Nuget API key.</span></span> <span data-ttu-id="8ae50-168">PowerShell 갤러리의 내 계정 페이지에서 확인할 수 있는 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-168">This is the API key found in the My Account page on the PowerShell Gallery.</span></span>

<span data-ttu-id="8ae50-169">명령줄에 포함된 대부분의 기타 옵션은 게시하는 항목의 매니페스트 데이터에 포함되어 있으므로 명령에서는 지정하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-169">Most of the other options in the command line should be in the manifest data for the item you are publishing, so you should not need to specify them in the command.</span></span>

<span data-ttu-id="8ae50-170">오류를 방지하려면 게시 전에 -Whatif -Verbose를 사용하여 명령을 실행해 보는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-170">To avoid errors, it is strongly recommended that you try the commands using -Whatif -Verbose, before publishing.</span></span>
<span data-ttu-id="8ae50-171">PowerShell 갤러리에 항목을 게시할 때마다 항목의 매니페스트 섹션에서 버전 번호를 업데이트해야 하므로, 이렇게 하면 시간을 크게 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-171">This will save considerable time, since every time you publish to the PowerShell Gallery, you must update the version number in the manifest section of the item.</span></span>

<span data-ttu-id="8ae50-172">예를 들어 'Publish-Module -Path ".\MyModule" -RequiredVersion "0.0.1" -NugetAPIKey "GUID" -Whatif -Verbose' 'Publish-Script -Path ".\MyScriptFile.PS1" -NugetAPIKey "GUID" -Whatif -Verbose'를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-172">Examples would be: 'Publish-Module -Path ".\MyModule" -RequiredVersion "0.0.1" -NugetAPIKey "GUID" -Whatif -Verbose' 'Publish-Script -Path ".\MyScriptFile.PS1" -NugetAPIKey "GUID" -Whatif -Verbose'</span></span>

<span data-ttu-id="8ae50-173">출력을 자세히 검토하고 오류나 경고가 없으면 -Whatif 없이 명령을 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-173">Review the output carefully, and if you see no errors or warnings, repeat the command without -Whatif.</span></span>

<span data-ttu-id="8ae50-174">PowerShell 갤러리에서는 게시하는 모든 항목에 대해 바이러스를 검사하며, PowerShell 스크립트 분석기를 사용하여 항목을 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-174">All items that are published to the PowerShell Gallery will be scanned for viruses, and will be analyzed using the PowerShell Script Analyzer.</span></span>
<span data-ttu-id="8ae50-175">이 시점에서 문제가 발생하면 해당 문제를 해결하도록 항목이 게시자에게 반송됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-175">Any issues that arise at that time will be sent back to the publisher for resolution.</span></span>

<span data-ttu-id="8ae50-176">PowerShell 갤러리에 항목을 게시한 후에는 항목에 대한 피드백을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-176">Once you have published an item to the PowerShell Gallery, you will need to watch for feedback on your item.</span></span>

- <span data-ttu-id="8ae50-177">게시할 때 사용한 계정과 연결된 전자 메일 주소를 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-177">Ensure you monitor the email address associated with the account used to publish.</span></span>
<span data-ttu-id="8ae50-178">PowerShell 갤러리 운영 팀과 사용자들이 해당 계정을 통해 PSSA 또는 바이러스 백신 검사 시에 발생하는 문제를 비롯한 피드백을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-178">Users, and the PowerShell Gallery Operations team will provide feedback via that account, including issues from the PSSA or antivirus scans.</span></span>
<span data-ttu-id="8ae50-179">전자 메일 계정이 잘못되었거나 심각한 문제가 계정으로 보고되었는데 장기간 해결되지 않는 경우에는 항목 유지 관리가 중단된 것으로 간주되어 [사용 약관](https://www.powershellgallery.com/policies/Terms)의 설명에 따라 PowerShell 갤러리에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-179">If the email account is invalid, or if serious issues are reported to the account and left unresolved for a long time, items can be considered abandoned and will be removed from the PowerShell Gallery as described in our [Terms of Use](https://www.powershellgallery.com/policies/Terms).</span></span>
- <span data-ttu-id="8ae50-180">게시하는 각 PowerShell 갤러리 항목의 댓글을 구독하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-180">We recommend you subscribe to Comments for each PowerShell Gallery item you publish.</span></span>
<span data-ttu-id="8ae50-181">이 경우 PowerShell 갤러리에서 소유한 항목에 댓글이 달리면 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-181">This allows you to be notified if anyone comments on your items in the PowerShell Gallery.</span></span>
<span data-ttu-id="8ae50-182">댓글을 구독하려면 LiveFyre에서 계정을 만들어야 하므로, 원하는 경우에만 구독을 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ae50-182">This is optional, as it requires creating an account with LiveFyre.</span></span>