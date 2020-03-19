---
title: 形参和实参
description: 了解 F# 语言对定义参数和将参数传递给函数、方法和属性的支持。
ms.date: 12/04/2019
ms.openlocfilehash: b234ef939128e7cf09d35f9580d4d5010d7dc639
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401051"
---
# <a name="parameters-and-arguments"></a><span data-ttu-id="6b71d-103">形参和实参</span><span class="sxs-lookup"><span data-stu-id="6b71d-103">Parameters and Arguments</span></span>

<span data-ttu-id="6b71d-104">本主题介绍定义参数和将参数传递给函数、方法和属性的语言支持。</span><span class="sxs-lookup"><span data-stu-id="6b71d-104">This topic describes language support for defining parameters and passing arguments to functions, methods, and properties.</span></span> <span data-ttu-id="6b71d-105">它包括有关如何通过引用传递的信息，以及如何定义和使用可以采用可变参数数的方法。</span><span class="sxs-lookup"><span data-stu-id="6b71d-105">It includes information about how to pass by reference, and how to define and use methods that can take a variable number of arguments.</span></span>

## <a name="parameters-and-arguments"></a><span data-ttu-id="6b71d-106">形参和实参</span><span class="sxs-lookup"><span data-stu-id="6b71d-106">Parameters and Arguments</span></span>

<span data-ttu-id="6b71d-107">术语*参数*用于描述预期提供的值的名称。</span><span class="sxs-lookup"><span data-stu-id="6b71d-107">The term *parameter* is used to describe the names for values that are expected to be supplied.</span></span> <span data-ttu-id="6b71d-108">术语*参数*用于为每个参数提供的值。</span><span class="sxs-lookup"><span data-stu-id="6b71d-108">The term *argument* is used for the values provided for each parameter.</span></span>

<span data-ttu-id="6b71d-109">参数可以以元组或咖喱形式指定，也可以以两者的某些组合指定。</span><span class="sxs-lookup"><span data-stu-id="6b71d-109">Parameters can be specified in tuple or curried form, or in some combination of the two.</span></span> <span data-ttu-id="6b71d-110">可以使用显式参数名称传递参数。</span><span class="sxs-lookup"><span data-stu-id="6b71d-110">You can pass arguments by using an explicit parameter name.</span></span> <span data-ttu-id="6b71d-111">方法的参数可以指定为可选，并给出默认值。</span><span class="sxs-lookup"><span data-stu-id="6b71d-111">Parameters of methods can be specified as optional and given a default value.</span></span>

## <a name="parameter-patterns"></a><span data-ttu-id="6b71d-112">参数模式</span><span class="sxs-lookup"><span data-stu-id="6b71d-112">Parameter Patterns</span></span>

<span data-ttu-id="6b71d-113">提供给函数和方法的参数一般是由空格分隔的模式。</span><span class="sxs-lookup"><span data-stu-id="6b71d-113">Parameters supplied to functions and methods are, in general, patterns separated by spaces.</span></span> <span data-ttu-id="6b71d-114">这意味着，原则上，[匹配表达式](match-expressions.md)中描述的任何模式都可以在函数或成员的参数列表中使用。</span><span class="sxs-lookup"><span data-stu-id="6b71d-114">This means that, in principle, any of the patterns described in [Match Expressions](match-expressions.md) can be used in a parameter list for a function or member.</span></span>

<span data-ttu-id="6b71d-115">方法通常使用传递参数的元组形式。</span><span class="sxs-lookup"><span data-stu-id="6b71d-115">Methods usually use the tuple form of passing arguments.</span></span> <span data-ttu-id="6b71d-116">从其他 .NET 语言的角度来看，这可实现更清晰的结果，因为元组形式与在 .NET 方法中传递参数的方式匹配。</span><span class="sxs-lookup"><span data-stu-id="6b71d-116">This achieves a clearer result from the perspective of other .NET languages because the tuple form matches the way arguments are passed in .NET methods.</span></span>

<span data-ttu-id="6b71d-117">咖喱窗体最常用于使用`let`绑定创建的函数。</span><span class="sxs-lookup"><span data-stu-id="6b71d-117">The curried form is most often used with functions created by using `let` bindings.</span></span>

