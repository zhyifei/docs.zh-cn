---
title: 计算表达式
description: 了解如何创建方便的语法中编写计算F#，可以进行序列化和组合使用控制流构造和绑定。
ms.date: 07/27/2018
ms.openlocfilehash: 79159146e24dc50f851c29e3cf7fffe892c6d196
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610692"
---
# <a name="computation-expressions"></a><span data-ttu-id="00520-103">计算表达式</span><span class="sxs-lookup"><span data-stu-id="00520-103">Computation Expressions</span></span>

<span data-ttu-id="00520-104">中的计算表达式F#提供的方便语法用于编写计算，可以进行排列和组合使用控制流构造和绑定。</span><span class="sxs-lookup"><span data-stu-id="00520-104">Computation expressions in F# provide a convenient syntax for writing computations that can be sequenced and combined using control flow constructs and bindings.</span></span> <span data-ttu-id="00520-105">根据计算表达式的种类，它们可以认为的 monad、 monoids、 monad 转换器和 applicative 函子的表达方式。</span><span class="sxs-lookup"><span data-stu-id="00520-105">Depending on the kind of computation expression, they can be thought of as a way to express monads, monoids, monad transformers, and applicative functors.</span></span> <span data-ttu-id="00520-106">但是，不同于其他语言 (如*是否表示法*Haskell 中)，它们不受限于单一的抽象概念，而不依赖宏或其他形式的元编程来完成方便且与上下文相关的语法。</span><span class="sxs-lookup"><span data-stu-id="00520-106">However, unlike other languages (such as *do-notation* in Haskell), they are not tied to a single abstraction, and do not rely on macros or other forms of metaprogramming to accomplish a convenient and context-sensitive syntax.</span></span>

## <a name="overview"></a><span data-ttu-id="00520-107">概述</span><span class="sxs-lookup"><span data-stu-id="00520-107">Overview</span></span>

<span data-ttu-id="00520-108">计算可以采取多种形式。</span><span class="sxs-lookup"><span data-stu-id="00520-108">Computations can take many forms.</span></span> <span data-ttu-id="00520-109">计算的最常见形式是单线程执行，这是易于理解和修改。</span><span class="sxs-lookup"><span data-stu-id="00520-109">The most common form of computation is single-threaded execution, which is easy to understand and modify.</span></span> <span data-ttu-id="00520-110">但是，并非所有形式都是计算的单线程执行像简单。</span><span class="sxs-lookup"><span data-stu-id="00520-110">However, not all forms of computation are as straightforward as single-threaded execution.</span></span> <span data-ttu-id="00520-111">一些示例包括：</span><span class="sxs-lookup"><span data-stu-id="00520-111">Some examples include:</span></span>

* <span data-ttu-id="00520-112">非确定性计算</span><span class="sxs-lookup"><span data-stu-id="00520-112">Non-deterministic computations</span></span>
* <span data-ttu-id="00520-113">异步计算</span><span class="sxs-lookup"><span data-stu-id="00520-113">Asynchronous computations</span></span>
* <span data-ttu-id="00520-114">Effectful 计算</span><span class="sxs-lookup"><span data-stu-id="00520-114">Effectful computations</span></span>
* <span data-ttu-id="00520-115">生成计算</span><span class="sxs-lookup"><span data-stu-id="00520-115">Generative computations</span></span>

<span data-ttu-id="00520-116">一般来说，有*上下文相关*必须在应用程序的某些部分中执行的计算。</span><span class="sxs-lookup"><span data-stu-id="00520-116">More generally, there are *context-sensitive* computations that you must perform in certain parts of an application.</span></span> <span data-ttu-id="00520-117">编写与上下文相关代码极具挑战性，因为可轻松之外不抽象来阻止你执行此操作的情况下的给定上下文将"泄漏"计算。</span><span class="sxs-lookup"><span data-stu-id="00520-117">Writing context-sensitive code can be challenging, as it is easy to "leak" computations outside of a given context without abstractions to prevent you from doing so.</span></span> <span data-ttu-id="00520-118">这些抽象通常具有挑战性，若要编写的自己，这就是为什么F#具有一个通用的方法来实现所谓**计算表达式**。</span><span class="sxs-lookup"><span data-stu-id="00520-118">These abstractions are often challenging to write by yourself, which is why F# has a generalized way to do so called **computation expressions**.</span></span>

