---
title: 참조 문서 편집
description: 이 문서에서는 cmdlet 참조를 편집하기 위한 특정 요구 사항과 PowerShell 설명서의 정보 항목에 대해 설명합니다.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 3c6f1b4fc27ca8ece7ec30317daf4ed2a6bc9228
ms.sourcegitcommit: 18d832858a7b8ea094763afa753e0f48f01372e7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2020
ms.locfileid: "79060328"
---
# <a name="editing-reference-articles"></a><span data-ttu-id="aaa37-103">참조 문서 편집</span><span class="sxs-lookup"><span data-stu-id="aaa37-103">Editing reference articles</span></span>

<span data-ttu-id="aaa37-104">Cmdlet 참조 문서에는 특정 구조가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaa37-104">Cmdlet reference articles have a specific structure.</span></span> <span data-ttu-id="aaa37-105">이 구조는 [PlatyPS][]에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaa37-105">This structure is defined by [PlatyPS][].</span></span>
<span data-ttu-id="aaa37-106">PlatyPS는 Markdown으로 PowerShell 모듈에 대한 cmdlet 도움말을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa37-106">PlatyPS generates the cmdlet help for PowerShell modules in Markdown.</span></span> <span data-ttu-id="aaa37-107">Markdown 파일을 편집한 후에는 PlatyPS를 사용하여 `Get-Help` cmdlet에서 사용하는 MAML 도움말 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="aaa37-107">After editing the Markdown files, PlatyPS is used create the MAML help files used by the `Get-Help` cmdlet.</span></span>

<span data-ttu-id="aaa37-108">PlatyPS에는 코드에 작성된 cmdlet 참조에 대한 하드 코딩된 스키마가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaa37-108">PlatyPS has a hard-coded schema for cmdlet reference that is written into the code.</span></span> <span data-ttu-id="aaa37-109">[platyPS.schema.md][] 문서는 이 구조를 설명하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa37-109">The [platyPS.schema.md][] document attempts to describe this structure.</span></span> <span data-ttu-id="aaa37-110">스키마를 위반할 경우 참가자의 기여를 수락하기 전에 수정해야 하는 빌드 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa37-110">Schema violations cause build errors that must be fixed before we can accept your contribution.</span></span>

## <a name="general-guidelines"></a><span data-ttu-id="aaa37-111">일반 지침</span><span class="sxs-lookup"><span data-stu-id="aaa37-111">General guidelines</span></span>

- <span data-ttu-id="aaa37-112">헤더 구조를 제거하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="aaa37-112">Do not remove any of the header structures.</span></span> <span data-ttu-id="aaa37-113">PlatyPS에는 특정 헤더 집합이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa37-113">PlatyPS expects a specific set of headers.</span></span>
- <span data-ttu-id="aaa37-114">**Input type** 및 **Output type** 헤더에는 형식이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa37-114">The **Input type** and **Output type** headers must have a type.</span></span> <span data-ttu-id="aaa37-115">Cmdlet이 입력을 사용하지 않거나 값을 반환하지 않는 경우 값 `None`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa37-115">If the cmdlet does not take input or return a value then use the value `None`.</span></span>
- <span data-ttu-id="aaa37-116">펜스된 코드 블록은 [예제](#structuring-examples) 섹션에서만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaa37-116">Fenced code blocks are only allowed in the [Examples](#structuring-examples) section.</span></span>
- <span data-ttu-id="aaa37-117">인라인 코드 스팬은 모든 단락에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaa37-117">Inline code spans can be used in any paragraph.</span></span>

## <a name="formatting-about_-files"></a><span data-ttu-id="aaa37-118">About_ 파일 서식 지정</span><span class="sxs-lookup"><span data-stu-id="aaa37-118">Formatting About_ files</span></span>

<span data-ttu-id="aaa37-119">이제 `About_*` 파일은 PlatyPS가 아니라 [Pandoc][]에 의해 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaa37-119">`About_*` files are now processed by [Pandoc][], instead of PlatyPS.</span></span> <span data-ttu-id="aaa37-120">`About_*` 파일은 모든 버전의 PowerShell에서 최상의 호환성을 보장하도록 게시 도구를 사용하여 서식 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaa37-120">`About_*` files are formatted for the best compatibility across all versions of PowerShell and with the publishing tools.</span></span>

<span data-ttu-id="aaa37-121">기본 서식 지정 지침:</span><span class="sxs-lookup"><span data-stu-id="aaa37-121">Basic formatting guidelines:</span></span>

- <span data-ttu-id="aaa37-122">줄을 80자로 제한</span><span class="sxs-lookup"><span data-stu-id="aaa37-122">Limit lines to 80 characters</span></span>
- <span data-ttu-id="aaa37-123">코드 블록 및 테이블은 76자로 제한됩니다. Pandoc이 일반 텍스트로 변환하는 동안 공백 4개를 들여쓰기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="aaa37-123">Code blocks and tables are limited to 76 characters because Pandoc indents these by four spaces during conversion to plain text</span></span>
- <span data-ttu-id="aaa37-124">테이블이 76자 이내에 들어가야 함</span><span class="sxs-lookup"><span data-stu-id="aaa37-124">Tables need to fit within 76 characters</span></span>
  - <span data-ttu-id="aaa37-125">여러 줄에 걸치는 셀의 내용을 수동으로 줄 바꿈</span><span class="sxs-lookup"><span data-stu-id="aaa37-125">Manually wrap contents of cells across multiple lines</span></span>
  - <span data-ttu-id="aaa37-126">각 줄에서 열기 및 닫기 `|` 문자를 사용</span><span class="sxs-lookup"><span data-stu-id="aaa37-126">Use opening and closing `|` characters on each line</span></span>
  - <span data-ttu-id="aaa37-127">[about_Comparison_Operators][about-example]의 작업 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aaa37-127">See a working example in [about_Comparison_Operators][about-example]</span></span>
- <span data-ttu-id="aaa37-128">Pandoc 특수 문자 `\`,`$` 및 `<` 사용</span><span class="sxs-lookup"><span data-stu-id="aaa37-128">Using Pandoc special characters `\`,`$`, and `<`</span></span>
  - <span data-ttu-id="aaa37-129">헤더 안에서 이러한 문자는 선행 `\` 문자를 사용하여 이스케이프하거나 역따옴표(`` ` ``)으로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa37-129">Within a header - these characters must be escaped using a leading `\` character or enclosed in backticks (`` ` ``)</span></span>
  - <span data-ttu-id="aaa37-130">단락 안에서 이러한 문자는 코드 스팬에 넣어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa37-130">Within a paragraph, these characters should be put into code spans.</span></span> <span data-ttu-id="aaa37-131">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="aaa37-131">For example:</span></span>

    ~~~markdown
    ### The purpose of the \$foo variable

    The `$foo` variable is used to store ...
    ~~~

