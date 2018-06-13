---
title: 确定序列中任何或所有元素是否满足某一条件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 339ec145-826c-46d2-8cf2-3acd252cd072
ms.openlocfilehash: cd910b35f82f816158cb686a283e44e3b8b6b33b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33359967"
---
# <a name="determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition"></a><span data-ttu-id="3d80e-102">确定序列中任何或所有元素是否满足某一条件</span><span class="sxs-lookup"><span data-stu-id="3d80e-102">Determine if Any or All Elements in a Sequence Satisfy a Condition</span></span>
<span data-ttu-id="3d80e-103">如果序列中的所有元素都满足某一项条件，则 <xref:System.Linq.Enumerable.All%2A> 运算符会返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="3d80e-103">The <xref:System.Linq.Enumerable.All%2A> operator returns `true` if all elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="3d80e-104">如果序列中的任意一个元素满足某一项条件，则 <xref:System.Linq.Queryable.Any%2A> 运算符会返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="3d80e-104">The <xref:System.Linq.Queryable.Any%2A> operator returns `true` if any element in a sequence satisfies a condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d80e-105">示例</span><span class="sxs-lookup"><span data-stu-id="3d80e-105">Example</span></span>  
 <span data-ttu-id="3d80e-106">下面的示例返回由至少下了一个订单的客户组成的序列。</span><span class="sxs-lookup"><span data-stu-id="3d80e-106">The following example returns a sequence of customers that have at least one order.</span></span> <span data-ttu-id="3d80e-107">`Where` / `where`子句的计算结果为`true`如果给定`Customer`具有任何`Order`。</span><span class="sxs-lookup"><span data-stu-id="3d80e-107">The `Where`/`where` clause evaluates to `true` if the given `Customer` has any `Order`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#37](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#37)]
 [!code-vb[DLinqQueryExamples#37](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37)]  
  
## <a name="example"></a><span data-ttu-id="3d80e-108">示例</span><span class="sxs-lookup"><span data-stu-id="3d80e-108">Example</span></span>  
 <span data-ttu-id="3d80e-109">下面的 Visual Basic 代码确定未下订单的客户的列表，并确保对于该列表中的每一位客户，都提供了联系人名称。</span><span class="sxs-lookup"><span data-stu-id="3d80e-109">The following Visual Basic code determines the list of customers who have not placed orders, and ensures that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#37v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37v)]  
  
## <a name="example"></a><span data-ttu-id="3d80e-110">示例</span><span class="sxs-lookup"><span data-stu-id="3d80e-110">Example</span></span>  
 <span data-ttu-id="3d80e-111">下面的 C# 示例返回由订单包含以“C”开头的 `ShipCity` 的客户组成的序列。</span><span class="sxs-lookup"><span data-stu-id="3d80e-111">The following C# example returns a sequence of customers whose orders have a `ShipCity` beginning with "C".</span></span> <span data-ttu-id="3d80e-112">返回结果中还包括未下订单的客户。</span><span class="sxs-lookup"><span data-stu-id="3d80e-112">Also included in the return are customers who have no orders.</span></span> <span data-ttu-id="3d80e-113">（按照设计，对于空序列，<xref:System.Linq.Queryable.All%2A> 运算符返回 `true`。）通过使用 `Count` 运算符在控制台输出中消除了未下订单的客户。</span><span class="sxs-lookup"><span data-stu-id="3d80e-113">(By design, the <xref:System.Linq.Queryable.All%2A> operator returns `true` for an empty sequence.) Customers with no orders are eliminated in the console output by using the `Count` operator.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#38](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#38)]  
  
## <a name="see-also"></a><span data-ttu-id="3d80e-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d80e-114">See Also</span></span>  
 [<span data-ttu-id="3d80e-115">查询示例</span><span class="sxs-lookup"><span data-stu-id="3d80e-115">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
