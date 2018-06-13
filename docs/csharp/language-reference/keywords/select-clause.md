---
title: select 子句（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- select_CSharpKeyword
- select
helpviewer_keywords:
- select keyword [C#]
- select clause [C#]
ms.assetid: df01e266-5781-4aaa-80c4-67cf28ea093f
ms.openlocfilehash: 6e7277b5d714e48059fe1ed7e8b85e46a14a840c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33279979"
---
# <a name="select-clause-c-reference"></a><span data-ttu-id="56fa2-102">select 子句（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="56fa2-102">select clause (C# Reference)</span></span>
<span data-ttu-id="56fa2-103">在查询表达式中，`select` 子句指定在执行查询时产生的值的类型。</span><span class="sxs-lookup"><span data-stu-id="56fa2-103">In a query expression, the `select` clause specifies the type of values that will be produced when the query is executed.</span></span> <span data-ttu-id="56fa2-104">根据计算所有以前的子句以及根据 `select` 子句本身的所有表达式得出结果。</span><span class="sxs-lookup"><span data-stu-id="56fa2-104">The result is based on the evaluation of all the previous clauses and on any expressions in the `select` clause itself.</span></span> <span data-ttu-id="56fa2-105">查询表达式必须以 `select` 子句或 [group](../../../csharp/language-reference/keywords/group-clause.md) 子句结尾。</span><span class="sxs-lookup"><span data-stu-id="56fa2-105">A query expression must terminate with either a `select` clause or a [group](../../../csharp/language-reference/keywords/group-clause.md) clause.</span></span>  
  
 <span data-ttu-id="56fa2-106">以下示例演示查询表达式中的简单的 `select` 子句。</span><span class="sxs-lookup"><span data-stu-id="56fa2-106">The following example shows a simple `select` clause in a query expression.</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_1.cs)]  
  
 <span data-ttu-id="56fa2-107">`select` 子句生成的序列的类型确定查询变量 `queryHighScores` 的类型。</span><span class="sxs-lookup"><span data-stu-id="56fa2-107">The type of the sequence produced by the `select` clause determines the type of the query variable `queryHighScores`.</span></span> <span data-ttu-id="56fa2-108">在最简单的情况下，`select` 子句仅指定范围变量。</span><span class="sxs-lookup"><span data-stu-id="56fa2-108">In the simplest case, the `select` clause just specifies the range variable.</span></span> <span data-ttu-id="56fa2-109">这将导致返回的序列包含与数据源类型相同的元素。</span><span class="sxs-lookup"><span data-stu-id="56fa2-109">This causes the returned sequence to contain elements of the same type as the data source.</span></span> <span data-ttu-id="56fa2-110">有关详细信息，请参阅 [LINQ 查询操作中的类型关系](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="56fa2-110">For more information, see [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span> <span data-ttu-id="56fa2-111">但是，`select` 子句还提供了强大的机制，用于将源数据转换（或投影）为新类型。</span><span class="sxs-lookup"><span data-stu-id="56fa2-111">However, the `select` clause also provides a powerful mechanism for transforming (or *projecting*) source data into new types.</span></span> <span data-ttu-id="56fa2-112">有关详细信息，请参阅[使用 LINQ 进行数据转换 (C#)](../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)。</span><span class="sxs-lookup"><span data-stu-id="56fa2-112">For more information, see [Data Transformations with LINQ (C#)](../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="56fa2-113">示例</span><span class="sxs-lookup"><span data-stu-id="56fa2-113">Example</span></span>  
 <span data-ttu-id="56fa2-114">以下示例展示 `select` 子句可能采用的所有不同窗体。</span><span class="sxs-lookup"><span data-stu-id="56fa2-114">The following example shows all the different forms that a `select` clause may take.</span></span> <span data-ttu-id="56fa2-115">在每个查询中，请注意 `select` 子句和查询变量（`studentQuery1`、`studentQuery2` 等）类型之间的关系。</span><span class="sxs-lookup"><span data-stu-id="56fa2-115">In each query, note the relationship between the `select` clause and the type of the *query variable* (`studentQuery1`, `studentQuery2`, and so on).</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_2.cs)]  
  
 <span data-ttu-id="56fa2-116">如前面示例中的 `studentQuery8` 所示，有时可能想要返回序列的元素仅包含一部分源元素属性。</span><span class="sxs-lookup"><span data-stu-id="56fa2-116">As shown in `studentQuery8` in the previous example, sometimes you might want the elements of the returned sequence to contain only a subset of the properties of the source elements.</span></span> <span data-ttu-id="56fa2-117">通过让返回序列尽可能变小，可以减少内存需求并提高执行查询的速度。</span><span class="sxs-lookup"><span data-stu-id="56fa2-117">By keeping the returned sequence as small as possible you can reduce the memory requirements and increase the speed of the execution of the query.</span></span> <span data-ttu-id="56fa2-118">在 `select` 子句中创建匿名类型并使用对象初始值设定项通过源元素中的相应属性初始化该类型可以完成此操作。</span><span class="sxs-lookup"><span data-stu-id="56fa2-118">You can accomplish this by creating an anonymous type in the `select` clause and using an object initializer to initialize it with the appropriate properties from the source element.</span></span> <span data-ttu-id="56fa2-119">有关如何执行此操作的示例，请参阅[对象和集合初始值设定项](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)。</span><span class="sxs-lookup"><span data-stu-id="56fa2-119">For an example of how to do this, see [Object and Collection Initializers](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56fa2-120">备注</span><span class="sxs-lookup"><span data-stu-id="56fa2-120">Remarks</span></span>  
 <span data-ttu-id="56fa2-121">在编译时，`select` 子句被转换为 <xref:System.Linq.Enumerable.Select%2A> 标准查询运算符的方法调用。</span><span class="sxs-lookup"><span data-stu-id="56fa2-121">At compile time, the `select` clause is translated to a method call to the <xref:System.Linq.Enumerable.Select%2A> standard query operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56fa2-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="56fa2-122">See Also</span></span>  
 [<span data-ttu-id="56fa2-123">C# 参考</span><span class="sxs-lookup"><span data-stu-id="56fa2-123">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="56fa2-124">查询关键字 (LINQ)</span><span class="sxs-lookup"><span data-stu-id="56fa2-124">Query Keywords (LINQ)</span></span>](../../../csharp/language-reference/keywords/query-keywords.md)  
 [<span data-ttu-id="56fa2-125">from 子句</span><span class="sxs-lookup"><span data-stu-id="56fa2-125">from clause</span></span>](../../../csharp/language-reference/keywords/from-clause.md)  
 [<span data-ttu-id="56fa2-126">分部（方法）（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="56fa2-126">partial (Method) (C# Reference)</span></span>](../../../csharp/language-reference/keywords/partial-method.md)  
 [<span data-ttu-id="56fa2-127">匿名类型</span><span class="sxs-lookup"><span data-stu-id="56fa2-127">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)  
 [<span data-ttu-id="56fa2-128">LINQ 查询表达式</span><span class="sxs-lookup"><span data-stu-id="56fa2-128">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="56fa2-129">C# 中的 LINQ 入门</span><span class="sxs-lookup"><span data-stu-id="56fa2-129">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
