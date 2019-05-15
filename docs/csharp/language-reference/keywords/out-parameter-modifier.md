---
title: out 参数修饰符 - C# 参考
ms.custom: seodec18
ms.date: 03/26/2019
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.openlocfilehash: 704b66e6cdec5caa47f85ed8e3acbd2a6a73b730
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598245"
---
# <a name="out-parameter-modifier-c-reference"></a><span data-ttu-id="0b071-102">out 参数修饰符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="0b071-102">out parameter modifier (C# Reference)</span></span>
<span data-ttu-id="0b071-103">`out` 关键字通过引用传递参数。</span><span class="sxs-lookup"><span data-stu-id="0b071-103">The `out` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="0b071-104">它让形参成为实参的别名，这必须是变量。</span><span class="sxs-lookup"><span data-stu-id="0b071-104">It makes the formal parameter an alias for the argument, which must be a variable.</span></span> <span data-ttu-id="0b071-105">换而言之，对形参执行的任何操作都是对实参执行的。</span><span class="sxs-lookup"><span data-stu-id="0b071-105">In other words, any operation on the parameter is made on the argument.</span></span> <span data-ttu-id="0b071-106">它与 [ref](ref.md) 关键字相似，只不过 `ref` 要求在传递之前初始化变量。</span><span class="sxs-lookup"><span data-stu-id="0b071-106">It is like the [ref](ref.md) keyword, except that `ref` requires that the variable be initialized before it is passed.</span></span> <span data-ttu-id="0b071-107">它也类似于 [in](in-parameter-modifier.md) 关键字，只不过 `in` 不允许通过调用方法来修改参数值。</span><span class="sxs-lookup"><span data-stu-id="0b071-107">It is also like the [in](in-parameter-modifier.md) keyword, except that `in` does not allow the called method to modify the argument value.</span></span> <span data-ttu-id="0b071-108">若要使用 `out` 参数，方法定义和调用方法均必须显式使用 `out` 关键字。</span><span class="sxs-lookup"><span data-stu-id="0b071-108">To use an `out` parameter, both the method definition and the calling method must explicitly use the `out` keyword.</span></span> <span data-ttu-id="0b071-109">例如:</span><span class="sxs-lookup"><span data-stu-id="0b071-109">For example:</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#1)]  

> [!NOTE] 
> <span data-ttu-id="0b071-110">`out` 关键字也可与泛型类型参数结合使用，以指定该类型参数是协变参数。</span><span class="sxs-lookup"><span data-stu-id="0b071-110">The `out` keyword can also be used with a generic type parameter to specify that the type parameter is covariant.</span></span> <span data-ttu-id="0b071-111">有关在此上下文中使用 `out` 关键字的详细信息，请参阅 [out（泛型修饰符）](out-generic-modifier.md)。</span><span class="sxs-lookup"><span data-stu-id="0b071-111">For more information on the use of the `out` keyword in this context, see [out (Generic Modifier)](out-generic-modifier.md).</span></span>
  
<span data-ttu-id="0b071-112">作为 `out` 参数传递的变量在方法调用中传递之前不必进行初始化。</span><span class="sxs-lookup"><span data-stu-id="0b071-112">Variables passed as `out` arguments do not have to be initialized before being passed in a method call.</span></span> <span data-ttu-id="0b071-113">但是，被调用的方法需要在返回之前赋一个值。</span><span class="sxs-lookup"><span data-stu-id="0b071-113">However, the called method is required to assign a value before the method returns.</span></span>  
  
<span data-ttu-id="0b071-114">`in`、`ref` 和 `out` 关键字不被视为用于重载决议的方法签名的一部分。</span><span class="sxs-lookup"><span data-stu-id="0b071-114">The `in`, `ref`, and `out` keywords are not considered part of the method signature for the purpose of overload resolution.</span></span> <span data-ttu-id="0b071-115">因此，如果唯一的不同是一个方法采用 `ref` 或 `in` 参数，而另一个方法采用 `out` 参数，则无法重载这两个方法。</span><span class="sxs-lookup"><span data-stu-id="0b071-115">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="0b071-116">例如，以下代码将不会编译：</span><span class="sxs-lookup"><span data-stu-id="0b071-116">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="0b071-117">但是，如果一个方法采用 `ref`、`in` 或 `out` 参数，而另一个方法采用其他参数，则可以完成重载，如：</span><span class="sxs-lookup"><span data-stu-id="0b071-117">Overloading is legal, however, if one method takes a `ref`, `in`, or `out` argument and the other has none of those modifiers, like this:</span></span>  
  
