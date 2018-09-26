---
title: 基于方法的查询语法示例：转换
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 19f66872-d5ab-49f8-969f-e53f9632a13d
ms.openlocfilehash: 5f1ef8680bc6826f4e8b1beb1e49fce3a15c40c9
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47197144"
---
# <a name="method-based-query-syntax-examples-conversion"></a><span data-ttu-id="6a2cd-102">基于方法的查询语法示例：转换</span><span class="sxs-lookup"><span data-stu-id="6a2cd-102">Method-Based Query Syntax Examples: Conversion</span></span>
<span data-ttu-id="6a2cd-103">本主题中的示例演示如何使用<xref:System.Linq.Enumerable.ToArray%2A>，<xref:System.Linq.Enumerable.ToDictionary%2A>并<xref:System.Linq.Enumerable.ToList%2A>方法来查询[AdventureWorks 销售模型](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832)使用基于方法的查询语法。</span><span class="sxs-lookup"><span data-stu-id="6a2cd-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> and <xref:System.Linq.Enumerable.ToList%2A> methods to query the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="6a2cd-104">这些示例中使用的 AdventureWorks 销售模型从 AdventureWorks 示例数据库中的 Contact、Address、Product、SalesOrderHeader 和 SalesOrderDetail 等表生成。</span><span class="sxs-lookup"><span data-stu-id="6a2cd-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="6a2cd-105">本主题中的示例使用以下`using` / `Imports`语句：</span><span class="sxs-lookup"><span data-stu-id="6a2cd-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="toarray"></a><span data-ttu-id="6a2cd-106">ToArray</span><span class="sxs-lookup"><span data-stu-id="6a2cd-106">ToArray</span></span>  
  
### <a name="example"></a><span data-ttu-id="6a2cd-107">示例</span><span class="sxs-lookup"><span data-stu-id="6a2cd-107">Example</span></span>  
 <span data-ttu-id="6a2cd-108">以下示例使用 <xref:System.Linq.Enumerable.ToArray%2A> 方法以立即将序列转换为数组。</span><span class="sxs-lookup"><span data-stu-id="6a2cd-108">The following example uses the <xref:System.Linq.Enumerable.ToArray%2A> method to immediately evaluate a sequence into an array.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToArray](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#toarray)]
 [!code-vb[DP L2E Examples#ToArray](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#toarray)]  
  
## <a name="todictionary"></a><span data-ttu-id="6a2cd-109">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="6a2cd-109">ToDictionary</span></span>  
  
### <a name="example"></a><span data-ttu-id="6a2cd-110">示例</span><span class="sxs-lookup"><span data-stu-id="6a2cd-110">Example</span></span>  
 <span data-ttu-id="6a2cd-111">以下示例使用 <xref:System.Linq.Enumerable.ToDictionary%2A> 方法以立即将序列和相关的键表达式转换为字典。</span><span class="sxs-lookup"><span data-stu-id="6a2cd-111">The following example uses the <xref:System.Linq.Enumerable.ToDictionary%2A> method to immediately evaluate a sequence and a related key expression into a dictionary.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#todictionary)]
 [!code-vb[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#todictionary)]  
  
## <a name="tolist"></a><span data-ttu-id="6a2cd-112">ToList</span><span class="sxs-lookup"><span data-stu-id="6a2cd-112">ToList</span></span>  
  
### <a name="example"></a><span data-ttu-id="6a2cd-113">示例</span><span class="sxs-lookup"><span data-stu-id="6a2cd-113">Example</span></span>  
 <span data-ttu-id="6a2cd-114">以下示例使用 <xref:System.Linq.Enumerable.ToList%2A> 方法以立即将序列转换为 <xref:System.Collections.Generic.List%601>，其中，`T` 属于类型 <xref:System.Data.DataRow>。</span><span class="sxs-lookup"><span data-stu-id="6a2cd-114">The following example uses the <xref:System.Linq.Enumerable.ToList%2A> method to immediately evaluate a sequence into a <xref:System.Collections.Generic.List%601>, where `T` is of type <xref:System.Data.DataRow>.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToList](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#tolist)]
 [!code-vb[DP L2E Examples#ToList](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#tolist)]  
  
## <a name="see-also"></a><span data-ttu-id="6a2cd-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a2cd-115">See Also</span></span>  
 [<span data-ttu-id="6a2cd-116">LINQ to Entities 中的查询</span><span class="sxs-lookup"><span data-stu-id="6a2cd-116">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
