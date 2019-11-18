---
title: 공급자 cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2465420-0970-4408-9ee5-260cf444cb67
caps.latest.revision: 8
ms.openlocfilehash: e6a0711cff6a550100f584fb64ae7f59f71a3cfb
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72359982"
---
# <a name="provider-cmdlets"></a><span data-ttu-id="b48a6-102">공급자 cmdlet</span><span class="sxs-lookup"><span data-stu-id="b48a6-102">Provider cmdlets</span></span>

<span data-ttu-id="b48a6-103">사용자가 데이터 저장소를 관리 하기 위해 실행할 수 있는 cmdlet을 공급자 cmdlet 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-103">The cmdlets that the user can run to manage a data store are referred to as provider cmdlets.</span></span> <span data-ttu-id="b48a6-104">이러한 cmdlet을 지원 하려면 기본 공급자 클래스 및 인터페이스에 의해 정의 된 메서드 중 일부를 덮어써야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-104">To support these cmdlets, you need to overwrite some of the methods defined by the base provider classes and interfaces.</span></span>

## <a name="provider-cmdlets"></a><span data-ttu-id="b48a6-105">공급자 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b48a6-105">Provider Cmdlets</span></span>

<span data-ttu-id="b48a6-106">사용자가 실행할 수 있는 공급자 cmdlet은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-106">Here are the provider cmdlets that can be run by the user:</span></span>

### <a name="psdrive-cmdlets"></a><span data-ttu-id="b48a6-107">PSDrive cmdlet</span><span class="sxs-lookup"><span data-stu-id="b48a6-107">PSDrive cmdlets</span></span>

- <span data-ttu-id="b48a6-108">`Get-PSDrive`: 이 cmdlet은 현재 세션의 Windows PowerShell 드라이브를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-108">`Get-PSDrive`: This cmdlet returns the Windows PowerShell drives in the current session.</span></span> <span data-ttu-id="b48a6-109">이 cmdlet을 지원 하기 위해 메서드를 덮어쓸 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-109">You do not need to overwrite any methods to support this cmdlet.</span></span>

- <span data-ttu-id="b48a6-110">`New-PSDrive`: 이 cmdlet을 사용 하면 사용자가 Windows PowerShell 드라이브를 만들어 데이터 저장소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-110">`New-PSDrive`: This cmdlet allows the user to create Windows PowerShell drives to access the data store.</span></span> <span data-ttu-id="b48a6-111">이 cmdlet을 지원 하려면 [Newdrive](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) 및 [Newdrivedynamicparameters](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) 메서드를 덮어쓰십시오... d m d. n a m. n a m.</span><span class="sxs-lookup"><span data-stu-id="b48a6-111">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) and [System.Management.Automation.Provider.Drivecmdletprovider.Newdrivedynamicparameters](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) methods.</span></span>

- <span data-ttu-id="b48a6-112">`Remove-PSDrive`: 이 cmdlet을 사용 하면 사용자가 데이터 저장소에 액세스 하는 Windows PowerShell 드라이브를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-112">`Remove-PSDrive`: This cmdlet allows the user to remove Windows PowerShell drives that access the data store.</span></span> <span data-ttu-id="b48a6-113">이 cmdlet을 지원 하려면 System.object를 덮어씁니다. [Removedrive](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) 메서드를 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-113">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method.</span></span>

### <a name="item-cmdlets"></a><span data-ttu-id="b48a6-114">항목 cmdlet</span><span class="sxs-lookup"><span data-stu-id="b48a6-114">Item cmdlets</span></span>

- <span data-ttu-id="b48a6-115">`Clear-Item`: 이 cmdlet을 사용 하면 사용자가 데이터 저장소에 있는 항목의 값을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-115">`Clear-Item`: This cmdlet allows the user to remove the value of an item in the data store.</span></span> <span data-ttu-id="b48a6-116">이 cmdlet을 지원 하려면 [system.web](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem) . m a n a m a. m a g. m a m a. m [a g.](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters)</span><span class="sxs-lookup"><span data-stu-id="b48a6-116">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Itemcmdletprovider.Clearitem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem) and [System.Management.Automation.Provider.Itemcmdletprovider.Clearitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters) methods.</span></span>

