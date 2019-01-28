---
title: LINQ 和泛型类型 (C#)
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], generic types
- generic types [LINQ]
- generics [LINQ]
ms.assetid: 660e3799-25ca-462c-8c4a-8bce04fbb031
ms.openlocfilehash: 02540db02d8e413ec254c0642d106ca41b263376
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662512"
---
# <a name="linq-and-generic-types-c"></a><span data-ttu-id="b73fc-102">LINQ 和泛型类型 (C#)</span><span class="sxs-lookup"><span data-stu-id="b73fc-102">LINQ and Generic Types (C#)</span></span>
[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] <span data-ttu-id="b73fc-103">查询基于 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 2.0 版中引入的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="b73fc-103">queries are based on generic types, which were introduced in version 2.0 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="b73fc-104">无需深入了解泛型即可开始编写查询。</span><span class="sxs-lookup"><span data-stu-id="b73fc-104">You do not need an in-depth knowledge of generics before you can start writing queries.</span></span> <span data-ttu-id="b73fc-105">但是，可能需要了解 2 个基本概念：</span><span class="sxs-lookup"><span data-stu-id="b73fc-105">However, you may want to understand two basic concepts:</span></span>  
  
1.  <span data-ttu-id="b73fc-106">创建泛型集合类（如 <xref:System.Collections.Generic.List%601>）的实例时，需将“T”替换为列表将包含的对象类型。</span><span class="sxs-lookup"><span data-stu-id="b73fc-106">When you create an instance of a generic collection class such as <xref:System.Collections.Generic.List%601>, you replace the "T" with the type of objects that the list will hold.</span></span> <span data-ttu-id="b73fc-107">例如，字符串列表表示为 `List<string>`，`Customer` 对象列表表示为 `List<Customer>`。</span><span class="sxs-lookup"><span data-stu-id="b73fc-107">For example, a list of strings is expressed as `List<string>`, and a list of `Customer` objects is expressed as `List<Customer>`.</span></span> <span data-ttu-id="b73fc-108">泛型列表属于强类型，与将其元素存储为 <xref:System.Object> 的集合相比，泛型列表具备更多优势。</span><span class="sxs-lookup"><span data-stu-id="b73fc-108">A generic list is strongly typed and provides many benefits over collections that store their elements as <xref:System.Object>.</span></span> <span data-ttu-id="b73fc-109">如果尝试将 `Customer` 添加到 `List<string>`，则会在编译时收到错误。</span><span class="sxs-lookup"><span data-stu-id="b73fc-109">If you try to add a `Customer` to a `List<string>`, you will get an error at compile time.</span></span> <span data-ttu-id="b73fc-110">泛型集合易于使用的原因是不必执行运行时类型转换。</span><span class="sxs-lookup"><span data-stu-id="b73fc-110">It is easy to use generic collections because you do not have to perform run-time type-casting.</span></span>  
  
2.  <span data-ttu-id="b73fc-111"><xref:System.Collections.Generic.IEnumerable%601> 是一个接口，通过该接口，可以使用 `foreach` 语句来枚举泛型集合类。</span><span class="sxs-lookup"><span data-stu-id="b73fc-111"><xref:System.Collections.Generic.IEnumerable%601> is the interface that enables generic collection classes to be enumerated by using the `foreach` statement.</span></span> <span data-ttu-id="b73fc-112">泛型集合类支持 <xref:System.Collections.Generic.IEnumerable%601>，正如非泛型集合类（如 <xref:System.Collections.ArrayList>）支持 <xref:System.Collections.IEnumerable>。</span><span class="sxs-lookup"><span data-stu-id="b73fc-112">Generic collection classes support <xref:System.Collections.Generic.IEnumerable%601> just as non-generic collection classes such as <xref:System.Collections.ArrayList> support <xref:System.Collections.IEnumerable>.</span></span>  
  
 <span data-ttu-id="b73fc-113">有关泛型的详细信息，请参阅[泛型](../../../../csharp/programming-guide/generics/index.md)。</span><span class="sxs-lookup"><span data-stu-id="b73fc-113">For more information about generics, see [Generics](../../../../csharp/programming-guide/generics/index.md).</span></span>  
  
