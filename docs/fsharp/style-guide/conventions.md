---
title: 'F # 编码约定'
description: '在编写 F # 代码时，了解一般指导原则和惯例。'
ms.date: 05/14/2018
ms.openlocfilehash: f3d16f735ddc1901aeaa5ebb39e2fa2b70a3d836
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457977"
---
# <a name="f-coding-conventions"></a>F # 编码约定

以下约定表述从大型 F # 使用经验基本代码。 [的良好的 F # 代码的五个原则](index.md#five-principles-of-good-f-code)每一项建议的基础。 与相关[F # 组件设计准则](component-design-guidelines.md)，但适用于任何 F # 代码，而不仅仅是组件，如库。

## <a name="organizing-code"></a>组织代码

F # 功能两种主要方式将代码组织： 模块和命名空间。 其中相似，但不要有以下不同：

* 命名空间是.NET 命名空间作为编译的。 静态类作为编译的模块。
* 命名空间始终是最高级别。 模块可以是顶级和嵌套在其他模块内。
* 命名空间可以跨多个文件。 模块不能。
* 可以使用修饰模块`[<RequireQualifiedAccess>]`和`[<AutoOpen>]`。

以下准则将帮助你使用它们来组织代码。

### <a name="prefer-namespaces-at-the-top-level"></a>选择最高级别的命名空间

对于任何公开可使用的代码，命名空间是到最高级别模块享受优惠。 由于它们.NET 命名空间作为编译的它们是可以从 C# 没有问题。

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

使用顶级模块可能不会显示不同时只能从 F # 中，但对于 C# 用户来说，调用方可能会对感到惊讶通过无需限定`MyClass`与`MyCode`模块。

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a>仔细应用 `[<AutoOpen>]`

`[<AutoOpen>]`构造可以会污染向调用方，可用的作用域和内容来自问题的回答是"神奇"。 这通常不是一件好事。 此规则的例外是在 F # 核心库自身 （尽管这种情况也是稍有争议的）。

但是，它是一种便于，如果你有一个公共 API，你希望组织单独从该公共 API 帮助程序功能。

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

这样就可以从一个函数的公共 API 的完全单独实现详细信息而无需每次调用该函数的完全限定程序的帮助。

此外，公开扩展方法和表达式生成器的命名空间级别可以巧妙地表示与`[<AutoOpen>]`。

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a>使用`[<RequireQualifiedAccess>]`每当名称无法冲突，或者你认为它是帮助可读性

添加`[<RequireQualifiedAccess>]`模块的属性指示模块可能无法打开，并对该模块的元素的引用，需要显式限定访问权限。 例如，`Microsoft.FSharp.Collections.List`模块具有此属性。

时函数和模块中的值可能与其他模块中的名称发生冲突的名称，这会很有用。 需限定的访问会大大增加的长期的可维护性和 evolvability 的库。

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a>排序`open`语句拓扑结构上

在 F # 中，声明的顺序非常重要，包括`open`语句。 这是与 C# 中，其中的效果`using`和`using static`无关的文件中的这些语句的顺序。

在 F # 中，打开到作用域中的元素可以隐藏其他人已存在。 这意味着该重新排序`open`语句无法更改代码的含义。 因此，任何任意排序的所有`open`语句 （例如，根据） 通常不建议，以免生成不同的行为，你预期的。

