---
title: 计算表达式 (F#)
description: '了解如何创建在 F #，可以对其进行排列和组合使用控制流构造和绑定中编写计算的方便语法。'
ms.date: 05/16/2016
ms.openlocfilehash: 4995efc757d99a575ee9fad3abf0465a32398c44
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207428"
---
# <a name="computation-expressions"></a><span data-ttu-id="2c5b3-103">计算表达式</span><span class="sxs-lookup"><span data-stu-id="2c5b3-103">Computation Expressions</span></span>

<span data-ttu-id="2c5b3-104">F # 中的计算表达式为编写计算，可以对其进行排列和组合使用控制流构造和绑定提供方便的语法。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-104">Computation expressions in F# provide a convenient syntax for writing computations that can be sequenced and combined using control flow constructs and bindings.</span></span> <span data-ttu-id="2c5b3-105">它们可以用于提供的一种方便语法*monad*，功能的编程功能，可以用于管理数据、 控件和功能的程序中的副作用。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-105">They can be used to provide a convenient syntax for *monads*, a functional programming feature that can be used to manage data, control, and side effects in functional programs.</span></span>


## <a name="built-in-workflows"></a><span data-ttu-id="2c5b3-106">内置的工作流</span><span class="sxs-lookup"><span data-stu-id="2c5b3-106">Built-in Workflows</span></span>

<span data-ttu-id="2c5b3-107">序列表达式是计算表达式的示例，如同异步工作流和查询表达式。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-107">Sequence expressions are an example of a computation expression, as are asynchronous workflows and query expressions.</span></span> <span data-ttu-id="2c5b3-108">有关详细信息，请参阅[序列](sequences.md)，[异步工作流](asynchronous-workflows.md)，和[查询表达式](query-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-108">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Query Expressions](query-expressions.md).</span></span>

<span data-ttu-id="2c5b3-109">某些功能序列表达式和异步工作流均通用的并说明计算表达式的基本语法：</span><span class="sxs-lookup"><span data-stu-id="2c5b3-109">Certain features are common to both sequence expressions and asynchronous workflows and illustrate the basic syntax for a computation expression:</span></span>

```fsharp
builder-name { expression }
```

<span data-ttu-id="2c5b3-110">前面的语法指定给定的表达式是指定的类型的计算表达式*生成器名称*。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-110">The previous syntax specifies that the given expression is a computation expression of a type specified by *builder-name*.</span></span> <span data-ttu-id="2c5b3-111">计算表达式可以是内置的工作流，如`seq`或`async`，也可以是你定义的内容。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-111">The computation expression can be a built-in workflow, such as `seq` or `async`, or it can be something you define.</span></span> <span data-ttu-id="2c5b3-112">*生成器名称*是称为特殊类型的实例的标识符*的生成器类型*。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-112">The *builder-name* is the identifier for an instance of a special type known as the *builder type*.</span></span> <span data-ttu-id="2c5b3-113">生成器类型是类类型，它定义控制表达式的执行方式，它控制的计算表达式的片段会进行合并，即代码的方式的特殊方法。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-113">The builder type is a class type that defines special methods that govern the way the fragments of the computation expression are combined, that is, code that controls how the expression executes.</span></span> <span data-ttu-id="2c5b3-114">另一种方式来描述的生成器类是： 它允许你自定义许多 F # 构造，如循环和绑定的操作。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-114">Another way to describe a builder class is to say that it enables you to customize the operation of many F# constructs, such as loops and bindings.</span></span>

<span data-ttu-id="2c5b3-115">在计算表达式中，两种形式是可用于一些常见的语言构造。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-115">In computation expressions, two forms are available for some common language constructs.</span></span> <span data-ttu-id="2c5b3-116">你可以通过使用调用的 variant 构造 ！</span><span class="sxs-lookup"><span data-stu-id="2c5b3-116">You can invoke the variant constructs by using a !</span></span> <span data-ttu-id="2c5b3-117">（感叹号） 后缀上某些关键字，如`let!`， `do!`，依次类推。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-117">(bang) suffix on certain keywords, such as `let!`, `do!`, and so on.</span></span> <span data-ttu-id="2c5b3-118">这些特殊形式会导致某些替换这些操作的普通内置行为的生成器类中定义的函数。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-118">These special forms cause certain functions defined in the builder class to replace the ordinary built-in behavior of these operations.</span></span> <span data-ttu-id="2c5b3-119">这些形式类似于`yield!`形式`yield`在序列表达式中使用的关键字。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-119">These forms resemble the `yield!` form of the `yield` keyword that is used in sequence expressions.</span></span> <span data-ttu-id="2c5b3-120">有关详细信息，请参阅[序列](sequences.md)。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-120">For more information, see [Sequences](sequences.md).</span></span>


