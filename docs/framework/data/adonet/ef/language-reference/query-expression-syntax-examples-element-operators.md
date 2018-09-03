---
title: 查询表达式语法示例：元素运算符
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 32268fe2-de18-4065-8060-f250def83837
ms.openlocfilehash: 36823b02d581b47493950b6393bda323b2e8f9b7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43467079"
---
# <a name="query-expression-syntax-examples-element-operators"></a><span data-ttu-id="3ba0f-102">查询表达式语法示例：元素运算符</span><span class="sxs-lookup"><span data-stu-id="3ba0f-102">Query Expression Syntax Examples: Element Operators</span></span>
<span data-ttu-id="3ba0f-103">本主题中的示例演示如何使用<xref:System.Linq.Enumerable.First%2A>方法来查询[AdventureWorks 销售模型](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832)使用查询表达式语法。</span><span class="sxs-lookup"><span data-stu-id="3ba0f-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using the query expression syntax.</span></span> <span data-ttu-id="3ba0f-104">这些示例中使用的 AdventureWorks 销售模型从 AdventureWorks 示例数据库中的 Contact、Address、Product、SalesOrderHeader 和 SalesOrderDetail 等表生成。</span><span class="sxs-lookup"><span data-stu-id="3ba0f-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="3ba0f-105">本主题中的示例使用以下`using` / `Imports`语句：</span><span class="sxs-lookup"><span data-stu-id="3ba0f-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="3ba0f-106">First</span><span class="sxs-lookup"><span data-stu-id="3ba0f-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="3ba0f-107">示例</span><span class="sxs-lookup"><span data-stu-id="3ba0f-107">Example</span></span>  
 <span data-ttu-id="3ba0f-108">以下示例使用 <xref:System.Linq.Enumerable.First%2A> 方法以返回其名字为“Brooke”的第一个联系人。</span><span class="sxs-lookup"><span data-stu-id="3ba0f-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to return the first contact whose first name is "Brooke".</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstsimple)]
 [!code-vb[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="3ba0f-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="3ba0f-109">See Also</span></span>  
 [<span data-ttu-id="3ba0f-110">LINQ to Entities 中的查询</span><span class="sxs-lookup"><span data-stu-id="3ba0f-110">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