- <span data-ttu-id="b48a6-117">`Copy-Item`: 이 cmdlet을 사용 하면 사용자가 한 위치에서 다른 위치로 항목을 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-117">`Copy-Item`: This cmdlet allows the user to copy an item from one location to another.</span></span> <span data-ttu-id="b48a6-118">이 cmdlet을 지원 하려면 [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) 및 [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters) . m a n a m e. m a n a m e.</span><span class="sxs-lookup"><span data-stu-id="b48a6-118">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Containercmdletprovider.Copyitem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) and [System.Management.Automation.Provider.Containercmdletprovider.Copyitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters) methods.</span></span>

- <span data-ttu-id="b48a6-119">`Get-Item`: 이 cmdlet을 사용 하면 사용자가 데이터 저장소에서 데이터를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-119">`Get-Item`: This cmdlet allows the user to retrieve data from the data store.</span></span> <span data-ttu-id="b48a6-120">이 cmdlet을 지원 하려면 [Getitem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) 및 [system.web](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) . n a m a. i n g. i n g. i n g.</span><span class="sxs-lookup"><span data-stu-id="b48a6-120">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Itemcmdletprovider.Getitem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) and [System.Management.Automation.Provider.Itemcmdletprovider.Getitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) methods.</span></span>

- <span data-ttu-id="b48a6-121">`Get-ChildItem`: 이 cmdlet을 사용 하 여 사용자는 부모 항목의 자식 항목을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-121">`Get-ChildItem`: This cmdlet allows the user to retrieve the child items of the parent item.</span></span> <span data-ttu-id="b48a6-122">이 cmdlet을 지원 하려면 다음 메서드를 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-122">To support this cmdlet, overwrite the following methods:</span></span>

  - [<span data-ttu-id="b48a6-123">Containercmdletprovider입니다. Getchilditems \*</span><span class="sxs-lookup"><span data-stu-id="b48a6-123">System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)

  - [<span data-ttu-id="b48a6-124">Containercmdletprovider입니다. Getchilditemsdynamicparameters \*</span><span class="sxs-lookup"><span data-stu-id="b48a6-124">System.Management.Automation.Provider.Containercmdletprovider.Getchilditemsdynamicparameters\*</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters)

  - [<span data-ttu-id="b48a6-125">Containercmdletprovider입니다. Getchildnames \*</span><span class="sxs-lookup"><span data-stu-id="b48a6-125">System.Management.Automation.Provider.Containercmdletprovider.Getchildnames\*</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)

  - [<span data-ttu-id="b48a6-126">Containercmdletprovider입니다. Getchildnamesdynamicparameters \*</span><span class="sxs-lookup"><span data-stu-id="b48a6-126">System.Management.Automation.Provider.Containercmdletprovider.Getchildnamesdynamicparameters\*</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters)

- <span data-ttu-id="b48a6-127">`Invoke-Item`: 이 cmdlet을 사용 하면 사용자가 항목에 지정 된 기본 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-127">`Invoke-Item`: This cmdlet allows the user to perform the default action specified by the item.</span></span> <span data-ttu-id="b48a6-128">이 cmdlet을 지원 하려면 [Invokedefaultaction](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) 및 Invokedefaultaction 메서드를 덮어쓰십시오. n a m. i n [g](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) . m a.</span><span class="sxs-lookup"><span data-stu-id="b48a6-128">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultaction](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) and [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultaction](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) methods.</span></span>

- <span data-ttu-id="b48a6-129">`Move-Item`: 이 cmdlet을 사용 하면 사용자가 한 위치에서 다른 위치로 항목을 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-129">`Move-Item`: This cmdlet allows the user to move an item from one location to another location.</span></span> <span data-ttu-id="b48a6-130">이 cmdlet을 지원 하려면 [Moveitem](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) 및 system.webserver를 덮어씁니다. [Moveitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters)s 메서드를 (를) 덮어씁니다 .이 경우.</span><span class="sxs-lookup"><span data-stu-id="b48a6-130">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) and [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters)s methods.</span></span>

