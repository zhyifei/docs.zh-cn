---
title: 隐式类型的局部变量（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- implicitly-typed local variables [C#]
- var [C#]
ms.assetid: b9218fb2-ef5d-4814-8a8e-2bc29b0bbc9b
ms.openlocfilehash: c6c2bae39764e78fad2510bbc8937b0ac790bef5
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172001"
---
# <a name="implicitly-typed-local-variables-c-programming-guide"></a><span data-ttu-id="34a5c-102">隐式类型的局部变量（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="34a5c-102">Implicitly Typed Local Variables (C# Programming Guide)</span></span>
<span data-ttu-id="34a5c-103">可声明局部变量而无需提供显式类型。</span><span class="sxs-lookup"><span data-stu-id="34a5c-103">Local variables can be declared without giving an explicit type.</span></span> <span data-ttu-id="34a5c-104">`var` 关键字指示编译器通过初始化语句右侧的表达式推断变量的类型。</span><span class="sxs-lookup"><span data-stu-id="34a5c-104">The `var` keyword instructs the compiler to infer the type of the variable from the expression on the right side of the initialization statement.</span></span> <span data-ttu-id="34a5c-105">推断类型可以是内置类型、匿名类型、用户定义类型或 .NET Framework 类库中定义的类型。</span><span class="sxs-lookup"><span data-stu-id="34a5c-105">The inferred type may be a built-in type, an anonymous type, a user-defined type, or a type defined in the .NET Framework class library.</span></span> <span data-ttu-id="34a5c-106">有关如何使用 `var` 初始化数组的详细信息，请参阅[隐式类型化数组](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md)。</span><span class="sxs-lookup"><span data-stu-id="34a5c-106">For more information about how to initialize arrays with `var`, see [Implicitly Typed Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span></span>  
  
 <span data-ttu-id="34a5c-107">以下示例演示使用 `var` 声明局部变量的各种方式：</span><span class="sxs-lookup"><span data-stu-id="34a5c-107">The following examples show various ways in which local variables can be declared with `var`:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#43](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_1.cs)]  
  
 <span data-ttu-id="34a5c-108">重要的是了解 `var` 关键字并不意味着“变体”，并且并不指示变量是松散类型或是后期绑定。</span><span class="sxs-lookup"><span data-stu-id="34a5c-108">It is important to understand that the `var` keyword does not mean "variant" and does not indicate that the variable is loosely typed, or late-bound.</span></span> <span data-ttu-id="34a5c-109">它只表示由编译器确定并分配最适合的类型。</span><span class="sxs-lookup"><span data-stu-id="34a5c-109">It just means that the compiler determines and assigns the most appropriate type.</span></span>  
  
 <span data-ttu-id="34a5c-110">在以下上下文中，可使用 `var` 关键字：</span><span class="sxs-lookup"><span data-stu-id="34a5c-110">The `var` keyword may be used in the following contexts:</span></span>  
  
-   <span data-ttu-id="34a5c-111">在局部变量（在方法范围内声明的变量）上，如前面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="34a5c-111">On local variables (variables declared at method scope) as shown in the previous example.</span></span>  
  
-   <span data-ttu-id="34a5c-112">在 [for](../../../csharp/language-reference/keywords/for.md) 初始化语句中。</span><span class="sxs-lookup"><span data-stu-id="34a5c-112">In a [for](../../../csharp/language-reference/keywords/for.md) initialization statement.</span></span>  
  
    ```csharp  
    for(var x = 1; x < 10; x++)  
    ```  
  
-   <span data-ttu-id="34a5c-113">在 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 初始化语句中。</span><span class="sxs-lookup"><span data-stu-id="34a5c-113">In a [foreach](../../../csharp/language-reference/keywords/foreach-in.md) initialization statement.</span></span>  
  
    ```csharp  
    foreach(var item in list){...}  
    ```  
  
-   <span data-ttu-id="34a5c-114">在 [using](../../../csharp/language-reference/keywords/using-statement.md) 域间中。</span><span class="sxs-lookup"><span data-stu-id="34a5c-114">In a [using](../../../csharp/language-reference/keywords/using-statement.md) statement.</span></span>  
  
    ```csharp  
    using (var file = new StreamReader("C:\\myfile.txt")) {...}  
    ```  
  
 <span data-ttu-id="34a5c-115">有关详细信息，请参阅[如何：在查询表达式中使用隐式类型化局部变量和数组](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md)。</span><span class="sxs-lookup"><span data-stu-id="34a5c-115">For more information, see [How to: Use Implicitly Typed Local Variables and Arrays in a Query Expression](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span></span>  
  
## <a name="var-and-anonymous-types"></a><span data-ttu-id="34a5c-116">var 和匿名类型</span><span class="sxs-lookup"><span data-stu-id="34a5c-116">var and Anonymous Types</span></span>  
 <span data-ttu-id="34a5c-117">在许多情况下，使用 `var` 是可选的，只是一种语法便利。</span><span class="sxs-lookup"><span data-stu-id="34a5c-117">In many cases the use of `var` is optional and is just a syntactic convenience.</span></span> <span data-ttu-id="34a5c-118">但是，在使用匿名类型初始化变量时，如果需要在以后访问对象的属性，则必须将变量声明为 `var`。</span><span class="sxs-lookup"><span data-stu-id="34a5c-118">However, when a variable is initialized with an anonymous type you must declare the variable as `var` if you need to access the properties of the object at a later point.</span></span> <span data-ttu-id="34a5c-119">这是 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 查询表达式中的常见方案。</span><span class="sxs-lookup"><span data-stu-id="34a5c-119">This is a common scenario in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="34a5c-120">有关详细信息，请参阅[匿名类型](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="34a5c-120">For more information, see [Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span>  
  
 <span data-ttu-id="34a5c-121">从源代码角度来看，匿名类型没有名称。</span><span class="sxs-lookup"><span data-stu-id="34a5c-121">From the perspective of your source code, an anonymous type has no name.</span></span> <span data-ttu-id="34a5c-122">因此，如果使用 `var` 初始化了查询变量，则访问返回对象序列中的属性的唯一方法是在 `foreach` 语句中将 `var` 用作迭代变量的类型。</span><span class="sxs-lookup"><span data-stu-id="34a5c-122">Therefore, if a query variable has been initialized with `var`, then the only way to access the properties in the returned sequence of objects is to use `var` as the type of the iteration variable in the `foreach` statement.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#44](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_2.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="34a5c-123">备注</span><span class="sxs-lookup"><span data-stu-id="34a5c-123">Remarks</span></span>  
 <span data-ttu-id="34a5c-124">以下限制适用于隐式类型化变量声明：</span><span class="sxs-lookup"><span data-stu-id="34a5c-124">The following restrictions apply to implicitly-typed variable declarations:</span></span>  
  
-   <span data-ttu-id="34a5c-125">仅当局部变量在相同语句中进行声明和初始化时，才能使用 `var`；变量不能初始化为 null，也不能初始化为方法组或匿名函数。</span><span class="sxs-lookup"><span data-stu-id="34a5c-125">`var` can only be used when a local variable is declared and initialized in the same statement; the variable cannot be initialized to null, or to a method group or an anonymous function.</span></span>  
  
-   <span data-ttu-id="34a5c-126">`var` 不能在类范围内对字段使用。</span><span class="sxs-lookup"><span data-stu-id="34a5c-126">`var` cannot be used on fields at class scope.</span></span>  
  
-   <span data-ttu-id="34a5c-127">使用 `var` 声明的变量不能在初始化表达式中使用。</span><span class="sxs-lookup"><span data-stu-id="34a5c-127">Variables declared by using `var` cannot be used in the initialization expression.</span></span> <span data-ttu-id="34a5c-128">换句话说，此表达式是合法的`: int i = (i = 20);`，但是此表达式会生成编译时错误：`var i = (i = 20);`</span><span class="sxs-lookup"><span data-stu-id="34a5c-128">In other words, this expression is legal`: int i = (i = 20);` but this expression produces a compile-time error: `var i = (i = 20);`</span></span>  
  
-   <span data-ttu-id="34a5c-129">不能在相同语句中初始化多个隐式类型化变量。</span><span class="sxs-lookup"><span data-stu-id="34a5c-129">Multiple implicitly-typed variables cannot be initialized in the same statement.</span></span>  
  
-   <span data-ttu-id="34a5c-130">如果一种名为 `var` 的类型处于范围内，则 `var` 关键字会解析为该类型名称，不会被视为隐式类型化局部变量声明的一部分。</span><span class="sxs-lookup"><span data-stu-id="34a5c-130">If a type named `var` is in scope, then the `var` keyword will resolve to that type name and will not be treated as part of an implicitly typed local variable declaration.</span></span>  
  
 <span data-ttu-id="34a5c-131">你可能会发现，对于在其中难以确定查询变量的确切构造类型的查询表达式，`var` 也可能会十分有用。</span><span class="sxs-lookup"><span data-stu-id="34a5c-131">You may find that `var` can also be useful with query expressions in which the exact constructed type of the query variable is difficult to determine.</span></span> <span data-ttu-id="34a5c-132">这可能会针对分组和排序操作发生。</span><span class="sxs-lookup"><span data-stu-id="34a5c-132">This can occur with grouping and ordering operations.</span></span>  
  
 <span data-ttu-id="34a5c-133">当变量的特定类型在键盘上键入时很繁琐、或是显而易见、或是不会提高代码的可读性时，`var` 关键字也可能非常有用。</span><span class="sxs-lookup"><span data-stu-id="34a5c-133">The `var` keyword can also be useful when the specific type of the variable is tedious to type on the keyboard, or is obvious, or does not add to the readability of the code.</span></span> <span data-ttu-id="34a5c-134">`var` 采用此方法提供帮助的一个示例是针对嵌套泛型类型（如用于分组操作的类型）。</span><span class="sxs-lookup"><span data-stu-id="34a5c-134">One example where `var` is helpful in this manner is with nested generic types such as those used with group operations.</span></span> <span data-ttu-id="34a5c-135">在下面的查询中，查询变量的类型是 `IEnumerable<IGrouping<string, Student>>`。</span><span class="sxs-lookup"><span data-stu-id="34a5c-135">In the following query, the type of the query variable is `IEnumerable<IGrouping<string, Student>>`.</span></span> <span data-ttu-id="34a5c-136">只要你和必须维护你的代码的其他人了解这一点，使用隐式类型化实现便利性和简便性时便不会出现问题。</span><span class="sxs-lookup"><span data-stu-id="34a5c-136">As long as you and others who must maintain your code understand this, there is no problem with using implicit typing for convenience and brevity.</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicitly-typed-local-variables_3.cs)]  
  
 <span data-ttu-id="34a5c-137">但是，使用 `var` 至少有可能使代码对其他开发人员更加难以理解。</span><span class="sxs-lookup"><span data-stu-id="34a5c-137">However, the use of `var` does have at least the potential to make your code more difficult to understand for other developers.</span></span> <span data-ttu-id="34a5c-138">为此，C# 文档通常只在需要时才使用 `var`。</span><span class="sxs-lookup"><span data-stu-id="34a5c-138">For that reason, the C# documentation generally uses `var` only when it is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34a5c-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="34a5c-139">See Also</span></span>  
 [<span data-ttu-id="34a5c-140">C# 参考</span><span class="sxs-lookup"><span data-stu-id="34a5c-140">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="34a5c-141">隐式类型化数组</span><span class="sxs-lookup"><span data-stu-id="34a5c-141">Implicitly Typed Arrays</span></span>](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md)  
 [<span data-ttu-id="34a5c-142">如何：在查询表达式中使用隐式类型的局部变量和数组</span><span class="sxs-lookup"><span data-stu-id="34a5c-142">How to: Use Implicitly Typed Local Variables and Arrays in a Query Expression</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md)  
 [<span data-ttu-id="34a5c-143">匿名类型</span><span class="sxs-lookup"><span data-stu-id="34a5c-143">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)  
 [<span data-ttu-id="34a5c-144">对象和集合初始值设定项</span><span class="sxs-lookup"><span data-stu-id="34a5c-144">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)  
 [<span data-ttu-id="34a5c-145">var</span><span class="sxs-lookup"><span data-stu-id="34a5c-145">var</span></span>](../../../csharp/language-reference/keywords/var.md)  
 [<span data-ttu-id="34a5c-146">LINQ 查询表达式</span><span class="sxs-lookup"><span data-stu-id="34a5c-146">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="34a5c-147">LINQ（语言集成查询）</span><span class="sxs-lookup"><span data-stu-id="34a5c-147">LINQ (Language-Integrated Query)</span></span>](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [<span data-ttu-id="34a5c-148">for</span><span class="sxs-lookup"><span data-stu-id="34a5c-148">for</span></span>](../../../csharp/language-reference/keywords/for.md)  
 [<span data-ttu-id="34a5c-149">foreach, in</span><span class="sxs-lookup"><span data-stu-id="34a5c-149">foreach, in</span></span>](../../../csharp/language-reference/keywords/foreach-in.md)  
 [<span data-ttu-id="34a5c-150">using 语句</span><span class="sxs-lookup"><span data-stu-id="34a5c-150">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)
