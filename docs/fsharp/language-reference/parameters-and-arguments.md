---
title: "参数和自变量 (F#)"
description: "了解有关定义参数并将自变量传递给函数、 方法和属性的 F # 语言支持。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9b37a5c4-9263-4513-822a-fbb0d1004254
ms.openlocfilehash: 50f54bacd9ba7ec20a7151794734f93200df9f2d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="parameters-and-arguments"></a><span data-ttu-id="74ba0-104">形参和实参</span><span class="sxs-lookup"><span data-stu-id="74ba0-104">Parameters and Arguments</span></span>

<span data-ttu-id="74ba0-105">本主题介绍用于定义参数并将自变量传递给函数、 方法和属性的语言支持。</span><span class="sxs-lookup"><span data-stu-id="74ba0-105">This topic describes language support for defining parameters and passing arguments to functions, methods, and properties.</span></span> <span data-ttu-id="74ba0-106">它包括有关如何通过引用传递以及如何定义和使用可以采用数量可变的自变量的方法的信息。</span><span class="sxs-lookup"><span data-stu-id="74ba0-106">It includes information about how to pass by reference, and how to define and use methods that can take a variable number of arguments.</span></span>


## <a name="parameters-and-arguments"></a><span data-ttu-id="74ba0-107">形参和实参</span><span class="sxs-lookup"><span data-stu-id="74ba0-107">Parameters and Arguments</span></span>
<span data-ttu-id="74ba0-108">术语*参数*用于描述应提供的值的名称。</span><span class="sxs-lookup"><span data-stu-id="74ba0-108">The term *parameter* is used to describe the names for values that are expected to be supplied.</span></span> <span data-ttu-id="74ba0-109">术语*参数*用于为每个参数提供的值。</span><span class="sxs-lookup"><span data-stu-id="74ba0-109">The term *argument* is used for the values provided for each parameter.</span></span>

<span data-ttu-id="74ba0-110">元组或扩充窗体，或两个的某种组合中，可以指定参数。</span><span class="sxs-lookup"><span data-stu-id="74ba0-110">Parameters can be specified in tuple or curried form, or in some combination of the two.</span></span> <span data-ttu-id="74ba0-111">可以使用显式参数名称传递参数。</span><span class="sxs-lookup"><span data-stu-id="74ba0-111">You can pass arguments by using an explicit parameter name.</span></span> <span data-ttu-id="74ba0-112">可以指定为可选并给定一个默认值的方法的参数。</span><span class="sxs-lookup"><span data-stu-id="74ba0-112">Parameters of methods can be specified as optional and given a default value.</span></span>


## <a name="parameter-patterns"></a><span data-ttu-id="74ba0-113">参数模式</span><span class="sxs-lookup"><span data-stu-id="74ba0-113">Parameter Patterns</span></span>
<span data-ttu-id="74ba0-114">一般情况下，提供给函数和方法的参数都是由空格分隔的模式。</span><span class="sxs-lookup"><span data-stu-id="74ba0-114">Parameters supplied to functions and methods are, in general, patterns separated by spaces.</span></span> <span data-ttu-id="74ba0-115">这意味着，原则上，任何的模式中所述[匹配表达式](match-expressions.md)可以用于在参数列表的函数或成员。</span><span class="sxs-lookup"><span data-stu-id="74ba0-115">This means that, in principle, any of the patterns described in [Match Expressions](match-expressions.md) can be used in a parameter list for a function or member.</span></span>

<span data-ttu-id="74ba0-116">方法通常使用传递自变量的元组形式。</span><span class="sxs-lookup"><span data-stu-id="74ba0-116">Methods usually use the tuple form of passing arguments.</span></span> <span data-ttu-id="74ba0-117">这能实现从其他.NET 语言的角度来看更加清晰的结果，因为元组形式与在.NET 方法中传递自变量的方式相匹配。</span><span class="sxs-lookup"><span data-stu-id="74ba0-117">This achieves a clearer result from the perspective of other .NET languages because the tuple form matches the way arguments are passed in .NET methods.</span></span>

<span data-ttu-id="74ba0-118">扩充窗体最常用于通过使用创建的函数`let`绑定。</span><span class="sxs-lookup"><span data-stu-id="74ba0-118">The curried form is most often used with functions created by using `let` bindings.</span></span>

<span data-ttu-id="74ba0-119">下面的伪代码演示元组和扩充自变量的示例。</span><span class="sxs-lookup"><span data-stu-id="74ba0-119">The following pseudocode shows examples of tuple and curried arguments.</span></span>

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

