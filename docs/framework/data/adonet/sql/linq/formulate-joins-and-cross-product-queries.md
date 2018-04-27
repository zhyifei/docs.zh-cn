---
title: 构建联接和跨产品查询
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
caps.latest.revision: 2
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 468ee54b0936afcbb548249bc714ea4b04abd3de
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="formulate-joins-and-cross-product-queries"></a><span data-ttu-id="52ffb-102">构建联接和跨产品查询</span><span class="sxs-lookup"><span data-stu-id="52ffb-102">Formulate Joins and Cross-Product Queries</span></span>
<span data-ttu-id="52ffb-103">下面的示例演示如何组合来自多个表的结果。</span><span class="sxs-lookup"><span data-stu-id="52ffb-103">The following examples show how to combine results from multiple tables.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52ffb-104">示例</span><span class="sxs-lookup"><span data-stu-id="52ffb-104">Example</span></span>  
 <span data-ttu-id="52ffb-105">下面的示例使用中的外键导航`From`在 Visual Basic 中的子句 (`from`子句在 C# 中) 以选择位于伦敦的客户的所有订单。</span><span class="sxs-lookup"><span data-stu-id="52ffb-105">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to select all orders for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a><span data-ttu-id="52ffb-106">示例</span><span class="sxs-lookup"><span data-stu-id="52ffb-106">Example</span></span>  
 <span data-ttu-id="52ffb-107">下面的示例使用中的外键导航`Where`在 Visual Basic 中的子句 (`where`子句在 C# 中) 来筛选出的 stock`Products`其`Supplier`是在美国。</span><span class="sxs-lookup"><span data-stu-id="52ffb-107">The following example uses foreign key navigation in the `Where` clause in Visual Basic (`where` clause in C#) to filter for out-of-stock `Products` whose `Supplier` is in the United States.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a><span data-ttu-id="52ffb-108">示例</span><span class="sxs-lookup"><span data-stu-id="52ffb-108">Example</span></span>  
 <span data-ttu-id="52ffb-109">下面的示例使用中的外键导航`From`在 Visual Basic 中的子句 (`from`子句在 C# 中) 来筛选出存在位于西雅图的员工并列出它们所在的地区。</span><span class="sxs-lookup"><span data-stu-id="52ffb-109">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to filter for employees in Seattle and to list their territories.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a><span data-ttu-id="52ffb-110">示例</span><span class="sxs-lookup"><span data-stu-id="52ffb-110">Example</span></span>  
 <span data-ttu-id="52ffb-111">下面的示例使用中的外键导航`Select`在 Visual Basic 中的子句 (`select`子句在 C# 中) 来筛选出存在关系的雇员对其中一个员工隶属于另且这两位雇员均来自同一`City`。</span><span class="sxs-lookup"><span data-stu-id="52ffb-111">The following example uses foreign key navigation in the `Select` clause in Visual Basic (`select` clause in C#) to filter for pairs of employees where one employee reports to the other and where both employees are from the same `City`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a><span data-ttu-id="52ffb-112">示例</span><span class="sxs-lookup"><span data-stu-id="52ffb-112">Example</span></span>  
 <span data-ttu-id="52ffb-113">下面的 Visual Basic 示例查找所有客户和订单、 可确保相应的订单匹配给客户，并保证对于该列表中每个客户，都提供了联系人名称。</span><span class="sxs-lookup"><span data-stu-id="52ffb-113">The following Visual Basic example looks for all customers and orders, makes sure that the orders are matched to customers, and guarantees that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## <a name="example"></a><span data-ttu-id="52ffb-114">示例</span><span class="sxs-lookup"><span data-stu-id="52ffb-114">Example</span></span>  
 <span data-ttu-id="52ffb-115">下面的示例显式联接两个表并投影来自这两个表的结果。</span><span class="sxs-lookup"><span data-stu-id="52ffb-115">The following example explicitly joins two tables and projects results from both tables.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## <a name="example"></a><span data-ttu-id="52ffb-116">示例</span><span class="sxs-lookup"><span data-stu-id="52ffb-116">Example</span></span>  
 <span data-ttu-id="52ffb-117">下面的示例显式联接三个表并投影来自其中各个表的结果。</span><span class="sxs-lookup"><span data-stu-id="52ffb-117">The following example explicitly joins three tables and projects results from each of them.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## <a name="example"></a><span data-ttu-id="52ffb-118">示例</span><span class="sxs-lookup"><span data-stu-id="52ffb-118">Example</span></span>  
 <span data-ttu-id="52ffb-119">下面的示例演示如何通过使用 `LEFT OUTER JOIN` 实现 `DefaultIfEmpty()`。</span><span class="sxs-lookup"><span data-stu-id="52ffb-119">The following example shows how to achieve a `LEFT OUTER JOIN` by using `DefaultIfEmpty()`.</span></span> <span data-ttu-id="52ffb-120">如果对应的 `DefaultIfEmpty()` 没有 `Order`，则 `Employee` 方法将返回 null。</span><span class="sxs-lookup"><span data-stu-id="52ffb-120">The `DefaultIfEmpty()` method returns null when there is no `Order` for the `Employee`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## <a name="example"></a><span data-ttu-id="52ffb-121">示例</span><span class="sxs-lookup"><span data-stu-id="52ffb-121">Example</span></span>  
 <span data-ttu-id="52ffb-122">下面的示例投影通过联接获得的 `let` 表达式。</span><span class="sxs-lookup"><span data-stu-id="52ffb-122">The following example projects a `let` expression resulting from a join.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## <a name="example"></a><span data-ttu-id="52ffb-123">示例</span><span class="sxs-lookup"><span data-stu-id="52ffb-123">Example</span></span>  
 <span data-ttu-id="52ffb-124">下面的示例显示了一个带有组合键的 `join`。</span><span class="sxs-lookup"><span data-stu-id="52ffb-124">The following example shows a `join` with a composite key.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## <a name="example"></a><span data-ttu-id="52ffb-125">示例</span><span class="sxs-lookup"><span data-stu-id="52ffb-125">Example</span></span>  
 <span data-ttu-id="52ffb-126">下面的示例演示如何构造其中一端可以为 null、另一端不可以为 null 的 `join`。</span><span class="sxs-lookup"><span data-stu-id="52ffb-126">The following example shows how to construct a `join` where one side is nullable and the other is not.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="52ffb-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="52ffb-127">See Also</span></span>  
 [<span data-ttu-id="52ffb-128">查询示例</span><span class="sxs-lookup"><span data-stu-id="52ffb-128">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