<span data-ttu-id="6b71d-118">下面的伪代码显示了元组和咖喱参数的示例。</span><span class="sxs-lookup"><span data-stu-id="6b71d-118">The following pseudocode shows examples of tuple and curried arguments.</span></span>

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

<span data-ttu-id="6b71d-119">当某些参数位于组合中，而有些参数不是时，可以组合形式。</span><span class="sxs-lookup"><span data-stu-id="6b71d-119">Combined forms are possible when some arguments are in tuples and some are not.</span></span>

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

<span data-ttu-id="6b71d-120">其他模式也可以在参数列表中使用，但如果参数模式与所有可能的输入不匹配，则运行时可能存在不完全匹配。</span><span class="sxs-lookup"><span data-stu-id="6b71d-120">Other patterns can also be used in parameter lists, but if the parameter pattern does not match all possible inputs, there might be an incomplete match at run time.</span></span> <span data-ttu-id="6b71d-121">当参数`MatchFailureException`的值与参数列表中指定的模式不匹配时，将生成异常。</span><span class="sxs-lookup"><span data-stu-id="6b71d-121">The exception `MatchFailureException` is generated when the value of an argument does not match the patterns specified in the parameter list.</span></span> <span data-ttu-id="6b71d-122">当参数模式允许不完全匹配时，编译器发出警告。</span><span class="sxs-lookup"><span data-stu-id="6b71d-122">The compiler issues a warning when a parameter pattern allows for incomplete matches.</span></span> <span data-ttu-id="6b71d-123">至少有一个其他模式通常可用于参数列表，即通配符模式。</span><span class="sxs-lookup"><span data-stu-id="6b71d-123">At least one other pattern is commonly useful for parameter lists, and that is the wildcard pattern.</span></span> <span data-ttu-id="6b71d-124">当您只想忽略提供的任何参数时，在参数列表中使用通配符模式。</span><span class="sxs-lookup"><span data-stu-id="6b71d-124">You use the wildcard pattern in a parameter list when you simply want to ignore any arguments that are supplied.</span></span> <span data-ttu-id="6b71d-125">以下代码说明了通配符模式在参数列表中的使用。</span><span class="sxs-lookup"><span data-stu-id="6b71d-125">The following code illustrates the use of the wildcard pattern in an argument list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

<span data-ttu-id="6b71d-126">当您不需要传入的参数（如程序的主入口点）时，当您对通常作为字符串数组提供的命令行参数不感兴趣时，通配符模式非常有用，如以下代码。</span><span class="sxs-lookup"><span data-stu-id="6b71d-126">The wildcard pattern can be useful whenever you do not need the arguments passed in, such as in the main entry point to a program, when you are not interested in the command-line arguments that are normally supplied as a string array, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

<span data-ttu-id="6b71d-127">参数中有时使用的其他模式是与受歧视的联合`as`和活动模式关联的模式和标识符模式。</span><span class="sxs-lookup"><span data-stu-id="6b71d-127">Other patterns that are sometimes used in arguments are the `as` pattern, and identifier patterns associated with discriminated unions and active patterns.</span></span> <span data-ttu-id="6b71d-128">可以使用单例区分联合模式，如下所示。</span><span class="sxs-lookup"><span data-stu-id="6b71d-128">You can use the single-case discriminated union pattern as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

<span data-ttu-id="6b71d-129">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="6b71d-129">The output is as follows.</span></span>

