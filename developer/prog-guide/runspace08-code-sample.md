---
title: RunSpace08 코드 샘플 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f286201-8a02-4b00-9a2c-1b833ccdbdbf
caps.latest.revision: 7
ms.openlocfilehash: 1a09cfee3bb317de6c1ca4dde86a87d72a498e6e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858609"
---
# <a name="runspace08-code-sample"></a><span data-ttu-id="f7821-102">RunSpace08 코드 샘플</span><span class="sxs-lookup"><span data-stu-id="f7821-102">RunSpace08 Code Sample</span></span>

<span data-ttu-id="f7821-103">에 설명 된 Runspace08 샘플에 대 한 소스 코드를 다음과 같습니다 [는 콘솔 응용 프로그램을 추가 매개 변수를 만드는 명령](http://msdn.microsoft.com/en-us/848b2b46-60f1-4a86-b448-cfc7c0cccfba)입니다.</span><span class="sxs-lookup"><span data-stu-id="f7821-103">Here is the source code for the Runspace08 sample described in [Creating a Console Application That Adds Parameters to a Command](http://msdn.microsoft.com/en-us/848b2b46-60f1-4a86-b448-cfc7c0cccfba).</span></span> <span data-ttu-id="f7821-104">이 샘플 응용 프로그램 runspace, 파이프라인을 만듭니다, 그리고 파이프라인에 두 개의 명령을 추가, 두 번째 명령은 두 개의 매개 변수 추가 만들고 파이프라인을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7821-104">This sample application creates a runspace, creates a pipeline, adds two commands to the pipeline, adds two parameters to the second command, and then executes the pipeline.</span></span> <span data-ttu-id="f7821-105">파이프라인에 추가 되는 명령은 합니다 `Get-Process` 고 `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f7821-105">The commands that are added to the pipeline are the `Get-Process` and `Sort-Object` cmdlets.</span></span>

## <a name="code-sample"></a><span data-ttu-id="f7821-106">코드 예제</span><span class="sxs-lookup"><span data-stu-id="f7821-106">Code Sample</span></span>

[!code-csharp[Runspace08.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace08/Runspace08.cs#L11-L86 "Runspace08.cs")]

## <a name="see-also"></a><span data-ttu-id="f7821-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f7821-107">See Also</span></span>

[<span data-ttu-id="f7821-108">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="f7821-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)