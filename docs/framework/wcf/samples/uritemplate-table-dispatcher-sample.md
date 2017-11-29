---
title: "UriTemplate 表调度程序示例"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b32975d-ba90-4c5c-83bc-2fbb48f11c0c
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3574183f0900c853bd3ff541aabc8fc6b7fcd157
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="uritemplate-table-dispatcher-sample"></a><span data-ttu-id="5e4fc-102">UriTemplate 表调度程序示例</span><span class="sxs-lookup"><span data-stu-id="5e4fc-102">UriTemplate Table Dispatcher Sample</span></span>
<span data-ttu-id="5e4fc-103"><xref:System.UriTemplateTable> 类提供了一个类似字典的关联表结构，该结构可用来处理一组 <xref:System.UriTemplate> 实例。</span><span class="sxs-lookup"><span data-stu-id="5e4fc-103">The <xref:System.UriTemplateTable> class provides a dictionary-like associative table structure for working with a set of <xref:System.UriTemplate> instances.</span></span> <span data-ttu-id="5e4fc-104">此示例演示使用 `UriTemplateTable` 生成的基本调度引擎，这是 `UriTemplateTable` 类的常见使用方案。</span><span class="sxs-lookup"><span data-stu-id="5e4fc-104">This sample demonstrates a basic dispatching engine built using `UriTemplateTable`, a common usage scenario for the `UriTemplateTable` class.</span></span>  
  
 <span data-ttu-id="5e4fc-105">此示例演示 `UriTemplateTable` 类的以下关键概念：</span><span class="sxs-lookup"><span data-stu-id="5e4fc-105">This sample demonstrates the following key concepts for the `UriTemplateTable` class:</span></span>  
  
-   <span data-ttu-id="5e4fc-106">将委托与 `UriTemplates` 中的 `UriTemplateTable` 关联。</span><span class="sxs-lookup"><span data-stu-id="5e4fc-106">Associating delegates with `UriTemplates` in a `UriTemplateTable`.</span></span>  
  
-   <span data-ttu-id="5e4fc-107">使用 <xref:System.UriTemplateTable.MatchSingle%2A> 获取特定 URI 的正确处理程序委托。</span><span class="sxs-lookup"><span data-stu-id="5e4fc-107">Using <xref:System.UriTemplateTable.MatchSingle%2A> to obtain the correct handler delegate for a particular URI.</span></span>  
  
-   <span data-ttu-id="5e4fc-108">调用处理程序委托以处理请求。</span><span class="sxs-lookup"><span data-stu-id="5e4fc-108">Invoking the handler delegate to process the request.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="5e4fc-109">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="5e4fc-109">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="5e4fc-110">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="5e4fc-110">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="5e4fc-111">若要在单或跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="5e4fc-111">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5e4fc-112">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="5e4fc-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5e4fc-113">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="5e4fc-113">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5e4fc-114">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="5e4fc-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5e4fc-115">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="5e4fc-115">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateDispatcher`  
  
## <a name="see-also"></a><span data-ttu-id="5e4fc-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e4fc-116">See Also</span></span>  
 [<span data-ttu-id="5e4fc-117">UriTemplate 表</span><span class="sxs-lookup"><span data-stu-id="5e4fc-117">UriTemplate Table</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)  
 [<span data-ttu-id="5e4fc-118">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="5e4fc-118">UriTemplate</span></span>](../../../../docs/framework/wcf/samples/uritemplate-sample.md)
