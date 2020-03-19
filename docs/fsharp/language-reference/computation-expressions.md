---
title: 计算表达式
description: 了解如何创建用于在 F# 中编写可使用控制流构造和绑定进行排序和组合的计算的便捷语法。
ms.date: 11/04/2019
ms.openlocfilehash: 55406cc12d9e6e890fe69d712f79486d23b84452
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401081"
---
# <a name="computation-expressions"></a><span data-ttu-id="29151-103">计算表达式</span><span class="sxs-lookup"><span data-stu-id="29151-103">Computation Expressions</span></span>

<span data-ttu-id="29151-104">F# 中的计算表达式为编写可以使用控制流构造和绑定进行排序和组合的计算提供了方便的语法。</span><span class="sxs-lookup"><span data-stu-id="29151-104">Computation expressions in F# provide a convenient syntax for writing computations that can be sequenced and combined using control flow constructs and bindings.</span></span> <span data-ttu-id="29151-105">根据计算表达式的类型，它们可以被认为是一种表达单体、单体、莫纳变压器和施用器的方法。</span><span class="sxs-lookup"><span data-stu-id="29151-105">Depending on the kind of computation expression, they can be thought of as a way to express monads, monoids, monad transformers, and applicative functors.</span></span> <span data-ttu-id="29151-106">但是，与其他语言（如 Haskell 中的*do-符号*）不同，它们不绑定到单个抽象，并且不依赖宏或其他形式的元编程来完成方便且上下文相关的语法。</span><span class="sxs-lookup"><span data-stu-id="29151-106">However, unlike other languages (such as *do-notation* in Haskell), they are not tied to a single abstraction, and do not rely on macros or other forms of metaprogramming to accomplish a convenient and context-sensitive syntax.</span></span>

## <a name="overview"></a><span data-ttu-id="29151-107">概述</span><span class="sxs-lookup"><span data-stu-id="29151-107">Overview</span></span>

<span data-ttu-id="29151-108">计算可以有多种形式。</span><span class="sxs-lookup"><span data-stu-id="29151-108">Computations can take many forms.</span></span> <span data-ttu-id="29151-109">最常见的计算形式是单线程执行，易于理解和修改。</span><span class="sxs-lookup"><span data-stu-id="29151-109">The most common form of computation is single-threaded execution, which is easy to understand and modify.</span></span> <span data-ttu-id="29151-110">但是，并非所有形式的计算都像单线程执行那样简单明了。</span><span class="sxs-lookup"><span data-stu-id="29151-110">However, not all forms of computation are as straightforward as single-threaded execution.</span></span> <span data-ttu-id="29151-111">示例包括：</span><span class="sxs-lookup"><span data-stu-id="29151-111">Some examples include:</span></span>

- <span data-ttu-id="29151-112">非确定性计算</span><span class="sxs-lookup"><span data-stu-id="29151-112">Non-deterministic computations</span></span>
- <span data-ttu-id="29151-113">异步计算</span><span class="sxs-lookup"><span data-stu-id="29151-113">Asynchronous computations</span></span>
- <span data-ttu-id="29151-114">有效的计算</span><span class="sxs-lookup"><span data-stu-id="29151-114">Effectful computations</span></span>
- <span data-ttu-id="29151-115">生成计算</span><span class="sxs-lookup"><span data-stu-id="29151-115">Generative computations</span></span>

<span data-ttu-id="29151-116">更一般情况下，必须在应用程序的某些部分执行*上下文相关的*计算。</span><span class="sxs-lookup"><span data-stu-id="29151-116">More generally, there are *context-sensitive* computations that you must perform in certain parts of an application.</span></span> <span data-ttu-id="29151-117">编写上下文敏感代码可能具有挑战性，因为很容易在给定上下文之外"泄漏"计算，而无需抽象来防止您这样做。</span><span class="sxs-lookup"><span data-stu-id="29151-117">Writing context-sensitive code can be challenging, as it is easy to "leak" computations outside of a given context without abstractions to prevent you from doing so.</span></span> <span data-ttu-id="29151-118">这些抽象通常具有挑战性，可以自己编写，这就是为什么 F# 具有一种通用的方式来执行此操作，称为**计算表达式**。</span><span class="sxs-lookup"><span data-stu-id="29151-118">These abstractions are often challenging to write by yourself, which is why F# has a generalized way to do so called **computation expressions**.</span></span>

<span data-ttu-id="29151-119">计算表达式为编码上下文敏感的计算提供了统一的语法和抽象模型。</span><span class="sxs-lookup"><span data-stu-id="29151-119">Computation expressions offer a uniform syntax and abstraction model for encoding context-sensitive computations.</span></span>

