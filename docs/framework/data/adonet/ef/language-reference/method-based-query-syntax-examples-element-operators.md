---
title: 基于方法的查询语法示例：元素运算符
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8438b995-bd07-4223-b22d-13adadef33fb
ms.openlocfilehash: 7add62a2792a0fc82346851b7dd835aad5082742
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397464"
---
# <a name="method-based-query-syntax-examples-element-operators"></a><span data-ttu-id="f332e-102">基于方法的查询语法示例：元素运算符</span><span class="sxs-lookup"><span data-stu-id="f332e-102">Method-Based Query Syntax Examples: Element Operators</span></span>
<span data-ttu-id="f332e-103">本主题中的示例演示如何使用<xref:System.Linq.Enumerable.First%2A>方法通过使用基于方法的查询语法来查询[AdventureWorks 销售模型](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)。</span><span class="sxs-lookup"><span data-stu-id="f332e-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="f332e-104">这些示例中使用的 AdventureWorks 销售模型从 AdventureWorks 示例数据库中的 Contact、Address、Product、SalesOrderHeader 和 SalesOrderDetail 等表生成。</span><span class="sxs-lookup"><span data-stu-id="f332e-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="f332e-105">本主题中的示例使用以下`using` / `Imports`语句：</span><span class="sxs-lookup"><span data-stu-id="f332e-105">The example in this topic uses the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="f332e-106">第一个</span><span class="sxs-lookup"><span data-stu-id="f332e-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="f332e-107">示例</span><span class="sxs-lookup"><span data-stu-id="f332e-107">Example</span></span>  
 <span data-ttu-id="f332e-108">下面的示例使用<xref:System.Linq.Enumerable.First%2A>方法查找以 "caroline" 开头的第一个电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="f332e-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to find the first email address that starts with 'caroline'.</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstcondition_mq)]
 [!code-vb[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstcondition_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="f332e-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="f332e-109">See also</span></span>

- [<span data-ttu-id="f332e-110">LINQ to Entities 中的查询</span><span class="sxs-lookup"><span data-stu-id="f332e-110">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
