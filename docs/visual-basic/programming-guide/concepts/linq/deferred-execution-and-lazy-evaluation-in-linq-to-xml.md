---
title: "延迟执行和迟缓计算 LINQ to XML (Visual Basic 中) 中的 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 31998eed-b95e-47fb-a865-9de1f337d1fb
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9ecb4d18cf7c61442e17de1c0f08824b360362e1
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017


---
# <a name="deferred-execution-and-lazy-evaluation-in-linq-to-xml-visual-basic"></a><span data-ttu-id="e570b-102">延迟的执行和迟缓计算在 LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e570b-102">Deferred Execution and Lazy Evaluation in LINQ to XML (Visual Basic)</span></span>
<span data-ttu-id="e570b-103">实现查询和轴操作通常是为了使用延迟执行。</span><span class="sxs-lookup"><span data-stu-id="e570b-103">Query and axis operations are often implemented to use deferred execution.</span></span> <span data-ttu-id="e570b-104">本主题解释延迟执行的要求和优点，以及某些实现注意事项。</span><span class="sxs-lookup"><span data-stu-id="e570b-104">This topic explains the requirements and advantages of deferred execution, and some implementation considerations.</span></span>  
  
## <a name="deferred-execution"></a><span data-ttu-id="e570b-105">延迟执行</span><span class="sxs-lookup"><span data-stu-id="e570b-105">Deferred Execution</span></span>  
 <span data-ttu-id="e570b-106">延迟执行意味着表达式的计算延迟，直到其*意识到*，则实际上需要值。</span><span class="sxs-lookup"><span data-stu-id="e570b-106">Deferred execution means that the evaluation of an expression is delayed until its *realized* value is actually required.</span></span> <span data-ttu-id="e570b-107">当必须操作大型数据集合，特别是在包含一系列链接的查询或操作的程序中操作时，延迟执行可以大大改善性能。</span><span class="sxs-lookup"><span data-stu-id="e570b-107">Deferred execution can greatly improve performance when you have to manipulate large data collections, especially in programs that contain a series of chained queries or manipulations.</span></span> <span data-ttu-id="e570b-108">在最佳情况下，延迟执行只允许对源集合的单个循环访问。</span><span class="sxs-lookup"><span data-stu-id="e570b-108">In the best case, deferred execution enables only a single iteration through the source collection.</span></span>  
  
 <span data-ttu-id="e570b-109">LINQ 技术广泛利用延迟执行这两个成员中的核心<xref:System.Linq?displayProperty=fullName>类和不同 LINQ 命名空间，如<xref:System.Xml.Linq.Extensions?displayProperty=fullName>。</xref:System.Xml.Linq.Extensions?displayProperty=fullName>中的扩展方法</xref:System.Linq?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e570b-109">The LINQ technologies make extensive use of deferred execution in both the members of core <xref:System.Linq?displayProperty=fullName> classes and in the extension methods in the various LINQ namespaces, such as <xref:System.Xml.Linq.Extensions?displayProperty=fullName>.</span></span>  
  
## <a name="eager-vs-lazy-evaluation"></a><span data-ttu-id="e570b-110">积极计算与迟缓计算</span><span class="sxs-lookup"><span data-stu-id="e570b-110">Eager vs. Lazy Evaluation</span></span>  
 <span data-ttu-id="e570b-111">当您编写实现延迟执行的方法时，还必须确定是使用迟缓计算还是积极计算来实现该方法。</span><span class="sxs-lookup"><span data-stu-id="e570b-111">When you write a method that implements deferred execution, you also have to decide whether to implement the method using lazy evaluation or eager evaluation.</span></span>  
  
-   <span data-ttu-id="e570b-112">在*迟缓计算*，在每次调用迭代器处理源集合的一个元素。</span><span class="sxs-lookup"><span data-stu-id="e570b-112">In *lazy evaluation*, a single element of the source collection is processed during each call to the iterator.</span></span> <span data-ttu-id="e570b-113">这是实现迭代器的典型方式。</span><span class="sxs-lookup"><span data-stu-id="e570b-113">This is the typical way in which iterators are implemented.</span></span>  
  
-   <span data-ttu-id="e570b-114">在*热情计算*，首次调用迭代器，则会在整个集合进行处理。</span><span class="sxs-lookup"><span data-stu-id="e570b-114">In *eager evaluation*, the first call to the iterator will result in the entire collection being processed.</span></span> <span data-ttu-id="e570b-115">还可能需要源集合的临时副本。</span><span class="sxs-lookup"><span data-stu-id="e570b-115">A temporary copy of the source collection might also be required.</span></span> <span data-ttu-id="e570b-116">例如，<xref:System.Linq.Enumerable.OrderBy%2A>方法必须返回第一个元素前对整个集合进行排序。</xref:System.Linq.Enumerable.OrderBy%2A></span><span class="sxs-lookup"><span data-stu-id="e570b-116">For example, the <xref:System.Linq.Enumerable.OrderBy%2A> method has to sort the entire collection before it returns the first element.</span></span>  
  
 <span data-ttu-id="e570b-117">迟缓计算通常产生更好的性能，因为它将系统开销处理平均分配到整个集合的计算中，并将临时数据的使用降至最低。</span><span class="sxs-lookup"><span data-stu-id="e570b-117">Lazy evaluation usually yields better performance because it distributes overhead processing evenly throughout the evaluation of the collection and minimizes the use of temporary data.</span></span> <span data-ttu-id="e570b-118">当然，对于某些操作，除了具体化中间结果之外，再没有其他选择。</span><span class="sxs-lookup"><span data-stu-id="e570b-118">Of course, for some operations, there is no other option than to materialize intermediate results.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e570b-119">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e570b-119">Next Steps</span></span>  
 <span data-ttu-id="e570b-120">本教程的下一个主题将解释延迟执行：</span><span class="sxs-lookup"><span data-stu-id="e570b-120">The next topic in this tutorial illustrates deferred execution:</span></span>  
  
-   [<span data-ttu-id="e570b-121">延迟的执行示例 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e570b-121">Deferred Execution Example (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-example.md)  
  
## <a name="see-also"></a><span data-ttu-id="e570b-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e570b-122">See Also</span></span>  
 <span data-ttu-id="e570b-123">[教程︰ 延迟执行 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md) </span><span class="sxs-lookup"><span data-stu-id="e570b-123">[Tutorial: Deferred Execution (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md) </span></span>  
<span data-ttu-id="e570b-124"> [概念和术语 （功能转换） (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/concepts-and-terminology-functional-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="e570b-124"> [Concepts and Terminology (Functional Transformation) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/concepts-and-terminology-functional-transformation.md) </span></span>  
<span data-ttu-id="e570b-125"> [聚合操作 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/aggregation-operations.md)</span><span class="sxs-lookup"><span data-stu-id="e570b-125"> [Aggregation Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/aggregation-operations.md)</span></span>