[!code-csharp[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#2)]  

<span data-ttu-id="0b071-118">编译器通过将调用站点上的参数修饰符与方法调用中使用的参数修饰符进行匹配，从而选择最佳重载。</span><span class="sxs-lookup"><span data-stu-id="0b071-118">The compiler chooses the best overload by matching the parameter modifiers at the call site to the parameter modifiers used in the method call.</span></span>
 
<span data-ttu-id="0b071-119">属性不是变量，因此不能作为 `out` 参数传递。</span><span class="sxs-lookup"><span data-stu-id="0b071-119">Properties are not variables and therefore cannot be passed as `out` parameters.</span></span>
  
<span data-ttu-id="0b071-120">不能将 `in`、`ref` 和 `out` 关键字用于以下几种方法：</span><span class="sxs-lookup"><span data-stu-id="0b071-120">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="0b071-121">异步方法，通过使用 [async](../../../csharp/language-reference/keywords/async.md) 修饰符定义。</span><span class="sxs-lookup"><span data-stu-id="0b071-121">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
- <span data-ttu-id="0b071-122">迭代器方法，包括 [yield return](../../../csharp/language-reference/keywords/yield.md) 或 `yield break` 语句。</span><span class="sxs-lookup"><span data-stu-id="0b071-122">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

## <a name="declaring-out-parameters"></a><span data-ttu-id="0b071-123">声明 `out` 参数</span><span class="sxs-lookup"><span data-stu-id="0b071-123">Declaring `out` parameters</span></span>   

<span data-ttu-id="0b071-124">使用 `out` 参数声明方法是返回多个值的经典解决方法。</span><span class="sxs-lookup"><span data-stu-id="0b071-124">Declaring a method with `out` arguments is a classic workaround to return multiple values.</span></span> <span data-ttu-id="0b071-125">自 C# 7.0 起，建议在类似方案中使用[元组](../../tuples.md)。</span><span class="sxs-lookup"><span data-stu-id="0b071-125">Beginning with C# 7.0, consider [tuples](../../tuples.md) for similar scenarios.</span></span> <span data-ttu-id="0b071-126">下面的示例使用 `out` 返回具有单个方法调用的三个变量。</span><span class="sxs-lookup"><span data-stu-id="0b071-126">The following example uses `out` to return three variables with a single method call.</span></span> <span data-ttu-id="0b071-127">注意，第三个参数赋 null 值。</span><span class="sxs-lookup"><span data-stu-id="0b071-127">Note that the third argument is assigned to null.</span></span> <span data-ttu-id="0b071-128">这使得方法可以有选择地返回值。</span><span class="sxs-lookup"><span data-stu-id="0b071-128">This enables methods to return values optionally.</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#3)]  

## <a name="calling-a-method-with-an-out-argument"></a><span data-ttu-id="0b071-129">调用具有 `out` 参数的方法</span><span class="sxs-lookup"><span data-stu-id="0b071-129">Calling a method with an `out` argument</span></span>

<span data-ttu-id="0b071-130">在 C# 6 及更早版本中，必须先在单独的语句中声明变量，然后才能将其作为 `out` 参数传递。</span><span class="sxs-lookup"><span data-stu-id="0b071-130">In C# 6 and earlier, you must declare a variable in a separate statement before you pass it as an `out` argument.</span></span> <span data-ttu-id="0b071-131">下面的示例先声明了变量 `number`，然后再将它传递给将字符串转换为数字的 [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) 方法。</span><span class="sxs-lookup"><span data-stu-id="0b071-131">The following example declares a variable named `number` before it is passed to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method, which attempts to convert a string to a number.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#4)]  

<span data-ttu-id="0b071-132">从 C# 7.0 开始，可以在方法调用的参数列表而不是单独的变量声明中声明 `out` 变量。</span><span class="sxs-lookup"><span data-stu-id="0b071-132">Starting with C# 7.0, you can declare the `out` variable in the argument list of the method call, rather than in a separate variable declaration.</span></span> <span data-ttu-id="0b071-133">这使得代码更简洁可读，还能防止在方法调用之前无意中向该变量赋值。</span><span class="sxs-lookup"><span data-stu-id="0b071-133">This produces more compact, readable code, and also prevents you from inadvertently assigning a value to the variable before the method call.</span></span> <span data-ttu-id="0b071-134">下面的示例与上一个示例基本相同，不同之处在于它在对 [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) 方法的调用中定义了 `number` 变量。</span><span class="sxs-lookup"><span data-stu-id="0b071-134">The following example is like the previous example, except that it defines the `number` variable in the call to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#5)]  
   
<span data-ttu-id="0b071-135">在上一个示例中，`number` 变量被强类型化为 `int`。</span><span class="sxs-lookup"><span data-stu-id="0b071-135">In the previous example, the `number` variable is strongly typed as an `int`.</span></span> <span data-ttu-id="0b071-136">你也可以声明一个隐式类型本地变量，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="0b071-136">You can also declare an implicitly typed local variable, as the following example does.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#6)]  
   
## <a name="c-language-specification"></a><span data-ttu-id="0b071-137">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="0b071-137">C# Language Specification</span></span>  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0b071-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b071-138">See also</span></span>

- [<span data-ttu-id="0b071-139">C# 参考</span><span class="sxs-lookup"><span data-stu-id="0b071-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="0b071-140">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="0b071-140">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="0b071-141">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="0b071-141">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="0b071-142">方法参数</span><span class="sxs-lookup"><span data-stu-id="0b071-142">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)
