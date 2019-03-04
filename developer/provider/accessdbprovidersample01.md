---
title: AccessDBProviderSample01 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 853b7e5d-76c1-490e-8269-0ef31ba2ff13
caps.latest.revision: 10
ms.openlocfilehash: dc1ae92af8a57d6197b595db8e098256ac444b78
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854159"
---
# <a name="accessdbprovidersample01"></a><span data-ttu-id="086c9-102">AccessDBProviderSample01</span><span class="sxs-lookup"><span data-stu-id="086c9-102">AccessDBProviderSample01</span></span>

<span data-ttu-id="086c9-103">이 샘플에서 직접 파생 되는 공급자 클래스를 선언 하는 방법을 보여 줍니다 합니다 [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="086c9-103">This sample shows how to declare a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span> <span data-ttu-id="086c9-104">여기서는 참조용으로만 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="086c9-104">It is included here only for completeness.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="086c9-105">시연</span><span class="sxs-lookup"><span data-stu-id="086c9-105">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="086c9-106">공급자 클래스는 대부분 다음 클래스 중 하나에서 파생 되며 다른 공급자 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="086c9-106">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> -   <span data-ttu-id="086c9-107">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span><span class="sxs-lookup"><span data-stu-id="086c9-107">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="086c9-108">참조 [AccessDBProviderSample03](./accessdbprovidersample03.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="086c9-108">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> -   <span data-ttu-id="086c9-109">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span><span class="sxs-lookup"><span data-stu-id="086c9-109">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="086c9-110">참조 [AccessDBProviderSample04](./accessdbprovidersample04.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="086c9-110">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> -   <span data-ttu-id="086c9-111">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span><span class="sxs-lookup"><span data-stu-id="086c9-111">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span> <span data-ttu-id="086c9-112">참조 [AccessDBProviderSample05](./accessdbprovidersample05.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="086c9-112">See [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>
>
> <span data-ttu-id="086c9-113">자세한 내용은 공급자 기능에 따라에서 파생 되는 공급자 클래스를 선택 하는 방법에 대 한 [Your Windows PowerShell 공급자 디자인](./provider-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="086c9-113">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="086c9-114">이 샘플에는 다음 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="086c9-114">This sample demonstrates the following:</span></span>

- <span data-ttu-id="086c9-115">선언 된 `CmdletProvider` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="086c9-115">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="086c9-116">직접 파생 되는 공급자 클래스를 정의 합니다 [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="086c9-116">Defining a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span>

## <a name="example"></a><span data-ttu-id="086c9-117">예제</span><span class="sxs-lookup"><span data-stu-id="086c9-117">Example</span></span>

<span data-ttu-id="086c9-118">이 샘플에는 공급자 클래스를 정의 하는 방법 및 선언 하는 방법을 보여 줍니다는 `CmdletProvider` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="086c9-118">This sample shows how to define a provider class and how to declare the `CmdletProvider` attribute.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Providers
{
  using System.Management.Automation;
  using System.Management.Automation.Provider;

  /// <summary>
  /// This sample shows how to declare a provider class and how to
  /// declare the CmdletProvider attribute.
  /// </summary>
  [CmdletProvider("AccessDB", ProviderCapabilities.None)]
  public class AccessDBProvider : CmdletProvider
  {
    // Add provider logic here.
  }
}
```

## <a name="see-also"></a><span data-ttu-id="086c9-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="086c9-119">See Also</span></span>

[<span data-ttu-id="086c9-120">System.Management.Automation.Provider.Itemcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="086c9-120">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="086c9-121">System.Management.Automation.Provider.Containercmdletprovider</span><span class="sxs-lookup"><span data-stu-id="086c9-121">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="086c9-122">System.Management.Automation.Provider.Navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="086c9-122">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="086c9-123">Windows PowerShell 공급자를 디자인합니다.</span><span class="sxs-lookup"><span data-stu-id="086c9-123">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)