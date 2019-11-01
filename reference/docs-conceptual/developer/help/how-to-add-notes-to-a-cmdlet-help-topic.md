---
title: Cmdlet 도움말 항목에 메모를 추가 하는 방법 | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bea35e5-b680-4f86-b928-176890aac99d
caps.latest.revision: 5
ms.openlocfilehash: 4e9ca9a3bbcbc900d079b9275bc47d21de9e2996
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361272"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a><span data-ttu-id="a1a64-102">Cmdlet 도움말 항목에 메모를 추가하는 방법</span><span class="sxs-lookup"><span data-stu-id="a1a64-102">How to Add Notes to a Cmdlet Help Topic</span></span>

<span data-ttu-id="a1a64-103">이 섹션에서는 Windows PowerShell® cmdlet 도움말 항목에 메모 섹션을 추가 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a64-103">This section describes how to add a Notes section to a Windows PowerShell® cmdlet Help topic.</span></span> <span data-ttu-id="a1a64-104">참고 섹션은 매개 변수에 대 한 자세한 설명과 같이 다른 구조화 된 섹션에 쉽게 맞지 않는 세부 정보를 설명 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1a64-104">The Notes section is used to explain details that do not fit easily into the other structured sections, such as a more detailed explanation of a parameter.</span></span> <span data-ttu-id="a1a64-105">이 콘텐츠에는 cmdlet이 특정 공급자와 작동 하는 방식, 몇 가지 고유 하 고 중요 한 cmdlet의 용도 또는 가능한 오류 조건을 방지 하는 방법에 대 한 설명을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1a64-105">This content could include comments on how the cmdlet works with a specific provider, some unique, yet important, uses of the cmdlet, or ways to avoid possible error conditions.</span></span>

<span data-ttu-id="a1a64-106">참고 섹션에 추가할 수 있는 메모 수에는 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1a64-106">There are no limits to the number of notes that you can add to a Notes section.</span></span> <span data-ttu-id="a1a64-107">각 메모에 대해 \<maml: alertset > 노드에 \<maml: alert > 태그 쌍을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a64-107">For each note, add a pair of \<maml:alert> tags to the \<maml:alertset> node.</span></span> <span data-ttu-id="a1a64-108">각 메모의 내용은 @no__t 0maml: 단락 > 태그 집합 내에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1a64-108">The content of each note is added within a set of \<maml:para> tags.</span></span> <span data-ttu-id="a1a64-109">공백에 \<maml: 단락 > 태그를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a64-109">Use blank \<maml:para> tags for spacing.</span></span>

<span data-ttu-id="a1a64-110">다음 XML은 두 개의 메모를 포함 하는 @no__t 0maml: alertset > 노드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a1a64-110">The following XML shows an \<maml:alertset> node with two notes.</span></span> <span data-ttu-id="a1a64-111">각 메모에는 선택적 \<maml: title > 태그가 있으며,이 태그를 사용 하 여 \<maml: alert > 태그의 모든 집합을 그룹화 할 수 있습니다. 또한 각 메모에는 공백에 대 한 콘텐츠 다음에 빈 줄이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1a64-111">Notice that each note has an optional \<maml:title> tag (titles can be used to group any set of \<maml:alert> tags), and that each note has a blank line following the content for spacing.</span></span>

```xml
<maml:alertSet>
  <maml:title>title for Note 1</maml:title>
  <maml:alert>
    <maml:para> Note 1</maml:para>
    <maml:para></maml:para>
  </maml:alert>
  <maml:title>title for Note 2</maml:title>
  <maml:alert>
    <maml:para> Note 1</maml:para>
    <maml:para></maml:para>
  </maml:alert>
</maml:alertSet>
```


