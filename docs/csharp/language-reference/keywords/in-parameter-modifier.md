---
title: "in 参数修饰符（C# 参考）"
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
ms.openlocfilehash: 035aac3e6b902f607e533b709713eb1d07c9774a
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
# <a name="in-parameter-modifier-c-reference"></a><span data-ttu-id="38951-102">in 参数修饰符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="38951-102">in parameter modifier (C# Reference)</span></span>

<span data-ttu-id="38951-103">`in` 关键字通过引用传递参数。</span><span class="sxs-lookup"><span data-stu-id="38951-103">The `in` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="38951-104">它类似于 [ref](ref.md) 或 [out](out-parameter-modifier.md) 关键字，只是通过调用的方法不能修改 `in` 参数，而可以修改 `ref` 参数，同时 `out` 参数必须由调用方修改，并且在调用上下文中可观测这些修改。</span><span class="sxs-lookup"><span data-stu-id="38951-104">It is like the [ref](ref.md) or [out](out-parameter-modifier.md) keywords, except that `in` arguments cannot be modified by the called method, whereas `ref` arguments may be modified,  `out` arguments must be modified by the caller, and those modifications are observable in the calling context.</span></span>

[!code-csharp-interactive[cs-in-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/InParameterModifier.cs#1)]  

<span data-ttu-id="38951-105">前面的示例说明调用站点处不需要 `in` 修饰符。</span><span class="sxs-lookup"><span data-stu-id="38951-105">The preceding example demonstrates that the `in` modifier is unnecessary at the call site.</span></span> <span data-ttu-id="38951-106">仅在方法声明中需要它。</span><span class="sxs-lookup"><span data-stu-id="38951-106">It is only required in the method declaration.</span></span>

> [!NOTE] 
> <span data-ttu-id="38951-107">`in` 关键字还作为 `foreach` 语句的一部分，或作为 LINQ 查询中 `join` 子句的一部分，与泛型类型参数一起使用来指定该类型参数为逆变。</span><span class="sxs-lookup"><span data-stu-id="38951-107">The `in` keyword can also be used with a generic type parameter to specify that the type parameter is contravariant, as part of a `foreach` statement, or as part of a `join` clause in a LINQ query.</span></span> <span data-ttu-id="38951-108">有关在这些上下文使用 `in` 关键字的详细信息，请参阅 [in](in.md)，其中提供了所有这些用法的链接。</span><span class="sxs-lookup"><span data-stu-id="38951-108">For more information on the use of the `in` keyword in these contexts, see [in](in.md) which provides links to all those uses.</span></span>
  
 <span data-ttu-id="38951-109">作为 `in` 参数传递的变量在方法调用中传递之前必须进行初始化。</span><span class="sxs-lookup"><span data-stu-id="38951-109">Variables passed as `in` arguments must be initialized before being passed in a method call.</span></span> <span data-ttu-id="38951-110">但是，所调用的方法可能不会分配值或修改参数。</span><span class="sxs-lookup"><span data-stu-id="38951-110">However, the called method may not assign a value or modify the argument.</span></span>  
  
 <span data-ttu-id="38951-111">尽管 `in`、`ref` 和 `out` 关键字会导致不同的运行时行为，它们并不被视为编译时方法签名的一部分。</span><span class="sxs-lookup"><span data-stu-id="38951-111">Although the `in`, `ref`, and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="38951-112">因此，如果唯一的不同是一个方法采用 `ref` 或 `in` 参数，而另一个方法采用 `out` 参数，则无法重载这两个方法。</span><span class="sxs-lookup"><span data-stu-id="38951-112">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="38951-113">例如，以下代码将不会编译：</span><span class="sxs-lookup"><span data-stu-id="38951-113">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on in, ref and out".
    public void SampleMethod(in int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="38951-114">允许基于 `in` 的存在进行重载，但会生成编译器警告：</span><span class="sxs-lookup"><span data-stu-id="38951-114">Overloading based on the presence of `in` is allowed, but generates a compiler warning:</span></span>  
  
```csharp
class InOverloads
{
    // Discouraged. Calling SampleMethod(value) is ambiguous.
    public void SampleMethod(in int i) { }
    public void SampleMethod(int i) { }
}
```

<span data-ttu-id="38951-115">属性或常量可能以 `in` 参数传递，因为调用的方法可能不会修改其值。</span><span class="sxs-lookup"><span data-stu-id="38951-115">Properties or constants may be passed as `in` parameters, because the calling method may not modify their values.</span></span>
  
<span data-ttu-id="38951-116">不能将 `in`、`ref` 和 `out` 关键字用于以下几种方法：</span><span class="sxs-lookup"><span data-stu-id="38951-116">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="38951-117">异步方法，通过使用 [async](../../../csharp/language-reference/keywords/async.md) 修饰符定义。</span><span class="sxs-lookup"><span data-stu-id="38951-117">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
- <span data-ttu-id="38951-118">迭代器方法，包括 [yield return](../../../csharp/language-reference/keywords/yield.md) 或 `yield break` 语句。</span><span class="sxs-lookup"><span data-stu-id="38951-118">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

<span data-ttu-id="38951-119">通常可声明 `in` 参数以避免按值传递参数所需的复制操作。</span><span class="sxs-lookup"><span data-stu-id="38951-119">You typically declare `in` arguments to avoid the copy operations necessary for passing arguments by value.</span></span> <span data-ttu-id="38951-120">参数为结构或结构数组时，这非常有用。</span><span class="sxs-lookup"><span data-stu-id="38951-120">This is most useful when arguments are structures or arrays of structures.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="38951-121">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="38951-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="38951-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="38951-122">See Also</span></span>  
 [<span data-ttu-id="38951-123">C# 参考</span><span class="sxs-lookup"><span data-stu-id="38951-123">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="38951-124">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="38951-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="38951-125">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="38951-125">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="38951-126">方法参数</span><span class="sxs-lookup"><span data-stu-id="38951-126">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)
