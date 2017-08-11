---
ms.date: 2017-06-05
keywords: powershell,cmdlet
title: "ISEEditor 개체"
ms.assetid: 0101daf8-4e31-4e4c-ab89-01d95dcb8f46
ms.openlocfilehash: 41f2a6f7684275ad9d6d967ea67b64ca02c1c100
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2017
---
# <a name="the-iseeditor-object"></a><span data-ttu-id="910c0-103">ISEEditor 개체</span><span class="sxs-lookup"><span data-stu-id="910c0-103">The ISEEditor Object</span></span>
  <span data-ttu-id="910c0-104">**ISEEditor** 개체는 Microsoft.PowerShell.Host.ISE.ISEEditor 클래스의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-104">An **ISEEditor** object is an instance of the Microsoft.PowerShell.Host.ISE.ISEEditor class.</span></span> <span data-ttu-id="910c0-105">콘솔 창은 **ISEEditor** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-105">The Console pane is an **ISEEditor** object.</span></span> <span data-ttu-id="910c0-106">각 [ISEFile](The-ISEFile-Object.md) 개체에는 연결된 **ISEEditor** 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-106">Each [ISEFile](The-ISEFile-Object.md) object has an associated **ISEEditor** object.</span></span> <span data-ttu-id="910c0-107">다음 섹션에는 **ISEEditor** 개체의 메서드 및 속성이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-107">The following sections list the methods and properties of an **ISEEditor** object.</span></span>

## <a name="methods"></a><span data-ttu-id="910c0-108">메서드</span><span class="sxs-lookup"><span data-stu-id="910c0-108">Methods</span></span>

### <a name="clear"></a><span data-ttu-id="910c0-109">Clear\(\)</span><span class="sxs-lookup"><span data-stu-id="910c0-109">Clear\(\)</span></span>
  <span data-ttu-id="910c0-110">Windows PowerShell ISE 2.0 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-110">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="910c0-111">편집기에서 텍스트를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-111">Clears the text in the editor.</span></span>

```PowerShell
# Clears the text in the Console pane.
$psISE.CurrentPowerShellTab.ConsolePane.Clear()
```

### <a name="ensurevisibleint-linenumber"></a><span data-ttu-id="910c0-112">EnsureVisible\(int lineNumber\)</span><span class="sxs-lookup"><span data-stu-id="910c0-112">EnsureVisible\(int lineNumber\)</span></span>
  <span data-ttu-id="910c0-113">Windows PowerShell ISE 2.0 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-113">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="910c0-114">지정된 **lineNumber** 매개 변수 값에 해당하는 줄이 표시되도록 편집기를 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-114">Scrolls the editor so that the line that corresponds to the specified **lineNumber** parameter value is visible.</span></span> <span data-ttu-id="910c0-115">지정된 줄 번호가 유효한 줄 번호를 정의하는 마지막 줄 번호인 1의 범위 밖에 있는 경우 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-115">It throws an exception if the specified line number is outside the range of 1,last line number, which defines the valid line numbers.</span></span>

 <span data-ttu-id="910c0-116">**lineNumber**
 표시할 줄의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-116">**lineNumber**
 The number of the line that is to be made visible.</span></span>

```PowerShell
# Scrolls the text in the Script pane so that the fifth line is in view. 
$psISE.CurrentFile.Editor.EnsureVisible(5)
```

### <a name="focus"></a><span data-ttu-id="910c0-117">Focus\(\)</span><span class="sxs-lookup"><span data-stu-id="910c0-117">Focus\(\)</span></span>
  <span data-ttu-id="910c0-118">Windows PowerShell ISE 2.0 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-118">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="910c0-119">포커스를 편집기로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-119">Sets the focus to the editor.</span></span>

```PowerShell
# Sets focus to the Console pane. 
$psISE.CurrentPowerShellTab.ConsolePane.Focus()
```

