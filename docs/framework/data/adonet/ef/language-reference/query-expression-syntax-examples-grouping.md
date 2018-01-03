---
title: "查询表达式语法示例：分组"
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
ms.assetid: 2d83d7c0-b3be-4c92-a630-25cd1285de31
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 313a218827122a8694ee314925408ec3526f01c9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="query-expression-syntax-examples-grouping"></a><span data-ttu-id="9039c-102">查询表达式语法示例：分组</span><span class="sxs-lookup"><span data-stu-id="9039c-102">Query Expression Syntax Examples: Grouping</span></span>
<span data-ttu-id="9039c-103">本主题中的示例演示如何使用`GroupBy`方法来查询[AdventureWorks 销售模型](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832)使用查询表达式语法。</span><span class="sxs-lookup"><span data-stu-id="9039c-103">The examples in this topic demonstrate how to use the `GroupBy` method to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) using query expression syntax.</span></span> <span data-ttu-id="9039c-104">这些示例中使用的 AdventureWorks 销售模型从 AdventureWorks 示例数据库中的 Contact、Address、Product、SalesOrderHeader 和 SalesOrderDetail 等表生成。</span><span class="sxs-lookup"><span data-stu-id="9039c-104">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="9039c-105">本主题中的示例使用以下`using` / `Imports`语句：</span><span class="sxs-lookup"><span data-stu-id="9039c-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="9039c-106">示例</span><span class="sxs-lookup"><span data-stu-id="9039c-106">Example</span></span>  
 <span data-ttu-id="9039c-107">以下示例返回按邮政编码分组的 `Address` 对象。</span><span class="sxs-lookup"><span data-stu-id="9039c-107">The following example returns `Address` objects grouped by postal code.</span></span> <span data-ttu-id="9039c-108">这些结果将投影到一个匿名类型。</span><span class="sxs-lookup"><span data-stu-id="9039c-108">The results are projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple3)]
 [!code-vb[DP L2E Examples#GroupBySimple3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple3)]  
  
## <a name="example"></a><span data-ttu-id="9039c-109">示例</span><span class="sxs-lookup"><span data-stu-id="9039c-109">Example</span></span>  
 <span data-ttu-id="9039c-110">以下示例返回按联系人姓氏的第一个字母分组的 `Contact` 对象。</span><span class="sxs-lookup"><span data-stu-id="9039c-110">The following example returns `Contact` objects grouped by the first letter of the contact's last name.</span></span> <span data-ttu-id="9039c-111">这些结果还可以按姓氏的第一个字母进行排序，并投影到一个匿名类型。</span><span class="sxs-lookup"><span data-stu-id="9039c-111">The results are also sorted by the first letter of last name and projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple2)]
 [!code-vb[DP L2E Examples#GroupBySimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple2)]  
  
## <a name="example"></a><span data-ttu-id="9039c-112">示例</span><span class="sxs-lookup"><span data-stu-id="9039c-112">Example</span></span>  
 <span data-ttu-id="9039c-113">下面的示例返回按客户 ID 分组的 `SalesOrderHeader` 对象。</span><span class="sxs-lookup"><span data-stu-id="9039c-113">The following example returns `SalesOrderHeader` objects grouped by customer ID.</span></span> <span data-ttu-id="9039c-114">同时还返回每个客户的销售数量。</span><span class="sxs-lookup"><span data-stu-id="9039c-114">The number of sales for each customer is also returned.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupByCount](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbycount)]
 [!code-vb[DP L2E Examples#GroupByCount](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbycount)]  
  
## <a name="see-also"></a><span data-ttu-id="9039c-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="9039c-115">See Also</span></span>  
 [<span data-ttu-id="9039c-116">LINQ to Entities 中的查询</span><span class="sxs-lookup"><span data-stu-id="9039c-116">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
