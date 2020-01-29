---
title: F# 코딩 규칙
description: 编写F#代码时，请了解一般准则和惯例。
ms.date: 01/15/2020
ms.openlocfilehash: ca86bcf714d2fb4ee5f173ee54ba12c317f9abe7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737820"
---
# <a name="f-coding-conventions"></a>F# 코딩 규칙

以下约定是从使用大型F#基本代码的经验中制定的。 [好F#代码的五大原则](index.md#five-principles-of-good-f-code)是每个建议的基础。 它们与[ F#组件设计准则](component-design-guidelines.md)相关，但适用于任何F#代码，不仅仅是库等组件。

## <a name="organizing-code"></a>组织代码

F#提供两种主要方法来组织代码：模块和命名空间。 这与此类似，但有以下差异：

* 命名空间编译为 .NET 命名空间。 模块编译为静态类。
* 命名空间始终为顶级。 模块可以是顶级的，也可以嵌套在其他模块中。
* 命名空间可以跨多个文件。 模块不能。
* 可以通过 `[<RequireQualifiedAccess>]` 和 `[<AutoOpen>]`修饰模块。

以下准则将帮助你使用它们来组织你的代码。

### <a name="prefer-namespaces-at-the-top-level"></a>首选顶级命名空间

对于任何公开的可执行代码，命名空间优先于顶层的模块。 由于这些命名空间被编译为 .NET 命名空间，因此C#它们可从中利用，无问题。

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

仅从F#调用时，使用顶级模块可能不会出现差异，但是对于C#使用者来说，必须使用 `MyCode` 模块限定 `MyClass`。

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a>仔细应用 `[<AutoOpen>]`

`[<AutoOpen>]` 构造可以污染可供调用方使用的作用域，并且从何处获得答案是 "神奇的"。 这并不是件好事。 此规则的例外情况是F#核心库本身（尽管这种情况也有争议）。

但是，如果你想要从该公共 API 单独组织的公共 API 具有 helper 功能，则此功能非常方便。

```fsharp
module MyAPI =
    [<AutoOpen>]
    module private Helpers =
        let helper1 x y z =
            ...

    let myFunction1 x =
        let y = ...
        let z = ...

        helper1 x y z
```

这使你可以从函数的公共 API 中完全分离实现详细信息，而无需在每次调用时都对其进行完全限定。

此外，还可以在命名空间级别公开扩展方法和表达式生成器，以 `[<AutoOpen>]`。

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a>当名称可能发生冲突时使用 `[<RequireQualifiedAccess>]`，你觉得这有助于提高可读性

将 `[<RequireQualifiedAccess>]` 特性添加到模块指示可能未打开该模块，并且对该模块中的元素的引用需要显式限定访问权限。 例如，`Microsoft.FSharp.Collections.List` 模块具有此属性。

当模块中的函数和值有可能与其他模块中的名称冲突的名称时，这将非常有用。 要求限定访问权限可大大增加库的长期可维护性和可进化性。

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a>Sort `open` 语句界定闭合

在F#中，声明的顺序很重要，包括 `open` 语句。 这不同于C#，`using` 和 `using static` 的影响与文件中这些语句的排序无关。

在F#中，在范围中打开的元素可以隐藏已存在的其他元素。 这意味着重新排序 `open` 语句可能会改变代码的含义。 因此，不建议对所有 `open` 语句（例如 alphanumerically）进行任意排序，避免会生成您可能需要的不同行为。