<span data-ttu-id="29151-120">每个计算表达式都由*生成器*类型支持。</span><span class="sxs-lookup"><span data-stu-id="29151-120">Every computation expression is backed by a *builder* type.</span></span> <span data-ttu-id="29151-121">生成器类型定义可用于计算表达式的操作。</span><span class="sxs-lookup"><span data-stu-id="29151-121">The builder type defines the operations that are available for the computation expression.</span></span> <span data-ttu-id="29151-122">请参阅[创建新类型的计算表达式](computation-expressions.md#creating-a-new-type-of-computation-expression)，其中演示如何创建自定义计算表达式。</span><span class="sxs-lookup"><span data-stu-id="29151-122">See [Creating a New Type of Computation Expression](computation-expressions.md#creating-a-new-type-of-computation-expression), which shows how to create a custom computation expression.</span></span>

### <a name="syntax-overview"></a><span data-ttu-id="29151-123">语法概述</span><span class="sxs-lookup"><span data-stu-id="29151-123">Syntax overview</span></span>

<span data-ttu-id="29151-124">所有计算表达式都具有以下形式：</span><span class="sxs-lookup"><span data-stu-id="29151-124">All computation expressions have the following form:</span></span>

```fsharp
builder-expr { cexper }
```

<span data-ttu-id="29151-125">其中`builder-expr`是定义计算表达式的生成器类型的名称，是`cexper`计算表达式的表达式正文。</span><span class="sxs-lookup"><span data-stu-id="29151-125">where `builder-expr` is the name of a builder type that defines the computation expression, and `cexper` is the expression body of the computation expression.</span></span> <span data-ttu-id="29151-126">例如，`async`计算表达式代码可以如下所示：</span><span class="sxs-lookup"><span data-stu-id="29151-126">For example, `async` computation expression code can look like this:</span></span>

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

<span data-ttu-id="29151-127">计算表达式中提供了一个特殊的附加语法，如上例所示。</span><span class="sxs-lookup"><span data-stu-id="29151-127">There is a special, additional syntax available within a computation expression, as shown in the previous example.</span></span> <span data-ttu-id="29151-128">计算表达式可以实现以下表达式形式：</span><span class="sxs-lookup"><span data-stu-id="29151-128">The following expression forms are possible with computation expressions:</span></span>

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

<span data-ttu-id="29151-129">这些关键字和其他标准 F# 关键字仅在支持生成器类型中定义时才在计算表达式中可用。</span><span class="sxs-lookup"><span data-stu-id="29151-129">Each of these keywords, and other standard F# keywords are only available in a computation expression if they have been defined in the backing builder type.</span></span> <span data-ttu-id="29151-130">唯一的例外是`match!`，它本身就是使用后跟模式匹配结果的`let!`语法糖。</span><span class="sxs-lookup"><span data-stu-id="29151-130">The only exception to this is `match!`, which is itself syntactic sugar for the use of `let!` followed by a pattern match on the result.</span></span>

<span data-ttu-id="29151-131">生成器类型是定义控制计算表达式片段组合方式的特殊方法的对象;也就是说，它的方法控制计算表达式的表现。</span><span class="sxs-lookup"><span data-stu-id="29151-131">The builder type is an object that defines special methods that govern the way the fragments of the computation expression are combined; that is, its methods control how the computation expression behaves.</span></span> <span data-ttu-id="29151-132">描述生成器类的另一种方法是说它使您能够自定义许多 F# 构造（如循环和绑定）的操作。</span><span class="sxs-lookup"><span data-stu-id="29151-132">Another way to describe a builder class is to say that it enables you to customize the operation of many F# constructs, such as loops and bindings.</span></span>

### `let!`

<span data-ttu-id="29151-133">关键字`let!`将调用到另一个计算表达式的结果绑定到名称：</span><span class="sxs-lookup"><span data-stu-id="29151-133">The `let!` keyword binds the result of a call to another computation expression to a name:</span></span>

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

<span data-ttu-id="29151-134">如果使用 将调用绑定到 计算表达式`let`，则不会获取计算表达式的结果。</span><span class="sxs-lookup"><span data-stu-id="29151-134">If you bind the call to a computation expression with `let`, you will not get the result of the computation expression.</span></span> <span data-ttu-id="29151-135">相反，您将绑定到该计算表达式的*未实现*调用的值。</span><span class="sxs-lookup"><span data-stu-id="29151-135">Instead, you will have bound the value of the *unrealized* call to that computation expression.</span></span> <span data-ttu-id="29151-136">用于`let!`绑定到结果。</span><span class="sxs-lookup"><span data-stu-id="29151-136">Use `let!` to bind to the result.</span></span>

<span data-ttu-id="29151-137">`let!`由生成器类型上`Bind(x, f)`的成员定义。</span><span class="sxs-lookup"><span data-stu-id="29151-137">`let!` is defined by the `Bind(x, f)` member on the builder type.</span></span>

### `do!`

<span data-ttu-id="29151-138">关键字`do!`用于调用返回`unit`类似类型（由生成器上`Zero`的成员定义）的计算表达式：</span><span class="sxs-lookup"><span data-stu-id="29151-138">The `do!` keyword is for calling a computation expression that returns a `unit`-like type (defined by the `Zero` member on the builder):</span></span>

```fsharp
let doThingsAsync data url =
    async {
        do! submitData data url
        ...
    }
```

<span data-ttu-id="29151-139">对于[异步工作流](asynchronous-workflows.md)，此类型为`Async<unit>`。</span><span class="sxs-lookup"><span data-stu-id="29151-139">For the [async workflow](asynchronous-workflows.md), this type is `Async<unit>`.</span></span> <span data-ttu-id="29151-140">对于其他计算表达式，类型可能是`CExpType<unit>`。</span><span class="sxs-lookup"><span data-stu-id="29151-140">For other computation expressions, the type is likely to be `CExpType<unit>`.</span></span>

<span data-ttu-id="29151-141">`do!`由生成器类型上`Bind(x, f)`的成员定义，其中`f`生成 。 `unit`</span><span class="sxs-lookup"><span data-stu-id="29151-141">`do!` is defined by the `Bind(x, f)` member on the builder type, where `f` produces a `unit`.</span></span>

### `yield`

<span data-ttu-id="29151-142">关键字`yield`用于从计算表达式返回值，以便它可以用作<xref:System.Collections.Generic.IEnumerable%601>：</span><span class="sxs-lookup"><span data-stu-id="29151-142">The `yield` keyword is for returning a value from the computation expression so that it can be consumed as an <xref:System.Collections.Generic.IEnumerable%601>:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

<span data-ttu-id="29151-143">在大多数情况下，调用方可以省略它。</span><span class="sxs-lookup"><span data-stu-id="29151-143">In most cases, it can be omitted by callers.</span></span> <span data-ttu-id="29151-144">省略的最常见方法是`yield`使用`->`运算符：</span><span class="sxs-lookup"><span data-stu-id="29151-144">The most common way to omit `yield` is with the `->` operator:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..10 -> i * i
    }

