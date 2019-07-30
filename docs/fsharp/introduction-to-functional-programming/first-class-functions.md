---
title: 头等函数
description: 了解第一类函数以及它们对于中F#的函数编程是非常重要的。
ms.date: 10/29/2018
ms.openlocfilehash: 4681d32abd59cc4aade6f4cb2d062e7888bcfbbc
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629713"
---
# <a name="first-class-functions"></a><span data-ttu-id="b5a7e-103">头等函数</span><span class="sxs-lookup"><span data-stu-id="b5a7e-103">First-class functions</span></span>

<span data-ttu-id="b5a7e-104">函数编程语言的一种定义特性是将函数提升为第一类状态。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-104">A defining characteristic of functional programming languages is the elevation of functions to first-class status.</span></span> <span data-ttu-id="b5a7e-105">您应该能够对使用其他内置类型的值的函数执行任何操作, 并且能够以相当的工作量来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-105">You should be able to do with a function whatever you can do with values of the other built-in types, and be able to do so with a comparable degree of effort.</span></span>

<span data-ttu-id="b5a7e-106">第一类状态的典型度量值包括:</span><span class="sxs-lookup"><span data-stu-id="b5a7e-106">Typical measures of first-class status include the following:</span></span>

- <span data-ttu-id="b5a7e-107">是否可以将函数绑定到标识符？</span><span class="sxs-lookup"><span data-stu-id="b5a7e-107">Can you bind functions to identifiers?</span></span> <span data-ttu-id="b5a7e-108">也就是说, 可以为其指定名称吗？</span><span class="sxs-lookup"><span data-stu-id="b5a7e-108">That is, can you give them names?</span></span>

- <span data-ttu-id="b5a7e-109">能否在数据结构 (如列表中) 中存储函数？</span><span class="sxs-lookup"><span data-stu-id="b5a7e-109">Can you store functions in data structures, such as in a list?</span></span>

- <span data-ttu-id="b5a7e-110">是否可以在函数调用中将函数作为参数传递？</span><span class="sxs-lookup"><span data-stu-id="b5a7e-110">Can you pass a function as an argument in a function call?</span></span>

- <span data-ttu-id="b5a7e-111">是否可以从函数调用返回函数？</span><span class="sxs-lookup"><span data-stu-id="b5a7e-111">Can you return a function from a function call?</span></span>

<span data-ttu-id="b5a7e-112">最后两个度量值定义了所谓的*高阶运算*或*高阶函数*。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-112">The last two measures define what are known as *higher-order operations* or *higher-order functions*.</span></span> <span data-ttu-id="b5a7e-113">高阶函数接受函数作为参数, 并返回函数作为函数调用的值。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-113">Higher-order functions accept functions as arguments and return functions as the value of function calls.</span></span> <span data-ttu-id="b5a7e-114">这些操作支持将函数编程作为映射函数和函数的组合。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-114">These operations support such mainstays of functional programming as mapping functions and composition of functions.</span></span>

## <a name="give-the-value-a-name"></a><span data-ttu-id="b5a7e-115">为值指定名称</span><span class="sxs-lookup"><span data-stu-id="b5a7e-115">Give the Value a Name</span></span>

<span data-ttu-id="b5a7e-116">如果函数是第一类值, 则您必须能够命名它, 就像您命名整数、字符串和其他内置类型一样。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-116">If a function is a first-class value, you must be able to name it, just as you can name integers, strings, and other built-in types.</span></span> <span data-ttu-id="b5a7e-117">这在函数编程文献中称为将标识符绑定到某个值。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-117">This is referred to in functional programming literature as binding an identifier to a value.</span></span> <span data-ttu-id="b5a7e-118">F#`let <identifier> = <value>` [使用`let`绑定](../language-reference/functions/let-bindings.md)将名称绑定到值:。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-118">F# uses [`let` bindings](../language-reference/functions/let-bindings.md) to bind names to values: `let <identifier> = <value>`.</span></span> <span data-ttu-id="b5a7e-119">下面的代码演示了两个示例。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-119">The following code shows two examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet20.fs)]

