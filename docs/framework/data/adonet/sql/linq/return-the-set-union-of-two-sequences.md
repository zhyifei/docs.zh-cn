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
# <a name="return-the-set-union-of-two-sequences"></a><span data-ttu-id="a11fb-102">返回两个序列的并集</span><span class="sxs-lookup"><span data-stu-id="a11fb-102">Return the Set Union of Two Sequences</span></span>
<span data-ttu-id="a11fb-103">使用 <xref:System.Linq.Queryable.Union%2A> 运算符可返回两个序列的并集。</span><span class="sxs-lookup"><span data-stu-id="a11fb-103">Use the <xref:System.Linq.Queryable.Union%2A> operator to return the set union of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a11fb-104">示例</span><span class="sxs-lookup"><span data-stu-id="a11fb-104">Example</span></span>  
 <span data-ttu-id="a11fb-105">此示例使用 <xref:System.Linq.Queryable.Union%2A> 返回有 `Customers` 或 `Employees` 的所有国家/地区的序列。</span><span class="sxs-lookup"><span data-stu-id="a11fb-105">This example uses <xref:System.Linq.Queryable.Union%2A> to return a sequence of all countries in which there are either `Customers` or `Employees`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 <span data-ttu-id="a11fb-106">在 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中，<xref:System.Linq.Queryable.Union%2A> 运算符是为多重集定义的，定义为多重集的无序串联（实际上是 SQL 中的 `UNION ALL` 子句的执行结果）。</span><span class="sxs-lookup"><span data-stu-id="a11fb-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Union%2A> operator is defined for multisets as the unordered concatenation of the multisets (effectively the result of the `UNION ALL` clause in SQL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a11fb-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a11fb-107">See Also</span></span>  
 [<span data-ttu-id="a11fb-108">查询示例</span><span class="sxs-lookup"><span data-stu-id="a11fb-108">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="a11fb-109">标准查询运算符转换</span><span class="sxs-lookup"><span data-stu-id="a11fb-109">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
