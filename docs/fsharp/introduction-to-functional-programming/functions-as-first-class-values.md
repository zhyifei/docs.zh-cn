---
title: 作为一类值的函数 (F#)
description: '了解如何提升至最优状态在 F # 编程语言中的函数。'
ms.date: 05/16/2016
ms.openlocfilehash: 45b65ab2454a592d38c80fd367e7243635614727
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44048227"
---
# <a name="functions-as-first-class-values"></a><span data-ttu-id="764c3-103">作为一类值的函数</span><span class="sxs-lookup"><span data-stu-id="764c3-103">Functions as First-Class Values</span></span>

<span data-ttu-id="764c3-104">函数编程语言的决定性特征是提升至最优状态的函数。</span><span class="sxs-lookup"><span data-stu-id="764c3-104">A defining characteristic of functional programming languages is the elevation of functions to first-class status.</span></span> <span data-ttu-id="764c3-105">您应能够执行的函数，任何您可以使用其他内置类型的值执行操作并将无法执行此操作与一般程度的工作量。</span><span class="sxs-lookup"><span data-stu-id="764c3-105">You should be able to do with a function whatever you can do with values of the other built-in types, and be able to do so with a comparable degree of effort.</span></span>

<span data-ttu-id="764c3-106">典型的第一类状态的度量值包括：</span><span class="sxs-lookup"><span data-stu-id="764c3-106">Typical measures of first-class status include the following:</span></span>

- <span data-ttu-id="764c3-107">您可以将函数绑定到标识符？</span><span class="sxs-lookup"><span data-stu-id="764c3-107">Can you bind functions to identifiers?</span></span> <span data-ttu-id="764c3-108">也就是说，可以在为其提供名称？</span><span class="sxs-lookup"><span data-stu-id="764c3-108">That is, can you give them names?</span></span>

- <span data-ttu-id="764c3-109">可以存储函数中的数据结构，如在列表中？</span><span class="sxs-lookup"><span data-stu-id="764c3-109">Can you store functions in data structures, such as in a list?</span></span>

- <span data-ttu-id="764c3-110">可以为函数调用中的自变量传递函数？</span><span class="sxs-lookup"><span data-stu-id="764c3-110">Can you pass a function as an argument in a function call?</span></span>

- <span data-ttu-id="764c3-111">您可以从函数调用返回一个函数？</span><span class="sxs-lookup"><span data-stu-id="764c3-111">Can you return a function from a function call?</span></span>

<span data-ttu-id="764c3-112">最后两个度量值定义所谓*高阶 operations*或*高阶函数*。</span><span class="sxs-lookup"><span data-stu-id="764c3-112">The last two measures define what are known as *higher-order operations* or *higher-order functions*.</span></span> <span data-ttu-id="764c3-113">高阶函数接受作为参数的函数，并返回函数作为函数调用的值。</span><span class="sxs-lookup"><span data-stu-id="764c3-113">Higher-order functions accept functions as arguments and return functions as the value of function calls.</span></span> <span data-ttu-id="764c3-114">这些操作支持这种功能性编程作为映射函数和函数的组合。</span><span class="sxs-lookup"><span data-stu-id="764c3-114">These operations support such mainstays of functional programming as mapping functions and composition of functions.</span></span>

## <a name="give-the-value-a-name"></a><span data-ttu-id="764c3-115">为指定名称的值</span><span class="sxs-lookup"><span data-stu-id="764c3-115">Give the Value a Name</span></span>

<span data-ttu-id="764c3-116">如果函数是第一类值，您必须能够将其命名，就像可以命名整数、 字符串和其他内置类型。</span><span class="sxs-lookup"><span data-stu-id="764c3-116">If a function is a first-class value, you must be able to name it, just as you can name integers, strings, and other built-in types.</span></span> <span data-ttu-id="764c3-117">这称为函数编程语言标识符绑定到的值中。</span><span class="sxs-lookup"><span data-stu-id="764c3-117">This is referred to in functional programming literature as binding an identifier to a value.</span></span> <span data-ttu-id="764c3-118">使用 F # [ `let`绑定](../language-reference/functions/let-bindings.md)要绑定到值的名称： `let <identifier> = <value>`。</span><span class="sxs-lookup"><span data-stu-id="764c3-118">F# uses [`let` bindings](../language-reference/functions/let-bindings.md) to bind names to values: `let <identifier> = <value>`.</span></span> <span data-ttu-id="764c3-119">下面的代码演示两个示例。</span><span class="sxs-lookup"><span data-stu-id="764c3-119">The following code shows two examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet20.fs)]

<span data-ttu-id="764c3-120">您可以命名很容易地函数。</span><span class="sxs-lookup"><span data-stu-id="764c3-120">You can name a function just as easily.</span></span> <span data-ttu-id="764c3-121">下面的示例定义一个名为函数`squareIt`通过将标识符绑定`squareIt`到[lambda 表达式](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n`。</span><span class="sxs-lookup"><span data-stu-id="764c3-121">The following example defines a function named `squareIt` by binding the identifier `squareIt` to the [lambda expression](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n`.</span></span> <span data-ttu-id="764c3-122">函数`squareIt`具有一个参数、 `n`，它将返回该参数的平方和。</span><span class="sxs-lookup"><span data-stu-id="764c3-122">Function `squareIt` has one parameter, `n`, and it returns the square of that parameter.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet21.fs)]

