---
title: "如何：执行异步数据服务查询（WCF 数据服务）"
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
helpviewer_keywords:
- WCF Data Services, asynchronous operations
- asynchronous operations [WCF Data Services]
ms.assetid: 902a2dc1-d0e9-4b00-90a8-becc4cb1f6a7
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 86c38049f21ff6e9e02e1e715e6517c2947394e1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-execute-asynchronous-data-service-queries-wcf-data-services"></a>如何：执行异步数据服务查询（WCF 数据服务）
通过使用 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 客户端库，可以采用异步方式执行客户端-服务器操作，如执行查询和保存更改。 有关详细信息，请参阅[异步操作](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md)。  
  
> [!NOTE]
>  对于必须在特定线程中调用回调的应用程序，必须显式封送 <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> 方法的执行。 有关详细信息，请参阅[异步操作](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md)。  
  
 本主题中的示例使用罗斯文示例数据服务和自动生成的客户端数据服务类。 在完成时创建此服务和客户端数据类[WCF 数据服务快速入门](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)。  
  
## <a name="example"></a>示例  
 下面的示例显示如何通过调用 <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> 方法以启动查询来执行异步查询。 内联委托调用 <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> 方法以显示查询结果。  
  
 [!code-csharp[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#executequeryasync)]
 [!code-vb[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#executequeryasync)]  
  
## <a name="see-also"></a>另请参阅  
 [WCF Data Services 客户端库](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
