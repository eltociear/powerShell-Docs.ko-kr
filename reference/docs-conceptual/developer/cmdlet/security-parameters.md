---
title: 보안 매개 변수 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e199bba3-90d3-41ca-9d78-cb502e58508d
caps.latest.revision: 6
ms.openlocfilehash: 9b4d83aeaf45eab1365dec5fbf48c3c796ed5bde
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369502"
---
# <a name="security-parameters"></a><span data-ttu-id="e41c8-102">보안 매개 변수</span><span class="sxs-lookup"><span data-stu-id="e41c8-102">Security Parameters</span></span>

<span data-ttu-id="e41c8-103">다음 표에서는 인증서 키 및 권한 정보를 지정 하는 매개 변수와 같이 작업에 대 한 보안 정보를 제공 하는 데 사용 되는 매개 변수에 대해 권장 되는 이름 및 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-103">The following table lists the recommended names and functionality for parameters used to provide security information for an operation, such as parameters that specify certificate key and privilege information.</span></span>

|<span data-ttu-id="e41c8-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e41c8-104">Parameter</span></span>|<span data-ttu-id="e41c8-105">기능</span><span class="sxs-lookup"><span data-stu-id="e41c8-105">Functionality</span></span>|
|---|---|
|<span data-ttu-id="e41c8-106">**ACL**</span><span class="sxs-lookup"><span data-stu-id="e41c8-106">**ACL**</span></span><br><span data-ttu-id="e41c8-107">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="e41c8-107">Data type: String</span></span>|<span data-ttu-id="e41c8-108">카탈로그 또는 URI (Uniform Resource Identifier)에 대 한 액세스 제어 수준을 지정 하려면이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-108">Implement this parameter to specify the access control level of protection for a catalog or for a Uniform Resource Identifier (URI).</span></span>|
|<span data-ttu-id="e41c8-109">**CertFile**</span><span class="sxs-lookup"><span data-stu-id="e41c8-109">**CertFile**</span></span><br><span data-ttu-id="e41c8-110">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="e41c8-110">Data type: String</span></span>|<span data-ttu-id="e41c8-111">사용자가 다음 중 하나를 포함 하는 파일의 이름을 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-111">Implement this parameter so that the user can specify the name of a file that contains one of the following:</span></span><br><span data-ttu-id="e41c8-112">-Base64 또는 Distinguished Encoding Rules (DER) 인코딩된 x.509 certificate</span><span class="sxs-lookup"><span data-stu-id="e41c8-112">- A Base64 or Distinguished Encoding Rules (DER) encoded x.509 certificate</span></span><br><span data-ttu-id="e41c8-113">-하나 이상의 인증서와 키를 포함 하는 PKCS (공개 키 암호화 표준) #12 파일</span><span class="sxs-lookup"><span data-stu-id="e41c8-113">- A Public Key Cryptography Standards (PKCS) #12 file that contains at least one certificate and key</span></span>|
|<span data-ttu-id="e41c8-114">**CertIssuerName**</span><span class="sxs-lookup"><span data-stu-id="e41c8-114">**CertIssuerName**</span></span><br><span data-ttu-id="e41c8-115">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="e41c8-115">Data type: String</span></span>|<span data-ttu-id="e41c8-116">사용자가 인증서 발급자의 이름을 지정 하거나 사용자가 하위 문자열을 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-116">Implement this parameter so that the user can specify the name of the issuer of a certificate or so that the user can specify a substring.</span></span>|
|<span data-ttu-id="e41c8-117">**CertRequestFile**</span><span class="sxs-lookup"><span data-stu-id="e41c8-117">**CertRequestFile**</span></span><br><span data-ttu-id="e41c8-118">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="e41c8-118">Data type: String</span></span>|<span data-ttu-id="e41c8-119">이 매개 변수를 구현 하 여 Base64 또는 DER로 인코딩된 PKCS #10 인증서 요청을 포함 하는 파일의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-119">Implement this parameter to specify the name of a file that contains a Base64 or DER-encoded PKCS #10 certificate request.</span></span>|
|<span data-ttu-id="e41c8-120">**CertSerialNumber**</span><span class="sxs-lookup"><span data-stu-id="e41c8-120">**CertSerialNumber**</span></span><br><span data-ttu-id="e41c8-121">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="e41c8-121">Data type: String</span></span>|<span data-ttu-id="e41c8-122">이 매개 변수를 구현 하 여 인증 기관에서 발급 한 일련 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-122">Implement this parameter to specify the serial number that was issued by the certification authority.</span></span>|
|<span data-ttu-id="e41c8-123">**찾아보십시오**</span><span class="sxs-lookup"><span data-stu-id="e41c8-123">**CertStoreLocation**</span></span><br><span data-ttu-id="e41c8-124">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="e41c8-124">Data type: String</span></span>|<span data-ttu-id="e41c8-125">사용자가 인증서 저장소의 위치를 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-125">Implement this parameter so that the user can specify the location of the certificate store.</span></span> <span data-ttu-id="e41c8-126">위치는 일반적으로 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-126">The location is typically a file path.</span></span>|
|<span data-ttu-id="e41c8-127">**CertSubjectName**</span><span class="sxs-lookup"><span data-stu-id="e41c8-127">**CertSubjectName**</span></span><br><span data-ttu-id="e41c8-128">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="e41c8-128">Data type: String</span></span>|<span data-ttu-id="e41c8-129">사용자가 인증서 발급자를 지정 하거나 사용자가 부분 문자열을 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-129">Implement this parameter so that the user can specify the issuer of a certificate or so that the user can specify a substring.</span></span>|
|<span data-ttu-id="e41c8-130">**CertUsage**</span><span class="sxs-lookup"><span data-stu-id="e41c8-130">**CertUsage**</span></span><br><span data-ttu-id="e41c8-131">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="e41c8-131">Data type: String</span></span>|<span data-ttu-id="e41c8-132">키 사용 또는 확장 된 키 사용을 지정 하려면이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-132">Implement this parameter to specify the key usage or the enhanced key usage.</span></span> <span data-ttu-id="e41c8-133">키를 비트 마스크, 비트, OID (개체 식별자) 또는 문자열로 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-133">The key can be represented as a bit mask, a bit, an object identifier (OID), or a string.</span></span>|
|<span data-ttu-id="e41c8-134">**증명서**</span><span class="sxs-lookup"><span data-stu-id="e41c8-134">**Credential**</span></span><br><span data-ttu-id="e41c8-135">데이터 형식: [system.web. PSCredential](/dotnet/api/System.Management.Automation.PSCredential)</span><span class="sxs-lookup"><span data-stu-id="e41c8-135">Data type: [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential)</span></span>|<span data-ttu-id="e41c8-136">Cmdlet이 사용자에 게 사용자 이름 또는 암호를 묻는 메시지를 자동으로 표시 하도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-136">Implement this parameter so that the cmdlet will automatically prompt the user for a user name or password.</span></span> <span data-ttu-id="e41c8-137">전체 자격 증명을 직접 제공 하지 않으면 둘 다에 대 한 프롬프트가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-137">A prompt for both is displayed if a full credential is not supplied directly.</span></span>|
|<span data-ttu-id="e41c8-138">**CSPName**</span><span class="sxs-lookup"><span data-stu-id="e41c8-138">**CSPName**</span></span><br><span data-ttu-id="e41c8-139">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="e41c8-139">Data type: String</span></span>|<span data-ttu-id="e41c8-140">사용자가 CSP (인증서 서비스 공급자)의 이름을 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-140">Implement this parameter so that the user can specify the name of the certificate service provider (CSP).</span></span>|
|<span data-ttu-id="e41c8-141">**CSPType**</span><span class="sxs-lookup"><span data-stu-id="e41c8-141">**CSPType**</span></span><br><span data-ttu-id="e41c8-142">데이터 형식: Integer</span><span class="sxs-lookup"><span data-stu-id="e41c8-142">Data type: Integer</span></span>|<span data-ttu-id="e41c8-143">사용자가 CSP 형식을 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-143">Implement this parameter so that the user can specify the type of CSP.</span></span>|
|<span data-ttu-id="e41c8-144">**그룹**</span><span class="sxs-lookup"><span data-stu-id="e41c8-144">**Group**</span></span><br><span data-ttu-id="e41c8-145">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="e41c8-145">Data type: String</span></span>|<span data-ttu-id="e41c8-146">사용자가 액세스에 대 한 보안 주체 컬렉션을 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-146">Implement this parameter so that the user can specify a collection of principals for access.</span></span> <span data-ttu-id="e41c8-147">자세한 내용은 **Principal** 매개 변수에 대 한 설명을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e41c8-147">For more information, see the description of the **Principal** parameter.</span></span>|
|<span data-ttu-id="e41c8-148">**KeyAlgorithm**</span><span class="sxs-lookup"><span data-stu-id="e41c8-148">**KeyAlgorithm**</span></span><br><span data-ttu-id="e41c8-149">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="e41c8-149">Data type: String</span></span>|<span data-ttu-id="e41c8-150">사용자가 보안에 사용할 키 생성 알고리즘을 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-150">Implement this parameter so that the user can specify the key generation algorithm to use for security.</span></span>|
|<span data-ttu-id="e41c8-151">**Cspparameters.keycontainername**</span><span class="sxs-lookup"><span data-stu-id="e41c8-151">**KeyContainerName**</span></span><br><span data-ttu-id="e41c8-152">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="e41c8-152">Data type: String</span></span>|<span data-ttu-id="e41c8-153">이 매개 변수를 구현 하 여 사용자가 키 컨테이너의 이름을 지정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-153">Implement this parameter so that the user can specify the name of the key container.</span></span>|
|<span data-ttu-id="e41c8-154">**KeyLength**</span><span class="sxs-lookup"><span data-stu-id="e41c8-154">**KeyLength**</span></span><br><span data-ttu-id="e41c8-155">데이터 형식: Integer</span><span class="sxs-lookup"><span data-stu-id="e41c8-155">Data type: Integer</span></span>|<span data-ttu-id="e41c8-156">사용자가 키의 길이 (비트)를 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-156">Implement this parameter so that the user can specify the length of the key in bits.</span></span>|
|<span data-ttu-id="e41c8-157">**연산의**</span><span class="sxs-lookup"><span data-stu-id="e41c8-157">**Operation**</span></span><br><span data-ttu-id="e41c8-158">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="e41c8-158">Data type: String</span></span>|<span data-ttu-id="e41c8-159">사용자가 보호 된 개체에 대해 수행할 수 있는 작업을 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-159">Implement this parameter so that the user can specify an action that can be performed on a protected object.</span></span>|
|<span data-ttu-id="e41c8-160">**원칙**</span><span class="sxs-lookup"><span data-stu-id="e41c8-160">**Principal**</span></span><br><span data-ttu-id="e41c8-161">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="e41c8-161">Data type: String</span></span>|<span data-ttu-id="e41c8-162">사용자가 액세스를 위해 고유 하 게 식별할 수 있는 엔터티를 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-162">Implement this parameter so that the user can specify a unique identifiable entity for access.</span></span>|
|<span data-ttu-id="e41c8-163">**권한과**</span><span class="sxs-lookup"><span data-stu-id="e41c8-163">**Privilege**</span></span><br><span data-ttu-id="e41c8-164">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="e41c8-164">Data type: String</span></span>|<span data-ttu-id="e41c8-165">사용자가 특정 엔터티에 대 한 작업을 수행 하는 데 필요한 권한을 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-165">Implement this parameter so that the user can specify the right a cmdlet needs to perform an operation for a particular entity.</span></span>|
|<span data-ttu-id="e41c8-166">**권한**</span><span class="sxs-lookup"><span data-stu-id="e41c8-166">**Privileges**</span></span><br><span data-ttu-id="e41c8-167">데이터 형식: 권한 배열</span><span class="sxs-lookup"><span data-stu-id="e41c8-167">Data type: Array of privileges</span></span>|<span data-ttu-id="e41c8-168">사용자가 특정 항목에 대 한 작업을 수행 하는 데 필요한 권한을 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-168">Implement this parameter so that the user can specify the rights that a cmdlet needs to perform its operation for a particular entry.</span></span>|
|<span data-ttu-id="e41c8-169">**역할**</span><span class="sxs-lookup"><span data-stu-id="e41c8-169">**Role**</span></span><br><span data-ttu-id="e41c8-170">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="e41c8-170">Data type: String</span></span>|<span data-ttu-id="e41c8-171">사용자가 엔터티에서 수행할 수 있는 작업 집합을 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-171">Implement this parameter so that the user can specify a set of operations that can be performed by an entity.</span></span>|
|<span data-ttu-id="e41c8-172">**SaveCred**</span><span class="sxs-lookup"><span data-stu-id="e41c8-172">**SaveCred**</span></span><br><span data-ttu-id="e41c8-173">데이터 형식: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="e41c8-173">Data type: SwitchParameter</span></span>|<span data-ttu-id="e41c8-174">매개 변수가 지정 될 때 사용자가 이전에 저장 한 자격 증명을 사용 하도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-174">Implement this parameter so that credentials that were previously saved by the user will be used when the parameter is specified.</span></span>|
|<span data-ttu-id="e41c8-175">**범위**</span><span class="sxs-lookup"><span data-stu-id="e41c8-175">**Scope**</span></span><br><span data-ttu-id="e41c8-176">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="e41c8-176">Data type: String</span></span>|<span data-ttu-id="e41c8-177">이 매개 변수를 구현 하 여 사용자가 cmdlet에 대 한 보호 된 개체의 그룹을 지정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-177">Implement this parameter so that the user can specify the group of protected objects for the cmdlet.</span></span>|
|<span data-ttu-id="e41c8-178">**S**</span><span class="sxs-lookup"><span data-stu-id="e41c8-178">**SID**</span></span><br><span data-ttu-id="e41c8-179">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="e41c8-179">Data type: String</span></span>|<span data-ttu-id="e41c8-180">사용자가 보안 주체를 나타내는 고유 식별자를 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-180">Implement this parameter so that the user can specify a unique identifier that represents a principal.</span></span>|
|<span data-ttu-id="e41c8-181">**신뢰할 수 있는**</span><span class="sxs-lookup"><span data-stu-id="e41c8-181">**Trusted**</span></span><br><span data-ttu-id="e41c8-182">데이터 형식: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="e41c8-182">Data type: SwitchParameter</span></span>|<span data-ttu-id="e41c8-183">매개 변수가 지정 된 경우 신뢰 수준이 지원 되도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-183">Implement this parameter so that trust levels are supported when the parameter is specified.</span></span>|
|<span data-ttu-id="e41c8-184">**TrustLevel**</span><span class="sxs-lookup"><span data-stu-id="e41c8-184">**TrustLevel**</span></span><br><span data-ttu-id="e41c8-185">데이터 형식: 키워드</span><span class="sxs-lookup"><span data-stu-id="e41c8-185">Data type: Keyword</span></span>|<span data-ttu-id="e41c8-186">사용자가 지원 되는 신뢰 수준을 지정할 수 있도록이 매개 변수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-186">Implement this parameter so that the user can specify the trust level that is supported.</span></span> <span data-ttu-id="e41c8-187">예를 들어 가능한 값에는 인터넷, 인트라넷 및 fulltrust가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e41c8-187">For example, possible values include internet, intranet, and fulltrust.</span></span>|

## <a name="see-also"></a><span data-ttu-id="e41c8-188">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e41c8-188">See Also</span></span>

[<span data-ttu-id="e41c8-189">Cmdlet 매개 변수</span><span class="sxs-lookup"><span data-stu-id="e41c8-189">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

<span data-ttu-id="e41c8-190">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)(Windows PowerShell Cmdlet 작성)</span><span class="sxs-lookup"><span data-stu-id="e41c8-190">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>

[<span data-ttu-id="e41c8-191">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="e41c8-191">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)