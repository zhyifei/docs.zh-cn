---
title: 计算表达式 (F#)
description: '了解如何创建在 F #，可以对其进行排列和组合使用控制流构造和绑定中编写计算的方便语法。'
ms.date: 05/16/2016
ms.openlocfilehash: a4ddb3fde284452bc901c5270551611e43742c1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="computation-expressions"></a>计算表达式

F # 中的计算表达式为编写计算，可以对其进行排列和组合使用控制流构造和绑定提供方便的语法。 它们可以用于提供的一种方便语法*monad*，功能的编程功能，可以用于管理数据、 控件和功能的程序中的副作用。


## <a name="built-in-workflows"></a>内置的工作流
序列表达式是计算表达式的示例，如同异步工作流和查询表达式。 有关详细信息，请参阅[序列](sequences.md)，[异步工作流](asynchronous-workflows.md)，和[查询表达式](query-expressions.md)。

某些功能序列表达式和异步工作流均通用的并说明计算表达式的基本语法：

```fsharp
builder-name { expression }
```

前面的语法指定给定的表达式是指定的类型的计算表达式*生成器名称*。 计算表达式可以是内置的工作流，如`seq`或`async`，也可以是你定义的内容。 *生成器名称*是称为特殊类型的实例的标识符*的生成器类型*。 生成器类型是类类型，它定义控制表达式的执行方式，它控制的计算表达式的片段会进行合并，即代码的方式的特殊方法。 另一种方式来描述的生成器类是： 它允许你自定义许多 F # 构造，如循环和绑定的操作。

在计算表达式中，两种形式是可用于一些常见的语言构造。 你可以通过使用调用的 variant 构造 ！ （感叹号） 后缀上某些关键字，如`let!`， `do!`，依次类推。 这些特殊形式会导致某些替换这些操作的普通内置行为的生成器类中定义的函数。 这些形式类似于`yield!`形式`yield`在序列表达式中使用的关键字。 有关详细信息，请参阅[序列](sequences.md)。


## <a name="creating-a-new-type-of-computation-expression"></a>创建新类型的计算表达式
你可以通过创建生成器类并在类上定义某些特殊的方法来定义你自己的计算表达式的特征。 下表中列出，生成器类可以选择定义方法。

下表介绍可在工作流生成器类的方法。


|**方法**|**典型的签名**|**说明**|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|为调用`let!`和`do!`中计算表达式。|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|包装计算表达式为函数。|
|`Return`|`'T -> M<'T>`|为调用`return`中计算表达式。|
|`ReturnFrom`|`M<'T> -> M<'T>`|为调用`return!`中计算表达式。|
|`Run`|`M<'T> -> M<'T>` 或<br /><br />`M<'T> -> 'T`|执行计算表达式。|
|`Combine`|`M<'T> * M<'T> -> M<'T>` 或<br /><br />`M<unit> * M<'T> -> M<'T>`|调用用于计算表达式中的排序。|
|`For`|`seq<'T> * ('T -> M<'U>) -> M<'U>` 或<br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|为调用`for...do`中计算表达式的表达式。|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|为调用`try...finally`中计算表达式的表达式。|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|为调用`try...with`中计算表达式的表达式。|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'U :> IDisposable`|为调用`use`中计算表达式绑定。|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|为调用`while...do`中计算表达式的表达式。|
|`Yield`|`'T -> M<'T>`|为调用`yield`中计算表达式的表达式。|
|`YieldFrom`|`M<'T> -> M<'T>`|为调用`yield!`中计算表达式的表达式。|
|`Zero`|`unit -> M<'T>`|为空调用`else`的分支`if...then`中计算表达式的表达式。|
许多生成器类中的方法使用，并返回`M<'T>`构造，这通常是已单独定义的类型，例如描述被组合的计算的种类，`Async<'T>`对异步工作流和`Seq<'T>`表示序列工作流。 这些方法的签名启用它们要合并且相互嵌套，以便从一个构造返回的工作流对象可以传递到下一步。 编译器在其分析计算表达式，通过使用前面的表中的方法和计算表达式中的代码将表达式转换为一系列嵌套的函数调用。

嵌套的表达式为以下形式：

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

在上面的代码中，对的调用`Run`和`Delay`如果它们未定义计算表达式生成器类中省略。 计算表达式，这里称为主体`{| cexpr |}`下, 表中所描述的翻译转换为涉及生成器类的方法的调用。 计算表达式`{| cexpr |}`根据这些转换的定义以递归方式其中`expr`是 F # 表达式和`cexpr`是计算表达式。



|表达式|转换|
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
在前面的表中，`other-expr`描述否则未列出表中的表达式。 生成器类不必实现所有方法和支持所有前面的表中列出的翻译。 未实现这些构造中均不提供该类型的计算表达式。 例如，如果你不想要支持`use`中计算表达式的关键字，则可以省略的定义`Use`生成器类中。

下面的代码示例演示了一个封装为一系列步骤可计算一次的一个步骤的计算的计算表达式。 一个可区分联合类型， `OkOrException`，然后在表达式的错误状态为止计算时对其进行编码。 此代码演示了几个可以计算表达式，如样本的一些生成器方法的实现中使用的典型模式。

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

计算表达式都有基础类型，该表达式返回。 基础类型可能表示计算所得的结果或的延迟的计算时，可以执行，或者它可能会提供了如何循环访问集合的某些类型。 在前面的示例中，工作基础类型为**最终**。 基础类型是序列表达式， <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>。 对于查询表达式中，基础类型是<xref:System.Linq.IQueryable?displayProperty=nameWithType>。 有关异步工作流中，基础类型是[ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7)。 `Async`对象表示要执行来计算出结果的工作。 例如，调用[ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b)以执行计算并返回结果。

## <a name="custom-operations"></a>自定义操作
你可以定义上计算表达式的自定义操作，并作为一个操作员计算表达式中使用自定义操作。 例如，你可以在查询表达式中包括的查询运算符。 当定义自定义操作时，你必须定义 Yield 和计算表达式中的方法。 若要定义自定义操作，将它放置在计算表达式，生成器类，然后将应用[ `CustomOperationAttribute` ](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19)。 此特性采用字符串作为参数，这是在自定义操作中使用的名称。 此名称是到作用域中计算表达式的左大括号的开头。 因此，不应使用在此块中有同名的自定义操作的标识符。 例如，如避免标识符使用`all`或`last`在查询表达式中。

## <a name="see-also"></a>请参阅
[F# 语言参考](index.md)

[异步工作流](asynchronous-workflows.md)

[序列](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)

[查询表达式](query-expressions.md)
