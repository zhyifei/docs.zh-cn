---
title: 如何：启用数据服务结果分页（WCF 数据服务）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- paging output [WCF Data Services]
ms.assetid: 9a316cbd-9612-4482-a541-a10bc78b2635
ms.openlocfilehash: 6b7cea2475a5c11091a04ef3044bbc958e55fc5d
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569096"
---
# <a name="how-to-enable-paging-of-data-service-results-wcf-data-services"></a>如何：启用数据服务结果分页（WCF 数据服务）
WCF 数据服务使你能够限制数据服务查询返回的实体数。 页限制在初始化服务时调用的方法中定义，并可为每个实体集单独设置页限制。  
  
 启用分页后，源中的最后一项包含指向下一页数据的链接。 有关详细信息，请参阅[配置数据服务](configuring-the-data-service-wcf-data-services.md)。  
  
 本主题介绍如何修改数据服务以启用返回的 `Customers` 和 `Orders` 实体集的分页。 本主题中的示例使用 Northwind 示例数据服务。 此服务是在完成[WCF 数据服务快速入门](quickstart-wcf-data-services.md)时创建的。  
  
### <a name="how-to-enable-paging-of-returned-customers-and-orders-entity-sets"></a>如何启用返回的 Customers 和 Orders 实体集的分页  
  
- 在数据服务的代码中，用下列代码替换 `InitializeService` 函数中的占位符代码：  
  
     [!code-csharp[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind.svc.cs#dataserviceconfigpaging)]
     [!code-vb[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind.svc.vb#dataserviceconfigpaging)]  
  
## <a name="see-also"></a>另请参阅

- [加载延迟的内容](loading-deferred-content-wcf-data-services.md)
- [如何：加载分页结果](how-to-load-paged-results-wcf-data-services.md)