for sq in squares do
    printfn "%d" sq
```

<span data-ttu-id="29151-145">对于可能产生许多不同的值的更复杂的表达式，也许有条件地省略关键字可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="29151-145">For more complex expressions that might yield many different values, and perhaps conditionally, simply omitting the keyword can do:</span></span>

```fsharp
let weekdays includeWeekend =
    seq {
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then
            "Saturday"
            "Sunday"
    }
```

<span data-ttu-id="29151-146">与[C# 中的屈服关键字](../../csharp/language-reference/keywords/yield.md)一样，计算表达式中的每个元素在迭代时都会返回。</span><span class="sxs-lookup"><span data-stu-id="29151-146">As with the [yield keyword in C#](../../csharp/language-reference/keywords/yield.md), each element in the computation expression is yielded back as it is iterated.</span></span>

<span data-ttu-id="29151-147">`yield`由生成器类型上`Yield(x)`的成员定义，其中`x`要回产的项目。</span><span class="sxs-lookup"><span data-stu-id="29151-147">`yield` is defined by the `Yield(x)` member on the builder type, where `x` is the item to yield back.</span></span>

### `yield!`

<span data-ttu-id="29151-148">关键字`yield!`用于拼平计算表达式中的值集合：</span><span class="sxs-lookup"><span data-stu-id="29151-148">The `yield!` keyword is for flattening a collection of values from a computation expression:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..3 -> i * i
    }

let cubes =
    seq {
        for i in 1..3 -> i * i * i
    }

let squaresAndCubes =
    seq {
        yield! squares
        yield! cubes
    }

printfn "%A" squaresAndCubes // Prints - 1; 4; 9; 1; 8; 27
```

<span data-ttu-id="29151-149">计算时，调用`yield!`的计算表达式将使其项逐个返回，从而使结果平展。</span><span class="sxs-lookup"><span data-stu-id="29151-149">When evaluated, the computation expression called by `yield!` will have its items yielded back one-by-one, flattening the result.</span></span>

<span data-ttu-id="29151-150">`yield!`由生成器类型上`YieldFrom(x)`的成员定义，其中`x`是值的集合。</span><span class="sxs-lookup"><span data-stu-id="29151-150">`yield!` is defined by the `YieldFrom(x)` member on the builder type, where `x` is a collection of values.</span></span>

<span data-ttu-id="29151-151">与`yield``yield!`必须显式指定不同。</span><span class="sxs-lookup"><span data-stu-id="29151-151">Unlike `yield`, `yield!` must be explicitly specified.</span></span> <span data-ttu-id="29151-152">它的行为在计算表达式中不隐式。</span><span class="sxs-lookup"><span data-stu-id="29151-152">Its behavior isn't implicit in computation expressions.</span></span>

### `return`

<span data-ttu-id="29151-153">关键字`return`在与计算表达式对应的类型中换行值。</span><span class="sxs-lookup"><span data-stu-id="29151-153">The `return` keyword wraps a value in the type corresponding to the computation expression.</span></span> <span data-ttu-id="29151-154">除了使用`yield`的计算表达式外，它还用于"完成"计算表达式：</span><span class="sxs-lookup"><span data-stu-id="29151-154">Aside from computation expressions using `yield`, it is used to "complete" a computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="29151-155">`return`由生成器类型上`Return(x)`的成员定义，要包装的项`x`所在的位置。</span><span class="sxs-lookup"><span data-stu-id="29151-155">`return` is defined by the `Return(x)` member on the builder type, where `x` is the item to wrap.</span></span>