相反，我们建议对它们进行排序[界定闭合](https://en.wikipedia.org/wiki/Topological_sorting);也就是说，按定义系统_层_的顺序对 `open` 语句排序。 还可以考虑在不同的拓扑层中执行字母数字排序。

例如，下面是针对F#编译器服务公共 API 文件的拓扑排序：

```fsharp
namespace Microsoft.FSharp.Compiler.SourceCodeServices

open System
open System.Collections.Generic
open System.Collections.Concurrent
open System.Diagnostics
open System.IO
open System.Reflection
open System.Text

open Microsoft.FSharp.Compiler
open Microsoft.FSharp.Compiler.AbstractIL
open Microsoft.FSharp.Compiler.AbstractIL.Diagnostics
open Microsoft.FSharp.Compiler.AbstractIL.IL
open Microsoft.FSharp.Compiler.AbstractIL.ILBinaryReader
open Microsoft.FSharp.Compiler.AbstractIL.Internal
open Microsoft.FSharp.Compiler.AbstractIL.Internal.Library

open Microsoft.FSharp.Compiler.AccessibilityLogic
open Microsoft.FSharp.Compiler.Ast
open Microsoft.FSharp.Compiler.CompileOps
open Microsoft.FSharp.Compiler.CompileOptions
open Microsoft.FSharp.Compiler.Driver
open Microsoft.FSharp.Compiler.ErrorLogger
open Microsoft.FSharp.Compiler.Infos
open Microsoft.FSharp.Compiler.InfoReader
open Microsoft.FSharp.Compiler.Lexhelp
open Microsoft.FSharp.Compiler.Layout
open Microsoft.FSharp.Compiler.Lib
open Microsoft.FSharp.Compiler.NameResolution
open Microsoft.FSharp.Compiler.PrettyNaming
open Microsoft.FSharp.Compiler.Parser
open Microsoft.FSharp.Compiler.Range
open Microsoft.FSharp.Compiler.Tast
open Microsoft.FSharp.Compiler.Tastops
open Microsoft.FSharp.Compiler.TcGlobals
open Microsoft.FSharp.Compiler.TypeChecker
open Microsoft.FSharp.Compiler.SourceCodeServices.SymbolHelpers

open Internal.Utilities
open Internal.Utilities.Collections
```

请注意，分行符分隔拓扑层，每个层将在 alphanumerically 之后进行排序。 这将完全组织代码，而不会意外地隐藏值。

## <a name="use-classes-to-contain-values-that-have-side-effects"></a>使用类来包含具有副作用的值

在许多情况下，初始化某个值可能会有副作用，如将上下文实例化到数据库或其他远程资源。 在模块中初始化此类东西并在后续函数中使用它非常有吸引力：

```fsharp
// This is bad!
module MyApi =
    let dep1 = File.ReadAllText "/Users/{your name}/connectionstring.txt"
    let dep2 = Environment.GetEnvironmentVariable "DEP_2"

    let private r = Random()
    let dep3() = r.Next() // Problematic if multiple threads use this

    let function1 arg = doStuffWith dep1 dep2 dep3 arg
    let function2 arg = doSutffWith dep1 dep2 dep3 arg
```

出于以下几个原因，这通常是一种不好的做法：

首先，将应用程序配置推送到带有 `dep1` 和 `dep2`的基本代码。 这在更大的基本代码中很难维护。

其次，静态初始化的数据不应包含不是线程安全的值（如果组件自身将使用多个线程）。 `dep3`清楚地违反了此情况。

最后，模块初始化为整个编译单元编译为静态构造函数。 如果在该模块中的 let 绑定值初始化中出现任何错误，则会将其视为一个 `TypeInitializationException`，然后在应用程序的整个生存期内对其进行缓存。 这可能很难诊断。 通常情况下，你可以尝试原因，但如果没有，则不会告诉根本原因是什么。

相反，只需使用简单的类来保存依赖项：

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member _.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member _.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

这会启用以下功能：

1. 将任何依赖状态推送到 API 自身之外。
2. 现在可以在 API 外完成配置。
3. 依赖值初始化中的错误不可能作为 `TypeInitializationException`清单。
4. API 现在更易于测试。

## <a name="error-management"></a>错误管理

大型系统中的错误管理是一项复杂且微妙的工作，在确保系统容错和行为良好的情况下没有任何银的项目符号。 以下准则应提供有关导航此困难空间的指导。

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a>表示域内部类型的错误事例和非法状态

利用可[区分联合](../language-reference/discriminated-unions.md)， F#可以在类型系统中表示有问题的程序状态。 예를 들면 다음과 같습니다.:

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

在这种情况下，有三种已知的方法可以取出银行帐户的资金。 每个错误事例均以类型表示，因而可在整个程序中安全地处理。

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

通常情况下，如果可以在域中对某些可能会**失败**的方法建模，则不再将错误处理代码视为除常规程序流之外必须处理的内容。 它只是正常程序流程的一部分，不被视为**例外**。 此操作主要有两个优点：

1. 随着域的不断变化，更易于维护。
2. 错误事例更易于进行单元测试。

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a>当错误无法用类型表示时使用异常

不是所有的错误都可以在问题域中表示。 这些类型的错误在本质上是不*例外*的，因此能够在中F#引发和捕获异常。

首先，建议您阅读[异常设计准则](../../standard/design-guidelines/exceptions.md)。 它们还适用于F#。

中F#可用于引发异常的主构造应按以下优先顺序考虑：

| 기능 | 구문 | 용도 |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | 使用指定的参数名引发 `System.ArgumentNullException`。 |
| `invalidArg` | `invalidArg "argumentName" "message"` | 使用指定的参数名称和消息引发 `System.ArgumentException`。 |
| `invalidOp` | `invalidOp "message"` | 使用指定的消息引发 `System.InvalidOperationException`。 |
|`raise`| `raise (ExceptionType("message"))` | 用于引发异常的通用机制。 |
| `failwith` | `failwith "message"` | 使用指定的消息引发 `System.Exception`。 |
| `failwithf` | `failwithf "format string" argForFormatString` | 使用由格式字符串及其输入确定的消息引发 `System.Exception`。 |

使用 `nullArg`、`invalidArg` 和 `invalidOp` 作为在适当的情况下引发 `ArgumentNullException`、`ArgumentException` 和 `InvalidOperationException` 的机制。

通常应避免使用 `failwith` 和 `failwithf` 函数，因为它们会引发基 `Exception` 类型，而不是特定异常。 根据[异常设计准则](../../standard/design-guidelines/exceptions.md)，你希望在可以时引发更具体的异常。

### <a name="using-exception-handling-syntax"></a>使用异常处理语法

F#通过 `try...with` 语法支持异常模式：

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

如果要使代码更清晰，则在面对具有模式匹配的异常时协调要执行的功能可能有点棘手。 处理此问题的一种方法是使用[活动模式](../language-reference/active-patterns.md)作为一种将错误情况的功能分组，并引发异常本身。 例如，你可能正在使用一个 API，该 API 在引发异常时，将有价值的信息包含在异常元数据中。 将有用的值解包到活动模式内捕获的异常的正文中，并在某些情况下返回该值会很有用。

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a>不要使用一元错误处理来替换异常

在函数编程中，异常会被视为有点 taboo。 事实上，例外违反了纯度，因此可以放心地将其视为不太有效。 但是，这会忽略必须运行代码的事实，并且可能会发生运行时错误。 一般情况下，编写代码假设大多数功能都既不是纯也不是总计，以最大程度减少意外的意外情况。

在 .NET 运行时和跨语言生态系统中，请务必考虑以下有关异常的核心优势/方面：

1. 它们包含详细的诊断信息，这在调试问题时非常有用。
2. 它们非常易于由运行时和其他 .NET 语言使用。
3. 与代码相比，在临时实现其语义的某些子集时，它们可以减少重大的样本，以*避免*异常。

这第三个要点非常重要。 对于重要复杂的操作，无法使用异常可能导致处理如下结构：

```fsharp
Result<Result<MyType, string>, string list>
```

这可以轻松地在 "stringly 类型" 错误上导致类似模式的代码，如模式匹配：

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

此外，在吞并返回 "更好" 类型的 "简单" 函数所需的任何异常时，可能会很有吸引力。

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

遗憾的是，`tryReadAllText` 可能会根据在文件系统上可能发生的许多事情引发许多异常，而此代码放弃了有关环境中实际出现错误的任何信息。 如果将此代码替换为结果类型，则返回 "stringly 类型" 错误消息分析：

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Ok
    with e -> Error e.Message

let r = tryReadAllText "path-to-file"
match r with
| Ok text -> ...
| Error e ->
    if e.Contains "uh oh, here we go again..." then ...
    else ...
```

然后，将异常对象本身放置在 `Error` 构造函数中，只会强制在调用站点（而非函数）正确处理异常类型。 这样做会有效地创建检查的异常，这是一项非常 unfun 的操作，可以作为 API 的调用方处理。

在上述示例中，一种很好的替代方法是捕获*特定*的异常，并在该异常的上下文中返回有意义的值。 如果按如下所述修改 `tryReadAllText` 函数，`None` 具有更多含义：

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

此函数现在会正确地处理找不到文件的情况，并将这种含义赋给返回，而不是作为全部捕获。 此返回值可以映射到该错误情况，同时不会丢弃任何上下文信息或强制调用方处理可能在代码中不相关的情况。

诸如 `Result<'Success, 'Error>` 之类的类型适用于不在其中嵌套的基本操作， F#可选类型适用于在某些情况下可能返回*内容*或不返回*任何*内容。 尽管它们不是异常的替代项，但不应在尝试替换异常时使用。 相反，它们应该谨慎地按目标方式处理异常和错误管理策略的特定方面。

## <a name="partial-application-and-point-free-programming"></a>部分应用和无点编程

F#支持部分应用程序，并因此使用各种方法来编程无点样式。 这对于模块内的代码重用或某些内容的实现非常有用，但它并不是公开公开的内容。 通常情况下，无点编程不是本身，也不能为不沉浸样式的人员添加重要认知障碍。

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a>不要在公共 Api 中使用部分应用程序和 currying

几乎不例外，在公共 Api 中使用部分应用程序可能会给使用者造成混淆。 通常，代码中F# `let`绑定值是**值**而不是**函数值**。 混合值和函数值可能会导致在 exchange 中保存少量的代码行，以实现很多认知开销，尤其是在与运算符（如 `>>` 结合使用以编写函数时）。

### <a name="consider-the-tooling-implications-for-point-free-programming"></a>考虑无点编程的工具含义

扩充函数不会标记其参数。 这会影响工具。 请考虑以下两个函数：

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

两者都是有效的函数，但 `funcWithApplication` 是一个扩充函数。 当你将鼠标悬停在编辑器中的类型上时，将看到以下内容：

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

在调用站点，工具（如 Visual Studio）中的工具提示将不会向你显示 `string` 和 `int` 输入类型实际表示的内容的有用信息。

如果遇到可公开使用的无点代码（如 `funcWithApplication`），则建议执行完全η的扩展，以便工具可以获取有意义的参数名称。

而且，如果不可能，调试无点代码可能会很难。 调试工具依赖于绑定到名称（例如 `let` 绑定）的值，以便您可以在执行中间检查中间值。 如果你的代码没有要检查的值，则没有要调试的内容。 将来，调试工具可以根据以前执行的路径来合成这些值，但不是最好地将您的匹配情况篱到*可能*的调试功能。

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a>考虑使用部分应用程序作为一项技术来减少内部样本

与前一个要点相比，部分应用程序是一种非常棒的工具，可用于减少应用程序内的样本或 API 的更深层次使用。 它对于实现更复杂的 Api 的单元测试非常有用，在这种情况下，样板通常是处理问题的难点。 例如，下面的代码演示了如何实现最模拟的框架，而无需对此类框架进行外部依赖并了解相关的订购 API。

例如，请考虑以下解决方案拓扑：

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

`ImplementationLogic.fsproj` 可能会公开如下代码：

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member _.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

`ImplementationLogic.Tests.fsproj` 中的单元测试 `Transactions.doTransaction` 很简单：

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

使用模拟上下文对象部分应用 `doTransaction`，可以在所有单元测试中调用函数，而无需每次都构造模拟上下文：

```fsharp
namespace TransactionTests

open Xunit
open TransactionTypes
open TransactionsTestingUtil
open TransactionsTestingUtil.TransactionsTestable

let testableContext =
    { new ITransactionContext with
        member _.TheFirstMember() = ...
        member _.TheSecondMember() = ... }

let transactionRoutine = getTestableTransactionRoutine testableContext

[<Fact>]
let ``Test withdrawal transaction with 0.0 for balance``() =
    let expected = ...
    let actual = transactionRoutine TransactionType.Withdraw 0.0
    Assert.Equal(expected, actual)
```

不应将此方法广泛应用于整个基本代码，但这是减少复杂内部和这些内部测试单元的样本的好办法。

## <a name="access-control"></a>액세스 제어

F#具有多个用于[访问控制](../language-reference/access-control.md)的选项，这些选项是从 .net 运行时中的可用项继承而来的。 这些类型不仅可用于类型，还可以将它们用于函数。

* 首选非`public` 类型和成员，直到你需要它们可公开使用。 这还可以最大程度地减少使用者。
* 努力保持所有帮助程序功能 `private`。
* 如果在 helper 函数的私有模块上使用 `[<AutoOpen>]`，请考虑使用这些功能。

## <a name="type-inference-and-generics"></a>类型推理和泛型

类型推理可以省去您键入大量样板。 编译器中的F#自动泛化可帮助你编写更通用的代码，几乎不需要额外的工作。 不过，这些功能并不是普遍适用的。

* 考虑在公共 Api 中用显式类型标记参数名称，并且不要依赖于此的类型推理。

    原因在于，**您**应该控制 API 的形状，而不是编译器的形式。 尽管编译器可以在推断类型时执行精细作业，但是，如果它依赖的内部机制已更改类型，则可能会更改 API 的形状。 这可能是你想要的，但几乎肯定会导致下游使用者需要处理的重大 API 更改。 相反，如果你显式控制公共 API 的形状，则可以控制这些重大更改。 在 DDD 术语中，这可以被视为反损坏层。

* 请考虑为泛型参数提供有意义的名称。

    除非您正在编写不特定于特定域的真正的泛型代码，否则，有意义的名称可以帮助其他程序员了解他们所使用的域。 例如，在与文档数据库交互的上下文中，名为 `'Document` 的类型参数使你可以更清楚地了解你正在使用的函数或成员可以接受的通用文档类型。

* 考虑将泛型类型参数命名为 PascalCase。

    这是在 .NET 中执行操作的常规方法，因此建议使用 PascalCase，而不是 snake_case 或 camelCase。

最后，对于新的F#或大的基本代码，自动通用化并非始终是 boon 的。 使用通用组件时存在认知开销。 此外，如果自动通用化的函数不用于不同的输入类型（如果打算将其用作这样的类型），则这些函数在该时间点是泛型的。 如果要编写的代码实际上是泛型的，则应始终考虑。

## <a name="performance"></a>성능

### <a name="prefer-structs-for-small-data-types"></a>更倾向于小型数据类型的结构

使用结构（也称为值类型）通常可以提高某些代码的性能，因为这通常会避免分配对象。 但结构并不总是 "更快" 按钮：如果结构中的数据大小超过16个字节，则复制数据通常会导致比使用引用类型更多的 CPU 时间。

若要确定是否应使用结构，请考虑以下情况：

- 如果数据的大小为16字节或更小。
- 如果有很多这样的数据类型存在于正在运行的程序中的内存中。

如果第一个条件适用，则通常应使用结构。 如果这两个均适用，则几乎始终使用结构。 在某些情况下，上述条件适用，但使用结构并不比使用引用类型更好或更糟，但这种情况很少发生。 但一定要在进行更改时始终度量，而不是在假设或直觉上操作。

#### <a name="prefer-struct-tuples-when-grouping-small-value-types"></a>分组小值类型时首选结构元组

请考虑以下两个函数：

```fsharp
let rec runWithTuple t offset times =
    let offsetValues x y z offset =
        (x + offset, y + offset, z + offset)

    if times <= 0 then
        t
    else
        let (x, y, z) = t
        let r = offsetValues x y z offset
        runWithTuple r offset (times - 1)

let rec runWithStructTuple t offset times =
    let offsetValues x y z offset =
        struct(x + offset, y + offset, z + offset)

    if times <= 0 then
        t
    else
        let struct(x, y, z) = t
        let r = offsetValues x y z offset
        runWithStructTuple r offset (times - 1)
```

当使用[BenchmarkDotNet](https://benchmarkdotnet.org/)等统计基准工具来对这些函数进行基准测试时，会发现使用结构元组的 `runWithStructTuple` 函数的运行速度40%，并且不会分配内存。

不过，这些结果在您自己的代码中并不总是如此。 如果将某个函数标记为 `inline`，则使用引用元组的代码可能会获得一些额外的优化，否则，将分配的代码只需进行优化即可。 应始终在性能考虑时测量结果，而永远不会根据假设或直觉来操作结果。

#### <a name="prefer-struct-records-when-the-data-type-is-small"></a>当数据类型为小型时，首选结构记录

前面所述的经验法则也包含在[ F#记录类型](../language-reference/records.md)中。 请考虑以下数据类型和处理这些数据类型的函数：

```fsharp
type Point = { X: float; Y: float; Z: float }

[<Struct>]
type SPoint = { X: float; Y: float; Z: float }

let rec processPoint (p: Point) offset times =
    let inline offsetValues (p: Point) offset =
        { p with X = p.X + offset; Y = p.Y + offset; Z = p.Z + offset }

    if times <= 0 then
        p
    else
        let r = offsetValues p offset
        processPoint r offset (times - 1)

let rec processStructPoint (p: SPoint) offset times =
    let inline offsetValues (p: SPoint) offset =
        { p with X = p.X + offset; Y = p.Y + offset; Z = p.Z + offset }

    if times <= 0 then
        p
    else
        let r = offsetValues p offset
        processStructPoint r offset (times - 1)
```

这类似于以前的元组代码，但这次此示例使用记录和内联的内部函数。

当使用[BenchmarkDotNet](https://benchmarkdotnet.org/)等统计基准工具对这些函数进行基准测试时，会发现 `processStructPoint` 的运行速度几乎60%，并且不会在托管堆上分配任何内容。

#### <a name="prefer-struct-discriminated-unions-when-the-data-type-is-small"></a>当数据类型为小时，首选结构可区分联合

前面对结构元组和记录的性能的观测值还适用于[ F#可区分联合](../language-reference/discriminated-unions.md)。 다음 코드를 살펴보세요.

```fsharp
    type Name = Name of string
    
    [<Struct>]
    type SName = SName of string

    let reverseName (Name s) =
        s.ToCharArray()
        |> Array.rev
        |> string
        |> Name

    let structReverseName (SName s) =
        s.ToCharArray()
        |> Array.rev
        |> string
        |> SName
```

通常为域建模定义单一用例可区分的联合。 当你使用[BenchmarkDotNet](https://benchmarkdotnet.org/)等统计基准工具来基准这些函数时，你会发现 `structReverseName` 比 `reverseName` 小字符串的速度要快25%。 对于大型字符串，这两个方法都执行相同的。 因此，在这种情况下，最好使用结构。 如前文所述，请始终度量，而不是在假设或直觉上操作。

尽管上面的示例演示了结构可区分联合生成了更好的性能，但在对域进行建模时，有一个很常见的可区分联合。 更大的数据类型（如这样的数据类型）可能不会执行，因为这些数据类型取决于其结构，因为这样做可能会涉及更多的复制操作。

### <a name="functional-programming-and-mutation"></a>函数编程和变化

F#默认情况下，值是不可变的，这使你可以避免某些类 bug （尤其是涉及并发和并行的类）。 但是，在某些情况下，为了实现执行时间或内存分配的最佳（甚至合理）的效率，可以通过使用状态的就地转变来最佳地实现一段工作量。 这可以通过F#使用 `mutable` 关键字来选择。

在中F#使用 `mutable` 可能会受到功能纯度的干扰。 这是可理解的，但任何位置的功能纯度都有可能与性能目标相同。 一种折衷是封装变化，使调用方不必关心调用函数时所发生的情况。 这样，便可以在性能关键代码的基于变化的实现上编写功能接口。

#### <a name="wrap-mutable-code-in-immutable-interfaces"></a>在不可变接口中包装可变代码

使用引用透明度作为目标，编写不公开性能关键函数的可变 underbelly 的代码至关重要。 例如，下面的代码实现F#核心库中的 `Array.contains` 函数：

```fsharp
[<CompiledName("Contains")>]
let inline contains value (array:'T[]) =
    checkNonNull "array" array
    let mutable state = false
    let mutable i = 0
    while not state && i < array.Length do
        state <- value = array.[i]
        i <- i + 1
    state
```

多次调用此函数不会更改基础数组，也不需要您维护任何使用它的可变状态。 尽管几乎每个代码行都使用变化，但它是引用的。

#### <a name="consider-encapsulating-mutable-data-in-classes"></a>考虑在类中封装可变数据

前面的示例使用了一个函数来封装使用可变数据的操作。 对于更复杂的数据集，这并不总是足够的。 请考虑以下几组函数：

```fsharp
open System.Collections.Generic

let addToClosureTable (key, value) (t: Dictionary<_,_>) =
    if not (t.ContainsKey(key)) then
        t.Add(key, value)
    else
        t.[key] <- value

let closureTableCount (t: Dictionary<_,_>) = t.Count

let closureTableContains (key, value) (t: Dictionary<_, HashSet<_>>) =
    match t.TryGetValue(key) with
    | (true, v) -> v.Equals(value)
    | (false, _) -> false
```

此代码具有高性能，但它公开了调用方负责维护的基于变化的数据结构。 这可以包装在类的内部，没有可更改的基础成员：

```fsharp
open System.Collections.Generic

/// The results of computing the LALR(1) closure of an LR(0) kernel
type Closure1Table() =
    let t = Dictionary<Item0, HashSet<TerminalIndex>>()

    member _.Add(key, value) =
        if not (t.ContainsKey(key)) then
            t.Add(key, value)
        else
            t.[key] <- value

    member _.Count = t.Count

    member _.Contains(key, value) =
        match t.TryGetValue(key) with
        | (true, v) -> v.Equals(value)
        | (false, _) -> false
```

`Closure1Table` 封装基于变化的基础数据结构，因此不强制调用方维护基础数据结构。 类是一种强大的方法，用于封装基于变化的数据和例程，而不会向调用方公开详细信息。

#### <a name="prefer-let-mutable-to-reference-cells"></a>首选 `let mutable` 引用单元格

引用单元是表示对值（而不是值本身）的引用的一种方法。 尽管它们可用于性能关键代码，但不建议这样做。 다음 예제를 참조하세요.

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

现在，使用引用单元格 "pollutes" 的所有后续代码都必须取消引用并重新引用基础数据。 相反，请考虑 `let mutable`：

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

除了 lambda 表达式中间的单点变化外，接触 `acc` 的所有其他代码都可以通过与正常的 `let`绑定不可变值的使用不相同的方式来实现此目的。 这可以更轻松地随时间推移而变化。

## <a name="object-programming"></a>对象编程

F#完全支持对象和面向对象的（OO）概念。 尽管许多 OO 概念非常强大且有用，但并非所有这些概念都是理想使用。 以下列表提供了有关高级别 OO 功能的指南。

**在许多情况下，请考虑使用这些功能：**

* 点表示法（`x.Length`）
* 实例成员
* 隐式构造函数
* 정적 멤버
* 索引器表示法（`arr.[x]`）
* 命名参数和可选参数
* 接口和接口实现

**不要首先接触这些功能，但在解决问题时，请慎用这些功能：**

* 메서드 오버로드
* 封装的可变数据
* 类型上的运算符
* 自动属性
* 实现 `IDisposable` 和 `IEnumerable`
* 类型扩展
* 이벤트
* Structs
* 대리자
* 열거형

**通常，请避免使用这些功能，除非您必须使用这些功能：**

* 基于继承的类型层次结构和实现继承
* Null 和 `Unchecked.defaultof<_>`

### <a name="prefer-composition-over-inheritance"></a>优先使用继承

[继承性之上的组合](https://en.wikipedia.org/wiki/Composition_over_inheritance)是一种长期可供使用F#的代码。 基本原则是，不应公开基类并强制调用方从该基类继承以获得功能。

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a>如果不需要类，请使用对象表达式来实现接口

[对象表达式](../language-reference/object-expressions.md)允许您动态实现接口，将实现的接口绑定到一个值，而无需在类中执行此操作。 这非常方便，尤其是在_只_需要实现接口且无需完整类的情况下。

例如，如果添加了一个没有 `open` 语句的符号，则在[ionide 入门](http://ionide.io/)中运行的代码可提供代码修复操作：

```fsharp
    let private createProvider () =
        { new CodeActionProvider with
            member this.provideCodeActions(doc, range, context, ct) =
                let diagnostics = context.diagnostics
                let diagnostic = diagnostics |> Seq.tryFind (fun d -> d.message.Contains "Unused open statement")
                let res =
                    match diagnostic with
                    | None -> [||]
                    | Some d ->
                        let line = doc.lineAt d.range.start.line
                        let cmd = createEmpty<Command>
                        cmd.title <- "Remove unused open"
                        cmd.command <- "fsharp.unusedOpenFix"
                        cmd.arguments <- Some ([| doc |> unbox; line.range |> unbox; |] |> ResizeArray)
                        [|cmd |]
                res
                |> ResizeArray
                |> U2.Case1
        }
```

由于与 Visual Studio Code API 交互时不需要类，因此对象表达式是适用于此的理想工具。 如果要以即席方式使用测试例程来围绕某个接口，则它们对于单元测试也很有用。

## <a name="consider-type-abbreviations-to-shorten-signatures"></a>考虑键入缩写以缩短签名

[类型缩写](../language-reference/type-abbreviations.md)是将标签分配给其他类型的一种简便方法，例如函数签名或更复杂的类型。 例如，以下别名为使用[CNTK](https://docs.microsoft.com/cognitive-toolkit/)（深度学习库）定义计算所需的内容分配一个标签：

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

`Computation` 名称是一种方便的方法，用于表示与它所别名的签名相匹配的任何函数。 使用类似于这样的类型缩写词是非常方便的，可实现更简洁的代码。

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a>避免使用类型缩写来表示域

尽管类型缩写词在为函数签名提供名称时很方便，但在 abbreviating 其他类型时可能会造成混淆。 请考虑此缩写：

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

这可能会造成混淆：

* `BufferSize` 不是抽象;它只是一个整数的另一个名称。
* 如果 `BufferSize` 在公共 API 中公开，则可以轻松地对其进行误解，使其只是 `int`。 通常，域类型具有多个属性，而不是基元类型，如 `int`。 此缩写违反了假设。
* `BufferSize` 的大小写（PascalCase）表示此类型包含更多数据。
* 与为函数提供命名参数相比，此别名不会提高清晰度。
* 缩写词不会在编译的 IL 中列出;它只是一个整数，而此别名是编译时构造。

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) = ...
```

总而言之，类型缩写的缺陷在于它们**不**是其所 abbreviating 的类型的抽象。 在上面的示例中，`BufferSize` 只是覆盖下的 `int`，不包含任何其他数据，也不包括 `int` 已有的任何权益。

使用类型缩写来表示域的另一种方法是使用单个用例可区分联合。 前面的示例可以建模，如下所示：

```fsharp
type BufferSize = BufferSize of int
```

如果你编写的代码在 `BufferSize` 及其基础值的基础上运行，则需要构造一个，而不是传入任意整数：

```fsharp
module Networking =
    ...
    let send data (BufferSize size) =
    ...
```

这会减少错误地将任意整数传递到 `send` 函数的可能性，因为调用方必须构造 `BufferSize` 类型以在调用函数之前包装值。