- <span data-ttu-id="b48a6-131">`New-ItemProperty`: 이 cmdlet을 사용 하면 사용자가 데이터 저장소에 새 항목을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-131">`New-ItemProperty`: This cmdlet allows the user to create a new item in the data store.</span></span>

- <span data-ttu-id="b48a6-132">`Remove-Item`: 이 cmdlet을 사용 하면 사용자가 데이터 저장소에서 항목을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-132">`Remove-Item`: This cmdlet allows the user to remove items from the data store.</span></span> <span data-ttu-id="b48a6-133">이 cmdlet을 지원 하려면 Containercmdletprovider 및 Containercmdletprovider를 덮어씁니다. [Removeitem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) 및 [. Removeitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters) 메서드를 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-133">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Containercmdletprovider.Removeitem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) and [System.Management.Automation.Provider.Containercmdletprovider.Removeitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters) methods.</span></span>

- <span data-ttu-id="b48a6-134">`Rename-Item`: 이 cmdlet을 사용 하면 사용자가 데이터 저장소에 있는 항목의 이름을 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-134">`Rename-Item`: This cmdlet allows the user to rename items in the data store.</span></span> <span data-ttu-id="b48a6-135">이 cmdlet을 지원 하려면 Renameitem 및 Containercmdletprovider 메서드를 덮어씁니다. [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) . [Renameitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters) 메서드를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-135">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Containercmdletprovider.Renameitem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) and [System.Management.Automation.Provider.Containercmdletprovider.Renameitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters) methods.</span></span>

- <span data-ttu-id="b48a6-136">`Set-Item`: 이 cmdlet을 사용 하면 사용자가 데이터 저장소에 있는 항목의 값을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-136">`Set-Item`: This cmdlet allows the user to update the values of items in the data store.</span></span> <span data-ttu-id="b48a6-137">이 cmdlet을 지원하려면 [System.Management.Automation.Provider.Itemcmdletprovider.Setitem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) 및 [System.Management.Automation.Provider.Itemcmdletprovider.Setitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters) 메서드를 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-137">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Itemcmdletprovider.Setitem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) and [System.Management.Automation.Provider.Itemcmdletprovider.Setitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters) methods.</span></span>

### <a name="item-content-cmdlets"></a><span data-ttu-id="b48a6-138">항목 콘텐츠 cmdlet</span><span class="sxs-lookup"><span data-stu-id="b48a6-138">Item content cmdlets</span></span>

- <span data-ttu-id="b48a6-139">`Add-Content`: 이 cmdlet을 사용 하면 사용자가 항목에 콘텐츠를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-139">`Add-Content`: This cmdlet allows the user to add content to an item.</span></span>

- <span data-ttu-id="b48a6-140">`Clear-Content`: 이 cmdlet을 사용 하면 사용자가 항목을 삭제 하지 않고 항목에서 콘텐츠를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-140">`Clear-Content`: This cmdlet allows the user to delete content from an item without deleting the item.</span></span> <span data-ttu-id="b48a6-141">이 cmdlet을 지원 하려면 Icontentcmdletprovider 및 Icontentcmdletprovider를 덮어씁니다. [Clearcontent](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) 및 [. Clearcontentdynamicparameters](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters) 메서드를 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-141">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) and [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontentdynamicparameters](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters) methods.</span></span>

