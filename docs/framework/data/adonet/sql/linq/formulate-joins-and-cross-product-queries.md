---
title: "构建联接和跨产品查询"
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
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 5f652f25d04480afb3df1f623347eee23d3ed258
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="formulate-joins-and-cross-product-queries"></a><span data-ttu-id="e09a4-102">构建联接和跨产品查询</span><span class="sxs-lookup"><span data-stu-id="e09a4-102">Formulate Joins and Cross-Product Queries</span></span>
<span data-ttu-id="e09a4-103">下面的示例演示如何组合来自多个表的结果。</span><span class="sxs-lookup"><span data-stu-id="e09a4-103">The following examples show how to combine results from multiple tables.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e09a4-104">示例</span><span class="sxs-lookup"><span data-stu-id="e09a4-104">Example</span></span>  
 <span data-ttu-id="e09a4-105">下面的示例在 `From` 中的 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 子句（在 C# 中为 `from` 子句）中使用外键导航来选择位于伦敦的客户所下的所有订单。</span><span class="sxs-lookup"><span data-stu-id="e09a4-105">The following example uses foreign key navigation in the `From` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`from` clause in C#) to select all orders for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a><span data-ttu-id="e09a4-106">示例</span><span class="sxs-lookup"><span data-stu-id="e09a4-106">Example</span></span>  
 <span data-ttu-id="e09a4-107">下面的示例在 `Where` 中的 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 子句（在 C# 中为 `where` 子句）中使用外键导航来筛选出 `Products` 位于美国的脱销 `Supplier`。</span><span class="sxs-lookup"><span data-stu-id="e09a4-107">The following example uses foreign key navigation in the `Where` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`where` clause in C#) to filter for out-of-stock `Products` whose `Supplier` is in the United States.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a><span data-ttu-id="e09a4-108">示例</span><span class="sxs-lookup"><span data-stu-id="e09a4-108">Example</span></span>  
 <span data-ttu-id="e09a4-109">下面的示例在 `From` 中的 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 子句（在 C# 中为 `from` 子句）中使用外键导航来筛选出位于西雅图的员工并列出它们所在的地区。</span><span class="sxs-lookup"><span data-stu-id="e09a4-109">The following example uses foreign key navigation in the `From` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`from` clause in C#) to filter for employees in Seattle and to list their territories.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a><span data-ttu-id="e09a4-110">示例</span><span class="sxs-lookup"><span data-stu-id="e09a4-110">Example</span></span>  
 <span data-ttu-id="e09a4-111">下面的示例在 `Select` 中的 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 子句（在 C# 中为 `select` 子句）中使用外键导航来筛选出存在以下关系的雇员对：其中一位雇员是另一位雇员的下属，且这两位雇员来自同一 `City`。</span><span class="sxs-lookup"><span data-stu-id="e09a4-111">The following example uses foreign key navigation in the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) to filter for pairs of employees where one employee reports to the other and where both employees are from the same `City`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a><span data-ttu-id="e09a4-112">示例</span><span class="sxs-lookup"><span data-stu-id="e09a4-112">Example</span></span>  
 <span data-ttu-id="e09a4-113">下面的 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 示例查找所有客户和订单，确保相应的订单与客户匹配，并保证对于该列表中的每位客户，都提供了联系人姓名。</span><span class="sxs-lookup"><span data-stu-id="e09a4-113">The following [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] example looks for all customers and orders, makes sure that the orders are matched to customers, and guarantees that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## <a name="example"></a><span data-ttu-id="e09a4-114">示例</span><span class="sxs-lookup"><span data-stu-id="e09a4-114">Example</span></span>  
 <span data-ttu-id="e09a4-115">下面的示例显式联接两个表并投影来自这两个表的结果。</span><span class="sxs-lookup"><span data-stu-id="e09a4-115">The following example explicitly joins two tables and projects results from both tables.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## <a name="example"></a><span data-ttu-id="e09a4-116">示例</span><span class="sxs-lookup"><span data-stu-id="e09a4-116">Example</span></span>  
 <span data-ttu-id="e09a4-117">下面的示例显式联接三个表并投影来自其中各个表的结果。</span><span class="sxs-lookup"><span data-stu-id="e09a4-117">The following example explicitly joins three tables and projects results from each of them.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## <a name="example"></a><span data-ttu-id="e09a4-118">示例</span><span class="sxs-lookup"><span data-stu-id="e09a4-118">Example</span></span>  
 <span data-ttu-id="e09a4-119">下面的示例演示如何通过使用 `LEFT OUTER JOIN` 实现 `DefaultIfEmpty()`。</span><span class="sxs-lookup"><span data-stu-id="e09a4-119">The following example shows how to achieve a `LEFT OUTER JOIN` by using `DefaultIfEmpty()`.</span></span> <span data-ttu-id="e09a4-120">如果对应的 `DefaultIfEmpty()` 没有 `Order`，则 `Employee` 方法将返回 null。</span><span class="sxs-lookup"><span data-stu-id="e09a4-120">The `DefaultIfEmpty()` method returns null when there is no `Order` for the `Employee`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## <a name="example"></a><span data-ttu-id="e09a4-121">示例</span><span class="sxs-lookup"><span data-stu-id="e09a4-121">Example</span></span>  
 <span data-ttu-id="e09a4-122">下面的示例投影通过联接获得的 `let` 表达式。</span><span class="sxs-lookup"><span data-stu-id="e09a4-122">The following example projects a `let` expression resulting from a join.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## <a name="example"></a><span data-ttu-id="e09a4-123">示例</span><span class="sxs-lookup"><span data-stu-id="e09a4-123">Example</span></span>  
 <span data-ttu-id="e09a4-124">下面的示例显示了一个带有组合键的 `join`。</span><span class="sxs-lookup"><span data-stu-id="e09a4-124">The following example shows a `join` with a composite key.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## <a name="example"></a><span data-ttu-id="e09a4-125">示例</span><span class="sxs-lookup"><span data-stu-id="e09a4-125">Example</span></span>  
 <span data-ttu-id="e09a4-126">下面的示例演示如何构造其中一端可以为 null、另一端不可以为 null 的 `join`。</span><span class="sxs-lookup"><span data-stu-id="e09a4-126">The following example shows how to construct a `join` where one side is nullable and the other is not.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="e09a4-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="e09a4-127">See Also</span></span>  
 [<span data-ttu-id="e09a4-128">查询示例</span><span class="sxs-lookup"><span data-stu-id="e09a4-128">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
