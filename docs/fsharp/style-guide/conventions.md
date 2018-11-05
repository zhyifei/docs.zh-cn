---
title: F# 编码约定
description: 编写 F# 代码时，了解一般指导原则和惯例。
ms.date: 05/14/2018
ms.openlocfilehash: 21119b6d69e00f359104bfb6eab7681bdbfb8d78
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "49087383"
---
# <a name="f-coding-conventions"></a><span data-ttu-id="8178a-103">F# 编码约定</span><span class="sxs-lookup"><span data-stu-id="8178a-103">F# coding conventions</span></span>

<span data-ttu-id="8178a-104">以下约定表述从体验使用大型 F# 代码库。</span><span class="sxs-lookup"><span data-stu-id="8178a-104">The following conventions are formulated from experience working with large F# codebases.</span></span> <span data-ttu-id="8178a-105">[优秀的 F# 代码的五个原则](index.md#five-principles-of-good-f-code)是每个建议的基础。</span><span class="sxs-lookup"><span data-stu-id="8178a-105">The [Five principles of good F# code](index.md#five-principles-of-good-f-code) are the foundation of each recommendation.</span></span> <span data-ttu-id="8178a-106">与相关[F# 组件设计准则](component-design-guidelines.md)，但适用于任何 F# 代码，而不仅仅是组件，例如库。</span><span class="sxs-lookup"><span data-stu-id="8178a-106">They are related to the [F# component design guidelines](component-design-guidelines.md), but are applicable for any F# code, not just components such as libraries.</span></span>

## <a name="organizing-code"></a><span data-ttu-id="8178a-107">组织代码</span><span class="sxs-lookup"><span data-stu-id="8178a-107">Organizing code</span></span>

<span data-ttu-id="8178a-108">F# 功能来组织代码的两种主要方式： 模块和命名空间。</span><span class="sxs-lookup"><span data-stu-id="8178a-108">F# features two primary ways to organize code: modules and namespaces.</span></span> <span data-ttu-id="8178a-109">这些相似，但存在以下差异：</span><span class="sxs-lookup"><span data-stu-id="8178a-109">These are similar, but do have the following differences:</span></span>

* <span data-ttu-id="8178a-110">命名空间被编译为.NET 命名空间。</span><span class="sxs-lookup"><span data-stu-id="8178a-110">Namespaces are compiled as .NET namespaces.</span></span> <span data-ttu-id="8178a-111">静态类作为编译模块。</span><span class="sxs-lookup"><span data-stu-id="8178a-111">Modules are compiled as static classes.</span></span>
* <span data-ttu-id="8178a-112">命名空间始终是最高级别。</span><span class="sxs-lookup"><span data-stu-id="8178a-112">Namespaces are always top level.</span></span> <span data-ttu-id="8178a-113">模块可以是顶级和嵌套在其他模块。</span><span class="sxs-lookup"><span data-stu-id="8178a-113">Modules can be top-level and nested within other modules.</span></span>
* <span data-ttu-id="8178a-114">命名空间可以跨多个文件。</span><span class="sxs-lookup"><span data-stu-id="8178a-114">Namespaces can span multiple files.</span></span> <span data-ttu-id="8178a-115">模块不能。</span><span class="sxs-lookup"><span data-stu-id="8178a-115">Modules cannot.</span></span>
* <span data-ttu-id="8178a-116">模块可以使用修饰`[<RequireQualifiedAccess>]`和`[<AutoOpen>]`。</span><span class="sxs-lookup"><span data-stu-id="8178a-116">Modules can be decorated with `[<RequireQualifiedAccess>]` and `[<AutoOpen>]`.</span></span>

<span data-ttu-id="8178a-117">以下准则将帮助您使用这些来组织你的代码。</span><span class="sxs-lookup"><span data-stu-id="8178a-117">The following guidelines will help you use these to organize your code.</span></span>

### <a name="prefer-namespaces-at-the-top-level"></a><span data-ttu-id="8178a-118">更喜欢在顶层命名空间</span><span class="sxs-lookup"><span data-stu-id="8178a-118">Prefer namespaces at the top level</span></span>

<span data-ttu-id="8178a-119">对于任何公开使用的代码，命名空间是优先于模块的顶层。</span><span class="sxs-lookup"><span data-stu-id="8178a-119">For any publicly consumable code, namespaces are preferential to modules at the top level.</span></span> <span data-ttu-id="8178a-120">作为.NET 命名空间对它们进行编译，因为它们是可使用 C# 中不存在问题。</span><span class="sxs-lookup"><span data-stu-id="8178a-120">Because they are compiled as .NET namespaces, they are consumable from C# with no issue.</span></span>

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

<span data-ttu-id="8178a-121">使用顶级模块可能不会显示不同时仅从 F# 中，但 C# 的使用者，调用方可能会惊讶于无需限定`MyClass`与`MyCode`模块。</span><span class="sxs-lookup"><span data-stu-id="8178a-121">Using a top-level module may not appear different when called only from F#, but for C# consumers, callers may be surprised by having to qualify `MyClass` with the `MyCode` module.</span></span>

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a><span data-ttu-id="8178a-122">请仔细应用 `[<AutoOpen>]`</span><span class="sxs-lookup"><span data-stu-id="8178a-122">Carefully apply `[<AutoOpen>]`</span></span>

<span data-ttu-id="8178a-123">`[<AutoOpen>]`构造可以污染，调用方提供的功能范围和内容来自的答案是"神奇"。</span><span class="sxs-lookup"><span data-stu-id="8178a-123">The `[<AutoOpen>]` construct can pollute the scope of what is available to callers, and the answer to where something comes from is "magic".</span></span> <span data-ttu-id="8178a-124">这通常不是一件好事。</span><span class="sxs-lookup"><span data-stu-id="8178a-124">This is generally not a good thing.</span></span> <span data-ttu-id="8178a-125">此规则的例外是 F# 核心库本身 （尽管这一事实也是有点有争议的）。</span><span class="sxs-lookup"><span data-stu-id="8178a-125">An exception to this rule is the F# Core Library itself (though this fact is also a bit controversial).</span></span>

<span data-ttu-id="8178a-126">但是，如果你有一个公共 API，你想要组织单独从该公共 API 帮助程序功能是提供了便利。</span><span class="sxs-lookup"><span data-stu-id="8178a-126">However, it is a convenience if you have helper functionality for a public API that you wish to organize separately from that public API.</span></span>

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

<span data-ttu-id="8178a-127">这样可以从一个函数的公共 API 完全不同的实现详细信息而无需完全限定程序的帮助程序每次调用它。</span><span class="sxs-lookup"><span data-stu-id="8178a-127">This lets you cleanly separate implementation details from the public API of a function without having to fully qualify a helper each time you call it.</span></span>

<span data-ttu-id="8178a-128">此外，公开的扩展方法和表达式生成器的命名空间级别可以巧妙地表示与`[<AutoOpen>]`。</span><span class="sxs-lookup"><span data-stu-id="8178a-128">Additionally, exposing extension methods and expression builders at the namespace level can be neatly expressed with `[<AutoOpen>]`.</span></span>

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a><span data-ttu-id="8178a-129">使用`[<RequireQualifiedAccess>]`时可能发生名称冲突或您认为它有助于提高可读性</span><span class="sxs-lookup"><span data-stu-id="8178a-129">Use `[<RequireQualifiedAccess>]` whenever names could conflict or you feel it helps with readability</span></span>

<span data-ttu-id="8178a-130">添加`[<RequireQualifiedAccess>]`对模块的特性指示模块不能打开，并且对模块的元素的引用需要显式限定访问权限。</span><span class="sxs-lookup"><span data-stu-id="8178a-130">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="8178a-131">例如，`Microsoft.FSharp.Collections.List`模块具有此属性。</span><span class="sxs-lookup"><span data-stu-id="8178a-131">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="8178a-132">当函数和模块中的值具有名称可能与其他模块中的名称发生冲突时，这很有用。</span><span class="sxs-lookup"><span data-stu-id="8178a-132">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="8178a-133">需要限定的访问可以极大地提高的长期可维护性和可进化性的库。</span><span class="sxs-lookup"><span data-stu-id="8178a-133">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a><span data-ttu-id="8178a-134">排序`open`语句拓扑结构上</span><span class="sxs-lookup"><span data-stu-id="8178a-134">Sort `open` statements topologically</span></span>

<span data-ttu-id="8178a-135">在 F# 中，声明的顺序非常重要，包括与`open`语句。</span><span class="sxs-lookup"><span data-stu-id="8178a-135">In F#, the order of declarations matters, including with `open` statements.</span></span> <span data-ttu-id="8178a-136">这是与 C# 中，其中的效果`using`和`using static`无关的文件中这些语句的顺序。</span><span class="sxs-lookup"><span data-stu-id="8178a-136">This is unlike C#, where the effect of `using` and `using static` is independent of the ordering of those statements in a file.</span></span>

