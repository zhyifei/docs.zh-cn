---
title: 作为一类值的函数 (F#)
description: '了解如何提升到 F # 编程语言中的第一类状态的函数。'
ms.date: 05/16/2016
ms.openlocfilehash: cccff5fcf9de150da26422f80cae032ddf21014c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566660"
---
# <a name="functions-as-first-class-values"></a><span data-ttu-id="2b0ee-103">作为一类值的函数</span><span class="sxs-lookup"><span data-stu-id="2b0ee-103">Functions as First-Class Values</span></span>

<span data-ttu-id="2b0ee-104">函数编程语言的定义特征是提升到第一类状态的函数。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-104">A defining characteristic of functional programming languages is the elevation of functions to first-class status.</span></span> <span data-ttu-id="2b0ee-105">你应能够执行的函数具有的任何你可以使用其他内置类型的值执行的操作和能够完成此操作可比较程度的工作量。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-105">You should be able to do with a function whatever you can do with values of the other built-in types, and be able to do so with a comparable degree of effort.</span></span>

<span data-ttu-id="2b0ee-106">典型的度量值的第一类的状态如下所示：</span><span class="sxs-lookup"><span data-stu-id="2b0ee-106">Typical measures of first-class status include the following:</span></span>

- <span data-ttu-id="2b0ee-107">你可以将函数绑定到标识符？</span><span class="sxs-lookup"><span data-stu-id="2b0ee-107">Can you bind functions to identifiers?</span></span> <span data-ttu-id="2b0ee-108">也就是说，你能大概给它们名称？</span><span class="sxs-lookup"><span data-stu-id="2b0ee-108">That is, can you give them names?</span></span>

- <span data-ttu-id="2b0ee-109">可以存储函数中数据结构，如在列表中？</span><span class="sxs-lookup"><span data-stu-id="2b0ee-109">Can you store functions in data structures, such as in a list?</span></span>

- <span data-ttu-id="2b0ee-110">你可以向函数传递作为函数调用中的参数？</span><span class="sxs-lookup"><span data-stu-id="2b0ee-110">Can you pass a function as an argument in a function call?</span></span>

- <span data-ttu-id="2b0ee-111">你可以从一个函数调用返回一个函数？</span><span class="sxs-lookup"><span data-stu-id="2b0ee-111">Can you return a function from a function call?</span></span>

<span data-ttu-id="2b0ee-112">最后两个度量值定义所谓的*更高序位操作*或*高阶函数*。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-112">The last two measures define what are known as *higher-order operations* or *higher-order functions*.</span></span> <span data-ttu-id="2b0ee-113">高阶函数接受作为自变量的函数，并返回函数作为函数调用的值。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-113">Higher-order functions accept functions as arguments and return functions as the value of function calls.</span></span> <span data-ttu-id="2b0ee-114">这些操作支持这种作为映射函数和函数的组合的函数编程。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-114">These operations support such mainstays of functional programming as mapping functions and composition of functions.</span></span>


## <a name="give-the-value-a-name"></a><span data-ttu-id="2b0ee-115">为指定名称的值</span><span class="sxs-lookup"><span data-stu-id="2b0ee-115">Give the Value a Name</span></span>

<span data-ttu-id="2b0ee-116">如果一个函数是一类值，你必须能够将其命名，就像可以命名整数、 字符串和其他内置类型。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-116">If a function is a first-class value, you must be able to name it, just as you can name integers, strings, and other built-in types.</span></span> <span data-ttu-id="2b0ee-117">这是在绑定到的值的标识符函数编程语言中称为。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-117">This is referred to in functional programming literature as binding an identifier to a value.</span></span> <span data-ttu-id="2b0ee-118">F # 使用[`let`绑定](../language-reference/functions/let-bindings.md)要绑定到值的名称： `let <identifier> = <value>`。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-118">F# uses [`let` bindings](../language-reference/functions/let-bindings.md) to bind names to values: `let <identifier> = <value>`.</span></span> <span data-ttu-id="2b0ee-119">下面的代码演示了两个示例。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-119">The following code shows two examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet20.fs)]

<span data-ttu-id="2b0ee-120">可以将名称轻松地为函数。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-120">You can name a function just as easily.</span></span> <span data-ttu-id="2b0ee-121">下面的示例定义一个名为函数`squareIt`由绑定标识符`squareIt`到[lambda 表达式](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n`。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-121">The following example defines a function named `squareIt` by binding the identifier `squareIt` to the [lambda expression](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n`.</span></span> <span data-ttu-id="2b0ee-122">函数`squareIt`具有一个参数、 `n`，并返回该参数的平方。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-122">Function `squareIt` has one parameter, `n`, and it returns the square of that parameter.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet21.fs)]

<span data-ttu-id="2b0ee-123">F # 提供了以下更简洁的语法以实现使用较少键入相同的结果。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-123">F# provides the following more concise syntax to achieve the same result with less typing.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet22.fs)]

<span data-ttu-id="2b0ee-124">主要下面的示例中使用的第一个样式， `let <function-name> = <lambda-expression>`，以强调函数的声明和其他类型的值的声明之间的相似之处。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-124">The examples that follow mostly use the first style, `let <function-name> = <lambda-expression>`, to emphasize the similarities between the declaration of functions and the declaration of other types of values.</span></span> <span data-ttu-id="2b0ee-125">但是，还可以使用简洁的语法编写所有命名的函数。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-125">However, all the named functions can also be written with the concise syntax.</span></span> <span data-ttu-id="2b0ee-126">用这两种方式编写的一些示例。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-126">Some of the examples are written in both ways.</span></span>


## <a name="store-the-value-in-a-data-structure"></a><span data-ttu-id="2b0ee-127">应用商店中的数据结构的值</span><span class="sxs-lookup"><span data-stu-id="2b0ee-127">Store the Value in a Data Structure</span></span>

<span data-ttu-id="2b0ee-128">第一类值可以存储在数据结构。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-128">A first-class value can be stored in a data structure.</span></span> <span data-ttu-id="2b0ee-129">下面的代码演示将值存储在列表和元组中的示例。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-129">The following code shows examples that store values in lists and in tuples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet23.fs)]

<span data-ttu-id="2b0ee-130">若要验证存储元组中的函数名称中的事实未计算结果为一个函数，下面的示例使用`fst`和`snd`运算符以从元组中提取的第一个和第二个元素`funAndArgTuple`。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-130">To verify that a function name stored in a tuple does in fact evaluate to a function, the following example uses the `fst` and `snd` operators to extract the first and second elements from tuple `funAndArgTuple`.</span></span> <span data-ttu-id="2b0ee-131">元组中的第一个元素是`squareIt`和第二个元素是`num`。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-131">The first element in the tuple is `squareIt` and the second element is `num`.</span></span> <span data-ttu-id="2b0ee-132">标识符`num`绑定中前一示例中为整数 10 的有效参数`squareIt`函数。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-132">Identifier `num` is bound in a previous example to integer 10, a valid argument for the `squareIt` function.</span></span> <span data-ttu-id="2b0ee-133">第二个表达式适用于此元组中的第二个元素的元组中的第一个元素： `squareIt num`。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-133">The second expression applies the first element in the tuple to the second element in the tuple: `squareIt num`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet24.fs)]

<span data-ttu-id="2b0ee-134">同样，就像标识符`num`和整数 10 可以互换使用，因此可以标识符`squareIt`和 lambda 表达式`fun n -> n * n`。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-134">Similarly, just as identifier `num` and integer 10 can be used interchangeably, so can identifier `squareIt` and lambda expression `fun n -> n * n`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet25.fs)]
    
## <a name="pass-the-value-as-an-argument"></a><span data-ttu-id="2b0ee-135">将值作为参数传递</span><span class="sxs-lookup"><span data-stu-id="2b0ee-135">Pass the Value as an Argument</span></span>

<span data-ttu-id="2b0ee-136">如果值有一种语言中的第一类的状态，你可以它作为参数传递给函数。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-136">If a value has first-class status in a language, you can pass it as an argument to a function.</span></span> <span data-ttu-id="2b0ee-137">例如，很常见整型和字符串作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-137">For example, it is common to pass integers and strings as arguments.</span></span> <span data-ttu-id="2b0ee-138">下面的代码演示整数和 F # 中作为参数传递的字符串。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-138">The following code shows integers and strings passed as arguments in F#.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet26.fs)]

<span data-ttu-id="2b0ee-139">如果函数的第一类的状态，你必须能够将它们作为参数传递的方式相同。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-139">If functions have first-class status, you must be able to pass them as arguments in the same way.</span></span> <span data-ttu-id="2b0ee-140">请记住，这是高阶函数的第一个特性。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-140">Remember that this is the first characteristic of higher-order functions.</span></span>

<span data-ttu-id="2b0ee-141">在下面的示例中，函数`applyIt`具有两个参数，`op`和`arg`。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-141">In the following example, function `applyIt` has two parameters, `op` and `arg`.</span></span> <span data-ttu-id="2b0ee-142">如果你发送的函数中，具有一个参数的`op`和到函数的相应自变量`arg`，该函数返回的结果应用`op`到`arg`。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-142">If you send in a function that has one parameter for `op` and an appropriate argument for the function to `arg`, the function returns the result of applying `op` to `arg`.</span></span> <span data-ttu-id="2b0ee-143">在以下示例中，该函数参数，整数自变量会发送相同的方式，通过使用其名称。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-143">In the following example, both the function argument and the integer argument are sent in the same way, by using their names.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet27.fs)]

<span data-ttu-id="2b0ee-144">能够将一个函数作为自变量发送到另一个函数是常见抽象函数编程语言，如映射或筛选器操作的基础。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-144">The ability to send a function as an argument to another function underlies common abstractions in functional programming languages, such as map or filter operations.</span></span> <span data-ttu-id="2b0ee-145">映射操作，例如，是捕获共享单步执行列表、 于每个元素执行操作，然后返回结果的列表的函数的计算，高阶函数。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-145">A map operation, for example, is a higher-order function that captures the computation shared by functions that step through a list, do something to each element, and then return a list of the results.</span></span> <span data-ttu-id="2b0ee-146">你可能想要递增的整数，列表中每个元素方形每个元素，或以将转换为大写的字符串列表中每个元素。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-146">You might want to increment each element in a list of integers, or to square each element, or to change each element in a list of strings to uppercase.</span></span> <span data-ttu-id="2b0ee-147">计算的易出错的一部分是通过列表该步骤的递归过程和生成要返回的结果的列表。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-147">The error-prone part of the computation is the recursive process that steps through the list and builds a list of the results to return.</span></span> <span data-ttu-id="2b0ee-148">映射函数中捕获该部分。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-148">That part is captured in the mapping function.</span></span> <span data-ttu-id="2b0ee-149">你只需编写特定的应用程序是你想要单独应用于每个列表元素的函数 （添加、 相乘、 更改大小写）。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-149">All you have to write for a particular application is the function that you want to apply to each list element individually (adding, squaring, changing case).</span></span> <span data-ttu-id="2b0ee-150">函数作为自变量映射函数中，只需将作为发送给`squareIt`发送到`applyIt`在前面的示例。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-150">That function is sent as an argument to the mapping function, just as `squareIt` is sent to `applyIt` in the previous example.</span></span>

<span data-ttu-id="2b0ee-151">F # 提供的大多数集合类型，包括映射方法[列出](../language-reference/lists.md)，[数组](../language-reference/arrays.md)，和[序列](../language-reference/sequences.md)。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-151">F# provides map methods for most collection types, including [lists](../language-reference/lists.md), [arrays](../language-reference/arrays.md), and [sequences](../language-reference/sequences.md).</span></span> <span data-ttu-id="2b0ee-152">下面的示例使用列表。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-152">The following examples use lists.</span></span> <span data-ttu-id="2b0ee-153">语法是`List.map <the function> <the list>`。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-153">The syntax is `List.map <the function> <the list>`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet28.fs)]

<span data-ttu-id="2b0ee-154">有关详细信息，请参阅[列出](../language-reference/lists.md)。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-154">For more information, see [Lists](../language-reference/lists.md).</span></span>

## <a name="return-the-value-from-a-function-call"></a><span data-ttu-id="2b0ee-155">从函数调用返回值</span><span class="sxs-lookup"><span data-stu-id="2b0ee-155">Return the Value from a Function Call</span></span>

<span data-ttu-id="2b0ee-156">最后，如果函数具有一种语言中的第一类的状态，你必须能够将其返回作为值的函数调用，就像返回其他类型，如整数和字符串。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-156">Finally, if a function has first-class status in a language, you must be able to return it as the value of a function call, just as you return other types, such as integers and strings.</span></span>

<span data-ttu-id="2b0ee-157">下面的函数调用返回整数，并将其显示。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-157">The following function calls return integers and display them.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet29.fs)]

<span data-ttu-id="2b0ee-158">以下函数调用返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-158">The following function call returns a string.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet30.fs)]

<span data-ttu-id="2b0ee-159">内联声明，在以下函数调用返回一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-159">The following function call, declared inline, returns a Boolean value.</span></span> <span data-ttu-id="2b0ee-160">显示的值是`True`。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-160">The value displayed is `True`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet31.fs)]

<span data-ttu-id="2b0ee-161">返回一个函数作为函数调用的值的功能是高阶函数的第二个特征。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-161">The ability to return a function as the value of a function call is the second characteristic of higher-order functions.</span></span> <span data-ttu-id="2b0ee-162">在下面的示例中，`checkFor`定义为采用一个自变量的函数`item`，并返回一个新函数作为其值。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-162">In the following example, `checkFor` is defined to be a function that takes one argument, `item`, and returns a new function as its value.</span></span> <span data-ttu-id="2b0ee-163">返回函数作为其自变量列表`lst`，并搜索`item`中`lst`。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-163">The returned function takes a list as its argument, `lst`, and searches for `item` in `lst`.</span></span> <span data-ttu-id="2b0ee-164">如果`item`不存在，该函数将返回`true`。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-164">If `item` is present, the function returns `true`.</span></span> <span data-ttu-id="2b0ee-165">如果`item`不存在，该函数将返回`false`。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-165">If `item` is not present, the function returns `false`.</span></span> <span data-ttu-id="2b0ee-166">下面的代码如下所示上一节中，使用提供的列表函数[List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8)，以在列表中搜索。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-166">As in the previous section, the following code uses a provided list function, [List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8), to search the list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet32.fs)]

<span data-ttu-id="2b0ee-167">下面的代码使用`checkFor`创建采用一个自变量、 列表和 7 搜索列表中的新函数。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-167">The following code uses `checkFor` to create a new function that takes one argument, a list, and searches for 7 in the list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet33.fs)]

<span data-ttu-id="2b0ee-168">下面的示例使用 F # 中的函数的第一类状态来声明函数， `compose`，返回两个函数自变量的组合。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-168">The following example uses the first-class status of functions in F# to declare a function, `compose`, that returns a composition of two function arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet34.fs)]
    
>[!NOTE]
<span data-ttu-id="2b0ee-169">有关甚至更短的版本，请参阅以下部分中，"扩充函数。"</span><span class="sxs-lookup"><span data-stu-id="2b0ee-169">For an even shorter version, see the following section, "Curried Functions."</span></span>


<span data-ttu-id="2b0ee-170">下面的代码将两个函数作为自变量发送`compose`，这两个的这需要相同类型的单个参数。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-170">The following code sends two functions as arguments to `compose`, both of which take a single argument of the same type.</span></span> <span data-ttu-id="2b0ee-171">返回值是一个新函数，则两个函数参数的组合。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-171">The return value is a new function that is a composition of the two function arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet35.fs)]
    
>[!NOTE] 
<span data-ttu-id="2b0ee-172">F # 提供了两个运算符，`<<`和`>>`，它们构成函数。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-172">F# provides two operators, `<<` and `>>`, that compose functions.</span></span> <span data-ttu-id="2b0ee-173">例如，`let squareAndDouble2 = doubleIt << squareIt`等效于`let squareAndDouble = compose doubleIt squareIt`在前面的示例。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-173">For example, `let squareAndDouble2 = doubleIt << squareIt` is equivalent to `let squareAndDouble = compose doubleIt squareIt` in the previous example.</span></span>

<span data-ttu-id="2b0ee-174">作为函数调用值返回函数的下面的示例创建一个简单的猜测游戏。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-174">The following example of returning a function as the value of a function call creates a simple guessing game.</span></span> <span data-ttu-id="2b0ee-175">若要创建一个游戏，调用`makeGame`值与你希望让人猜出为传入的`target`。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-175">To create a game, call `makeGame` with the value that you want someone to guess sent in for `target`.</span></span> <span data-ttu-id="2b0ee-176">函数的返回值`makeGame`是采用一个自变量 （猜测） 和报告猜测是正确的函数。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-176">The return value from function `makeGame` is a function that takes one argument (the guess) and reports whether the guess is correct.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet36.fs)]

<span data-ttu-id="2b0ee-177">下面的代码调用`makeGame`，将值发送`7`为`target`。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-177">The following code calls `makeGame`, sending the value `7` for `target`.</span></span> <span data-ttu-id="2b0ee-178">标识符`playGame`绑定到返回的 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-178">Identifier `playGame` is bound to the returned lambda expression.</span></span> <span data-ttu-id="2b0ee-179">因此，`playGame`是采用作为它的一个参数值为一个函数`guess`。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-179">Therefore, `playGame` is a function that takes as its one argument a value for `guess`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet37.fs)]
    
## <a name="curried-functions"></a><span data-ttu-id="2b0ee-180">扩充的函数</span><span class="sxs-lookup"><span data-stu-id="2b0ee-180">Curried Functions</span></span>

<span data-ttu-id="2b0ee-181">可以通过利用的隐式更确切地编写的许多上一节中示例*扩充*F # 函数声明中。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-181">Many of the examples in the previous section can be written more concisely by taking advantage of the implicit *currying* in F# function declarations.</span></span> <span data-ttu-id="2b0ee-182">扩充是一个转换具有多个参数为一系列的嵌入式函数，其中每个具有单个参数的函数的过程。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-182">Currying is a process that transforms a function that has more than one parameter into a series of embedded functions, each of which has a single parameter.</span></span> <span data-ttu-id="2b0ee-183">在 F # 中，都会被扩充具有多个参数的函数。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-183">In F#, functions that have more than one parameter are inherently curried.</span></span> <span data-ttu-id="2b0ee-184">例如，`compose`从上一节可以编写以下的简洁样式，带有三个参数中所示。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-184">For example, `compose` from the previous section can be written as shown in the following concise style, with three parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet38.fs)]

<span data-ttu-id="2b0ee-185">但是，结果是返回反过来返回的一个参数，另一个函数的一个参数的函数中所示的一个参数的函数`compose4curried`。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-185">However, the result is a function of one parameter that returns a function of one parameter that in turn returns another function of one parameter, as shown in `compose4curried`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet39.fs)]

<span data-ttu-id="2b0ee-186">你可以访问此函数在几种方法中。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-186">You can access this function in several ways.</span></span> <span data-ttu-id="2b0ee-187">每个以下的示例返回并显示 18。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-187">Each of the following examples returns and displays 18.</span></span> <span data-ttu-id="2b0ee-188">你可以替换`compose4`与`compose4curried`示例中。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-188">You can replace `compose4` with `compose4curried` in any of the examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet40.fs)]

<span data-ttu-id="2b0ee-189">若要验证，该函数仍适用像以前一样，重试原始测试用例。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-189">To verify that the function still works as it did before, try the original test cases again.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet41.fs)]
    
>[!NOTE] 
<span data-ttu-id="2b0ee-190">你可以限制扩充括在元组中的参数。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-190">You can restrict currying by enclosing parameters in tuples.</span></span> <span data-ttu-id="2b0ee-191">有关详细信息，请参阅"参数模式"[参数和自变量](../language-reference/parameters-and-arguments.md)。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-191">For more information, see "Parameter Patterns" in [Parameters and Arguments](../language-reference/parameters-and-arguments.md).</span></span>

<span data-ttu-id="2b0ee-192">下面的示例使用隐式扩充要写入的简短版本`makeGame`。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-192">The following example uses implicit currying to write a shorter version of `makeGame`.</span></span> <span data-ttu-id="2b0ee-193">方法的详细信息`makeGame`构造并返回`game`函数不太明确按以下格式，但你可以通过使用原始的结果是相同的测试用例来验证。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-193">The details of how `makeGame` constructs and returns the `game` function are less explicit in this format, but you can verify by using the original test cases that the result is the same.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet42.fs)]

<span data-ttu-id="2b0ee-194">有关扩充的详细信息，请参见"部分应用程序的参数"中[函数](../language-reference/functions/index.md)。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-194">For more information about currying, see "Partial Application of Arguments" in [Functions](../language-reference/functions/index.md).</span></span>


## <a name="identifier-and-function-definition-are-interchangeable"></a><span data-ttu-id="2b0ee-195">标识符和函数定义是可互换</span><span class="sxs-lookup"><span data-stu-id="2b0ee-195">Identifier and Function Definition Are Interchangeable</span></span>
<span data-ttu-id="2b0ee-196">变量名称`num`在前面示例的计算结果为 10 的整数，它也就不足为奇，因为`num`是有效，10 也是有效的。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-196">The variable name `num` in the previous examples evaluates to the integer 10, and it is no surprise that where `num` is valid, 10 is also valid.</span></span> <span data-ttu-id="2b0ee-197">这同样适用函数标识符及其值的： 可以位置可以使用函数的名称，使用绑定到 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-197">The same is true of function identifiers and their values: anywhere the name of the function can be used, the lambda expression to which it is bound can be used.</span></span>

<span data-ttu-id="2b0ee-198">下面的示例定义`Boolean`函数调用`isNegative`，然后互换使用的函数名称和函数的定义。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-198">The following example defines a `Boolean` function called `isNegative`, and then uses the name of the function and the definition of the function interchangeably.</span></span> <span data-ttu-id="2b0ee-199">接下来三个示例都返回并显示`False`。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-199">The next three examples all return and display `False`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet43.fs)]

<span data-ttu-id="2b0ee-200">若要进一步它一个步骤，将替换值的`applyIt`绑定到`applyIt`。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-200">To take it one step further, substitute the value that `applyIt` is bound to for `applyIt`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet44.fs)]

## <a name="functions-are-first-class-values-in-f"></a><span data-ttu-id="2b0ee-201">函数是在 F # 中的第一类值</span><span class="sxs-lookup"><span data-stu-id="2b0ee-201">Functions Are First-Class Values in F#</span></span> #

<span data-ttu-id="2b0ee-202">前几节中的示例演示 F # 中的函数满足正在 F # 中的一类值的条件：</span><span class="sxs-lookup"><span data-stu-id="2b0ee-202">The examples in the previous sections demonstrate that functions in F# satisfy the criteria for being first-class values in F#:</span></span>

- <span data-ttu-id="2b0ee-203">你可以绑定到函数定义的标识符。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-203">You can bind an identifier to a function definition.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet21.fs)]

- <span data-ttu-id="2b0ee-204">可以将函数存储的数据结构。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-204">You can store a function in a data structure.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet45.fs)]

- <span data-ttu-id="2b0ee-205">可以将函数作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-205">You can pass a function as an argument.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet46.fs)]

- <span data-ttu-id="2b0ee-206">你可以返回函数作为函数调用的值。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-206">You can return a function as the value of a function call.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet32.fs)]

<span data-ttu-id="2b0ee-207">有关 F # 的详细信息，请参阅[F # 语言参考](../language-reference/index.md)。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-207">For more information about F#, see the [F# Language Reference](../language-reference/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="2b0ee-208">示例</span><span class="sxs-lookup"><span data-stu-id="2b0ee-208">Example</span></span>

### <a name="description"></a><span data-ttu-id="2b0ee-209">描述</span><span class="sxs-lookup"><span data-stu-id="2b0ee-209">Description</span></span>

<span data-ttu-id="2b0ee-210">下面的代码包含本主题中的所有示例。</span><span class="sxs-lookup"><span data-stu-id="2b0ee-210">The following code contains all the examples in this topic.</span></span>

### <a name="code"></a><span data-ttu-id="2b0ee-211">代码</span><span class="sxs-lookup"><span data-stu-id="2b0ee-211">Code</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet47.fs)]
    
## <a name="see-also"></a><span data-ttu-id="2b0ee-212">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b0ee-212">See Also</span></span>

[<span data-ttu-id="2b0ee-213">列表</span><span class="sxs-lookup"><span data-stu-id="2b0ee-213">Lists</span></span>](../language-reference/lists.md)

[<span data-ttu-id="2b0ee-214">元组</span><span class="sxs-lookup"><span data-stu-id="2b0ee-214">Tuples</span></span>](../language-reference/tuples.md)

[<span data-ttu-id="2b0ee-215">函数</span><span class="sxs-lookup"><span data-stu-id="2b0ee-215">Functions</span></span>](../language-reference/functions/index.md)

[<span data-ttu-id="2b0ee-216">`let` 绑定</span><span class="sxs-lookup"><span data-stu-id="2b0ee-216">`let` Bindings</span></span>](../language-reference/functions/let-bindings.md)

[<span data-ttu-id="2b0ee-217">Lambda 表达式：`fun`关键字</span><span class="sxs-lookup"><span data-stu-id="2b0ee-217">Lambda Expressions: The `fun` Keyword</span></span>](../language-reference/functions/lambda-expressions-the-fun-keyword.md)