<span data-ttu-id="764c3-123">F # 提供了以下更简洁的语法来实现相同的结果，少键入一些字符。</span><span class="sxs-lookup"><span data-stu-id="764c3-123">F# provides the following more concise syntax to achieve the same result with less typing.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet22.fs)]

<span data-ttu-id="764c3-124">主要是下面的示例使用第一个样式， `let <function-name> = <lambda-expression>`，以强调函数的声明和其他类型的值的声明之间的相似之处。</span><span class="sxs-lookup"><span data-stu-id="764c3-124">The examples that follow mostly use the first style, `let <function-name> = <lambda-expression>`, to emphasize the similarities between the declaration of functions and the declaration of other types of values.</span></span> <span data-ttu-id="764c3-125">但是，还可以使用简洁的语法编写所有命名的函数。</span><span class="sxs-lookup"><span data-stu-id="764c3-125">However, all the named functions can also be written with the concise syntax.</span></span> <span data-ttu-id="764c3-126">这两种方式编写的一些示例。</span><span class="sxs-lookup"><span data-stu-id="764c3-126">Some of the examples are written in both ways.</span></span>

## <a name="store-the-value-in-a-data-structure"></a><span data-ttu-id="764c3-127">应用商店中的数据结构的值</span><span class="sxs-lookup"><span data-stu-id="764c3-127">Store the Value in a Data Structure</span></span>

<span data-ttu-id="764c3-128">第一类值可以存储在一个数据结构。</span><span class="sxs-lookup"><span data-stu-id="764c3-128">A first-class value can be stored in a data structure.</span></span> <span data-ttu-id="764c3-129">下面的代码显示了将值存储在列表和元组中的示例。</span><span class="sxs-lookup"><span data-stu-id="764c3-129">The following code shows examples that store values in lists and in tuples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet23.fs)]

<span data-ttu-id="764c3-130">若要验证存储元组中的函数名称的确会实际计算的函数，下面的示例，请使用`fst`并`snd`运算符从元组中提取的第一个和第二个元素`funAndArgTuple`。</span><span class="sxs-lookup"><span data-stu-id="764c3-130">To verify that a function name stored in a tuple does in fact evaluate to a function, the following example uses the `fst` and `snd` operators to extract the first and second elements from tuple `funAndArgTuple`.</span></span> <span data-ttu-id="764c3-131">元组中的第一个元素是`squareIt`和第二个元素是`num`。</span><span class="sxs-lookup"><span data-stu-id="764c3-131">The first element in the tuple is `squareIt` and the second element is `num`.</span></span> <span data-ttu-id="764c3-132">标识符`num`绑定到的有效参数的整数 10 上, 一示例中`squareIt`函数。</span><span class="sxs-lookup"><span data-stu-id="764c3-132">Identifier `num` is bound in a previous example to integer 10, a valid argument for the `squareIt` function.</span></span> <span data-ttu-id="764c3-133">第二个表达式所应用到的元组中的第二个元素的元组中的第一个元素： `squareIt num`。</span><span class="sxs-lookup"><span data-stu-id="764c3-133">The second expression applies the first element in the tuple to the second element in the tuple: `squareIt num`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet24.fs)]

<span data-ttu-id="764c3-134">同样，就像标识符`num`整数 10 可以互换使用，因此可以标识符`squareIt`和 lambda 表达式`fun n -> n * n`。</span><span class="sxs-lookup"><span data-stu-id="764c3-134">Similarly, just as identifier `num` and integer 10 can be used interchangeably, so can identifier `squareIt` and lambda expression `fun n -> n * n`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet25.fs)]