### `return!`

<span data-ttu-id="29151-156">关键字`return!`实现计算表达式的值，并换行导致与计算表达式对应的类型：</span><span class="sxs-lookup"><span data-stu-id="29151-156">The `return!` keyword realizes the value of a computation expression and wraps that result in the type corresponding to the computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="29151-157">`return!`由生成器类型上`ReturnFrom(x)`的成员定义，其中`x`是另一个计算表达式。</span><span class="sxs-lookup"><span data-stu-id="29151-157">`return!` is defined by the `ReturnFrom(x)` member on the builder type, where `x` is another computation expression.</span></span>

### `match!`

<span data-ttu-id="29151-158">关键字`match!`允许您在结果上内联对另一个计算表达式和模式匹配的调用：</span><span class="sxs-lookup"><span data-stu-id="29151-158">The `match!` keyword allows you to inline a call to another computation expression and pattern match on its result:</span></span>

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

<span data-ttu-id="29151-159">使用`match!`调用 计算表达式时，它将实现调用的结果，如`let!`。</span><span class="sxs-lookup"><span data-stu-id="29151-159">When calling a computation expression with `match!`, it will realize the result of the call like `let!`.</span></span> <span data-ttu-id="29151-160">这通常用于调用计算表达式时，其中结果为[可选](options.md)。</span><span class="sxs-lookup"><span data-stu-id="29151-160">This is often used when calling a computation expression where the result is an [optional](options.md).</span></span>

## <a name="built-in-computation-expressions"></a><span data-ttu-id="29151-161">内置计算表达式</span><span class="sxs-lookup"><span data-stu-id="29151-161">Built-in computation expressions</span></span>

<span data-ttu-id="29151-162">F# 核心库定义了三个内置计算表达式：[序列表达式](sequences.md)、[异步工作流](asynchronous-workflows.md)和[查询表达式](query-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="29151-162">The F# core library defines three built-in computation expressions: [Sequence Expressions](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Query Expressions](query-expressions.md).</span></span>

## <a name="creating-a-new-type-of-computation-expression"></a><span data-ttu-id="29151-163">创建新类型的计算表达式</span><span class="sxs-lookup"><span data-stu-id="29151-163">Creating a New Type of Computation Expression</span></span>

<span data-ttu-id="29151-164">您可以通过创建生成器类并在类上定义某些特殊方法来定义自己的计算表达式的特征。</span><span class="sxs-lookup"><span data-stu-id="29151-164">You can define the characteristics of your own computation expressions by creating a builder class and defining certain special methods on the class.</span></span> <span data-ttu-id="29151-165">生成器类可以选择定义下表中列出的方法。</span><span class="sxs-lookup"><span data-stu-id="29151-165">The builder class can optionally define the methods as listed in the following table.</span></span>

<span data-ttu-id="29151-166">下表描述了可在工作流生成器类中使用的方法。</span><span class="sxs-lookup"><span data-stu-id="29151-166">The following table describes methods that can be used in a workflow builder class.</span></span>

