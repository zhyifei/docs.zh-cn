---
title: "标准查询运算符概述 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: 302bd39e-2ec1-495b-94bf-37d370d6f05f
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 229b63db761f2a1ed5333fd6f8e4eb9b5c0b75de
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="standard-query-operators-overview-visual-basic"></a><span data-ttu-id="e46ae-102">标准查询运算符概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e46ae-102">Standard Query Operators Overview (Visual Basic)</span></span>
<span data-ttu-id="e46ae-103">*标准查询运算符*是窗体中的 LINQ 模式的方法。</span><span class="sxs-lookup"><span data-stu-id="e46ae-103">The *standard query operators* are the methods that form the LINQ pattern.</span></span> <span data-ttu-id="e46ae-104">这些方法中的大多数作用于序列，其中的序列是其类型实现的对象<xref:System.Collections.Generic.IEnumerable%601>接口或<xref:System.Linq.IQueryable%601>接口。</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="e46ae-104">Most of these methods operate on sequences, where a sequence is an object whose type implements the <xref:System.Collections.Generic.IEnumerable%601> interface or the <xref:System.Linq.IQueryable%601> interface.</span></span> <span data-ttu-id="e46ae-105">标准查询运算符提供了查询功能包括筛选、 投影、 聚合、 排序和的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e46ae-105">The standard query operators provide query capabilities including filtering, projection, aggregation, sorting and more.</span></span>  
  
 <span data-ttu-id="e46ae-106">有两套 LINQ 标准查询运算符，一种类型<xref:System.Collections.Generic.IEnumerable%601>，另一个操作类型<xref:System.Linq.IQueryable%601>。</xref:System.Linq.IQueryable%601>的对象</xref:System.Collections.Generic.IEnumerable%601>的对象上运行</span><span class="sxs-lookup"><span data-stu-id="e46ae-106">There are two sets of LINQ standard query operators, one that operates on objects of type <xref:System.Collections.Generic.IEnumerable%601> and the other that operates on objects of type <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="e46ae-107">构成每个集合的方法是静态成员<xref:System.Linq.Enumerable>和<xref:System.Linq.Queryable>类，分别。</xref:System.Linq.Queryable> </xref:System.Linq.Enumerable></span><span class="sxs-lookup"><span data-stu-id="e46ae-107">The methods that make up each set are static members of the <xref:System.Linq.Enumerable> and <xref:System.Linq.Queryable> classes, respectively.</span></span> <span data-ttu-id="e46ae-108">它们定义为*扩展方法*它们对操作的类型。</span><span class="sxs-lookup"><span data-stu-id="e46ae-108">They are defined as *extension methods* of the type that they operate on.</span></span> <span data-ttu-id="e46ae-109">这意味着可以通过使用静态方法的语法或实例方法语法调用它们。</span><span class="sxs-lookup"><span data-stu-id="e46ae-109">This means that they can be called by using either static method syntax or instance method syntax.</span></span>  
  
 <span data-ttu-id="e46ae-110">此外，多个标准查询运算符方法操作类型而不是基于<xref:System.Collections.Generic.IEnumerable%601>或<xref:System.Linq.IQueryable%601>。</xref:System.Linq.IQueryable%601></xref:System.Collections.Generic.IEnumerable%601>上</span><span class="sxs-lookup"><span data-stu-id="e46ae-110">In addition, several standard query operator methods operate on types other than those based on <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="e46ae-111"><xref:System.Linq.Enumerable>类型定义了两个此类方法的类型<xref:System.Collections.IEnumerable>。</xref:System.Collections.IEnumerable>对象上同时运行</xref:System.Linq.Enumerable></span><span class="sxs-lookup"><span data-stu-id="e46ae-111">The <xref:System.Linq.Enumerable> type defines two such methods that both operate on objects of type <xref:System.Collections.IEnumerable>.</span></span> <span data-ttu-id="e46ae-112">这些方法，<xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29>和<xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29>，可让您启用要在 LINQ 模式中查询的非参数化或非泛型集合。</xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29> </xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29></span><span class="sxs-lookup"><span data-stu-id="e46ae-112">These methods, <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> and <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29>, let you enable a non-parameterized, or non-generic, collection to be queried in the LINQ pattern.</span></span> <span data-ttu-id="e46ae-113">他们通过创建强类型化对象的集合来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e46ae-113">They do this by creating a strongly-typed collection of objects.</span></span> <span data-ttu-id="e46ae-114"><xref:System.Linq.Queryable>类定义了两个类似的方法，<xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29>并且<xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>，针对对象类型<xref:System.Linq.Queryable>。</xref:System.Linq.Queryable>运行</xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29></xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29></xref:System.Linq.Queryable></span><span class="sxs-lookup"><span data-stu-id="e46ae-114">The <xref:System.Linq.Queryable> class defines two similar methods, <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> and <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>, that operate on objects of type <xref:System.Linq.Queryable>.</span></span>  
  
 <span data-ttu-id="e46ae-115">标准查询运算符在其执行，具体取决于它们返回单一实例值或一系列值的时间会有所不同。</span><span class="sxs-lookup"><span data-stu-id="e46ae-115">The standard query operators differ in the timing of their execution, depending on whether they return a singleton value or a sequence of values.</span></span> <span data-ttu-id="e46ae-116">返回单一实例值的那些方法 (例如，<xref:System.Linq.Enumerable.Average%2A>和<xref:System.Linq.Enumerable.Sum%2A>) 将会立即执行。</xref:System.Linq.Enumerable.Sum%2A> </xref:System.Linq.Enumerable.Average%2A></span><span class="sxs-lookup"><span data-stu-id="e46ae-116">Those methods that return a singleton value (for example, <xref:System.Linq.Enumerable.Average%2A> and <xref:System.Linq.Enumerable.Sum%2A>) execute immediately.</span></span> <span data-ttu-id="e46ae-117">延迟查询执行和返回一个可枚举对象返回一系列的方法。</span><span class="sxs-lookup"><span data-stu-id="e46ae-117">Methods that return a sequence defer the query execution and return an enumerable object.</span></span>  
  
 <span data-ttu-id="e46ae-118">在对集合执行运算内存中，即，将扩展这些方法的方法的情况下<xref:System.Collections.Generic.IEnumerable%601>，返回的可枚举对象捕获已传递到方法的参数。</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="e46ae-118">In the case of the methods that operate on in-memory collections, that is, those methods that extend <xref:System.Collections.Generic.IEnumerable%601>, the returned enumerable object captures the arguments that were passed to the method.</span></span> <span data-ttu-id="e46ae-119">当枚举该对象时，使用查询运算符的逻辑，并返回查询结果。</span><span class="sxs-lookup"><span data-stu-id="e46ae-119">When that object is enumerated, the logic of the query operator is employed and the query results are returned.</span></span>  
  
 <span data-ttu-id="e46ae-120">与此相反，用于扩展的方法<xref:System.Linq.IQueryable%601>不实现任何查询行为，但创建表示要执行该查询的表达式树。</xref:System.Linq.IQueryable%601></span><span class="sxs-lookup"><span data-stu-id="e46ae-120">In contrast, methods that extend <xref:System.Linq.IQueryable%601> do not implement any querying behavior, but build an expression tree that represents the query to be performed.</span></span> <span data-ttu-id="e46ae-121">查询处理源<xref:System.Linq.IQueryable%601>对象。</xref:System.Linq.IQueryable%601></span><span class="sxs-lookup"><span data-stu-id="e46ae-121">The query processing is handled by the source <xref:System.Linq.IQueryable%601> object.</span></span>  
  
 <span data-ttu-id="e46ae-122">对查询方法的调用可以链接在一起在一个查询中，这就使得查询变得很复杂。</span><span class="sxs-lookup"><span data-stu-id="e46ae-122">Calls to query methods can be chained together in one query, which enables queries to become arbitrarily complex.</span></span>  
  
 <span data-ttu-id="e46ae-123">下面的代码示例演示如何使用标准查询运算符来获取有关序列的信息。</span><span class="sxs-lookup"><span data-stu-id="e46ae-123">The following code example demonstrates how the standard query operators can be used to obtain information about a sequence.</span></span>  
  