## <a name="creating-a-new-type-of-computation-expression"></a><span data-ttu-id="2c5b3-121">创建新类型的计算表达式</span><span class="sxs-lookup"><span data-stu-id="2c5b3-121">Creating a New Type of Computation Expression</span></span>
<span data-ttu-id="2c5b3-122">你可以通过创建生成器类并在类上定义某些特殊的方法来定义你自己的计算表达式的特征。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-122">You can define the characteristics of your own computation expressions by creating a builder class and defining certain special methods on the class.</span></span> <span data-ttu-id="2c5b3-123">下表中列出，生成器类可以选择定义方法。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-123">The builder class can optionally define the methods as listed in the following table.</span></span>

<span data-ttu-id="2c5b3-124">下表介绍可在工作流生成器类的方法。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-124">The following table describes methods that can be used in a workflow builder class.</span></span>


|<span data-ttu-id="2c5b3-125">**方法**</span><span class="sxs-lookup"><span data-stu-id="2c5b3-125">**Method**</span></span>|<span data-ttu-id="2c5b3-126">**典型的签名**</span><span class="sxs-lookup"><span data-stu-id="2c5b3-126">**Typical signature(s)**</span></span>|<span data-ttu-id="2c5b3-127">**说明**</span><span class="sxs-lookup"><span data-stu-id="2c5b3-127">**Description**</span></span>|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|<span data-ttu-id="2c5b3-128">为调用`let!`和`do!`中计算表达式。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-128">Called for `let!` and `do!` in computation expressions.</span></span>|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|<span data-ttu-id="2c5b3-129">包装计算表达式为函数。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-129">Wraps a computation expression as a function.</span></span>|
|`Return`|`'T -> M<'T>`|<span data-ttu-id="2c5b3-130">为调用`return`中计算表达式。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-130">Called for `return` in computation expressions.</span></span>|
|`ReturnFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="2c5b3-131">为调用`return!`中计算表达式。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-131">Called for `return!` in computation expressions.</span></span>|
|`Run`|<span data-ttu-id="2c5b3-132">`M<'T> -> M<'T>` 或</span><span class="sxs-lookup"><span data-stu-id="2c5b3-132">`M<'T> -> M<'T>` or</span></span><br /><br />`M<'T> -> 'T`|<span data-ttu-id="2c5b3-133">执行计算表达式。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-133">Executes a computation expression.</span></span>|
|`Combine`|<span data-ttu-id="2c5b3-134">`M<'T> * M<'T> -> M<'T>` 或</span><span class="sxs-lookup"><span data-stu-id="2c5b3-134">`M<'T> * M<'T> -> M<'T>` or</span></span><br /><br />`M<unit> * M<'T> -> M<'T>`|<span data-ttu-id="2c5b3-135">调用用于计算表达式中的排序。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-135">Called for sequencing in computation expressions.</span></span>|
|`For`|<span data-ttu-id="2c5b3-136">`seq<'T> * ('T -> M<'U>) -> M<'U>` 或</span><span class="sxs-lookup"><span data-stu-id="2c5b3-136">`seq<'T> * ('T -> M<'U>) -> M<'U>` or</span></span><br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|<span data-ttu-id="2c5b3-137">为调用`for...do`中计算表达式的表达式。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-137">Called for `for...do` expressions in computation expressions.</span></span>|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|<span data-ttu-id="2c5b3-138">为调用`try...finally`中计算表达式的表达式。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-138">Called for `try...finally` expressions in computation expressions.</span></span>|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|<span data-ttu-id="2c5b3-139">为调用`try...with`中计算表达式的表达式。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-139">Called for `try...with` expressions in computation expressions.</span></span>|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'U :> IDisposable`|<span data-ttu-id="2c5b3-140">为调用`use`中计算表达式绑定。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-140">Called for `use` bindings in computation expressions.</span></span>|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|<span data-ttu-id="2c5b3-141">为调用`while...do`中计算表达式的表达式。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-141">Called for `while...do` expressions in computation expressions.</span></span>|
|`Yield`|`'T -> M<'T>`|<span data-ttu-id="2c5b3-142">为调用`yield`中计算表达式的表达式。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-142">Called for `yield` expressions in computation expressions.</span></span>|
|`YieldFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="2c5b3-143">为调用`yield!`中计算表达式的表达式。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-143">Called for `yield!` expressions in computation expressions.</span></span>|
|`Zero`|`unit -> M<'T>`|<span data-ttu-id="2c5b3-144">为空调用`else`的分支`if...then`中计算表达式的表达式。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-144">Called for empty `else` branches of `if...then` expressions in computation expressions.</span></span>|
<span data-ttu-id="2c5b3-145">许多生成器类中的方法使用，并返回`M<'T>`构造，这通常是已单独定义的类型，例如描述被组合的计算的种类，`Async<'T>`对异步工作流和`Seq<'T>`表示序列工作流。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-145">Many of the methods in a builder class use and return an `M<'T>` construct, which is typically a separately defined type that characterizes the kind of computations being combined, for example, `Async<'T>` for asynchronous workflows and `Seq<'T>` for sequence workflows.</span></span> <span data-ttu-id="2c5b3-146">这些方法的签名启用它们要合并且相互嵌套，以便从一个构造返回的工作流对象可以传递到下一步。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-146">The signatures of these methods enable them to be combined and nested with each other, so that the workflow object returned from one construct can be passed to the next.</span></span> <span data-ttu-id="2c5b3-147">编译器在其分析计算表达式，通过使用前面的表中的方法和计算表达式中的代码将表达式转换为一系列嵌套的函数调用。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-147">The compiler, when it parses a computation expression, converts the expression into a series of nested function calls by using the methods in the preceding table and the code in the computation expression.</span></span>