<span data-ttu-id="b5a7e-120">您可以轻松地命名函数。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-120">You can name a function just as easily.</span></span> <span data-ttu-id="b5a7e-121">下面的示例定义了一个名`squareIt`为的函数, `squareIt`该函数将标识符绑定到[lambda 表达式](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n`。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-121">The following example defines a function named `squareIt` by binding the identifier `squareIt` to the [lambda expression](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n`.</span></span> <span data-ttu-id="b5a7e-122">函数`squareIt`具有一个参数, `n`并返回该参数的平方。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-122">Function `squareIt` has one parameter, `n`, and it returns the square of that parameter.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet21.fs)]

<span data-ttu-id="b5a7e-123">F#提供了以下更简洁的语法来实现相同的结果, 但键入的内容更少。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-123">F# provides the following more concise syntax to achieve the same result with less typing.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet22.fs)]

<span data-ttu-id="b5a7e-124">下面的示例使用第一种样式`let <function-name> = <lambda-expression>`来强调函数声明和其他类型值的声明之间的相似之处。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-124">The examples that follow mostly use the first style, `let <function-name> = <lambda-expression>`, to emphasize the similarities between the declaration of functions and the declaration of other types of values.</span></span> <span data-ttu-id="b5a7e-125">但是, 还可以用简洁的语法来编写所有命名函数。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-125">However, all the named functions can also be written with the concise syntax.</span></span> <span data-ttu-id="b5a7e-126">其中的一些示例是以这两种方式编写的。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-126">Some of the examples are written in both ways.</span></span>

## <a name="store-the-value-in-a-data-structure"></a><span data-ttu-id="b5a7e-127">将值存储在数据结构中</span><span class="sxs-lookup"><span data-stu-id="b5a7e-127">Store the Value in a Data Structure</span></span>

<span data-ttu-id="b5a7e-128">第一类值可以存储在数据结构中。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-128">A first-class value can be stored in a data structure.</span></span> <span data-ttu-id="b5a7e-129">下面的代码演示将值存储在列表和元组中的示例。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-129">The following code shows examples that store values in lists and in tuples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet23.fs)]

<span data-ttu-id="b5a7e-130">若要验证存储在元组中的函数名称实际上是否计算为函数, 下面的示例使用`fst`和`snd`运算符从元组`funAndArgTuple`中提取第一个和第二个元素。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-130">To verify that a function name stored in a tuple does in fact evaluate to a function, the following example uses the `fst` and `snd` operators to extract the first and second elements from tuple `funAndArgTuple`.</span></span> <span data-ttu-id="b5a7e-131">元组中的第一个元素`squareIt`是, 第二个`num`元素是。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-131">The first element in the tuple is `squareIt` and the second element is `num`.</span></span> <span data-ttu-id="b5a7e-132">标识符`num`在前面的示例中绑定到整数 10, 这是`squareIt`函数的有效参数。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-132">Identifier `num` is bound in a previous example to integer 10, a valid argument for the `squareIt` function.</span></span> <span data-ttu-id="b5a7e-133">第二个表达式将元组中的第一个元素应用到元组中的`squareIt num`第二个元素:。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-133">The second expression applies the first element in the tuple to the second element in the tuple: `squareIt num`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet24.fs)]

<span data-ttu-id="b5a7e-134">同样, 可以互换使用`num`标识符和整数 10, 因此可以使用标识符`squareIt`和 lambda 表达式`fun n -> n * n`。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-134">Similarly, just as identifier `num` and integer 10 can be used interchangeably, so can identifier `squareIt` and lambda expression `fun n -> n * n`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet25.fs)]

## <a name="pass-the-value-as-an-argument"></a><span data-ttu-id="b5a7e-135">将值作为参数传递</span><span class="sxs-lookup"><span data-stu-id="b5a7e-135">Pass the Value as an Argument</span></span>

<span data-ttu-id="b5a7e-136">如果某个值具有语言形式的第一类状态, 则可以将其作为参数传递给函数。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-136">If a value has first-class status in a language, you can pass it as an argument to a function.</span></span> <span data-ttu-id="b5a7e-137">例如, 通常将整数和字符串作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-137">For example, it is common to pass integers and strings as arguments.</span></span> <span data-ttu-id="b5a7e-138">下面的代码显示了在中作为参数传递的F#整数和字符串。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-138">The following code shows integers and strings passed as arguments in F#.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet26.fs)]

<span data-ttu-id="b5a7e-139">如果函数具有一流状态, 则您必须能够以相同的方式将它们作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-139">If functions have first-class status, you must be able to pass them as arguments in the same way.</span></span> <span data-ttu-id="b5a7e-140">请记住, 这是高阶函数的第一个特征。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-140">Remember that this is the first characteristic of higher-order functions.</span></span>

<span data-ttu-id="b5a7e-141">在下面的示例中, `applyIt`函数具有两个`op`参数`arg`: 和。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-141">In the following example, function `applyIt` has two parameters, `op` and `arg`.</span></span> <span data-ttu-id="b5a7e-142">如果在具有`op`一个参数的函数中进行发送, 并向提供`arg`函数的适当参数, 则函数将返回应用`op`到`arg`的结果。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-142">If you send in a function that has one parameter for `op` and an appropriate argument for the function to `arg`, the function returns the result of applying `op` to `arg`.</span></span> <span data-ttu-id="b5a7e-143">在下面的示例中, 函数参数和整数参数都是通过使用其名称以相同方式发送的。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-143">In the following example, both the function argument and the integer argument are sent in the same way, by using their names.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet27.fs)]

<span data-ttu-id="b5a7e-144">将函数作为自变量发送到另一个函数的能力是在函数编程语言 (例如映射或筛选器操作) 中为常见的抽象。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-144">The ability to send a function as an argument to another function underlies common abstractions in functional programming languages, such as map or filter operations.</span></span> <span data-ttu-id="b5a7e-145">例如, 映射操作是一个高阶函数, 该函数捕获逐句通过列表的函数所共享的计算, 对每个元素执行一些操作, 然后返回结果列表。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-145">A map operation, for example, is a higher-order function that captures the computation shared by functions that step through a list, do something to each element, and then return a list of the results.</span></span> <span data-ttu-id="b5a7e-146">您可能想要在一个整数列表中递增每个元素, 或在每个元素的后面递增, 或将字符串列表中的每个元素更改为大写。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-146">You might want to increment each element in a list of integers, or to square each element, or to change each element in a list of strings to uppercase.</span></span> <span data-ttu-id="b5a7e-147">计算中易出错的部分是单步执行列表并生成要返回的结果列表的递归过程。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-147">The error-prone part of the computation is the recursive process that steps through the list and builds a list of the results to return.</span></span> <span data-ttu-id="b5a7e-148">该部件在映射函数中捕获。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-148">That part is captured in the mapping function.</span></span> <span data-ttu-id="b5a7e-149">对于特定应用程序, 只需对每个列表元素分别应用 (添加、求平方、变化大小写)。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-149">All you have to write for a particular application is the function that you want to apply to each list element individually (adding, squaring, changing case).</span></span> <span data-ttu-id="b5a7e-150">该函数作为参数发送到 mapping 函数, 就像`squareIt` `applyIt`在前面的示例中一样。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-150">That function is sent as an argument to the mapping function, just as `squareIt` is sent to `applyIt` in the previous example.</span></span>

<span data-ttu-id="b5a7e-151">F#为大多数集合类型 (包括[列表](../language-reference/lists.md)、[数组](../language-reference/arrays.md)和[序列](../language-reference/sequences.md)) 提供映射方法。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-151">F# provides map methods for most collection types, including [lists](../language-reference/lists.md), [arrays](../language-reference/arrays.md), and [sequences](../language-reference/sequences.md).</span></span> <span data-ttu-id="b5a7e-152">下面的示例使用列表。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-152">The following examples use lists.</span></span> <span data-ttu-id="b5a7e-153">语法为`List.map <the function> <the list>`。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-153">The syntax is `List.map <the function> <the list>`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet28.fs)]

<span data-ttu-id="b5a7e-154">有关详细信息, 请参阅[列表](../language-reference/lists.md)。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-154">For more information, see [Lists](../language-reference/lists.md).</span></span>

## <a name="return-the-value-from-a-function-call"></a><span data-ttu-id="b5a7e-155">从函数调用返回值</span><span class="sxs-lookup"><span data-stu-id="b5a7e-155">Return the Value from a Function Call</span></span>

<span data-ttu-id="b5a7e-156">最后, 如果某个函数在某种语言中具有一流状态, 则您必须能够将其作为函数调用的值返回, 就像您返回其他类型 (如整数和字符串) 一样。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-156">Finally, if a function has first-class status in a language, you must be able to return it as the value of a function call, just as you return other types, such as integers and strings.</span></span>

<span data-ttu-id="b5a7e-157">以下函数调用返回整数并显示它们。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-157">The following function calls return integers and display them.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet29.fs)]

<span data-ttu-id="b5a7e-158">以下函数调用返回一个字符串。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-158">The following function call returns a string.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet30.fs)]

<span data-ttu-id="b5a7e-159">以下函数调用 (以内联方式声明) 将返回一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-159">The following function call, declared inline, returns a Boolean value.</span></span> <span data-ttu-id="b5a7e-160">显示的值为`True`。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-160">The value displayed is `True`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet31.fs)]

<span data-ttu-id="b5a7e-161">将函数作为函数调用值返回的能力是高阶函数的第二个特征。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-161">The ability to return a function as the value of a function call is the second characteristic of higher-order functions.</span></span> <span data-ttu-id="b5a7e-162">在下面的示例中`checkFor` , 将定义为一个函数, 该函数采用一个`item`参数, 并返回一个新函数作为其值。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-162">In the following example, `checkFor` is defined to be a function that takes one argument, `item`, and returns a new function as its value.</span></span> <span data-ttu-id="b5a7e-163">返回的函数采用列表作为其参数, `lst`并在中`lst`进行`item`搜索。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-163">The returned function takes a list as its argument, `lst`, and searches for `item` in `lst`.</span></span> <span data-ttu-id="b5a7e-164">如果`item`存在, 则该函数返回`true`。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-164">If `item` is present, the function returns `true`.</span></span> <span data-ttu-id="b5a7e-165">如果`item`不存在, 则该函数将`false`返回。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-165">If `item` is not present, the function returns `false`.</span></span> <span data-ttu-id="b5a7e-166">如上一节所示, 以下代码使用提供的列表函数[list](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8), 以搜索列表。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-166">As in the previous section, the following code uses a provided list function, [List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8), to search the list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet32.fs)]

<span data-ttu-id="b5a7e-167">下面的代码使用`checkFor`创建一个新函数, 该函数采用一个自变量和一个列表, 并在列表中搜索7。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-167">The following code uses `checkFor` to create a new function that takes one argument, a list, and searches for 7 in the list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet33.fs)]

<span data-ttu-id="b5a7e-168">下面的示例使用中F#函数的第一类状态声明一个函数, `compose`该函数返回两个函数参数的组合。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-168">The following example uses the first-class status of functions in F# to declare a function, `compose`, that returns a composition of two function arguments.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet34.fs)]

> [!NOTE]
> <span data-ttu-id="b5a7e-169">对于更短的版本, 请参阅下一节 "扩充函数"。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-169">For an even shorter version, see the following section, "Curried Functions."</span></span>

<span data-ttu-id="b5a7e-170">下面的代码将两个函数作为自`compose`变量发送到, 这两个函数都采用同一类型的单个自变量。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-170">The following code sends two functions as arguments to `compose`, both of which take a single argument of the same type.</span></span> <span data-ttu-id="b5a7e-171">返回值是一个新函数, 它是两个函数参数的组合。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-171">The return value is a new function that is a composition of the two function arguments.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet35.fs)]

> [!NOTE]
> <span data-ttu-id="b5a7e-172">F#提供两个编写`<<`函数`>>`的运算符和。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-172">F# provides two operators, `<<` and `>>`, that compose functions.</span></span> <span data-ttu-id="b5a7e-173">例如, `let squareAndDouble = compose doubleIt squareIt`在`let squareAndDouble2 = doubleIt << squareIt`前面的示例中, 等效于。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-173">For example, `let squareAndDouble2 = doubleIt << squareIt` is equivalent to `let squareAndDouble = compose doubleIt squareIt` in the previous example.</span></span>

<span data-ttu-id="b5a7e-174">以下用于将函数作为函数调用值返回的示例将创建一个简单的推测游戏。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-174">The following example of returning a function as the value of a function call creates a simple guessing game.</span></span> <span data-ttu-id="b5a7e-175">若要创建游戏, 请`makeGame`调用, 并在中调用要将其发送到的`target`某个值。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-175">To create a game, call `makeGame` with the value that you want someone to guess sent in for `target`.</span></span> <span data-ttu-id="b5a7e-176">函数`makeGame`的返回值是一个函数, 它采用一个参数 (guess) 并报告推测是否正确。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-176">The return value from function `makeGame` is a function that takes one argument (the guess) and reports whether the guess is correct.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet36.fs)]

<span data-ttu-id="b5a7e-177">下面的代码调用`makeGame`, 并发送的`7` `target`值。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-177">The following code calls `makeGame`, sending the value `7` for `target`.</span></span> <span data-ttu-id="b5a7e-178">标识符`playGame`绑定到返回的 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-178">Identifier `playGame` is bound to the returned lambda expression.</span></span> <span data-ttu-id="b5a7e-179">因此, `playGame`它是一个函数, 它将作为一个参数的`guess`值。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-179">Therefore, `playGame` is a function that takes as its one argument a value for `guess`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet37.fs)]

## <a name="curried-functions"></a><span data-ttu-id="b5a7e-180">扩充函数</span><span class="sxs-lookup"><span data-stu-id="b5a7e-180">Curried Functions</span></span>

<span data-ttu-id="b5a7e-181">可以通过利用函数声明中F#的隐式*currying* , 将上一节中的许多示例编写得更简洁。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-181">Many of the examples in the previous section can be written more concisely by taking advantage of the implicit *currying* in F# function declarations.</span></span> <span data-ttu-id="b5a7e-182">Currying 是将具有多个参数的函数转换为一系列嵌入函数的过程, 其中每个函数都有一个参数。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-182">Currying is a process that transforms a function that has more than one parameter into a series of embedded functions, each of which has a single parameter.</span></span> <span data-ttu-id="b5a7e-183">在F#中, 具有多个参数的函数在本质上是扩充的。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-183">In F#, functions that have more than one parameter are inherently curried.</span></span> <span data-ttu-id="b5a7e-184">例如, `compose`可以按照下面的简洁样式中所示, 用三个参数来编写上述部分。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-184">For example, `compose` from the previous section can be written as shown in the following concise style, with three parameters.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet38.fs)]

<span data-ttu-id="b5a7e-185">但是, 结果是一个参数的函数, 该函数返回一个参数的函数, 该函数反过来返回一个参数的另一个函数, 如中`compose4curried`所示。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-185">However, the result is a function of one parameter that returns a function of one parameter that in turn returns another function of one parameter, as shown in `compose4curried`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet39.fs)]

<span data-ttu-id="b5a7e-186">可以通过多种方式访问此函数。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-186">You can access this function in several ways.</span></span> <span data-ttu-id="b5a7e-187">下面的每个示例都返回并显示18。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-187">Each of the following examples returns and displays 18.</span></span> <span data-ttu-id="b5a7e-188">您可以在`compose4`任何`compose4curried`示例中将替换为。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-188">You can replace `compose4` with `compose4curried` in any of the examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet40.fs)]

<span data-ttu-id="b5a7e-189">若要验证函数是否仍像以前一样工作, 请再次尝试原始测试用例。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-189">To verify that the function still works as it did before, try the original test cases again.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet41.fs)]

> [!NOTE]
> <span data-ttu-id="b5a7e-190">可以通过在元组中包含参数来限制 currying。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-190">You can restrict currying by enclosing parameters in tuples.</span></span> <span data-ttu-id="b5a7e-191">有关详细信息, 请参阅[参数和参数](../language-reference/parameters-and-arguments.md)中的 "参数模式"。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-191">For more information, see "Parameter Patterns" in [Parameters and Arguments](../language-reference/parameters-and-arguments.md).</span></span>

<span data-ttu-id="b5a7e-192">下面的示例使用隐式 currying 来编写较短的`makeGame`版本。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-192">The following example uses implicit currying to write a shorter version of `makeGame`.</span></span> <span data-ttu-id="b5a7e-193">在此格式中`makeGame` , 构造和`game`返回函数的方式的详细信息不太明确, 但你可以使用结果相同的原始测试用例进行验证。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-193">The details of how `makeGame` constructs and returns the `game` function are less explicit in this format, but you can verify by using the original test cases that the result is the same.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet42.fs)]

<span data-ttu-id="b5a7e-194">有关 currying 的详细信息, 请参阅[函数](../language-reference/functions/index.md)中的 "参数的部分应用"。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-194">For more information about currying, see "Partial Application of Arguments" in [Functions](../language-reference/functions/index.md).</span></span>

## <a name="identifier-and-function-definition-are-interchangeable"></a><span data-ttu-id="b5a7e-195">标识符和函数定义可互换</span><span class="sxs-lookup"><span data-stu-id="b5a7e-195">Identifier and Function Definition Are Interchangeable</span></span>

<span data-ttu-id="b5a7e-196">前面的示例`num`中的变量名的计算结果为整数 10, 并且在其中`num`有效的情况下, 也是很奇怪的, 10 也是有效的。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-196">The variable name `num` in the previous examples evaluates to the integer 10, and it is no surprise that where `num` is valid, 10 is also valid.</span></span> <span data-ttu-id="b5a7e-197">函数标识符及其值也是如此: 任何位置都可以使用函数的名称, 可以使用它绑定到的 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-197">The same is true of function identifiers and their values: anywhere the name of the function can be used, the lambda expression to which it is bound can be used.</span></span>

<span data-ttu-id="b5a7e-198">下面的示例定义了`Boolean`一个名`isNegative`为的函数, 然后使用函数的名称和函数的定义。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-198">The following example defines a `Boolean` function called `isNegative`, and then uses the name of the function and the definition of the function interchangeably.</span></span> <span data-ttu-id="b5a7e-199">接下来的三个示例都返回`False`并显示。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-199">The next three examples all return and display `False`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet43.fs)]

<span data-ttu-id="b5a7e-200">若要进一步执行此`applyIt`操作, 请将绑定到的值替换为。 `applyIt`</span><span class="sxs-lookup"><span data-stu-id="b5a7e-200">To take it one step further, substitute the value that `applyIt` is bound to for `applyIt`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet44.fs)]

## <a name="functions-are-first-class-values-in-f"></a><span data-ttu-id="b5a7e-201">函数是 F 中的第一类值\#</span><span class="sxs-lookup"><span data-stu-id="b5a7e-201">Functions Are First-Class Values in F\#</span></span>

<span data-ttu-id="b5a7e-202">前面几节中的示例说明中F#的函数满足中第一类值的条件: F#</span><span class="sxs-lookup"><span data-stu-id="b5a7e-202">The examples in the previous sections demonstrate that functions in F# satisfy the criteria for being first-class values in F#:</span></span>

- <span data-ttu-id="b5a7e-203">可以将标识符绑定到函数定义。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-203">You can bind an identifier to a function definition.</span></span>
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet21.fs)]

- <span data-ttu-id="b5a7e-204">您可以将函数存储在数据结构中。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-204">You can store a function in a data structure.</span></span>
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet45.fs)]

- <span data-ttu-id="b5a7e-205">可以将函数作为自变量传递。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-205">You can pass a function as an argument.</span></span>
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet46.fs)]

- <span data-ttu-id="b5a7e-206">您可以返回函数作为函数调用的值。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-206">You can return a function as the value of a function call.</span></span>
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet32.fs)]

<span data-ttu-id="b5a7e-207">有关的详细信息F#, 请参阅[ F#语言参考](../language-reference/index.md)。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-207">For more information about F#, see the [F# Language Reference](../language-reference/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="b5a7e-208">示例</span><span class="sxs-lookup"><span data-stu-id="b5a7e-208">Example</span></span>

### <a name="description"></a><span data-ttu-id="b5a7e-209">描述</span><span class="sxs-lookup"><span data-stu-id="b5a7e-209">Description</span></span>

<span data-ttu-id="b5a7e-210">下面的代码包含本主题中的所有示例。</span><span class="sxs-lookup"><span data-stu-id="b5a7e-210">The following code contains all the examples in this topic.</span></span>

### <a name="code"></a><span data-ttu-id="b5a7e-211">代码</span><span class="sxs-lookup"><span data-stu-id="b5a7e-211">Code</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet47.fs)]

## <a name="see-also"></a><span data-ttu-id="b5a7e-212">请参阅</span><span class="sxs-lookup"><span data-stu-id="b5a7e-212">See also</span></span>

- [<span data-ttu-id="b5a7e-213">列表</span><span class="sxs-lookup"><span data-stu-id="b5a7e-213">Lists</span></span>](../language-reference/lists.md)
- [<span data-ttu-id="b5a7e-214">元组</span><span class="sxs-lookup"><span data-stu-id="b5a7e-214">Tuples</span></span>](../language-reference/tuples.md)
- [<span data-ttu-id="b5a7e-215">函数</span><span class="sxs-lookup"><span data-stu-id="b5a7e-215">Functions</span></span>](../language-reference/functions/index.md)
- [<span data-ttu-id="b5a7e-216">`let`绑定</span><span class="sxs-lookup"><span data-stu-id="b5a7e-216">`let` Bindings</span></span>](../language-reference/functions/let-bindings.md)
- [<span data-ttu-id="b5a7e-217">Lambda 表达式:`fun` 关键字</span><span class="sxs-lookup"><span data-stu-id="b5a7e-217">Lambda Expressions: The `fun` Keyword</span></span>](../language-reference/functions/lambda-expressions-the-fun-keyword.md)
