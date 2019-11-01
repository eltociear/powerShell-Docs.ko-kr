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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364642"
---
# <a name="activity-parameters"></a><span data-ttu-id="9ef49-102">활동 매개 변수</span><span class="sxs-lookup"><span data-stu-id="9ef49-102">Activity Parameters</span></span>

<span data-ttu-id="9ef49-103">다음 표에서는 작업 매개 변수의 권장 이름 및 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-103">The following table lists the recommended names and functionality for activity parameters.</span></span>

|<span data-ttu-id="9ef49-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9ef49-104">Parameter</span></span>|<span data-ttu-id="9ef49-105">기능</span><span class="sxs-lookup"><span data-stu-id="9ef49-105">Functionality</span></span>|
|---|---|
|<span data-ttu-id="9ef49-106">**추가할**</span><span class="sxs-lookup"><span data-stu-id="9ef49-106">**Append**</span></span><br><span data-ttu-id="9ef49-107">데이터 형식: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9ef49-107">Data type: SwitchParameter</span></span>|<span data-ttu-id="9ef49-108">매개 변수가 지정 된 경우 사용자가 리소스의 끝에 콘텐츠를 추가할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-108">Implement this parameter so that the user can add content to the end of a resource when the parameter is specified.</span></span>|
|<span data-ttu-id="9ef49-109">**CaseSensitive**</span><span class="sxs-lookup"><span data-stu-id="9ef49-109">**CaseSensitive**</span></span><br><span data-ttu-id="9ef49-110">데이터 형식: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9ef49-110">Data type: SwitchParameter</span></span>|<span data-ttu-id="9ef49-111">이 매개 변수를 구현 하 여 사용자가 매개 변수를 지정할 때 대/소문자 구분을 요구할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-111">Implement this parameter so the user can require case sensitivity when the parameter is specified.</span></span>|
|<span data-ttu-id="9ef49-112">**Command**</span><span class="sxs-lookup"><span data-stu-id="9ef49-112">**Command**</span></span><br><span data-ttu-id="9ef49-113">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="9ef49-113">Data type: String</span></span>|<span data-ttu-id="9ef49-114">사용자가 실행할 명령 문자열을 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-114">Implement this parameter so the user can specify a command string to run.</span></span>|
|<span data-ttu-id="9ef49-115">**CompatibleVersion**</span><span class="sxs-lookup"><span data-stu-id="9ef49-115">**CompatibleVersion**</span></span><br><span data-ttu-id="9ef49-116">데이터 형식: System.object 개체</span><span class="sxs-lookup"><span data-stu-id="9ef49-116">Data type: System.Version object</span></span>|<span data-ttu-id="9ef49-117">이 매개 변수를 구현 하 여 사용자가 이전 버전과의 호환성을 위해 cmdlet이 호환 되어야 하는 의미 체계를 지정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-117">Implement this parameter so the user can specify the semantics that the cmdlet must be compatible with for compatibility with previous versions.</span></span>|
|<span data-ttu-id="9ef49-118">**압축**</span><span class="sxs-lookup"><span data-stu-id="9ef49-118">**Compress**</span></span><br><span data-ttu-id="9ef49-119">데이터 형식: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9ef49-119">Data type: SwitchParameter</span></span>|<span data-ttu-id="9ef49-120">매개 변수를 지정할 때 데이터 압축이 사용 되도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-120">Implement this parameter so that data compression is used when the parameter is specified.</span></span>|
|<span data-ttu-id="9ef49-121">**압축**</span><span class="sxs-lookup"><span data-stu-id="9ef49-121">**Compress**</span></span><br><span data-ttu-id="9ef49-122">데이터 형식: 키워드</span><span class="sxs-lookup"><span data-stu-id="9ef49-122">Data type: Keyword</span></span>|<span data-ttu-id="9ef49-123">사용자가 데이터 압축에 사용할 알고리즘을 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-123">Implement this parameter so that the user can specify the algorithm to use for data compression.</span></span>|
|<span data-ttu-id="9ef49-124">**주기가**</span><span class="sxs-lookup"><span data-stu-id="9ef49-124">**Continuous**</span></span><br><span data-ttu-id="9ef49-125">데이터 형식: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9ef49-125">Data type: SwitchParameter</span></span>|<span data-ttu-id="9ef49-126">매개 변수가 지정 될 때 사용자가 cmdlet을 종료할 때까지 데이터를 처리 하도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-126">Implement this parameter so that data is processed until the user terminates the cmdlet when the parameter is specified.</span></span> <span data-ttu-id="9ef49-127">매개 변수를 지정 하지 않으면 cmdlet이 미리 정의 된 양의 데이터를 처리 한 다음 작업을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-127">If the parameter is not specified, the cmdlet processes a predefined amount of data and then terminates the operation.</span></span>|
|<span data-ttu-id="9ef49-128">**만들기**</span><span class="sxs-lookup"><span data-stu-id="9ef49-128">**Create**</span></span><br><span data-ttu-id="9ef49-129">데이터 형식: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9ef49-129">Data type: SwitchParameter</span></span>|<span data-ttu-id="9ef49-130">이 매개 변수를 구현 하 여 매개 변수를 지정할 때 리소스가 아직 없는 경우이를 만들도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-130">Implement this parameter to indicate that a resource is created if one does not already exist when the parameter is specified.</span></span>|
|<span data-ttu-id="9ef49-131">**제거**</span><span class="sxs-lookup"><span data-stu-id="9ef49-131">**Delete**</span></span><br><span data-ttu-id="9ef49-132">데이터 형식: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9ef49-132">Data type: SwitchParameter</span></span>|<span data-ttu-id="9ef49-133">매개 변수가 지정 된 경우 cmdlet이 작업을 완료 했을 때 리소스가 삭제 되도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-133">Implement this parameter so that resources are deleted when the cmdlet has completed its operation when the parameter is specified.</span></span>|
|<span data-ttu-id="9ef49-134">**방전**</span><span class="sxs-lookup"><span data-stu-id="9ef49-134">**Drain**</span></span><br><span data-ttu-id="9ef49-135">데이터 형식: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9ef49-135">Data type: SwitchParameter</span></span>|<span data-ttu-id="9ef49-136">매개 변수가 지정 된 경우 cmdlet이 새 데이터를 처리 하기 전에 처리 중인 작업 항목이 처리 됨을 나타내려면이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-136">Implement this parameter to indicate that outstanding work items are processed before the cmdlet processes new data when the parameter is specified.</span></span> <span data-ttu-id="9ef49-137">매개 변수를 지정 하지 않으면 작업 항목이 즉시 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-137">If the parameter is not specified, the work items are processed immediately.</span></span>|
|<span data-ttu-id="9ef49-138">**지우는**</span><span class="sxs-lookup"><span data-stu-id="9ef49-138">**Erase**</span></span><br><span data-ttu-id="9ef49-139">데이터 형식: Int32</span><span class="sxs-lookup"><span data-stu-id="9ef49-139">Data type: Int32</span></span>|<span data-ttu-id="9ef49-140">사용자가 리소스를 삭제 하기 전에 삭제 되는 횟수를 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-140">Implement this parameter so that the user can specify the number of times a resource is erased before it is deleted.</span></span>|
|<span data-ttu-id="9ef49-141">**수준은**</span><span class="sxs-lookup"><span data-stu-id="9ef49-141">**ErrorLevel**</span></span><br><span data-ttu-id="9ef49-142">데이터 형식: Int32</span><span class="sxs-lookup"><span data-stu-id="9ef49-142">Data type: Int32</span></span>|<span data-ttu-id="9ef49-143">사용자가 보고할 오류 수준을 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-143">Implement this parameter so that the user can specify the level of errors to report.</span></span>|
|<span data-ttu-id="9ef49-144">**시키고**</span><span class="sxs-lookup"><span data-stu-id="9ef49-144">**Exclude**</span></span><br><span data-ttu-id="9ef49-145">데이터 형식: String[]</span><span class="sxs-lookup"><span data-stu-id="9ef49-145">Data type: String[]</span></span>|<span data-ttu-id="9ef49-146">사용자가 활동에서 항목을 제외할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-146">Implement this parameter so that the user can exclude something from an activity.</span></span> <span data-ttu-id="9ef49-147">입력 필터를 사용 하는 방법에 대 한 자세한 내용은 [입력 필터 매개 변수](input-filter-parameters.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ef49-147">For more information about how to use input filters, see [Input Filter Parameters](input-filter-parameters.md).</span></span>|
|<span data-ttu-id="9ef49-148">**필터가**</span><span class="sxs-lookup"><span data-stu-id="9ef49-148">**Filter**</span></span><br><span data-ttu-id="9ef49-149">데이터 형식: 키워드</span><span class="sxs-lookup"><span data-stu-id="9ef49-149">Data type: Keyword</span></span>|<span data-ttu-id="9ef49-150">이 매개 변수를 구현 하 여 사용자가 cmdlet 작업을 수행할 리소스를 선택 하는 필터를 지정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-150">Implement this parameter so that the user can specify a filter that selects the resources upon which to perform the cmdlet action.</span></span> <span data-ttu-id="9ef49-151">입력 필터를 사용 하는 방법에 대 한 자세한 내용은 [입력 필터 매개 변수](./input-filter-parameters.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ef49-151">For more information about how to use input filters, see [Input Filter Parameters](./input-filter-parameters.md).</span></span>|
|<span data-ttu-id="9ef49-152">**따르세요**</span><span class="sxs-lookup"><span data-stu-id="9ef49-152">**Follow**</span></span><br><span data-ttu-id="9ef49-153">데이터 형식: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9ef49-153">Data type: SwitchParameter</span></span>|<span data-ttu-id="9ef49-154">매개 변수가 지정 된 경우 진행률이 추적 되도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-154">Implement this parameter so that progress is tracked when the parameter is specified.</span></span>|
|<span data-ttu-id="9ef49-155">**설정**</span><span class="sxs-lookup"><span data-stu-id="9ef49-155">**Force**</span></span><br><span data-ttu-id="9ef49-156">데이터 형식: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9ef49-156">Data type: SwitchParameter</span></span>|<span data-ttu-id="9ef49-157">매개 변수를 지정할 때 제한이 발생 하더라도 사용자가 작업을 수행할 수 있음을 나타내려면이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-157">Implement this parameter to indicate that the user can perform an action even if restrictions are encountered when the parameter is specified.</span></span> <span data-ttu-id="9ef49-158">매개 변수는 보안이 손상 되는 것을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-158">The parameter does not allow security to be compromised.</span></span> <span data-ttu-id="9ef49-159">예를 들어이 매개 변수를 사용 하면 사용자가 읽기 전용 파일을 덮어쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-159">For example, this parameter lets a user overwrite a read-only file.</span></span>|
|<span data-ttu-id="9ef49-160">**되어야**</span><span class="sxs-lookup"><span data-stu-id="9ef49-160">**Include**</span></span><br><span data-ttu-id="9ef49-161">데이터 형식: String[]</span><span class="sxs-lookup"><span data-stu-id="9ef49-161">Data type: String[]</span></span>|<span data-ttu-id="9ef49-162">사용자가 활동에 항목을 포함할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-162">Implement this parameter so that the user can include something in an activity.</span></span> <span data-ttu-id="9ef49-163">입력 필터를 사용 하는 방법에 대 한 자세한 내용은 [입력 필터 매개 변수](input-filter-parameters.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ef49-163">For more information about how to use input filters, see [Input Filter Parameters](input-filter-parameters.md).</span></span>|
|<span data-ttu-id="9ef49-164">**대비**</span><span class="sxs-lookup"><span data-stu-id="9ef49-164">**Incremental**</span></span><br><span data-ttu-id="9ef49-165">데이터 형식: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9ef49-165">Data type: SwitchParameter</span></span>|<span data-ttu-id="9ef49-166">이 매개 변수를 구현 하 여 매개 변수가 지정 될 때 처리가 증분 수행 됨을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-166">Implement this parameter to indicate that processing is performed incrementally when the parameter is specified.</span></span> <span data-ttu-id="9ef49-167">예를 들어이 매개 변수를 통해 사용자는 마지막 백업 이후에만 파일을 백업 하는 증분 백업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-167">For example, this parameter lets a user perform incremental backups that back up files only since the last backup.</span></span>|
|<span data-ttu-id="9ef49-168">**InputObject**</span><span class="sxs-lookup"><span data-stu-id="9ef49-168">**InputObject**</span></span><br><span data-ttu-id="9ef49-169">데이터 형식: Object</span><span class="sxs-lookup"><span data-stu-id="9ef49-169">Data type: Object</span></span>|<span data-ttu-id="9ef49-170">Cmdlet이 다른 cmdlet의 입력을 사용 하는 경우이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-170">Implement this parameter when the cmdlet takes input from other cmdlets.</span></span> <span data-ttu-id="9ef49-171">**InputObject** 매개 변수를 정의할 때 **매개 변수** 특성을 선언할 때 항상 **ValueFromPipeline** 키워드를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-171">When you define an **InputObject** parameter, always specify the **ValueFromPipeline** keyword when you declare the **Parameter** attribute.</span></span> <span data-ttu-id="9ef49-172">입력 필터를 사용 하는 방법에 대 한 자세한 내용은 [입력 필터 매개 변수](./input-filter-parameters.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ef49-172">For more information about using input filters, see [Input Filter Parameters](./input-filter-parameters.md).</span></span>|
|<span data-ttu-id="9ef49-173">**넣거나**</span><span class="sxs-lookup"><span data-stu-id="9ef49-173">**Insert**</span></span><br><span data-ttu-id="9ef49-174">데이터 형식: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9ef49-174">Data type: SwitchParameter</span></span>|<span data-ttu-id="9ef49-175">매개 변수가 지정 된 경우 cmdlet이 항목을 삽입 하도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-175">Implement this parameter so that the cmdlet inserts an item when the parameter is specified.</span></span>|
|<span data-ttu-id="9ef49-176">**데스크톱**</span><span class="sxs-lookup"><span data-stu-id="9ef49-176">**Interactive**</span></span><br><span data-ttu-id="9ef49-177">데이터 형식: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9ef49-177">Data type: SwitchParameter</span></span>|<span data-ttu-id="9ef49-178">매개 변수가 지정 된 경우 cmdlet이 사용자와 대화형으로 작동 하도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-178">Implement this parameter so that the cmdlet works interactively with the user when the parameter is specified.</span></span>|
|<span data-ttu-id="9ef49-179">**간격은**</span><span class="sxs-lookup"><span data-stu-id="9ef49-179">**Interval**</span></span><br><span data-ttu-id="9ef49-180">데이터 형식: 테이블</span><span class="sxs-lookup"><span data-stu-id="9ef49-180">Data type: HashTable</span></span>|<span data-ttu-id="9ef49-181">사용자가 값을 포함 하는 키워드의 해시 테이블을 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-181">Implement this parameter so that the user can specify a hash table of keywords that contains the values.</span></span> <span data-ttu-id="9ef49-182">다음 예에서는 **Interval** 매개 변수에 대 한 샘플 값을 보여 줍니다. `-interval @{ResumeScan=15; Retry=3}`.</span><span class="sxs-lookup"><span data-stu-id="9ef49-182">The following example shows sample values for the **Interval** parameter: `-interval @{ResumeScan=15; Retry=3}`.</span></span>|
|<span data-ttu-id="9ef49-183">**Log**</span><span class="sxs-lookup"><span data-stu-id="9ef49-183">**Log**</span></span><br><span data-ttu-id="9ef49-184">데이터 형식: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9ef49-184">Data type: SwitchParameter</span></span>|<span data-ttu-id="9ef49-185">매개 변수가 지정 된 경우이 매개 변수를 구현 하 여 cmdlet의 동작을 감사 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-185">Implement this parameter audit the actions of the cmdlet when the parameter is specified.</span></span>|
|<span data-ttu-id="9ef49-186">**NoClobber**</span><span class="sxs-lookup"><span data-stu-id="9ef49-186">**NoClobber**</span></span><br><span data-ttu-id="9ef49-187">데이터 형식: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9ef49-187">Data type: SwitchParameter</span></span>|<span data-ttu-id="9ef49-188">매개 변수를 지정할 때 리소스를 덮어쓰지 않도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-188">Implement this parameter so that the resource will not be overwritten when the parameter is specified.</span></span> <span data-ttu-id="9ef49-189">이 매개 변수는 일반적으로 새 개체를 만드는 cmdlet에 적용 되므로 이름이 같은 기존 개체를 덮어쓸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-189">This parameter generally applies to cmdlets that create new objects so that they can be prevented from overwriting existing objects with the same name.</span></span>|
|<span data-ttu-id="9ef49-190">**되었음을**</span><span class="sxs-lookup"><span data-stu-id="9ef49-190">**Notify**</span></span><br><span data-ttu-id="9ef49-191">데이터 형식: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9ef49-191">Data type: SwitchParameter</span></span>|<span data-ttu-id="9ef49-192">매개 변수를 지정할 때 작업이 완료 되었다는 알림이 사용자에 게 표시 되도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-192">Implement this parameter so that the user will be notified that the activity is complete when the parameter is specified.</span></span>|
|<span data-ttu-id="9ef49-193">**NotifyAddress**</span><span class="sxs-lookup"><span data-stu-id="9ef49-193">**NotifyAddress**</span></span><br><span data-ttu-id="9ef49-194">데이터 형식: 메일 주소</span><span class="sxs-lookup"><span data-stu-id="9ef49-194">Data type: Email address</span></span>|<span data-ttu-id="9ef49-195">**알림 매개 변수가** 지정 된 경우 사용자가 알림을 보내는 데 사용할 전자 메일 주소를 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-195">Implement this parameter so that the user can specify the e-mail address to use to send a notification when the **Notify** parameter is specified.</span></span>|
|<span data-ttu-id="9ef49-196">**언제**</span><span class="sxs-lookup"><span data-stu-id="9ef49-196">**Overwrite**</span></span><br><span data-ttu-id="9ef49-197">데이터 형식: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9ef49-197">Data type: SwitchParameter</span></span>|<span data-ttu-id="9ef49-198">매개 변수가 지정 된 경우 cmdlet이 기존 데이터를 덮어쓰도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-198">Implement this parameter so that the cmdlet overwrites any existing data when the parameter is specified.</span></span>|
|<span data-ttu-id="9ef49-199">**요청할**</span><span class="sxs-lookup"><span data-stu-id="9ef49-199">**Prompt**</span></span><br><span data-ttu-id="9ef49-200">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="9ef49-200">Data type: String</span></span>|<span data-ttu-id="9ef49-201">사용자가 cmdlet에 대 한 프롬프트를 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-201">Implement this parameter so that the user can specify a prompt for the cmdlet.</span></span>|
|<span data-ttu-id="9ef49-202">**개입**</span><span class="sxs-lookup"><span data-stu-id="9ef49-202">**Quiet**</span></span><br><span data-ttu-id="9ef49-203">데이터 형식: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9ef49-203">Data type: SwitchParameter</span></span>|<span data-ttu-id="9ef49-204">매개 변수가 지정 된 경우 cmdlet이 작업 중에 사용자 피드백을 표시 하지 않도록 하려면이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-204">Implement this parameter so that the cmdlet suppresses user feedback during its actions when the parameter is specified.</span></span>|
|<span data-ttu-id="9ef49-205">**Recurse**</span><span class="sxs-lookup"><span data-stu-id="9ef49-205">**Recurse**</span></span><br><span data-ttu-id="9ef49-206">데이터 형식: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9ef49-206">Data type: SwitchParameter</span></span>|<span data-ttu-id="9ef49-207">매개 변수가 지정 된 경우 cmdlet이 리소스에 대 한 작업을 재귀적으로 수행 하도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-207">Implement this parameter so that the cmdlet recursively performs its actions on resources when the parameter is specified.</span></span>|
|<span data-ttu-id="9ef49-208">**복구한**</span><span class="sxs-lookup"><span data-stu-id="9ef49-208">**Repair**</span></span><br><span data-ttu-id="9ef49-209">데이터 형식: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9ef49-209">Data type: SwitchParameter</span></span>|<span data-ttu-id="9ef49-210">매개 변수가 지정 된 경우 cmdlet이 손상 된 상태에서 무언가를 수정 하려고 시도 하도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-210">Implement this parameter so that the cmdlet will attempt to correct something from a broken state when the parameter is specified.</span></span>|
|<span data-ttu-id="9ef49-211">**RepairString**</span><span class="sxs-lookup"><span data-stu-id="9ef49-211">**RepairString**</span></span><br><span data-ttu-id="9ef49-212">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="9ef49-212">Data type: String</span></span>|<span data-ttu-id="9ef49-213">사용자가 **Repair** 매개 변수를 지정할 때 사용할 문자열을 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-213">Implement this parameter so that the user can specify a string to use when the **Repair** parameter is specified.</span></span>|
|<span data-ttu-id="9ef49-214">**Retry**</span><span class="sxs-lookup"><span data-stu-id="9ef49-214">**Retry**</span></span><br><span data-ttu-id="9ef49-215">데이터 형식: Int32</span><span class="sxs-lookup"><span data-stu-id="9ef49-215">Data type: Int32</span></span>|<span data-ttu-id="9ef49-216">사용자가 cmdlet에서 작업을 시도 하는 횟수를 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-216">Implement this parameter so the user can specify the number of times the cmdlet will attempt an action.</span></span>|
|<span data-ttu-id="9ef49-217">**선택**</span><span class="sxs-lookup"><span data-stu-id="9ef49-217">**Select**</span></span><br><span data-ttu-id="9ef49-218">데이터 형식: 키워드 배열</span><span class="sxs-lookup"><span data-stu-id="9ef49-218">Data type: Keyword array</span></span>|<span data-ttu-id="9ef49-219">사용자가 항목 형식의 배열을 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-219">Implement this parameter so that the user can specify an array of the types of items.</span></span>|
|<span data-ttu-id="9ef49-220">**스트림**</span><span class="sxs-lookup"><span data-stu-id="9ef49-220">**Stream**</span></span><br><span data-ttu-id="9ef49-221">데이터 형식: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9ef49-221">Data type: SwitchParameter</span></span>|<span data-ttu-id="9ef49-222">매개 변수가 지정 된 경우 사용자가 파이프라인을 통해 여러 출력 개체를 스트리밍할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-222">Implement this parameter so the user can stream multiple output objects through the pipeline when the parameter is specified.</span></span>|
|<span data-ttu-id="9ef49-223">**제품과**</span><span class="sxs-lookup"><span data-stu-id="9ef49-223">**Strict**</span></span><br><span data-ttu-id="9ef49-224">데이터 형식: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9ef49-224">Data type: SwitchParameter</span></span>|<span data-ttu-id="9ef49-225">이 매개 변수를 구현 하 여 매개 변수가 지정 된 경우 모든 오류가 종료 오류로 처리 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-225">Implement this parameter so that all errors are handled as terminating errors when the parameter is specified.</span></span>|
|<span data-ttu-id="9ef49-226">**TempLocation**</span><span class="sxs-lookup"><span data-stu-id="9ef49-226">**TempLocation**</span></span><br><span data-ttu-id="9ef49-227">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="9ef49-227">Data type: String</span></span>|<span data-ttu-id="9ef49-228">이 매개 변수를 구현 하 여 사용자가 cmdlet 작업 중에 사용 되는 임시 데이터의 위치를 지정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-228">Implement this parameter so the user can specify the location of temporary data that is used during the operation of the cmdlet.</span></span>|
|<span data-ttu-id="9ef49-229">**초과가**</span><span class="sxs-lookup"><span data-stu-id="9ef49-229">**Timeout**</span></span><br><span data-ttu-id="9ef49-230">데이터 형식: Int32</span><span class="sxs-lookup"><span data-stu-id="9ef49-230">Data type: Int32</span></span>|<span data-ttu-id="9ef49-231">사용자가 제한 시간 간격 (밀리초)을 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-231">Implement this parameter so that the user can specify the timeout interval (in milliseconds).</span></span>|
|<span data-ttu-id="9ef49-232">**잘라내야**</span><span class="sxs-lookup"><span data-stu-id="9ef49-232">**Truncate**</span></span><br><span data-ttu-id="9ef49-233">데이터 형식: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9ef49-233">Data type: SwitchParameter</span></span>|<span data-ttu-id="9ef49-234">매개 변수가 지정 된 경우 cmdlet에서 해당 작업을 잘라내는이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-234">Implement this parameter so that the cmdlet will truncate its actions when the parameter is specified.</span></span> <span data-ttu-id="9ef49-235">매개 변수를 지정 하지 않으면 cmdlet이 다른 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-235">If the parameter is not specified, the cmdlet performs another action.</span></span>|
|<span data-ttu-id="9ef49-236">**올바른지**</span><span class="sxs-lookup"><span data-stu-id="9ef49-236">**Verify**</span></span><br><span data-ttu-id="9ef49-237">데이터 형식: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9ef49-237">Data type: SwitchParameter</span></span>|<span data-ttu-id="9ef49-238">Cmdlet에서 매개 변수를 지정할 때 동작이 발생 했는지 여부를 확인 하도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-238">Implement this parameter so that the cmdlet will test to determine whether an action has occurred when the parameter is specified.</span></span>|
|<span data-ttu-id="9ef49-239">**대기한**</span><span class="sxs-lookup"><span data-stu-id="9ef49-239">**Wait**</span></span><br><span data-ttu-id="9ef49-240">데이터 형식: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9ef49-240">Data type: SwitchParameter</span></span>|<span data-ttu-id="9ef49-241">매개 변수가 지정 되 면 계속 하기 전에 cmdlet이 사용자 입력을 대기 하도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-241">Implement this parameter so that the cmdlet will wait for user input before continuing when the parameter is specified.</span></span>
|<span data-ttu-id="9ef49-242">**WaitTime**</span><span class="sxs-lookup"><span data-stu-id="9ef49-242">**WaitTime**</span></span><br><span data-ttu-id="9ef49-243">데이터 형식: Int32</span><span class="sxs-lookup"><span data-stu-id="9ef49-243">Data type: Int32</span></span>|<span data-ttu-id="9ef49-244">**대기** 매개 변수가 지정 된 경우 사용자가 cmdlet이 사용자 입력을 대기 하는 기간 (초)을 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef49-244">Implement this parameter so that the user can specify the duration (in seconds) that the cmdlet will wait for user input when the **Wait** parameter is specified.</span></span>|

## <a name="see-also"></a><span data-ttu-id="9ef49-245">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ef49-245">See Also</span></span>

[<span data-ttu-id="9ef49-246">Cmdlet 매개 변수</span><span class="sxs-lookup"><span data-stu-id="9ef49-246">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

<span data-ttu-id="9ef49-247">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)(Windows PowerShell Cmdlet 작성)</span><span class="sxs-lookup"><span data-stu-id="9ef49-247">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>

[<span data-ttu-id="9ef49-248">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="9ef49-248">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)