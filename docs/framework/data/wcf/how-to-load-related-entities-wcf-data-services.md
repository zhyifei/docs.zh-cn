---
title: 如何：加载相关实体（WCF 数据服务）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, deferred content
- WCF Data Services, loading data
ms.assetid: 6f143d30-d997-4e6b-bcf0-d5c394ecb108
ms.openlocfilehash: f7aa13ac217d86be23d0957ddb6c069831cacd2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-load-related-entities-wcf-data-services"></a>如何：加载相关实体（WCF 数据服务）
如果需要在 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 中加载关联实体，可以使用 <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A> 类的 <xref:System.Data.Services.Client.DataServiceContext> 方法。 你还可以使用<xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A>方法<xref:System.Data.Services.Client.DataServiceQuery%601>需要，在相同的查询响应中积极加载相关的实体。  
  
 本主题中的示例使用罗斯文示例数据服务和自动生成的客户端数据服务类。 在完成时创建此服务和客户端数据类[WCF 数据服务快速入门](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)。  
  
## <a name="example"></a>示例  
 下面的示例演示如何显式加载与每个返回的 `Customer` 实例相关的 `Orders`。  
  
 [!code-csharp[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#loadrelatedordercustomer)]
 [!code-vb[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#loadrelatedordercustomer)]  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用 <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> 方法返回属于由查询返回的 `Order Details` 的 `Orders`。  
  
 [!code-csharp[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#expandorderdetails)]
 [!code-vb[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#expandorderdetails)]  
  
## <a name="see-also"></a>请参阅  
 [查询数据服务](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)