### <a name="getlinelengthint-linenumber-"></a><span data-ttu-id="910c0-120">GetLineLength\(int lineNumber \)</span><span class="sxs-lookup"><span data-stu-id="910c0-120">GetLineLength\(int lineNumber \)</span></span>
  <span data-ttu-id="910c0-121">Windows PowerShell ISE 2.0 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-121">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="910c0-122">줄 번호로 지정된 줄에 대한 정수 줄 길이를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-122">Gets the line length as an integer for the line that is specified by the line number.</span></span>

 <span data-ttu-id="910c0-123">**lineNumber**
 길이를 가져올 줄의 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-123">**lineNumber**
 The number of the line of which to get the length.</span></span>

 <span data-ttu-id="910c0-124">**Returns**
 지정된 줄 번호의 줄에 대한 줄 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-124">**Returns**
 The line length for the line at the specified line number.</span></span>

```PowerShell
# Gets the length of the first line in the text of the Command pane. 
$psISE.CurrentPowerShellTab.ConsolePane.GetLineLength(1)
```

### <a name="gotomatch"></a><span data-ttu-id="910c0-125">GoToMatch\(\)</span><span class="sxs-lookup"><span data-stu-id="910c0-125">GoToMatch\(\)</span></span>
  <span data-ttu-id="910c0-126">Windows PowerShell ISE 3.0 이상에서 지원되며, 이전 버전에는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-126">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span> 

 <span data-ttu-id="910c0-127">편집기 개체의 **CanGoToMatch** 속성이 **$true**인 경우, 캐럿을 일치하는 문자로 이동합니다. 캐럿이 여는 괄호, 대괄호 또는 중괄호 \(,\[,{ 바로 앞에 있거나 닫는 괄호, 대괄호 또는 중괄호 \),\],} 바로 뒤에 있을 때 이런 일이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-127">Moves the caret to the matching character if the **CanGoToMatch** property of the editor object is **$true**, which occurs when the caret is immediately before an opening parenthesis, bracket, or brace - \(,\[,{ - or immediately after a closing parenthesis, bracket, or brace - \),\],}.</span></span>  <span data-ttu-id="910c0-128">캐럿은 여는 문자가 앞이나 닫는 문자 뒤에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-128">The caret is placed before an opening character or after a closing character.</span></span> <span data-ttu-id="910c0-129">**CanGoToMatch** 속성이 **$false**라면, 이 메서드는 아무 작업도 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-129">If the **CanGoToMatch** property is **$false**, then this method does nothing.</span></span> <span data-ttu-id="910c0-130">[CanGoToMatch](#cangotomatch)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="910c0-130">See [CanGoToMatch](#cangotomatch).</span></span>

```PowerShell
# Test to see if the caret is next to a parenthesis, bracket, or brace.
```

