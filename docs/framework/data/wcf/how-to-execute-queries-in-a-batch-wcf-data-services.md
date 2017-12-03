---
title: "如何：在一个批处理作业中执行查询（WCF 数据服务）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: WCF Data Services, batch requests
ms.assetid: 3b4db7df-bd33-43a1-8ea4-63a18e131f97
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 384274b127e04004117cbb2f6d5f7764c3212d0b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-execute-queries-in-a-batch-wcf-data-services"></a>如何：在一个批处理作业中执行查询（WCF 数据服务）
通过使用[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]客户端库，你可以在单个批处理中执行针对数据服务的多个查询。 有关详细信息，请参阅[批处理操作](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md)。  
  
 本主题中的示例使用罗斯文示例数据服务和自动生成的客户端数据服务类。 在完成时创建此服务和客户端数据类[WCF 数据服务快速入门](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)。  
  
## <a name="example"></a>示例  
 下面的示例演示如何调用 <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A> 方法来执行一个 <xref:System.Data.Services.Client.DataServiceRequest%601> 对象数组，该数组包含从 Northwind 数据服务同时返回 `Customers` 和 `Products` 对象的查询。 此示例将枚举返回的 <xref:System.Data.Services.Client.QueryOperationResponse%601> 中的 <xref:System.Data.Services.Client.DataServiceResponse> 对象的集合，并且还会枚举每个 <xref:System.Data.Services.Client.QueryOperationResponse%601> 中包含的对象的集合。  
  
 [!code-csharp[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#batchquery)]
 [!code-vb[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#batchquery)]  
  
## <a name="see-also"></a>另请参阅  
 [WCF Data Services 客户端库](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