|<span data-ttu-id="29151-167">**方法**</span><span class="sxs-lookup"><span data-stu-id="29151-167">**Method**</span></span>|<span data-ttu-id="29151-168">**典型签名**</span><span class="sxs-lookup"><span data-stu-id="29151-168">**Typical signature(s)**</span></span>|<span data-ttu-id="29151-169">**说明**</span><span class="sxs-lookup"><span data-stu-id="29151-169">**Description**</span></span>|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|<span data-ttu-id="29151-170">调用`let!`和`do!`在计算表达式中。</span><span class="sxs-lookup"><span data-stu-id="29151-170">Called for `let!` and `do!` in computation expressions.</span></span>|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|<span data-ttu-id="29151-171">将计算表达式包装为函数。</span><span class="sxs-lookup"><span data-stu-id="29151-171">Wraps a computation expression as a function.</span></span>|
|`Return`|`'T -> M<'T>`|<span data-ttu-id="29151-172">在计算`return`表达式中调用。</span><span class="sxs-lookup"><span data-stu-id="29151-172">Called for `return` in computation expressions.</span></span>|
|`ReturnFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="29151-173">在计算`return!`表达式中调用。</span><span class="sxs-lookup"><span data-stu-id="29151-173">Called for `return!` in computation expressions.</span></span>|
|`Run`|<span data-ttu-id="29151-174">`M<'T> -> M<'T>` 或</span><span class="sxs-lookup"><span data-stu-id="29151-174">`M<'T> -> M<'T>` or</span></span><br /><br />`M<'T> -> 'T`|<span data-ttu-id="29151-175">执行计算表达式。</span><span class="sxs-lookup"><span data-stu-id="29151-175">Executes a computation expression.</span></span>|
|`Combine`|<span data-ttu-id="29151-176">`M<'T> * M<'T> -> M<'T>` 或</span><span class="sxs-lookup"><span data-stu-id="29151-176">`M<'T> * M<'T> -> M<'T>` or</span></span><br /><br />`M<unit> * M<'T> -> M<'T>`|<span data-ttu-id="29151-177">调用计算表达式中的排序。</span><span class="sxs-lookup"><span data-stu-id="29151-177">Called for sequencing in computation expressions.</span></span>|
|`For`|<span data-ttu-id="29151-178">`seq<'T> * ('T -> M<'U>) -> M<'U>` 或</span><span class="sxs-lookup"><span data-stu-id="29151-178">`seq<'T> * ('T -> M<'U>) -> M<'U>` or</span></span><br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|<span data-ttu-id="29151-179">在计算`for...do`表达式中调用表达式。</span><span class="sxs-lookup"><span data-stu-id="29151-179">Called for `for...do` expressions in computation expressions.</span></span>|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|<span data-ttu-id="29151-180">在计算`try...finally`表达式中调用表达式。</span><span class="sxs-lookup"><span data-stu-id="29151-180">Called for `try...finally` expressions in computation expressions.</span></span>|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|<span data-ttu-id="29151-181">在计算`try...with`表达式中调用表达式。</span><span class="sxs-lookup"><span data-stu-id="29151-181">Called for `try...with` expressions in computation expressions.</span></span>|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'T :> IDisposable`|<span data-ttu-id="29151-182">在计算`use`表达式中调用绑定。</span><span class="sxs-lookup"><span data-stu-id="29151-182">Called for `use` bindings in computation expressions.</span></span>|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|<span data-ttu-id="29151-183">在计算`while...do`表达式中调用表达式。</span><span class="sxs-lookup"><span data-stu-id="29151-183">Called for `while...do` expressions in computation expressions.</span></span>|
|`Yield`|`'T -> M<'T>`|<span data-ttu-id="29151-184">在计算`yield`表达式中调用表达式。</span><span class="sxs-lookup"><span data-stu-id="29151-184">Called for `yield` expressions in computation expressions.</span></span>|
|`YieldFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="29151-185">在计算`yield!`表达式中调用表达式。</span><span class="sxs-lookup"><span data-stu-id="29151-185">Called for `yield!` expressions in computation expressions.</span></span>|
|`Zero`|`unit -> M<'T>`|<span data-ttu-id="29151-186">调用计算表达式`else`中的空`if...then`表达式分支。</span><span class="sxs-lookup"><span data-stu-id="29151-186">Called for empty `else` branches of `if...then` expressions in computation expressions.</span></span>|
|`Quote`|`Quotations.Expr<'T> -> Quotations.Expr<'T>`|<span data-ttu-id="29151-187">指示计算表达式作为引号传递给`Run`成员。</span><span class="sxs-lookup"><span data-stu-id="29151-187">Indicates that the computation expression is passed to the `Run` member as a quotation.</span></span> <span data-ttu-id="29151-188">它将计算的所有实例转换为引号。</span><span class="sxs-lookup"><span data-stu-id="29151-188">It translates all instances of a computation into a quotation.</span></span>|

<span data-ttu-id="29151-189">生成器类中的许多方法使用并返回`M<'T>`构造，该构造通常是单独定义的类型，用于描述要组合的计算类型，例如，`Async<'T>`对于异步工作流和`Seq<'T>`序列工作流。</span><span class="sxs-lookup"><span data-stu-id="29151-189">Many of the methods in a builder class use and return an `M<'T>` construct, which is typically a separately defined type that characterizes the kind of computations being combined, for example, `Async<'T>` for asynchronous workflows and `Seq<'T>` for sequence workflows.</span></span> <span data-ttu-id="29151-190">这些方法的签名使它们能够相互组合和嵌套，以便从一个构造返回的工作流对象可以传递给下一个构造。</span><span class="sxs-lookup"><span data-stu-id="29151-190">The signatures of these methods enable them to be combined and nested with each other, so that the workflow object returned from one construct can be passed to the next.</span></span> <span data-ttu-id="29151-191">编译器在解析计算表达式时，使用上表中的方法和计算表达式中的代码将表达式转换为一系列嵌套函数调用。</span><span class="sxs-lookup"><span data-stu-id="29151-191">The compiler, when it parses a computation expression, converts the expression into a series of nested function calls by using the methods in the preceding table and the code in the computation expression.</span></span>

<span data-ttu-id="29151-192">嵌套表达式的格式如下：</span><span class="sxs-lookup"><span data-stu-id="29151-192">The nested expression is of the following form:</span></span>

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

<span data-ttu-id="29151-193">在上述代码中，如果计算表达式`Run`生成器`Delay`类中未定义对 和 的调用，则省略它们。</span><span class="sxs-lookup"><span data-stu-id="29151-193">In the above code, the calls to `Run` and `Delay` are omitted if they are not defined in the computation expression builder class.</span></span> <span data-ttu-id="29151-194">计算表达式的正文（此处表示为`{| cexpr |}`）通过下表中描述的翻译转换为涉及生成器类方法的调用。</span><span class="sxs-lookup"><span data-stu-id="29151-194">The body of the computation expression, here denoted as `{| cexpr |}`, is translated into calls involving the methods of the builder class by the translations described in the following table.</span></span> <span data-ttu-id="29151-195">计算表达式`{| cexpr |}`根据这些翻译以递归方式定义，其中`expr`是 F# 表达式，是`cexpr`计算表达式。</span><span class="sxs-lookup"><span data-stu-id="29151-195">The computation expression `{| cexpr |}` is defined recursively according to these translations where `expr` is an F# expression and `cexpr` is a computation expression.</span></span>

