---
title: in 参数修饰符 - C# 参考
ms.custom: seodec18
ms.date: 03/26/2019
helpviewer_keywords:
- parameters [C#], in
- in parameters [C#]
ms.openlocfilehash: e39d470308ed5a2b2ed82ade0faf8ba925228c2c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59112640"
---
# <a name="in-parameter-modifier-c-reference"></a><span data-ttu-id="cd911-102">in 参数修饰符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="cd911-102">in parameter modifier (C# Reference)</span></span>

<span data-ttu-id="cd911-103">`in` 关键字通过引用传递参数。</span><span class="sxs-lookup"><span data-stu-id="cd911-103">The `in` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="cd911-104">它让形参成为实参的别名，这必须是变量。</span><span class="sxs-lookup"><span data-stu-id="cd911-104">It makes the formal parameter an alias for the argument, which must be a variable.</span></span> <span data-ttu-id="cd911-105">换而言之，对形参执行的任何操作都是对实参执行的。</span><span class="sxs-lookup"><span data-stu-id="cd911-105">In other words, any operation on the parameter is made on the argument.</span></span> <span data-ttu-id="cd911-106">它类似于 [ref](ref.md) 或 [out](out-parameter-modifier.md) 关键字，不同之处在于 `in` 参数无法通过调用的方法进行修改。</span><span class="sxs-lookup"><span data-stu-id="cd911-106">It is like the [ref](ref.md) or [out](out-parameter-modifier.md) keywords, except that `in` arguments cannot be modified by the called method.</span></span> <span data-ttu-id="cd911-107">`out` 参数必须由调用的方法进行修改，这些修改在调用上下文中是可观察的，而 `ref` 参数是可以修改的。</span><span class="sxs-lookup"><span data-stu-id="cd911-107">Whereas `ref` arguments may be modified, `out` arguments must be modified by the called method, and those modifications are observable in the calling context.</span></span>

[!code-csharp-interactive[cs-in-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/InParameterModifier.cs#1)]  

<span data-ttu-id="cd911-108">前面的示例说明调用站点处通常不需要 `in` 修饰符。</span><span class="sxs-lookup"><span data-stu-id="cd911-108">The preceding example demonstrates that the `in` modifier is usually unnecessary at the call site.</span></span> <span data-ttu-id="cd911-109">仅在方法声明中需要它。</span><span class="sxs-lookup"><span data-stu-id="cd911-109">It is only required in the method declaration.</span></span>

> [!NOTE] 
> <span data-ttu-id="cd911-110">`in` 关键字还作为 `foreach` 语句的一部分，或作为 LINQ 查询中 `join` 子句的一部分，与泛型类型参数一起使用来指定该类型参数为逆变。</span><span class="sxs-lookup"><span data-stu-id="cd911-110">The `in` keyword can also be used with a generic type parameter to specify that the type parameter is contravariant, as part of a `foreach` statement, or as part of a `join` clause in a LINQ query.</span></span> <span data-ttu-id="cd911-111">有关在这些上下文使用 `in` 关键字的详细信息，请参阅 [in](in.md)，其中提供了所有这些用法的链接。</span><span class="sxs-lookup"><span data-stu-id="cd911-111">For more information on the use of the `in` keyword in these contexts, see [in](in.md), which provides links to all those uses.</span></span>
  
<span data-ttu-id="cd911-112">作为 `in` 参数传递的变量在方法调用中传递之前必须进行初始化。</span><span class="sxs-lookup"><span data-stu-id="cd911-112">Variables passed as `in` arguments must be initialized before being passed in a method call.</span></span> <span data-ttu-id="cd911-113">但是，所调用的方法可能不会分配值或修改参数。</span><span class="sxs-lookup"><span data-stu-id="cd911-113">However, the called method may not assign a value or modify the argument.</span></span>  

<span data-ttu-id="cd911-114">`in` 参数修饰符可在 C# 7.2 及更高版本中使用。</span><span class="sxs-lookup"><span data-stu-id="cd911-114">The `in` parameter modifier is available in C# 7.2 and later.</span></span> <span data-ttu-id="cd911-115">以前的版本生成编译器错误 `CS8107`（“‘readonly 引用’功能在 C# 7.0 中不可用。</span><span class="sxs-lookup"><span data-stu-id="cd911-115">Previous versions generate compiler error `CS8107` ("Feature 'readonly references' is not available in C# 7.0.</span></span> <span data-ttu-id="cd911-116">请使用语言版本 7.2 或更高版本。”）若要配置编译器语言版本，请参阅[选择 C# 语言版本](../configure-language-version.md)。</span><span class="sxs-lookup"><span data-stu-id="cd911-116">Please use language version 7.2 or greater.") To configure the compiler language version, see [Select the C# language version](../configure-language-version.md).</span></span>

<span data-ttu-id="cd911-117">`in`、`ref` 和 `out` 关键字不被视为用于重载决议的方法签名的一部分。</span><span class="sxs-lookup"><span data-stu-id="cd911-117">The `in`, `ref`, and `out` keywords are not considered part of the method signature for the purpose of overload resolution.</span></span> <span data-ttu-id="cd911-118">因此，如果唯一的不同是一个方法采用 `ref` 或 `in` 参数，而另一个方法采用 `out` 参数，则无法重载这两个方法。</span><span class="sxs-lookup"><span data-stu-id="cd911-118">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="cd911-119">例如，以下代码将不会编译：</span><span class="sxs-lookup"><span data-stu-id="cd911-119">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on in, ref and out".
    public void SampleMethod(in int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="cd911-120">存在 `in` 时可以重载：</span><span class="sxs-lookup"><span data-stu-id="cd911-120">Overloading based on the presence of `in` is allowed:</span></span>  
  
```csharp
class InOverloads
{
    public void SampleMethod(in int i) { }
    public void SampleMethod(int i) { }
}
```

## <a name="overload-resolution-rules"></a><span data-ttu-id="cd911-121">重载决策规则</span><span class="sxs-lookup"><span data-stu-id="cd911-121">Overload resolution rules</span></span>

<span data-ttu-id="cd911-122">通过理解使用 `in` 参数的动机，可以理解使用按值方法和使用 `in` 参数方法的重载决策规则。</span><span class="sxs-lookup"><span data-stu-id="cd911-122">You can understand the overload resolution rules for methods with by value vs. `in` arguments by understanding the motivation for `in` arguments.</span></span> <span data-ttu-id="cd911-123">定义使用 `in` 参数的方法是一项潜在的性能优化。</span><span class="sxs-lookup"><span data-stu-id="cd911-123">Defining methods using `in` parameters is a potential performance optimization.</span></span> <span data-ttu-id="cd911-124">某些 `struct` 类型参数可能很大，在紧凑的循环或关键代码路径中调用方法时，复制这些结构的成本就很高。</span><span class="sxs-lookup"><span data-stu-id="cd911-124">Some `struct` type arguments may be large in size, and when methods are called in tight loops or critical code paths, the cost of copying those structures is critical.</span></span> <span data-ttu-id="cd911-125">方法声明 `in` 参数以指定参数可能按引用安全传递，因为所调用的方法不修改该参数的状态。</span><span class="sxs-lookup"><span data-stu-id="cd911-125">Methods declare `in` parameters to specify that arguments may be passed by reference safely because the called method does not modify the state of that argument.</span></span> <span data-ttu-id="cd911-126">按引用传递这些参数可以避免（可能产生的）高昂的复制成本。</span><span class="sxs-lookup"><span data-stu-id="cd911-126">Passing those arguments by reference avoids the (potentially) expensive copy.</span></span> 

<span data-ttu-id="cd911-127">为调用站点上的参数指定 `in` 通常为可选。</span><span class="sxs-lookup"><span data-stu-id="cd911-127">Specifying `in` for arguments at the call site is typically optional.</span></span> <span data-ttu-id="cd911-128">按值传递参数和使用 `in` 修饰符按引用传递参数这两种方法并没有语义差异。</span><span class="sxs-lookup"><span data-stu-id="cd911-128">There is no semantic difference between passing arguments by value and passing them by reference using the `in` modifier.</span></span> <span data-ttu-id="cd911-129">可以在调用站点选择 `in` 修饰符，因为你不需要指出参数值可能会改变。</span><span class="sxs-lookup"><span data-stu-id="cd911-129">The `in` modifier at the call site is optional because you don't need to indicate that the argument's value might be changed.</span></span> <span data-ttu-id="cd911-130">在调用站点显式添加 `in` 修饰符以确保参数是按引用传递，而不是按值传递。</span><span class="sxs-lookup"><span data-stu-id="cd911-130">You explicitly add the `in` modifier at the call site to ensure the argument is passed by reference, not by value.</span></span> <span data-ttu-id="cd911-131">显式使用 `in` 有以下两个效果：</span><span class="sxs-lookup"><span data-stu-id="cd911-131">Explicitly using `in` has the following two effects:</span></span>

<span data-ttu-id="cd911-132">首先，在调用站点指定 `in` 会强制编译器选择使用匹配的 `in` 参数定义的方法。</span><span class="sxs-lookup"><span data-stu-id="cd911-132">First, specifying `in` at the call site forces the compiler to select a method defined with a matching `in` parameter.</span></span> <span data-ttu-id="cd911-133">否则，如果两种方法唯一的区别在于是否存在 `in`，则按值重载的匹配度会更高。</span><span class="sxs-lookup"><span data-stu-id="cd911-133">Otherwise, when two methods differ only in the presence of `in`, the by value overload is a better match.</span></span>

<span data-ttu-id="cd911-134">第二点，指定 `in` 会声明你想按引用传递参数。</span><span class="sxs-lookup"><span data-stu-id="cd911-134">Second, specifying `in` declares your intent to pass an argument by reference.</span></span> <span data-ttu-id="cd911-135">结合 `in` 使用的参数必须代表一个可以直接引用的位置。</span><span class="sxs-lookup"><span data-stu-id="cd911-135">The argument used with `in` must represent a location that can be directly referred to.</span></span> <span data-ttu-id="cd911-136">`out` 和 `ref` 参数的相同常规规则适用：不得使用常量、普通属性或其他生成值的表达式。</span><span class="sxs-lookup"><span data-stu-id="cd911-136">The same general rules for `out` and `ref` arguments apply: You cannot use constants, ordinary properties, or other expressions that produce values.</span></span> <span data-ttu-id="cd911-137">否则，在调用站点省略 `in` 就会通知编译器你将允许它创建临时变量，并按只读引用传递至方法。</span><span class="sxs-lookup"><span data-stu-id="cd911-137">Otherwise, omitting `in` at the call site informs the compiler that you will allow it to create a temporary variable to pass by read-only reference to the method.</span></span> <span data-ttu-id="cd911-138">编译器创建临时变量以克服一些 `in` 参数的限制：</span><span class="sxs-lookup"><span data-stu-id="cd911-138">The compiler creates a temporary variable to overcome several restrictions with `in` arguments:</span></span>

- <span data-ttu-id="cd911-139">临时变量允许将编译时常数作为 `in` 参数。</span><span class="sxs-lookup"><span data-stu-id="cd911-139">A temporary variable allows compile-time constants as `in` parameters.</span></span>
- <span data-ttu-id="cd911-140">临时变量允许使用属性或 `in` 参数的其他表达式。</span><span class="sxs-lookup"><span data-stu-id="cd911-140">A temporary variable allows properties, or other expressions for `in` parameters.</span></span>
- <span data-ttu-id="cd911-141">存在从实参类型到形参类型的隐式转换时，临时变量允许使用实参。</span><span class="sxs-lookup"><span data-stu-id="cd911-141">A temporary variable allows arguments where there is an implicit conversion from the argument type to the parameter type.</span></span>

<span data-ttu-id="cd911-142">在前面的所有实例中，编译器创建了临时变量，用于存储常数、属性或其他表达式的值。</span><span class="sxs-lookup"><span data-stu-id="cd911-142">In all the preceding instances, the compiler creates a temporary variable that stores the value of the constant, property, or other expression.</span></span>

<span data-ttu-id="cd911-143">以下代码阐释了这些规则：</span><span class="sxs-lookup"><span data-stu-id="cd911-143">The following code illustrates these rules:</span></span>

```csharp
static void Method(in int argument)
{
    // implementation removed
}

Method(5); // OK, temporary variable created.
Method(5L); // CS1503: no implicit conversion from long to int
short s = 0;
Method(s); // OK, temporary int created with the value 0
Method(in s); // CS1503: cannot convert from in short to in int
int i = 42;
Method(i); // passed by readonly reference
Method(in i); // passed by readonly reference, explicitly using `in`
```

<span data-ttu-id="cd911-144">现在，假设可以使用另一种使用按值参数的方法。</span><span class="sxs-lookup"><span data-stu-id="cd911-144">Now, suppose another method using by value arguments was available.</span></span> <span data-ttu-id="cd911-145">结果的变化如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="cd911-145">The results change as shown in the following code:</span></span>

```csharp
static void Method(int argument)
{
    // implementation removed
}

static void Method(in int argument)
{
    // implementation removed
}

Method(5); // Calls overload passed by value
Method(5L); // CS1503: no implicit conversion from long to int
short s = 0;
Method(s); // Calls overload passed by value.
Method(in s); // CS1503: cannot convert from in short to in int
int i = 42;
Method(i); // Calls overload passed by value
Method(in i); // passed by readonly reference, explicitly using `in`
```

<span data-ttu-id="cd911-146">最后一个是按引用传递参数的唯一方法调用。</span><span class="sxs-lookup"><span data-stu-id="cd911-146">The only method call where the argument is passed by reference is the final one.</span></span>

> [!NOTE]
> <span data-ttu-id="cd911-147">为了简化操作，前面的代码将 `int` 用作参数类型。</span><span class="sxs-lookup"><span data-stu-id="cd911-147">The preceding code uses `int` as the argument type for simplicity.</span></span> <span data-ttu-id="cd911-148">因为大多数新式计算机中的引用都比 `int` 大，所以将单个 `int` 作为只读引用传递没有任何好处。</span><span class="sxs-lookup"><span data-stu-id="cd911-148">Because `int` is no larger than a reference in most modern machines, there is no benefit to passing a single `int` as a readonly reference.</span></span> 

## <a name="limitations-on-in-parameters"></a><span data-ttu-id="cd911-149">`in` 参数的限制</span><span class="sxs-lookup"><span data-stu-id="cd911-149">Limitations on `in` parameters</span></span>

<span data-ttu-id="cd911-150">不能将 `in`、`ref` 和 `out` 关键字用于以下几种方法：</span><span class="sxs-lookup"><span data-stu-id="cd911-150">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="cd911-151">异步方法，通过使用 [async](async.md) 修饰符定义。</span><span class="sxs-lookup"><span data-stu-id="cd911-151">Async methods, which you define by using the [async](async.md) modifier.</span></span>  
- <span data-ttu-id="cd911-152">迭代器方法，包括 [yield return](yield.md) 或 `yield break` 语句。</span><span class="sxs-lookup"><span data-stu-id="cd911-152">Iterator methods, which include a [yield return](yield.md) or `yield break` statement.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="cd911-153">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="cd911-153">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cd911-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="cd911-154">See also</span></span>

- [<span data-ttu-id="cd911-155">C# 参考</span><span class="sxs-lookup"><span data-stu-id="cd911-155">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="cd911-156">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="cd911-156">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="cd911-157">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="cd911-157">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="cd911-158">方法参数</span><span class="sxs-lookup"><span data-stu-id="cd911-158">Method Parameters</span></span>](method-parameters.md)
- [<span data-ttu-id="cd911-159">编写安全高效的代码</span><span class="sxs-lookup"><span data-stu-id="cd911-159">Write safe efficient code</span></span>](../../write-safe-efficient-code.md)