```vb  
Dim sentence = "the quick brown fox jumps over the lazy dog"  
' Split the string into individual words to create a collection.  
Dim words = sentence.Split(" "c)  
  
Dim query = From word In words   
            Group word.ToUpper() By word.Length Into gr = Group   
            Order By Length _  
            Select Length, GroupedWords = gr  
  
Dim output As New System.Text.StringBuilder  
For Each obj In query  
    output.AppendLine(String.Format("Words of length {0}:", obj.Length))  
    For Each word As String In obj.GroupedWords  
        output.AppendLine(word)  
    Next  
Next  
  
'Display the output  
MsgBox(output.ToString())  
  
' This code example produces the following output:  
'  
' Words of length 3:  
' THE  
' FOX  
' THE  
' DOG  
' Words of length 4:  
' OVER  
' LAZY  
' Words of length 5:  
' QUICK  
' BROWN  
' JUMPS   
```  
  
## <a name="query-expression-syntax"></a><span data-ttu-id="e46ae-124">查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="e46ae-124">Query Expression Syntax</span></span>  
 <span data-ttu-id="e46ae-125">一些经常使用的标准查询运算符包含专用使他们能够作为的一部分调用的 C# 和 Visual Basic 语言关键字语法*查询**表达式*。</span><span class="sxs-lookup"><span data-stu-id="e46ae-125">Some of the more frequently used standard query operators have dedicated C# and Visual Basic language keyword syntax that enables them to be called as part of a *query* *expression*.</span></span> <span data-ttu-id="e46ae-126">有关具有专用的关键字和其对应的语法的标准查询运算符的详细信息，请参阅[标准查询运算符 (Visual Basic 中) 的查询表达式语法](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md)。</span><span class="sxs-lookup"><span data-stu-id="e46ae-126">For more information about standard query operators that have dedicated keywords and their corresponding syntaxes, see [Query Expression Syntax for Standard Query Operators (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md).</span></span>  
  
