---
title: 批处理操作（WCF 数据服务）
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
ms.assetid: 962a49d1-cc11-4b96-bc7d-071dd6607d6c
ms.openlocfilehash: 48c0a5f1573f64396971e1265dbf467300a98406
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569347"
---
# <a name="batching-operations-wcf-data-services"></a>批处理操作（WCF 数据服务）
Open Data Protocol （OData）支持批处理发送到基于 OData 的服务的请求。 有关详细信息，请参阅[OData：批处理](https://go.microsoft.com/fwlink/?LinkId=186075)。 在 WCF 数据服务中，使用 <xref:System.Data.Services.Client.DataServiceContext>的每个操作（如执行查询或保存更改）都会导致向数据服务发送一个单独的请求。 为保持操作集的合理范围，可以显式定义操作批。 这可确保批处理中的所有操作都在单个 HTTP 请求中发送到数据服务，使服务器能够以原子方式处理操作，并减少与数据服务的往返次数。  
  
## <a name="batching-query-operations"></a>查询操作批处理  
 若要在一个批中执行多个查询，必须在该批中将每个查询创建为 <xref:System.Data.Services.Client.DataServiceRequest%601> 类的一个单独实例。 以这种方式创建查询请求时，查询本身将定义为 URI，并遵循资源寻址规则。 有关详细信息，请参阅[访问数据服务资源](accessing-data-service-resources-wcf-data-services.md)。 在调用包含查询请求对象的 <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A> 方法时，会将批处理查询请求发送到数据服务。 此方法返回一个 <xref:System.Data.Services.Client.DataServiceResponse> 对象，它是代表对批中各个查询的响应的 <xref:System.Data.Services.Client.QueryOperationResponse%601> 对象的集合，其中每个对象包含查询返回的对象集合或错误信息。 当批中任何一个查询操作失败时，将针对失败的操作在 <xref:System.Data.Services.Client.QueryOperationResponse%601> 对象中返回错误信息，并继续执行其余操作。 有关详细信息，请参阅[如何：在批处理中执行查询](how-to-execute-queries-in-a-batch-wcf-data-services.md)。  
  
 批处理查询也可以采用异步方式执行。 有关详细信息，请参阅[异步操作](asynchronous-operations-wcf-data-services.md)。  
  
## <a name="batching-the-savechanges-operation"></a>SaveChanges 操作批处理  
 调用 <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> 方法时，会将上下文跟踪的所有更改转换为基于 REST 的操作，这些操作将作为请求发送到 OData 服务。 默认情况下，不会在同一请求消息中发送这些更改。 若要要求在单个请求中发送所有更改，必须调用 <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%28System.Data.Services.Client.SaveChangesOptions%29> 方法，并在提供给方法的 <xref:System.Data.Services.Client.SaveChangesOptions> 枚举中包含值 <xref:System.Data.Services.Client.SaveChangesOptions.Batch>。  
  
 此外，还可以采用异步方式保存批处理更改。 有关详细信息，请参阅[异步操作](asynchronous-operations-wcf-data-services.md)。  
  
## <a name="see-also"></a>另请参阅

- [WCF Data Services 客户端库](wcf-data-services-client-library.md)