## <a name="pass-the-value-as-an-argument"></a><span data-ttu-id="764c3-135">值作为参数传递</span><span class="sxs-lookup"><span data-stu-id="764c3-135">Pass the Value as an Argument</span></span>

<span data-ttu-id="764c3-136">如果值有一种语言中的第一类的状态，则可以它作为参数传递给函数。</span><span class="sxs-lookup"><span data-stu-id="764c3-136">If a value has first-class status in a language, you can pass it as an argument to a function.</span></span> <span data-ttu-id="764c3-137">例如，它是常见整数和字符串作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="764c3-137">For example, it is common to pass integers and strings as arguments.</span></span> <span data-ttu-id="764c3-138">下面的代码演示整数和 F # 中作为参数传递的字符串。</span><span class="sxs-lookup"><span data-stu-id="764c3-138">The following code shows integers and strings passed as arguments in F#.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet26.fs)]

<span data-ttu-id="764c3-139">如果函数的第一类的状态，您必须能够将它们作为参数传递相同的方式。</span><span class="sxs-lookup"><span data-stu-id="764c3-139">If functions have first-class status, you must be able to pass them as arguments in the same way.</span></span> <span data-ttu-id="764c3-140">请记住，这是高阶函数的第一个特征。</span><span class="sxs-lookup"><span data-stu-id="764c3-140">Remember that this is the first characteristic of higher-order functions.</span></span>

<span data-ttu-id="764c3-141">在以下示例中，函数`applyIt`具有两个参数`op`和`arg`。</span><span class="sxs-lookup"><span data-stu-id="764c3-141">In the following example, function `applyIt` has two parameters, `op` and `arg`.</span></span> <span data-ttu-id="764c3-142">如果您将发送具有一个参数的函数`op`和到函数的相应参数`arg`，该函数返回应用的结果`op`到`arg`。</span><span class="sxs-lookup"><span data-stu-id="764c3-142">If you send in a function that has one parameter for `op` and an appropriate argument for the function to `arg`, the function returns the result of applying `op` to `arg`.</span></span> <span data-ttu-id="764c3-143">在以下示例中，函数参数和整数自变量将发送相同方式使用它们的名称。</span><span class="sxs-lookup"><span data-stu-id="764c3-143">In the following example, both the function argument and the integer argument are sent in the same way, by using their names.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet27.fs)]

<span data-ttu-id="764c3-144">能够将函数作为参数发送到另一个函数是函数编程语言，例如映射或筛选器操作中的常见抽象的基础。</span><span class="sxs-lookup"><span data-stu-id="764c3-144">The ability to send a function as an argument to another function underlies common abstractions in functional programming languages, such as map or filter operations.</span></span> <span data-ttu-id="764c3-145">映射操作，例如，是捕获共享单步执行列表、 对每个元素进行一些操作，然后返回结果的列表的函数的计算，高阶函数。</span><span class="sxs-lookup"><span data-stu-id="764c3-145">A map operation, for example, is a higher-order function that captures the computation shared by functions that step through a list, do something to each element, and then return a list of the results.</span></span> <span data-ttu-id="764c3-146">您可能想要递增的整数，列表中每个元素或正方形每个元素，或更改为大写的字符串列表中每个元素。</span><span class="sxs-lookup"><span data-stu-id="764c3-146">You might want to increment each element in a list of integers, or to square each element, or to change each element in a list of strings to uppercase.</span></span> <span data-ttu-id="764c3-147">计算的易出错部分是递归过程的列表的步骤和生成的要返回的结果列表。</span><span class="sxs-lookup"><span data-stu-id="764c3-147">The error-prone part of the computation is the recursive process that steps through the list and builds a list of the results to return.</span></span> <span data-ttu-id="764c3-148">映射函数中捕获该部分。</span><span class="sxs-lookup"><span data-stu-id="764c3-148">That part is captured in the mapping function.</span></span> <span data-ttu-id="764c3-149">你已将某个特定应用程序是你想要单独应用于每个列表元素的函数 （添加、 求平方、 更改大小写）。</span><span class="sxs-lookup"><span data-stu-id="764c3-149">All you have to write for a particular application is the function that you want to apply to each list element individually (adding, squaring, changing case).</span></span> <span data-ttu-id="764c3-150">函数作为参数发送到映射函数，就像`squareIt`发送到`applyIt`在前面的示例。</span><span class="sxs-lookup"><span data-stu-id="764c3-150">That function is sent as an argument to the mapping function, just as `squareIt` is sent to `applyIt` in the previous example.</span></span>

