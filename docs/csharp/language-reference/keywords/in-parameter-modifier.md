---
title: in 参数修饰符（C# 参考）
ms.date: 03/06/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- parameters [C#], in
- in parameters [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9b8b21e2bdc95829c831ee71f24b47986321b7d0
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="in-parameter-modifier-c-reference"></a><span data-ttu-id="7581b-102">in 参数修饰符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="7581b-102">in parameter modifier (C# Reference)</span></span>

<span data-ttu-id="7581b-103">`in` 关键字通过引用传递参数。</span><span class="sxs-lookup"><span data-stu-id="7581b-103">The `in` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="7581b-104">它类似于 [ref](ref.md) 或 [out](out-parameter-modifier.md) 关键字，只是通过调用的方法不能修改 `in` 参数，而可以修改 `ref` 参数，同时 `out` 参数必须由调用方修改，并且在调用上下文中可观测这些修改。</span><span class="sxs-lookup"><span data-stu-id="7581b-104">It is like the [ref](ref.md) or [out](out-parameter-modifier.md) keywords, except that `in` arguments cannot be modified by the called method, whereas `ref` arguments may be modified,  `out` arguments must be modified by the caller, and those modifications are observable in the calling context.</span></span>

[!code-csharp-interactive[cs-in-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/InParameterModifier.cs#1)]  

<span data-ttu-id="7581b-105">前面的示例说明调用站点处不需要 `in` 修饰符。</span><span class="sxs-lookup"><span data-stu-id="7581b-105">The preceding example demonstrates that the `in` modifier is unnecessary at the call site.</span></span> <span data-ttu-id="7581b-106">仅在方法声明中需要它。</span><span class="sxs-lookup"><span data-stu-id="7581b-106">It is only required in the method declaration.</span></span>

> [!NOTE] 
> <span data-ttu-id="7581b-107">`in` 关键字还作为 `foreach` 语句的一部分，或作为 LINQ 查询中 `join` 子句的一部分，与泛型类型参数一起使用来指定该类型参数为逆变。</span><span class="sxs-lookup"><span data-stu-id="7581b-107">The `in` keyword can also be used with a generic type parameter to specify that the type parameter is contravariant, as part of a `foreach` statement, or as part of a `join` clause in a LINQ query.</span></span> <span data-ttu-id="7581b-108">有关在这些上下文使用 `in` 关键字的详细信息，请参阅 [in](in.md)，其中提供了所有这些用法的链接。</span><span class="sxs-lookup"><span data-stu-id="7581b-108">For more information on the use of the `in` keyword in these contexts, see [in](in.md) which provides links to all those uses.</span></span>
  
 <span data-ttu-id="7581b-109">作为 `in` 参数传递的变量在方法调用中传递之前必须进行初始化。</span><span class="sxs-lookup"><span data-stu-id="7581b-109">Variables passed as `in` arguments must be initialized before being passed in a method call.</span></span> <span data-ttu-id="7581b-110">但是，所调用的方法可能不会分配值或修改参数。</span><span class="sxs-lookup"><span data-stu-id="7581b-110">However, the called method may not assign a value or modify the argument.</span></span>  
  
 <span data-ttu-id="7581b-111">尽管 `in`、`ref` 和 `out` 关键字会导致不同的运行时行为，它们并不被视为编译时方法签名的一部分。</span><span class="sxs-lookup"><span data-stu-id="7581b-111">Although the `in`, `ref`, and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="7581b-112">因此，如果唯一的不同是一个方法采用 `ref` 或 `in` 参数，而另一个方法采用 `out` 参数，则无法重载这两个方法。</span><span class="sxs-lookup"><span data-stu-id="7581b-112">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="7581b-113">例如，以下代码将不会编译：</span><span class="sxs-lookup"><span data-stu-id="7581b-113">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on in, ref and out".
    public void SampleMethod(in int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="7581b-114">允许基于 `in` 的存在进行重载，但会生成编译器警告：</span><span class="sxs-lookup"><span data-stu-id="7581b-114">Overloading based on the presence of `in` is allowed, but generates a compiler warning:</span></span>  
  
```csharp
class InOverloads
{
    // Discouraged. Calling SampleMethod(value) is ambiguous.
    public void SampleMethod(in int i) { }
    public void SampleMethod(int i) { }
}
```

<span data-ttu-id="7581b-115">属性或常量可能以 `in` 参数传递，因为调用的方法可能不会修改其值。</span><span class="sxs-lookup"><span data-stu-id="7581b-115">Properties or constants may be passed as `in` parameters, because the calling method may not modify their values.</span></span>
  
<span data-ttu-id="7581b-116">不能将 `in`、`ref` 和 `out` 关键字用于以下几种方法：</span><span class="sxs-lookup"><span data-stu-id="7581b-116">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="7581b-117">异步方法，通过使用 [async](../../../csharp/language-reference/keywords/async.md) 修饰符定义。</span><span class="sxs-lookup"><span data-stu-id="7581b-117">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
- <span data-ttu-id="7581b-118">迭代器方法，包括 [yield return](../../../csharp/language-reference/keywords/yield.md) 或 `yield break` 语句。</span><span class="sxs-lookup"><span data-stu-id="7581b-118">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

<span data-ttu-id="7581b-119">通常可声明 `in` 参数以避免按值传递参数所需的复制操作。</span><span class="sxs-lookup"><span data-stu-id="7581b-119">You typically declare `in` arguments to avoid the copy operations necessary for passing arguments by value.</span></span> <span data-ttu-id="7581b-120">当自变量为值类型（例如复制操作比按引用传递开销更大的结构）时，这最为有用。</span><span class="sxs-lookup"><span data-stu-id="7581b-120">This is most useful when arguments are value types such as structures where copy operations are more expensive than passing by reference.</span></span>

> [!WARNING]
>  <span data-ttu-id="7581b-121">如果使用不当，`in` 参数的开销甚至可能更大。</span><span class="sxs-lookup"><span data-stu-id="7581b-121">`in` parameters can be even more expensive if misused.</span></span> <span data-ttu-id="7581b-122">编译器可能不知晓成员方法是否修改结构的状态。</span><span class="sxs-lookup"><span data-stu-id="7581b-122">The compiler may not know if member methods modify the state of the struct.</span></span> <span data-ttu-id="7581b-123">每当编译器无法确定对象是否未修改时，它就会防御性地创建副本并使用该副本调用成员引用。</span><span class="sxs-lookup"><span data-stu-id="7581b-123">Whenever the compiler cannot ensure that the object is not modified, it defensively creates a copy and calls member references using that copy.</span></span> <span data-ttu-id="7581b-124">任何可能的修改均针对该防御性副本。</span><span class="sxs-lookup"><span data-stu-id="7581b-124">Any possible modifications are to that defensive copy.</span></span> <span data-ttu-id="7581b-125">避免这些副本的两种方法是：传递 `in` 参数作为 `in` 自变量，或定义结构作为 `readonly struct` 。</span><span class="sxs-lookup"><span data-stu-id="7581b-125">The two ways to avoid these copies are to pass `in` parameters as `in` arguments or to define structures as `readonly struct`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="7581b-126">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="7581b-126">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7581b-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="7581b-127">See Also</span></span>  
 [<span data-ttu-id="7581b-128">C# 参考</span><span class="sxs-lookup"><span data-stu-id="7581b-128">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="7581b-129">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="7581b-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7581b-130">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="7581b-130">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="7581b-131">方法参数</span><span class="sxs-lookup"><span data-stu-id="7581b-131">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)  
 [<span data-ttu-id="7581b-132">具有值类型的引用语义</span><span class="sxs-lookup"><span data-stu-id="7581b-132">Reference Semantics with Value Types</span></span>](../../../csharp/reference-semantics-with-value-types.md)