<span data-ttu-id="8178a-137">在 F# 中，打开到作用域的元素可以隐藏其他人已存在。</span><span class="sxs-lookup"><span data-stu-id="8178a-137">In F#, elements opened into a scope can shadow others already present.</span></span> <span data-ttu-id="8178a-138">这意味着重新排序`open`语句无法更改代码的含义。</span><span class="sxs-lookup"><span data-stu-id="8178a-138">This means that reordering `open` statements could alter the meaning of code.</span></span> <span data-ttu-id="8178a-139">因此，任何任意排序的所有`open`语句 （例如，根据） 通常不建议，避免生成您所料的不同行为。</span><span class="sxs-lookup"><span data-stu-id="8178a-139">As a result, any arbitrary sorting of all `open` statements (for example, alphanumerically) is generally not recommended, lest you generate different behavior that you might expect.</span></span>

<span data-ttu-id="8178a-140">相反，我们建议，您对其进行排序[拓扑结构上](https://en.wikipedia.org/wiki/Topological_sorting); 即，排序你`open`语句中的顺序_层_系统的定义。</span><span class="sxs-lookup"><span data-stu-id="8178a-140">Instead, we recommend that you sort them [topologically](https://en.wikipedia.org/wiki/Topological_sorting); that is, order your `open` statements in the order in which _layers_ of your system are defined.</span></span> <span data-ttu-id="8178a-141">也可以考虑不同的拓扑图层内的排序字母数字。</span><span class="sxs-lookup"><span data-stu-id="8178a-141">Doing alphanumeric sorting within different topological layers may also be considered.</span></span>

<span data-ttu-id="8178a-142">例如，下面是 F# 编译器服务公共 API 文件的拓扑排序：</span><span class="sxs-lookup"><span data-stu-id="8178a-142">As an example, here is the topological sorting for the F# compiler service public API file:</span></span>

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

<span data-ttu-id="8178a-143">请注意，一个分行符将分开的拓扑图层，与正在排序根据之后每个层。</span><span class="sxs-lookup"><span data-stu-id="8178a-143">Note that a line break separates topological layers, with each layer being sorted alphanumerically afterwards.</span></span> <span data-ttu-id="8178a-144">这完全可以将代码组织而不会意外地隐藏值中。</span><span class="sxs-lookup"><span data-stu-id="8178a-144">This cleanly organizes code without accidentally shadowing values.</span></span>

## <a name="use-classes-to-contain-values-that-have-side-effects"></a><span data-ttu-id="8178a-145">使用类来包含具有副作用的值</span><span class="sxs-lookup"><span data-stu-id="8178a-145">Use classes to contain values that have side effects</span></span>

<span data-ttu-id="8178a-146">有很多时候时初始化一个值，可能会有副作用，如实例化到的数据库或其他远程资源的上下文。</span><span class="sxs-lookup"><span data-stu-id="8178a-146">There are many times when initializing a value can have side effects, such as instantiating a context to a database or other remote resource.</span></span> <span data-ttu-id="8178a-147">它很容易初始化模块这类问题，并将其用于后续函数：</span><span class="sxs-lookup"><span data-stu-id="8178a-147">It is tempting to initialize such things in a module and use it in subsequent functions:</span></span>

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

<span data-ttu-id="8178a-148">这通常是一个好主意几个原因：</span><span class="sxs-lookup"><span data-stu-id="8178a-148">This is frequently a bad idea for a few reasons:</span></span>

<span data-ttu-id="8178a-149">首先，应用程序配置推送到的基本代码`dep1`和`dep2`。</span><span class="sxs-lookup"><span data-stu-id="8178a-149">First, application configuration is pushed into the codebase with `dep1` and `dep2`.</span></span> <span data-ttu-id="8178a-150">这将很难维护中较大代码库。</span><span class="sxs-lookup"><span data-stu-id="8178a-150">This is difficult to maintain in larger codebases.</span></span>

<span data-ttu-id="8178a-151">第二个，将以静态方式初始化数据不应包含不是线程安全，如果你的组件本身会使用多个线程的值。</span><span class="sxs-lookup"><span data-stu-id="8178a-151">Second, statically initialized data should not include values that are not thread safe if your component will itself use multiple threads.</span></span> <span data-ttu-id="8178a-152">显然，这违反了`dep3`。</span><span class="sxs-lookup"><span data-stu-id="8178a-152">This is clearly violated by `dep3`.</span></span>

<span data-ttu-id="8178a-153">最后，初始化模块编译到静态构造函数在整个编译单元。</span><span class="sxs-lookup"><span data-stu-id="8178a-153">Finally, module initialization compiles into a static constructor for the entire compilation unit.</span></span> <span data-ttu-id="8178a-154">如果该模块中的 let 绑定值初始化中出现任何错误，它表现为`TypeInitializationException`然后应用程序的整个生存期内缓存。</span><span class="sxs-lookup"><span data-stu-id="8178a-154">If any error occurs in let-bound value initialization in that module, it manifests as a `TypeInitializationException` that is then cached for the entire lifetime of the application.</span></span> <span data-ttu-id="8178a-155">这可能很难诊断。</span><span class="sxs-lookup"><span data-stu-id="8178a-155">This can be difficult to diagnose.</span></span> <span data-ttu-id="8178a-156">通常是内部异常，您可以尝试推断，但如果没有，则根本原因无法区分。</span><span class="sxs-lookup"><span data-stu-id="8178a-156">There is usually an inner exception that you can attempt to reason about, but if there is not, then there is no telling what the root cause is.</span></span>

<span data-ttu-id="8178a-157">相反，只需使用一个简单的类来保存依赖项：</span><span class="sxs-lookup"><span data-stu-id="8178a-157">Instead, just use a simple class to hold dependencies:</span></span>

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member __.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member __.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

<span data-ttu-id="8178a-158">这可实现以下目的：</span><span class="sxs-lookup"><span data-stu-id="8178a-158">This enables the following:</span></span>

1. <span data-ttu-id="8178a-159">将推送 API 本身之外的任何依赖于状态。</span><span class="sxs-lookup"><span data-stu-id="8178a-159">Pushing any dependent state outside of the API itself.</span></span>
2. <span data-ttu-id="8178a-160">现在可以外部 API 完成配置。</span><span class="sxs-lookup"><span data-stu-id="8178a-160">Configuration can now be done outside of the API.</span></span>
3. <span data-ttu-id="8178a-161">初始化为因变量值中的错误不是可能会表现为`TypeInitializationException`。</span><span class="sxs-lookup"><span data-stu-id="8178a-161">Errors in initialization for dependent values are not likely to manifest as a `TypeInitializationException`.</span></span>
4. <span data-ttu-id="8178a-162">该 API 是现在可以轻松地测试。</span><span class="sxs-lookup"><span data-stu-id="8178a-162">The API is now easier to test.</span></span>

## <a name="error-management"></a><span data-ttu-id="8178a-163">错误管理</span><span class="sxs-lookup"><span data-stu-id="8178a-163">Error management</span></span>

<span data-ttu-id="8178a-164">大型系统中的错误管理是一项复杂且能体现细微差别工作，并且没有确保您的系统中的项目符号是容错的和的行为也没有 silver。</span><span class="sxs-lookup"><span data-stu-id="8178a-164">Error management in large systems is a complex and nuanced endeavor, and there are no silver bullets in ensuring your systems are fault-tolerant and behave well.</span></span> <span data-ttu-id="8178a-165">以下指南应提供导航此困难空间中的指导。</span><span class="sxs-lookup"><span data-stu-id="8178a-165">The following guidelines should offer guidance in navigating this difficult space.</span></span>

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a><span data-ttu-id="8178a-166">表示错误情况和你的域中的内部类型中的非法状态</span><span class="sxs-lookup"><span data-stu-id="8178a-166">Represent error cases and illegal state in types intrinsic to your domain</span></span>

<span data-ttu-id="8178a-167">与[可区分联合](../language-reference/discriminated-unions.md)，F# 使你能够在类型系统中表示发生故障的程序状态。</span><span class="sxs-lookup"><span data-stu-id="8178a-167">With [Discriminated Unions](../language-reference/discriminated-unions.md), F# gives you the ability to represent faulty program state in your type system.</span></span> <span data-ttu-id="8178a-168">例如：</span><span class="sxs-lookup"><span data-stu-id="8178a-168">For example:</span></span>

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

<span data-ttu-id="8178a-169">在这种情况下，有三种已知的方式从银行帐户提取资金可能会失败。</span><span class="sxs-lookup"><span data-stu-id="8178a-169">In this case, there are three known ways that withdrawing money from a bank account can fail.</span></span> <span data-ttu-id="8178a-170">每个错误用例表示在类型中，并因此地进行处理安全地在整个程序。</span><span class="sxs-lookup"><span data-stu-id="8178a-170">Each error case is represented in the type, and can thus be dealt with safely throughout the program.</span></span>

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

<span data-ttu-id="8178a-171">一般情况下，如果您可以建立模型的不同方法的内容可以**失败**中你的域，然后处理错误的代码不再视为必须处理常规程序流除了的内容。</span><span class="sxs-lookup"><span data-stu-id="8178a-171">In general, if you can model the different ways that something can **fail** in your domain, then error handling code is no longer treated as something you must deal with in addition to regular program flow.</span></span> <span data-ttu-id="8178a-172">它是只需正常程序流的一部分，不会被视为**异常**。</span><span class="sxs-lookup"><span data-stu-id="8178a-172">It is simply a part of normal program flow, and not considered **exceptional**.</span></span> <span data-ttu-id="8178a-173">有这两个主要好处：</span><span class="sxs-lookup"><span data-stu-id="8178a-173">There are two primary benefits to this:</span></span>

1. <span data-ttu-id="8178a-174">更轻松地根据你的域更改随着时间的推移维护它。</span><span class="sxs-lookup"><span data-stu-id="8178a-174">It is easier to maintain as your domain changes over time.</span></span>
2. <span data-ttu-id="8178a-175">错误情况下是容易进行单元测试。</span><span class="sxs-lookup"><span data-stu-id="8178a-175">Error cases are easier to unit test.</span></span>

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a><span data-ttu-id="8178a-176">当错误不能表示的类型时使用异常</span><span class="sxs-lookup"><span data-stu-id="8178a-176">Use exceptions when errors cannot be represented with types</span></span>

<span data-ttu-id="8178a-177">并非所有的错误可表示问题域中。</span><span class="sxs-lookup"><span data-stu-id="8178a-177">Not all errors can be represented in a problem domain.</span></span> <span data-ttu-id="8178a-178">这些类型的故障*异常*在本质上，因此能够引发和 F# 中捕获异常。</span><span class="sxs-lookup"><span data-stu-id="8178a-178">These kinds of faults are *exceptional* in nature, hence the ability to raise and catch exceptions in F#.</span></span>

<span data-ttu-id="8178a-179">首先，建议先阅读[异常设计准则](../../standard/design-guidelines/exceptions.md)。</span><span class="sxs-lookup"><span data-stu-id="8178a-179">First, it is recommended that you read the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md).</span></span> <span data-ttu-id="8178a-180">它们还适用于 F#。</span><span class="sxs-lookup"><span data-stu-id="8178a-180">These are also applicable to F#.</span></span>