|<span data-ttu-id="29151-196">表达式</span><span class="sxs-lookup"><span data-stu-id="29151-196">Expression</span></span>|<span data-ttu-id="29151-197">翻译</span><span class="sxs-lookup"><span data-stu-id="29151-197">Translation</span></span>|
|----------|-----------|
|<code>{ let binding in cexpr }</code>|<code>let binding in {&#124; cexpr &#124;}</code>|
|<code>{ let! pattern = expr in cexpr }</code>|<code>builder.Bind(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{ do! expr in cexpr }</code>|<code>builder.Bind(expr, (fun () -> {&#124; cexpr &#124;}))</code>|
|<code>{ yield expr }</code>|`builder.Yield(expr)`|
|<code>{ yield! expr }</code>|`builder.YieldFrom(expr)`|
|<code>{ return expr }</code>|`builder.Return(expr)`|
|<code>{ return! expr }</code>|`builder.ReturnFrom(expr)`|
|<code>{ use pattern = expr in cexpr }</code>|<code>builder.Using(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{ use! value = expr in cexpr }</code>|<code>builder.Bind(expr, (fun value -> builder.Using(value, (fun value -> { cexpr }))))</code>|
|<code>{ if expr then cexpr0 &#124;}</code>|<code>if expr then { cexpr0 } else builder.Zero()</code>|
|<code>{ if expr then cexpr0 else cexpr1 &#124;}</code>|<code>if expr then { cexpr0 } else { cexpr1 }</code>|
|<code>{ match expr with &#124; pattern_i -> cexpr_i }</code>|<code>match expr with &#124; pattern_i -> { cexpr_i }</code>|
|<code>{ for pattern in expr do cexpr }</code>|<code>builder.For(enumeration, (fun pattern -> { cexpr }))</code>|
|<code>{ for identifier = expr1 to expr2 do cexpr }</code>|<code>builder.For(enumeration, (fun identifier -> { cexpr }))</code>|
|<code>{ while expr do cexpr }</code>|<code>builder.While(fun () -> expr, builder.Delay({ cexpr }))</code>|
|<code>{ try cexpr with &#124; pattern_i -> expr_i }</code>|<code>builder.TryWith(builder.Delay({ cexpr }), (fun value -> match value with &#124; pattern_i -> expr_i &#124; exn -> reraise exn)))</code>|
|<code>{ try cexpr finally expr }</code>|<code>builder.TryFinally(builder.Delay( { cexpr }), (fun () -> expr))</code>|
|<code>{ cexpr1; cexpr2 }</code>|<code>builder.Combine({ cexpr1 }, { cexpr2 })</code>|
|<code>{ other-expr; cexpr }</code>|<code>expr; { cexpr }</code>|
|<code>{ other-expr }</code>|`expr; builder.Zero()`|

<span data-ttu-id="29151-198">在上表中，`other-expr`描述表中未以其他方式列出的表达式。</span><span class="sxs-lookup"><span data-stu-id="29151-198">In the previous table, `other-expr` describes an expression that is not otherwise listed in the table.</span></span> <span data-ttu-id="29151-199">生成器类不需要实现所有方法并支持上表中列出的所有翻译。</span><span class="sxs-lookup"><span data-stu-id="29151-199">A builder class does not need to implement all of the methods and support all of the translations listed in the previous table.</span></span> <span data-ttu-id="29151-200">未实现的构造在该类型的计算表达式中不可用。</span><span class="sxs-lookup"><span data-stu-id="29151-200">Those constructs that are not implemented are not available in computation expressions of that type.</span></span> <span data-ttu-id="29151-201">例如，如果不想在计算表达式中支持`use`关键字，则可以省略生成器类中的定义。 `Use`</span><span class="sxs-lookup"><span data-stu-id="29151-201">For example, if you do not want to support the `use` keyword in your computation expressions, you can omit the definition of `Use` in your builder class.</span></span>

<span data-ttu-id="29151-202">下面的代码示例显示了一个计算表达式，该表达式将计算封装为一系列步骤，可以一次计算一个步骤。</span><span class="sxs-lookup"><span data-stu-id="29151-202">The following code example shows a computation expression that encapsulates a computation as a series of steps that can be evaluated one step at a time.</span></span> <span data-ttu-id="29151-203">受歧视的联合类型`OkOrException`， 编码表达式的错误状态，以计算到目前为止。</span><span class="sxs-lookup"><span data-stu-id="29151-203">A discriminated union type, `OkOrException`, encodes the error state of the expression as evaluated so far.</span></span> <span data-ttu-id="29151-204">此代码演示了可在计算表达式中使用的几个典型模式，例如某些生成器方法的样板实现。</span><span class="sxs-lookup"><span data-stu-id="29151-204">This code demonstrates several typical patterns that you can use in your computation expressions, such as boilerplate implementations of some of the builder methods.</span></span>

```fsharp
// Computations that can be run step by step
type Eventually<'T> =
    | Done of 'T
    | NotYetDone of (unit -> Eventually<'T>)

module Eventually =
    // The bind for the computations. Append 'func' to the
    // computation.
    let rec bind func expr =
        match expr with
        | Done value -> func value
        | NotYetDone work -> NotYetDone (fun () -> bind func (work()))

    // Return the final value wrapped in the Eventually type.
    let result value = Done value

    type OkOrException<'T> =
        | Ok of 'T
        | Exception of System.Exception

    // The catch for the computations. Stitch try/with throughout
    // the computation, and return the overall result as an OkOrException.
    let rec catch expr =
        match expr with
        | Done value -> result (Ok value)
        | NotYetDone work ->
            NotYetDone (fun () ->
                let res = try Ok(work()) with | exn -> Exception exn
                match res with
                | Ok cont -> catch cont // note, a tailcall
                | Exception exn -> result (Exception exn))

    // The delay operator.
    let delay func = NotYetDone (fun () -> func())

    // The stepping action for the computations.
    let step expr =
        match expr with
        | Done _ -> expr
        | NotYetDone func -> func ()

    // The rest of the operations are boilerplate.
    // The tryFinally operator.
    // This is boilerplate in terms of "result", "catch", and "bind".
    let tryFinally expr compensation =
        catch (expr)
        |> bind (fun res ->
            compensation();
            match res with
            | Ok value -> result value
            | Exception exn -> raise exn)

    // The tryWith operator.
    // This is boilerplate in terms of "result", "catch", and "bind".
    let tryWith exn handler =
        catch exn
        |> bind (function Ok value -> result value | Exception exn -> handler exn)

    // The whileLoop operator.
    // This is boilerplate in terms of "result" and "bind".
    let rec whileLoop pred body =
        if pred() then body |> bind (fun _ -> whileLoop pred body)
        else result ()

    // The sequential composition operator.
    // This is boilerplate in terms of "result" and "bind".
    let combine expr1 expr2 =
        expr1 |> bind (fun () -> expr2)

    // The using operator.
    let using (resource: #System.IDisposable) func =
        tryFinally (func resource) (fun () -> resource.Dispose())

    // The forLoop operator.
    // This is boilerplate in terms of "catch", "result", and "bind".
    let forLoop (collection:seq<_>) func =
        let ie = collection.GetEnumerator()
        tryFinally
            (whileLoop
                (fun () -> ie.MoveNext())
                (delay (fun () -> let value = ie.Current in func value)))
            (fun () -> ie.Dispose())

// The builder class.
type EventuallyBuilder() =
    member x.Bind(comp, func) = Eventually.bind func comp
    member x.Return(value) = Eventually.result value
    member x.ReturnFrom(value) = value
    member x.Combine(expr1, expr2) = Eventually.combine expr1 expr2
    member x.Delay(func) = Eventually.delay func
    member x.Zero() = Eventually.result ()
    member x.TryWith(expr, handler) = Eventually.tryWith expr handler
    member x.TryFinally(expr, compensation) = Eventually.tryFinally expr compensation
    member x.For(coll:seq<_>, func) = Eventually.forLoop coll func
    member x.Using(resource, expr) = Eventually.using resource expr

let eventually = new EventuallyBuilder()

let comp = eventually {
    for x in 1..2 do
        printfn " x = %d" x
    return 3 + 4 }

// Try the remaining lines in F# interactive to see how this
// computation expression works in practice.
let step x = Eventually.step x

// returns "NotYetDone <closure>"
comp |> step

// prints "x = 1"
// returns "NotYetDone <closure>"
comp |> step |> step

// prints "x = 1"
// prints "x = 2"
// returns "Done 7"
comp |> step |> step |> step |> step
```

<span data-ttu-id="29151-205">计算表达式具有基础类型，表达式返回该类型。</span><span class="sxs-lookup"><span data-stu-id="29151-205">A computation expression has an underlying type, which the expression returns.</span></span> <span data-ttu-id="29151-206">基础类型可能表示可以执行的计算结果或延迟计算，或者它可能提供一种通过某些类型的集合迭代的方法。</span><span class="sxs-lookup"><span data-stu-id="29151-206">The underlying type may represent a computed result or a delayed computation that can be performed, or it may provide a way to iterate through some type of collection.</span></span> <span data-ttu-id="29151-207">在前面的示例中，基础类型**为 最终**。</span><span class="sxs-lookup"><span data-stu-id="29151-207">In the previous example, the underlying type was **Eventually**.</span></span> <span data-ttu-id="29151-208">对于序列表达式，基础类型为<xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="29151-208">For a sequence expression, the underlying type is <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="29151-209">对于查询表达式，基础类型为<xref:System.Linq.IQueryable?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="29151-209">For a query expression, the underlying type is <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="29151-210">对于异步工作流，基础类型为[`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7)。</span><span class="sxs-lookup"><span data-stu-id="29151-210">For an asynchronous workflow, the underlying type is [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span></span> <span data-ttu-id="29151-211">对象`Async`表示要执行的工作来计算结果。</span><span class="sxs-lookup"><span data-stu-id="29151-211">The `Async` object represents the work to be performed to compute the result.</span></span> <span data-ttu-id="29151-212">例如，调用[`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b)以执行计算并返回结果。</span><span class="sxs-lookup"><span data-stu-id="29151-212">For example, you call [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) to execute a computation and return the result.</span></span>

## <a name="custom-operations"></a><span data-ttu-id="29151-213">自定义操作</span><span class="sxs-lookup"><span data-stu-id="29151-213">Custom Operations</span></span>

<span data-ttu-id="29151-214">可以在计算表达式上定义自定义操作，并在计算表达式中使用自定义操作作为运算符。</span><span class="sxs-lookup"><span data-stu-id="29151-214">You can define a custom operation on a computation expression and use a custom operation as an operator in a computation expression.</span></span> <span data-ttu-id="29151-215">例如，可以在查询表达式中包括查询运算符。</span><span class="sxs-lookup"><span data-stu-id="29151-215">For example, you can include a query operator in a query expression.</span></span> <span data-ttu-id="29151-216">定义自定义操作时，必须在计算表达式中定义"产量"和"For"方法。</span><span class="sxs-lookup"><span data-stu-id="29151-216">When you define a custom operation, you must define the Yield and For methods in the computation expression.</span></span> <span data-ttu-id="29151-217">要定义自定义操作，请将其放在计算表达式的生成器类中，然后应用 。 [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19)</span><span class="sxs-lookup"><span data-stu-id="29151-217">To define a custom operation, put it in a builder class for the computation expression, and then apply the [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span></span> <span data-ttu-id="29151-218">此属性将字符串作为参数，它是要在自定义操作中使用的名称。</span><span class="sxs-lookup"><span data-stu-id="29151-218">This attribute takes a string as an argument, which is the name to be used in a custom operation.</span></span> <span data-ttu-id="29151-219">此名称在计算表达式的开头大括号开始时进入作用域。</span><span class="sxs-lookup"><span data-stu-id="29151-219">This name comes into scope at the start of the opening curly brace of the computation expression.</span></span> <span data-ttu-id="29151-220">因此，不应使用此块中与自定义操作同名的标识符。</span><span class="sxs-lookup"><span data-stu-id="29151-220">Therefore, you shouldn’t use identifiers that have the same name as a custom operation in this block.</span></span> <span data-ttu-id="29151-221">例如，避免使用标识符（如`all`或`last`在查询表达式中）。</span><span class="sxs-lookup"><span data-stu-id="29151-221">For example, avoid the use of identifiers such as `all` or `last` in query expressions.</span></span>

### <a name="extending-existing-builders-with-new-custom-operations"></a><span data-ttu-id="29151-222">使用新的自定义操作扩展现有生成器</span><span class="sxs-lookup"><span data-stu-id="29151-222">Extending existing Builders with new Custom Operations</span></span>

<span data-ttu-id="29151-223">如果您已经具有生成器类，则可以在此生成器类之外扩展其自定义操作。</span><span class="sxs-lookup"><span data-stu-id="29151-223">If you already have a builder class, its custom operations can be extended from outside of this builder class.</span></span> <span data-ttu-id="29151-224">必须在模块中声明扩展。</span><span class="sxs-lookup"><span data-stu-id="29151-224">Extensions must be declared in modules.</span></span> <span data-ttu-id="29151-225">命名空间不能包含扩展成员，但在同一文件和定义该类型的同一命名空间声明组中除外。</span><span class="sxs-lookup"><span data-stu-id="29151-225">Namespaces cannot contain extension members except in the same file and the same namespace declaration group where the type is defined.</span></span>

<span data-ttu-id="29151-226">下面的示例显示了现有`Microsoft.FSharp.Linq.QueryBuilder`类的扩展。</span><span class="sxs-lookup"><span data-stu-id="29151-226">The following example shows the extension of the existing `Microsoft.FSharp.Linq.QueryBuilder` class.</span></span>

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member _.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a><span data-ttu-id="29151-227">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29151-227">See also</span></span>

- [<span data-ttu-id="29151-228">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="29151-228">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="29151-229">异步工作流</span><span class="sxs-lookup"><span data-stu-id="29151-229">Asynchronous Workflows</span></span>](asynchronous-workflows.md)
- [<span data-ttu-id="29151-230">序列</span><span class="sxs-lookup"><span data-stu-id="29151-230">Sequences</span></span>](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)
- [<span data-ttu-id="29151-231">查询表达式</span><span class="sxs-lookup"><span data-stu-id="29151-231">Query Expressions</span></span>](query-expressions.md)
