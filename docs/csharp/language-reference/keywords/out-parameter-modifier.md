---
title: "out 参数修饰符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.assetid: 3fce0dc5-03f4-4faa-bd61-36c41bc6baf1
caps.latest.revision: 9
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
ms.sourcegitcommit: 59e445ac27f07c85d9e98c5f595cf5f935f75443
ms.openlocfilehash: 9a0a488c6f444608a335cd990847774fb6fe9e3f
ms.contentlocale: zh-cn
ms.lasthandoff: 08/31/2017

---
# <a name="out-parameter-modifier-c-reference"></a><span data-ttu-id="5c0e4-102">out 参数修饰符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="5c0e4-102">out parameter modifier (C# Reference)</span></span>
<span data-ttu-id="5c0e4-103">`out` 关键字通过引用传递参数。</span><span class="sxs-lookup"><span data-stu-id="5c0e4-103">The `out` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="5c0e4-104">它与 [ref](../../../csharp/language-reference/keywords/ref.md) 关键字相似，只不过 `ref` 要求在传递之前初始化变量。</span><span class="sxs-lookup"><span data-stu-id="5c0e4-104">It is like the [ref](../../../csharp/language-reference/keywords/ref.md) keyword, except that `ref` requires that the variable be initialized before it is passed.</span></span> <span data-ttu-id="5c0e4-105">若要使用 `out` 参数，方法定义和调用方法均必须显式使用 `out` 关键字。</span><span class="sxs-lookup"><span data-stu-id="5c0e4-105">To use an `out` parameter, both the method definition and the calling method must explicitly use the `out` keyword.</span></span> <span data-ttu-id="5c0e4-106">例如: </span><span class="sxs-lookup"><span data-stu-id="5c0e4-106">For example:</span></span>  
  
 <span data-ttu-id="5c0e4-107">[!code-cs[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/out/out-1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5c0e4-107">[!code-cs[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/out/out-1.cs)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="5c0e4-108">`out` 关键字也可与泛型类型参数结合使用，以指定该类型参数是协变参数。</span><span class="sxs-lookup"><span data-stu-id="5c0e4-108">The `out` keyword can also be used with a generic type parameter to specify that the type parameter is covariant.</span></span> <span data-ttu-id="5c0e4-109">有关在此上下文中使用 `out` 关键字的详细信息，请参阅 [out（泛型修饰符）](../../../csharp/language-reference/keywords/out-generic-modifier.md)。</span><span class="sxs-lookup"><span data-stu-id="5c0e4-109">For more information on the use of the `out` keyword in this context, see [out (Generic Modifier)](../../../csharp/language-reference/keywords/out-generic-modifier.md).</span></span>
  
 <span data-ttu-id="5c0e4-110">作为 `out` 参数传递的变量在方法调用中传递之前不必进行初始化。</span><span class="sxs-lookup"><span data-stu-id="5c0e4-110">Variables passed as `out` arguments do not have to be initialized before being passed in a method call.</span></span> <span data-ttu-id="5c0e4-111">但是，被调用的方法需要在返回之前赋一个值。</span><span class="sxs-lookup"><span data-stu-id="5c0e4-111">However, the called method is required to assign a value before the method returns.</span></span>  
  
 <span data-ttu-id="5c0e4-112">尽管 `ref` 和 `out` 关键字会导致不同的运行时行为，它们并不被视为编译时方法签名的一部分。</span><span class="sxs-lookup"><span data-stu-id="5c0e4-112">Although the `ref` and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="5c0e4-113">因此，如果唯一的不同是一个方法采用 `ref` 参数，而另一个方法采用 `out` 参数，则无法重载这两个方法。</span><span class="sxs-lookup"><span data-stu-id="5c0e4-113">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="5c0e4-114">例如，以下代码将不会编译：</span><span class="sxs-lookup"><span data-stu-id="5c0e4-114">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="5c0e4-115">但是，如果一个方法采用 `ref` 或 `out` 参数，而另一个方法采用其他参数，则可以完成重载，如：</span><span class="sxs-lookup"><span data-stu-id="5c0e4-115">Overloading is legal, however, if one method takes a `ref` or `out` argument and the other uses neither, like this:</span></span>  
  
 <span data-ttu-id="5c0e4-116">[!code-cs[csrefKeywordsMethodParams#3](../../../../samples/snippets/csharp/language-reference/keywords/out/out-3.cs)]</span><span class="sxs-lookup"><span data-stu-id="5c0e4-116">[!code-cs[csrefKeywordsMethodParams#3](../../../../samples/snippets/csharp/language-reference/keywords/out/out-3.cs)]</span></span>  
  
 <span data-ttu-id="5c0e4-117">属性不是变量，因此不能作为 `out` 参数传递。</span><span class="sxs-lookup"><span data-stu-id="5c0e4-117">Properties are not variables and therefore cannot be passed as `out` parameters.</span></span>  
  
 <span data-ttu-id="5c0e4-118">有关传递数组的信息，请参阅[使用 ref 和 out 传递数组](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)。</span><span class="sxs-lookup"><span data-stu-id="5c0e4-118">For information about passing arrays, see [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="5c0e4-119">你不能将 `ref` 和 `out` 关键字用于以下几种方法：</span><span class="sxs-lookup"><span data-stu-id="5c0e4-119">You can't use the `ref` and `out` keywords for the following kinds of methods:</span></span>  
  
-   <span data-ttu-id="5c0e4-120">异步方法，通过使用 [async](../../../csharp/language-reference/keywords/async.md) 修饰符定义。</span><span class="sxs-lookup"><span data-stu-id="5c0e4-120">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
-   <span data-ttu-id="5c0e4-121">迭代器方法，包括 [yield return](../../../csharp/language-reference/keywords/yield.md) 或 `yield break` 语句。</span><span class="sxs-lookup"><span data-stu-id="5c0e4-121">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

## <a name="declaring-out-arguments"></a><span data-ttu-id="5c0e4-122">声明 `out` 参数</span><span class="sxs-lookup"><span data-stu-id="5c0e4-122">Declaring `out` arguments</span></span>   

 <span data-ttu-id="5c0e4-123">如果希望方法返回多个值，可以声明具有多个 `out` 参数的方法。</span><span class="sxs-lookup"><span data-stu-id="5c0e4-123">Declaring a method with `out` arguments is useful when you want a method to return multiple values.</span></span> <span data-ttu-id="5c0e4-124">下面的示例使用 `out` 返回具有单个方法调用的三个变量。</span><span class="sxs-lookup"><span data-stu-id="5c0e4-124">The following example uses `out` to return three variables with a single method call.</span></span> <span data-ttu-id="5c0e4-125">注意，第三个参数赋 null 值。</span><span class="sxs-lookup"><span data-stu-id="5c0e4-125">Note that the third argument is assigned to null.</span></span> <span data-ttu-id="5c0e4-126">这使得方法可以有选择地返回值。</span><span class="sxs-lookup"><span data-stu-id="5c0e4-126">This enables methods to return values optionally.</span></span>  
  
 <span data-ttu-id="5c0e4-127">[!code-cs[csrefKeywordsMethodParams#4](../../../../samples/snippets/csharp/language-reference/keywords/out/out-4.cs)]</span><span class="sxs-lookup"><span data-stu-id="5c0e4-127">[!code-cs[csrefKeywordsMethodParams#4](../../../../samples/snippets/csharp/language-reference/keywords/out/out-4.cs)]</span></span>  

 <span data-ttu-id="5c0e4-128">[重试模式](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md)会返回一个 `bool`，指示某个操作是成功还是失败，并在 `out` 参数中返回该操作生成的值。</span><span class="sxs-lookup"><span data-stu-id="5c0e4-128">The [Try pattern](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) involves returning a `bool` to indicate whether an operation succeeded and failed, and returning the value produced by the operation in an `out` argument.</span></span> <span data-ttu-id="5c0e4-129">许多分析方法（如 [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) 方法）都采用此模式。</span><span class="sxs-lookup"><span data-stu-id="5c0e4-129">A number of parsing methods, such as the [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) method, use this pattern.</span></span>
   
## <a name="calling-a-method-with-an-out-argument"></a><span data-ttu-id="5c0e4-130">调用具有 `out` 参数的方法</span><span class="sxs-lookup"><span data-stu-id="5c0e4-130">Calling a method with an `out` argument</span></span>

<span data-ttu-id="5c0e4-131">在 C# 6 及更早版本中，必须先在单独的语句中声明变量，然后才能将其作为 `out` 参数传递。</span><span class="sxs-lookup"><span data-stu-id="5c0e4-131">In C# 6 and earlier, you must declare a variable in a separate statement before you pass it as an `out` argument.</span></span> <span data-ttu-id="5c0e4-132">下面的示例先声明了变量 `number`，然后再将它传递给将字符串转换为数字的 [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) 方法。</span><span class="sxs-lookup"><span data-stu-id="5c0e4-132">The following example declares a variable named `number` before it is passed to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method, which attempts to convert a string to a number.</span></span>

 <span data-ttu-id="5c0e4-133">[!code-cs[csrefKeywordsMethodParams#5](../../../../samples/snippets/csharp/language-reference/keywords/out/out-5.cs)]</span><span class="sxs-lookup"><span data-stu-id="5c0e4-133">[!code-cs[csrefKeywordsMethodParams#5](../../../../samples/snippets/csharp/language-reference/keywords/out/out-5.cs)]</span></span>  

<span data-ttu-id="5c0e4-134">从 C# 7 开始，可以在方法调用的参数列表而不是单独的变量声明中声明 `out` 变量。</span><span class="sxs-lookup"><span data-stu-id="5c0e4-134">Starting with C# 7, you can declare the `out` variable in the argument list of the method call, rather than in a separate variable declaration.</span></span> <span data-ttu-id="5c0e4-135">这使得代码更简洁可读，还能防止在方法调用之前无意中向该变量赋值。</span><span class="sxs-lookup"><span data-stu-id="5c0e4-135">This produces more compact, readable code, and also prevents you from inadvertently assigning a value to the variable before the method call.</span></span> <span data-ttu-id="5c0e4-136">下面的示例与上一个示例基本相同，不同之处在于它在对 [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) 方法的调用中定义了 `number` 变量。</span><span class="sxs-lookup"><span data-stu-id="5c0e4-136">The following example is like the previous example, except that it defines the `number` variable in the call to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method.</span></span>

 <span data-ttu-id="5c0e4-137">[!code-cs[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/out/out-6.cs)]</span><span class="sxs-lookup"><span data-stu-id="5c0e4-137">[!code-cs[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/out/out-6.cs)]</span></span>  
   
<span data-ttu-id="5c0e4-138">在上一个示例中，`number` 变量被强类型化为 `int`。</span><span class="sxs-lookup"><span data-stu-id="5c0e4-138">In the previous example, the `number` variable is strongly typed as an `int`.</span></span> <span data-ttu-id="5c0e4-139">你也可以声明一个隐式类型本地变量，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="5c0e4-139">You can also declare an implicitly typed local variable, as the following example does.</span></span>

 <span data-ttu-id="5c0e4-140">[!code-cs[csrefKeywordsMethodParams#7](../../../../samples/snippets/csharp/language-reference/keywords/out/out-7.cs)]</span><span class="sxs-lookup"><span data-stu-id="5c0e4-140">[!code-cs[csrefKeywordsMethodParams#7](../../../../samples/snippets/csharp/language-reference/keywords/out/out-7.cs)]</span></span>  
   
## <a name="c-language-specification"></a><span data-ttu-id="5c0e4-141">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="5c0e4-141">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5c0e4-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c0e4-142">See Also</span></span>  
 <span data-ttu-id="5c0e4-143">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="5c0e4-143">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="5c0e4-144">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5c0e4-144">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="5c0e4-145">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="5c0e4-145">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 [<span data-ttu-id="5c0e4-146">方法参数</span><span class="sxs-lookup"><span data-stu-id="5c0e4-146">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)