<span data-ttu-id="00520-119">计算表达式提供统一的语法和抽象的编码与上下文相关的计算模型。</span><span class="sxs-lookup"><span data-stu-id="00520-119">Computation expressions offer a uniform syntax and abstraction model for encoding context-sensitive computations.</span></span>

<span data-ttu-id="00520-120">每个计算表达式受*生成器*类型。</span><span class="sxs-lookup"><span data-stu-id="00520-120">Every computation expression is backed by a *builder* type.</span></span> <span data-ttu-id="00520-121">生成器类型定义可用于计算表达式的操作。</span><span class="sxs-lookup"><span data-stu-id="00520-121">The builder type defines the operations that are available for the computation expression.</span></span> <span data-ttu-id="00520-122">请参阅[创建一个新类型的计算的表达式](computation-expressions.md#creating-a-new-type-of-computation-expression)，其中说明了如何创建自定义计算表达式。</span><span class="sxs-lookup"><span data-stu-id="00520-122">See [Creating a New Type of Computation Expression](computation-expressions.md#creating-a-new-type-of-computation-expression), which shows how to create a custom computation expression.</span></span>

### <a name="syntax-overview"></a><span data-ttu-id="00520-123">语法概述</span><span class="sxs-lookup"><span data-stu-id="00520-123">Syntax overview</span></span>

<span data-ttu-id="00520-124">所有计算表达式都具有以下形式：</span><span class="sxs-lookup"><span data-stu-id="00520-124">All computation expressions have the following form:</span></span>

```
builder-expr { cexper }
```

<span data-ttu-id="00520-125">其中`builder-expr`的定义是计算表达式的生成器类型名称和`cexper`是计算表达式的表达式主体。</span><span class="sxs-lookup"><span data-stu-id="00520-125">where `builder-expr` is the name of a builder type that defines the computation expression, and `cexper` is the expression body of the computation expression.</span></span> <span data-ttu-id="00520-126">例如，`async`计算的表达式代码可以如下所示：</span><span class="sxs-lookup"><span data-stu-id="00520-126">For example, `async` computation expression code can look like this:</span></span>

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

<span data-ttu-id="00520-127">没有中计算表达式，提供的特殊的附加语法，如前面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="00520-127">There is a special, additional syntax available within a computation expression, as shown in the previous example.</span></span> <span data-ttu-id="00520-128">以下表达式窗体而言，可能有计算表达式：</span><span class="sxs-lookup"><span data-stu-id="00520-128">The following expression forms are possible with computation expressions:</span></span>

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

<span data-ttu-id="00520-129">这些关键字和其他标准的每个F#关键字才在计算表达式中可用，如果它们已在后备生成器类型中定义。</span><span class="sxs-lookup"><span data-stu-id="00520-129">Each of these keywords, and other standard F# keywords are only available in a computation expression if they have been defined in the backing builder type.</span></span> <span data-ttu-id="00520-130">唯一的例外是`match!`，它本身就是使用的语法糖`let!`跟模式匹配的结果。</span><span class="sxs-lookup"><span data-stu-id="00520-130">The only exception to this is `match!`, which is itself syntactic sugar for the use of `let!` followed by a pattern match on the result.</span></span>

<span data-ttu-id="00520-131">生成器类型是一个对象，定义的管理的方式合并的片段的计算表达式; 的特殊方法也就是说，其方法控制计算表达式的行为方式。</span><span class="sxs-lookup"><span data-stu-id="00520-131">The builder type is an object that defines special methods that govern the way the fragments of the computation expression are combined; that is, its methods control how the computation expression behaves.</span></span> <span data-ttu-id="00520-132">另一种方法来描述的生成器类是说它允许你自定义的许多操作F#构造，如循环和绑定。</span><span class="sxs-lookup"><span data-stu-id="00520-132">Another way to describe a builder class is to say that it enables you to customize the operation of many F# constructs, such as loops and bindings.</span></span>

### `let!`

<span data-ttu-id="00520-133">`let!`关键字将调用与另一个计算表达式的结果绑定到一个名称：</span><span class="sxs-lookup"><span data-stu-id="00520-133">The `let!` keyword binds the result of a call to another computation expression to a name:</span></span>

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

<span data-ttu-id="00520-134">如果将绑定到具有的计算表达式调用`let`，则不会计算表达式的结果。</span><span class="sxs-lookup"><span data-stu-id="00520-134">If you bind the call to a computation expression with `let`, you will not get the result of the computation expression.</span></span> <span data-ttu-id="00520-135">相反，您将有绑定的值*未实现*调用到该计算表达式。</span><span class="sxs-lookup"><span data-stu-id="00520-135">Instead, you will have bound the value of the *unrealized* call to that computation expression.</span></span> <span data-ttu-id="00520-136">使用`let!`要绑定到结果。</span><span class="sxs-lookup"><span data-stu-id="00520-136">Use `let!` to bind to the result.</span></span>

<span data-ttu-id="00520-137">`let!` 由定义`Bind(x, f)`生成器类型上的成员。</span><span class="sxs-lookup"><span data-stu-id="00520-137">`let!` is defined by the `Bind(x, f)` member on the builder type.</span></span>

### `do!`

<span data-ttu-id="00520-138">`do!`关键字是用于调用计算表达式将返回`unit`-等类型 (由定义`Zero`生成器上的成员):</span><span class="sxs-lookup"><span data-stu-id="00520-138">The `do!` keyword is for calling a computation expression that returns a `unit`-like type (defined by the `Zero` member on the builder):</span></span>

```fsharp
let doThingsAsync data url =
    async {
        do! submitData data url
        ...
    }
```

<span data-ttu-id="00520-139">有关[异步工作流](asynchronous-workflows.md)，此类型是`Async<unit>`。</span><span class="sxs-lookup"><span data-stu-id="00520-139">For the [async workflow](asynchronous-workflows.md), this type is `Async<unit>`.</span></span> <span data-ttu-id="00520-140">对于其他计算表达式，该类型很可能是`CExpType<unit>`。</span><span class="sxs-lookup"><span data-stu-id="00520-140">For other computation expressions, the type is likely to be `CExpType<unit>`.</span></span>

<span data-ttu-id="00520-141">`do!` 定义由`Bind(x, f)`成员上的生成器类型，其中`f`生成`unit`。</span><span class="sxs-lookup"><span data-stu-id="00520-141">`do!` is defined by the `Bind(x, f)` member on the builder type, where `f` produces a `unit`.</span></span>

### `yield`

<span data-ttu-id="00520-142">`yield`关键字，以便它可以用作从计算表达式返回一个值是<xref:System.Collections.Generic.IEnumerable%601>:</span><span class="sxs-lookup"><span data-stu-id="00520-142">The `yield` keyword is for returning a value from the computation expression so that it can be consumed as an <xref:System.Collections.Generic.IEnumerable%601>:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

<span data-ttu-id="00520-143">如同[yield 关键字在 C# 中的](../../csharp/language-reference/keywords/yield.md)，因为它循环访问生成计算表达式中的每个元素。</span><span class="sxs-lookup"><span data-stu-id="00520-143">As with the [yield keyword in C#](../../csharp/language-reference/keywords/yield.md), each element in the computation expression is yielded back as it is iterated.</span></span>

<span data-ttu-id="00520-144">`yield` 定义由`Yield(x)`成员上的生成器类型，其中`x`是要重新生成的项。</span><span class="sxs-lookup"><span data-stu-id="00520-144">`yield` is defined by the `Yield(x)` member on the builder type, where `x` is the item to yield back.</span></span>

### `yield!`

<span data-ttu-id="00520-145">`yield!`关键字是用于平铺中计算表达式的值的集合：</span><span class="sxs-lookup"><span data-stu-id="00520-145">The `yield!` keyword is for flattening a collection of values from a computation expression:</span></span>

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

<span data-ttu-id="00520-146">计算表达式求值时，由调用`yield!`将具有其项生成后一通过一，平展结果。</span><span class="sxs-lookup"><span data-stu-id="00520-146">When evaluated, the computation expression called by `yield!` will have its items yielded back one-by-one, flattening the result.</span></span>

<span data-ttu-id="00520-147">`yield!` 定义由`YieldFrom(x)`成员上的生成器类型，其中`x`是值的集合。</span><span class="sxs-lookup"><span data-stu-id="00520-147">`yield!` is defined by the `YieldFrom(x)` member on the builder type, where `x` is a collection of values.</span></span>

### `return`

<span data-ttu-id="00520-148">`return`关键字将值包装在对应于计算表达式的类型。</span><span class="sxs-lookup"><span data-stu-id="00520-148">The `return` keyword wraps a value in the type corresponding to the computation expression.</span></span> <span data-ttu-id="00520-149">除了使用的计算表达式`yield`，使用它来"完成"计算表达式：</span><span class="sxs-lookup"><span data-stu-id="00520-149">Aside from computation expressions using `yield`, it is used to "complete" a computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="00520-150">`return` 定义由`Return(x)`成员上的生成器类型，其中`x`是要包装的项。</span><span class="sxs-lookup"><span data-stu-id="00520-150">`return` is defined by the `Return(x)` member on the builder type, where `x` is the item to wrap.</span></span>

### `return!`

<span data-ttu-id="00520-151">`return!`关键字意识到计算表达式的值并将该结果包装中对应于计算表达式的类型：</span><span class="sxs-lookup"><span data-stu-id="00520-151">The `return!` keyword realizes the value of a computation expression and wraps that result in the type corresponding to the computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="00520-152">`return!` 定义由`ReturnFrom(x)`成员上的生成器类型，其中`x`是另一个计算表达式。</span><span class="sxs-lookup"><span data-stu-id="00520-152">`return!` is defined by the `ReturnFrom(x)` member on the builder type, where `x` is another computation expression.</span></span>

### `match!`

<span data-ttu-id="00520-153">从F#4.5 中，`match!`关键字可以内联调用根据其结果的另一个计算表达式和模式匹配：</span><span class="sxs-lookup"><span data-stu-id="00520-153">Starting with F# 4.5, the `match!` keyword allows you to inline a call to another computation expression and pattern match on its result:</span></span>

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

<span data-ttu-id="00520-154">调用具有的计算表达式时`match!`，它将会获得如下调用的结果`let!`。</span><span class="sxs-lookup"><span data-stu-id="00520-154">When calling a computation expression with `match!`, it will realize the result of the call like `let!`.</span></span> <span data-ttu-id="00520-155">这常用于调用计算表达式结果时[可选](options.md)。</span><span class="sxs-lookup"><span data-stu-id="00520-155">This is often used when calling a computation expression where the result is an [optional](options.md).</span></span>

## <a name="built-in-computation-expressions"></a><span data-ttu-id="00520-156">内置的计算表达式</span><span class="sxs-lookup"><span data-stu-id="00520-156">Built-in computation expressions</span></span>

<span data-ttu-id="00520-157">F#核心库定义了三个内置的计算表达式：[序列表达式](sequences.md)，[异步工作流](asynchronous-workflows.md)，和[查询表达式](query-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="00520-157">The F# core library defines three built-in computation expressions: [Sequence Expressions](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Query Expressions](query-expressions.md).</span></span>

## <a name="creating-a-new-type-of-computation-expression"></a><span data-ttu-id="00520-158">创建新的计算表达式的类型</span><span class="sxs-lookup"><span data-stu-id="00520-158">Creating a New Type of Computation Expression</span></span>

<span data-ttu-id="00520-159">可以通过创建一个生成器类和类上定义某些特殊的方法来定义您自己的计算表达式的特征。</span><span class="sxs-lookup"><span data-stu-id="00520-159">You can define the characteristics of your own computation expressions by creating a builder class and defining certain special methods on the class.</span></span> <span data-ttu-id="00520-160">下表中列出，生成器类可以选择定义方法。</span><span class="sxs-lookup"><span data-stu-id="00520-160">The builder class can optionally define the methods as listed in the following table.</span></span>

<span data-ttu-id="00520-161">下表介绍可在工作流生成器类的方法。</span><span class="sxs-lookup"><span data-stu-id="00520-161">The following table describes methods that can be used in a workflow builder class.</span></span>

|<span data-ttu-id="00520-162">**方法**</span><span class="sxs-lookup"><span data-stu-id="00520-162">**Method**</span></span>|<span data-ttu-id="00520-163">**典型的签名**</span><span class="sxs-lookup"><span data-stu-id="00520-163">**Typical signature(s)**</span></span>|<span data-ttu-id="00520-164">**说明**</span><span class="sxs-lookup"><span data-stu-id="00520-164">**Description**</span></span>|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|<span data-ttu-id="00520-165">为调用`let!`和`do!`中计算表达式。</span><span class="sxs-lookup"><span data-stu-id="00520-165">Called for `let!` and `do!` in computation expressions.</span></span>|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|<span data-ttu-id="00520-166">包装一个函数作为计算表达式。</span><span class="sxs-lookup"><span data-stu-id="00520-166">Wraps a computation expression as a function.</span></span>|
|`Return`|`'T -> M<'T>`|<span data-ttu-id="00520-167">为调用`return`中计算表达式。</span><span class="sxs-lookup"><span data-stu-id="00520-167">Called for `return` in computation expressions.</span></span>|
|`ReturnFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="00520-168">为调用`return!`中计算表达式。</span><span class="sxs-lookup"><span data-stu-id="00520-168">Called for `return!` in computation expressions.</span></span>|
|`Run`|<span data-ttu-id="00520-169">`M<'T> -> M<'T>` 或</span><span class="sxs-lookup"><span data-stu-id="00520-169">`M<'T> -> M<'T>` or</span></span><br /><br />`M<'T> -> 'T`|<span data-ttu-id="00520-170">执行计算表达式。</span><span class="sxs-lookup"><span data-stu-id="00520-170">Executes a computation expression.</span></span>|
|`Combine`|<span data-ttu-id="00520-171">`M<'T> * M<'T> -> M<'T>` 或</span><span class="sxs-lookup"><span data-stu-id="00520-171">`M<'T> * M<'T> -> M<'T>` or</span></span><br /><br />`M<unit> * M<'T> -> M<'T>`|<span data-ttu-id="00520-172">调用用于在计算表达式中的排序。</span><span class="sxs-lookup"><span data-stu-id="00520-172">Called for sequencing in computation expressions.</span></span>|
|`For`|<span data-ttu-id="00520-173">`seq<'T> * ('T -> M<'U>) -> M<'U>` 或</span><span class="sxs-lookup"><span data-stu-id="00520-173">`seq<'T> * ('T -> M<'U>) -> M<'U>` or</span></span><br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|<span data-ttu-id="00520-174">为调用`for...do`中计算表达式的表达式。</span><span class="sxs-lookup"><span data-stu-id="00520-174">Called for `for...do` expressions in computation expressions.</span></span>|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|<span data-ttu-id="00520-175">为调用`try...finally`中计算表达式的表达式。</span><span class="sxs-lookup"><span data-stu-id="00520-175">Called for `try...finally` expressions in computation expressions.</span></span>|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|<span data-ttu-id="00520-176">为调用`try...with`中计算表达式的表达式。</span><span class="sxs-lookup"><span data-stu-id="00520-176">Called for `try...with` expressions in computation expressions.</span></span>|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'U :> IDisposable`|<span data-ttu-id="00520-177">为调用`use`中计算表达式的绑定。</span><span class="sxs-lookup"><span data-stu-id="00520-177">Called for `use` bindings in computation expressions.</span></span>|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|<span data-ttu-id="00520-178">为调用`while...do`中计算表达式的表达式。</span><span class="sxs-lookup"><span data-stu-id="00520-178">Called for `while...do` expressions in computation expressions.</span></span>|
|`Yield`|`'T -> M<'T>`|<span data-ttu-id="00520-179">为调用`yield`中计算表达式的表达式。</span><span class="sxs-lookup"><span data-stu-id="00520-179">Called for `yield` expressions in computation expressions.</span></span>|
|`YieldFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="00520-180">为调用`yield!`中计算表达式的表达式。</span><span class="sxs-lookup"><span data-stu-id="00520-180">Called for `yield!` expressions in computation expressions.</span></span>|
|`Zero`|`unit -> M<'T>`|<span data-ttu-id="00520-181">调用空`else`的分支`if...then`中计算表达式的表达式。</span><span class="sxs-lookup"><span data-stu-id="00520-181">Called for empty `else` branches of `if...then` expressions in computation expressions.</span></span>|

<span data-ttu-id="00520-182">许多生成器类中的方法使用并返回`M<'T>`构造，这通常是已单独定义的类型特征的计算种类的组合，例如，`Async<'T>`对异步工作流和`Seq<'T>`表示序列工作流。</span><span class="sxs-lookup"><span data-stu-id="00520-182">Many of the methods in a builder class use and return an `M<'T>` construct, which is typically a separately defined type that characterizes the kind of computations being combined, for example, `Async<'T>` for asynchronous workflows and `Seq<'T>` for sequence workflows.</span></span> <span data-ttu-id="00520-183">这些方法的签名启用它们要合并且相互嵌套，以便从一个构造返回的工作流对象可以传递到下一步。</span><span class="sxs-lookup"><span data-stu-id="00520-183">The signatures of these methods enable them to be combined and nested with each other, so that the workflow object returned from one construct can be passed to the next.</span></span> <span data-ttu-id="00520-184">编译器分析计算表达式时使用上表中的方法和计算表达式中的代码，为一系列嵌套的函数调用的转换表达式。</span><span class="sxs-lookup"><span data-stu-id="00520-184">The compiler, when it parses a computation expression, converts the expression into a series of nested function calls by using the methods in the preceding table and the code in the computation expression.</span></span>

<span data-ttu-id="00520-185">嵌套的表达式采用以下形式：</span><span class="sxs-lookup"><span data-stu-id="00520-185">The nested expression is of the following form:</span></span>

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

<span data-ttu-id="00520-186">在上面的代码中，对调用`Run`和`Delay`省略了如果中计算表达式生成器类未定义。</span><span class="sxs-lookup"><span data-stu-id="00520-186">In the above code, the calls to `Run` and `Delay` are omitted if they are not defined in the computation expression builder class.</span></span> <span data-ttu-id="00520-187">计算表达式，此处表示为正文`{| cexpr |}`下, 表中所描述的翻译转换为涉及生成器类的方法的调用。</span><span class="sxs-lookup"><span data-stu-id="00520-187">The body of the computation expression, here denoted as `{| cexpr |}`, is translated into calls involving the methods of the builder class by the translations described in the following table.</span></span> <span data-ttu-id="00520-188">计算表达式`{| cexpr |}`定义以递归方式根据这些翻译其中`expr`是F#表达式并`cexpr`是计算表达式。</span><span class="sxs-lookup"><span data-stu-id="00520-188">The computation expression `{| cexpr |}` is defined recursively according to these translations where `expr` is an F# expression and `cexpr` is a computation expression.</span></span>

|<span data-ttu-id="00520-189">表达式</span><span class="sxs-lookup"><span data-stu-id="00520-189">Expression</span></span>|<span data-ttu-id="00520-190">转换</span><span class="sxs-lookup"><span data-stu-id="00520-190">Translation</span></span>|
|----------|-----------|
|<code>{&#124; let binding in cexpr &#124;}</code>|<code>let binding in {&#124; cexpr &#124;}</code>|
|<code>{&#124; let! pattern = expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; do! expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun () -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; yield expr &#124;}</code>|`builder.Yield(expr)`|
|<code>{&#124; yield! expr &#124;}</code>|`builder.YieldFrom(expr)`|
|<code>{&#124; return expr &#124;}</code>|`builder.Return(expr)`|
|<code>{&#124; return! expr &#124;}</code>|`builder.ReturnFrom(expr)`|
|<code>{&#124; use pattern = expr in cexpr &#124;}</code>|<code>builder.Using(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; use! value = expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun value -> builder.Using(value, (fun value -> {&#124; cexpr &#124;}))))</code>|
|<code>{&#124; if expr then cexpr0 &#124;}</code>|<code>if expr then {&#124; cexpr0 &#124;} else binder.Zero()</code>|
|<code>{&#124; if expr then cexpr0 else cexpr1 &#124;}</code>|<code>if expr then {&#124; cexpr0 &#124;} else {&#124; cexpr1 &#124;}</code>|
|<code>{&#124; match expr with &#124; pattern_i -> cexpr_i &#124;}</code>|<code>match expr with &#124; pattern_i -> {&#124; cexpr_i &#124;}</code>|
|<code>{&#124; for pattern in expr do cexpr &#124;}</code>|<code>builder.For(enumeration, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; for identifier = expr1 to expr2 do cexpr &#124;}</code>|<code>builder.For(enumeration, (fun identifier -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; while expr do cexpr &#124;}</code>|<code>builder.While(fun () -> expr), builder.Delay({&#124;cexpr &#124;})</code>|
|<code>{&#124; try cexpr with &#124; pattern_i -> expr_i &#124;}</code>|<code>builder.TryWith(builder.Delay({&#124; cexpr &#124;}), (fun value -> match value with &#124; pattern_i -> expr_i &#124; exn -> reraise exn)))</code>|
|<code>{&#124; try cexpr finally expr &#124;}</code>|<code>builder.TryFinally(builder.Delay( {&#124; cexpr &#124;}), (fun () -> expr))</code>|
|<code>{&#124; cexpr1; cexpr2 &#124;}</code>|<code>builder.Combine({&#124;cexpr1 &#124;}, {&#124; cexpr2 &#124;})</code>|
|<code>{&#124; other-expr; cexpr &#124;}</code>|<code>expr; {&#124; cexpr &#124;}</code>|
|<code>{&#124; other-expr &#124;}</code>|`expr; builder.Zero()`|

<span data-ttu-id="00520-191">上表中`other-expr`介绍一个表达式，否则不表中列出。</span><span class="sxs-lookup"><span data-stu-id="00520-191">In the previous table, `other-expr` describes an expression that is not otherwise listed in the table.</span></span> <span data-ttu-id="00520-192">生成器类不需要实现的所有方法和支持所有前面的表中列出的翻译。</span><span class="sxs-lookup"><span data-stu-id="00520-192">A builder class does not need to implement all of the methods and support all of the translations listed in the previous table.</span></span> <span data-ttu-id="00520-193">未实现这些构造不在该类型的计算表达式中可用。</span><span class="sxs-lookup"><span data-stu-id="00520-193">Those constructs that are not implemented are not available in computation expressions of that type.</span></span> <span data-ttu-id="00520-194">例如，如果你不想要支持`use`中计算表达式的关键字，则可以省略的定义`Use`生成器类中。</span><span class="sxs-lookup"><span data-stu-id="00520-194">For example, if you do not want to support the `use` keyword in your computation expressions, you can omit the definition of `Use` in your builder class.</span></span>

<span data-ttu-id="00520-195">下面的代码示例显示了一系列步骤，可以是计算一次一个步骤封装计算的计算表达式。</span><span class="sxs-lookup"><span data-stu-id="00520-195">The following code example shows a computation expression that encapsulates a computation as a series of steps that can be evaluated one step at a time.</span></span> <span data-ttu-id="00520-196">一个可区分联合类型`OkOrException`，到目前为止计算对表达式的错误状态进行编码。</span><span class="sxs-lookup"><span data-stu-id="00520-196">A discriminated union type, `OkOrException`, encodes the error state of the expression as evaluated so far.</span></span> <span data-ttu-id="00520-197">此代码演示了可以在您的计算表达式，如生成器方法的一些样本实现中使用的几种典型模式。</span><span class="sxs-lookup"><span data-stu-id="00520-197">This code demonstrates several typical patterns that you can use in your computation expressions, such as boilerplate implementations of some of the builder methods.</span></span>

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

<span data-ttu-id="00520-198">计算表达式的表达式返回的基础类型。</span><span class="sxs-lookup"><span data-stu-id="00520-198">A computation expression has an underlying type, which the expression returns.</span></span> <span data-ttu-id="00520-199">基础类型可表示计算所得的结果或可以执行的延迟的计算或它可能会提供一种方法来循环访问某种类型的集合。</span><span class="sxs-lookup"><span data-stu-id="00520-199">The underlying type may represent a computed result or a delayed computation that can be performed, or it may provide a way to iterate through some type of collection.</span></span> <span data-ttu-id="00520-200">在上一示例中，基础类型是**最终**。</span><span class="sxs-lookup"><span data-stu-id="00520-200">In the previous example, the underlying type was **Eventually**.</span></span> <span data-ttu-id="00520-201">为序列表达式的基础类型是<xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="00520-201">For a sequence expression, the underlying type is <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="00520-202">对于查询表达式中，基础类型是<xref:System.Linq.IQueryable?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="00520-202">For a query expression, the underlying type is <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="00520-203">对于异步工作流，基础类型是[ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7)。</span><span class="sxs-lookup"><span data-stu-id="00520-203">For an asynchronous workflow, the underlying type is [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span></span> <span data-ttu-id="00520-204">`Async`对象都表示为计算的结果执行的工作。</span><span class="sxs-lookup"><span data-stu-id="00520-204">The `Async` object represents the work to be performed to compute the result.</span></span> <span data-ttu-id="00520-205">例如，调用[ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b)执行计算并返回结果。</span><span class="sxs-lookup"><span data-stu-id="00520-205">For example, you call [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) to execute a computation and return the result.</span></span>

## <a name="custom-operations"></a><span data-ttu-id="00520-206">自定义操作</span><span class="sxs-lookup"><span data-stu-id="00520-206">Custom Operations</span></span>

<span data-ttu-id="00520-207">您可以定义上计算表达式的自定义操作和使用自定义操作作为计算表达式中的运算符。</span><span class="sxs-lookup"><span data-stu-id="00520-207">You can define a custom operation on a computation expression and use a custom operation as an operator in a computation expression.</span></span> <span data-ttu-id="00520-208">例如，您可以在查询表达式中包含的查询运算符。</span><span class="sxs-lookup"><span data-stu-id="00520-208">For example, you can include a query operator in a query expression.</span></span> <span data-ttu-id="00520-209">在定义自定义操作时，必须定义 Yield 和计算表达式中的方法。</span><span class="sxs-lookup"><span data-stu-id="00520-209">When you define a custom operation, you must define the Yield and For methods in the computation expression.</span></span> <span data-ttu-id="00520-210">若要定义自定义操作，将其放入一个生成器类，用于计算表达式，并将[ `CustomOperationAttribute` ](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19)。</span><span class="sxs-lookup"><span data-stu-id="00520-210">To define a custom operation, put it in a builder class for the computation expression, and then apply the [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span></span> <span data-ttu-id="00520-211">此属性采用一个字符串作为参数，它是用于在自定义操作中使用的名称。</span><span class="sxs-lookup"><span data-stu-id="00520-211">This attribute takes a string as an argument, which is the name to be used in a custom operation.</span></span> <span data-ttu-id="00520-212">此名称发送到开头的计算表达式的左大括号的作用域中时。</span><span class="sxs-lookup"><span data-stu-id="00520-212">This name comes into scope at the start of the opening curly brace of the computation expression.</span></span> <span data-ttu-id="00520-213">因此，不应使用此块中具有相同名称作为自定义操作的标识符。</span><span class="sxs-lookup"><span data-stu-id="00520-213">Therefore, you shouldn’t use identifiers that have the same name as a custom operation in this block.</span></span> <span data-ttu-id="00520-214">例如，例如避免使用的标识符`all`或`last`在查询表达式中。</span><span class="sxs-lookup"><span data-stu-id="00520-214">For example, avoid the use of identifiers such as `all` or `last` in query expressions.</span></span>

### <a name="extending-existing-builders-with-new-custom-operations"></a><span data-ttu-id="00520-215">扩展现有生成器与新的自定义操作</span><span class="sxs-lookup"><span data-stu-id="00520-215">Extending existing Builders with new Custom Operations</span></span>

<span data-ttu-id="00520-216">如果您已有一个生成器类，其自定义操作可从此生成器类的外部进行扩展。</span><span class="sxs-lookup"><span data-stu-id="00520-216">If you already have a builder class, its custom operations can be extended from outside of this builder class.</span></span> <span data-ttu-id="00520-217">必须在模块中声明扩展。</span><span class="sxs-lookup"><span data-stu-id="00520-217">Extensions must be declared in modules.</span></span> <span data-ttu-id="00520-218">命名空间不能包含除相同的文件和定义该类型的相同命名空间声明组中的扩展成员。</span><span class="sxs-lookup"><span data-stu-id="00520-218">Namespaces cannot contain extension members except in the same file and the same namespace declaration group where the type is defined.</span></span>

<span data-ttu-id="00520-219">下面的示例演示的现有扩展`Microsoft.FSharp.Linq.QueryBuilder`类。</span><span class="sxs-lookup"><span data-stu-id="00520-219">The following example shows the extension of the existing `Microsoft.FSharp.Linq.QueryBuilder` class.</span></span>

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member __.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a><span data-ttu-id="00520-220">请参阅</span><span class="sxs-lookup"><span data-stu-id="00520-220">See also</span></span>

- [<span data-ttu-id="00520-221">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="00520-221">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="00520-222">异步工作流</span><span class="sxs-lookup"><span data-stu-id="00520-222">Asynchronous Workflows</span></span>](asynchronous-workflows.md)
- [<span data-ttu-id="00520-223">序列</span><span class="sxs-lookup"><span data-stu-id="00520-223">Sequences</span></span>](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)
- [<span data-ttu-id="00520-224">查询表达式</span><span class="sxs-lookup"><span data-stu-id="00520-224">Query Expressions</span></span>](query-expressions.md)