<span data-ttu-id="8178a-181">可在 F# 中用于引发异常的目的的主要构造应考虑按以下顺序的首选项：</span><span class="sxs-lookup"><span data-stu-id="8178a-181">The main constructs available in F# for the purposes of raising exceptions should be considered in the following order of preference:</span></span>

| <span data-ttu-id="8178a-182">函数</span><span class="sxs-lookup"><span data-stu-id="8178a-182">Function</span></span> | <span data-ttu-id="8178a-183">语法</span><span class="sxs-lookup"><span data-stu-id="8178a-183">Syntax</span></span> | <span data-ttu-id="8178a-184">目标</span><span class="sxs-lookup"><span data-stu-id="8178a-184">Purpose</span></span> |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | <span data-ttu-id="8178a-185">引发`System.ArgumentNullException`与指定的参数名称。</span><span class="sxs-lookup"><span data-stu-id="8178a-185">Raises a `System.ArgumentNullException` with the specified argument name.</span></span> |
| `invalidArg` | `invalidArg "argumentName" "message"` | <span data-ttu-id="8178a-186">引发`System.ArgumentException`使用指定的参数名称和消息。</span><span class="sxs-lookup"><span data-stu-id="8178a-186">Raises a `System.ArgumentException` with a specified argument name and message.</span></span> |
| `invalidOp` | `invalidOp "message"` | <span data-ttu-id="8178a-187">引发`System.InvalidOperationException`使用指定的消息。</span><span class="sxs-lookup"><span data-stu-id="8178a-187">Raises a `System.InvalidOperationException` with the specified message.</span></span> |
|`raise`| `raise (ExceptionType("message"))` | <span data-ttu-id="8178a-188">引发异常的通用机制。</span><span class="sxs-lookup"><span data-stu-id="8178a-188">General-purpose mechanism for throwing exceptions.</span></span> |
| `failwith` | `failwith "message"` | <span data-ttu-id="8178a-189">引发`System.Exception`使用指定的消息。</span><span class="sxs-lookup"><span data-stu-id="8178a-189">Raises a `System.Exception` with the specified message.</span></span> |
| `failwithf` | `failwithf "format string" argForFormatString` | <span data-ttu-id="8178a-190">引发`System.Exception`由格式字符串和其输入一条消息。</span><span class="sxs-lookup"><span data-stu-id="8178a-190">Raises a `System.Exception` with a message determined by the format string and its inputs.</span></span> |

<span data-ttu-id="8178a-191">使用`nullArg`，`invalidArg`并`invalidOp`作为机制引发`ArgumentNullException`，`ArgumentException`和`InvalidOperationException`在适当的时候。</span><span class="sxs-lookup"><span data-stu-id="8178a-191">Use `nullArg`, `invalidArg` and `invalidOp` as the mechanism to throw `ArgumentNullException`, `ArgumentException` and `InvalidOperationException` when appropriate.</span></span>

<span data-ttu-id="8178a-192">`failwith`并`failwithf`应通常避免函数，因为它们会引发基`Exception`类型，不特定的异常。</span><span class="sxs-lookup"><span data-stu-id="8178a-192">The `failwith` and `failwithf` functions should generally be avoided because they raise the base `Exception` type, not a specific exception.</span></span> <span data-ttu-id="8178a-193">为每个[异常设计准则](../../standard/design-guidelines/exceptions.md)，你想要时可以引发更具体的异常。</span><span class="sxs-lookup"><span data-stu-id="8178a-193">As per the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md), you want to raise more specific exceptions when you can.</span></span>

### <a name="using-exception-handling-syntax"></a><span data-ttu-id="8178a-194">使用异常处理语法</span><span class="sxs-lookup"><span data-stu-id="8178a-194">Using exception-handling syntax</span></span>

<span data-ttu-id="8178a-195">F# 支持通过异常模式`try...with`语法：</span><span class="sxs-lookup"><span data-stu-id="8178a-195">F# supports exception patterns via the `try...with` syntax:</span></span>

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

<span data-ttu-id="8178a-196">协调遇到模式匹配的异常时执行的功能可能需要一些技巧，如果你想要保持代码干净。</span><span class="sxs-lookup"><span data-stu-id="8178a-196">Reconciling functionality to perform in the face of an exception with pattern matching can be a bit tricky if you wish to keep the code clean.</span></span> <span data-ttu-id="8178a-197">一种此类方法来处理这种情况是使用[活动模式](../language-reference/active-patterns.md)作为一种方式对组功能围绕本身出现异常错误情况。</span><span class="sxs-lookup"><span data-stu-id="8178a-197">One such way to handle this is to use [active patterns](../language-reference/active-patterns.md) as a means to group functionality surrounding an error case with an exception itself.</span></span> <span data-ttu-id="8178a-198">例如，您可能要使用的 API 时将引发异常，异常元数据中包含有价值的信息。</span><span class="sxs-lookup"><span data-stu-id="8178a-198">For example, you may be consuming an API that, when it throws an exception, encloses valuable information in the exception metadata.</span></span> <span data-ttu-id="8178a-199">解包捕获的异常活动模式在正文中有用的值和返回值可以在某些情况下有用。</span><span class="sxs-lookup"><span data-stu-id="8178a-199">Unwrapping a useful value in the body of the captured exception inside the Active Pattern and returning that value can be helpful in some situations.</span></span>

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a><span data-ttu-id="8178a-200">不使用一元错误处理程序来替换异常</span><span class="sxs-lookup"><span data-stu-id="8178a-200">Do not use monadic error handling to replace exceptions</span></span>

