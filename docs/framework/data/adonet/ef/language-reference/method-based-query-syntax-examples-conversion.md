---
title: "基于方法的查询语法示例：转换"
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
ms.assetid: 19f66872-d5ab-49f8-969f-e53f9632a13d
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: aafc059b5560af1fef54c20a3718d3f405ce7ba9
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="method-based-query-syntax-examples-conversion"></a><span data-ttu-id="28ba7-102">基于方法的查询语法示例：转换</span><span class="sxs-lookup"><span data-stu-id="28ba7-102">Method-Based Query Syntax Examples: Conversion</span></span>
<span data-ttu-id="28ba7-103">本主题中的示例演示如何使用<xref:System.Linq.Enumerable.ToArray%2A>，<xref:System.Linq.Enumerable.ToDictionary%2A>和<xref:System.Linq.Enumerable.ToList%2A>方法来查询[AdventureWorks 销售模型](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832)使用基于方法的查询语法。</span><span class="sxs-lookup"><span data-stu-id="28ba7-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> and <xref:System.Linq.Enumerable.ToList%2A> methods to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="28ba7-104">这些示例中使用的 AdventureWorks 销售模型从 AdventureWorks 示例数据库中的 Contact、Address、Product、SalesOrderHeader 和 SalesOrderDetail 等表生成。</span><span class="sxs-lookup"><span data-stu-id="28ba7-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="28ba7-105">本主题中的示例使用以下`using` / `Imports`语句：</span><span class="sxs-lookup"><span data-stu-id="28ba7-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="toarray"></a><span data-ttu-id="28ba7-106">ToArray</span><span class="sxs-lookup"><span data-stu-id="28ba7-106">ToArray</span></span>  
  
### <a name="example"></a><span data-ttu-id="28ba7-107">示例</span><span class="sxs-lookup"><span data-stu-id="28ba7-107">Example</span></span>  
 <span data-ttu-id="28ba7-108">以下示例使用 <xref:System.Linq.Enumerable.ToArray%2A> 方法以立即将序列转换为数组。</span><span class="sxs-lookup"><span data-stu-id="28ba7-108">The following example uses the <xref:System.Linq.Enumerable.ToArray%2A> method to immediately evaluate a sequence into an array.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToArray](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#toarray)]
 [!code-vb[DP L2E Examples#ToArray](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#toarray)]  
  
## <a name="todictionary"></a><span data-ttu-id="28ba7-109">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="28ba7-109">ToDictionary</span></span>  
  
### <a name="example"></a><span data-ttu-id="28ba7-110">示例</span><span class="sxs-lookup"><span data-stu-id="28ba7-110">Example</span></span>  
 <span data-ttu-id="28ba7-111">以下示例使用 <xref:System.Linq.Enumerable.ToDictionary%2A> 方法以立即将序列和相关的键表达式转换为字典。</span><span class="sxs-lookup"><span data-stu-id="28ba7-111">The following example uses the <xref:System.Linq.Enumerable.ToDictionary%2A> method to immediately evaluate a sequence and a related key expression into a dictionary.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#todictionary)]
 [!code-vb[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#todictionary)]  
  
## <a name="tolist"></a><span data-ttu-id="28ba7-112">ToList</span><span class="sxs-lookup"><span data-stu-id="28ba7-112">ToList</span></span>  
  
### <a name="example"></a><span data-ttu-id="28ba7-113">示例</span><span class="sxs-lookup"><span data-stu-id="28ba7-113">Example</span></span>  
 <span data-ttu-id="28ba7-114">以下示例使用 <xref:System.Linq.Enumerable.ToList%2A> 方法以立即将序列转换为 <xref:System.Collections.Generic.List%601>，其中，`T` 属于类型 <xref:System.Data.DataRow>。</span><span class="sxs-lookup"><span data-stu-id="28ba7-114">The following example uses the <xref:System.Linq.Enumerable.ToList%2A> method to immediately evaluate a sequence into a <xref:System.Collections.Generic.List%601>, where `T` is of type <xref:System.Data.DataRow>.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToList](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#tolist)]
 [!code-vb[DP L2E Examples#ToList](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#tolist)]  
  
## <a name="see-also"></a><span data-ttu-id="28ba7-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="28ba7-115">See Also</span></span>  
 [<span data-ttu-id="28ba7-116">LINQ to Entities 中的查询</span><span class="sxs-lookup"><span data-stu-id="28ba7-116">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
