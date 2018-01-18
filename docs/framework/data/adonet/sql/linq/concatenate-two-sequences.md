---
title: "连接两个序列"
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
ms.assetid: 76767e7c-0607-4e1d-9ca2-a94f311f45eb
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a73ace484c3ca519f250069063a9222b75ef6c17
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="concatenate-two-sequences"></a>连接两个序列
使用 <xref:System.Linq.Queryable.Concat%2A> 运算符可串联两个序列。  
  
 <xref:System.Linq.Queryable.Concat%2A> 运算符是为有序多重集定义的，其中接收方的顺序与参数的顺序相同。  
  
 在 SQL 中排序是产生结果前的最后一步。 因此，<xref:System.Linq.Queryable.Concat%2A> 运算符是通过使用 `UNION ALL` 实现的，并且不保留其参数的顺序。 为确保结果中的顺序正确，一定要显式地对结果进行排序。  
  
## <a name="example"></a>示例  
 此示例使用 <xref:System.Linq.Queryable.Concat%2A> 返回由所有 `Customer` 和 `Employee` 的电话和传真号码组成的序列。  
  
 [!code-csharp[DLinqQueryExamples#39](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#39)]
 [!code-vb[DLinqQueryExamples#39](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#39)]  
  
## <a name="example"></a>示例  
 此示例使用 <xref:System.Linq.Queryable.Concat%2A> 返回由所有 `Customer` 和 `Employee` 的名字和电话号码映射组成的序列。  
  
 [!code-csharp[DLinqQueryExamples#40](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#40)]
 [!code-vb[DLinqQueryExamples#40](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#40)]  
  
## <a name="see-also"></a>请参阅  
 [查询示例](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [标准查询运算符转换](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
