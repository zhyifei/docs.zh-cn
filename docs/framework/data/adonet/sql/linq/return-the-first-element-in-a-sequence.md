---
title: 返回序列中的第一个元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccdc3777-b2c2-44e3-a627-abef8d79a555
ms.openlocfilehash: dca917b3c12b0f9923cc9ea34a2568c412a09831
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033444"
---
# <a name="return-the-first-element-in-a-sequence"></a><span data-ttu-id="38e2d-102">返回序列中的第一个元素</span><span class="sxs-lookup"><span data-stu-id="38e2d-102">Return the First Element in a Sequence</span></span>
<span data-ttu-id="38e2d-103">使用 <xref:System.Linq.Enumerable.First%2A> 运算符可返回序列中的第一个元素。</span><span class="sxs-lookup"><span data-stu-id="38e2d-103">Use the <xref:System.Linq.Enumerable.First%2A> operator to return the first element in a sequence.</span></span> <span data-ttu-id="38e2d-104">使用 <xref:System.Linq.Enumerable.First%2A> 的查询是立即执行的。</span><span class="sxs-lookup"><span data-stu-id="38e2d-104">Queries that use <xref:System.Linq.Enumerable.First%2A> are executed immediately.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="38e2d-105">不支持 <xref:System.Linq.Enumerable.Last%2A> 运算符。</span><span class="sxs-lookup"><span data-stu-id="38e2d-105">does not support the <xref:System.Linq.Enumerable.Last%2A> operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38e2d-106">示例</span><span class="sxs-lookup"><span data-stu-id="38e2d-106">Example</span></span>  
 <span data-ttu-id="38e2d-107">下面的代码查找表中的第一个 `Shipper`：</span><span class="sxs-lookup"><span data-stu-id="38e2d-107">The following code finds the first `Shipper` in a table:</span></span>  
  
 <span data-ttu-id="38e2d-108">如果您对 Northwind 示例数据库运行此查询，则结果为</span><span class="sxs-lookup"><span data-stu-id="38e2d-108">If you run this query against the Northwind sample database, the results are</span></span>  
  
 <span data-ttu-id="38e2d-109">`ID = 1, Company = Speedy Express`。</span><span class="sxs-lookup"><span data-stu-id="38e2d-109">`ID = 1, Company = Speedy Express`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#14](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#14)]
 [!code-vb[DLinqQueryExamples#14](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="38e2d-110">示例</span><span class="sxs-lookup"><span data-stu-id="38e2d-110">Example</span></span>  
 <span data-ttu-id="38e2d-111">下面的代码查找具有 `Customer` BONAP 的单个 `CustomerID`。</span><span class="sxs-lookup"><span data-stu-id="38e2d-111">The following code finds the single `Customer` that has the `CustomerID` BONAP.</span></span>  
  
 <span data-ttu-id="38e2d-112">如果您对 Northwind 示例数据库运行此查询，则结果为 `ID = BONAP, Contact = Laurence Lebihan`。</span><span class="sxs-lookup"><span data-stu-id="38e2d-112">If you run this query against the Northwind sample database, the results are `ID = BONAP, Contact = Laurence Lebihan`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#15](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#15)]
 [!code-vb[DLinqQueryExamples#15](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="38e2d-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="38e2d-113">See also</span></span>

- [<span data-ttu-id="38e2d-114">查询示例</span><span class="sxs-lookup"><span data-stu-id="38e2d-114">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="38e2d-115">下载示例数据库</span><span class="sxs-lookup"><span data-stu-id="38e2d-115">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