<span data-ttu-id="8178a-201">异常被视为某种程度上禁忌在函数式编程。</span><span class="sxs-lookup"><span data-stu-id="8178a-201">Exceptions are seen as somewhat taboo in functional programming.</span></span> <span data-ttu-id="8178a-202">实际上，异常违反纯度，以便安全地将其视为不完全正常工作。</span><span class="sxs-lookup"><span data-stu-id="8178a-202">Indeed, exceptions violate purity, so it's safe to consider them not-quite functional.</span></span> <span data-ttu-id="8178a-203">但是，这会忽略代码必须运行的位置和该运行时，可能会发生错误的实际的情况。</span><span class="sxs-lookup"><span data-stu-id="8178a-203">However, this ignores the reality of where code must run, and that runtime errors can occur.</span></span> <span data-ttu-id="8178a-204">一般情况下，假定大多数内容都是纯和总，尽量少的意外事件都不编写代码。</span><span class="sxs-lookup"><span data-stu-id="8178a-204">In general, write code on the assumption that most things are neither pure nor total, to minimize unpleasant surprises.</span></span>

<span data-ttu-id="8178a-205">请务必考虑以下核心优势/方面的异常相对于其相关性和.NET 运行时和跨语言生态系统中作为一个整体的适合程度：</span><span class="sxs-lookup"><span data-stu-id="8178a-205">It is important to consider the following core strengths/aspects of Exceptions with respect to their relevance and appropriateness in the .NET runtime and cross-language ecosystem as a whole:</span></span>

1. <span data-ttu-id="8178a-206">它们包含详细的诊断信息，这一点非常有用，调试问题时。</span><span class="sxs-lookup"><span data-stu-id="8178a-206">They contain detailed diagnostic information, which is very helpful when debugging an issue.</span></span>
2. <span data-ttu-id="8178a-207">它们是由运行时和其他.NET 语言易于理解。</span><span class="sxs-lookup"><span data-stu-id="8178a-207">They are well-understood by the runtime and other .NET languages.</span></span>
3. <span data-ttu-id="8178a-208">它们可以减少大量样板与超出其方法的代码相比*避免*通过 ad hoc 基础上实现它们的语义的某个子集的异常。</span><span class="sxs-lookup"><span data-stu-id="8178a-208">They can reduce significant boilerplate when compared with code that goes out of its way to *avoid* exceptions by implementing some subset of their semantics on an ad-hoc basis.</span></span>

<span data-ttu-id="8178a-209">此第三个点至关重要。</span><span class="sxs-lookup"><span data-stu-id="8178a-209">This third point is critical.</span></span> <span data-ttu-id="8178a-210">对于重要的复杂操作，无法使用异常会导致处理此类结构：</span><span class="sxs-lookup"><span data-stu-id="8178a-210">For nontrivial complex operations, failing to use exceptions can result in dealing with structures like this:</span></span>

```fsharp
Result<Result<MyType, string>, string list>
```

<span data-ttu-id="8178a-211">这很容易导致脆弱的模式匹配的"stringly 类型化"错误代码：</span><span class="sxs-lookup"><span data-stu-id="8178a-211">Which can easily lead to fragile code like pattern matching on "stringly-typed" errors:</span></span>

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

<span data-ttu-id="8178a-212">此外，它可以是很吸引人，但在返回的"更好"类型的"简单"函数所需的任何异常：</span><span class="sxs-lookup"><span data-stu-id="8178a-212">Additionally, it can be tempting to swallow any exception in the desire for a "simple" function that returns a "nicer" type:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

<span data-ttu-id="8178a-213">遗憾的是，`tryReadAllText`可能会引发大量异常基于在文件系统中，可以发生的事情的各种和此代码会立即丢弃有关可能实际上发生哪些错误在您的环境中的任何信息。</span><span class="sxs-lookup"><span data-stu-id="8178a-213">Unfortunately, `tryReadAllText` can throw numerous exceptions based on the myriad of things that can happen on a file system, and this code discards away any information about what might actually be going wrong in your environment.</span></span> <span data-ttu-id="8178a-214">如果此代码替换为结果类型，然后您返回到"stringly 类型化"错误消息分析：</span><span class="sxs-lookup"><span data-stu-id="8178a-214">If you replace this code with a result type, then you're back to "stringly-typed" error message parsing:</span></span>

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

<span data-ttu-id="8178a-215">并将放入异常对象本身中`Error`构造函数只是强制您能够正确处理在调用站点，而不是在函数中的异常类型。</span><span class="sxs-lookup"><span data-stu-id="8178a-215">And placing the exception object itself in the `Error` constructor just forces you to properly deal with the exception type at the call site rather than in the function.</span></span> <span data-ttu-id="8178a-216">执行此操作有效地创建选中是众所周知 unfun 作为 API 的调用方处理的异常。</span><span class="sxs-lookup"><span data-stu-id="8178a-216">Doing this effectively creates checked exceptions, which are notoriously unfun to deal with as a caller of an API.</span></span>

<span data-ttu-id="8178a-217">与上述示例的良好替代方法是捕捉*特定*异常并返回该异常的上下文中有意义的值。</span><span class="sxs-lookup"><span data-stu-id="8178a-217">A good alternative to the above examples is to catch *specific* exceptions and return a meaningful value in the context of that exception.</span></span> <span data-ttu-id="8178a-218">如果你修改`tryReadAllText`函数，如下所示，`None`具有更多的含义：</span><span class="sxs-lookup"><span data-stu-id="8178a-218">If you modify the `tryReadAllText` function as follows, `None` has more meaning:</span></span>

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

<span data-ttu-id="8178a-219">而不是作为万法归宗正常运行，此函数现在正确地处理这种情况时文件找不到，并将该含义分配给返回。</span><span class="sxs-lookup"><span data-stu-id="8178a-219">Instead of functioning as a catch-all, this function will now properly handle the case when a file was not found and assign that meaning to a return.</span></span> <span data-ttu-id="8178a-220">此返回值可以将映射到错误这种情况下，不放弃任何上下文信息或强制调用方不得不面临可能无法在该点在代码中相关的用例时。</span><span class="sxs-lookup"><span data-stu-id="8178a-220">This return value can map to that error case, while not discarding any contextual information or forcing callers to deal with a case that may not be relevant at that point in the code.</span></span>

<span data-ttu-id="8178a-221">类型，如`Result<'Success, 'Error>`适用于基本操作，其中它们不嵌套和 F# 可选类型非常适合表示当内容无法返回时，*一些*或*nothing*.</span><span class="sxs-lookup"><span data-stu-id="8178a-221">Types such as `Result<'Success, 'Error>` are appropriate for basic operations where they aren't nested, and F# optional types are perfect for representing when something could either return *something* or *nothing*.</span></span> <span data-ttu-id="8178a-222">它们也不能取代有关例外情况，但是，和参数不应尝试使用，以替换异常。</span><span class="sxs-lookup"><span data-stu-id="8178a-222">They are not a replacement for exceptions, though, and should not be used in an attempt to replace exceptions.</span></span> <span data-ttu-id="8178a-223">相反，它们应当应用明智地到地址的异常和错误管理策略的特定方面中目标的方式。</span><span class="sxs-lookup"><span data-stu-id="8178a-223">Rather, they should be applied judiciously to address specific aspects of exception and error management policy in targeted ways.</span></span>

## <a name="partial-application-and-point-free-programming"></a><span data-ttu-id="8178a-224">部分应用程序和无点的编程</span><span class="sxs-lookup"><span data-stu-id="8178a-224">Partial application and point-free programming</span></span>

<span data-ttu-id="8178a-225">F# 无点的方式，支持部分应用程序，因此，不同的方法来计划。</span><span class="sxs-lookup"><span data-stu-id="8178a-225">F# supports partial application, and thus, various ways to program in a point-free style.</span></span> <span data-ttu-id="8178a-226">这会很有用的代码重用在模块或实现的操作，但它通常不是要公开的内容。</span><span class="sxs-lookup"><span data-stu-id="8178a-226">This can be beneficial for code reuse within a module or the implementation of something, but it is generally not something to expose publicly.</span></span> <span data-ttu-id="8178a-227">一般情况下，无点的编程有益本身并不是，并可以添加一个巨大的认知障碍不沉浸在样式中的人员。</span><span class="sxs-lookup"><span data-stu-id="8178a-227">In general, point-free programming is not a virtue in and of itself, and can add a significant cognitive barrier for people who are not immersed in the style.</span></span>

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a><span data-ttu-id="8178a-228">不要使用部分应用程序和科中的公共 Api</span><span class="sxs-lookup"><span data-stu-id="8178a-228">Do not use partial application and currying in public APIs</span></span>