- <span data-ttu-id="b48a6-142">`Get-Content`: 이 cmdlet을 사용 하면 사용자가 항목의 내용을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-142">`Get-Content`: This cmdlet allows the user to retrieve the content of an item.</span></span> <span data-ttu-id="b48a6-143">이 cmdlet을 지원 하려면 [Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) 을 덮어씁니다. [Icontentcmdletprovider 및. Getcontentreaderdynamicparameters](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) (영문)를 덮어씁니다. 메서드.</span><span class="sxs-lookup"><span data-stu-id="b48a6-143">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) and [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreaderdynamicparameters](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) methods.</span></span> <span data-ttu-id="b48a6-144">[Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) 메서드는 콘텐츠를 읽는 데 사용 되는 메서드를 정의 하는 [Icontentreader](/dotnet/api/System.Management.Automation.Provider.IContentReader) 인터페이스를 반환 합니다 .이 인터페이스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-144">The [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) method returns an [System.Management.Automation.Provider.Icontentreader](/dotnet/api/System.Management.Automation.Provider.IContentReader) interface that defines the methods used to read the content.</span></span>

- <span data-ttu-id="b48a6-145">`Set-Content`: 이 cmdlet을 사용 하면 사용자가 항목의 내용을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-145">`Set-Content`: This cmdlet allows the user to update the content of an item.</span></span> <span data-ttu-id="b48a6-146">이 cmdlet을 지원 하려면 [Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) 을 덮어씁니다. [Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) . n a m a. n a m a. 메서드.</span><span class="sxs-lookup"><span data-stu-id="b48a6-146">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) and [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriterdynamicparameters](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) methods.</span></span> <span data-ttu-id="b48a6-147">[Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) 메서드는 콘텐츠를 쓰는 데 사용 되는 메서드를 정의 하는 [Icontentwriter](/dotnet/api/System.Management.Automation.Provider.IContentWriter) 인터페이스를 반환 합니다 .이 인터페이스는 콘텐츠를 쓰는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-147">The [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) method returns an [System.Management.Automation.Provider.Icontentwriter](/dotnet/api/System.Management.Automation.Provider.IContentWriter) interface that defines the methods used to write the content.</span></span>

### <a name="item-property-cmdlets"></a><span data-ttu-id="b48a6-148">Item 속성 cmdlet</span><span class="sxs-lookup"><span data-stu-id="b48a6-148">Item property cmdlets</span></span>

- <span data-ttu-id="b48a6-149">`Clear-ItemProperty`: 이 cmdlet을 사용 하면 사용자가 속성의 값을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-149">`Clear-ItemProperty`: This cmdlet allows the user to delete the value of a property.</span></span> <span data-ttu-id="b48a6-150">이 cmdlet을 지원 하려면 System.object를 덮어씁니다. [Clearproperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) 및 system.object를 덮어씁니다 [. Clearpropertydynamicparameters를 덮어씁니다. clearpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) 메서드.</span><span class="sxs-lookup"><span data-stu-id="b48a6-150">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Ipropertycmdletprovider.Clearproperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) and [System.Management.Automation.Provider.Ipropertycmdletprovider.Clearpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) methods.</span></span>

- <span data-ttu-id="b48a6-151">`Copy-ItemProperty`: 이 cmdlet을 사용 하면 사용자가 한 위치에서 다른 위치로 속성 및 값을 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-151">`Copy-ItemProperty`: This cmdlet allows the user to copy a property and its value from one location to another.</span></span> <span data-ttu-id="b48a6-152">이 cmdlet을 지원 하려면 [Idynamicpropertycmdletprovider 속성](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyProperty) [을 덮어써야 합니다. Idynamicpropertycmdletprovider Propertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyPropertyDynamicParameters) 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-152">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Copyproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyProperty) and [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Copypropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyPropertyDynamicParameters) methods.</span></span>

- <span data-ttu-id="b48a6-153">`Get-ItemProperty`: 이 cmdlet은 항목의 속성을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-153">`Get-ItemProperty`: This cmdlet retrieves the properties of an item.</span></span> <span data-ttu-id="b48a6-154">이 cmdlet을 지원 하려면 [system.object](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) 를 덮어씁니다. x m p. i n g. i n g. [i n](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) d o d.</span><span class="sxs-lookup"><span data-stu-id="b48a6-154">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Ipropertycmdletprovider.Getproperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) and [System.Management.Automation.Provider.Ipropertycmdletprovider.Getpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) methods.</span></span>