## <a name="ienumerablet-variables-in-linq-queries"></a><span data-ttu-id="b73fc-114">LINQ 查询中的 IEnumerable<T\> 变量</span><span class="sxs-lookup"><span data-stu-id="b73fc-114">IEnumerable<T\> variables in LINQ Queries</span></span>  
 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] <span data-ttu-id="b73fc-115">查询变量被类型化为 <xref:System.Collections.Generic.IEnumerable%601> 或者派生类型（如 <xref:System.Linq.IQueryable%601>）。</span><span class="sxs-lookup"><span data-stu-id="b73fc-115">query variables are typed as <xref:System.Collections.Generic.IEnumerable%601> or a derived type such as <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="b73fc-116">看到类型化为 `IEnumerable<Customer>` 的查询变量时，这只意味着执行查询时，该查询将生成包含零个或多个 `Customer` 对象的序列。</span><span class="sxs-lookup"><span data-stu-id="b73fc-116">When you see a query variable that is typed as `IEnumerable<Customer>`, it just means that the query, when it is executed, will produce a sequence of zero or more `Customer` objects.</span></span>  
  
 [!code-csharp[csLINQGettingStarted#34](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/linq-and-generic-types_1.cs)]  
  
 <span data-ttu-id="b73fc-117">有关详细信息，请参阅 [LINQ 查询操作中的类型关系](../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="b73fc-117">For more information, see [Type Relationships in LINQ Query Operations](../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span>  
  
## <a name="letting-the-compiler-handle-generic-type-declarations"></a><span data-ttu-id="b73fc-118">让编译器处理泛型类型声明</span><span class="sxs-lookup"><span data-stu-id="b73fc-118">Letting the Compiler Handle Generic Type Declarations</span></span>  
 <span data-ttu-id="b73fc-119">如果愿意，可以使用 [var](../../../../csharp/language-reference/keywords/var.md) 关键字来避免使用泛型语法。</span><span class="sxs-lookup"><span data-stu-id="b73fc-119">If you prefer, you can avoid generic syntax by using the [var](../../../../csharp/language-reference/keywords/var.md) keyword.</span></span> <span data-ttu-id="b73fc-120">`var` 关键字指示编译器通过查看在 `from` 子句中指定的数据源来推断查询变量的类型。</span><span class="sxs-lookup"><span data-stu-id="b73fc-120">The `var` keyword instructs the compiler to infer the type of a query variable by looking at the data source specified in the `from` clause.</span></span> <span data-ttu-id="b73fc-121">以下示例生成与上例相同的编译代码：</span><span class="sxs-lookup"><span data-stu-id="b73fc-121">The following example produces the same compiled code as the previous example:</span></span>  
  
 [!code-csharp[csLINQGettingStarted#35](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/linq-and-generic-types_2.cs)]  
  
 <span data-ttu-id="b73fc-122">变量的类型明显或显式指定嵌套泛型类型（如由组查询生成的那些类型）并不重要时，`var` 关键字很有用。</span><span class="sxs-lookup"><span data-stu-id="b73fc-122">The `var` keyword is useful when the type of the variable is obvious or when it is not that important to explicitly specify nested generic types such as those that are produced by group queries.</span></span> <span data-ttu-id="b73fc-123">通常，我们建议如果使用 `var`，应意识到这可能使他人更难以理解代码。</span><span class="sxs-lookup"><span data-stu-id="b73fc-123">In general, we recommend that if you use `var`, realize that it can make your code more difficult for others to read.</span></span> <span data-ttu-id="b73fc-124">有关详细信息，请参阅[隐式类型局部变量](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)。</span><span class="sxs-lookup"><span data-stu-id="b73fc-124">For more information, see [Implicitly Typed Local Variables](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b73fc-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="b73fc-125">See also</span></span>

- [<span data-ttu-id="b73fc-126">C# 中的 LINQ 入门</span><span class="sxs-lookup"><span data-stu-id="b73fc-126">Getting Started with LINQ in C#</span></span>](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="b73fc-127">泛型</span><span class="sxs-lookup"><span data-stu-id="b73fc-127">Generics</span></span>](../../../../csharp/programming-guide/generics/index.md)