<span data-ttu-id="74ba0-120">组合的窗体还可能某些自变量是元组中，还有一些不是。</span><span class="sxs-lookup"><span data-stu-id="74ba0-120">Combined forms are possible when some arguments are in tuples and some are not.</span></span>

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

<span data-ttu-id="74ba0-121">其他模式还可用于在参数列表中，但如果参数的模式不匹配所有可能的输入，则可能有不完整的匹配项在运行时。</span><span class="sxs-lookup"><span data-stu-id="74ba0-121">Other patterns can also be used in parameter lists, but if the parameter pattern does not match all possible inputs, there might be an incomplete match at run time.</span></span> <span data-ttu-id="74ba0-122">异常`MatchFailureException`自变量的值与参数列表中指定的模式不匹配时，将生成。</span><span class="sxs-lookup"><span data-stu-id="74ba0-122">The exception `MatchFailureException` is generated when the value of an argument does not match the patterns specified in the parameter list.</span></span> <span data-ttu-id="74ba0-123">当参数模式允许的不完整的匹配项时，编译器会发出警告。</span><span class="sxs-lookup"><span data-stu-id="74ba0-123">The compiler issues a warning when a parameter pattern allows for incomplete matches.</span></span> <span data-ttu-id="74ba0-124">至少一个其他的模式是通常用于参数列表和通配符模式。</span><span class="sxs-lookup"><span data-stu-id="74ba0-124">At least one other pattern is commonly useful for parameter lists, and that is the wildcard pattern.</span></span> <span data-ttu-id="74ba0-125">你只想要忽略提供任何自变量时，可使用参数列表中的通配符模式。</span><span class="sxs-lookup"><span data-stu-id="74ba0-125">You use the wildcard pattern in a parameter list when you simply want to ignore any arguments that are supplied.</span></span> <span data-ttu-id="74ba0-126">下面的代码演示如何使用自变量列表中的通配符模式。</span><span class="sxs-lookup"><span data-stu-id="74ba0-126">The following code illustrates the use of the wildcard pattern in an argument list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

<span data-ttu-id="74ba0-127">通配符模式可以是在不需要传递中的自变量时很有用，如所到某个程序的主入口点时您不感兴趣通常提供作为字符串数组，如以下代码所示的命令行自变量。</span><span class="sxs-lookup"><span data-stu-id="74ba0-127">The wildcard pattern can be useful whenever you do not need the arguments passed in, such as in the main entry point to a program, when you are not interested in the command-line arguments that are normally supplied as a string array, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

<span data-ttu-id="74ba0-128">有时使用自变量中的其他模式包括`as`模式，且可区分的联合以及活动模式与关联的标识符模式。</span><span class="sxs-lookup"><span data-stu-id="74ba0-128">Other patterns that are sometimes used in arguments are the `as` pattern, and identifier patterns associated with discriminated unions and active patterns.</span></span> <span data-ttu-id="74ba0-129">可以使用单一大小写的可区分联合模式，如下所示。</span><span class="sxs-lookup"><span data-stu-id="74ba0-129">You can use the single-case discriminated union pattern as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

<span data-ttu-id="74ba0-130">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="74ba0-130">The output is as follows.</span></span>

