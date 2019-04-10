---
title: 基于方法的查询语法示例：元素运算符
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8438b995-bd07-4223-b22d-13adadef33fb
ms.openlocfilehash: 3656ea6d2d9602c3790ab4113b5c2f153b4f7c73
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188586"
---
# <a name="method-based-query-syntax-examples-element-operators"></a><span data-ttu-id="e967f-102">基于方法的查询语法示例：元素运算符</span><span class="sxs-lookup"><span data-stu-id="e967f-102">Method-Based Query Syntax Examples: Element Operators</span></span>
<span data-ttu-id="e967f-103">本主题中的示例演示如何使用<xref:System.Linq.Enumerable.First%2A>方法来查询[AdventureWorks 销售模型](https://archive.codeplex.com/?p=msftdbprodsamples)使用基于方法的查询语法。</span><span class="sxs-lookup"><span data-stu-id="e967f-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="e967f-104">这些示例中使用的 AdventureWorks 销售模型从 AdventureWorks 示例数据库中的 Contact、Address、Product、SalesOrderHeader 和 SalesOrderDetail 等表生成。</span><span class="sxs-lookup"><span data-stu-id="e967f-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="e967f-105">本主题中的示例使用以下`using` / `Imports`语句：</span><span class="sxs-lookup"><span data-stu-id="e967f-105">The example in this topic uses the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="e967f-106">First</span><span class="sxs-lookup"><span data-stu-id="e967f-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="e967f-107">示例</span><span class="sxs-lookup"><span data-stu-id="e967f-107">Example</span></span>  
 <span data-ttu-id="e967f-108">下面的示例使用<xref:System.Linq.Enumerable.First%2A>方法启动的第一个电子邮件地址查找 caroline 开头。</span><span class="sxs-lookup"><span data-stu-id="e967f-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to find the first email address that starts with 'caroline'.</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstcondition_mq)]
 [!code-vb[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstcondition_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="e967f-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="e967f-109">See also</span></span>

- [<span data-ttu-id="e967f-110">LINQ to Entities 中的查询</span><span class="sxs-lookup"><span data-stu-id="e967f-110">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
