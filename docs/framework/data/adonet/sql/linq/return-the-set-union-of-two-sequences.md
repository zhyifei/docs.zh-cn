---
title: 返回两个序列的并集
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: c7d7a267df13cfa54d682ab9b65953f2c0a85a27
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2018
ms.locfileid: "49347541"
---
# <a name="return-the-set-union-of-two-sequences"></a><span data-ttu-id="17b61-102">返回两个序列的并集</span><span class="sxs-lookup"><span data-stu-id="17b61-102">Return the Set Union of Two Sequences</span></span>
<span data-ttu-id="17b61-103">使用 <xref:System.Linq.Queryable.Union%2A> 运算符可返回两个序列的并集。</span><span class="sxs-lookup"><span data-stu-id="17b61-103">Use the <xref:System.Linq.Queryable.Union%2A> operator to return the set union of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17b61-104">示例</span><span class="sxs-lookup"><span data-stu-id="17b61-104">Example</span></span>  
 <span data-ttu-id="17b61-105">此示例使用 <xref:System.Linq.Queryable.Union%2A> 返回有 `Customers` 或 `Employees` 的所有国家/地区的序列。</span><span class="sxs-lookup"><span data-stu-id="17b61-105">This example uses <xref:System.Linq.Queryable.Union%2A> to return a sequence of all countries in which there are either `Customers` or `Employees`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 <span data-ttu-id="17b61-106">在中[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]，则<xref:System.Linq.Queryable.Union%2A>运算符定义为多重集为多重集的无序串联 (有效的结果[ `UNION ALL` ](https://docs.microsoft.com/sql/t-sql/language-elements/set-operators-union-transact-sql?view=sql-server-2017) SQL 中的子句)。</span><span class="sxs-lookup"><span data-stu-id="17b61-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Union%2A> operator is defined for multisets as the unordered concatenation of the multisets (effectively the result of the [`UNION ALL`](https://docs.microsoft.com/sql/t-sql/language-elements/set-operators-union-transact-sql?view=sql-server-2017) clause in SQL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17b61-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="17b61-107">See Also</span></span>  
 [<span data-ttu-id="17b61-108">查询示例</span><span class="sxs-lookup"><span data-stu-id="17b61-108">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="17b61-109">标准查询运算符转换</span><span class="sxs-lookup"><span data-stu-id="17b61-109">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