```
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

<span data-ttu-id="74ba0-131">活动模式作为参数，例如，如果可将自变量转换为所需的格式，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="74ba0-131">Active patterns can be useful as parameters, for example, when transforming an argument into a desired format, as in the following example:</span></span>

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

<span data-ttu-id="74ba0-132">你可以使用`as`模式将匹配的值存储为本地值，如以下代码行所示。</span><span class="sxs-lookup"><span data-stu-id="74ba0-132">You can use the `as` pattern to store a matched value as a local value, as is shown in the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

<span data-ttu-id="74ba0-133">偶尔使用的另一种模式是离开通过提供作为函数的正文未命名的最后一个参数的函数，对的隐式的自变量将立即执行模式匹配的 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="74ba0-133">Another pattern that is used occasionally is a function that leaves the last argument unnamed by providing, as the body of the function, a lambda expression that immediately performs a pattern match on the implicit argument.</span></span> <span data-ttu-id="74ba0-134">此示例是代码的下面行。</span><span class="sxs-lookup"><span data-stu-id="74ba0-134">An example of this is the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

<span data-ttu-id="74ba0-135">此代码定义一个函数，它接受泛型列表，并返回`true`如果列表为空，和`false`否则为。</span><span class="sxs-lookup"><span data-stu-id="74ba0-135">This code defines a function that takes a generic list and returns `true` if the list is empty, and `false` otherwise.</span></span> <span data-ttu-id="74ba0-136">此类技术的使用会使代码更难阅读。</span><span class="sxs-lookup"><span data-stu-id="74ba0-136">The use of such techniques can make code more difficult to read.</span></span>

<span data-ttu-id="74ba0-137">有时，涉及不完整的匹配项的模式非常有用，例如，如果你知道你的程序中的列表具有只有三个元素，则可能使用类似于下面的模式参数列表中。</span><span class="sxs-lookup"><span data-stu-id="74ba0-137">Occasionally, patterns that involve incomplete matches are useful, for example, if you know that the lists in your program have only three elements, you might use a pattern like the following in a parameter list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

<span data-ttu-id="74ba0-138">利用具有不完全匹配的模式最留待快速原型制作和其他临时使用。</span><span class="sxs-lookup"><span data-stu-id="74ba0-138">The use of patterns that have incomplete matches is best reserved for quick prototyping and other temporary uses.</span></span> <span data-ttu-id="74ba0-139">编译器会发出此类代码的警告。</span><span class="sxs-lookup"><span data-stu-id="74ba0-139">The compiler will issue a warning for such code.</span></span> <span data-ttu-id="74ba0-140">这种模式不能涵盖所有可能的输入的一般情况下，因此不适合组件 Api。</span><span class="sxs-lookup"><span data-stu-id="74ba0-140">Such patterns cannot cover the general case of all possible inputs and therefore are not suitable for component APIs.</span></span>

## <a name="named-arguments"></a><span data-ttu-id="74ba0-141">命名实参</span><span class="sxs-lookup"><span data-stu-id="74ba0-141">Named Arguments</span></span>
<span data-ttu-id="74ba0-142">可以按位置在以逗号分隔的自变量列表中，指定方法的参数，或可以将它们传递到方法显式通过提供名称后, 跟一个等号和要在中传递的值。</span><span class="sxs-lookup"><span data-stu-id="74ba0-142">Arguments for methods can be specified by position in a comma-separated argument list, or they can be passed to a method explicitly by providing the name, followed by an equal sign and the value to be passed in.</span></span> <span data-ttu-id="74ba0-143">如果指定提供名称，它们可以出现在不同的声明中所用顺序。</span><span class="sxs-lookup"><span data-stu-id="74ba0-143">If specified by providing the name, they can appear in a different order from that used in the declaration.</span></span>

<span data-ttu-id="74ba0-144">命名自变量可使代码更具可读性且更适应某些类型的 API，如重新排序方法参数中的更改。</span><span class="sxs-lookup"><span data-stu-id="74ba0-144">Named arguments can make code more readable and more adaptable to certain types of changes in the API, such as a reordering of method parameters.</span></span>

<span data-ttu-id="74ba0-145">命名自变量仅允许使用方法，不能为`let`-绑定函数、 函数值或 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="74ba0-145">Named arguments are allowed only for methods, not for `let`-bound functions, function values, or lambda expressions.</span></span>

<span data-ttu-id="74ba0-146">下面的代码示例演示了利用命名自变量。</span><span class="sxs-lookup"><span data-stu-id="74ba0-146">The following code example demonstrates the use of named arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

<span data-ttu-id="74ba0-147">在类构造函数的调用中，你可以通过使用类似于命名自变量的语法设置类的属性的值。</span><span class="sxs-lookup"><span data-stu-id="74ba0-147">In a call to a class constructor, you can set the values of properties of the class by using a syntax similar to that of named arguments.</span></span> <span data-ttu-id="74ba0-148">下面的示例演示了此语法。</span><span class="sxs-lookup"><span data-stu-id="74ba0-148">The following example shows this syntax.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="74ba0-149">有关详细信息，请参阅[构造函数 （F #）](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05)。</span><span class="sxs-lookup"><span data-stu-id="74ba0-149">For more information, see [Constructors (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span></span>

## <a name="optional-parameters"></a><span data-ttu-id="74ba0-150">可选参数</span><span class="sxs-lookup"><span data-stu-id="74ba0-150">Optional Parameters</span></span>
<span data-ttu-id="74ba0-151">可以使用问号的前面的参数名称来指定一种方法的可选参数。</span><span class="sxs-lookup"><span data-stu-id="74ba0-151">You can specify an optional parameter for a method by using a question mark in front of the parameter name.</span></span> <span data-ttu-id="74ba0-152">可选参数将解释为 F # 选项类型，因此你可以查询它们中的查询选项类型，通过使用正则方式`match`具有表达式`Some`和`None`。</span><span class="sxs-lookup"><span data-stu-id="74ba0-152">Optional parameters are interpreted as the F# option type, so you can query them in the regular way that option types are queried, by using a `match` expression with `Some` and `None`.</span></span> <span data-ttu-id="74ba0-153">仅适用于成员，通过使用创建的函数上不允许使用可选参数`let`绑定。</span><span class="sxs-lookup"><span data-stu-id="74ba0-153">Optional parameters are permitted only on members, not on functions created by using `let` bindings.</span></span>

<span data-ttu-id="74ba0-154">你还可以使用一个函数`defaultArg`，这会设置默认值为可选自变量。</span><span class="sxs-lookup"><span data-stu-id="74ba0-154">You can also use a function `defaultArg`, which sets a default value of an optional argument.</span></span> <span data-ttu-id="74ba0-155">`defaultArg`函数使用的第一个参数的可选参数，以及为第二个的默认值。</span><span class="sxs-lookup"><span data-stu-id="74ba0-155">The `defaultArg` function takes the optional parameter as the first argument and the default value as the second.</span></span>

<span data-ttu-id="74ba0-156">下面的示例演示如何使用可选参数。</span><span class="sxs-lookup"><span data-stu-id="74ba0-156">The following example illustrates the use of optional parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

<span data-ttu-id="74ba0-157">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="74ba0-157">The output is as follows.</span></span>

```
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
```

## <a name="passing-by-reference"></a><span data-ttu-id="74ba0-158">通过引用传递</span><span class="sxs-lookup"><span data-stu-id="74ba0-158">Passing by Reference</span></span>
<span data-ttu-id="74ba0-159">F # 支持`byref`关键字，用于指定通过引用传递参数。</span><span class="sxs-lookup"><span data-stu-id="74ba0-159">F# supports the `byref` keyword, which specifies that a parameter is passed by reference.</span></span> <span data-ttu-id="74ba0-160">这意味着后执行函数将保留任何更改的值。</span><span class="sxs-lookup"><span data-stu-id="74ba0-160">This means that any changes to the value are retained after the execution of the function.</span></span> <span data-ttu-id="74ba0-161">值提供给`byref`参数必须是可变。</span><span class="sxs-lookup"><span data-stu-id="74ba0-161">Values provided to a `byref` parameter must be mutable.</span></span> <span data-ttu-id="74ba0-162">或者，你可以将传递适当类型的引用单元格。</span><span class="sxs-lookup"><span data-stu-id="74ba0-162">Alternatively, you can pass reference cells of the appropriate type.</span></span>

<span data-ttu-id="74ba0-163">作为一种方法，以从函数返回多个值发展的.NET 语言中的引用进行传递。</span><span class="sxs-lookup"><span data-stu-id="74ba0-163">Passing by reference in .NET languages evolved as a way to return more than one value from a function.</span></span> <span data-ttu-id="74ba0-164">在 F # 中，可以为此，返回一个元组，或使用作为参数的可变的引用单元格。</span><span class="sxs-lookup"><span data-stu-id="74ba0-164">In F#, you can return a tuple for this purpose, or use a mutable reference cell as a parameter.</span></span> <span data-ttu-id="74ba0-165">`byref`与.NET 库互操作性的主要提供参数。</span><span class="sxs-lookup"><span data-stu-id="74ba0-165">The `byref` parameter is mainly provided for interoperability with .NET libraries.</span></span>

<span data-ttu-id="74ba0-166">下面的示例演示如何使用`byref`关键字。</span><span class="sxs-lookup"><span data-stu-id="74ba0-166">The following examples illustrate the use of the `byref` keyword.</span></span> <span data-ttu-id="74ba0-167">请注意，当你使用作为参数的引用单元格，你必须创建引用单元格作为命名值并将其用作参数，不只是添加`ref`运算符首次调用中所示`Increment`下面的代码中。</span><span class="sxs-lookup"><span data-stu-id="74ba0-167">Note that when you use a reference cell as a parameter, you must create a reference cell as a named value and use that as the parameter, not just add the `ref` operator as shown in the first call to `Increment` in the following code.</span></span> <span data-ttu-id="74ba0-168">创建引用单元格创建基础值的副本，因为第一个调用只会递增的临时值。</span><span class="sxs-lookup"><span data-stu-id="74ba0-168">Because creating a reference cell creates a copy of the underlying value, the first call just increments a temporary value.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3809.fs)]

<span data-ttu-id="74ba0-169">可以使用一个元组作为返回值来存储任何`out`.NET 库方法中的参数。</span><span class="sxs-lookup"><span data-stu-id="74ba0-169">You can use a tuple as a return value to store any `out` parameters in .NET library methods.</span></span> <span data-ttu-id="74ba0-170">或者，您可以将`out`参数作为`byref`参数。</span><span class="sxs-lookup"><span data-stu-id="74ba0-170">Alternatively, you can treat the `out` parameter as a `byref` parameter.</span></span> <span data-ttu-id="74ba0-171">下面的代码示例阐释了这两种方式。</span><span class="sxs-lookup"><span data-stu-id="74ba0-171">The following code example illustrates both ways.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a><span data-ttu-id="74ba0-172">参数数组</span><span class="sxs-lookup"><span data-stu-id="74ba0-172">Parameter Arrays</span></span>
<span data-ttu-id="74ba0-173">有时是需要定义采用任意数目的异类类型参数的函数。</span><span class="sxs-lookup"><span data-stu-id="74ba0-173">Occasionally it is necessary to define a function that takes an arbitrary number of parameters of heterogeneous type.</span></span> <span data-ttu-id="74ba0-174">它不会实际创建所有可能的重载的方法以解决可能使用的所有类型。</span><span class="sxs-lookup"><span data-stu-id="74ba0-174">It would not be practical to create all the possible overloaded methods to account for all the types that could be used.</span></span> <span data-ttu-id="74ba0-175">.NET 实现此类方法的参数数组功能通过提供支持。</span><span class="sxs-lookup"><span data-stu-id="74ba0-175">The .NET implementations provide support for such methods through the parameter array feature.</span></span> <span data-ttu-id="74ba0-176">可以具有任意数量的参数提供的签名中使用参数数组的方法。</span><span class="sxs-lookup"><span data-stu-id="74ba0-176">A method that takes a parameter array in its signature can be provided with an arbitrary number of parameters.</span></span> <span data-ttu-id="74ba0-177">参数被放入数组中。</span><span class="sxs-lookup"><span data-stu-id="74ba0-177">The parameters are put into an array.</span></span> <span data-ttu-id="74ba0-178">数组元素的类型确定可以传递给函数的参数类型。</span><span class="sxs-lookup"><span data-stu-id="74ba0-178">The type of the array elements determines the parameter types that can be passed to the function.</span></span> <span data-ttu-id="74ba0-179">如果你定义的参数数组`System.Object`作为元素类型，然后客户端代码可以通过任何类型的值。</span><span class="sxs-lookup"><span data-stu-id="74ba0-179">If you define the parameter array with `System.Object` as the element type, then client code can pass values of any type.</span></span>

<span data-ttu-id="74ba0-180">在 F # 中，仅在方法中定义参数数组。</span><span class="sxs-lookup"><span data-stu-id="74ba0-180">In F#, parameter arrays can only be defined in methods.</span></span> <span data-ttu-id="74ba0-181">它们不能在独立函数或模块中定义的函数。</span><span class="sxs-lookup"><span data-stu-id="74ba0-181">They cannot be used in standalone functions or functions that are defined in modules.</span></span>

<span data-ttu-id="74ba0-182">使用定义的参数数组`ParamArray`属性。</span><span class="sxs-lookup"><span data-stu-id="74ba0-182">You define a parameter array by using the `ParamArray` attribute.</span></span> <span data-ttu-id="74ba0-183">`ParamArray`属性只能应用到的最后一个参数。</span><span class="sxs-lookup"><span data-stu-id="74ba0-183">The `ParamArray` attribute can only be applied to the last parameter.</span></span>

<span data-ttu-id="74ba0-184">下面的代码阐释了这两个调用采用 F # 具有方法接受参数数组中的一个参数数组和类型定义的.NET 方法。</span><span class="sxs-lookup"><span data-stu-id="74ba0-184">The following code illustrates both calling a .NET method that takes a parameter array and the definition of a type in F# that has a method that takes a parameter array.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

<span data-ttu-id="74ba0-185">一个项目在运行时，上述代码的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="74ba0-185">When run in a project, the output of the previous code is as follows:</span></span>

```
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a><span data-ttu-id="74ba0-186">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74ba0-186">See Also</span></span>
[<span data-ttu-id="74ba0-187">成员</span><span class="sxs-lookup"><span data-stu-id="74ba0-187">Members</span></span>](members/index.md)
