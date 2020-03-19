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
# <a name="computation-expressions"></a>计算表达式

F# 中的计算表达式为编写可以使用控制流构造和绑定进行排序和组合的计算提供了方便的语法。 根据计算表达式的类型，它们可以被认为是一种表达单体、单体、莫纳变压器和施用器的方法。 但是，与其他语言（如 Haskell 中的*do-符号*）不同，它们不绑定到单个抽象，并且不依赖宏或其他形式的元编程来完成方便且上下文相关的语法。

## <a name="overview"></a>概述

计算可以有多种形式。 最常见的计算形式是单线程执行，易于理解和修改。 但是，并非所有形式的计算都像单线程执行那样简单明了。 示例包括：

- 非确定性计算
- 异步计算
- 有效的计算
- 生成计算

更一般情况下，必须在应用程序的某些部分执行*上下文相关的*计算。 编写上下文敏感代码可能具有挑战性，因为很容易在给定上下文之外"泄漏"计算，而无需抽象来防止您这样做。 这些抽象通常具有挑战性，可以自己编写，这就是为什么 F# 具有一种通用的方式来执行此操作，称为**计算表达式**。

计算表达式为编码上下文敏感的计算提供了统一的语法和抽象模型。

每个计算表达式都由*生成器*类型支持。 生成器类型定义可用于计算表达式的操作。 请参阅[创建新类型的计算表达式](computation-expressions.md#creating-a-new-type-of-computation-expression)，其中演示如何创建自定义计算表达式。

### <a name="syntax-overview"></a>语法概述

所有计算表达式都具有以下形式：

```fsharp
builder-expr { cexper }
```

其中`builder-expr`是定义计算表达式的生成器类型的名称，是`cexper`计算表达式的表达式正文。 例如，`async`计算表达式代码可以如下所示：

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

计算表达式中提供了一个特殊的附加语法，如上例所示。 计算表达式可以实现以下表达式形式：

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

这些关键字和其他标准 F# 关键字仅在支持生成器类型中定义时才在计算表达式中可用。 唯一的例外是`match!`，它本身就是使用后跟模式匹配结果的`let!`语法糖。

生成器类型是定义控制计算表达式片段组合方式的特殊方法的对象;也就是说，它的方法控制计算表达式的表现。 描述生成器类的另一种方法是说它使您能够自定义许多 F# 构造（如循环和绑定）的操作。

### `let!`

关键字`let!`将调用到另一个计算表达式的结果绑定到名称：

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

如果使用 将调用绑定到 计算表达式`let`，则不会获取计算表达式的结果。 相反，您将绑定到该计算表达式的*未实现*调用的值。 用于`let!`绑定到结果。

`let!`由生成器类型上`Bind(x, f)`的成员定义。

### `do!`

关键字`do!`用于调用返回`unit`类似类型（由生成器上`Zero`的成员定义）的计算表达式：

```fsharp
let doThingsAsync data url =
    async {
        do! submitData data url
        ...
    }
```

对于[异步工作流](asynchronous-workflows.md)，此类型为`Async<unit>`。 对于其他计算表达式，类型可能是`CExpType<unit>`。

`do!`由生成器类型上`Bind(x, f)`的成员定义，其中`f`生成 。 `unit`

### `yield`

关键字`yield`用于从计算表达式返回值，以便它可以用作<xref:System.Collections.Generic.IEnumerable%601>：

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

在大多数情况下，调用方可以省略它。 省略的最常见方法是`yield`使用`->`运算符：

```fsharp
let squares =
    seq {
        for i in 1..10 -> i * i
    }

for sq in squares do
    printfn "%d" sq
```

对于可能产生许多不同的值的更复杂的表达式，也许有条件地省略关键字可以执行以下操作：

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

与[C# 中的屈服关键字](../../csharp/language-reference/keywords/yield.md)一样，计算表达式中的每个元素在迭代时都会返回。

`yield`由生成器类型上`Yield(x)`的成员定义，其中`x`要回产的项目。

### `yield!`

关键字`yield!`用于拼平计算表达式中的值集合：

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

计算时，调用`yield!`的计算表达式将使其项逐个返回，从而使结果平展。

`yield!`由生成器类型上`YieldFrom(x)`的成员定义，其中`x`是值的集合。

与`yield``yield!`必须显式指定不同。 它的行为在计算表达式中不隐式。

### `return`

关键字`return`在与计算表达式对应的类型中换行值。 除了使用`yield`的计算表达式外，它还用于"完成"计算表达式：

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return`由生成器类型上`Return(x)`的成员定义，要包装的项`x`所在的位置。

### `return!`

关键字`return!`实现计算表达式的值，并换行导致与计算表达式对应的类型：

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return!`由生成器类型上`ReturnFrom(x)`的成员定义，其中`x`是另一个计算表达式。

### `match!`

关键字`match!`允许您在结果上内联对另一个计算表达式和模式匹配的调用：

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

使用`match!`调用 计算表达式时，它将实现调用的结果，如`let!`。 这通常用于调用计算表达式时，其中结果为[可选](options.md)。

## <a name="built-in-computation-expressions"></a>内置计算表达式

F# 核心库定义了三个内置计算表达式：[序列表达式](sequences.md)、[异步工作流](asynchronous-workflows.md)和[查询表达式](query-expressions.md)。

## <a name="creating-a-new-type-of-computation-expression"></a>创建新类型的计算表达式

您可以通过创建生成器类并在类上定义某些特殊方法来定义自己的计算表达式的特征。 生成器类可以选择定义下表中列出的方法。

下表描述了可在工作流生成器类中使用的方法。

|**方法**|**典型签名**|**说明**|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|调用`let!`和`do!`在计算表达式中。|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|将计算表达式包装为函数。|
|`Return`|`'T -> M<'T>`|在计算`return`表达式中调用。|
|`ReturnFrom`|`M<'T> -> M<'T>`|在计算`return!`表达式中调用。|
|`Run`|`M<'T> -> M<'T>` 或<br /><br />`M<'T> -> 'T`|执行计算表达式。|
|`Combine`|`M<'T> * M<'T> -> M<'T>` 或<br /><br />`M<unit> * M<'T> -> M<'T>`|调用计算表达式中的排序。|
|`For`|`seq<'T> * ('T -> M<'U>) -> M<'U>` 或<br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|在计算`for...do`表达式中调用表达式。|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|在计算`try...finally`表达式中调用表达式。|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|在计算`try...with`表达式中调用表达式。|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'T :> IDisposable`|在计算`use`表达式中调用绑定。|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|在计算`while...do`表达式中调用表达式。|
|`Yield`|`'T -> M<'T>`|在计算`yield`表达式中调用表达式。|
|`YieldFrom`|`M<'T> -> M<'T>`|在计算`yield!`表达式中调用表达式。|
|`Zero`|`unit -> M<'T>`|调用计算表达式`else`中的空`if...then`表达式分支。|
|`Quote`|`Quotations.Expr<'T> -> Quotations.Expr<'T>`|指示计算表达式作为引号传递给`Run`成员。 它将计算的所有实例转换为引号。|

生成器类中的许多方法使用并返回`M<'T>`构造，该构造通常是单独定义的类型，用于描述要组合的计算类型，例如，`Async<'T>`对于异步工作流和`Seq<'T>`序列工作流。 这些方法的签名使它们能够相互组合和嵌套，以便从一个构造返回的工作流对象可以传递给下一个构造。 编译器在解析计算表达式时，使用上表中的方法和计算表达式中的代码将表达式转换为一系列嵌套函数调用。

嵌套表达式的格式如下：

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

在上述代码中，如果计算表达式`Run`生成器`Delay`类中未定义对 和 的调用，则省略它们。 计算表达式的正文（此处表示为`{| cexpr |}`）通过下表中描述的翻译转换为涉及生成器类方法的调用。 计算表达式`{| cexpr |}`根据这些翻译以递归方式定义，其中`expr`是 F# 表达式，是`cexpr`计算表达式。

|表达式|翻译|
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

在上表中，`other-expr`描述表中未以其他方式列出的表达式。 生成器类不需要实现所有方法并支持上表中列出的所有翻译。 未实现的构造在该类型的计算表达式中不可用。 例如，如果不想在计算表达式中支持`use`关键字，则可以省略生成器类中的定义。 `Use`

下面的代码示例显示了一个计算表达式，该表达式将计算封装为一系列步骤，可以一次计算一个步骤。 受歧视的联合类型`OkOrException`， 编码表达式的错误状态，以计算到目前为止。 此代码演示了可在计算表达式中使用的几个典型模式，例如某些生成器方法的样板实现。

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

计算表达式具有基础类型，表达式返回该类型。 基础类型可能表示可以执行的计算结果或延迟计算，或者它可能提供一种通过某些类型的集合迭代的方法。 在前面的示例中，基础类型**为 最终**。 对于序列表达式，基础类型为<xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>。 对于查询表达式，基础类型为<xref:System.Linq.IQueryable?displayProperty=nameWithType>。 对于异步工作流，基础类型为[`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7)。 对象`Async`表示要执行的工作来计算结果。 例如，调用[`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b)以执行计算并返回结果。

## <a name="custom-operations"></a>自定义操作

可以在计算表达式上定义自定义操作，并在计算表达式中使用自定义操作作为运算符。 例如，可以在查询表达式中包括查询运算符。 定义自定义操作时，必须在计算表达式中定义"产量"和"For"方法。 要定义自定义操作，请将其放在计算表达式的生成器类中，然后应用 。 [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19) 此属性将字符串作为参数，它是要在自定义操作中使用的名称。 此名称在计算表达式的开头大括号开始时进入作用域。 因此，不应使用此块中与自定义操作同名的标识符。 例如，避免使用标识符（如`all`或`last`在查询表达式中）。

### <a name="extending-existing-builders-with-new-custom-operations"></a>使用新的自定义操作扩展现有生成器

如果您已经具有生成器类，则可以在此生成器类之外扩展其自定义操作。 必须在模块中声明扩展。 命名空间不能包含扩展成员，但在同一文件和定义该类型的同一命名空间声明组中除外。

下面的示例显示了现有`Microsoft.FSharp.Linq.QueryBuilder`类的扩展。

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member _.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a>另请参阅

- [F# 语言参考](index.md)
- [异步工作流](asynchronous-workflows.md)
- [序列](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)
- [查询表达式](query-expressions.md)