```console
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

<span data-ttu-id="6b71d-130">活动模式可用作参数，例如，将参数转换为所需格式时，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="6b71d-130">Active patterns can be useful as parameters, for example, when transforming an argument into a desired format, as in the following example:</span></span>

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

<span data-ttu-id="6b71d-131">可以使用`as`模式将匹配值存储为本地值，如下代码行所示。</span><span class="sxs-lookup"><span data-stu-id="6b71d-131">You can use the `as` pattern to store a matched value as a local value, as is shown in the following line of code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

<span data-ttu-id="6b71d-132">偶尔使用的另一种模式是一个函数，该函数通过提供 lambda 表达式（作为函数的正文）来保留最后一个参数未命名，该表达式将立即对隐式参数执行模式匹配。</span><span class="sxs-lookup"><span data-stu-id="6b71d-132">Another pattern that is used occasionally is a function that leaves the last argument unnamed by providing, as the body of the function, a lambda expression that immediately performs a pattern match on the implicit argument.</span></span> <span data-ttu-id="6b71d-133">例如以下代码行。</span><span class="sxs-lookup"><span data-stu-id="6b71d-133">An example of this is the following line of code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

<span data-ttu-id="6b71d-134">此代码定义一个函数，该函数获取泛型列表`true`，并在列表为空时返回`false`，否则返回。</span><span class="sxs-lookup"><span data-stu-id="6b71d-134">This code defines a function that takes a generic list and returns `true` if the list is empty, and `false` otherwise.</span></span> <span data-ttu-id="6b71d-135">使用此类技术会使代码更难阅读。</span><span class="sxs-lookup"><span data-stu-id="6b71d-135">The use of such techniques can make code more difficult to read.</span></span>

<span data-ttu-id="6b71d-136">有时，涉及不完全匹配的模式很有用，例如，如果您知道程序中的列表只有三个元素，则可以在参数列表中使用如下所示的模式。</span><span class="sxs-lookup"><span data-stu-id="6b71d-136">Occasionally, patterns that involve incomplete matches are useful, for example, if you know that the lists in your program have only three elements, you might use a pattern like the following in a parameter list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

<span data-ttu-id="6b71d-137">使用匹配不完全的模式最好保留用于快速原型设计和其他临时用途。</span><span class="sxs-lookup"><span data-stu-id="6b71d-137">The use of patterns that have incomplete matches is best reserved for quick prototyping and other temporary uses.</span></span> <span data-ttu-id="6b71d-138">编译器将针对此类代码发出警告。</span><span class="sxs-lookup"><span data-stu-id="6b71d-138">The compiler will issue a warning for such code.</span></span> <span data-ttu-id="6b71d-139">此类模式不能涵盖所有可能输入的一般情况，因此不适合组件 API。</span><span class="sxs-lookup"><span data-stu-id="6b71d-139">Such patterns cannot cover the general case of all possible inputs and therefore are not suitable for component APIs.</span></span>

## <a name="named-arguments"></a><span data-ttu-id="6b71d-140">命名实参</span><span class="sxs-lookup"><span data-stu-id="6b71d-140">Named Arguments</span></span>

<span data-ttu-id="6b71d-141">方法的参数可以按逗号分隔参数列表中的位置指定，也可以通过提供名称（后跟等符号和要传入的值）显式传递给方法。</span><span class="sxs-lookup"><span data-stu-id="6b71d-141">Arguments for methods can be specified by position in a comma-separated argument list, or they can be passed to a method explicitly by providing the name, followed by an equal sign and the value to be passed in.</span></span> <span data-ttu-id="6b71d-142">如果通过提供名称指定，它们可以按与声明中使用的顺序不同的显示顺序显示。</span><span class="sxs-lookup"><span data-stu-id="6b71d-142">If specified by providing the name, they can appear in a different order from that used in the declaration.</span></span>

<span data-ttu-id="6b71d-143">命名参数可以使代码更具可读性，并更适应 API 中的某些类型的更改，例如方法参数的重新排序。</span><span class="sxs-lookup"><span data-stu-id="6b71d-143">Named arguments can make code more readable and more adaptable to certain types of changes in the API, such as a reordering of method parameters.</span></span>

<span data-ttu-id="6b71d-144">命名参数仅允许用于方法，不适用于`let`绑定函数、函数值或 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="6b71d-144">Named arguments are allowed only for methods, not for `let`-bound functions, function values, or lambda expressions.</span></span>

<span data-ttu-id="6b71d-145">以下代码示例演示了命名参数的使用。</span><span class="sxs-lookup"><span data-stu-id="6b71d-145">The following code example demonstrates the use of named arguments.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

<span data-ttu-id="6b71d-146">在调用类构造函数时，可以使用类似于命名参数的语法来设置类的属性值。</span><span class="sxs-lookup"><span data-stu-id="6b71d-146">In a call to a class constructor, you can set the values of properties of the class by using a syntax similar to that of named arguments.</span></span> <span data-ttu-id="6b71d-147">下面的示例显示了此语法。</span><span class="sxs-lookup"><span data-stu-id="6b71d-147">The following example shows this syntax.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="6b71d-148">有关详细信息，请参阅[构造函数 （F#）。](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05)</span><span class="sxs-lookup"><span data-stu-id="6b71d-148">For more information, see [Constructors (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span></span>

## <a name="optional-parameters"></a><span data-ttu-id="6b71d-149">可选参数</span><span class="sxs-lookup"><span data-stu-id="6b71d-149">Optional Parameters</span></span>

<span data-ttu-id="6b71d-150">可以使用参数名称前面的问号为方法指定可选参数。</span><span class="sxs-lookup"><span data-stu-id="6b71d-150">You can specify an optional parameter for a method by using a question mark in front of the parameter name.</span></span> <span data-ttu-id="6b71d-151">可选参数被解释为 F# 选项类型，因此可以使用 的`match``Some`表达式 和 ，以查询选项类型的常规方式查询它们。 `None`</span><span class="sxs-lookup"><span data-stu-id="6b71d-151">Optional parameters are interpreted as the F# option type, so you can query them in the regular way that option types are queried, by using a `match` expression with `Some` and `None`.</span></span> <span data-ttu-id="6b71d-152">可选参数仅允许在成员上，不允许使用`let`绑定创建的函数。</span><span class="sxs-lookup"><span data-stu-id="6b71d-152">Optional parameters are permitted only on members, not on functions created by using `let` bindings.</span></span>

<span data-ttu-id="6b71d-153">可以按参数名称将现有可选值传递给方法，例如`?arg=None`或`?arg=Some(3)``?arg=arg`。</span><span class="sxs-lookup"><span data-stu-id="6b71d-153">You can pass existing optional values to method by parameter name, such as `?arg=None` or `?arg=Some(3)` or `?arg=arg`.</span></span> <span data-ttu-id="6b71d-154">这在构建将可选参数传递给另一种方法的方法时非常有用。</span><span class="sxs-lookup"><span data-stu-id="6b71d-154">This can be useful when building a method that passes optional arguments to another method.</span></span>

<span data-ttu-id="6b71d-155">您还可以使用 函数`defaultArg`，它设置可选参数的默认值。</span><span class="sxs-lookup"><span data-stu-id="6b71d-155">You can also use a function `defaultArg`, which sets a default value of an optional argument.</span></span> <span data-ttu-id="6b71d-156">函数`defaultArg`将可选参数作为第一个参数，将默认值作为第二个参数。</span><span class="sxs-lookup"><span data-stu-id="6b71d-156">The `defaultArg` function takes the optional parameter as the first argument and the default value as the second.</span></span>

<span data-ttu-id="6b71d-157">下面的示例说明了可选参数的使用。</span><span class="sxs-lookup"><span data-stu-id="6b71d-157">The following example illustrates the use of optional parameters.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

<span data-ttu-id="6b71d-158">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="6b71d-158">The output is as follows.</span></span>

```console
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
```

<span data-ttu-id="6b71d-159">出于 C# 和 Visual Basic 互操作的目的，可以使用`[<Optional; DefaultParameterValue<(...)>]`F# 中的属性，以便调用方将参数视为可选参数。</span><span class="sxs-lookup"><span data-stu-id="6b71d-159">For the purposes of C# and Visual Basic interop you can use the attributes `[<Optional; DefaultParameterValue<(...)>]` in F#, so that callers will see an argument as optional.</span></span> <span data-ttu-id="6b71d-160">这相当于在 C# 中将参数定义为可选参数，如`MyMethod(int i = 3)`在 中。</span><span class="sxs-lookup"><span data-stu-id="6b71d-160">This is equivalent to defining the argument as optional in C# as in `MyMethod(int i = 3)`.</span></span>

```fsharp
open System
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue("Hello world")>] message) =
        printfn "%s" message