## <a name="extending-the-standard-query-operators"></a><span data-ttu-id="e46ae-127">扩展标准查询运算符</span><span class="sxs-lookup"><span data-stu-id="e46ae-127">Extending the Standard Query Operators</span></span>  
 <span data-ttu-id="e46ae-128">您可以通过创建适合于目标域或技术的特定于域的方法扩展的一套标准查询运算符。</span><span class="sxs-lookup"><span data-stu-id="e46ae-128">You can augment the set of standard query operators by creating domain-specific methods that are appropriate for your target domain or technology.</span></span> <span data-ttu-id="e46ae-129">您还可以用您自己提供其他服务，如远程评估、 查询转换和优化的实现替换标准查询运算符。</span><span class="sxs-lookup"><span data-stu-id="e46ae-129">You can also replace the standard query operators with your own implementations that provide additional services such as remote evaluation, query translation, and optimization.</span></span> <span data-ttu-id="e46ae-130">请参阅<xref:System.Linq.Enumerable.AsEnumerable%2A>以举例。</xref:System.Linq.Enumerable.AsEnumerable%2A></span><span class="sxs-lookup"><span data-stu-id="e46ae-130">See <xref:System.Linq.Enumerable.AsEnumerable%2A> for an example.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e46ae-131">相关章节</span><span class="sxs-lookup"><span data-stu-id="e46ae-131">Related Sections</span></span>  
 <span data-ttu-id="e46ae-132">以下链接可转至主题提供了有关各种基于功能的标准查询运算符的其他信息。</span><span class="sxs-lookup"><span data-stu-id="e46ae-132">The following links take you to topics that provide additional information about the various standard query operators based on functionality.</span></span>  
  
 [<span data-ttu-id="e46ae-133">对数据进行排序</span><span class="sxs-lookup"><span data-stu-id="e46ae-133">Sorting Data</span></span>](../../../../visual-basic/programming-guide/concepts/linq/sorting-data.md)  
  
 [<span data-ttu-id="e46ae-134">Set 运算 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e46ae-134">Set Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/set-operations.md)  
  
 [<span data-ttu-id="e46ae-135">筛选数据 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e46ae-135">Filtering Data (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/filtering-data.md)  
  
 [<span data-ttu-id="e46ae-136">限定符操作 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e46ae-136">Quantifier Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md)  
  
 [<span data-ttu-id="e46ae-137">投影运算 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e46ae-137">Projection Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)  
  
 [<span data-ttu-id="e46ae-138">分区数据 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e46ae-138">Partitioning Data (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/partitioning-data.md)  
  
 [<span data-ttu-id="e46ae-139">联接操作 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e46ae-139">Join Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/join-operations.md)  
  
 [<span data-ttu-id="e46ae-140">对数据进行分组 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e46ae-140">Grouping Data (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/grouping-data.md)  
  
 [<span data-ttu-id="e46ae-141">生成操作 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e46ae-141">Generation Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/generation-operations.md)  
  
 [<span data-ttu-id="e46ae-142">相等运算 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e46ae-142">Equality Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/equality-operations.md)  
  
 [<span data-ttu-id="e46ae-143">元素操作 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e46ae-143">Element Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/element-operations.md)  
  
 [<span data-ttu-id="e46ae-144">转换数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e46ae-144">Converting Data Types (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md)  
  
 [<span data-ttu-id="e46ae-145">串联运算 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e46ae-145">Concatenation Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/concatenation-operations.md)  
  
 [<span data-ttu-id="e46ae-146">聚合操作 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e46ae-146">Aggregation Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/aggregation-operations.md)  
  
## <a name="see-also"></a><span data-ttu-id="e46ae-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e46ae-147">See Also</span></span>  
 <span data-ttu-id="e46ae-148"><xref:System.Linq.Enumerable></xref:System.Linq.Enumerable></span><span class="sxs-lookup"><span data-stu-id="e46ae-148"><xref:System.Linq.Enumerable></span></span>   
 <span data-ttu-id="e46ae-149"><xref:System.Linq.Queryable></xref:System.Linq.Queryable></span><span class="sxs-lookup"><span data-stu-id="e46ae-149"><xref:System.Linq.Queryable></span></span>   
<span data-ttu-id="e46ae-150"> [(Visual Basic 中) 的 LINQ 简介](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md) </span><span class="sxs-lookup"><span data-stu-id="e46ae-150"> [Introduction to LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md) </span></span>  
<span data-ttu-id="e46ae-151"> [标准查询运算符 (Visual Basic 中) 的查询表达式语法](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md) </span><span class="sxs-lookup"><span data-stu-id="e46ae-151"> [Query Expression Syntax for Standard Query Operators (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md) </span></span>  
<span data-ttu-id="e46ae-152"> [标准查询运算符按执行 (Visual Basic 中) 的方式的分类](../../../../visual-basic/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md) </span><span class="sxs-lookup"><span data-stu-id="e46ae-152"> [Classification of Standard Query Operators by Manner of Execution (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md) </span></span>  
<span data-ttu-id="e46ae-153"> [扩展方法](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)</span><span class="sxs-lookup"><span data-stu-id="e46ae-153"> [Extension Methods](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)</span></span>
