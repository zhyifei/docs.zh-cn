---
title: "如何：查询信息"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 55ef74cecf5a3669662e5fe189aea88b7d912344
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-query-for-information"></a>如何：查询信息
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中的查询与 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 中的查询使用相同的语法。 唯一的区别是中引用的对象[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]查询映射到数据库中的元素。 有关详细信息，请参阅 [LINQ 查询简介 (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)。  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 将您编写的查询转换成等效的 SQL 查询，然后将它们发送至服务器进行处理。  
  
 在 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 应用程序中，可能需要特别注意 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 查询的某些功能。 有关详细信息，请参阅[查询概念](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)。  
  
## <a name="example"></a>示例  
 下面的查询请求来自伦敦的客户的列表。 在此示例中，`Customers` 是 Northwind 示例数据库中的表。  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>请参阅  
 [创建对象模型](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 [下载示例数据库](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [查询数据库](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
