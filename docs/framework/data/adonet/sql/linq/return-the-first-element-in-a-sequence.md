---
title: "返回序列中的第一个元素"
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
ms.assetid: ccdc3777-b2c2-44e3-a627-abef8d79a555
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: bbdfe78f15490ce2c6722c83a4615ca29cbc5863
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="return-the-first-element-in-a-sequence"></a>返回序列中的第一个元素
使用 <xref:System.Linq.Enumerable.First%2A> 运算符可返回序列中的第一个元素。 使用 <xref:System.Linq.Enumerable.First%2A> 的查询是立即执行的。  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 不支持 <xref:System.Linq.Enumerable.Last%2A> 运算符。  
  
## <a name="example"></a>示例  
 下面的代码查找表中的第一个 `Shipper`：  
  
 如果您对 Northwind 示例数据库运行此查询，则结果为  
  
 `ID = 1, Company = Speedy Express`。  
  
 [!code-csharp[DLinqQueryExamples#14](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#14)]
 [!code-vb[DLinqQueryExamples#14](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#14)]  
  
## <a name="example"></a>示例  
 下面的代码查找具有 `Customer` BONAP 的单个 `CustomerID`。  
  
 如果您对 Northwind 示例数据库运行此查询，则结果为 `ID = BONAP, Contact = Laurence Lebihan`。  
  
 [!code-csharp[DLinqQueryExamples#15](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#15)]
 [!code-vb[DLinqQueryExamples#15](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#15)]  
  
## <a name="see-also"></a>请参阅  
 [查询示例](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [下载示例数据库](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