- <span data-ttu-id="b48a6-155">`Move-ItemProperty`: 이 cmdlet을 통해 사용자는 속성 및 해당 값을 한 위치에서 다른 위치로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-155">`Move-ItemProperty`: This cmdlet allows the user to move a property and its value from one location to another.</span></span> <span data-ttu-id="b48a6-156">이 cmdlet을 지원 하려면 [Idynamicpropertycmdletprovider 속성](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MoveProperty) [을 덮어써야 합니다. Idynamicpropertycmdletprovider-Movepropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MovePropertyDynamicParameters) 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-156">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Moveproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MoveProperty) and [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Movepropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MovePropertyDynamicParameters) methods.</span></span>

- <span data-ttu-id="b48a6-157">`New-ItemProperty`: 이 cmdlet을 사용 하면 사용자가 새 속성을 만들고 해당 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-157">`New-ItemProperty`: This cmdlet allows the user to create a new property and set its value.</span></span> <span data-ttu-id="b48a6-158">이 cmdlet을 지원하려면 [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Newproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewProperty) 및 [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Newpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters) 메서드를 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-158">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Newproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewProperty) and [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Newpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters) methods.</span></span>

- <span data-ttu-id="b48a6-159">`Remove-ItemProperty`: 이 cmdlet을 통해 사용자는 속성과 해당 값을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-159">`Remove-ItemProperty`: This cmdlet allows the user to delete a property and its value.</span></span> <span data-ttu-id="b48a6-160">이 cmdlet을 지원 하려면 [Idynamicpropertycmdletprovider 속성](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemoveProperty) [을 덮어써야 합니다. Idynamicpropertycmdletprovider-Removepropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters) 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-160">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Removeproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemoveProperty) and [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Removepropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters) methods.</span></span>

- <span data-ttu-id="b48a6-161">`Rename-ItemProperty`: 이 cmdlet을 사용 하면 사용자가 속성의 이름을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-161">`Rename-ItemProperty`: This cmdlet allows the user to change the name of a property.</span></span> <span data-ttu-id="b48a6-162">이 cmdlet을 지원 하려면 Idynamicpropertycmdletprovider. [Renameproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenameProperty) [를 덮어씁니다. Idynamicpropertycmdletprovider. Renamepropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters) 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-162">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Renameproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenameProperty) and [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Renamepropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters) methods.</span></span>

- <span data-ttu-id="b48a6-163">`Set-ItemProperty`: 이 cmdlet을 사용 하면 사용자가 항목의 속성을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-163">`Set-ItemProperty`: This cmdlet allows the user to update the properties of an item.</span></span> <span data-ttu-id="b48a6-164">이 cmdlet을 지원 하려면 [system.object](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) 를 덮어씁니다. d a t a. d a t a. d a t a. d a [t.](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters)</span><span class="sxs-lookup"><span data-stu-id="b48a6-164">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Ipropertycmdletprovider.Setproperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) and [System.Management.Automation.Provider.Ipropertycmdletprovider.Setpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters) methods.</span></span>

### <a name="location-cmdlets"></a><span data-ttu-id="b48a6-165">위치 cmdlet</span><span class="sxs-lookup"><span data-stu-id="b48a6-165">Location cmdlets</span></span>

- <span data-ttu-id="b48a6-166">`Get-Location`: 현재 작업 위치에 대 한 정보를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-166">`Get-Location`: Retrieves information about the current working location.</span></span> <span data-ttu-id="b48a6-167">이 cmdlet을 지원 하기 위해 메서드를 덮어쓸 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-167">You do not need to overwrite any methods to support this cmdlet.</span></span>

