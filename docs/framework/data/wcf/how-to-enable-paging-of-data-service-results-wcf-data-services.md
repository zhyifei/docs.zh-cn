---
title: 如何：启用分页的数据服务结果 （WCF 数据服务）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- paging output [WCF Data Services]
ms.assetid: 9a316cbd-9612-4482-a541-a10bc78b2635
ms.openlocfilehash: be5bd41494c27724a360b785b8706b618447e7de
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523450"
---
# <a name="how-to-enable-paging-of-data-service-results-wcf-data-services"></a><span data-ttu-id="916fe-102">如何：启用分页的数据服务结果 （WCF 数据服务）</span><span class="sxs-lookup"><span data-stu-id="916fe-102">How to: Enable Paging of Data Service Results (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] <span data-ttu-id="916fe-103">使您能够限制由数据服务查询返回的实体数。</span><span class="sxs-lookup"><span data-stu-id="916fe-103">enables you to limit the number of entities returned by a data service query.</span></span> <span data-ttu-id="916fe-104">页限制在初始化服务时调用的方法中定义，并可为每个实体集单独设置页限制。</span><span class="sxs-lookup"><span data-stu-id="916fe-104">Page limits are defined in the method that is called when the service is initialized and can be set separately for each entity set.</span></span>  
  
 <span data-ttu-id="916fe-105">启用分页后，源中的最后一项包含指向下一页数据的链接。</span><span class="sxs-lookup"><span data-stu-id="916fe-105">When paging is enabled, the final entry in the feed contains a link to the next page of data.</span></span> <span data-ttu-id="916fe-106">有关详细信息，请参阅[数据服务配置](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="916fe-106">For more information, see [Configuring the Data Service](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="916fe-107">本主题介绍如何修改数据服务以启用返回的 `Customers` 和 `Orders` 实体集的分页。</span><span class="sxs-lookup"><span data-stu-id="916fe-107">This topic shows how to modify a data service to enable paging of returned `Customers` and `Orders` entity sets.</span></span> <span data-ttu-id="916fe-108">本主题中的示例使用 Northwind 示例数据服务。</span><span class="sxs-lookup"><span data-stu-id="916fe-108">The example in this topic uses the Northwind sample data service.</span></span> <span data-ttu-id="916fe-109">此服务创建完成后[WCF Data Services 快速入门](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="916fe-109">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>  
  
### <a name="how-to-enable-paging-of-returned-customers-and-orders-entity-sets"></a><span data-ttu-id="916fe-110">如何启用返回的 Customers 和 Orders 实体集的分页</span><span class="sxs-lookup"><span data-stu-id="916fe-110">How to enable paging of returned Customers and Orders entity sets</span></span>  
  
-   <span data-ttu-id="916fe-111">在数据服务的代码中，用下列代码替换 `InitializeService` 函数中的占位符代码：</span><span class="sxs-lookup"><span data-stu-id="916fe-111">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind.svc.cs#dataserviceconfigpaging)]
     [!code-vb[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind.svc.vb#dataserviceconfigpaging)]  
  
## <a name="see-also"></a><span data-ttu-id="916fe-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="916fe-112">See also</span></span>
- [<span data-ttu-id="916fe-113">加载延迟的内容</span><span class="sxs-lookup"><span data-stu-id="916fe-113">Loading Deferred Content</span></span>](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)
- [<span data-ttu-id="916fe-114">如何：加载分页结果</span><span class="sxs-lookup"><span data-stu-id="916fe-114">How to: Load Paged Results</span></span>](../../../../docs/framework/data/wcf/how-to-load-paged-results-wcf-data-services.md)