相反，我们建议您进行排序它们[拓扑结构上](https://en.wikipedia.org/wiki/Topological_sorting); 即，排序你`open`中的顺序的语句_层_定义你的系统。 也可以考虑不同的拓扑图层内的排序字母数字。

例如，下面是拓扑排序的 F # 编译器服务公共 API 文件：

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

请注意，一个分行符将分开的拓扑图层，每个层正在排序进行排序之后。 这完全不会意外地隐藏值的情况下组织代码。

## <a name="use-classes-to-contain-values-that-have-side-effects"></a>使用类来包含具有副作用的值

很多时候当初始化值可能会有副作用，如实例化到数据库或其他远程资源的上下文。 它很容易初始化之类模块中的内容并将其用于后续的函数：

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

这通常是个好主意原因有多种：

首先，应用程序配置被推入到与基本代码`dep1`和`dep2`。 这是难以维护在更大的基本代码。

第二个、 静态初始化的数据不应包含不是线程安全，如果你的组件将本身使用多个线程的值。 这通过清楚地违反了`dep3`。

最后，初始化模块将编译到一个静态构造函数为整个编译单元。 如果该模块中的 let 绑定值初始化发生任何错误时，表现为`TypeInitializationException`，然后缓存应用程序的整个生存期内。 这可能很难诊断。 通常没有内部异常，则可以尝试以解释的但如果没有，则没有的根本原因无法区分。

相反，只需使用一个简单的类来保存依赖关系：

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member __.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member __.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

这可实现以下目的：

1. 将推送用 API 自身之外的任何依赖状态。
2. 现在可以在 API 之外执行配置。
3. 在依赖值的初始化错误不是可能会表现为`TypeInitializationException`。
4. 此 API 现可以轻松地测试。

## <a name="error-management"></a>错误管理

大型系统中的错误管理是一项复杂且一些略有区别的任务，并且没有中确保你的系统的项目符号是容错和行为也没有白银。 以下指南应提供的指南在浏览此困难的空间。

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a>表示错误情况和中固有的你的域的类型非法状态

与[可区分联合](../language-reference/discriminated-unions.md)，F # 使你能够在类型系统中表示发生故障的程序状态。 例如：

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

在这种情况下，有三种已知的方式从银行帐户中取出 money 可能会失败。 每个错误用例表示在类型中，并可以因此得到处理安全地在整个程序。

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

一般情况下，如果你可以对不同的方式进行建模问题可以**失败**在你的域，然后错误处理代码将被不再视为内容必须除了常规程序流处理。 它是只需正常程序流的一部分，不被视为**异常**。 有这两个主要好处：

1. 很容易地保持你的域随着时间推移而变化。
2. 错误情况下更易于进行单元测试。

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a>当错误不能用类型来表示使用异常

可以在问题域中表示不是所有错误。 这些类型的错误是*异常*性质，因此中引发和捕获异常，F # 中的功能。

首先，建议你阅读[异常设计准则](../../standard/design-guidelines/exceptions.md)。 这些是还适用于 F #。

按以下顺序的首选项，应考虑出于引发异常的 F # 中可用的主要构造：

| 函数 | 语法 | 目标 |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | 引发`System.ArgumentNullException`与指定的参数名称。 |
| `invalidArg` | `invalidArg "argumentName" "message"` | 引发`System.ArgumentException`使用指定的参数名称和消息。 |
| `invalidOp` | `invalidOp "message"` | 引发`System.InvalidOperationException`使用指定的消息。 |
|`raise`| `raise (ExceptionType("message"))` | 引发异常的通用机制。 |
| `failwith` | `failwith "message"` | 引发`System.Exception`使用指定的消息。 |
| `failwithf` | `failwithf "format string" argForFormatString` | 引发`System.Exception`由格式字符串和其输入一条消息。 |

使用`nullArg`，`invalidArg`和`invalidOp`作为机制引发`ArgumentNullException`，`ArgumentException`和`InvalidOperationException`在适当的时候。

`failwith`和`failwithf`函数应通常避免使用，因为它们会引发基`Exception`类型，不特定异常。 按照[异常设计准则](../../standard/design-guidelines/exceptions.md)，您想要提升时你可以更具体的异常。

### <a name="using-exception-handling-syntax"></a>使用异常处理语法

F # 支持通过异常模式`try...with`语法：

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

协调在遇到与模式匹配异常时执行的功能可能会有点很棘手，如果您想要保留的代码清理。 一个此类方法来处理这种情况是使用[活动模式](../language-reference/active-patterns.md)作为组功能周围的错误情况的异常自身的一种手段。 例如，你可能要使用的 API 时它引发异常，异常元数据中包含有价值的信息。 解包内活动的模式的捕获异常的正文中有用的值和返回值可以在某些情况下有用。

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a>不使用一元错误处理程序来替换异常

异常被视为某种程度上 taboo 函数编程中。 事实上，异常违反颜色纯度，以便安全地认为它们不完全功能。 但是，这将忽略的实际情况之前，必须运行代码，以及该运行时，可能会出现错误。 一般情况下，假定在大多数情况下是既不纯，也不是总，尽量少的意外事件中编写代码。

请务必考虑以下核心优势/方面的异常其相关性和.NET 运行时和跨语言生态系统中作为一个整体的适合程度方面：

1. 它们包含详细的诊断信息，这将非常有用，在调试问题时。
2. 它们是由运行时和其他.NET 语言易于理解。
3. 它们可以降低与超出其方法的代码进行比较时的重要样本*避免*通过即席基础上实现其语义的某个子集的异常。

此第三个点至关重要。 对于不常用的复杂操作，无法使用异常可能会导致处理结构如下：

```fsharp
Result<Result<MyType, string>, string list>
```

这很容易导致脆弱代码与在"stringly 类型化"的错误进行匹配的模式一样：

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

此外，它可以是容易让人想到吞并"简单"返回"不用去涉猎"类型的函数所需的任何异常：

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

遗憾的是，`tryReadAllText`可以引发基于花费更多的文件系统，可能发生的事情的大量异常和此代码离开放弃有关可能实际上什么问题在你的环境中的任何信息。 如果将此代码替换的结果类型，然后你返回到"stringly 类型化"错误消息分析：

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

并将放入异常对象本身中`Error`构造函数仅仅是强制您能够正确处理在调用站点，而不在函数中的异常类型。 有效地执行此操作创建选中是非常 unfun 作为 API 的调用方处理的异常。

与上述示例的良好替代方法是捕获*特定*异常并返回该异常的上下文中有意义的值。 如果你修改`tryReadAllText`函数，如下所示，`None`具有多个含义：

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

而不是用作全部捕获时，此函数现在正确地处理这种情况时文件未找到，然后将该含义分配给返回。 此返回值可以将映射到错误这种情况下，在不放弃任何上下文的信息或强制调用方以处理可能不在该点在代码中相关情况。

类型，如`Result<'Success, 'Error>`适用于基本操作，它们不嵌套的且 F # 可选类型也特别适合于表示当内容无法任一返回*内容*或*执行任何操作*. 它们不取代异常，不过，且参数不应尝试使用，以替换异常。 相反，它们应谨慎地到地址的异常和错误管理策略的特定方面采用目标的方式应用。

## <a name="partial-application-and-point-free-programming"></a>部分应用和免点编程

F # 点释放样式，支持部分应用，从而对程序的各种方法。 这可以对在模块或事物的实现代码重用有用，但通常不是以公开公开。 一般情况下，点释放编程不是本身，并可以添加一个巨大的认知障碍的用户不深陷样式。

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a>不要使用部分应用和扩充中公共 Api

很少有例外，在公共 Api 中的部分应用程序的使用可以让使用者感到困惑。 通常情况下， `let`-F # 代码中的绑定的值为**值**，而不**函数值**。 将混合在一起的值和函数值可能导致保存少量的代码以认知开销，相当多的位交换的行尤其是结合运算符如`>>`编写函数。

### <a name="consider-the-tooling-implications-for-point-free-programming"></a>请考虑点释放编程的工具含义

扩充的函数不标记其参数。 这具有工具影响。 请考虑以下两个函数：

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

都有效函数，但`funcWithApplication`是扩充的函数。 当你将鼠标悬停在其类型在编辑器中时，你将看到以下内容：

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

在调用站点上，如 Visual Studio 工具中的工具提示将不为你提供有意义信息关于什么`string`和`int`实际表示输入的类型。

如果你遇到类似点释放代码`funcWithApplication`公开可耗用，建议执行完全的 η 扩展，以便工具可以选取在自变量有意义的名称。

此外，调试点无代码会有点困难，如果不是不可能。 调试工具依赖值绑定到名称 (例如，`let`绑定)，以便你可以检查中间值中途执行。 当你的代码具有要检查的值时，没有要调试的内容。 将来，调试工具可演变以便综合这些值基于以前执行的路径，但它不是 hedge 你匹配上一个好办法*潜在*调试功能。

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a>请考虑部分应用程序作为一种技术来减少内部样本

与上一个点，部分应用程序是一个用于减少应用程序或 API 的更深层次的内部结构内的样本的曾经工具。 它可以帮助进行单元测试的更复杂的 Api，样本通常是处理困难的实现。 例如，下面的代码演示如何实现什么最模拟框架为你提供不在此类的框架执行的外部依赖关系并无需了解相关订货的 API。

例如，考虑以下解决方案拓扑：

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

`ImplementationLogic.fsproj` 例如，可能会公开代码：

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member __.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

单元测试`Transactions.doTransaction`中`ImplementationLogic.Tests.fspoj`很容易：

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

部分应用`doTransaction`与模拟上下文对象，可以在你的单元测试的所有调用函数，而无需每次构造模拟的上下文：

```fsharp
namespace TransactionTests

open Xunit
open TransactionTypes
open TransactionsTestingUtil
open TransactionsTestingUtil.TransactionsTestable

let testableContext =
    { new ITransactionContext with
        member __.TheFirstMember() = ...
        member __.TheSecondMember() = ... }

let transactionRoutine = getTestableTransactionRoutine testableContext

[<Fact>]
let ``Test withdrawal transaction with 0.0 for balance``() =
    let expected = ...
    let actual = transactionRoutine TransactionType.Withdraw 0.0
    Assert.Equal(expected, actual)
```

不应将此技术普遍应用到整个基本代码，但它是一种好方法，以减少复杂的内部结构和单元测试这些内部结构的样本。

## <a name="access-control"></a>访问控制

F # 包含多个选项[访问控制](../language-reference/access-control.md)，从可用的.NET 运行时中继承。 这些并不是只可用于类型-你可以使用它们对于函数，太。

* 首选非`public`类型和成员之前你需要对其可以公开使用。 这还将减少到何种使用者几
* 尽可能将所有的帮助器功能`private`。
* 请考虑使用`[<AutoOpen>]`在专用模块的帮助器函数，如果趋于大量上。

## <a name="type-inference-and-generics"></a>类型推理和泛型

类型推理可为你节省键入大量的样本。 和 F # 编译器中的自动泛化可帮助你编写对您来说几乎没有任何额外的工作量的更通用代码。 但是，这些功能不是全局完好的。

* 考虑与公共 Api 中的显式类型标记自变量名称并不依赖此类型推理。

    这样做的原因在于**你**应在控件中的形状的你的 API，不编译器。 虽然编译器可以执行在为你推理类型了很好，很可能有的 API 更改形状，如果它依赖于内部结构已更改类型。 这可能是你的想，但它几乎可以肯定将导致下游使用者随后必须处理的重大 API 更改。 相反，若要显式控制形状的公共 API，你可以控制这些重大更改。 在 DDD 术语中，这被想象的作为防损坏层。

* 请考虑为泛型参数指定有意义的名称。

    你正在编写的并不特定于特定域真正泛型代码，除非有意义的名称可帮助其他程序员了解他们正在使用的域。 例如，一个名为的类型参数`'Document`文档与之进行交互的上下文中数据库使它清楚地了解泛型文档类型，可以接受由该函数或你正在使用的成员。

* 请考虑命名 PascalCase 泛型类型参数。

    这是常见的方式进行某些操作在.NET 中，因此建议你使用 PascalCase 而不是 snake_case 或驼峰匹配。

最后，自动泛化并不总是熟悉 F # 或大型基本代码的人员一件好事。 使用都是泛型方法的组件处于认知开销。 此外，如果自动通用的函数不用于不同的输入类型 （让单独如果它们旨在用于这种情况下），则它们正在泛型时间中此点处没有实际的好处。 应始终考虑是否你正在编写的代码实际上将从正在泛型受益。

## <a name="performance"></a>性能

F # 的值为默认情况下，你可以避免 bug （尤其是那些涉及并发和并行） 的某些类不可变。 但是，在某些情况下，以便实现最佳 （或甚至合理） 效率的执行时间或内存分配的工作范围可能最实现使用就地转变的状态。 这是在 F # 使用可以选择使用的基础可能`mutable`关键字。

但是，使用`mutable`F # 中可能觉得功能纯度一致。 这没什么关系，如果调整到的颜色纯度上预期[引用透明度](https://en.wikipedia.org/wiki/Referential_transparency)。 在编写 F # 函数时，引用透明度-而不是颜色纯度-很最终目标。 这样，您可以编写通过性能关键代码的基于转变的实现的功能的接口。

### <a name="wrap-mutable-code-in-immutable-interfaces"></a>在不可变的接口中包装可变代码

具有为目标的引用透明度，编写代码，不会公开性能关键函数可变 underbelly 至关重要。 例如，下面的代码实现`Array.contains`F # 核心库中的函数：

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

多次调用此函数不会更改基础的数组，也不会要求你维护在使用它的任何可变状态。 它是代码的 referentially 透明的即使中它几乎每个行使用转变。

### <a name="consider-encapsulating-mutable-data-in-classes"></a>请考虑将封装在类中的可变数据

前面的示例使用单个函数封装使用可变数据操作。 这并不总是能够满足更复杂的数据集。 请考虑以下几组函数：

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

此代码是高性能，但它公开调用方负责维护的基于变化的数据结构。 这可以在不包含可以更改任何基础成员类内部包装：

```fsharp
open System.Collections.Generic

/// The results of computing the LALR(1) closure of an LR(0) kernel
type Closure1Table() =
    let t = Dictionary<Item0, HashSet<TerminalIndex>>()

    member __.Add(key, value) =
        if not (t.ContainsKey(key)) then
            t.Add(key, value)
        else
            t.[key] <- value

    member __.Count = t.Count

    member __.Contains(key, value) =
        match t.TryGetValue(key) with
        | (true, v) -> v.Equals(value)
        | (false, _) -> false
```

`Closure1Table` 封装的基础的基于变化的数据结构，因此无法强制调用方来维护的基础数据结构。 类是一种强大方法封装了数据以及可以基于变化的而公开给调用方的详细信息的例程。

### <a name="prefer-let-mutable-to-reference-cells"></a>首选`let mutable`引用单元格

引用单元格是表示对一个值，而不是值本身的引用的方式。 虽然它们可以使用性能关键代码，但通常不建议将其。 请看下面的示例：

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

使用引用单元格现在"破坏"与无需取消引用和重新引用基础数据的所有后续代码。 相反，请考虑`let mutable`:

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

除了转变中间 lambda 表达式的单个点，所有其他代码的接触`acc`可以这样的常规用法没有什么不同的方式`let`-绑定不可变的值。 这将使更轻松地随时间而变化。

## <a name="object-programming"></a>对象编程

F # 包含对对象和面向对象的 (OO) 概念的完整支持。 尽管许多 OO 概念是功能强大且有用，但不是所有进行使用。 以下列表提供的类别的较高层面 OO 功能的指南。

**请考虑在许多情况下使用这些功能：**

* 点表示法 (`x.Length`)
* 实例成员
* 隐式构造函数
* 静态成员
* 索引器表示法 (`arr.[x]`)
* 命名参数和可选参数
* 接口和接口实现

**首先，不达到为这些功能，但不要谨慎地将其应用时方便地解决问题：**

* 方法重载
* 封装的可变数据
* 对类型的运算符
* 自动属性
* 实现`IDisposable`和 `IEnumerable`
* 类型扩展
* 事件
* 结构
* 委托
* 枚举

**除非你必须使用它们，通常避免这些功能：**

* 基于继承的类型层次结构和实现继承
* Null 值和 `Unchecked.defaultof<_>`

### <a name="prefer-composition-over-inheritance"></a>更愿意组合，而继承

[通过继承组合](https://en.wikipedia.org/wiki/Composition_over_inheritance)是一种长期存在的方法，可以遵循良好的 F # 代码。 基本原则是，不应公开的基本类和强制调用方继承自该基类，以获取的功能。

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a>使用对象表达式实现接口，如果你不需要一个类

[对象表达式](../language-reference/object-expressions.md)允许你动态，实现接口在无需为此，在类内部实现的接口绑定到的值。 此方法很方便，尤其是如果你_仅_需要实现接口，并且无需完整的类。

例如，以下是在中运行的代码[Ionide](http://ionide.io/)提供的代码修复操作，如果你已添加你没有的符号`open`语句：

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

由于没有为类无需与 Visual Studio 代码 API 交互时，对象表达式是此的理想工具。 此外，还为单元测试，如果你想要与测试例程接口存根以即席方式有价值。

## <a name="type-abbreviations"></a>类型缩写

[类型缩写，用](../language-reference/type-abbreviations.md)是一种简便的方法，以将标签分配给另一个类型，例如函数签名或更复杂的类型。 例如，以下别名将标签分配给需要定义与计算哪些[CNTK](https://www.microsoft.com/cognitive-toolkit/)、 深入学习库：

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

`Computation`名称是一种简便的方法来表示它是别名的签名匹配的任何函数。 此类使用类型缩写是方便，允许进行更简洁的代码。

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a>避免使用类型缩写来表示你的域

虽然类型缩写很方便，将交给函数的签名的名称，它们可能容易引起混淆时 abbreviating 其他类型。 请考虑此缩写：

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

这可能容易引起混淆采用多种方式：

* `BufferSize` 不是一个抽象概念。它是一个整数的另一个名称。
* 如果`BufferSize`公开在公共 API 中，它可以轻松地被错误解释不仅仅表示`int`。 通常情况下，域类型具有到它们的多个属性，以及是否不等的基元类型`int`。 此缩写违反这一假定。
* 大小写`BufferSize`(PascalCase) 表示此类型包含更多的数据。
* 此别名不提供起见与提供给函数的命名自变量进行比较。
* 缩写不将清单中编译的 IL;它是只是一个整数，此别名是一个编译时构造。

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) =
        ...
```

总之，与类型缩写缺陷就是它们是**不**它们 abbreviating 类型的抽象。 在前面的示例中，`BufferSize`只有`int`事实上，与任何其他数据，也不从除了新增功能的类型系统带来的好处`int`已有。