<span data-ttu-id="8178a-229">有一些例外，在公共 Api 中的部分应用程序的用法容易混淆的使用者。</span><span class="sxs-lookup"><span data-stu-id="8178a-229">With little exception, the use of partial application in public APIs can be confusing for consumers.</span></span> <span data-ttu-id="8178a-230">通常情况下， `let`-F# 代码中的绑定的值为**值**，而非**函数值**。</span><span class="sxs-lookup"><span data-stu-id="8178a-230">Usually, `let`-bound values in F# code are **values**, not **function values**.</span></span> <span data-ttu-id="8178a-231">值和函数值，将混合在一起可能会导致保存少量的几行代码来交换一小段认知开销，尤其是与运算符结合使用如`>>`编写函数。</span><span class="sxs-lookup"><span data-stu-id="8178a-231">Mixing together values and function values can result in saving a small number of lines of code in exchange for quite a bit of cognitive overhead, especially if combined with operators such as `>>` to compose functions.</span></span>

### <a name="consider-the-tooling-implications-for-point-free-programming"></a><span data-ttu-id="8178a-232">请考虑无点的编程的工具含义</span><span class="sxs-lookup"><span data-stu-id="8178a-232">Consider the tooling implications for point-free programming</span></span>

<span data-ttu-id="8178a-233">扩充的函数未标记其参数。</span><span class="sxs-lookup"><span data-stu-id="8178a-233">Curried functions do not label their arguments.</span></span> <span data-ttu-id="8178a-234">这会产生工具产生影响。</span><span class="sxs-lookup"><span data-stu-id="8178a-234">This has tooling implications.</span></span> <span data-ttu-id="8178a-235">请考虑以下两个函数：</span><span class="sxs-lookup"><span data-stu-id="8178a-235">Consider the following two functions:</span></span>

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

<span data-ttu-id="8178a-236">两者都是有效的函数，但`funcWithApplication`是扩充的函数。</span><span class="sxs-lookup"><span data-stu-id="8178a-236">Both are valid functions, but `funcWithApplication` is a curried function.</span></span> <span data-ttu-id="8178a-237">当鼠标悬停在其类型在编辑器中时，会看到此：</span><span class="sxs-lookup"><span data-stu-id="8178a-237">When you hover over their types in an editor, you see this:</span></span>

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

<span data-ttu-id="8178a-238">在调用站点，如 Visual Studio 工具中的工具提示将不提供有意义信息关于什么`string`和`int`实际上表示输入的类型。</span><span class="sxs-lookup"><span data-stu-id="8178a-238">At the call site, tooltips in tooling such as Visual Studio will not give you meaningful information as to what the `string` and `int` input types actually represent.</span></span>

<span data-ttu-id="8178a-239">如果遇到类似的点无代码`funcWithApplication`公开使用，建议执行完全的 η 扩展，以便工具可以选择在有意义的自变量的名称。</span><span class="sxs-lookup"><span data-stu-id="8178a-239">If you encounter point-free code like `funcWithApplication` that is publicly consumable, it is recommended to do a full η-expansion so that tooling can pick up on meaningful names for arguments.</span></span>

<span data-ttu-id="8178a-240">此外，调试无点的代码可能相当困难，如果不是不可能。</span><span class="sxs-lookup"><span data-stu-id="8178a-240">Furthermore, debugging point-free code can be challenging, if not impossible.</span></span> <span data-ttu-id="8178a-241">调试工具依赖于绑定到名称的值 (例如，`let`绑定)，以便您可以检查中间值中途执行。</span><span class="sxs-lookup"><span data-stu-id="8178a-241">Debugging tools rely on values bound to names (for example, `let` bindings) so that you can inspect intermediate values midway through execution.</span></span> <span data-ttu-id="8178a-242">当你的代码具有没有要检查的值时，要调试。</span><span class="sxs-lookup"><span data-stu-id="8178a-242">When your code has no values to inspect, there is nothing to debug.</span></span> <span data-ttu-id="8178a-243">将来，调试工具可能会发展为合成基于以前执行路径，这些值，但并不在草木皆兵你一个好办法*潜在*调试功能。</span><span class="sxs-lookup"><span data-stu-id="8178a-243">In the future, debugging tools may evolve to synthesize these values based on previously executed paths, but it's not a good idea to hedge your bets on *potential* debugging functionality.</span></span>

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a><span data-ttu-id="8178a-244">请考虑部分应用程序作为一种技术来减少内部样本</span><span class="sxs-lookup"><span data-stu-id="8178a-244">Consider partial application as a technique to reduce internal boilerplate</span></span>

<span data-ttu-id="8178a-245">与以前的点，部分应用程序是非常棒的工具减少内部应用程序或 API 的更深层次的内部的样本。</span><span class="sxs-lookup"><span data-stu-id="8178a-245">In contrast to the previous point, partial application is a wonderful tool for reducing boilerplate inside of an application or the deeper internals of an API.</span></span> <span data-ttu-id="8178a-246">它可以是有用的单元测试更复杂的 Api，样板通常非常困难不得不面临的实现。</span><span class="sxs-lookup"><span data-stu-id="8178a-246">It can be helpful for unit testing the implementation of more complicated APIs, where boilerplate is often a pain to deal with.</span></span> <span data-ttu-id="8178a-247">例如，下面的代码演示如何可以完成哪些最模拟框架为您提供无需在此类框架使外部依赖关系，而无需了解相关订购 API。</span><span class="sxs-lookup"><span data-stu-id="8178a-247">For example, the following code shows how you can accomplish what most mocking frameworks give you without taking an external dependency on such a framework and having to learn a related bespoke API.</span></span>

<span data-ttu-id="8178a-248">例如，考虑以下解决方案拓扑：</span><span class="sxs-lookup"><span data-stu-id="8178a-248">For example, consider the following solution topography:</span></span>

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

<span data-ttu-id="8178a-249">`ImplementationLogic.fsproj` 例如，可能会公开代码：</span><span class="sxs-lookup"><span data-stu-id="8178a-249">`ImplementationLogic.fsproj` might expose code such as:</span></span>

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member __.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

<span data-ttu-id="8178a-250">单元测试`Transactions.doTransaction`在`ImplementationLogic.Tests.fspoj`很简单：</span><span class="sxs-lookup"><span data-stu-id="8178a-250">Unit testing `Transactions.doTransaction` in `ImplementationLogic.Tests.fspoj` is easy:</span></span>

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

<span data-ttu-id="8178a-251">部分应用`doTransaction`与模拟上下文对象，而无需每次构造模拟的上下文中的所有单元测试都调用该函数可以：</span><span class="sxs-lookup"><span data-stu-id="8178a-251">Partially applying `doTransaction` with a mocking context object lets you call the function in all of your unit tests without needing to construct a mocked context each time:</span></span>

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

<span data-ttu-id="8178a-252">不应将此技术普遍应用到整个代码库，但它是以减少样本的复杂的内部机制和单元测试这些内部结构的好方法。</span><span class="sxs-lookup"><span data-stu-id="8178a-252">This technique should not be universally applied to your entire codebase, but it is a good way to reduce boilerplate for complicated internals and unit testing those internals.</span></span>

## <a name="access-control"></a><span data-ttu-id="8178a-253">访问控制</span><span class="sxs-lookup"><span data-stu-id="8178a-253">Access control</span></span>

<span data-ttu-id="8178a-254">F# 的多个选项[访问控制](../language-reference/access-control.md)继承从所用的.NET 运行时中可用。</span><span class="sxs-lookup"><span data-stu-id="8178a-254">F# has multiple options for [Access control](../language-reference/access-control.md), inherited from what is available in the .NET runtime.</span></span> <span data-ttu-id="8178a-255">这些不是只可用于类型-您也可以使用它们对于函数。</span><span class="sxs-lookup"><span data-stu-id="8178a-255">These are not just usable for types - you can use them for functions, too.</span></span>

* <span data-ttu-id="8178a-256">更喜欢非`public`类型和成员，直到需要它们是公开使用。</span><span class="sxs-lookup"><span data-stu-id="8178a-256">Prefer non-`public` types and members until you need them to be publicly consumable.</span></span> <span data-ttu-id="8178a-257">这还可以尽量降低到哪些使用者几。</span><span class="sxs-lookup"><span data-stu-id="8178a-257">This also minimizes what consumers couple to.</span></span>
* <span data-ttu-id="8178a-258">尽量保证所有帮助器功能`private`。</span><span class="sxs-lookup"><span data-stu-id="8178a-258">Strive to keep all helper functionality `private`.</span></span>
* <span data-ttu-id="8178a-259">请考虑使用`[<AutoOpen>]`上的帮助器函数，如果它们可以大量专用模块。</span><span class="sxs-lookup"><span data-stu-id="8178a-259">Consider the use of `[<AutoOpen>]` on a private module of helper functions if they become numerous.</span></span>

## <a name="type-inference-and-generics"></a><span data-ttu-id="8178a-260">类型推断和泛型</span><span class="sxs-lookup"><span data-stu-id="8178a-260">Type inference and generics</span></span>

