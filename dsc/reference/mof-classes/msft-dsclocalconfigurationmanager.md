---
ms.date: 06/12/2017
keywords: dsc,powershell,configuration,setup
title: MSFT_DSCLocalConfigurationManager 클래스
ms.openlocfilehash: 7f6aaf209601e99b0120407eb301d32fcfda9eb8
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047709"
---
# <a name="msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="a82d6-103">MSFT_DSCLocalConfigurationManager 클래스</span><span class="sxs-lookup"><span data-stu-id="a82d6-103">MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="a82d6-104">구성 파일의 상태를 제어하고 구성 에이전트를 사용해 구성을 적용하는 LCM(로컬 구성 관리자)입니다.</span><span class="sxs-lookup"><span data-stu-id="a82d6-104">The Local Configuration Manager (LCM) that controls the states of configuration files and uses Configuration Agent to apply the configurations.</span></span>

<span data-ttu-id="a82d6-105">다음 구문은 MOF(Managed Object Format) 코드를 단순화한 것으로 상속된 속성이 모두 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a82d6-105">The following syntax is simplified from Managed Object Format (MOF) code and includes all of the inherited properties.</span></span>

## <a name="syntax"></a><span data-ttu-id="a82d6-106">구문</span><span class="sxs-lookup"><span data-stu-id="a82d6-106">Syntax</span></span>

```
[ClassVersion("1.0.0"), dynamic, provider("dsccore"), AMENDMENT]
class MSFT_DSCLocalConfigurationManager
{
};
```

## <a name="members"></a><span data-ttu-id="a82d6-107">구성원</span><span class="sxs-lookup"><span data-stu-id="a82d6-107">Members</span></span>

<span data-ttu-id="a82d6-108">**MSFT_DSCLocalConfigurationManager** 클래스에 다음 멤버가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a82d6-108">The **MSFT_DSCLocalConfigurationManager** class has the following members:</span></span>

- <span data-ttu-id="a82d6-109">[메서드][]</span><span class="sxs-lookup"><span data-stu-id="a82d6-109">[Methods][]</span></span>

### <a name="methods"></a><span data-ttu-id="a82d6-110">메서드</span><span class="sxs-lookup"><span data-stu-id="a82d6-110">Methods</span></span>

<span data-ttu-id="a82d6-111">**MSFT_DSCLocalConfigurationManager** 클래스에 다음 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a82d6-111">The **MSFT_DSCLocalConfigurationManager** class has these methods.</span></span>

