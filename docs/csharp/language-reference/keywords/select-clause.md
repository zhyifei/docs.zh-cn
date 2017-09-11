---
title: "select 子句（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- select_CSharpKeyword
- select
dev_langs:
- CSharp
helpviewer_keywords:
- select keyword [C#]
- select clause [C#]
ms.assetid: df01e266-5781-4aaa-80c4-67cf28ea093f
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a505399eb79cbecbefcc53953329279a4abd92f6
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="select-clause-c-reference"></a><span data-ttu-id="e6435-102">select 子句（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="e6435-102">select clause (C# Reference)</span></span>
<span data-ttu-id="e6435-103">在查询表达式中，`select` 子句指定在执行查询时产生的值的类型。</span><span class="sxs-lookup"><span data-stu-id="e6435-103">In a query expression, the `select` clause specifies the type of values that will be produced when the query is executed.</span></span> <span data-ttu-id="e6435-104">根据计算所有以前的子句以及根据 `select` 子句本身的所有表达式得出结果。</span><span class="sxs-lookup"><span data-stu-id="e6435-104">The result is based on the evaluation of all the previous clauses and on any expressions in the `select` clause itself.</span></span> <span data-ttu-id="e6435-105">查询表达式必须以 `select` 子句或 [group](../../../csharp/language-reference/keywords/group-clause.md) 子句结尾。</span><span class="sxs-lookup"><span data-stu-id="e6435-105">A query expression must terminate with either a `select` clause or a [group](../../../csharp/language-reference/keywords/group-clause.md) clause.</span></span>  
  
 <span data-ttu-id="e6435-106">以下示例演示查询表达式中的简单的 `select` 子句。</span><span class="sxs-lookup"><span data-stu-id="e6435-106">The following example shows a simple `select` clause in a query expression.</span></span>  
  
 <span data-ttu-id="e6435-107">[!code-cs[cscsrefQueryKeywords#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e6435-107">[!code-cs[cscsrefQueryKeywords#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_1.cs)]</span></span>  
  
 <span data-ttu-id="e6435-108">`select` 子句生成的序列的类型确定查询变量 `queryHighScores` 的类型。</span><span class="sxs-lookup"><span data-stu-id="e6435-108">The type of the sequence produced by the `select` clause determines the type of the query variable `queryHighScores`.</span></span> <span data-ttu-id="e6435-109">在最简单的情况下，`select` 子句仅指定范围变量。</span><span class="sxs-lookup"><span data-stu-id="e6435-109">In the simplest case, the `select` clause just specifies the range variable.</span></span> <span data-ttu-id="e6435-110">这将导致返回的序列包含与数据源类型相同的元素。</span><span class="sxs-lookup"><span data-stu-id="e6435-110">This causes the returned sequence to contain elements of the same type as the data source.</span></span> <span data-ttu-id="e6435-111">有关详细信息，请参阅 [LINQ 查询操作中的类型关系](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="e6435-111">For more information, see [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span> <span data-ttu-id="e6435-112">但是，`select` 子句还提供了强大的机制，用于将源数据转换（或投影）为新类型。</span><span class="sxs-lookup"><span data-stu-id="e6435-112">However, the `select` clause also provides a powerful mechanism for transforming (or *projecting*) source data into new types.</span></span> <span data-ttu-id="e6435-113">有关详细信息，请参阅[使用 LINQ 进行数据转换 (C#)](../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)。</span><span class="sxs-lookup"><span data-stu-id="e6435-113">For more information, see [Data Transformations with LINQ (C#)](../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6435-114">示例</span><span class="sxs-lookup"><span data-stu-id="e6435-114">Example</span></span>  
 <span data-ttu-id="e6435-115">以下示例展示 `select` 子句可能采用的所有不同窗体。</span><span class="sxs-lookup"><span data-stu-id="e6435-115">The following example shows all the different forms that a `select` clause may take.</span></span> <span data-ttu-id="e6435-116">在每个查询中，请注意 `select` 子句和查询变量（`studentQuery1`、`studentQuery2` 等）类型之间的关系。</span><span class="sxs-lookup"><span data-stu-id="e6435-116">In each query, note the relationship between the `select` clause and the type of the *query variable* (`studentQuery1`, `studentQuery2`, and so on).</span></span>  
  
 <span data-ttu-id="e6435-117">[!code-cs[cscsrefQueryKeywords#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="e6435-117">[!code-cs[cscsrefQueryKeywords#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_2.cs)]</span></span>  
  
 <span data-ttu-id="e6435-118">如前面示例中的 `studentQuery8` 所示，有时可能想要返回序列的元素仅包含一部分源元素属性。</span><span class="sxs-lookup"><span data-stu-id="e6435-118">As shown in `studentQuery8` in the previous example, sometimes you might want the elements of the returned sequence to contain only a subset of the properties of the source elements.</span></span> <span data-ttu-id="e6435-119">通过让返回序列尽可能变小，可以减少内存需求并提高执行查询的速度。</span><span class="sxs-lookup"><span data-stu-id="e6435-119">By keeping the returned sequence as small as possible you can reduce the memory requirements and increase the speed of the execution of the query.</span></span> <span data-ttu-id="e6435-120">在 `select` 子句中创建匿名类型并使用对象初始值设定项通过源元素中的相应属性初始化该类型可以完成此操作。</span><span class="sxs-lookup"><span data-stu-id="e6435-120">You can accomplish this by creating an anonymous type in the `select` clause and using an object initializer to initialize it with the appropriate properties from the source element.</span></span> <span data-ttu-id="e6435-121">有关如何执行此操作的示例，请参阅[对象和集合初始值设定项](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)。</span><span class="sxs-lookup"><span data-stu-id="e6435-121">For an example of how to do this, see [Object and Collection Initializers](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6435-122">备注</span><span class="sxs-lookup"><span data-stu-id="e6435-122">Remarks</span></span>  
 <span data-ttu-id="e6435-123">在编译时，`select` 子句被转换为 <xref:System.Linq.Enumerable.Select%2A> 标准查询运算符的方法调用。</span><span class="sxs-lookup"><span data-stu-id="e6435-123">At compile time, the `select` clause is translated to a method call to the <xref:System.Linq.Enumerable.Select%2A> standard query operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6435-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6435-124">See Also</span></span>  
 <span data-ttu-id="e6435-125">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e6435-125">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e6435-126">[查询关键字 (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="e6435-126">[Query Keywords (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span></span>  
 <span data-ttu-id="e6435-127">[from 子句](../../../csharp/language-reference/keywords/from-clause.md) </span><span class="sxs-lookup"><span data-stu-id="e6435-127">[from clause](../../../csharp/language-reference/keywords/from-clause.md) </span></span>  
 <span data-ttu-id="e6435-128">[分部（方法）（C# 参考）](../../../csharp/language-reference/keywords/partial-method.md) </span><span class="sxs-lookup"><span data-stu-id="e6435-128">[partial (Method) (C# Reference)](../../../csharp/language-reference/keywords/partial-method.md) </span></span>  
 <span data-ttu-id="e6435-129">[匿名类型](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="e6435-129">[Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span></span>  
 <span data-ttu-id="e6435-130">[LINQ 查询表达式](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="e6435-130">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 [<span data-ttu-id="e6435-131">C# 中的 LINQ 入门</span><span class="sxs-lookup"><span data-stu-id="e6435-131">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

