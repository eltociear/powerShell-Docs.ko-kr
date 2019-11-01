---
title: 사용자 지정 서식 파일 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 85d27545-8097-4010-9947-6d8b3ce2eac0
caps.latest.revision: 15
ms.openlocfilehash: 71c1c181058c5646c817b90d9832976a78c6c7de
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369832"
---
# <a name="custom-formatting-files"></a><span data-ttu-id="6dade-102">형식 지정 파일 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="6dade-102">Custom Formatting Files</span></span>

<span data-ttu-id="6dade-103">Cmdlet, 함수 및 스크립트에서 반환 되는 개체의 표시 형식은 형식 지정 파일 (types.ps1xml 파일)을 사용 하 여 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-103">The display format for the objects returned by cmdlets, functions, and scripts are defined using formatting files (format.ps1xml files).</span></span> <span data-ttu-id="6dade-104">이러한 파일 중 일부는 windows powershell cmdlet에서 반환 되는 개체에 대 한 기본 표시 형식을 정의 하기 위해 Windows PowerShell에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-104">Several of these files are provided by Windows PowerShell to define the default display format for those objects returned by Windows PowerShell cmdlets.</span></span> <span data-ttu-id="6dade-105">그러나 사용자 고유의 사용자 지정 서식 파일을 만들어 기본 표시 형식을 덮어쓰거나 사용자의 명령으로 반환 되는 개체의 표시를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-105">However, you can also create your own custom formatting files to overwrite the default display formats or to define the display of objects returned by your own commands.</span></span>

<span data-ttu-id="6dade-106">Windows PowerShell은 이러한 서식 지정 파일의 데이터를 사용 하 여 표시 되는 내용과 데이터의 형식 지정 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-106">Windows PowerShell uses the data in these formatting files to determine what is displayed and how the data is formatted.</span></span> <span data-ttu-id="6dade-107">표시 되는 데이터에는 개체의 속성 또는 스크립트 블록의 값이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-107">The displayed data can include the properties of an object or the value of a script block.</span></span>  <span data-ttu-id="6dade-108">스크립트 블록은 개체의 속성에서 직접 사용할 수 없는 일부 값을 표시 하려는 경우에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-108">Script blocks are used if you want to display some value that is not available directly from the properties of an object.</span></span> <span data-ttu-id="6dade-109">예를 들어 개체의 두 속성 값을 추가 하 고 합계를 별도의 데이터로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-109">For example, you may want to add the value of two properties of an object and display the sum as a separate piece of data.</span></span> <span data-ttu-id="6dade-110">사용자 고유의 서식 지정 파일을 작성 하는 경우 표시할 개체에 대 한 *보기* 를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-110">When you write your own formatting file, you will need to define *views* for the objects that you want to display.</span></span> <span data-ttu-id="6dade-111">각 개체에 대해 단일 뷰를 정의 하거나, 여러 개체에 대해 단일 뷰를 정의 하거나, 동일한 개체에 대해 여러 뷰를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-111">You can define a single view for each object, you can define a single view for multiple objects, or you can define multiple views for the same object.</span></span> <span data-ttu-id="6dade-112">정의할 수 있는 뷰 수에는 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-112">There is no limit to the number of views that you can define.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6dade-113">파일 서식 지정은 파이프라인에 반환 되는 개체의 요소를 결정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-113">Formatting files do not determine the elements of an object that are returned to the pipeline.</span></span> <span data-ttu-id="6dade-114">개체가 파이프라인으로 반환 되 면 해당 개체의 모든 멤버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-114">When an object is returned to the pipeline, all members of that object are available.</span></span>

## <a name="format-views"></a><span data-ttu-id="6dade-115">뷰 서식</span><span class="sxs-lookup"><span data-stu-id="6dade-115">Format Views</span></span>