|<span data-ttu-id="a82d6-112">방법</span><span class="sxs-lookup"><span data-stu-id="a82d6-112">Method</span></span> |<span data-ttu-id="a82d6-113">설명</span><span class="sxs-lookup"><span data-stu-id="a82d6-113">Description</span></span> |
|:--- |:---|
| [<span data-ttu-id="a82d6-114">ApplyConfiguration</span><span class="sxs-lookup"><span data-stu-id="a82d6-114">ApplyConfiguration</span></span>](msft-dsclocalconfigurationmanager-applyconfiguration.md)| <span data-ttu-id="a82d6-115">구성 에이전트를 사용해 보류 중인 구성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="a82d6-115">Uses the Configuration Agent to apply the configuration that is pending.</span></span>|
| [<span data-ttu-id="a82d6-116">DisableDebugConfiguration</span><span class="sxs-lookup"><span data-stu-id="a82d6-116">DisableDebugConfiguration</span></span>](msft-dsclocalconfigurationmanager-disabledebugconfiguration.md)| <span data-ttu-id="a82d6-117">DSC 리소스 디버깅을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a82d6-117">Disables DSC resource debugging.</span></span>|
| [<span data-ttu-id="a82d6-118">EnableDebugConfiguration</span><span class="sxs-lookup"><span data-stu-id="a82d6-118">EnableDebugConfiguration</span></span>](msft-dsclocalconfigurationmanager-enabledebugconfiguration.md)| <span data-ttu-id="a82d6-119">DSC 리소스 디버깅을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a82d6-119">Enables DSC resource debugging.</span></span>|
| [<span data-ttu-id="a82d6-120">GetConfiguration</span><span class="sxs-lookup"><span data-stu-id="a82d6-120">GetConfiguration</span></span>](msft-dsclocalconfigurationmanager-getconfiguration.md)| <span data-ttu-id="a82d6-121">구성 문서를 관리 노드로 보내고, 구성 에이전트의 **Get** 메서드를 사용해 구성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="a82d6-121">Sends the configuration document to the managed node and uses the **Get** method of the Configuration Agent to apply the configuration.</span></span>|
| [<span data-ttu-id="a82d6-122">GetConfigurationResultOutput</span><span class="sxs-lookup"><span data-stu-id="a82d6-122">GetConfigurationResultOutput</span></span>](msft-dsclocalconfigurationmanager-getconfigurationresultoutput.md)| <span data-ttu-id="a82d6-123">특정 작업과 관련된 구성 에이전트 출력을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a82d6-123">Gets the Configuration Agent output relating to a specific job.</span></span>|
| [<span data-ttu-id="a82d6-124">GetConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="a82d6-124">GetConfigurationStatus</span></span>](msft-dsclocalconfigurationmanager-getconfigurationstatus.md)| <span data-ttu-id="a82d6-125">구성 상태 기록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a82d6-125">Get the configuration status history.</span></span>|
| [<span data-ttu-id="a82d6-126">GetMetaConfiguration</span><span class="sxs-lookup"><span data-stu-id="a82d6-126">GetMetaConfiguration</span></span>](msft-dsclocalconfigurationmanager-getmetaconfiguration.md)| <span data-ttu-id="a82d6-127">구성 에이전트를 제어하는 데 사용되는 LCM 설정을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a82d6-127">Gets the LCM settings that are used to control Configuration Agent.</span></span>|
| [<span data-ttu-id="a82d6-128">PerformRequiredConfigurationChecks</span><span class="sxs-lookup"><span data-stu-id="a82d6-128">PerformRequiredConfigurationChecks</span></span>](msft-dsclocalconfigurationmanager-performrequiredconfigurationchecks.md)| <span data-ttu-id="a82d6-129">일관성 확인을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a82d6-129">Starts the consistency check.</span></span>|
| [<span data-ttu-id="a82d6-130">RemoveConfiguration</span><span class="sxs-lookup"><span data-stu-id="a82d6-130">RemoveConfiguration</span></span>](msft-dsclocalconfigurationmanager-removeconfiguration.md)| <span data-ttu-id="a82d6-131">구성 파일을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="a82d6-131">Removes the configuration files.</span></span>|
| [<span data-ttu-id="a82d6-132">ResourceGet</span><span class="sxs-lookup"><span data-stu-id="a82d6-132">ResourceGet</span></span>](msft-dsclocalconfigurationmanager-resourceget.md)| <span data-ttu-id="a82d6-133">DSC 리소스의 **Get** 메서드를 직접 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a82d6-133">Directly calls the **Get** method of a DSC resource.</span></span>|
| [<span data-ttu-id="a82d6-134">ResourceSet</span><span class="sxs-lookup"><span data-stu-id="a82d6-134">ResourceSet</span></span>](msft-dsclocalconfigurationmanager-resourceset.md)| <span data-ttu-id="a82d6-135">DSC 리소스의 **Set** 메서드를 직접 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a82d6-135">Directly calls the **Set** method of a DSC resource.</span></span>|
| [<span data-ttu-id="a82d6-136">ResourceTest</span><span class="sxs-lookup"><span data-stu-id="a82d6-136">ResourceTest</span></span>](msft-dsclocalconfigurationmanager-resourcetest.md)| <span data-ttu-id="a82d6-137">DSC 리소스의 **Test** 메서드를 직접 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a82d6-137">Directly calls the **Test** method of a DSC resource.</span></span>|
| [<span data-ttu-id="a82d6-138">RollBack</span><span class="sxs-lookup"><span data-stu-id="a82d6-138">RollBack</span></span>](msft-dsclocalconfigurationmanager-rollback.md)| <span data-ttu-id="a82d6-139">이전 구성으로 롤백합니다.</span><span class="sxs-lookup"><span data-stu-id="a82d6-139">Rolls back to a previous configuration.</span></span>|
| [<span data-ttu-id="a82d6-140">SendConfiguration</span><span class="sxs-lookup"><span data-stu-id="a82d6-140">SendConfiguration</span></span>](msft-dsclocalconfigurationmanager-sendconfiguration.md)| <span data-ttu-id="a82d6-141">구성 문서를 관리 노드로 보내고 보류 중인 변경으로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a82d6-141">Sends the configuration document to the managed node and saves it as a pending change.</span></span>|
| [<span data-ttu-id="a82d6-142">SendConfigurationApply</span><span class="sxs-lookup"><span data-stu-id="a82d6-142">SendConfigurationApply</span></span>](msft-dsclocalconfigurationmanager-sendconfigurationapply.md)| <span data-ttu-id="a82d6-143">구성 문서를 관리 노드로 보내고, 구성 에이전트를 사용해 구성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="a82d6-143">Sends the configuration document to the managed node and uses the Configuration Agent to apply the configuration.</span></span>|
| [<span data-ttu-id="a82d6-144">SendConfigurationApplyAsync</span><span class="sxs-lookup"><span data-stu-id="a82d6-144">SendConfigurationApplyAsync</span></span>](msft-dsclocalconfigurationmanager-sendconfigurationapplyasync.md)| <span data-ttu-id="a82d6-145">구성 문서를 관리 노드로 보내고, 구성 에이전트를 사용해 구성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="a82d6-145">Send the configuration document to the managed node and start using the Configuration Agent to apply the configuration.</span></span> <span data-ttu-id="a82d6-146">GetConfigurationResultOutput을 사용해 결과 출력을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a82d6-146">Use GetConfigurationResultOutput to retrieve result output.</span></span>|
| [<span data-ttu-id="a82d6-147">SendMetaConfigurationApply</span><span class="sxs-lookup"><span data-stu-id="a82d6-147">SendMetaConfigurationApply</span></span>](msft-dsclocalconfigurationmanager-sendmetaconfigurationapply.md)| <span data-ttu-id="a82d6-148">구성 에이전트를 제어하는 데 사용되는 LCM 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a82d6-148">Sets the LCM settings that are used to control the Configuration Agent.</span></span>|
| [<span data-ttu-id="a82d6-149">StopConfiguration</span><span class="sxs-lookup"><span data-stu-id="a82d6-149">StopConfiguration</span></span>](msft-dsclocalconfigurationmanager-stopconfiguration.md)| <span data-ttu-id="a82d6-150">진행 중인 구성을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="a82d6-150">Stops the configuration that is in progress.</span></span>|
| [<span data-ttu-id="a82d6-151">TestConfiguration</span><span class="sxs-lookup"><span data-stu-id="a82d6-151">TestConfiguration</span></span>](msft-dsclocalconfigurationmanager-testconfiguration.md)| <span data-ttu-id="a82d6-152">구성 문서를 관리 노드로 보내고, 문서에 대해 현재 구성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a82d6-152">Sends the configuration document to the managed node and verifies the current configuration against the document.</span></span>|

## <a name="requirements"></a><span data-ttu-id="a82d6-153">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a82d6-153">Requirements</span></span>

<span data-ttu-id="a82d6-154">MOF\*\* DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="a82d6-154">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="a82d6-155">{0} 네임스페이스 Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="a82d6-155">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>