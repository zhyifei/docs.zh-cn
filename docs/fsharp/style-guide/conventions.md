---
title: F# 编码约定
description: 编写 F# 代码时，请学习一般准则和习语。
ms.date: 01/15/2020
ms.openlocfilehash: 7266211e501bdb52564220781e2347d1aceaf296
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401147"
---
# <a name="f-coding-conventions"></a>F# 编码约定

以下约定是从使用大型 F# 代码库的经验中制定的。 [好的 F# 代码的五个原则](index.md#five-principles-of-good-f-code)是每个建议的基础。 它们与[F# 组件设计指南](component-design-guidelines.md)相关，但适用于任何 F# 代码，而不仅仅是库等组件。

## <a name="organizing-code"></a>组织代码

F# 具有两种组织代码的主要方法：模块和命名空间。 这些相似，但确实有以下差异：

* 命名空间编译为 .NET 命名空间。 模块编译为静态类。
* 命名空间始终是顶层。 模块可以是顶级的，可以嵌套在其他模块中。
* 命名空间可以跨多个文件。 模块不能。
* 模块可以使用`[<RequireQualifiedAccess>]`和`[<AutoOpen>]`进行修饰。

以下指南将帮助您使用这些准则来组织代码。

### <a name="prefer-namespaces-at-the-top-level"></a>首选顶层的命名空间

对于任何公共易用代码，命名空间优先支持顶层模块。 因为它们编译为 .NET 命名空间，因此它们可消耗来自 C#，没有问题。

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

仅从 F# 调用时，使用顶级模块可能看起来不同，但对于 C# 使用者，调用方可能会因为必须符合`MyClass``MyCode`该模块的资格而感到惊讶。

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a>小心涂抹`[<AutoOpen>]`

构造`[<AutoOpen>]`会污染调用方可用的范围，而对事物来源的答案是"神奇"。 这不是一件好事。 此规则的一个例外是 F# 核心库本身（尽管这一事实也有点争议）。

但是，如果您具有公共 API 的帮助器功能，您希望独立于该公共 API 进行组织，则这样做会很方便。

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

这样，您就可以将实现详细信息与函数的公共 API 进行干净分离，而无需在每次调用帮助程序时完全限定帮助程序。

此外，在命名空间级别公开扩展方法和表达式生成器可以使用 整齐地表示。 `[<AutoOpen>]`

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a>每当`[<RequireQualifiedAccess>]`名称可能发生冲突或您觉得它有助于可读性时使用

将`[<RequireQualifiedAccess>]`属性添加到模块表示可能无法打开模块，并且对模块元素的引用需要显式限定访问。 例如，`Microsoft.FSharp.Collections.List`模块具有此属性。

当模块中的函数和值具有可能与其他模块中的名称冲突的名称时，这非常有用。 要求合格的访问可以大大提高库的长期可维护性和可进化性。

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a>从`open`拓扑上对语句进行排序

在 F#中，声明的顺序很重要，包括与语句一`open`起。 这与 C# 不同，C#`using``using static`的影响与文件中这些语句的顺序无关。

在 F# 中，打开到作用域中的元素可能会隐藏其他已经存在的元素。 这意味着重新排序`open`语句可能会更改代码的含义。 因此，不建议对所有`open`语句进行任何任意排序（例如，以 alpha 数字方式排序），以免生成您可能期望的不同行为。

