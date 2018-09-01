---
title: 基于方法的查询语法示例：元素运算符
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8438b995-bd07-4223-b22d-13adadef33fb
ms.openlocfilehash: 4215dcddf44647d98ee70c6f2d06345737cba5de
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43384585"
---
# <a name="method-based-query-syntax-examples-element-operators"></a><span data-ttu-id="c056d-102">基于方法的查询语法示例：元素运算符</span><span class="sxs-lookup"><span data-stu-id="c056d-102">Method-Based Query Syntax Examples: Element Operators</span></span>
<span data-ttu-id="c056d-103">本主题中的示例演示如何使用<xref:System.Linq.Enumerable.First%2A>方法来查询[AdventureWorks 销售模型](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832)使用基于方法的查询语法。</span><span class="sxs-lookup"><span data-stu-id="c056d-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="c056d-104">这些示例中使用的 AdventureWorks 销售模型从 AdventureWorks 示例数据库中的 Contact、Address、Product、SalesOrderHeader 和 SalesOrderDetail 等表生成。</span><span class="sxs-lookup"><span data-stu-id="c056d-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="c056d-105">本主题中的示例使用以下`using` / `Imports`语句：</span><span class="sxs-lookup"><span data-stu-id="c056d-105">The example in this topic uses the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="c056d-106">First</span><span class="sxs-lookup"><span data-stu-id="c056d-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="c056d-107">示例</span><span class="sxs-lookup"><span data-stu-id="c056d-107">Example</span></span>  
 <span data-ttu-id="c056d-108">下面的示例使用<xref:System.Linq.Enumerable.First%2A>方法启动的第一个电子邮件地址查找 caroline 开头。</span><span class="sxs-lookup"><span data-stu-id="c056d-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to find the first email address that starts with 'caroline'.</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstcondition_mq)]
 [!code-vb[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstcondition_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="c056d-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="c056d-109">See Also</span></span>  
 [<span data-ttu-id="c056d-110">LINQ to Entities 中的查询</span><span class="sxs-lookup"><span data-stu-id="c056d-110">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
