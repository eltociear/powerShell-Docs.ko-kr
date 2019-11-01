---
title: 사용자 지정 컨트롤 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c3baa406-cd33-4420-be5a-07ef09d93480
caps.latest.revision: 8
ms.openlocfilehash: 3504ab1d974c55e9279172d0e851961474ccb926
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363382"
---
# <a name="creating-custom-controls"></a><span data-ttu-id="2bc67-102">사용자 지정 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="2bc67-102">Creating Custom Controls</span></span>

<span data-ttu-id="2bc67-103">사용자 지정 컨트롤은 서식 파일의 가장 유연한 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2bc67-103">Custom controls are the most flexible components of a formatting file.</span></span> <span data-ttu-id="2bc67-104">데이터 테이블과 같은 데이터의 공식 구조를 정의 하는 테이블, 목록 및 넓은 뷰와 달리 사용자 지정 컨트롤을 사용 하면 개별 데이터 조각이 표시 되는 방식을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bc67-104">Unlike table, list, and wide views that define a formal structure of data, such as a table of data, custom controls allow you to define how an individual piece of data is displayed.</span></span> <span data-ttu-id="2bc67-105">서식 파일의 모든 뷰에 사용할 수 있는 사용자 지정 컨트롤의 공통 집합을 정의 하거나, 특정 뷰에서 사용할 수 있는 사용자 지정 컨트롤을 정의 하거나, 개체 그룹에 사용할 수 있는 컨트롤 집합을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bc67-105">You can define a common set of custom controls that are available to all the views of the formatting file, you can define custom controls that are available to a specific view, or you can define a set of controls that are available to a group of objects.</span></span>

## <a name="custom-control-example"></a><span data-ttu-id="2bc67-106">사용자 지정 컨트롤 예제</span><span class="sxs-lookup"><span data-stu-id="2bc67-106">Custom Control Example</span></span>

<span data-ttu-id="2bc67-107">다음 예제에서는 types.ps1xml 파일에 정의 된 사용자 지정 컨트롤을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2bc67-107">The following example shows a custom control that is defined in the Certificates.Format.ps1xml file.</span></span> <span data-ttu-id="2bc67-108">이 사용자 지정 컨트롤을 사용 하 여 테이블 뷰에 표시 되는 [system.web. Signature](/dotnet/api/System.Management.Automation.Signature) 개체를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bc67-108">This custom control is used to separate the [System.Management.Automation.Signature](/dotnet/api/System.Management.Automation.Signature) objects displayed in a table view.</span></span>

```xml
<Controls>
  <Control>
    <Name>SignatureTypes-GroupingFormat</Name>
    <CustomControl>
      <CustomEntries>
        <CustomEntry>
          <CustomItem>
            <Frame>
              <LeftIndent>4</LeftIndent>
              <CustomItem>
                <Text AssemblyName="System.Management.Automation" BaseName="FileSystemProviderStrings"
                  ResourceId="DirectoryDisplayGrouping"/>
                <ExpressionBinding>
                  <ScriptBlock>split-path $_.Path</ScriptBlock>
                </ExpressionBinding>
                <NewLine/>
              </CustomItem>
            </Frame>
          </CustomItem>
        </CustomEntry>
      </CustomEntries>
    </CustomControl>
  </Control>
</Controls>

```

## <a name="see-also"></a><span data-ttu-id="2bc67-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2bc67-109">See Also</span></span>

[<span data-ttu-id="2bc67-110">PowerShell 서식 파일 작성</span><span class="sxs-lookup"><span data-stu-id="2bc67-110">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)