<span data-ttu-id="8178a-261">类型推断可以将保存您键入了大量的样板。</span><span class="sxs-lookup"><span data-stu-id="8178a-261">Type inference can save you from typing a lot of boilerplate.</span></span> <span data-ttu-id="8178a-262">在 F# 编译器自动泛化可帮助您编写更为通用的代码几乎没有任何额外的工作量。</span><span class="sxs-lookup"><span data-stu-id="8178a-262">And automatic generalization in the F# compiler can help you write more generic code with almost no extra effort on your part.</span></span> <span data-ttu-id="8178a-263">但是，这些功能不是普遍很好的。</span><span class="sxs-lookup"><span data-stu-id="8178a-263">However, these features are not universally good.</span></span>

* <span data-ttu-id="8178a-264">考虑标签与公共 Api 中的显式类型的参数名称并不依赖此类型推断。</span><span class="sxs-lookup"><span data-stu-id="8178a-264">Consider labeling argument names with explicit types in public APIs and do not rely on type inference for this.</span></span>

    <span data-ttu-id="8178a-265">这样做的原因在于**您**应在你的 API，编译器不该形状的控制。</span><span class="sxs-lookup"><span data-stu-id="8178a-265">The reason for this is that **you** should be in control of the shape of your API, not the compiler.</span></span> <span data-ttu-id="8178a-266">虽然编译器可以执行在推断类型为您的正常作业，就可能有的 API 更改形状，如果它依赖于内部已更改类型。</span><span class="sxs-lookup"><span data-stu-id="8178a-266">Although the compiler can do a fine job at inferring types for you, it is possible to have the shape of your API change if the internals it relies on have changed types.</span></span> <span data-ttu-id="8178a-267">这可能是你想的但几乎可以肯定会导致重大 API 变化的下游使用者然后需要处理。</span><span class="sxs-lookup"><span data-stu-id="8178a-267">This may be what you want, but it will almost certainly result in a breaking API change that downstream consumers will then have to deal with.</span></span> <span data-ttu-id="8178a-268">相反，如果您显式控制公共 API 的形状，则可以控制这些重大更改。</span><span class="sxs-lookup"><span data-stu-id="8178a-268">Instead, if you explicitly control the shape of your public API, then you can control these breaking changes.</span></span> <span data-ttu-id="8178a-269">在 DDD 术语中，这可以认为的防损层。</span><span class="sxs-lookup"><span data-stu-id="8178a-269">In DDD terms, this can be thought of as an Anti-corruption layer.</span></span>

* <span data-ttu-id="8178a-270">请考虑为泛型参数指定有意义的名称。</span><span class="sxs-lookup"><span data-stu-id="8178a-270">Consider giving a meaningful name to your generic arguments.</span></span>

    <span data-ttu-id="8178a-271">除非你正在编写不是特定于特定域的真正泛型代码，有意义的名称可帮助了解的域处于其他程序员。</span><span class="sxs-lookup"><span data-stu-id="8178a-271">Unless you are writing truly generic code that is not specific to a particular domain, a meaningful name can help other programmers understanding the domain they're working in.</span></span> <span data-ttu-id="8178a-272">例如，名为的类型参数`'Document`与文档交互的上下文中数据库中可更清晰通用文档类型，可以接受由函数或正在使用的成员。</span><span class="sxs-lookup"><span data-stu-id="8178a-272">For example, a type parameter named `'Document` in the context of interacting with a document database makes it clearer that generic document types can be accepted by the function or member you are working with.</span></span>

* <span data-ttu-id="8178a-273">请考虑命名使用 pascal 命名法的泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="8178a-273">Consider naming generic type parameters with PascalCase.</span></span>

    <span data-ttu-id="8178a-274">这是常规的方法进行某些操作在.NET 中，因此建议使用 pascal 命名法而不是 snake_case 或驼峰式大小写。</span><span class="sxs-lookup"><span data-stu-id="8178a-274">This is the general way to do things in .NET, so it's recommended that you use PascalCase rather than snake_case or camelCase.</span></span>

<span data-ttu-id="8178a-275">最后，自动泛化并不总是不熟悉 F# 或大型基本代码的人员的一大福音。</span><span class="sxs-lookup"><span data-stu-id="8178a-275">Finally, automatic generalization is not always a boon for people who are new to F# or a large codebase.</span></span> <span data-ttu-id="8178a-276">在使用都是泛型方法的组件则认知开销。</span><span class="sxs-lookup"><span data-stu-id="8178a-276">There is cognitive overhead in using components that are generic.</span></span> <span data-ttu-id="8178a-277">此外，如果自动对不同的输入类型 (let 单独如果他们要这种情况下使用) 不使用通用的函数，就是在该点在时间没有实际的好处。</span><span class="sxs-lookup"><span data-stu-id="8178a-277">Furthermore, if automatically generalized functions are not used with different input types (let alone if they are intended to be used as such), then there is no real benefit to them being generic at that point in time.</span></span> <span data-ttu-id="8178a-278">应始终考虑是否你正在编写的代码将实际上是受益泛型。</span><span class="sxs-lookup"><span data-stu-id="8178a-278">Always consider if the code you are writing will actually benefit from being generic.</span></span>

## <a name="performance"></a><span data-ttu-id="8178a-279">性能</span><span class="sxs-lookup"><span data-stu-id="8178a-279">Performance</span></span>

<span data-ttu-id="8178a-280">F# 的值为默认情况下，你可以避免某些 bug （特别是那些涉及并发和并行度） 的类不可变。</span><span class="sxs-lookup"><span data-stu-id="8178a-280">F# values are immutable by default, which allows you to avoid certain classes of bugs (especially those involving concurrency and parallelism).</span></span> <span data-ttu-id="8178a-281">但是，在某些情况下，为了实现最佳 （或甚至合理） 高效的执行时间或内存分配的工作范围可能最实现使用就地变化的状态。</span><span class="sxs-lookup"><span data-stu-id="8178a-281">However, in certain cases, in order to achieve optimal (or even reasonable) efficiency of execution time or memory allocations, a span of work may best be implemented by using in-place mutation of state.</span></span> <span data-ttu-id="8178a-282">这可在使用 F# 与选择的基础`mutable`关键字。</span><span class="sxs-lookup"><span data-stu-id="8178a-282">This is possible in an opt-in basis with F# with the `mutable` keyword.</span></span>

<span data-ttu-id="8178a-283">但是，使用的`mutable`在 F# 中可能会觉得促使功能纯度。</span><span class="sxs-lookup"><span data-stu-id="8178a-283">However, use of `mutable` in F# may feel at odds with functional purity.</span></span> <span data-ttu-id="8178a-284">这是没问题，如果调整到纯度上的预期[引用透明度](https://en.wikipedia.org/wiki/Referential_transparency)。</span><span class="sxs-lookup"><span data-stu-id="8178a-284">This is fine, if you adjust expectations from purity to [referential transparency](https://en.wikipedia.org/wiki/Referential_transparency).</span></span> <span data-ttu-id="8178a-285">引用透明度-不纯度-时编写 F# 函数中的最终目标。</span><span class="sxs-lookup"><span data-stu-id="8178a-285">Referential transparency - not purity - is the end goal when writing F# functions.</span></span> <span data-ttu-id="8178a-286">这可以通过性能关键代码的变化基于实现编写功能的接口。</span><span class="sxs-lookup"><span data-stu-id="8178a-286">This allows you to write a functional interface over a mutation-based implementation for performance critical code.</span></span>

### <a name="wrap-mutable-code-in-immutable-interfaces"></a><span data-ttu-id="8178a-287">可变代码包装在不可变接口</span><span class="sxs-lookup"><span data-stu-id="8178a-287">Wrap mutable code in immutable interfaces</span></span>

<span data-ttu-id="8178a-288">作为一个目标的引用透明度，与编写代码，不会公开性能关键功能可变 underbelly 至关重要。</span><span class="sxs-lookup"><span data-stu-id="8178a-288">With referential transparency as a goal, it is critical to write code that does not expose the mutable underbelly of performance-critical functions.</span></span> <span data-ttu-id="8178a-289">例如，下面的代码实现`Array.contains`F# 核心库中的函数：</span><span class="sxs-lookup"><span data-stu-id="8178a-289">For example, the following code implements the `Array.contains` function in the F# core library:</span></span>

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