<span data-ttu-id="764c3-151">F # 提供的映射方法对于大多数集合类型，包括[列出了](../language-reference/lists.md)，[数组](../language-reference/arrays.md)，并[序列](../language-reference/sequences.md)。</span><span class="sxs-lookup"><span data-stu-id="764c3-151">F# provides map methods for most collection types, including [lists](../language-reference/lists.md), [arrays](../language-reference/arrays.md), and [sequences](../language-reference/sequences.md).</span></span> <span data-ttu-id="764c3-152">下面的示例使用列表。</span><span class="sxs-lookup"><span data-stu-id="764c3-152">The following examples use lists.</span></span> <span data-ttu-id="764c3-153">语法是`List.map <the function> <the list>`。</span><span class="sxs-lookup"><span data-stu-id="764c3-153">The syntax is `List.map <the function> <the list>`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet28.fs)]

<span data-ttu-id="764c3-154">有关详细信息，请参阅[列出了](../language-reference/lists.md)。</span><span class="sxs-lookup"><span data-stu-id="764c3-154">For more information, see [Lists](../language-reference/lists.md).</span></span>

## <a name="return-the-value-from-a-function-call"></a><span data-ttu-id="764c3-155">从函数调用返回值</span><span class="sxs-lookup"><span data-stu-id="764c3-155">Return the Value from a Function Call</span></span>

<span data-ttu-id="764c3-156">最后，如果函数具有一种语言中的第一类的状态，您必须能够将其作为函数调用的值返回就像返回其他类型，如整数和字符串。</span><span class="sxs-lookup"><span data-stu-id="764c3-156">Finally, if a function has first-class status in a language, you must be able to return it as the value of a function call, just as you return other types, such as integers and strings.</span></span>

<span data-ttu-id="764c3-157">以下函数调用返回整数并将其显示。</span><span class="sxs-lookup"><span data-stu-id="764c3-157">The following function calls return integers and display them.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet29.fs)]

<span data-ttu-id="764c3-158">以下函数调用返回一个字符串。</span><span class="sxs-lookup"><span data-stu-id="764c3-158">The following function call returns a string.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet30.fs)]

<span data-ttu-id="764c3-159">以下函数调用中，声明为内联，返回一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="764c3-159">The following function call, declared inline, returns a Boolean value.</span></span> <span data-ttu-id="764c3-160">显示的值是`True`。</span><span class="sxs-lookup"><span data-stu-id="764c3-160">The value displayed is `True`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet31.fs)]

<span data-ttu-id="764c3-161">返回一个函数作为函数调用的值的功能是高阶函数的第二个特征。</span><span class="sxs-lookup"><span data-stu-id="764c3-161">The ability to return a function as the value of a function call is the second characteristic of higher-order functions.</span></span> <span data-ttu-id="764c3-162">在以下示例中，`checkFor`被定义为采用一个参数的函数`item`，并返回作为其值的新函数。</span><span class="sxs-lookup"><span data-stu-id="764c3-162">In the following example, `checkFor` is defined to be a function that takes one argument, `item`, and returns a new function as its value.</span></span> <span data-ttu-id="764c3-163">返回的函数采用一个列表作为其参数`lst`，并搜索`item`中`lst`。</span><span class="sxs-lookup"><span data-stu-id="764c3-163">The returned function takes a list as its argument, `lst`, and searches for `item` in `lst`.</span></span> <span data-ttu-id="764c3-164">如果`item`，则该函数将返回`true`。</span><span class="sxs-lookup"><span data-stu-id="764c3-164">If `item` is present, the function returns `true`.</span></span> <span data-ttu-id="764c3-165">如果`item`不存在，该函数将返回`false`。</span><span class="sxs-lookup"><span data-stu-id="764c3-165">If `item` is not present, the function returns `false`.</span></span> <span data-ttu-id="764c3-166">上一节中，以下代码使用提供的列表函数[List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8)，以在列表中搜索。</span><span class="sxs-lookup"><span data-stu-id="764c3-166">As in the previous section, the following code uses a provided list function, [List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8), to search the list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet32.fs)]