```

<span data-ttu-id="6b71d-161">还可以指定新对象作为默认参数值。</span><span class="sxs-lookup"><span data-stu-id="6b71d-161">You can also specify a new object as a default parameter value.</span></span> <span data-ttu-id="6b71d-162">例如，`Foo`成员可以改为具有可选`CancellationToken`作为输入：</span><span class="sxs-lookup"><span data-stu-id="6b71d-162">For example, the `Foo` member could have an optional `CancellationToken` as input instead:</span></span>

```fsharp
open System.Threading
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue(CancellationToken())>] ct: CancellationToken) =
        printfn "%A" ct
```

<span data-ttu-id="6b71d-163">作为参数给出的值`DefaultParameterValue`必须与参数的类型匹配。</span><span class="sxs-lookup"><span data-stu-id="6b71d-163">The value given as argument to `DefaultParameterValue` must match the type of the parameter.</span></span> <span data-ttu-id="6b71d-164">例如，不允许使用以下内容：</span><span class="sxs-lookup"><span data-stu-id="6b71d-164">For example, the following is not allowed:</span></span>

```fsharp
type C =
    static member Wrong([<Optional; DefaultParameterValue("string")>] i:int) = ()
```

<span data-ttu-id="6b71d-165">在这种情况下，编译器将生成警告，并将完全忽略这两个属性。</span><span class="sxs-lookup"><span data-stu-id="6b71d-165">In this case, the compiler generates a warning and will ignore both attributes altogether.</span></span> <span data-ttu-id="6b71d-166">请注意，需要对默认值`null`进行类型注释，否则编译器将推断错误的类型，即`[<Optional; DefaultParameterValue(null:obj)>] o:obj`。</span><span class="sxs-lookup"><span data-stu-id="6b71d-166">Note that the default value `null` needs to be type-annotated, as otherwise the compiler infers the wrong type, i.e. `[<Optional; DefaultParameterValue(null:obj)>] o:obj`.</span></span>

## <a name="passing-by-reference"></a><span data-ttu-id="6b71d-167">通过引用传递</span><span class="sxs-lookup"><span data-stu-id="6b71d-167">Passing by Reference</span></span>

<span data-ttu-id="6b71d-168">通过引用传递 F# 值涉及[byrefs，](byrefs.md)它们是托管指针类型。</span><span class="sxs-lookup"><span data-stu-id="6b71d-168">Passing an F# value by reference involves [byrefs](byrefs.md), which are managed pointer types.</span></span> <span data-ttu-id="6b71d-169">使用哪种类型的指南如下所示：</span><span class="sxs-lookup"><span data-stu-id="6b71d-169">Guidance for which type to use is as follows:</span></span>

- <span data-ttu-id="6b71d-170">如果`inref<'T>`只需要读取指针，请使用。</span><span class="sxs-lookup"><span data-stu-id="6b71d-170">Use `inref<'T>` if you only need to read the pointer.</span></span>
- <span data-ttu-id="6b71d-171">如果`outref<'T>`只需要写入指针，请使用。</span><span class="sxs-lookup"><span data-stu-id="6b71d-171">Use `outref<'T>` if you only need to write to the pointer.</span></span>
- <span data-ttu-id="6b71d-172">如果需要`byref<'T>`同时读取指针并写入指针，请使用。</span><span class="sxs-lookup"><span data-stu-id="6b71d-172">Use `byref<'T>` if you need to both read from and write to the pointer.</span></span>

```fsharp
let example1 (x: inref<int>) = printfn "It's %d" x

