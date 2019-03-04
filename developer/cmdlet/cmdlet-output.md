---
title: Cmdlet 출력 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1362f4cd-4e05-4ace-ade6-7128da8ad86c
caps.latest.revision: 10
ms.openlocfilehash: 4c6aacd49b0a87bca6806ba5f08a1b4d48a90959
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853819"
---
# <a name="cmdlet-output"></a><span data-ttu-id="932ed-102">Cmdlet 출력</span><span class="sxs-lookup"><span data-stu-id="932ed-102">Cmdlet Output</span></span>

<span data-ttu-id="932ed-103">이 섹션에서는 cmdlet 오류 메시지 및 개체와 같은 출력을 생성 하기 위해 호출할 수 있는 메서드와 cmdlet 출력의 형식을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="932ed-103">This section discusses the types of cmdlet output and the methods that cmdlets can call to generate output such as error messages and objects.</span></span> <span data-ttu-id="932ed-104">또한이 섹션에는 cmdlet에서 반환 되는.NET Framework 형식을 정의 하는 방법 및 개체만 표시 되는 방식을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="932ed-104">This section also describes how to define the .NET Framework types that are returned by your cmdlets and how those objects are displayed.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="932ed-105">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="932ed-105">In This Section</span></span>

<span data-ttu-id="932ed-106">[Cmdlet 출력 유형의](./types-of-cmdlet-output.md) 형식 및 cmdlet을 생성할 수 있는 출력 및 cmdlet 호출의 출력을 생성 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="932ed-106">[Types of Cmdlet Output](./types-of-cmdlet-output.md) Describes the types and output that cmdlets can generate and the methods that cmdlets call to generate the output.</span></span>

<span data-ttu-id="932ed-107">[Cmdlet은 오류 보고](./cmdlet-error-reporting.md) cmdlet 오류 보고, cmdlet 출력의 하위 집합에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="932ed-107">[Cmdlet Error Reporting](./cmdlet-error-reporting.md) Discusses cmdlet error reporting, a subset of cmdlet output.</span></span>

<span data-ttu-id="932ed-108">[출력 개체를 확장](./extending-output-objects.md) cmdlet, 함수 및 스크립트에서 반환 되는.NET Framework 개체를 확장 하는 유형 파일 (.ps1xml)를 사용 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="932ed-108">[Extending Output Objects](./extending-output-objects.md) Discusses how to use the types files (.ps1xml) to extend the .NET Framework objects that are returned by cmdlets, functions, and scripts.</span></span>

<span data-ttu-id="932ed-109">[PowerShell 형식 지정 파일](../format/powershell-formatting-files.md) 형식 지정 파일에 설명 합니다 (. format.ps1xml) Windows PowerShell에서.NET Framework 개체의 특정 집합에 대 한 기본값을 정의 하는 파일을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="932ed-109">[PowerShell Formatting Files](../format/powershell-formatting-files.md) Describes the formatting files (.format.ps1xml) files that define the default display for a specific set of .NET Framework objects in Windows PowerShell.</span></span>

<span data-ttu-id="932ed-110">[사용자 지정 서식 파일](./custom-formatting-files.md) 사용자 고유의 사용자 지정 서식 지정을 만드는 기본값 덮어쓰기 파일 표시 형식 또는 고유한 명령에서 반환 된 개체의 표시를 정의 하 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="932ed-110">[Custom Formatting Files](./custom-formatting-files.md) Describes how to create your own custom formatting files to overwrite the default display formats or to define the display of objects returned by your own commands.</span></span>

## <a name="see-also"></a><span data-ttu-id="932ed-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="932ed-111">See Also</span></span>

<span data-ttu-id="932ed-112">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)(Windows PowerShell Cmdlet 작성)</span><span class="sxs-lookup"><span data-stu-id="932ed-112">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>