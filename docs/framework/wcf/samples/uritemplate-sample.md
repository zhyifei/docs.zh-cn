---
title: "UriTemplate 示例"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0aaf91d0-ce18-468d-8006-bc9bc2e48231
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 729a48fe0ea34bf1630824d941341fff82ade1ef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="uritemplate-sample"></a><span data-ttu-id="c9932-102">UriTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="c9932-102">UriTemplate Sample</span></span>
<span data-ttu-id="c9932-103"><xref:System.UriTemplate> 类提供了用于处理共享公共结构的 URI 组的方法。</span><span class="sxs-lookup"><span data-stu-id="c9932-103">The <xref:System.UriTemplate> class provides methods for working with sets of URIs that share a common structure.</span></span> <span data-ttu-id="c9932-104">此示例演示与 `UriTemplate` 相关的以下关键概念：</span><span class="sxs-lookup"><span data-stu-id="c9932-104">This sample demonstrates the following key concepts relating to `UriTemplate`:</span></span>  
  
-   <span data-ttu-id="c9932-105">创建模板的语法。</span><span class="sxs-lookup"><span data-stu-id="c9932-105">Syntax for creating templates.</span></span>  
  
-   <span data-ttu-id="c9932-106">使用 `UriTemplate` 和 <xref:System.UriTemplate.BindByName%2A> 实例化 <xref:System.UriTemplate.BindByPosition%2A> 中的 URI。</span><span class="sxs-lookup"><span data-stu-id="c9932-106">Instantiating URIs from a `UriTemplate` using <xref:System.UriTemplate.BindByName%2A> and <xref:System.UriTemplate.BindByPosition%2A>.</span></span>  
  
-   <span data-ttu-id="c9932-107">作为 <xref:System.UriTemplateTable.Match%2A> 和 `BindByName` 的反向操作的 `BindByPosition`。</span><span class="sxs-lookup"><span data-stu-id="c9932-107"><xref:System.UriTemplateTable.Match%2A>, which is the inverse operation of `BindByName` and `BindByPosition`.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c9932-108">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="c9932-108">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="c9932-109">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="c9932-109">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="c9932-110">若要在单或跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="c9932-110">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c9932-111">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="c9932-111">The samples may already be installed on your computer.</span></span> <span data-ttu-id="c9932-112">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="c9932-112">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c9932-113">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="c9932-113">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c9932-114">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="c9932-114">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplate`  
  
## <a name="see-also"></a><span data-ttu-id="c9932-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9932-115">See Also</span></span>  
 [<span data-ttu-id="c9932-116">UriTemplate 表</span><span class="sxs-lookup"><span data-stu-id="c9932-116">UriTemplate Table</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)  
 [<span data-ttu-id="c9932-117">UriTemplate 表调度程序</span><span class="sxs-lookup"><span data-stu-id="c9932-117">UriTemplate Table Dispatcher</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)