<span data-ttu-id="2c5b3-148">嵌套的表达式为以下形式：</span><span class="sxs-lookup"><span data-stu-id="2c5b3-148">The nested expression is of the following form:</span></span>

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

<span data-ttu-id="2c5b3-149">在上面的代码中，对的调用`Run`和`Delay`如果它们未定义计算表达式生成器类中省略。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-149">In the above code, the calls to `Run` and `Delay` are omitted if they are not defined in the computation expression builder class.</span></span> <span data-ttu-id="2c5b3-150">计算表达式，这里称为主体`{| cexpr |}`下, 表中所描述的翻译转换为涉及生成器类的方法的调用。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-150">The body of the computation expression, here denoted as `{| cexpr |}`, is translated into calls involving the methods of the builder class by the translations described in the following table.</span></span> <span data-ttu-id="2c5b3-151">计算表达式`{| cexpr |}`根据这些转换的定义以递归方式其中`expr`是 F # 表达式和`cexpr`是计算表达式。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-151">The computation expression `{| cexpr |}` is defined recursively according to these translations where `expr` is an F# expression and `cexpr` is a computation expression.</span></span>



|<span data-ttu-id="2c5b3-152">表达式</span><span class="sxs-lookup"><span data-stu-id="2c5b3-152">Expression</span></span>|<span data-ttu-id="2c5b3-153">转换</span><span class="sxs-lookup"><span data-stu-id="2c5b3-153">Translation</span></span>|
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
<span data-ttu-id="2c5b3-154">在前面的表中，`other-expr`描述否则未列出表中的表达式。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-154">In the previous table, `other-expr` describes an expression that is not otherwise listed in the table.</span></span> <span data-ttu-id="2c5b3-155">生成器类不必实现所有方法和支持所有前面的表中列出的翻译。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-155">A builder class does not need to implement all of the methods and support all of the translations listed in the previous table.</span></span> <span data-ttu-id="2c5b3-156">未实现这些构造中均不提供该类型的计算表达式。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-156">Those constructs that are not implemented are not available in computation expressions of that type.</span></span> <span data-ttu-id="2c5b3-157">例如，如果你不想要支持`use`中计算表达式的关键字，则可以省略的定义`Use`生成器类中。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-157">For example, if you do not want to support the `use` keyword in your computation expressions, you can omit the definition of `Use` in your builder class.</span></span>

<span data-ttu-id="2c5b3-158">下面的代码示例演示了一个封装为一系列步骤可计算一次的一个步骤的计算的计算表达式。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-158">The following code example shows a computation expression that encapsulates a computation as a series of steps that can be evaluated one step at a time.</span></span> <span data-ttu-id="2c5b3-159">一个可区分联合类型， `OkOrException`，然后在表达式的错误状态为止计算时对其进行编码。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-159">A discriminated union type, `OkOrException`, encodes the error state of the expression as evaluated so far.</span></span> <span data-ttu-id="2c5b3-160">此代码演示了几个可以计算表达式，如样本的一些生成器方法的实现中使用的典型模式。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-160">This code demonstrates several typical patterns that you can use in your computation expressions, such as boilerplate implementations of some of the builder methods.</span></span>

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
        | Done value -> NotYetDone (fun () -> func value)
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
// returns "NotYetDone <closure>"
comp |> step |> step |> step |> step |> step |> step

