---
title: out 参数修饰符（C# 参考）
ms.date: 03/06/2018
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.openlocfilehash: c9fb03560e30bab3cc71a6171c731d887e859f6c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43423577"
---
# <a name="out-parameter-modifier-c-reference"></a><span data-ttu-id="a6f0b-102">out 参数修饰符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="a6f0b-102">out parameter modifier (C# Reference)</span></span>
<span data-ttu-id="a6f0b-103">`out` 关键字通过引用传递参数。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-103">The `out` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="a6f0b-104">它与 [ref](ref.md) 关键字相似，只不过 `ref` 要求在传递之前初始化变量。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-104">It is like the [ref](ref.md) keyword, except that `ref` requires that the variable be initialized before it is passed.</span></span> <span data-ttu-id="a6f0b-105">它也类似于 [in](in-parameter-modifier.md) 关键字，只不过 `in` 不允许通过调用方法来修改参数值。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-105">It is also like the [in](in-parameter-modifier.md) keyword, except that `in` does not allow the called method to modify the argument value.</span></span> <span data-ttu-id="a6f0b-106">若要使用 `out` 参数，方法定义和调用方法均必须显式使用 `out` 关键字。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-106">To use an `out` parameter, both the method definition and the calling method must explicitly use the `out` keyword.</span></span> <span data-ttu-id="a6f0b-107">例如:</span><span class="sxs-lookup"><span data-stu-id="a6f0b-107">For example:</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#1)]  

> [!NOTE] 
> <span data-ttu-id="a6f0b-108">`out` 关键字也可与泛型类型参数结合使用，以指定该类型参数是协变参数。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-108">The `out` keyword can also be used with a generic type parameter to specify that the type parameter is covariant.</span></span> <span data-ttu-id="a6f0b-109">有关在此上下文中使用 `out` 关键字的详细信息，请参阅 [out（泛型修饰符）](out-generic-modifier.md)。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-109">For more information on the use of the `out` keyword in this context, see [out (Generic Modifier)](out-generic-modifier.md).</span></span>
  
<span data-ttu-id="a6f0b-110">作为 `out` 参数传递的变量在方法调用中传递之前不必进行初始化。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-110">Variables passed as `out` arguments do not have to be initialized before being passed in a method call.</span></span> <span data-ttu-id="a6f0b-111">但是，被调用的方法需要在返回之前赋一个值。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-111">However, the called method is required to assign a value before the method returns.</span></span>  
  
<span data-ttu-id="a6f0b-112">尽管 `in`、`ref` 和 `out` 关键字会导致不同的运行时行为，它们并不被视为编译时方法签名的一部分。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-112">Although the `in`, `ref`, and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="a6f0b-113">因此，如果唯一的不同是一个方法采用 `ref` 或 `in` 参数，而另一个方法采用 `out` 参数，则无法重载这两个方法。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-113">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="a6f0b-114">例如，以下代码将不会编译：</span><span class="sxs-lookup"><span data-stu-id="a6f0b-114">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="a6f0b-115">但是，如果一个方法采用 `ref`、`in` 或 `out` 参数，而另一个方法采用其他参数，则可以完成重载，如：</span><span class="sxs-lookup"><span data-stu-id="a6f0b-115">Overloading is legal, however, if one method takes a `ref`, `in`, or `out` argument and the other has none of those modifiers, like this:</span></span>  
  