- <span data-ttu-id="b48a6-168">`Pop-Location`: 이 cmdlet은 현재 위치를 가장 최근에 스택으로 푸시되는 위치로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-168">`Pop-Location`: This cmdlet changes the current location to the location most recently pushed onto the stack.</span></span> <span data-ttu-id="b48a6-169">이 cmdlet을 지원 하기 위해 메서드를 덮어쓸 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-169">You do not need to overwrite any methods to support this cmdlet.</span></span>

- <span data-ttu-id="b48a6-170">`Push-Location`: 이 cmdlet은 위치 목록 ("stack")의 맨 위에 현재 위치를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-170">`Push-Location`: This cmdlet adds the current location to the top of a list of locations (a "stack").</span></span> <span data-ttu-id="b48a6-171">이 cmdlet을 지원 하기 위해 메서드를 덮어쓸 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-171">You do not need to overwrite any methods to support this cmdlet.</span></span>

- <span data-ttu-id="b48a6-172">`Set-Location`: 이 cmdlet은 현재 작업 위치를 지정 된 위치로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-172">`Set-Location`: This cmdlet sets the current working location to a specified location.</span></span> <span data-ttu-id="b48a6-173">이 cmdlet을 지원 하기 위해 메서드를 덮어쓸 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-173">You do not need to overwrite any methods to support this cmdlet.</span></span>

### <a name="path-cmdlets"></a><span data-ttu-id="b48a6-174">경로 cmdlet</span><span class="sxs-lookup"><span data-stu-id="b48a6-174">Path cmdlets</span></span>

- <span data-ttu-id="b48a6-175">`Join-Path`: 이 cmdlet을 통해 사용자는 부모 및 자식 경로 세그먼트를 결합 하 여 공급자 내부 경로를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-175">`Join-Path`: This cmdlet allows the user to combine a parent and child path segment to create a provider-internal path.</span></span> <span data-ttu-id="b48a6-176">이 cmdlet을 지원 하려면 [system.web](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) . n a m a.</span><span class="sxs-lookup"><span data-stu-id="b48a6-176">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) method.</span></span>

- <span data-ttu-id="b48a6-177">`Convert-Path`: 이 cmdlet은 Windows PowerShell 경로에서 Windows PowerShell 공급자 경로로 경로를 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-177">`Convert-Path`: This cmdlet converts a path from a Windows PowerShell path to a Windows PowerShell provider path.</span></span>

- <span data-ttu-id="b48a6-178">`Split-Path`: 경로의 지정된 일부를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-178">`Split-Path`: Returns the specified part of a path.</span></span>

- <span data-ttu-id="b48a6-179">`Resolve-Path`: 경로에서 와일드카드 문자를 확인하고 경로 내용을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-179">`Resolve-Path`: Resolves the wildcard characters in a path, and displays the path contents.</span></span>

- <span data-ttu-id="b48a6-180">`Test-Path`: 이 cmdlet은 경로의 모든 요소가 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-180">`Test-Path`: This cmdlet determines whether all elements of a path exist.</span></span> <span data-ttu-id="b48a6-181">이 cmdlet을 지원 하려면 [Itemexistsdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExistsDynamicParameters) 메서드를 덮어쓰십시오. i n g. i [n g.](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) m a n g.</span><span class="sxs-lookup"><span data-stu-id="b48a6-181">To support this cmdlet, overwrite the [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) and [System.Management.Automation.Provider.Itemcmdletprovider.Itemexistsdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExistsDynamicParameters) methods.</span></span>

### <a name="psprovider-cmdlets"></a><span data-ttu-id="b48a6-182">PSProvider cmdlet</span><span class="sxs-lookup"><span data-stu-id="b48a6-182">PSProvider cmdlets</span></span>

- <span data-ttu-id="b48a6-183">`Get-PSProvider`: 이 cmdlet은 세션에서 사용할 수 있는 공급자에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-183">`Get-PSProvider`: This cmdlet returns information about the providers available in the session.</span></span> <span data-ttu-id="b48a6-184">이 cmdlet을 지원 하기 위해 메서드를 덮어쓸 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b48a6-184">You do not need to overwrite any methods to support this cmdlet.</span></span>