<span data-ttu-id="8178a-290">多次调用此函数不会更改基础数组，也不要求您维护中使用它的任何可变状态。</span><span class="sxs-lookup"><span data-stu-id="8178a-290">Calling this function multiple times does not change the underlying array, nor does it require you to maintain any mutable state in consuming it.</span></span> <span data-ttu-id="8178a-291">它是引用透明的即使的几乎每行代码在其中使用变化。</span><span class="sxs-lookup"><span data-stu-id="8178a-291">It is referentially transparent, even though almost every line of code within it uses mutation.</span></span>

### <a name="consider-encapsulating-mutable-data-in-classes"></a><span data-ttu-id="8178a-292">请考虑封装在类中的可变数据</span><span class="sxs-lookup"><span data-stu-id="8178a-292">Consider encapsulating mutable data in classes</span></span>

<span data-ttu-id="8178a-293">前面的示例使用单个函数来封装操作使用可变的数据。</span><span class="sxs-lookup"><span data-stu-id="8178a-293">The previous example used a single function to encapsulate operations using mutable data.</span></span> <span data-ttu-id="8178a-294">这并不总是能够满足更复杂的数据集。</span><span class="sxs-lookup"><span data-stu-id="8178a-294">This is not always sufficient for more complex sets of data.</span></span> <span data-ttu-id="8178a-295">请考虑以下几组函数：</span><span class="sxs-lookup"><span data-stu-id="8178a-295">Consider the following sets of functions:</span></span>

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

<span data-ttu-id="8178a-296">此代码是高性能，但它会公开调用方负责维护基于变化的数据结构。</span><span class="sxs-lookup"><span data-stu-id="8178a-296">This code is performant, but it exposes the mutation-based data structure that callers are responsible for maintaining.</span></span> <span data-ttu-id="8178a-297">这可以不包含可以更改任何基础成员类内部包装：</span><span class="sxs-lookup"><span data-stu-id="8178a-297">This can be wrapped inside of a class with no underlying members that can change:</span></span>

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

<span data-ttu-id="8178a-298">`Closure1Table` 封装基础的基于变化的数据结构，从而不强制调用方可以维护基础数据结构。</span><span class="sxs-lookup"><span data-stu-id="8178a-298">`Closure1Table` encapsulates the underlying mutation-based data structure, thereby not forcing callers to maintain the underlying data structure.</span></span> <span data-ttu-id="8178a-299">类是封装数据和例程，而无需公开给调用方的详细信息是基于变化的一种强大方法。</span><span class="sxs-lookup"><span data-stu-id="8178a-299">Classes are a powerful way to encapsulate data and routines that are mutation-based without exposing the details to callers.</span></span>

### <a name="prefer-let-mutable-to-reference-cells"></a><span data-ttu-id="8178a-300">更喜欢`let mutable`到引用单元格</span><span class="sxs-lookup"><span data-stu-id="8178a-300">Prefer `let mutable` to reference cells</span></span>

<span data-ttu-id="8178a-301">引用单元格是一种方法来表示对一个值，而不是值本身的引用。</span><span class="sxs-lookup"><span data-stu-id="8178a-301">Reference cells are a way to represent the reference to a value rather than the value itself.</span></span> <span data-ttu-id="8178a-302">虽然它们可以用于性能关键代码，但它们通常不建议。</span><span class="sxs-lookup"><span data-stu-id="8178a-302">Although they can be used for performance-critical code, they are generally not recommended.</span></span> <span data-ttu-id="8178a-303">请看下面的示例：</span><span class="sxs-lookup"><span data-stu-id="8178a-303">Consider the following example:</span></span>

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

<span data-ttu-id="8178a-304">使用引用单元格现在"破坏"与无需取消引用和重新引用基础数据的所有后续代码。</span><span class="sxs-lookup"><span data-stu-id="8178a-304">The use of a reference cell now "pollutes" all subsequent code with having to dereference and re-reference the underlying data.</span></span> <span data-ttu-id="8178a-305">相反，应考虑`let mutable`:</span><span class="sxs-lookup"><span data-stu-id="8178a-305">Instead, consider `let mutable`:</span></span>

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

<span data-ttu-id="8178a-306">除了在 lambda 表达式中间的变化的单个点，所有其他代码的接触`acc`可以在没有任何差别的普通的使用情况的方式操作`let`-绑定不变的值。</span><span class="sxs-lookup"><span data-stu-id="8178a-306">Aside from the single point of mutation in the middle of the lambda expression, all other code that touches `acc` can do so in a manner that is no different to the usage of a normal `let`-bound immutable value.</span></span> <span data-ttu-id="8178a-307">这将使更轻松地随时间而变化。</span><span class="sxs-lookup"><span data-stu-id="8178a-307">This will make it easier to change over time.</span></span>

## <a name="object-programming"></a><span data-ttu-id="8178a-308">对象编程</span><span class="sxs-lookup"><span data-stu-id="8178a-308">Object programming</span></span>

<span data-ttu-id="8178a-309">F# 具有对对象和面向对象的 (OO) 概念的完整支持。</span><span class="sxs-lookup"><span data-stu-id="8178a-309">F# has full support for objects and object-oriented (OO) concepts.</span></span> <span data-ttu-id="8178a-310">尽管许多 OO 概念是功能强大且有用，但并非所有这些都使用的理想之选。</span><span class="sxs-lookup"><span data-stu-id="8178a-310">Although many OO concepts are powerful and useful, not all of them are ideal to use.</span></span> <span data-ttu-id="8178a-311">以下列表提供类别在高级别 OO 功能的指导。</span><span class="sxs-lookup"><span data-stu-id="8178a-311">The following lists offer guidance on categories of OO features at a high level.</span></span>

<span data-ttu-id="8178a-312">**请考虑在许多情况下使用这些功能：**</span><span class="sxs-lookup"><span data-stu-id="8178a-312">**Consider using these features in many situations:**</span></span>

* <span data-ttu-id="8178a-313">点表示法 (`x.Length`)</span><span class="sxs-lookup"><span data-stu-id="8178a-313">Dot notation (`x.Length`)</span></span>
* <span data-ttu-id="8178a-314">实例成员</span><span class="sxs-lookup"><span data-stu-id="8178a-314">Instance members</span></span>
* <span data-ttu-id="8178a-315">隐式构造函数</span><span class="sxs-lookup"><span data-stu-id="8178a-315">Implicit constructors</span></span>
* <span data-ttu-id="8178a-316">静态成员</span><span class="sxs-lookup"><span data-stu-id="8178a-316">Static members</span></span>
* <span data-ttu-id="8178a-317">索引器表示法 (`arr.[x]`)</span><span class="sxs-lookup"><span data-stu-id="8178a-317">Indexer notation (`arr.[x]`)</span></span>
* <span data-ttu-id="8178a-318">命名实参和可选实参</span><span class="sxs-lookup"><span data-stu-id="8178a-318">Named and Optional arguments</span></span>
* <span data-ttu-id="8178a-319">接口和接口实现</span><span class="sxs-lookup"><span data-stu-id="8178a-319">Interfaces and interface implementations</span></span>

<span data-ttu-id="8178a-320">**不会到达这些功能的第一次，但请谨慎应用它们时才可以方便地解决问题：**</span><span class="sxs-lookup"><span data-stu-id="8178a-320">**Don't reach for these features first, but do judiciously apply them when they are convenient to solve a problem:**</span></span>

* <span data-ttu-id="8178a-321">方法重载</span><span class="sxs-lookup"><span data-stu-id="8178a-321">Method overloading</span></span>
* <span data-ttu-id="8178a-322">封装的可变数据</span><span class="sxs-lookup"><span data-stu-id="8178a-322">Encapsulated mutable data</span></span>
* <span data-ttu-id="8178a-323">类型运算符</span><span class="sxs-lookup"><span data-stu-id="8178a-323">Operators on types</span></span>
* <span data-ttu-id="8178a-324">自动属性</span><span class="sxs-lookup"><span data-stu-id="8178a-324">Auto properties</span></span>
* <span data-ttu-id="8178a-325">实现`IDisposable`和 `IEnumerable`</span><span class="sxs-lookup"><span data-stu-id="8178a-325">Implementing `IDisposable` and `IEnumerable`</span></span>
* <span data-ttu-id="8178a-326">类型扩展</span><span class="sxs-lookup"><span data-stu-id="8178a-326">Type extensions</span></span>
* <span data-ttu-id="8178a-327">事件</span><span class="sxs-lookup"><span data-stu-id="8178a-327">Events</span></span>
* <span data-ttu-id="8178a-328">结构</span><span class="sxs-lookup"><span data-stu-id="8178a-328">Structs</span></span>
* <span data-ttu-id="8178a-329">委托</span><span class="sxs-lookup"><span data-stu-id="8178a-329">Delegates</span></span>
* <span data-ttu-id="8178a-330">枚举</span><span class="sxs-lookup"><span data-stu-id="8178a-330">Enums</span></span>