相反，我们建议您[按拓扑分类](https://en.wikipedia.org/wiki/Topological_sorting)它们;也就是说，按定义系统`open`_图层_的顺序对语句进行排序。 也可以考虑在不同的拓扑层内进行字母数字排序。

例如，下面是 F# 编译器服务公共 API 文件的拓扑排序：

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

请注意，换行符将拓扑图层分开，之后将按字母数字对每一层进行排序。 这样可以干净地组织代码，而不会意外地隐藏值。

## <a name="use-classes-to-contain-values-that-have-side-effects"></a>使用类包含具有副作用的值

初始化值很多时候会产生副作用，例如将上下文实例化到数据库或其他远程资源。 在模块中初始化此类内容并将其用于后续函数是很有诱惑力的：

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

由于几个原因，这通常是一个坏主意：

首先，应用程序配置被推送到 代码库中`dep1`， `dep2` 这在较大的代码库中很难维护。

其次，静态初始化数据不应包括不安全的线程值（如果组件本身将使用多个线程）。 这显然被`dep3`违反。

最后，模块初始化编译为整个编译单元的静态构造函数。 如果该模块中的允许绑定值初始化中出现任何错误，则该初始化将表现为`TypeInitializationException`然后缓存整个应用程序的生存期。 这可能很难诊断。 通常有一个内部异常，你可以尝试推理，但如果没有，那么没有告诉根本原因是什么。

相反，只需使用简单类来保存依赖项：

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member _.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member _.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

这支持以下功能：

1. 将任何从属状态推送到 API 本身之外。
2. 配置现在可以在 API 之外完成。
3. 从属值的初始化错误不太可能表现为`TypeInitializationException`。
4. API 现在更易于测试。

## <a name="error-management"></a>错误管理

大型系统中的错误管理是一项复杂而细致的工作，在确保系统具有容错性和良好行为方面没有银弹。 以下指南应为导航此困难空间提供指导。

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a>在域固有的类型中表示错误案例和非法状态

使用["歧视联合"，F#](../language-reference/discriminated-unions.md)使您能够在类型系统中表示错误的程序状态。 例如：

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

在这种情况下，有三种已知方式从银行帐户提取资金可能会失败。 每个错误案例都以类型表示，因此可以在整个程序中安全地处理。

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

通常，如果可以对域中某些内容可能**失败**的不同方式进行建模，则错误处理代码不再被视为除常规程序流之外必须处理的内容。 它只是正常程序流的一部分，不被认为是**例外**。 这有两个主要好处：

1. 随着域随时间的变化而更易于维护。
2. 错误案例更易于单元测试。

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a>当无法用类型表示错误时，请使用异常

并非所有错误都可以在问题域中表示。 这些类型的故障在性质上*是例外*的，因此能够提高和捕获 F# 中的异常。

首先，建议您阅读[例外设计指南](../../standard/design-guidelines/exceptions.md)。 这些也适用于 F#。

F# 中用于引发异常的主要构造应考虑以下首选项顺序：

| 函数 | 语法 | 目的 |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | 使用指定的`System.ArgumentNullException`参数名称引发 a。 |
| `invalidArg` | `invalidArg "argumentName" "message"` | 使用指定的`System.ArgumentException`参数名称和消息引发 。 |
| `invalidOp` | `invalidOp "message"` | 使用指定`System.InvalidOperationException`的消息引发 a。 |
|`raise`| `raise (ExceptionType("message"))` | 用于引发异常的通用机制。 |
| `failwith` | `failwith "message"` | 使用指定`System.Exception`的消息引发 a。 |
| `failwithf` | `failwithf "format string" argForFormatString` | 使用格式`System.Exception`字符串及其输入确定的消息引发 。 |

使用`nullArg` `invalidArg` ，`invalidOp`并作为投掷`ArgumentNullException`的机制，`ArgumentException`并在`InvalidOperationException`适当时使用 。

通常`failwith`应避免`failwithf`和 函数，因为它们会引发基`Exception`类型，而不是特定的异常。 根据[例外设计指南](../../standard/design-guidelines/exceptions.md)，您希望在可以时提出更具体的异常。

### <a name="using-exception-handling-syntax"></a>使用异常处理语法

F# 通过`try...with`语法支持异常模式：

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

如果要保持代码整洁，在面对模式匹配的异常时要执行的功能可能会有点棘手。 处理这种情况的一种方法是使用[活动模式](../language-reference/active-patterns.md)作为将围绕错误案例的功能分组具有异常本身的方法。 例如，您可能正在使用 API，当它引发异常时，该 API 会将有价值的信息包含在异常元数据中。 在某些情况下，在活动模式内展开捕获的异常正文中的有用值并返回该值可能会有所帮助。

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a>请勿使用单体错误处理来替换异常

异常在函数式编程中被视为一些禁忌。 事实上，异常会侵犯纯度，因此可以放心地考虑它们不太有效。 但是，这忽略了代码必须运行的位置，并且可能发生运行时错误。 通常，编写代码时假定大多数事物既不是纯的也不是完全的，以尽量减少令人不快的意外。

在 .NET 运行时和整个跨语言生态系统中的相关性和适当性方面，必须考虑异常的以下核心优势/方面：

1. 它们包含详细的诊断信息，这在调试问题时非常有用。
2. 运行时和其他 .NET 语言都很好地理解它们。
3. 与通过临时实现语义的某些子集来*避免*异常的代码相比，它们可以减少重要的样板。

第三点至关重要。 对于不处理非大型复杂操作，不使用异常可能会导致处理这样的结构：

```fsharp
Result<Result<MyType, string>, string list>
```

这很容易导致脆弱的代码，如模式匹配的"字符串类型"错误：

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

此外，对于返回"更好"类型的"简单"函数的渴望，可以接受任何异常是很有诱惑力的：

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

遗憾的是，`tryReadAllText`可以基于文件系统上可能发生的无数事情引发大量异常，并且此代码会丢弃有关环境中实际出错的任何信息。 如果使用此代码类型替换此代码，则返回"字符串键入"错误消息分析：

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

将异常对象本身放在构造函数中`Error`只会强制您在调用站点而不是函数中正确处理异常类型。 这样做可以有效地创建已检查的异常，这些异常作为 API 的调用方处理起来非常不有趣。

上述示例的一个很好的替代方法是在该异常上下文中捕获*特定*异常并返回有意义的值。 如果修改函数`tryReadAllText`如下所示，`None`则具有更多含义：

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

现在，当找不到文件并将该含义分配给返回时，此函数将正确处理案例，而不是充当"全部捕获"功能。 此返回值可以映射到该错误情况，同时不会放弃任何上下文信息或强制调用方处理代码中此时可能不相关的案例。

类型（如`Result<'Success, 'Error>`适用于未嵌套的基本操作）和 F# 可选类型非常适合表示某些内容可以返回*或**什么都不*返回时。 但是，它们不是异常的替换，不应用于尝试替换异常。 相反，应明智地应用它们，以有针对性的方式处理异常和错误管理政策的具体方面。

## <a name="partial-application-and-point-free-programming"></a>部分应用和无点编程

F# 支持部分应用程序，因此，以各种方式以无点样式进行编程。 这有利于模块内的代码重用或某些内容的实现，但这不是公开的内容。 一般来说，无点编程本身并不是一种美德，它可以为不沉浸于这种风格的人增加一个重大的认知障碍。

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a>请勿在公共 API 中使用部分应用程序和咖喱

除了很少的情况外，在公共 API 中使用部分应用程序可能会令使用者感到困惑。 通常，F#`let`代码中的绑定值是**值**，而不是**函数值**。 将值和函数值混合在一起可以节省少量代码行，以换取相当多的认知开销，特别是如果与组合函数等`>>`运算符结合使用时。

### <a name="consider-the-tooling-implications-for-point-free-programming"></a>考虑无点编程的工具含义

库瑞德函数不标记其参数。 这具有工具含义。 请考虑以下两个函数：

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

两者都是有效的函数，`funcWithApplication`但都是一个咖喱函数。 当您在编辑器中悬停在它们的类型上时，您将看到：

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

在呼叫站点，Visual Studio 等工具工具提示不会为您提供有关`string`和`int`输入类型实际表示的内容的有意义的信息。

如果您遇到这样的`funcWithApplication`无点代码是公共易用的，建议执行完全 +扩展，以便工具可以获取有意义的参数名称。

此外，调试无点代码可能具有挑战性，如果不是不可能的话。 调试工具依赖于绑定到名称的值（例如绑定`let`），以便在执行中途检查中间值。 当代码没有要检查的值时，将没有任何要调试的值。 将来，调试工具可能会根据以前执行的路径来合成这些值，但最好对*潜在的*调试功能进行对冲。

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a>将部分应用视为减少内部样板的技术

与前一点不同，部分应用程序是减少应用程序内部的样板或 API 的深层内部的绝妙工具。 对于单元测试更复杂的 API 的实现很有帮助，其中样板通常需要处理。 例如，以下代码演示如何完成大多数模拟框架所赋予您的内容，而无需对此类框架进行外部依赖，并且必须学习相关的定制 API。

例如，请考虑以下解决方案地形：

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

`ImplementationLogic.fsproj`可能会公开代码，例如：

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member _.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

单元`ImplementationLogic.Tests.fsproj`测试`Transactions.doTransaction`非常简单：

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

使用模拟`doTransaction`上下文对象进行部分应用允许您在所有单元测试中调用函数，而无需每次都构造模拟上下文：

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

此技术不应普遍应用于整个代码库，但它是减少复杂内部和单元测试这些内部的样板的好方法。

## <a name="access-control"></a>访问控制

F# 具有多个[访问控制](../language-reference/access-control.md)选项，从 .NET 运行时中可用的选项继承。 这些不仅可用于类型 - 您也可以将它们用于函数。

* 首选非`public`类型和成员，直到您需要它们是公共消耗品。 这也最大限度地减少了消费者对之的耦合。
* 努力保持所有帮助器的功能`private`。
* 请考虑在帮助器`[<AutoOpen>]`函数的专用模块上使用这些函数（如果它们变为大量）。

## <a name="type-inference-and-generics"></a>类型推理和泛型

类型推理可以节省您输入大量样板。 F# 编译器中的自动泛化可以帮助您编写更通用的代码，而您几乎不需要额外的工作。 但是，这些功能并非普遍良好。

* 请考虑在公共 API 中标记具有显式类型的参数名称，并且不要为此依赖类型推断。

    原因是**您应该**控制 API 的形状，而不是编译器。 尽管编译器可以出色地推断类型，但如果它所依赖的内部类型已更改，则 API 的形状可能会发生变化。 这可能是你想要的，但它几乎肯定会导致一个突破的API更改，然后下游使用者将不得不处理。 相反，如果您显式控制公共 API 的形状，则可以控制这些重大更改。 用 DDD 术语来说，这可以被视为反腐败层。

* 请考虑为泛型参数指定一个有意义的名称。

    除非您正在编写不特定于特定域的真正通用代码，否则有意义的名称可以帮助其他程序员了解他们正在处理的域。 例如，在与文档数据库交互的`'Document`上下文中命名的类型参数使正在使用的函数或成员可以接受通用文档类型更加清晰。

* 请考虑使用 PascalCase 命名泛型类型参数。

    这是在 .NET 中执行操作的一般方法，因此建议您使用 PascalCase 而不是snake_case或骆驼Case。

最后，对于 F# 或大型代码库的新增人员而言，自动泛化并不总是一个福音。 使用通用组件存在认知开销。 此外，如果自动通用化函数不用于不同的输入类型（更不用说它们打算用作此类函数），那么在那个时间点，它们是泛型函数没有实际的好处。 始终考虑您编写的代码是否实际上将受益于泛型。

## <a name="performance"></a>性能

### <a name="prefer-structs-for-small-data-types"></a>首选小型数据类型的结构

使用结构（也称为值类型）通常会导致某些代码的性能更高，因为它通常避免分配对象。 但是，结构并不总是一个"更快"按钮：如果结构中的数据大小超过 16 个字节，则复制数据通常会导致比使用引用类型花费更多的 CPU 时间。

要确定是否应使用结构，请考虑以下条件：

- 如果数据的大小为 16 字节或更小。
- 如果运行程序中的内存中可能有许多此类数据类型驻留在内存中。

如果应用第一个条件，通常应使用结构。 如果两者都适用，您几乎总是应该使用结构。 可能在某些情况下，应用前面的条件，但使用结构并不比使用引用类型更好或更差，但它们可能很少见。 但是，在进行这样的更改时，始终要衡量，而不是根据假设或直觉行事，这一点很重要。

#### <a name="prefer-struct-tuples-when-grouping-small-value-types"></a>在分组小值类型时，首选结构组合

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

当您使用基准数据测试工具（如[基准点网](https://benchmarkdotnet.org/)）对这些函数进行基准测试时，您会发现使用`runWithStructTuple`结构元数的函数运行速度要快 40%，并且不分配内存。

但是，这些结果并不总是在您自己的代码中如此。 如果将函数标记为`inline`，使用参考元数的代码可能会获得一些额外的优化，或者分配的代码可以简单地进行优化。 您应该始终在绩效方面衡量结果，并且绝不基于假设或直觉操作。

#### <a name="prefer-struct-records-when-the-data-type-is-small"></a>数据类型较小时更喜欢结构记录

前面描述的经验法则也适用于[F# 记录类型](../language-reference/records.md)。 请考虑处理它们的以下数据类型和函数：

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

这与前面的元组代码类似，但这次示例使用记录和内联内部函数。

当您使用基准数据测试工具（如[基准点网](https://benchmarkdotnet.org/)）对这些函数进行基准测试时，您会发现`processStructPoint`运行速度接近 60%，并且在托管堆上不分配任何内容。

#### <a name="prefer-struct-discriminated-unions-when-the-data-type-is-small"></a>在数据类型较小时，首选结构区分结合

以前关于具有结构元数和记录的表现的观察也适用于[F_ 歧视联盟](../language-reference/discriminated-unions.md)。 考虑下列代码：

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

为域建模定义像这样的单一案例"歧视联合"很常见。 当您使用基准数据测试工具（如[基准点网](https://benchmarkdotnet.org/)）对这些函数进行基准测试时，您会发现`structReverseName`运行速度比`reverseName`小字符串快 25%。 对于大字符串，两者执行大致相同。 因此，在这种情况下，最好使用结构。 如前所述，始终根据假设或直觉进行测量和操作。

尽管前面的示例显示结构歧视联合产生了更好的性能，但建模域时通常具有较大的"歧视联合"。 如果较大的数据类型根据它们的操作进行结构，则它们可能无法很好地执行，因为可能涉及更多的复制。

### <a name="functional-programming-and-mutation"></a>函数编程和突变

默认情况下，F# 值是不可变的，这允许您避免某些类 bug（尤其是涉及并发和并行性的错误类）。 但是，在某些情况下，为了实现执行时间或内存分配的最佳（甚至合理）效率，最好使用就地状态突变来实现工作跨度。 这在选择加入的基础上是可能的，F# 与`mutable`关键字。

`mutable`在 F# 中使用可能会感觉与功能纯度不一致。 这是可以理解的，但无处不在的功能纯度可能与性能目标相悖。 一种妥协是封装突变，这样调用方就不必关心调用函数时会发生什么。 这允许您通过基于突变的实现为性能关键代码编写功能接口。

#### <a name="wrap-mutable-code-in-immutable-interfaces"></a>在不可变接口中包装可变代码

以参考透明度为目标，编写不公开性能关键函数可变下层代码至关重要。 例如，以下代码在`Array.contains`F# 核心库中实现函数：

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

多次调用此函数不会更改基础数组，也不要求您在使用该函数时保持任何可变状态。 它具有参考性透明，即使其中几乎每行代码都使用突变。

#### <a name="consider-encapsulating-mutable-data-in-classes"></a>考虑在类中封装可变数据

前面的示例使用单个函数来使用可变数据封装操作。 对于更复杂的数据集，这并不总是足够。 请考虑以下函数集：

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

此代码是执行的，但它公开调用方负责维护的基于突变的数据结构。 这可以包装在类中，而没有可以更改的基础成员：

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

`Closure1Table`封装基于突变的基础数据结构，从而不强制调用方维护基础数据结构。 类是封装基于突变的数据和例程而不向调用方公开详细信息的强大方法。

#### <a name="prefer-let-mutable-to-reference-cells"></a>更喜欢`let mutable`引用单元格

引用单元格是表示对值的引用而不是值本身的一种方式。 尽管它们可用于性能关键型代码，但不建议它们。 请考虑以下示例：

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

使用引用单元格现在"污染"所有后续代码，必须取消引用和重新引用基础数据。 相反，请考虑`let mutable`：

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

除了 lambda 表达式中间的单点突变之外，所有其他涉及`acc`的代码都可以以与正常`let`绑定不可变值的使用没有什么不同的方式执行此操作。 这将使随着时间的推移更容易改变。

## <a name="object-programming"></a>对象编程

F# 完全支持对象和面向对象 （OO） 概念。 尽管许多 OO 概念功能强大且有用，但并非所有概念都是理想的使用。 以下列表提供了有关高级别 OO 功能类别的指导。

**考虑在许多情况下使用这些功能：**

* 点表示法`x.Length`（ ）
* 实例成员
* 隐式构造函数
* 静态成员
* 索引器表示法`arr.[x]`（ ）
* 命名和可选参数
* 接口和接口实现

**不要首先访问这些功能，但在它们方便解决问题时，请明智地应用它们：**

* 方法重载
* 封装的可变数据
* 类型上的运算符
* 自动属性
* 实施`IDisposable`和`IEnumerable`
* 类型扩展
* 事件
* 结构
* 委派
* 枚举

**通常避免这些功能，除非您必须使用它们：**

* 基于继承的类型层次结构和实现继承
* 空和`Unchecked.defaultof<_>`

### <a name="prefer-composition-over-inheritance"></a>首选组合而不是继承

[继承的组成](https://en.wikipedia.org/wiki/Composition_over_inheritance)是一个长期存在的习惯用法，好的 F# 代码可以遵循。 基本原则是，不应公开基类，并强制调用方从该基类继承以获取功能。

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a>如果不需要类，请使用对象表达式实现接口

[对象表达式](../language-reference/object-expressions.md)允许您动态实现接口，将实现的接口绑定到值，而无需在类内部执行此操作。 这很方便，特别是当您_只需要_实现接口，并且不需要完整类时。

例如，如果您添加了没有用于以下语句的`open`符号，则下面是在[Ionide](http://ionide.io/)中运行的代码，以提供代码修复操作：

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

由于与 Visual Studio 代码 API 交互时不需要类，因此对象表达式是理想的工具。 当您想要以临时方式与测试例程建立接口时，它们对于单元测试也很有价值。

## <a name="consider-type-abbreviations-to-shorten-signatures"></a>考虑类型缩写以缩短签名

[类型缩写](../language-reference/type-abbreviations.md)是将标签分配给另一种类型（如函数签名或更复杂的类型）的便捷方法。 例如，以下别名将标签分配给使用[CNTK（](https://docs.microsoft.com/cognitive-toolkit/)深度学习库）定义计算所需的内容：

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

该`Computation`名称是表示与它所混叠的签名匹配的任何函数的便捷方式。 使用像这样的类型缩写很方便，并允许更简洁的代码。

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a>避免使用类型缩写来表示您的域

尽管类型缩写对于为函数签名指定名称很方便，但当缩写其他类型时，它们可能会令人困惑。 请考虑此缩写：

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

这可以通过多种方式令人困惑：

* `BufferSize`不是抽象的;不是抽象的。它只是整数的另一个名称。
* 如果在`BufferSize`公共 API 中公开，很容易被误解为不仅仅是`int`。 通常，域类型具有多个属性，并且不是基元类型，如`int`。 此缩写违反了这一假设。
* （PascalCase） 的`BufferSize`套管意味着此类型包含更多数据。
* 与向函数提供命名参数相比，此别名的清晰度不会提高。
* 缩写不会在编译的 IL 中体现;因此，缩写不会以 IL 表示。它只是一个整数，这个别名是一个编译时构造。

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) = ...
```

总之，类型缩写的陷阱是，**它们不是**对缩写类型的抽象。 在前面的示例中，`BufferSize`只是一个`int`封面，没有额外的数据，也没有从类型系统的任何好处，除了`int`已经拥有。

使用类型缩写来表示域的另一种方法是使用单一案例区分结合。 前面的示例可以建模如下：

```fsharp
type BufferSize = BufferSize of int
```

如果编写的代码按`BufferSize`及其基础值运行，则需要构造一个代码，而不是传递任何任意整数：

```fsharp
module Networking =
    ...
    let send data (BufferSize size) =
    ...
```

这降低了错误地将任意整数传递到`send`函数的可能性，因为调用方必须在调用函数之前构造一个`BufferSize`类型来包装值。