<span data-ttu-id="764c3-167">下面的代码使用`checkFor`若要创建新的函数采用一个自变量、 列表和 7 的搜索列表中。</span><span class="sxs-lookup"><span data-stu-id="764c3-167">The following code uses `checkFor` to create a new function that takes one argument, a list, and searches for 7 in the list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet33.fs)]

<span data-ttu-id="764c3-168">下面的示例使用在 F # 中函数的第一类状态来声明函数， `compose`，返回两个函数参数的组合。</span><span class="sxs-lookup"><span data-stu-id="764c3-168">The following example uses the first-class status of functions in F# to declare a function, `compose`, that returns a composition of two function arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet34.fs)]

>[!NOTE]
<span data-ttu-id="764c3-169">更短的版本，请参阅以下部分中，"扩充函数。"</span><span class="sxs-lookup"><span data-stu-id="764c3-169">For an even shorter version, see the following section, "Curried Functions."</span></span>

<span data-ttu-id="764c3-170">下面的代码将作为参数发送两个函数`compose`，这两个的这需要相同类型的单个参数。</span><span class="sxs-lookup"><span data-stu-id="764c3-170">The following code sends two functions as arguments to `compose`, both of which take a single argument of the same type.</span></span> <span data-ttu-id="764c3-171">返回值是一个新函数，则两个函数参数的组合。</span><span class="sxs-lookup"><span data-stu-id="764c3-171">The return value is a new function that is a composition of the two function arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet35.fs)]

>[!NOTE]
<span data-ttu-id="764c3-172">F # 提供了两个运算符`<<`和`>>`，组合函数。</span><span class="sxs-lookup"><span data-stu-id="764c3-172">F# provides two operators, `<<` and `>>`, that compose functions.</span></span> <span data-ttu-id="764c3-173">例如，`let squareAndDouble2 = doubleIt << squareIt`等效于`let squareAndDouble = compose doubleIt squareIt`在前面的示例。</span><span class="sxs-lookup"><span data-stu-id="764c3-173">For example, `let squareAndDouble2 = doubleIt << squareIt` is equivalent to `let squareAndDouble = compose doubleIt squareIt` in the previous example.</span></span>

<span data-ttu-id="764c3-174">返回一个函数作为函数调用的值的以下示例创建一个简单的猜测游戏。</span><span class="sxs-lookup"><span data-stu-id="764c3-174">The following example of returning a function as the value of a function call creates a simple guessing game.</span></span> <span data-ttu-id="764c3-175">若要创建一个游戏，调用`makeGame`的值，希望有人猜测中发送`target`。</span><span class="sxs-lookup"><span data-stu-id="764c3-175">To create a game, call `makeGame` with the value that you want someone to guess sent in for `target`.</span></span> <span data-ttu-id="764c3-176">函数的返回值`makeGame`是接受一个参数 （猜测值），并报告猜测是正确的函数。</span><span class="sxs-lookup"><span data-stu-id="764c3-176">The return value from function `makeGame` is a function that takes one argument (the guess) and reports whether the guess is correct.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet36.fs)]

<span data-ttu-id="764c3-177">下面的代码调用`makeGame`，将值发送`7`为`target`。</span><span class="sxs-lookup"><span data-stu-id="764c3-177">The following code calls `makeGame`, sending the value `7` for `target`.</span></span> <span data-ttu-id="764c3-178">标识符`playGame`绑定到返回的 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="764c3-178">Identifier `playGame` is bound to the returned lambda expression.</span></span> <span data-ttu-id="764c3-179">因此，`playGame`是一个函数，将作为它的一个参数值为`guess`。</span><span class="sxs-lookup"><span data-stu-id="764c3-179">Therefore, `playGame` is a function that takes as its one argument a value for `guess`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet37.fs)]

## <a name="curried-functions"></a><span data-ttu-id="764c3-180">扩充的函数</span><span class="sxs-lookup"><span data-stu-id="764c3-180">Curried Functions</span></span>