### <a name="inserttext-text-"></a><span data-ttu-id="910c0-131">InsertText\( text \)</span><span class="sxs-lookup"><span data-stu-id="910c0-131">InsertText\( text \)</span></span>
  <span data-ttu-id="910c0-132">Windows PowerShell ISE 2.0 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-132">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="910c0-133">선택 영역을 텍스트로 바꾸거나, 현재 캐럿 위치에 텍스트를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-133">Replaces the selection with text or inserts text at the current caret position.</span></span>

 <span data-ttu-id="910c0-134">**text** - String 삽입할 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-134">**text** - String The text to insert.</span></span>

 <span data-ttu-id="910c0-135">이 항목의 뒷부분에 나오는 [스크립팅 예제](#example)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="910c0-135">See the [Scripting Example](#example) later in this topic.</span></span>

### <a name="select-startline-startcolumn-endline-endcolumn-"></a><span data-ttu-id="910c0-136">Select\( startLine, startColumn, endLine, endColumn \)</span><span class="sxs-lookup"><span data-stu-id="910c0-136">Select\( startLine, startColumn, endLine, endColumn \)</span></span>
  <span data-ttu-id="910c0-137">Windows PowerShell ISE 2.0 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-137">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="910c0-138">**startLine**, **startColumn**, **endLine** 및 **endColumn** 매개 변수에서 텍스트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-138">Selects the text from the **startLine**, **startColumn**, **endLine**, and **endColumn** parameters.</span></span>

 <span data-ttu-id="910c0-139">**startLine** - Integer 선택이 시작되는 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-139">**startLine** - Integer The line where the selection starts.</span></span>

 <span data-ttu-id="910c0-140">**startColumn** - Integer 선택이 시작되는 시작 줄 내의 열입니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-140">**startColumn** - Integer The column within the start line where the selection starts.</span></span>

 <span data-ttu-id="910c0-141">**endLine** - Integer 선택이 끝나는 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-141">**endLine** - Integer The line where the selection ends.</span></span>

 <span data-ttu-id="910c0-142">**endColumn** - Integer 선택이 끝나는 끝 줄 내의 열입니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-142">**endColumn** - Integer The column within the end line where the selection ends.</span></span>

 <span data-ttu-id="910c0-143">이 항목의 뒷부분에 나오는 [스크립팅 예제](#example)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="910c0-143">See the  [Scripting Example](#example) later in this topic.</span></span>

### <a name="selectcaretline"></a><span data-ttu-id="910c0-144">SelectCaretLine\(\)</span><span class="sxs-lookup"><span data-stu-id="910c0-144">SelectCaretLine\(\)</span></span>
  <span data-ttu-id="910c0-145">Windows PowerShell ISE 2.0 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-145">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="910c0-146">현재 캐럿을 포함하는 텍스트의 전체 줄을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-146">Selects the entire line of text that currently contains the caret.</span></span>

```PowerShell
# First, set the caret position on line 5.
$psISE.CurrentFile.Editor.SetCaretPosition(5,1) 
# Now select that entire line of text
$psISE.CurrentFile.Editor.SelectCaretLine()
```

### <a name="setcaretposition-linenumber-columnnumber-"></a><span data-ttu-id="910c0-147">SetCaretPosition\( lineNumber, columnNumber \)</span><span class="sxs-lookup"><span data-stu-id="910c0-147">SetCaretPosition\( lineNumber, columnNumber \)</span></span>
  <span data-ttu-id="910c0-148">Windows PowerShell ISE 2.0 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-148">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="910c0-149">줄 번호 및 열 번호로 캐럿 위치를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-149">Sets the caret position at the line number and the column number.</span></span> <span data-ttu-id="910c0-150">캐럿 줄 번호 또는 캐럿 열 번호가 각각의 유효한 범위를 벗어나는 경우 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-150">It throws an exception if either the caret line number  or the caret column number  are out of their respective valid ranges.</span></span>

 <span data-ttu-id="910c0-151">**lineNumber** - Integer 캐럿 줄 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-151">**lineNumber** - Integer The caret line number.</span></span>

 <span data-ttu-id="910c0-152">**columnNumber** - Integer 캐럿 열 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-152">**columnNumber** - Integer The caret column number.</span></span>

```PowerShell
# Set the CaretPosition.
$psISE.CurrentFile.Editor.SetCaretPosition(5,1)
```

### <a name="toggleoutliningexpansion"></a><span data-ttu-id="910c0-153">ToggleOutliningExpansion\(\)</span><span class="sxs-lookup"><span data-stu-id="910c0-153">ToggleOutliningExpansion\(\)</span></span>
  <span data-ttu-id="910c0-154">Windows PowerShell ISE 3.0 이상에서 지원되며, 이전 버전에는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-154">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span> 

 <span data-ttu-id="910c0-155">모든 개요 섹션을 확장하거나 축소합니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-155">Causes all the outline sections to expand or collapse.</span></span>

```PowerShell
# Toggle the outlining expansion
$psISE.CurrentFile.Editor.ToggleOutliningExpansion()
```

## <a name="properties"></a><span data-ttu-id="910c0-156">속성</span><span class="sxs-lookup"><span data-stu-id="910c0-156">Properties</span></span>

###  <span data-ttu-id="910c0-157"><a name="CanGoToMatch"></a> CanGoToMatch</span><span class="sxs-lookup"><span data-stu-id="910c0-157"><a name="CanGoToMatch"></a> CanGoToMatch</span></span>
  <span data-ttu-id="910c0-158">Windows PowerShell ISE 3.0 이상에서 지원되며, 이전 버전에는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-158">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span> 

 <span data-ttu-id="910c0-159">캐럿이 괄호, 대괄호 또는 중괄호(\(\), \[\], {}) 옆에 있는지 여부를 나타내는 읽기 전용 부울 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-159">The read-only Boolean property to indicate whether the caret is next to a parenthesis, bracket, or brace - \(\), \[\], {}.</span></span> <span data-ttu-id="910c0-160">캐럿이 여는 문자의 바로 앞 또는 닫는 문자 바로 뒤에 있다면 이 속성 값은 **$true**입니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-160">If the caret is immediately before the opening character or immediately after the closing character of a pair, then this property value is **$true**.</span></span> <span data-ttu-id="910c0-161">그렇지 않으면 **$false**입니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-161">Otherwise, it is **$false**.</span></span>

```PowerShell
# Test to see if the caret is next to a parenthesis, bracket, or brace
$psISE.CurrentFile.Editor.CanGoToMatch
```

###  <span data-ttu-id="910c0-162"><a name="CaretColumn"></a> CaretColumn</span><span class="sxs-lookup"><span data-stu-id="910c0-162"><a name="CaretColumn"></a> CaretColumn</span></span>
  <span data-ttu-id="910c0-163">Windows PowerShell ISE 2.0 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-163">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="910c0-164">캐럿의 위치에 해당하는 열 번호를 가져오는 읽기 전용 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-164">The read-only property that gets the column number that corresponds to the position of the caret.</span></span>

```PowerShell
# Get the CaretColumn.
$psISE.CurrentFile.Editor.CaretColumn
```

###  <span data-ttu-id="910c0-165"><a name="CaretLine"></a> CaretLine</span><span class="sxs-lookup"><span data-stu-id="910c0-165"><a name="CaretLine"></a> CaretLine</span></span>
  <span data-ttu-id="910c0-166">Windows PowerShell ISE 2.0 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-166">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="910c0-167">캐럿을 포함하는 줄 번호를 가져오는 읽기 전용 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-167">The read-only property that gets the number of the line that contains the caret.</span></span>

```PowerShell
# Get the CaretLine.
$psISE.CurrentFile.Editor.CaretLine
```

###  <span data-ttu-id="910c0-168"><a name="CaretLineText"></a> CaretLineText</span><span class="sxs-lookup"><span data-stu-id="910c0-168"><a name="CaretLineText"></a> CaretLineText</span></span>
  <span data-ttu-id="910c0-169">Windows PowerShell ISE 2.0 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-169">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="910c0-170">캐럿을 포함하는 텍스트의 전체 줄을 가져오는 읽기 전용 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-170">The read-only property that gets the complete line of text that contains the caret.</span></span>

```PowerShell
# Get all of the text on the line that contains the caret.
$psISE.CurrentFile.Editor.CaretLineText
```

###  <span data-ttu-id="910c0-171"><a name="LineCount"></a> LineCount</span><span class="sxs-lookup"><span data-stu-id="910c0-171"><a name="LineCount"></a> LineCount</span></span>
  <span data-ttu-id="910c0-172">Windows PowerShell ISE 2.0 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-172">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="910c0-173">편집기에서 줄 수를 가져오는 읽기 전용 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-173">The read-only property that gets the line count from the editor.</span></span>

```PowerShell
# Get the LineCount.
$psISE.CurrentFile.Editor.LineCount
```

###  <span data-ttu-id="910c0-174"><a name="SelectedText"></a> SelectedText</span><span class="sxs-lookup"><span data-stu-id="910c0-174"><a name="SelectedText"></a> SelectedText</span></span>
  <span data-ttu-id="910c0-175">Windows PowerShell ISE 2.0 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-175">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="910c0-176">편집기에서 선택한 텍스트를 가져오는 읽기 전용 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-176">The read-only property that gets the selected text from the editor.</span></span>

 <span data-ttu-id="910c0-177">이 항목의 뒷부분에 나오는 [스크립팅 예제](#example)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="910c0-177">See the  [Scripting Example](#example) later in this topic.</span></span>

###  <span data-ttu-id="910c0-178"><a name="Text"></a> Text</span><span class="sxs-lookup"><span data-stu-id="910c0-178"><a name="Text"></a> Text</span></span>
  <span data-ttu-id="910c0-179">Windows PowerShell ISE 2.0 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-179">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="910c0-180">편집기에 있는 텍스트를 설정하거나 가져오는 읽기/쓰기 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="910c0-180">The read/write property that gets or sets the text in the editor.</span></span>

 <span data-ttu-id="910c0-181">이 항목의 뒷부분에 나오는 [스크립팅 예제](#example)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="910c0-181">See the [Scripting Example](#example) later in this topic.</span></span>

##  <span data-ttu-id="910c0-182"><a name="example"></a> 스크립팅 예제</span><span class="sxs-lookup"><span data-stu-id="910c0-182"><a name="example"></a> Scripting Example</span></span>

```PowerShell
# This illustrates how you can use the length of a line to
# select the entire line and shows how you can make it lowercase. 
# You must run this in the Console pane. It will not run in the Script pane.
# Begin by getting a variable that points to the editor.
$myEditor = $psISE.CurrentFile.Editor
# Clear the text in the current file editor.
$myEditor.Clear()

# Make sure the file has five lines of text.
$myEditor.InsertText("LINE1 `n")
$myEditor.InsertText("LINE2 `n")
$myEditor.InsertText("LINE3 `n")
$myEditor.InsertText("LINE4 `n")
$myEditor.InsertText("LINE5 `n")

# Use the GetLineLength method to get the length of the third line. 
$endColumn= $myEditor.GetLineLength(3)
# Select the text in the first three lines.
$myEditor.Select(1,1,3,$endColumn + 1)
$selection = $myEditor.SelectedText
# Clear all the text in the editor.
$myEditor.Clear()
# Add the selected text back, but in lower case.
$myEditor.InsertText($selection.ToLower())
```

## <a name="see-also"></a><span data-ttu-id="910c0-183">참고 항목</span><span class="sxs-lookup"><span data-stu-id="910c0-183">See Also</span></span>
- [<span data-ttu-id="910c0-184">ISEFile 개체</span><span class="sxs-lookup"><span data-stu-id="910c0-184">The ISEFile Object</span></span>](The-ISEFile-Object.md) 
- [<span data-ttu-id="910c0-185">PowerShellTab 개체</span><span class="sxs-lookup"><span data-stu-id="910c0-185">The PowerShellTab Object</span></span>](The-PowerShellTab-Object.md) 
- [<span data-ttu-id="910c0-186">Windows PowerShell ISE 스크립팅 개체 모델</span><span class="sxs-lookup"><span data-stu-id="910c0-186">The Windows PowerShell ISE Scripting Object Model</span></span>](The-Windows-PowerShell-ISE-Scripting-Object-Model.md) 
- [<span data-ttu-id="910c0-187">Windows PowerShell ISE 개체 모델 참조</span><span class="sxs-lookup"><span data-stu-id="910c0-187">Windows PowerShell ISE Object Model Reference</span></span>](Windows-PowerShell-ISE-Object-Model-Reference.md) 
- [<span data-ttu-id="910c0-188">ISE 개체 모델 계층 구조</span><span class="sxs-lookup"><span data-stu-id="910c0-188">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)

  