// prints "x = 1"
// prints "x = 2"
// returns "Done 7"
comp |> step |> step |> step |> step |> step |> step |> step |> step
```

<span data-ttu-id="2c5b3-161">计算表达式都有基础类型，该表达式返回。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-161">A computation expression has an underlying type, which the expression returns.</span></span> <span data-ttu-id="2c5b3-162">基础类型可能表示计算所得的结果或的延迟的计算时，可以执行，或者它可能会提供了如何循环访问集合的某些类型。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-162">The underlying type may represent a computed result or a delayed computation that can be performed, or it may provide a way to iterate through some type of collection.</span></span> <span data-ttu-id="2c5b3-163">在前面的示例中，工作基础类型为**最终**。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-163">In the previous example, the underlying type was **Eventually**.</span></span> <span data-ttu-id="2c5b3-164">基础类型是序列表达式， <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-164">For a sequence expression, the underlying type is <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2c5b3-165">对于查询表达式中，基础类型是<xref:System.Linq.IQueryable?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-165">For a query expression, the underlying type is <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2c5b3-166">有关异步工作流中，基础类型是[ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7)。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-166">For an asychronous workflow, the underlying type is [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span></span> <span data-ttu-id="2c5b3-167">`Async`对象表示要执行来计算出结果的工作。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-167">The `Async` object represents the work to be performed to compute the result.</span></span> <span data-ttu-id="2c5b3-168">例如，调用[ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b)以执行计算并返回结果。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-168">For example, you call [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) to execute a computation and return the result.</span></span>

## <a name="custom-operations"></a><span data-ttu-id="2c5b3-169">自定义操作</span><span class="sxs-lookup"><span data-stu-id="2c5b3-169">Custom Operations</span></span>
<span data-ttu-id="2c5b3-170">你可以定义上计算表达式的自定义操作，并作为一个操作员计算表达式中使用自定义操作。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-170">You can define a custom operation on a computation expression and use a custom operation as an operator in a computation expression.</span></span> <span data-ttu-id="2c5b3-171">例如，你可以在查询表达式中包括的查询运算符。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-171">For example, you can include a query operator in a query expression.</span></span> <span data-ttu-id="2c5b3-172">当定义自定义操作时，你必须定义 Yield 和计算表达式中的方法。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-172">When you define a custom operation, you must define the Yield and For methods in the computation expression.</span></span> <span data-ttu-id="2c5b3-173">若要定义自定义操作，将它放置在计算表达式，生成器类，然后将应用[ `CustomOperationAttribute` ](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19)。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-173">To define a custom operation, put it in a builder class for the computation expression, and then apply the [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span></span> <span data-ttu-id="2c5b3-174">此特性采用字符串作为参数，这是在自定义操作中使用的名称。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-174">This attribute takes a string as an argument, which is the name to be used in a custom operation.</span></span> <span data-ttu-id="2c5b3-175">此名称是到作用域中计算表达式的左大括号的开头。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-175">This name comes into scope at the start of the opening curly brace of the computation expression.</span></span> <span data-ttu-id="2c5b3-176">因此，不应使用在此块中有同名的自定义操作的标识符。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-176">Therefore, you shouldn’t use identifiers that have the same name as a custom operation in this block.</span></span> <span data-ttu-id="2c5b3-177">例如，如避免标识符使用`all`或`last`在查询表达式中。</span><span class="sxs-lookup"><span data-stu-id="2c5b3-177">For example, avoid the use of identifiers such as `all` or `last` in query expressions.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c5b3-178">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c5b3-178">See Also</span></span>
[<span data-ttu-id="2c5b3-179">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="2c5b3-179">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="2c5b3-180">异步工作流</span><span class="sxs-lookup"><span data-stu-id="2c5b3-180">Asynchronous Workflows</span></span>](asynchronous-workflows.md)

[<span data-ttu-id="2c5b3-181">序列</span><span class="sxs-lookup"><span data-stu-id="2c5b3-181">Sequences</span></span>](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)

[<span data-ttu-id="2c5b3-182">查询表达式</span><span class="sxs-lookup"><span data-stu-id="2c5b3-182">Query Expressions</span></span>](query-expressions.md)
