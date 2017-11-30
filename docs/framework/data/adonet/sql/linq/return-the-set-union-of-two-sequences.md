---
title: "返回两个序列的并集"
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
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 865aa82ebc119a3952124a93f9042c2732e3ab48
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="return-the-set-union-of-two-sequences"></a>返回两个序列的并集
使用 <xref:System.Linq.Queryable.Union%2A> 运算符可返回两个序列的并集。  
  
## <a name="example"></a>示例  
 此示例使用 <xref:System.Linq.Queryable.Union%2A> 返回有 `Customers` 或 `Employees` 的所有国家/地区的序列。  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 在 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中，<xref:System.Linq.Queryable.Union%2A> 运算符是为多重集定义的，定义为多重集的无序串联（实际上是 SQL 中的 `UNION ALL` 子句的执行结果）。  
  
## <a name="see-also"></a>另请参阅  
 [查询示例](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [标准查询运算符转换](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
