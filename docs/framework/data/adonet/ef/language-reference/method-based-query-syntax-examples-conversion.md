---
title: 基于方法的查询语法示例：转换
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 19f66872-d5ab-49f8-969f-e53f9632a13d
ms.openlocfilehash: a78588cb4bd09f8a8a8ce8ed4a60dd45fce1d386
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397486"
---
# <a name="method-based-query-syntax-examples-conversion"></a><span data-ttu-id="dfa6c-102">基于方法的查询语法示例：转换</span><span class="sxs-lookup"><span data-stu-id="dfa6c-102">Method-Based Query Syntax Examples: Conversion</span></span>
<span data-ttu-id="dfa6c-103">本主题中的示例演示如何使用<xref:System.Linq.Enumerable.ToArray%2A>和<xref:System.Linq.Enumerable.ToList%2A>方法， <xref:System.Linq.Enumerable.ToDictionary%2A>通过基于方法的查询语法来查询[AdventureWorks 销售模型](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)。</span><span class="sxs-lookup"><span data-stu-id="dfa6c-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> and <xref:System.Linq.Enumerable.ToList%2A> methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="dfa6c-104">这些示例中使用的 AdventureWorks 销售模型从 AdventureWorks 示例数据库中的 Contact、Address、Product、SalesOrderHeader 和 SalesOrderDetail 等表生成。</span><span class="sxs-lookup"><span data-stu-id="dfa6c-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="dfa6c-105">本主题中的示例使用以下`using` / `Imports`语句：</span><span class="sxs-lookup"><span data-stu-id="dfa6c-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="toarray"></a><span data-ttu-id="dfa6c-106">ToArray</span><span class="sxs-lookup"><span data-stu-id="dfa6c-106">ToArray</span></span>  
  
### <a name="example"></a><span data-ttu-id="dfa6c-107">示例</span><span class="sxs-lookup"><span data-stu-id="dfa6c-107">Example</span></span>  
 <span data-ttu-id="dfa6c-108">以下示例使用 <xref:System.Linq.Enumerable.ToArray%2A> 方法以立即将序列转换为数组。</span><span class="sxs-lookup"><span data-stu-id="dfa6c-108">The following example uses the <xref:System.Linq.Enumerable.ToArray%2A> method to immediately evaluate a sequence into an array.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToArray](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#toarray)]
 [!code-vb[DP L2E Examples#ToArray](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#toarray)]  
  
## <a name="todictionary"></a><span data-ttu-id="dfa6c-109">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="dfa6c-109">ToDictionary</span></span>  
  
### <a name="example"></a><span data-ttu-id="dfa6c-110">示例</span><span class="sxs-lookup"><span data-stu-id="dfa6c-110">Example</span></span>  
 <span data-ttu-id="dfa6c-111">以下示例使用 <xref:System.Linq.Enumerable.ToDictionary%2A> 方法以立即将序列和相关的键表达式转换为字典。</span><span class="sxs-lookup"><span data-stu-id="dfa6c-111">The following example uses the <xref:System.Linq.Enumerable.ToDictionary%2A> method to immediately evaluate a sequence and a related key expression into a dictionary.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#todictionary)]
 [!code-vb[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#todictionary)]  
  
## <a name="tolist"></a><span data-ttu-id="dfa6c-112">ToList</span><span class="sxs-lookup"><span data-stu-id="dfa6c-112">ToList</span></span>  
  
### <a name="example"></a><span data-ttu-id="dfa6c-113">示例</span><span class="sxs-lookup"><span data-stu-id="dfa6c-113">Example</span></span>  
 <span data-ttu-id="dfa6c-114">以下示例使用 <xref:System.Linq.Enumerable.ToList%2A> 方法以立即将序列转换为 <xref:System.Collections.Generic.List%601>，其中，`T` 属于类型 <xref:System.Data.DataRow>。</span><span class="sxs-lookup"><span data-stu-id="dfa6c-114">The following example uses the <xref:System.Linq.Enumerable.ToList%2A> method to immediately evaluate a sequence into a <xref:System.Collections.Generic.List%601>, where `T` is of type <xref:System.Data.DataRow>.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToList](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#tolist)]
 [!code-vb[DP L2E Examples#ToList](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#tolist)]  
  
## <a name="see-also"></a><span data-ttu-id="dfa6c-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="dfa6c-115">See also</span></span>

- [<span data-ttu-id="dfa6c-116">LINQ to Entities 中的查询</span><span class="sxs-lookup"><span data-stu-id="dfa6c-116">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