<span data-ttu-id="764c3-181">可以通过利用隐式更简洁地编写的示例在上一节中的许多*科*F # 函数声明中。</span><span class="sxs-lookup"><span data-stu-id="764c3-181">Many of the examples in the previous section can be written more concisely by taking advantage of the implicit *currying* in F# function declarations.</span></span> <span data-ttu-id="764c3-182">科是一个转换具有多个参数为一系列的嵌入功能，其中每个具有单个参数的函数的过程。</span><span class="sxs-lookup"><span data-stu-id="764c3-182">Currying is a process that transforms a function that has more than one parameter into a series of embedded functions, each of which has a single parameter.</span></span> <span data-ttu-id="764c3-183">在 F # 中，都会被扩充具有多个参数的函数。</span><span class="sxs-lookup"><span data-stu-id="764c3-183">In F#, functions that have more than one parameter are inherently curried.</span></span> <span data-ttu-id="764c3-184">例如，`compose`从上一节可以编写以下简洁样式，带有三个参数中所示。</span><span class="sxs-lookup"><span data-stu-id="764c3-184">For example, `compose` from the previous section can be written as shown in the following concise style, with three parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet38.fs)]

<span data-ttu-id="764c3-185">但是，结果是返回一个参数，它又会返回一个参数的另一个函数的函数，如中所示的一个参数的函数`compose4curried`。</span><span class="sxs-lookup"><span data-stu-id="764c3-185">However, the result is a function of one parameter that returns a function of one parameter that in turn returns another function of one parameter, as shown in `compose4curried`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet39.fs)]

<span data-ttu-id="764c3-186">您可以访问以下几种方式的此函数。</span><span class="sxs-lookup"><span data-stu-id="764c3-186">You can access this function in several ways.</span></span> <span data-ttu-id="764c3-187">下面的示例的每个返回并显示 18。</span><span class="sxs-lookup"><span data-stu-id="764c3-187">Each of the following examples returns and displays 18.</span></span> <span data-ttu-id="764c3-188">您可以替换`compose4`与`compose4curried`中任何示例。</span><span class="sxs-lookup"><span data-stu-id="764c3-188">You can replace `compose4` with `compose4curried` in any of the examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet40.fs)]

<span data-ttu-id="764c3-189">若要验证函数仍像以前一样工作，试一次原始测试用例。</span><span class="sxs-lookup"><span data-stu-id="764c3-189">To verify that the function still works as it did before, try the original test cases again.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet41.fs)]

>[!NOTE]
<span data-ttu-id="764c3-190">你可以限制科参数括在元组中。</span><span class="sxs-lookup"><span data-stu-id="764c3-190">You can restrict currying by enclosing parameters in tuples.</span></span> <span data-ttu-id="764c3-191">详细信息，请参阅"参数模式"中[形参和实参](../language-reference/parameters-and-arguments.md)。</span><span class="sxs-lookup"><span data-stu-id="764c3-191">For more information, see "Parameter Patterns" in [Parameters and Arguments](../language-reference/parameters-and-arguments.md).</span></span>

<span data-ttu-id="764c3-192">下面的示例使用隐式扩充编写的简短版本`makeGame`。</span><span class="sxs-lookup"><span data-stu-id="764c3-192">The following example uses implicit currying to write a shorter version of `makeGame`.</span></span> <span data-ttu-id="764c3-193">如何的详细信息`makeGame`构造并返回`game`函数不太明确按以下格式，但你可以通过使用原始的结果是相同的测试用例验证。</span><span class="sxs-lookup"><span data-stu-id="764c3-193">The details of how `makeGame` constructs and returns the `game` function are less explicit in this format, but you can verify by using the original test cases that the result is the same.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet42.fs)]

<span data-ttu-id="764c3-194">科的详细信息，请参阅"的参数的部分应用程序"中[函数](../language-reference/functions/index.md)。</span><span class="sxs-lookup"><span data-stu-id="764c3-194">For more information about currying, see "Partial Application of Arguments" in [Functions](../language-reference/functions/index.md).</span></span>

## <a name="identifier-and-function-definition-are-interchangeable"></a><span data-ttu-id="764c3-195">是可互换的标识符和函数定义</span><span class="sxs-lookup"><span data-stu-id="764c3-195">Identifier and Function Definition Are Interchangeable</span></span>

<span data-ttu-id="764c3-196">变量名称`num`中的上一个示例的计算结果为整数 10，并不奇怪，因为`num`是有效，10 也是有效的。</span><span class="sxs-lookup"><span data-stu-id="764c3-196">The variable name `num` in the previous examples evaluates to the integer 10, and it is no surprise that where `num` is valid, 10 is also valid.</span></span> <span data-ttu-id="764c3-197">这同样适用的函数标识符和它们的值： 可以随处可用的函数的名称，使用绑定到的 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="764c3-197">The same is true of function identifiers and their values: anywhere the name of the function can be used, the lambda expression to which it is bound can be used.</span></span>