<span data-ttu-id="8178a-331">**除非您必须将它们通常避免这些功能：**</span><span class="sxs-lookup"><span data-stu-id="8178a-331">**Generally avoid these features unless you must use them:**</span></span>

* <span data-ttu-id="8178a-332">基于继承的类型层次结构和实现继承</span><span class="sxs-lookup"><span data-stu-id="8178a-332">Inheritance-based type hierarchies and implementation inheritance</span></span>
* <span data-ttu-id="8178a-333">Null 值和 `Unchecked.defaultof<_>`</span><span class="sxs-lookup"><span data-stu-id="8178a-333">Nulls and `Unchecked.defaultof<_>`</span></span>

### <a name="prefer-composition-over-inheritance"></a><span data-ttu-id="8178a-334">组合为首继承</span><span class="sxs-lookup"><span data-stu-id="8178a-334">Prefer composition over inheritance</span></span>

<span data-ttu-id="8178a-335">[通过继承复合](https://en.wikipedia.org/wiki/Composition_over_inheritance)是良好的 F# 代码可以遵循一个长期惯例。</span><span class="sxs-lookup"><span data-stu-id="8178a-335">[Composition over inheritance](https://en.wikipedia.org/wiki/Composition_over_inheritance) is a long-standing idiom that good F# code can adhere to.</span></span> <span data-ttu-id="8178a-336">基本原则是，不应公开的基类，强制调用方继承该基类可以实现功能。</span><span class="sxs-lookup"><span data-stu-id="8178a-336">The fundamental principle is that you should not expose a base class and force callers to inherit from that base class to get functionality.</span></span>

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a><span data-ttu-id="8178a-337">使用对象表达式实现接口，如果您不需要一个类</span><span class="sxs-lookup"><span data-stu-id="8178a-337">Use object expressions to implement interfaces if you don't need a class</span></span>

<span data-ttu-id="8178a-338">[对象表达式](../language-reference/object-expressions.md)可用于快速实现接口在无需执行此操作类内部实现的接口绑定到的值。</span><span class="sxs-lookup"><span data-stu-id="8178a-338">[Object Expressions](../language-reference/object-expressions.md) allow you to implement interfaces on the fly, binding the implemented interface to a value without needing to do so inside of a class.</span></span> <span data-ttu-id="8178a-339">这很方便，尤其是当您_仅_需要实现接口并不需要完整的类。</span><span class="sxs-lookup"><span data-stu-id="8178a-339">This is convenient, especially if you _only_ need to implement the interface and have no need for a full class.</span></span>

<span data-ttu-id="8178a-340">例如，下面是在中运行的代码[Ionide](http://ionide.io/)提供的代码修复操作，如果你已添加没有的符号`open`语句：</span><span class="sxs-lookup"><span data-stu-id="8178a-340">For example, here is the code that is run in [Ionide](http://ionide.io/) to provide a code fix action if you've added a symbol that you don't have an `open` statement for:</span></span>

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

<span data-ttu-id="8178a-341">由于没有为类无需与 Visual Studio Code API 进行交互时，对象表达式是对此的理想工具。</span><span class="sxs-lookup"><span data-stu-id="8178a-341">Because there is no need for a class when interacting with the Visual Studio Code API, Object Expressions are an ideal tool for this.</span></span> <span data-ttu-id="8178a-342">它们也是有价值的单元测试，如果想要进行存根处理出测试例程的接口中特别的方式。</span><span class="sxs-lookup"><span data-stu-id="8178a-342">They are also valuable for unit testing, when you want to stub out an interface with test routines in an ad hoc manner.</span></span>

## <a name="type-abbreviations"></a><span data-ttu-id="8178a-343">类型缩写</span><span class="sxs-lookup"><span data-stu-id="8178a-343">Type Abbreviations</span></span>

<span data-ttu-id="8178a-344">[类型缩写，用](../language-reference/type-abbreviations.md)是要将标签分配到另一个类型，例如函数签名或更复杂类型的简便方法。</span><span class="sxs-lookup"><span data-stu-id="8178a-344">[Type Abbreviations](../language-reference/type-abbreviations.md) are a convenient way to assign a label to another type, such as a function signature or a more complex type.</span></span> <span data-ttu-id="8178a-345">例如，以下别名将标签分配给所需定义与计算[CNTK](https://www.microsoft.com/en-us/cognitive-toolkit/)、 深度学习库：</span><span class="sxs-lookup"><span data-stu-id="8178a-345">For example, the following alias assigns a label to what's needed to define a computation with [CNTK](https://www.microsoft.com/en-us/cognitive-toolkit/), a deep learning library:</span></span>

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

<span data-ttu-id="8178a-346">`Computation`名称是以表示它是别名的签名匹配的任何函数的简便方法。</span><span class="sxs-lookup"><span data-stu-id="8178a-346">The `Computation` name is a convenient way to denote any function that matches the signature it is aliasing.</span></span> <span data-ttu-id="8178a-347">使用此类类型缩写方便，且允许更简洁的代码。</span><span class="sxs-lookup"><span data-stu-id="8178a-347">Using Type Abbreviations like this is convenient and allows for more succinct code.</span></span>

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a><span data-ttu-id="8178a-348">避免使用类型缩写来表示你的域</span><span class="sxs-lookup"><span data-stu-id="8178a-348">Avoid using Type Abbreviations to represent your domain</span></span>

<span data-ttu-id="8178a-349">尽管类型缩写便于到函数签名中提供一个名称，但它们可以是令人困惑时缩写加上其他类型。</span><span class="sxs-lookup"><span data-stu-id="8178a-349">Although Type Abbreviations are convenient for giving a name to function signatures, they can be confusing when abbreviating other types.</span></span> <span data-ttu-id="8178a-350">请考虑此缩写：</span><span class="sxs-lookup"><span data-stu-id="8178a-350">Consider this abbreviation:</span></span>

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

<span data-ttu-id="8178a-351">这可以是令人困惑，在多个方面：</span><span class="sxs-lookup"><span data-stu-id="8178a-351">This can be confusing in multiple ways:</span></span>

* <span data-ttu-id="8178a-352">`BufferSize` 不是一个抽象概念。它是整数的只是另一个名称。</span><span class="sxs-lookup"><span data-stu-id="8178a-352">`BufferSize` is not an abstraction; it is just another name for an integer.</span></span>
* <span data-ttu-id="8178a-353">如果`BufferSize`公开在公共 API 中，它可以轻松地被错误地解释不止是表示`int`。</span><span class="sxs-lookup"><span data-stu-id="8178a-353">If `BufferSize` is exposed in a public API, it can easily be misinterpreted to mean more than just `int`.</span></span> <span data-ttu-id="8178a-354">通常情况下，域类型具有多个属性到它们并不是基元类型，如`int`。</span><span class="sxs-lookup"><span data-stu-id="8178a-354">Generally, domain types have multiple attributes to them and are not primitive types like `int`.</span></span> <span data-ttu-id="8178a-355">此缩写违反了这种假设。</span><span class="sxs-lookup"><span data-stu-id="8178a-355">This abbreviation violates that assumption.</span></span>
* <span data-ttu-id="8178a-356">大小写`BufferSize`（pascal 命名法） 意味着此类型包含更多的数据。</span><span class="sxs-lookup"><span data-stu-id="8178a-356">The casing of `BufferSize` (PascalCase) implies that this type holds more data.</span></span>
* <span data-ttu-id="8178a-357">此别名不提供与提供的函数的命名的参数进行比较时会更加的明确。</span><span class="sxs-lookup"><span data-stu-id="8178a-357">This alias does not offer increased clarity compared with providing a named argument to a function.</span></span>
* <span data-ttu-id="8178a-358">缩写不将清单中已编译 IL;它是只是一个整数，此别名是编译时构造。</span><span class="sxs-lookup"><span data-stu-id="8178a-358">The abbreviation will not manifest in compiled IL; it is just an integer and this alias is a compile-time construct.</span></span>

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) =
        ...
```

<span data-ttu-id="8178a-359">总之，与类型缩写缺陷是它们**不**抽象概念通过它们缩写加上的类型。</span><span class="sxs-lookup"><span data-stu-id="8178a-359">In summary, the pitfall with Type Abbreviations is that they are **not** abstractions over the types they are abbreviating.</span></span> <span data-ttu-id="8178a-360">在上一示例中，`BufferSize`只是`int`事实上，与任何其他数据，也不从除了什么类型系统的任何权益`int`已有。</span><span class="sxs-lookup"><span data-stu-id="8178a-360">In the previous example, `BufferSize` is just an `int` under the covers, with no additional data, nor any benefits from the type system besides what `int` already has.</span></span>
