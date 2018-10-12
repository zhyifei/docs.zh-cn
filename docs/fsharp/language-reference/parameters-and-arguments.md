---
title: 参数和自变量 (F#)
description: '了解有关 F # 语言支持对定义形参并将参数传递给函数、 方法和属性。'
ms.date: 05/16/2016
ms.openlocfilehash: a1e2a70ca560bbb09d2cd10f47485cbe5c5e029d
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49123353"
---
# <a name="parameters-and-arguments"></a><span data-ttu-id="16a7d-103">形参和实参</span><span class="sxs-lookup"><span data-stu-id="16a7d-103">Parameters and Arguments</span></span>

<span data-ttu-id="16a7d-104">本主题介绍对定义形参并将参数传递给函数、 方法和属性的语言支持。</span><span class="sxs-lookup"><span data-stu-id="16a7d-104">This topic describes language support for defining parameters and passing arguments to functions, methods, and properties.</span></span> <span data-ttu-id="16a7d-105">它包括有关如何将传递的引用，以及如何定义和使用可以采用可变数量的参数的方法的信息。</span><span class="sxs-lookup"><span data-stu-id="16a7d-105">It includes information about how to pass by reference, and how to define and use methods that can take a variable number of arguments.</span></span>

## <a name="parameters-and-arguments"></a><span data-ttu-id="16a7d-106">形参和实参</span><span class="sxs-lookup"><span data-stu-id="16a7d-106">Parameters and Arguments</span></span>

<span data-ttu-id="16a7d-107">术语*参数*用于描述的预期提供的值的名称。</span><span class="sxs-lookup"><span data-stu-id="16a7d-107">The term *parameter* is used to describe the names for values that are expected to be supplied.</span></span> <span data-ttu-id="16a7d-108">术语*自变量*用于为每个参数提供的值。</span><span class="sxs-lookup"><span data-stu-id="16a7d-108">The term *argument* is used for the values provided for each parameter.</span></span>

<span data-ttu-id="16a7d-109">元组或扩充窗体，或两者的某种组合中，可以指定参数。</span><span class="sxs-lookup"><span data-stu-id="16a7d-109">Parameters can be specified in tuple or curried form, or in some combination of the two.</span></span> <span data-ttu-id="16a7d-110">可以通过使用显式参数名称传递参数。</span><span class="sxs-lookup"><span data-stu-id="16a7d-110">You can pass arguments by using an explicit parameter name.</span></span> <span data-ttu-id="16a7d-111">方法的参数可以是指定为可选，指定的默认值。</span><span class="sxs-lookup"><span data-stu-id="16a7d-111">Parameters of methods can be specified as optional and given a default value.</span></span>

## <a name="parameter-patterns"></a><span data-ttu-id="16a7d-112">参数模式</span><span class="sxs-lookup"><span data-stu-id="16a7d-112">Parameter Patterns</span></span>

<span data-ttu-id="16a7d-113">一般情况下，提供给函数和方法的参数是由空格分隔的模式。</span><span class="sxs-lookup"><span data-stu-id="16a7d-113">Parameters supplied to functions and methods are, in general, patterns separated by spaces.</span></span> <span data-ttu-id="16a7d-114">这意味着，从原理上讲，任何模式中所述[匹配表达式](match-expressions.md)可用于在参数列表中的函数或成员。</span><span class="sxs-lookup"><span data-stu-id="16a7d-114">This means that, in principle, any of the patterns described in [Match Expressions](match-expressions.md) can be used in a parameter list for a function or member.</span></span>

<span data-ttu-id="16a7d-115">方法通常会使用元组形式传递自变量。</span><span class="sxs-lookup"><span data-stu-id="16a7d-115">Methods usually use the tuple form of passing arguments.</span></span> <span data-ttu-id="16a7d-116">这实现了从其他.NET 语言的角度来看更加清晰的结果，因为元组形式与.NET 方法中传递参数的方法相匹配。</span><span class="sxs-lookup"><span data-stu-id="16a7d-116">This achieves a clearer result from the perspective of other .NET languages because the tuple form matches the way arguments are passed in .NET methods.</span></span>

<span data-ttu-id="16a7d-117">通过使用创建的函数最常使用扩充的形式`let`绑定。</span><span class="sxs-lookup"><span data-stu-id="16a7d-117">The curried form is most often used with functions created by using `let` bindings.</span></span>

<span data-ttu-id="16a7d-118">下面的伪代码显示了元组和扩充的参数的示例。</span><span class="sxs-lookup"><span data-stu-id="16a7d-118">The following pseudocode shows examples of tuple and curried arguments.</span></span>

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

<span data-ttu-id="16a7d-119">组合的窗体时，某些参数是在元组中，有些则不然。</span><span class="sxs-lookup"><span data-stu-id="16a7d-119">Combined forms are possible when some arguments are in tuples and some are not.</span></span>

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

<span data-ttu-id="16a7d-120">其他模式还可用于在参数列表中，但如果参数模式与所有可能的输入不匹配，则可能是不完整的匹配项在运行时。</span><span class="sxs-lookup"><span data-stu-id="16a7d-120">Other patterns can also be used in parameter lists, but if the parameter pattern does not match all possible inputs, there might be an incomplete match at run time.</span></span> <span data-ttu-id="16a7d-121">异常`MatchFailureException`自变量的值与参数列表中指定的模式不匹配时生成。</span><span class="sxs-lookup"><span data-stu-id="16a7d-121">The exception `MatchFailureException` is generated when the value of an argument does not match the patterns specified in the parameter list.</span></span> <span data-ttu-id="16a7d-122">当参数模式允许的不完整的匹配项时，编译器将发出警告。</span><span class="sxs-lookup"><span data-stu-id="16a7d-122">The compiler issues a warning when a parameter pattern allows for incomplete matches.</span></span> <span data-ttu-id="16a7d-123">至少一个其他模式在通常可用于参数列表，这就是通配符模式。</span><span class="sxs-lookup"><span data-stu-id="16a7d-123">At least one other pattern is commonly useful for parameter lists, and that is the wildcard pattern.</span></span> <span data-ttu-id="16a7d-124">如果只是想要忽略提供的任何自变量参数列表中使用通配符模式。</span><span class="sxs-lookup"><span data-stu-id="16a7d-124">You use the wildcard pattern in a parameter list when you simply want to ignore any arguments that are supplied.</span></span> <span data-ttu-id="16a7d-125">下面的代码演示如何使用参数列表中的通配符模式。</span><span class="sxs-lookup"><span data-stu-id="16a7d-125">The following code illustrates the use of the wildcard pattern in an argument list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

<span data-ttu-id="16a7d-126">您不感兴趣通常提供作为一个字符串数组，如以下代码所示的命令行参数时，可能很有用，只要不需要传入的参数，如主入口点到程序中，通配符模式。</span><span class="sxs-lookup"><span data-stu-id="16a7d-126">The wildcard pattern can be useful whenever you do not need the arguments passed in, such as in the main entry point to a program, when you are not interested in the command-line arguments that are normally supplied as a string array, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

<span data-ttu-id="16a7d-127">有时使用参数中的其他模式包括`as`模式，且可区分的联合和活动模式与相关联的标识符模式。</span><span class="sxs-lookup"><span data-stu-id="16a7d-127">Other patterns that are sometimes used in arguments are the `as` pattern, and identifier patterns associated with discriminated unions and active patterns.</span></span> <span data-ttu-id="16a7d-128">可以使用单用例可区分联合模式，如下所示。</span><span class="sxs-lookup"><span data-stu-id="16a7d-128">You can use the single-case discriminated union pattern as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

<span data-ttu-id="16a7d-129">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="16a7d-129">The output is as follows.</span></span>

```
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

<span data-ttu-id="16a7d-130">活动模式可作为参数，例如，如果将参数转换为所需的格式，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="16a7d-130">Active patterns can be useful as parameters, for example, when transforming an argument into a desired format, as in the following example:</span></span>

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

<span data-ttu-id="16a7d-131">可以使用`as`模式匹配的值存储为本地值，如以下代码行中所示。</span><span class="sxs-lookup"><span data-stu-id="16a7d-131">You can use the `as` pattern to store a matched value as a local value, as is shown in the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

<span data-ttu-id="16a7d-132">偶尔使用的另一种模式是离开通过提供，作为函数的正文未命名的最后一个参数的函数、 隐式的自变量将立即执行模式匹配的 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="16a7d-132">Another pattern that is used occasionally is a function that leaves the last argument unnamed by providing, as the body of the function, a lambda expression that immediately performs a pattern match on the implicit argument.</span></span> <span data-ttu-id="16a7d-133">此示例为以下代码行。</span><span class="sxs-lookup"><span data-stu-id="16a7d-133">An example of this is the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

<span data-ttu-id="16a7d-134">此代码定义一个函数接受一个泛型列表，并返回`true`如果列表为空，和`false`否则为。</span><span class="sxs-lookup"><span data-stu-id="16a7d-134">This code defines a function that takes a generic list and returns `true` if the list is empty, and `false` otherwise.</span></span> <span data-ttu-id="16a7d-135">使用此类技术可以使代码更难以阅读。</span><span class="sxs-lookup"><span data-stu-id="16a7d-135">The use of such techniques can make code more difficult to read.</span></span>

<span data-ttu-id="16a7d-136">有时，涉及不完整的匹配项的模式是有用的例如，如果您知道您的程序中的列表具有只有三个元素，您可以使用如下所示的模式参数列表中。</span><span class="sxs-lookup"><span data-stu-id="16a7d-136">Occasionally, patterns that involve incomplete matches are useful, for example, if you know that the lists in your program have only three elements, you might use a pattern like the following in a parameter list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

<span data-ttu-id="16a7d-137">最好保留以供快速原型制作和其他临时使用具有不完全匹配的模式的使用。</span><span class="sxs-lookup"><span data-stu-id="16a7d-137">The use of patterns that have incomplete matches is best reserved for quick prototyping and other temporary uses.</span></span> <span data-ttu-id="16a7d-138">编译器将发出此类代码的警告。</span><span class="sxs-lookup"><span data-stu-id="16a7d-138">The compiler will issue a warning for such code.</span></span> <span data-ttu-id="16a7d-139">此类模式无法涵盖所有可能的输入的一般情况下，并因此不适合组件 Api。</span><span class="sxs-lookup"><span data-stu-id="16a7d-139">Such patterns cannot cover the general case of all possible inputs and therefore are not suitable for component APIs.</span></span>

## <a name="named-arguments"></a><span data-ttu-id="16a7d-140">命名实参</span><span class="sxs-lookup"><span data-stu-id="16a7d-140">Named Arguments</span></span>

<span data-ttu-id="16a7d-141">可以通过在逗号分隔参数列表中，位置指定的方法参数或它们可以显式传递给方法通过提供名称后, 跟一个等号和要在中传递的值。</span><span class="sxs-lookup"><span data-stu-id="16a7d-141">Arguments for methods can be specified by position in a comma-separated argument list, or they can be passed to a method explicitly by providing the name, followed by an equal sign and the value to be passed in.</span></span> <span data-ttu-id="16a7d-142">如果指定通过提供的名称，它们可以出现在不同的声明中使用的顺序。</span><span class="sxs-lookup"><span data-stu-id="16a7d-142">If specified by providing the name, they can appear in a different order from that used in the declaration.</span></span>

<span data-ttu-id="16a7d-143">命名的自变量可以对某些类型的 API，如方法参数的重新排序中的更改使代码更具可读性且更适应能力更强。</span><span class="sxs-lookup"><span data-stu-id="16a7d-143">Named arguments can make code more readable and more adaptable to certain types of changes in the API, such as a reordering of method parameters.</span></span>

<span data-ttu-id="16a7d-144">命名的参数只允许在方法，不能用于`let`-绑定函数、 函数或 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="16a7d-144">Named arguments are allowed only for methods, not for `let`-bound functions, function values, or lambda expressions.</span></span>

<span data-ttu-id="16a7d-145">下面的代码示例演示如何将命名参数。</span><span class="sxs-lookup"><span data-stu-id="16a7d-145">The following code example demonstrates the use of named arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

<span data-ttu-id="16a7d-146">在类构造函数调用中，可以使用类似于的命名参数的语法来设置类的属性的值。</span><span class="sxs-lookup"><span data-stu-id="16a7d-146">In a call to a class constructor, you can set the values of properties of the class by using a syntax similar to that of named arguments.</span></span> <span data-ttu-id="16a7d-147">下面的示例显示了此语法。</span><span class="sxs-lookup"><span data-stu-id="16a7d-147">The following example shows this syntax.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="16a7d-148">有关详细信息，请参阅[构造函数 （F #）](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05)。</span><span class="sxs-lookup"><span data-stu-id="16a7d-148">For more information, see [Constructors (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span></span>

## <a name="optional-parameters"></a><span data-ttu-id="16a7d-149">可选参数</span><span class="sxs-lookup"><span data-stu-id="16a7d-149">Optional Parameters</span></span>

<span data-ttu-id="16a7d-150">可以通过使用参数名称前面的问号指定一种方法的可选参数。</span><span class="sxs-lookup"><span data-stu-id="16a7d-150">You can specify an optional parameter for a method by using a question mark in front of the parameter name.</span></span> <span data-ttu-id="16a7d-151">可选参数被解释为 F # 选项类型，因此您可以将这些查询，查询选项类型，通过常规方式`match`与表达式`Some`和`None`。</span><span class="sxs-lookup"><span data-stu-id="16a7d-151">Optional parameters are interpreted as the F# option type, so you can query them in the regular way that option types are queried, by using a `match` expression with `Some` and `None`.</span></span> <span data-ttu-id="16a7d-152">仅在成员上，通过使用创建的函数上不允许使用可选参数`let`绑定。</span><span class="sxs-lookup"><span data-stu-id="16a7d-152">Optional parameters are permitted only on members, not on functions created by using `let` bindings.</span></span>

<span data-ttu-id="16a7d-153">此外可以使用一个函数`defaultArg`，用于设置默认值为可选的参数。</span><span class="sxs-lookup"><span data-stu-id="16a7d-153">You can also use a function `defaultArg`, which sets a default value of an optional argument.</span></span> <span data-ttu-id="16a7d-154">`defaultArg`函数使用的第一个参数的可选参数，以及为第二个的默认值。</span><span class="sxs-lookup"><span data-stu-id="16a7d-154">The `defaultArg` function takes the optional parameter as the first argument and the default value as the second.</span></span>

<span data-ttu-id="16a7d-155">下面的示例演示如何使用可选参数。</span><span class="sxs-lookup"><span data-stu-id="16a7d-155">The following example illustrates the use of optional parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

<span data-ttu-id="16a7d-156">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="16a7d-156">The output is as follows.</span></span>

```
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
```

## <a name="passing-by-reference"></a><span data-ttu-id="16a7d-157">按引用传递</span><span class="sxs-lookup"><span data-stu-id="16a7d-157">Passing by Reference</span></span>

<span data-ttu-id="16a7d-158">按引用传递的 F # 值涉及[byref](byrefs.md)，哪些是托管的指针类型。</span><span class="sxs-lookup"><span data-stu-id="16a7d-158">Passing an F# value by reference involves [byrefs](byrefs.md), which are managed pointer types.</span></span> <span data-ttu-id="16a7d-159">对于要使用的类型是，如下所示的指南：</span><span class="sxs-lookup"><span data-stu-id="16a7d-159">Guidance for which type to use is as follows:</span></span>

* <span data-ttu-id="16a7d-160">使用`inref<'T>`如果只需要读取指针。</span><span class="sxs-lookup"><span data-stu-id="16a7d-160">Use `inref<'T>` if you only need to read the pointer.</span></span>
* <span data-ttu-id="16a7d-161">使用`outref<'T>`如果只需编写的指针。</span><span class="sxs-lookup"><span data-stu-id="16a7d-161">Use `outref<'T>` if you only need to write to the pointer.</span></span>
* <span data-ttu-id="16a7d-162">使用`byref<'T>`如果你需要同时读取和写入到的指针。</span><span class="sxs-lookup"><span data-stu-id="16a7d-162">Use `byref<'T>` if you need to both read from and write to the pointer.</span></span>

```fsharp
let example1 (x: inref<int>) = printfn "It's %d" x

let example2 (x: outref<int>) = x <- x + 1

let example3 (x: byref<int>) =
    printfn "It'd %d" x
    x <- x + 1

// No need to make it mutable, since it's read-only
let x = 1
example1 &x

// Needs to be mutable, since we write to it
let mutable y = 2
example2 &y
example3 &y // Now 'y' is 3
```

<span data-ttu-id="16a7d-163">因为参数是一个指针，值为可变，对值的任何更改将保留后执行函数。</span><span class="sxs-lookup"><span data-stu-id="16a7d-163">Because the parameter is a pointer and the value is mutable, any changes to the value are retained after the execution of the function.</span></span>

<span data-ttu-id="16a7d-164">可以使用一个元组作为返回值来存储任何`out`中.NET 库方法的参数。</span><span class="sxs-lookup"><span data-stu-id="16a7d-164">You can use a tuple as a return value to store any `out` parameters in .NET library methods.</span></span> <span data-ttu-id="16a7d-165">或者，您可以将`out`参数作为`byref`参数。</span><span class="sxs-lookup"><span data-stu-id="16a7d-165">Alternatively, you can treat the `out` parameter as a `byref` parameter.</span></span> <span data-ttu-id="16a7d-166">下面的代码示例说明了这两种方式。</span><span class="sxs-lookup"><span data-stu-id="16a7d-166">The following code example illustrates both ways.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a><span data-ttu-id="16a7d-167">参数数组</span><span class="sxs-lookup"><span data-stu-id="16a7d-167">Parameter Arrays</span></span>

<span data-ttu-id="16a7d-168">有时有必要定义采用任意数量的异构类型的参数的函数。</span><span class="sxs-lookup"><span data-stu-id="16a7d-168">Occasionally it is necessary to define a function that takes an arbitrary number of parameters of heterogeneous type.</span></span> <span data-ttu-id="16a7d-169">它不会实际创建所有可能的重载的方法来应对可能使用的所有类型。</span><span class="sxs-lookup"><span data-stu-id="16a7d-169">It would not be practical to create all the possible overloaded methods to account for all the types that could be used.</span></span> <span data-ttu-id="16a7d-170">.NET 实现为此类方法的参数数组功能通过提供支持。</span><span class="sxs-lookup"><span data-stu-id="16a7d-170">The .NET implementations provide support for such methods through the parameter array feature.</span></span> <span data-ttu-id="16a7d-171">可以有任意数量的参数提供的签名中使用参数数组的方法。</span><span class="sxs-lookup"><span data-stu-id="16a7d-171">A method that takes a parameter array in its signature can be provided with an arbitrary number of parameters.</span></span> <span data-ttu-id="16a7d-172">参数被放入数组中。</span><span class="sxs-lookup"><span data-stu-id="16a7d-172">The parameters are put into an array.</span></span> <span data-ttu-id="16a7d-173">数组元素的类型确定可以传递给函数的参数类型。</span><span class="sxs-lookup"><span data-stu-id="16a7d-173">The type of the array elements determines the parameter types that can be passed to the function.</span></span> <span data-ttu-id="16a7d-174">如果定义数组，该参数数组`System.Object`与元素类型，然后客户端代码可以通过任何类型的值。</span><span class="sxs-lookup"><span data-stu-id="16a7d-174">If you define the parameter array with `System.Object` as the element type, then client code can pass values of any type.</span></span>

<span data-ttu-id="16a7d-175">在 F # 中，只能在方法中定义参数数组。</span><span class="sxs-lookup"><span data-stu-id="16a7d-175">In F#, parameter arrays can only be defined in methods.</span></span> <span data-ttu-id="16a7d-176">它们不能独立函数或模块中定义的函数中使用。</span><span class="sxs-lookup"><span data-stu-id="16a7d-176">They cannot be used in standalone functions or functions that are defined in modules.</span></span>

<span data-ttu-id="16a7d-177">使用定义的参数数组`ParamArray`属性。</span><span class="sxs-lookup"><span data-stu-id="16a7d-177">You define a parameter array by using the `ParamArray` attribute.</span></span> <span data-ttu-id="16a7d-178">`ParamArray`属性只能应用到的最后一个参数。</span><span class="sxs-lookup"><span data-stu-id="16a7d-178">The `ParamArray` attribute can only be applied to the last parameter.</span></span>

<span data-ttu-id="16a7d-179">以下代码演示了这两个调用 F # 具有采用参数数组的方法中使用参数数组和类型的定义的.NET 方法。</span><span class="sxs-lookup"><span data-stu-id="16a7d-179">The following code illustrates both calling a .NET method that takes a parameter array and the definition of a type in F# that has a method that takes a parameter array.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

<span data-ttu-id="16a7d-180">当运行在项目中，上述代码的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="16a7d-180">When run in a project, the output of the previous code is as follows:</span></span>

```console
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a><span data-ttu-id="16a7d-181">请参阅</span><span class="sxs-lookup"><span data-stu-id="16a7d-181">See also</span></span>

- [<span data-ttu-id="16a7d-182">成员</span><span class="sxs-lookup"><span data-stu-id="16a7d-182">Members</span></span>](members/index.md)