let example2 (x: outref<int>) = x <- x + 1

let example3 (x: byref<int>) =
    printfn "It'd %d" x
    x <- x + 1

let test () =
    // No need to make it mutable, since it's read-only
    let x = 1
    example1 &x

    // Needs to be mutable, since we write to it
    let mutable y = 2
    example2 &y
    example3 &y // Now 'y' is 3
```

<span data-ttu-id="6b71d-173">由于参数是指针，并且值是可变的，因此在执行函数后将保留对值的任何更改。</span><span class="sxs-lookup"><span data-stu-id="6b71d-173">Because the parameter is a pointer and the value is mutable, any changes to the value are retained after the execution of the function.</span></span>

<span data-ttu-id="6b71d-174">可以使用元组作为返回值，在 .NET 库`out`方法中存储任何参数。</span><span class="sxs-lookup"><span data-stu-id="6b71d-174">You can use a tuple as a return value to store any `out` parameters in .NET library methods.</span></span> <span data-ttu-id="6b71d-175">或者，您可以将参数`out`视为参数。 `byref`</span><span class="sxs-lookup"><span data-stu-id="6b71d-175">Alternatively, you can treat the `out` parameter as a `byref` parameter.</span></span> <span data-ttu-id="6b71d-176">以下代码示例说明了这两种方法。</span><span class="sxs-lookup"><span data-stu-id="6b71d-176">The following code example illustrates both ways.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a><span data-ttu-id="6b71d-177">参数数组</span><span class="sxs-lookup"><span data-stu-id="6b71d-177">Parameter Arrays</span></span>

<span data-ttu-id="6b71d-178">有时，需要定义一个函数，该函数采用异构类型的任意数量的参数。</span><span class="sxs-lookup"><span data-stu-id="6b71d-178">Occasionally it is necessary to define a function that takes an arbitrary number of parameters of heterogeneous type.</span></span> <span data-ttu-id="6b71d-179">创建所有可能的重载方法以考虑可以使用的所有类型是不现实的。</span><span class="sxs-lookup"><span data-stu-id="6b71d-179">It would not be practical to create all the possible overloaded methods to account for all the types that could be used.</span></span> <span data-ttu-id="6b71d-180">.NET 实现通过参数数组功能为这些方法提供支持。</span><span class="sxs-lookup"><span data-stu-id="6b71d-180">The .NET implementations provide support for such methods through the parameter array feature.</span></span> <span data-ttu-id="6b71d-181">在其签名中采用参数数组的方法可以提供任意数量的参数。</span><span class="sxs-lookup"><span data-stu-id="6b71d-181">A method that takes a parameter array in its signature can be provided with an arbitrary number of parameters.</span></span> <span data-ttu-id="6b71d-182">参数被放入数组中。</span><span class="sxs-lookup"><span data-stu-id="6b71d-182">The parameters are put into an array.</span></span> <span data-ttu-id="6b71d-183">数组元素的类型确定可传递给函数的参数类型。</span><span class="sxs-lookup"><span data-stu-id="6b71d-183">The type of the array elements determines the parameter types that can be passed to the function.</span></span> <span data-ttu-id="6b71d-184">如果将参数数组`System.Object`定义为元素类型，则客户端代码可以传递任何类型的值。</span><span class="sxs-lookup"><span data-stu-id="6b71d-184">If you define the parameter array with `System.Object` as the element type, then client code can pass values of any type.</span></span>

<span data-ttu-id="6b71d-185">在 F# 中，只能在方法中定义参数数组。</span><span class="sxs-lookup"><span data-stu-id="6b71d-185">In F#, parameter arrays can only be defined in methods.</span></span> <span data-ttu-id="6b71d-186">它们不能用于在模块中定义的独立函数或函数中。</span><span class="sxs-lookup"><span data-stu-id="6b71d-186">They cannot be used in standalone functions or functions that are defined in modules.</span></span>

<span data-ttu-id="6b71d-187">通过使用`ParamArray`属性定义参数数组。</span><span class="sxs-lookup"><span data-stu-id="6b71d-187">You define a parameter array by using the `ParamArray` attribute.</span></span> <span data-ttu-id="6b71d-188">该`ParamArray`属性只能应用于最后一个参数。</span><span class="sxs-lookup"><span data-stu-id="6b71d-188">The `ParamArray` attribute can only be applied to the last parameter.</span></span>

<span data-ttu-id="6b71d-189">以下代码说明了调用采用参数数组的 .NET 方法，以及 F# 中具有采用参数数组的方法的类型的定义。</span><span class="sxs-lookup"><span data-stu-id="6b71d-189">The following code illustrates both calling a .NET method that takes a parameter array and the definition of a type in F# that has a method that takes a parameter array.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

<span data-ttu-id="6b71d-190">在项目中运行时，前一个代码的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="6b71d-190">When run in a project, the output of the previous code is as follows:</span></span>

```console
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a><span data-ttu-id="6b71d-191">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b71d-191">See also</span></span>

- [<span data-ttu-id="6b71d-192">成员</span><span class="sxs-lookup"><span data-stu-id="6b71d-192">Members</span></span>](./members/index.md)