<span data-ttu-id="764c3-198">下面的示例定义`Boolean`调用的函数`isNegative`，然后互换使用的函数的名称和函数的定义。</span><span class="sxs-lookup"><span data-stu-id="764c3-198">The following example defines a `Boolean` function called `isNegative`, and then uses the name of the function and the definition of the function interchangeably.</span></span> <span data-ttu-id="764c3-199">接下来三个示例都返回并显示`False`。</span><span class="sxs-lookup"><span data-stu-id="764c3-199">The next three examples all return and display `False`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet43.fs)]

<span data-ttu-id="764c3-200">若要进一步它一个步骤，替换为的值的`applyIt`为绑定到`applyIt`。</span><span class="sxs-lookup"><span data-stu-id="764c3-200">To take it one step further, substitute the value that `applyIt` is bound to for `applyIt`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet44.fs)]

## <a name="functions-are-first-class-values-in-f"></a><span data-ttu-id="764c3-201">函数是 F 中的第一类值\#</span><span class="sxs-lookup"><span data-stu-id="764c3-201">Functions Are First-Class Values in F\#</span></span>

<span data-ttu-id="764c3-202">前面几节中的示例演示 F # 中的函数满足 F # 中的一类值的条件：</span><span class="sxs-lookup"><span data-stu-id="764c3-202">The examples in the previous sections demonstrate that functions in F# satisfy the criteria for being first-class values in F#:</span></span>

- <span data-ttu-id="764c3-203">可以绑定到函数定义的标识符。</span><span class="sxs-lookup"><span data-stu-id="764c3-203">You can bind an identifier to a function definition.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet21.fs)]

- <span data-ttu-id="764c3-204">您可以在数据结构存储函数。</span><span class="sxs-lookup"><span data-stu-id="764c3-204">You can store a function in a data structure.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet45.fs)]

- <span data-ttu-id="764c3-205">可以将函数作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="764c3-205">You can pass a function as an argument.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet46.fs)]

- <span data-ttu-id="764c3-206">可以将函数作为函数调用的值返回。</span><span class="sxs-lookup"><span data-stu-id="764c3-206">You can return a function as the value of a function call.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet32.fs)]

<span data-ttu-id="764c3-207">有关 F # 的详细信息，请参阅[F # 语言参考](../language-reference/index.md)。</span><span class="sxs-lookup"><span data-stu-id="764c3-207">For more information about F#, see the [F# Language Reference](../language-reference/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="764c3-208">示例</span><span class="sxs-lookup"><span data-stu-id="764c3-208">Example</span></span>

### <a name="description"></a><span data-ttu-id="764c3-209">描述</span><span class="sxs-lookup"><span data-stu-id="764c3-209">Description</span></span>

<span data-ttu-id="764c3-210">下面的代码包含本主题中的所有示例。</span><span class="sxs-lookup"><span data-stu-id="764c3-210">The following code contains all the examples in this topic.</span></span>

### <a name="code"></a><span data-ttu-id="764c3-211">代码</span><span class="sxs-lookup"><span data-stu-id="764c3-211">Code</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet47.fs)]

## <a name="see-also"></a><span data-ttu-id="764c3-212">请参阅</span><span class="sxs-lookup"><span data-stu-id="764c3-212">See also</span></span>

- [<span data-ttu-id="764c3-213">列表</span><span class="sxs-lookup"><span data-stu-id="764c3-213">Lists</span></span>](../language-reference/lists.md)
- [<span data-ttu-id="764c3-214">元组</span><span class="sxs-lookup"><span data-stu-id="764c3-214">Tuples</span></span>](../language-reference/tuples.md)
- [<span data-ttu-id="764c3-215">函数</span><span class="sxs-lookup"><span data-stu-id="764c3-215">Functions</span></span>](../language-reference/functions/index.md)
- [<span data-ttu-id="764c3-216">`let` 绑定</span><span class="sxs-lookup"><span data-stu-id="764c3-216">`let` Bindings</span></span>](../language-reference/functions/let-bindings.md)
- [<span data-ttu-id="764c3-217">Lambda 表达式：`fun`关键字</span><span class="sxs-lookup"><span data-stu-id="764c3-217">Lambda Expressions: The `fun` Keyword</span></span>](../language-reference/functions/lambda-expressions-the-fun-keyword.md)
