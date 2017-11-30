---
title: "将某一类型转换为泛型 IEnumerable"
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
ms.assetid: 64774fb5-7447-4296-ad3b-8a94346f99a1
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f2e91a5fe4b27891b1750b0d74a8e9b01ad68449
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="convert-a-type-to-a-generic-ienumerable"></a>将某一类型转换为泛型 IEnumerable
使用 <xref:System.Linq.Enumerable.AsEnumerable%2A> 可返回类型化为泛型 `IEnumerable` 的参数。  
  
## <a name="example"></a>示例  
 在此示例中，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]（使用默认泛型 `Query`）会尝试将查询转换为 SQL 并在服务器上执行。 但 `where` 子句引用用户定义的客户端方法 (`isValidProduct`)，此方法无法转换为 SQL。  
  
 解决方法是指定 <xref:System.Collections.Generic.IEnumerable%601> 的客户端泛型 `where` 实现以替换泛型 <xref:System.Linq.IQueryable%601>。 可通过调用 <xref:System.Linq.Enumerable.AsEnumerable%2A> 运算符来执行此操作。  
  
 [!code-csharp[DLinqQueryExamples#46](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#46)]
 [!code-vb[DLinqQueryExamples#46](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#46)]  
  
## <a name="see-also"></a>另请参阅  
 [查询示例](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