<span data-ttu-id="6dade-116">서식 보기에서는 개체를 테이블 형식으로 표시 하 고, 목록 형식, 너비를 지정 하 고, 사용자 지정 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-116">Formatting views can display objects in a table format, a list format, a wide format, and a custom format.</span></span> <span data-ttu-id="6dade-117">대부분의 경우 각 서식 정의는 뷰를 설명 하는 XML 태그 집합으로 설명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-117">For the most part, each formatting definition is described by a set of XML tags that describe a view.</span></span> <span data-ttu-id="6dade-118">각 뷰에는 뷰 이름, 뷰를 사용 하는 개체 및 뷰의 요소 (예: 테이블 뷰의 열 및 행 정보)가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-118">Each view contains the name of the view, the objects that use the view, and the elements of the view, such as the column and row information for a table view.</span></span>

<span data-ttu-id="6dade-119">다음 뷰를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-119">The following views are available.</span></span>

<span data-ttu-id="6dade-120">테이블 뷰 하나 이상의 열에 있는 개체 또는 스크립트 블록 값의 속성을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-120">Table view Lists the properties of an object or a script block value in one or more columns.</span></span> <span data-ttu-id="6dade-121">각 열은 개체의 속성 또는 스크립트 블록 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-121">Each column represents a property of the object or a script block value.</span></span> <span data-ttu-id="6dade-122">개체의 모든 속성, 개체 속성의 하위 집합 또는 속성 및 스크립트 블록 값의 조합을 표시 하는 테이블 뷰를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-122">You can define a table view that displays all the properties of an object, a subset of the properties of an object, or a combination of properties and script block values.</span></span> <span data-ttu-id="6dade-123">테이블의 각 행은 반환 된 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-123">Each row of the table represents a returned object.</span></span> <span data-ttu-id="6dade-124">이 보기에 대 한 자세한 내용은 [테이블 뷰](../format/creating-a-table-view.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6dade-124">For more information about this view, see [Table View](../format/creating-a-table-view.md).</span></span>

<span data-ttu-id="6dade-125">목록 뷰 단일 열에 개체 또는 스크립트 블록 값의 속성을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-125">List view Lists the properties of an object or a script block value in a single column.</span></span> <span data-ttu-id="6dade-126">목록의 각 행에는 선택적 레이블 또는 속성 이름과 속성 또는 스크립트 블록 값이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-126">Each row of the list displays an optional label or the property name followed by the value of the property or script block.</span></span> <span data-ttu-id="6dade-127">이 보기에 대 한 자세한 내용은 [목록 뷰](../format/creating-a-list-view.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6dade-127">For more information about this view, see [List View](../format/creating-a-list-view.md).</span></span>

<span data-ttu-id="6dade-128">넓은 뷰 하나 이상의 열에 있는 단일 개체 속성 또는 스크립트 블록 값을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-128">Wide view Lists a single property of an object or a script block value in one or more columns.</span></span> <span data-ttu-id="6dade-129">이 보기에 대 한 레이블이나 머리글이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-129">There is no label or header for this view.</span></span> <span data-ttu-id="6dade-130">이 보기에 대 한 자세한 내용은 [Wide view](../format/creating-a-wide-view.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6dade-130">For more information about this view, see [Wide View](../format/creating-a-wide-view.md).</span></span>

<span data-ttu-id="6dade-131">사용자 지정 뷰는 테이블 뷰, 목록 뷰 또는 넓은 보기의 고정 구조를 따르지 않는 개체 속성 또는 스크립트 블록 값의 사용자 지정 가능한 뷰를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-131">Custom view Displays a customizable view of object properties or script block values that does not adhere to the rigid structure of table views, list views, or wide views.</span></span> <span data-ttu-id="6dade-132">독립 실행형 사용자 지정 보기를 정의 하거나, 다른 보기에서 사용 되는 사용자 지정 보기 (예: 테이블 뷰 또는 목록 보기)를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-132">You can define a standalone custom view, or you can define a custom view that is used by another view, such as a table view or list view.</span></span> <span data-ttu-id="6dade-133">이 보기에 대 한 자세한 내용은 [사용자 지정 뷰](../format/creating-custom-controls.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6dade-133">For more information about this view, see [Custom View](../format/creating-custom-controls.md).</span></span>

## <a name="view-xml-elements"></a><span data-ttu-id="6dade-134">XML 요소 보기</span><span class="sxs-lookup"><span data-stu-id="6dade-134">View XML Elements</span></span>

<span data-ttu-id="6dade-135">다음 예에서는 두 개의 열이 포함 된 테이블 뷰를 정의 하는 데 사용 되는 XML 태그를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-135">The following example shows the XML tags used to define a table view that contains two columns.</span></span> <span data-ttu-id="6dade-136">[Viewdefinitions](../format/viewdefinitions-element-format.md) 요소는 서식 파일에 정의 된 모든 뷰에 대 한 컨테이너 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-136">The [ViewDefinitions](../format/viewdefinitions-element-format.md) element is the container element for all the views defined in the formatting file.</span></span> <span data-ttu-id="6dade-137">[View](../format/view-element-format.md) 요소는 특정 테이블, 목록, 전체 또는 사용자 지정 뷰를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-137">The [View](../format/view-element-format.md) element defines the specific table, list, wide, or custom view.</span></span> <span data-ttu-id="6dade-138">각 뷰 내에서 [name](../format/name-element-for-view-format.md) 요소는 뷰의 이름을 지정 하 고 [viewselectedby](../format/viewselectedby-element-format.md) 요소는 뷰를 사용 하는 개체를 정의 하며, `TableControl` 요소와 같은 다른 컨트롤 요소는 뷰의 형식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dade-138">Within each view, the [Name](../format/name-element-for-view-format.md) element specifies the name of the view, the [ViewSelectedBy](../format/viewselectedby-element-format.md) element defines the objects that use the view, and the different control elements (such as the `TableControl` element) define the format of the view.</span></span>

```xml
ViewDefinitions
  <View>
    <Name>Name of View</Name>
    <ViewSelectedBy>
      <TypeName>Object to display using this view</TypeName>
      <TypeName>Object to display using this view</TypeName>
    </ViewSelectedBy>
    <TableControl>
      <TableHeaders>
        <TableColumnHeader>
          <Width></Width>
        </TableColumnHeader>
        <TableColumnHeader>
          <Width></Width>
        </TableColumnHeader>
      </TableHeaders>
      <TableRowEntries>
        <TableRowEntry>
          <TableColumnItems>
            <TableColumnItem>
              <PropertyName>Header for column 1</PropertyName>
            </TableColumnItem>
            <TableColumnItem>
              <PropertyName>Header for column 2</PropertyName>
            </TableColumnItem>
          </TableColumnItems>
        </TableRowEntry>
      </TableRowEntries>
    </TableControl)
  </View>
</ViewDefinitions>

```

## <a name="see-also"></a><span data-ttu-id="6dade-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6dade-139">See Also</span></span>

[<span data-ttu-id="6dade-140">테이블 보기</span><span class="sxs-lookup"><span data-stu-id="6dade-140">Table View</span></span>](../format/creating-a-table-view.md)

[<span data-ttu-id="6dade-141">목록 보기</span><span class="sxs-lookup"><span data-stu-id="6dade-141">List View</span></span>](../format/creating-a-list-view.md)

[<span data-ttu-id="6dade-142">넓은 보기</span><span class="sxs-lookup"><span data-stu-id="6dade-142">Wide View</span></span>](../format/creating-a-wide-view.md)

[<span data-ttu-id="6dade-143">사용자 지정 보기</span><span class="sxs-lookup"><span data-stu-id="6dade-143">Custom View</span></span>](../format/creating-custom-controls.md)

<span data-ttu-id="6dade-144">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)(Windows PowerShell Cmdlet 작성)</span><span class="sxs-lookup"><span data-stu-id="6dade-144">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>