## <a name="structuring-examples"></a><span data-ttu-id="aaa37-132">예제 구조화</span><span class="sxs-lookup"><span data-stu-id="aaa37-132">Structuring examples</span></span>

<span data-ttu-id="aaa37-133">PlatyPS 스키마에서 **EXAMPLES** 헤더는 H2 헤더이며 각 예제는 H3 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="aaa37-133">In the PlatyPS schema, the **EXAMPLES** header is an H2 header and each example is an H3 header.</span></span>

<span data-ttu-id="aaa37-134">예제 내에서 스키마는 코드 블록을 단락으로 구분할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aaa37-134">Within an example, the schema does not allow code blocks to be separated by paragraphs.</span></span> <span data-ttu-id="aaa37-135">지원되는 스키마는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aaa37-135">The supported schema is:</span></span>

```
### Example #X title

0 or more paragraphs
1 or more code blocks
0 or more paragraphs.
```

<span data-ttu-id="aaa37-136">각 예제에 번호를 표시하고 간단한 제목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa37-136">Number each example and add a brief title.</span></span>

<span data-ttu-id="aaa37-137">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="aaa37-137">For example:</span></span>

### <a name="example-1-get-cmdlets-functions-and-aliases"></a><span data-ttu-id="aaa37-138">예제 1: Cmdlet, 함수 및 별칭 가져오기</span><span class="sxs-lookup"><span data-stu-id="aaa37-138">Example 1: Get cmdlets, functions, and aliases</span></span>

<span data-ttu-id="aaa37-139">다음 명령은 컴퓨터에 설치된 Windows PowerShell cmdlet, 함수 및 별칭을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="aaa37-139">This command gets the PowerShell cmdlets, functions, and aliases that are installed on the computer.</span></span>

```powershell
Get-Command
```

### <a name="example-2-get-commands-in-the-current-session"></a><span data-ttu-id="aaa37-140">예제 2: 현재 세션의 명령 가져오기</span><span class="sxs-lookup"><span data-stu-id="aaa37-140">Example 2: Get commands in the current session</span></span>

```powershell
Get-Command -ListImported
```

## <a name="next-steps"></a><span data-ttu-id="aaa37-141">다음 단계</span><span class="sxs-lookup"><span data-stu-id="aaa37-141">Next steps</span></span>

[<span data-ttu-id="aaa37-142">편집 검사 목록</span><span class="sxs-lookup"><span data-stu-id="aaa37-142">Editorial checklist</span></span>](editorial-checklist.md)

<!-- link references -->
[PlatyPS]: https://github.com/powershell/platyps
[platyPS.schema.md]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[issue1806]: https://github.com/MicrosoftDocs/PowerShell-Docs/issues/1806
[about-example]: https://github.com/MicrosoftDocs/PowerShell-Docs/reference/5.1/Microsoft.PowerShell.Core/About/about_Comparison_Operators.md
[Pandoc]: https://pandoc.org