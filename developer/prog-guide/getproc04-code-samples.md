---
title: GetProc04 코드 샘플 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c00afd46-758a-4aec-b865-2c9d8f6a17ad
caps.latest.revision: 5
ms.openlocfilehash: d679bc8cbdb026e072628d3e0c5704de2eec7af9
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855449"
---
# <a name="getproc04-code-samples"></a><span data-ttu-id="b04a7-102">GetProc04 코드 샘플</span><span class="sxs-lookup"><span data-stu-id="b04a7-102">GetProc04 Code Samples</span></span>

<span data-ttu-id="b04a7-103">GetProc04 샘플 cmdlet에 대 한 코드 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b04a7-103">Here are the code samples for the GetProc04 sample cmdlet.</span></span> <span data-ttu-id="b04a7-104">이 `Get-Process` 에 설명 된 cmdlet 샘플 [Your cmdlet 종료 되지 않는 오류 보고를 추가](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b04a7-104">This is the `Get-Process` cmdlet sample described in [Adding Nonterminating Error Reporting to Your Cmdlet](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md).</span></span> <span data-ttu-id="b04a7-105">이렇게 `Get-Process` cmdlet 호출을 [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) 메서드 때마다 프로세스 정보를 검색 하는 동안 잘못 된 작업 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b04a7-105">This `Get-Process` cmdlet calls the [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method whenever an invalid operation exception is thrown while retrieving process information.</span></span>

> [!NOTE]
> <span data-ttu-id="b04a7-106">다운로드할 수 있습니다는 C# Microsoft Windows 소프트웨어 개발 키트에 대 한 Windows Vista 및.NET Framework 3.0 런타임 구성 요소를 사용 하 여이 Get-proc cmdlet에 대 한 소스 파일 (getprov04.cs).</span><span class="sxs-lookup"><span data-stu-id="b04a7-106">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="b04a7-107">다운로드 지침에 대해서 [Windows PowerShell 설치 및 Windows PowerShell SDK를 다운로드 하는 방법을](/powershell/developer/installing-the-windows-powershell-sdk)합니다.</span><span class="sxs-lookup"><span data-stu-id="b04a7-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="b04a7-108">다운로드할 수 있습니다는 C# Microsoft Windows 소프트웨어 개발 키트에 대 한 Windows Vista 및.NET Framework 3.0 런타임 구성 요소를 사용 하 여이 Get-proc cmdlet에 대 한 소스 파일 (getprov04.cs).</span><span class="sxs-lookup"><span data-stu-id="b04a7-108">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="b04a7-109">다운로드 지침에 대해서 [Windows PowerShell 설치 및 Windows PowerShell SDK를 다운로드 하는 방법을](/powershell/developer/installing-the-windows-powershell-sdk)합니다.</span><span class="sxs-lookup"><span data-stu-id="b04a7-109">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="b04a7-110">다운로드 한 소스 파일에서 사용할 수는  **\<PowerShell 샘플 >** 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="b04a7-110">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="b04a7-111">전체 샘플 코드를 다음 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b04a7-111">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="b04a7-112">Language</span><span class="sxs-lookup"><span data-stu-id="b04a7-112">Language</span></span>|<span data-ttu-id="b04a7-113">항목</span><span class="sxs-lookup"><span data-stu-id="b04a7-113">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="b04a7-114">C#</span><span class="sxs-lookup"><span data-stu-id="b04a7-114">C#</span></span>|[<span data-ttu-id="b04a7-115">GetProc04 (C#) 코드 샘플</span><span class="sxs-lookup"><span data-stu-id="b04a7-115">GetProc04 (C#) Sample Code</span></span>](./getproc04-csharp-sample-code.md)|
|<span data-ttu-id="b04a7-116">VB.NET</span><span class="sxs-lookup"><span data-stu-id="b04a7-116">VB.NET</span></span>|[<span data-ttu-id="b04a7-117">GetProc04 (VB.NET) 샘플 코드</span><span class="sxs-lookup"><span data-stu-id="b04a7-117">GetProc04 (VB.NET) Sample Code</span></span>](./getproc04-vb-net-sample-code.md)|

## <a name="see-also"></a><span data-ttu-id="b04a7-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b04a7-118">See Also</span></span>

[<span data-ttu-id="b04a7-119">Windows PowerShell 프로그래머 가이드</span><span class="sxs-lookup"><span data-stu-id="b04a7-119">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="b04a7-120">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="b04a7-120">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)