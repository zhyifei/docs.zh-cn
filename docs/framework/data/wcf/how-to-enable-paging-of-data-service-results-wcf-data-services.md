---
title: "如何：启用数据服务结果分页（WCF 数据服务）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- paging output [WCF Data Services]
ms.assetid: 9a316cbd-9612-4482-a541-a10bc78b2635
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b03dd234681d031361696108702a7bbb558065ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-paging-of-data-service-results-wcf-data-services"></a><span data-ttu-id="f711b-102">如何：启用数据服务结果分页（WCF 数据服务）</span><span class="sxs-lookup"><span data-stu-id="f711b-102">How to: Enable Paging of Data Service Results (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="f711b-103"> 使您能够限制由数据服务查询返回的实体数。</span><span class="sxs-lookup"><span data-stu-id="f711b-103"> enables you to limit the number of entities returned by a data service query.</span></span> <span data-ttu-id="f711b-104">页限制在初始化服务时调用的方法中定义，并可为每个实体集单独设置页限制。</span><span class="sxs-lookup"><span data-stu-id="f711b-104">Page limits are defined in the method that is called when the service is initialized and can be set separately for each entity set.</span></span>  
  
 <span data-ttu-id="f711b-105">启用分页后，源中的最后一项包含指向下一页数据的链接。</span><span class="sxs-lookup"><span data-stu-id="f711b-105">When paging is enabled, the final entry in the feed contains a link to the next page of data.</span></span> <span data-ttu-id="f711b-106">有关详细信息，请参阅[配置数据服务](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="f711b-106">For more information, see [Configuring the Data Service](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="f711b-107">本主题介绍如何修改数据服务以启用返回的 `Customers` 和 `Orders` 实体集的分页。</span><span class="sxs-lookup"><span data-stu-id="f711b-107">This topic shows how to modify a data service to enable paging of returned `Customers` and `Orders` entity sets.</span></span> <span data-ttu-id="f711b-108">本主题中的示例使用 Northwind 示例数据服务。</span><span class="sxs-lookup"><span data-stu-id="f711b-108">The example in this topic uses the Northwind sample data service.</span></span> <span data-ttu-id="f711b-109">在完成时创建此服务[WCF 数据服务快速入门](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="f711b-109">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>  
  
### <a name="how-to-enable-paging-of-returned-customers-and-orders-entity-sets"></a><span data-ttu-id="f711b-110">如何启用返回的 Customers 和 Orders 实体集的分页</span><span class="sxs-lookup"><span data-stu-id="f711b-110">How to enable paging of returned Customers and Orders entity sets</span></span>  
  
-   <span data-ttu-id="f711b-111">在数据服务的代码中，用下列代码替换 `InitializeService` 函数中的占位符代码：</span><span class="sxs-lookup"><span data-stu-id="f711b-111">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind.svc.cs#dataserviceconfigpaging)]
     [!code-vb[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind.svc.vb#dataserviceconfigpaging)]  
  
## <a name="see-also"></a><span data-ttu-id="f711b-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="f711b-112">See Also</span></span>  
 [<span data-ttu-id="f711b-113">加载延迟的内容</span><span class="sxs-lookup"><span data-stu-id="f711b-113">Loading Deferred Content</span></span>](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)  
 [<span data-ttu-id="f711b-114">如何：加载分页结果</span><span class="sxs-lookup"><span data-stu-id="f711b-114">How to: Load Paged Results</span></span>](../../../../docs/framework/data/wcf/how-to-load-paged-results-wcf-data-services.md)