[!code-csharp[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#2)]  

<span data-ttu-id="a6f0b-116">编译器通过将调用站点上的参数修饰符与方法调用中使用的参数修饰符进行匹配，从而选择最佳重载。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-116">The compiler chooses the best overload by matching the parameter modifiers at the call site to the parameter modifiers used in the method call.</span></span>
 
<span data-ttu-id="a6f0b-117">属性不是变量，因此不能作为 `out` 参数传递。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-117">Properties are not variables and therefore cannot be passed as `out` parameters.</span></span>
  
 <span data-ttu-id="a6f0b-118">有关传递数组的信息，请参阅[使用 ref 和 out 传递数组](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-118">For information about passing arrays, see [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="a6f0b-119">不能将 `in`、`ref` 和 `out` 关键字用于以下几种方法：</span><span class="sxs-lookup"><span data-stu-id="a6f0b-119">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
-   <span data-ttu-id="a6f0b-120">异步方法，通过使用 [async](../../../csharp/language-reference/keywords/async.md) 修饰符定义。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-120">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
-   <span data-ttu-id="a6f0b-121">迭代器方法，包括 [yield return](../../../csharp/language-reference/keywords/yield.md) 或 `yield break` 语句。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-121">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

## <a name="declaring-out-arguments"></a><span data-ttu-id="a6f0b-122">声明 `out` 参数</span><span class="sxs-lookup"><span data-stu-id="a6f0b-122">Declaring `out` arguments</span></span>   

 <span data-ttu-id="a6f0b-123">如果希望方法返回多个值，可以声明具有多个 `out` 参数的方法。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-123">Declaring a method with `out` arguments is useful when you want a method to return multiple values.</span></span> <span data-ttu-id="a6f0b-124">下面的示例使用 `out` 返回具有单个方法调用的三个变量。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-124">The following example uses `out` to return three variables with a single method call.</span></span> <span data-ttu-id="a6f0b-125">注意，第三个参数赋 null 值。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-125">Note that the third argument is assigned to null.</span></span> <span data-ttu-id="a6f0b-126">这使得方法可以有选择地返回值。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-126">This enables methods to return values optionally.</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#3)]  

 <span data-ttu-id="a6f0b-127">[重试模式](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md)会返回一个 `bool`，指示某个操作是成功还是失败，并在 `out` 参数中返回该操作生成的值。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-127">The [Try pattern](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) involves returning a `bool` to indicate whether an operation succeeded or failed, and returning the value produced by the operation in an `out` argument.</span></span> <span data-ttu-id="a6f0b-128">许多分析方法（如 [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) 方法）都采用此模式。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-128">A number of parsing methods, such as the [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) method, use this pattern.</span></span>
   
## <a name="calling-a-method-with-an-out-argument"></a><span data-ttu-id="a6f0b-129">调用具有 `out` 参数的方法</span><span class="sxs-lookup"><span data-stu-id="a6f0b-129">Calling a method with an `out` argument</span></span>

<span data-ttu-id="a6f0b-130">在 C# 6 及更早版本中，必须先在单独的语句中声明变量，然后才能将其作为 `out` 参数传递。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-130">In C# 6 and earlier, you must declare a variable in a separate statement before you pass it as an `out` argument.</span></span> <span data-ttu-id="a6f0b-131">下面的示例先声明了变量 `number`，然后再将它传递给将字符串转换为数字的 [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) 方法。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-131">The following example declares a variable named `number` before it is passed to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method, which attempts to convert a string to a number.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#4)]  

<span data-ttu-id="a6f0b-132">从 C# 7.0 开始，可以在方法调用的参数列表而不是单独的变量声明中声明 `out` 变量。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-132">Starting with C# 7.0, you can declare the `out` variable in the argument list of the method call, rather than in a separate variable declaration.</span></span> <span data-ttu-id="a6f0b-133">这使得代码更简洁可读，还能防止在方法调用之前无意中向该变量赋值。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-133">This produces more compact, readable code, and also prevents you from inadvertently assigning a value to the variable before the method call.</span></span> <span data-ttu-id="a6f0b-134">下面的示例与上一个示例基本相同，不同之处在于它在对 [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) 方法的调用中定义了 `number` 变量。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-134">The following example is like the previous example, except that it defines the `number` variable in the call to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#5)]  
   
<span data-ttu-id="a6f0b-135">在上一个示例中，`number` 变量被强类型化为 `int`。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-135">In the previous example, the `number` variable is strongly typed as an `int`.</span></span> <span data-ttu-id="a6f0b-136">你也可以声明一个隐式类型本地变量，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="a6f0b-136">You can also declare an implicitly typed local variable, as the following example does.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#6)]  
   
## <a name="c-language-specification"></a><span data-ttu-id="a6f0b-137">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="a6f0b-137">C# Language Specification</span></span>  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a6f0b-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6f0b-138">See Also</span></span>

- [<span data-ttu-id="a6f0b-139">C# 参考</span><span class="sxs-lookup"><span data-stu-id="a6f0b-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="a6f0b-140">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="a6f0b-140">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a6f0b-141">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="a6f0b-141">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="a6f0b-142">方法参数</span><span class="sxs-lookup"><span data-stu-id="a6f0b-142">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)
