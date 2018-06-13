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
# <a name="f-coding-conventions"></a><span data-ttu-id="0d223-103">F # 编码约定</span><span class="sxs-lookup"><span data-stu-id="0d223-103">F# coding conventions</span></span>

<span data-ttu-id="0d223-104">以下约定表述从大型 F # 使用经验基本代码。</span><span class="sxs-lookup"><span data-stu-id="0d223-104">The following conventions are formulated from experience working with large F# codebases.</span></span> <span data-ttu-id="0d223-105">[的良好的 F # 代码的五个原则](index.md#five-principles-of-good-f-code)每一项建议的基础。</span><span class="sxs-lookup"><span data-stu-id="0d223-105">The [Five principles of good F# code](index.md#five-principles-of-good-f-code) are the foundation of each recommendation.</span></span> <span data-ttu-id="0d223-106">与相关[F # 组件设计准则](component-design-guidelines.md)，但适用于任何 F # 代码，而不仅仅是组件，如库。</span><span class="sxs-lookup"><span data-stu-id="0d223-106">They are related to the [F# component design guidelines](component-design-guidelines.md), but are applicable for any F# code, not just components such as libraries.</span></span>

## <a name="organizing-code"></a><span data-ttu-id="0d223-107">组织代码</span><span class="sxs-lookup"><span data-stu-id="0d223-107">Organizing code</span></span>

<span data-ttu-id="0d223-108">F # 功能两种主要方式将代码组织： 模块和命名空间。</span><span class="sxs-lookup"><span data-stu-id="0d223-108">F# features two primary ways to organize code: modules and namespaces.</span></span> <span data-ttu-id="0d223-109">其中相似，但不要有以下不同：</span><span class="sxs-lookup"><span data-stu-id="0d223-109">These are similar, but do have the following differences:</span></span>

* <span data-ttu-id="0d223-110">命名空间是.NET 命名空间作为编译的。</span><span class="sxs-lookup"><span data-stu-id="0d223-110">Namespaces are compiled as .NET namespaces.</span></span> <span data-ttu-id="0d223-111">静态类作为编译的模块。</span><span class="sxs-lookup"><span data-stu-id="0d223-111">Modules are compiled as static classes.</span></span>
* <span data-ttu-id="0d223-112">命名空间始终是最高级别。</span><span class="sxs-lookup"><span data-stu-id="0d223-112">Namespaces are always top level.</span></span> <span data-ttu-id="0d223-113">模块可以是顶级和嵌套在其他模块内。</span><span class="sxs-lookup"><span data-stu-id="0d223-113">Modules can be top-level and nested within other modules.</span></span>
* <span data-ttu-id="0d223-114">命名空间可以跨多个文件。</span><span class="sxs-lookup"><span data-stu-id="0d223-114">Namespaces can span multiple files.</span></span> <span data-ttu-id="0d223-115">模块不能。</span><span class="sxs-lookup"><span data-stu-id="0d223-115">Modules cannot.</span></span>
* <span data-ttu-id="0d223-116">可以使用修饰模块`[<RequireQualifiedAccess>]`和`[<AutoOpen>]`。</span><span class="sxs-lookup"><span data-stu-id="0d223-116">Modules can be decorated with `[<RequireQualifiedAccess>]` and `[<AutoOpen>]`.</span></span>

<span data-ttu-id="0d223-117">以下准则将帮助你使用它们来组织代码。</span><span class="sxs-lookup"><span data-stu-id="0d223-117">The following guidelines will help you use these to organize your code.</span></span>

### <a name="prefer-namespaces-at-the-top-level"></a><span data-ttu-id="0d223-118">选择最高级别的命名空间</span><span class="sxs-lookup"><span data-stu-id="0d223-118">Prefer namespaces at the top level</span></span>

<span data-ttu-id="0d223-119">对于任何公开可使用的代码，命名空间是到最高级别模块享受优惠。</span><span class="sxs-lookup"><span data-stu-id="0d223-119">For any publicly consumable code, namespaces are preferential to modules at the top level.</span></span> <span data-ttu-id="0d223-120">由于它们.NET 命名空间作为编译的它们是可以从 C# 没有问题。</span><span class="sxs-lookup"><span data-stu-id="0d223-120">Because they are compiled as .NET namespaces, they are consumable from C# with no issue.</span></span>

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

<span data-ttu-id="0d223-121">使用顶级模块可能不会显示不同时只能从 F # 中，但对于 C# 用户来说，调用方可能会对感到惊讶通过无需限定`MyClass`与`MyCode`模块。</span><span class="sxs-lookup"><span data-stu-id="0d223-121">Using a top-level module may not appear different when called only from F#, but for C# consumers, callers may be surprised by having to qualify `MyClass` with the `MyCode` module.</span></span>

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a><span data-ttu-id="0d223-122">仔细应用 `[<AutoOpen>]`</span><span class="sxs-lookup"><span data-stu-id="0d223-122">Carefully apply `[<AutoOpen>]`</span></span>

<span data-ttu-id="0d223-123">`[<AutoOpen>]`构造可以会污染向调用方，可用的作用域和内容来自问题的回答是"神奇"。</span><span class="sxs-lookup"><span data-stu-id="0d223-123">The `[<AutoOpen>]` construct can pollute the scope of what is available to callers, and the answer to where something comes from is "magic".</span></span> <span data-ttu-id="0d223-124">这通常不是一件好事。</span><span class="sxs-lookup"><span data-stu-id="0d223-124">This is generally not a good thing.</span></span> <span data-ttu-id="0d223-125">此规则的例外是在 F # 核心库自身 （尽管这种情况也是稍有争议的）。</span><span class="sxs-lookup"><span data-stu-id="0d223-125">An exception to this rule is the F# Core Library itself (though this fact is also a bit controversial).</span></span>

<span data-ttu-id="0d223-126">但是，它是一种便于，如果你有一个公共 API，你希望组织单独从该公共 API 帮助程序功能。</span><span class="sxs-lookup"><span data-stu-id="0d223-126">However, it is a convenience if you have helper functionality for a public API that you wish to organize separately from that public API.</span></span>

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

<span data-ttu-id="0d223-127">这样就可以从一个函数的公共 API 的完全单独实现详细信息而无需每次调用该函数的完全限定程序的帮助。</span><span class="sxs-lookup"><span data-stu-id="0d223-127">This lets you cleanly separate implementation details from the public API of a function without having to fully qualify a helper each time you call it.</span></span>

<span data-ttu-id="0d223-128">此外，公开扩展方法和表达式生成器的命名空间级别可以巧妙地表示与`[<AutoOpen>]`。</span><span class="sxs-lookup"><span data-stu-id="0d223-128">Additionally, exposing extension methods and expression builders at the namespace level can be neatly expressed with `[<AutoOpen>]`.</span></span>

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a><span data-ttu-id="0d223-129">使用`[<RequireQualifiedAccess>]`每当名称无法冲突，或者你认为它是帮助可读性</span><span class="sxs-lookup"><span data-stu-id="0d223-129">Use `[<RequireQualifiedAccess>]` whenever names could conflict or you feel it helps with readability</span></span>

<span data-ttu-id="0d223-130">添加`[<RequireQualifiedAccess>]`模块的属性指示模块可能无法打开，并对该模块的元素的引用，需要显式限定访问权限。</span><span class="sxs-lookup"><span data-stu-id="0d223-130">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="0d223-131">例如，`Microsoft.FSharp.Collections.List`模块具有此属性。</span><span class="sxs-lookup"><span data-stu-id="0d223-131">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="0d223-132">时函数和模块中的值可能与其他模块中的名称发生冲突的名称，这会很有用。</span><span class="sxs-lookup"><span data-stu-id="0d223-132">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="0d223-133">需限定的访问会大大增加的长期的可维护性和 evolvability 的库。</span><span class="sxs-lookup"><span data-stu-id="0d223-133">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a><span data-ttu-id="0d223-134">排序`open`语句拓扑结构上</span><span class="sxs-lookup"><span data-stu-id="0d223-134">Sort `open` statements topologically</span></span>

<span data-ttu-id="0d223-135">在 F # 中，声明的顺序非常重要，包括`open`语句。</span><span class="sxs-lookup"><span data-stu-id="0d223-135">In F#, the order of declarations matters, including with `open` statements.</span></span> <span data-ttu-id="0d223-136">这是与 C# 中，其中的效果`using`和`using static`无关的文件中的这些语句的顺序。</span><span class="sxs-lookup"><span data-stu-id="0d223-136">This is unlike C#, where the effect of `using` and `using static` is independent of the ordering of those statements in a file.</span></span>

<span data-ttu-id="0d223-137">在 F # 中，打开到作用域中的元素可以隐藏其他人已存在。</span><span class="sxs-lookup"><span data-stu-id="0d223-137">In F#, elements opened into a scope can shadow others already present.</span></span> <span data-ttu-id="0d223-138">这意味着该重新排序`open`语句无法更改代码的含义。</span><span class="sxs-lookup"><span data-stu-id="0d223-138">This means that reordering `open` statements could alter the meaning of code.</span></span> <span data-ttu-id="0d223-139">因此，任何任意排序的所有`open`语句 （例如，根据） 通常不建议，以免生成不同的行为，你预期的。</span><span class="sxs-lookup"><span data-stu-id="0d223-139">As a result, any arbitrary sorting of all `open` statements (for example, alphanumerically) is generally not recommended, lest you generate different behavior that you might expect.</span></span>

<span data-ttu-id="0d223-140">相反，我们建议您进行排序它们[拓扑结构上](https://en.wikipedia.org/wiki/Topological_sorting); 即，排序你`open`中的顺序的语句_层_定义你的系统。</span><span class="sxs-lookup"><span data-stu-id="0d223-140">Instead, we recommend that you sort them [topologically](https://en.wikipedia.org/wiki/Topological_sorting); that is, order your `open` statements in the order in which _layers_ of your system are defined.</span></span> <span data-ttu-id="0d223-141">也可以考虑不同的拓扑图层内的排序字母数字。</span><span class="sxs-lookup"><span data-stu-id="0d223-141">Doing alphanumeric sorting within different topological layers may also be considered.</span></span>

<span data-ttu-id="0d223-142">例如，下面是拓扑排序的 F # 编译器服务公共 API 文件：</span><span class="sxs-lookup"><span data-stu-id="0d223-142">As an example, here is the topological sorting for the F# compiler service public API file:</span></span>

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

<span data-ttu-id="0d223-143">请注意，一个分行符将分开的拓扑图层，每个层正在排序进行排序之后。</span><span class="sxs-lookup"><span data-stu-id="0d223-143">Note that a line break separates topological layers, with each layer being sorted alphanumerically afterwards.</span></span> <span data-ttu-id="0d223-144">这完全不会意外地隐藏值的情况下组织代码。</span><span class="sxs-lookup"><span data-stu-id="0d223-144">This cleanly organizes code without accidentally shadowing values.</span></span>

## <a name="use-classes-to-contain-values-that-have-side-effects"></a><span data-ttu-id="0d223-145">使用类来包含具有副作用的值</span><span class="sxs-lookup"><span data-stu-id="0d223-145">Use classes to contain values that have side effects</span></span>

<span data-ttu-id="0d223-146">很多时候当初始化值可能会有副作用，如实例化到数据库或其他远程资源的上下文。</span><span class="sxs-lookup"><span data-stu-id="0d223-146">There are many times when initializing a value can have side effects, such as instantiating a context to a database or other remote resource.</span></span> <span data-ttu-id="0d223-147">它很容易初始化之类模块中的内容并将其用于后续的函数：</span><span class="sxs-lookup"><span data-stu-id="0d223-147">It is tempting to initialize such things in a module and use it in subsequent functions:</span></span>

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

<span data-ttu-id="0d223-148">这通常是个好主意原因有多种：</span><span class="sxs-lookup"><span data-stu-id="0d223-148">This is frequently a bad idea for a few reasons:</span></span>

<span data-ttu-id="0d223-149">首先，应用程序配置被推入到与基本代码`dep1`和`dep2`。</span><span class="sxs-lookup"><span data-stu-id="0d223-149">First, application configuration is pushed into the codebase with `dep1` and `dep2`.</span></span> <span data-ttu-id="0d223-150">这是难以维护在更大的基本代码。</span><span class="sxs-lookup"><span data-stu-id="0d223-150">This is difficult to maintain in larger codebases.</span></span>

<span data-ttu-id="0d223-151">第二个、 静态初始化的数据不应包含不是线程安全，如果你的组件将本身使用多个线程的值。</span><span class="sxs-lookup"><span data-stu-id="0d223-151">Second, statically initialized data should not include values that are not thread safe if your component will itself use multiple threads.</span></span> <span data-ttu-id="0d223-152">这通过清楚地违反了`dep3`。</span><span class="sxs-lookup"><span data-stu-id="0d223-152">This is clearly violated by `dep3`.</span></span>

<span data-ttu-id="0d223-153">最后，初始化模块将编译到一个静态构造函数为整个编译单元。</span><span class="sxs-lookup"><span data-stu-id="0d223-153">Finally, module initialization compiles into a static constructor for the entire compilation unit.</span></span> <span data-ttu-id="0d223-154">如果该模块中的 let 绑定值初始化发生任何错误时，表现为`TypeInitializationException`，然后缓存应用程序的整个生存期内。</span><span class="sxs-lookup"><span data-stu-id="0d223-154">If any error occurs in let-bound value initialization in that module, it manifests as a `TypeInitializationException` that is then cached for the entire lifetime of the application.</span></span> <span data-ttu-id="0d223-155">这可能很难诊断。</span><span class="sxs-lookup"><span data-stu-id="0d223-155">This can be difficult to diagnose.</span></span> <span data-ttu-id="0d223-156">通常没有内部异常，则可以尝试以解释的但如果没有，则没有的根本原因无法区分。</span><span class="sxs-lookup"><span data-stu-id="0d223-156">There is usually an inner exception that you can attempt to reason about, but if there is not, then there is no telling what the root cause is.</span></span>

<span data-ttu-id="0d223-157">相反，只需使用一个简单的类来保存依赖关系：</span><span class="sxs-lookup"><span data-stu-id="0d223-157">Instead, just use a simple class to hold dependencies:</span></span>

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member __.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member __.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

<span data-ttu-id="0d223-158">这可实现以下目的：</span><span class="sxs-lookup"><span data-stu-id="0d223-158">This enables the following:</span></span>

1. <span data-ttu-id="0d223-159">将推送用 API 自身之外的任何依赖状态。</span><span class="sxs-lookup"><span data-stu-id="0d223-159">Pushing any dependent state outside of the API itself.</span></span>
2. <span data-ttu-id="0d223-160">现在可以在 API 之外执行配置。</span><span class="sxs-lookup"><span data-stu-id="0d223-160">Configuration can now be done outside of the API.</span></span>
3. <span data-ttu-id="0d223-161">在依赖值的初始化错误不是可能会表现为`TypeInitializationException`。</span><span class="sxs-lookup"><span data-stu-id="0d223-161">Errors in initialization for dependent values are not likely to manifest as a `TypeInitializationException`.</span></span>
4. <span data-ttu-id="0d223-162">此 API 现可以轻松地测试。</span><span class="sxs-lookup"><span data-stu-id="0d223-162">The API is now easier to test.</span></span>

## <a name="error-management"></a><span data-ttu-id="0d223-163">错误管理</span><span class="sxs-lookup"><span data-stu-id="0d223-163">Error management</span></span>

<span data-ttu-id="0d223-164">大型系统中的错误管理是一项复杂且一些略有区别的任务，并且没有中确保你的系统的项目符号是容错和行为也没有白银。</span><span class="sxs-lookup"><span data-stu-id="0d223-164">Error management in large systems is a complex and nuanced endeavor, and there are no silver bullets in ensuring your systems are fault-tolerant and behave well.</span></span> <span data-ttu-id="0d223-165">以下指南应提供的指南在浏览此困难的空间。</span><span class="sxs-lookup"><span data-stu-id="0d223-165">The following guidelines should offer guidance in navigating this difficult space.</span></span>

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a><span data-ttu-id="0d223-166">表示错误情况和中固有的你的域的类型非法状态</span><span class="sxs-lookup"><span data-stu-id="0d223-166">Represent error cases and illegal state in types intrinsic to your domain</span></span>

<span data-ttu-id="0d223-167">与[可区分联合](../language-reference/discriminated-unions.md)，F # 使你能够在类型系统中表示发生故障的程序状态。</span><span class="sxs-lookup"><span data-stu-id="0d223-167">With [Discriminated Unions](../language-reference/discriminated-unions.md), F# gives you the ability to represent faulty program state in your type system.</span></span> <span data-ttu-id="0d223-168">例如：</span><span class="sxs-lookup"><span data-stu-id="0d223-168">For example:</span></span>

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

<span data-ttu-id="0d223-169">在这种情况下，有三种已知的方式从银行帐户中取出 money 可能会失败。</span><span class="sxs-lookup"><span data-stu-id="0d223-169">In this case, there are three known ways that withdrawing money from a bank account can fail.</span></span> <span data-ttu-id="0d223-170">每个错误用例表示在类型中，并可以因此得到处理安全地在整个程序。</span><span class="sxs-lookup"><span data-stu-id="0d223-170">Each error case is represented in the type, and can thus be dealt with safely throughout the program.</span></span>

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

<span data-ttu-id="0d223-171">一般情况下，如果你可以对不同的方式进行建模问题可以**失败**在你的域，然后错误处理代码将被不再视为内容必须除了常规程序流处理。</span><span class="sxs-lookup"><span data-stu-id="0d223-171">In general, if you can model the different ways that something can **fail** in your domain, then error handling code is no longer treated as something you must deal with in addition to regular program flow.</span></span> <span data-ttu-id="0d223-172">它是只需正常程序流的一部分，不被视为**异常**。</span><span class="sxs-lookup"><span data-stu-id="0d223-172">It is simply a part of normal program flow, and not considered **exceptional**.</span></span> <span data-ttu-id="0d223-173">有这两个主要好处：</span><span class="sxs-lookup"><span data-stu-id="0d223-173">There are two primary benefits to this:</span></span>

1. <span data-ttu-id="0d223-174">很容易地保持你的域随着时间推移而变化。</span><span class="sxs-lookup"><span data-stu-id="0d223-174">It is easier to maintain as your domain changes over time.</span></span>
2. <span data-ttu-id="0d223-175">错误情况下更易于进行单元测试。</span><span class="sxs-lookup"><span data-stu-id="0d223-175">Error cases are easier to unit test.</span></span>

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a><span data-ttu-id="0d223-176">当错误不能用类型来表示使用异常</span><span class="sxs-lookup"><span data-stu-id="0d223-176">Use exceptions when errors cannot be represented with types</span></span>

<span data-ttu-id="0d223-177">可以在问题域中表示不是所有错误。</span><span class="sxs-lookup"><span data-stu-id="0d223-177">Not all errors can be represented in a problem domain.</span></span> <span data-ttu-id="0d223-178">这些类型的错误是*异常*性质，因此中引发和捕获异常，F # 中的功能。</span><span class="sxs-lookup"><span data-stu-id="0d223-178">These kinds of faults are *exceptional* in nature, hence the ability to raise and catch exceptions in F#.</span></span>

<span data-ttu-id="0d223-179">首先，建议你阅读[异常设计准则](../../standard/design-guidelines/exceptions.md)。</span><span class="sxs-lookup"><span data-stu-id="0d223-179">First, it is recommended that you read the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md).</span></span> <span data-ttu-id="0d223-180">这些是还适用于 F #。</span><span class="sxs-lookup"><span data-stu-id="0d223-180">These are also applicable to F#.</span></span>

<span data-ttu-id="0d223-181">按以下顺序的首选项，应考虑出于引发异常的 F # 中可用的主要构造：</span><span class="sxs-lookup"><span data-stu-id="0d223-181">The main constructs available in F# for the purposes of raising exceptions should be considered in the following order of preference:</span></span>

| <span data-ttu-id="0d223-182">函数</span><span class="sxs-lookup"><span data-stu-id="0d223-182">Function</span></span> | <span data-ttu-id="0d223-183">语法</span><span class="sxs-lookup"><span data-stu-id="0d223-183">Syntax</span></span> | <span data-ttu-id="0d223-184">目标</span><span class="sxs-lookup"><span data-stu-id="0d223-184">Purpose</span></span> |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | <span data-ttu-id="0d223-185">引发`System.ArgumentNullException`与指定的参数名称。</span><span class="sxs-lookup"><span data-stu-id="0d223-185">Raises a `System.ArgumentNullException` with the specified argument name.</span></span> |
| `invalidArg` | `invalidArg "argumentName" "message"` | <span data-ttu-id="0d223-186">引发`System.ArgumentException`使用指定的参数名称和消息。</span><span class="sxs-lookup"><span data-stu-id="0d223-186">Raises a `System.ArgumentException` with a specified argument name and message.</span></span> |
| `invalidOp` | `invalidOp "message"` | <span data-ttu-id="0d223-187">引发`System.InvalidOperationException`使用指定的消息。</span><span class="sxs-lookup"><span data-stu-id="0d223-187">Raises a `System.InvalidOperationException` with the specified message.</span></span> |
|`raise`| `raise (ExceptionType("message"))` | <span data-ttu-id="0d223-188">引发异常的通用机制。</span><span class="sxs-lookup"><span data-stu-id="0d223-188">General-purpose mechanism for throwing exceptions.</span></span> |
| `failwith` | `failwith "message"` | <span data-ttu-id="0d223-189">引发`System.Exception`使用指定的消息。</span><span class="sxs-lookup"><span data-stu-id="0d223-189">Raises a `System.Exception` with the specified message.</span></span> |
| `failwithf` | `failwithf "format string" argForFormatString` | <span data-ttu-id="0d223-190">引发`System.Exception`由格式字符串和其输入一条消息。</span><span class="sxs-lookup"><span data-stu-id="0d223-190">Raises a `System.Exception` with a message determined by the format string and its inputs.</span></span> |

<span data-ttu-id="0d223-191">使用`nullArg`，`invalidArg`和`invalidOp`作为机制引发`ArgumentNullException`，`ArgumentException`和`InvalidOperationException`在适当的时候。</span><span class="sxs-lookup"><span data-stu-id="0d223-191">Use `nullArg`, `invalidArg` and `invalidOp` as the mechanism to throw `ArgumentNullException`, `ArgumentException` and `InvalidOperationException` when appropriate.</span></span>

<span data-ttu-id="0d223-192">`failwith`和`failwithf`函数应通常避免使用，因为它们会引发基`Exception`类型，不特定异常。</span><span class="sxs-lookup"><span data-stu-id="0d223-192">The `failwith` and `failwithf` functions should generally be avoided because they raise the base `Exception` type, not a specific exception.</span></span> <span data-ttu-id="0d223-193">按照[异常设计准则](../../standard/design-guidelines/exceptions.md)，您想要提升时你可以更具体的异常。</span><span class="sxs-lookup"><span data-stu-id="0d223-193">As per the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md), you want to raise more specific exceptions when you can.</span></span>

### <a name="using-exception-handling-syntax"></a><span data-ttu-id="0d223-194">使用异常处理语法</span><span class="sxs-lookup"><span data-stu-id="0d223-194">Using exception-handling syntax</span></span>

<span data-ttu-id="0d223-195">F # 支持通过异常模式`try...with`语法：</span><span class="sxs-lookup"><span data-stu-id="0d223-195">F# supports exception patterns via the `try...with` syntax:</span></span>

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

<span data-ttu-id="0d223-196">协调在遇到与模式匹配异常时执行的功能可能会有点很棘手，如果您想要保留的代码清理。</span><span class="sxs-lookup"><span data-stu-id="0d223-196">Reconciling functionality to perform in the face of an exception with pattern matching can be a bit tricky if you wish to keep the code clean.</span></span> <span data-ttu-id="0d223-197">一个此类方法来处理这种情况是使用[活动模式](../language-reference/active-patterns.md)作为组功能周围的错误情况的异常自身的一种手段。</span><span class="sxs-lookup"><span data-stu-id="0d223-197">One such way to handle this is to use [active patterns](../language-reference/active-patterns.md) as a means to group functionality surrounding an error case with an exception itself.</span></span> <span data-ttu-id="0d223-198">例如，你可能要使用的 API 时它引发异常，异常元数据中包含有价值的信息。</span><span class="sxs-lookup"><span data-stu-id="0d223-198">For example, you may be consuming an API that, when it throws an exception, encloses valuable information in the exception metadata.</span></span> <span data-ttu-id="0d223-199">解包内活动的模式的捕获异常的正文中有用的值和返回值可以在某些情况下有用。</span><span class="sxs-lookup"><span data-stu-id="0d223-199">Unwrapping a useful value in the body of the captured exception inside the Active Pattern and returning that value can be helpful in some situations.</span></span>

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a><span data-ttu-id="0d223-200">不使用一元错误处理程序来替换异常</span><span class="sxs-lookup"><span data-stu-id="0d223-200">Do not use monadic error handling to replace exceptions</span></span>

<span data-ttu-id="0d223-201">异常被视为某种程度上 taboo 函数编程中。</span><span class="sxs-lookup"><span data-stu-id="0d223-201">Exceptions are seen as somewhat taboo in functional programming.</span></span> <span data-ttu-id="0d223-202">事实上，异常违反颜色纯度，以便安全地认为它们不完全功能。</span><span class="sxs-lookup"><span data-stu-id="0d223-202">Indeed, exceptions violate purity, so it's safe to consider them not-quite functional.</span></span> <span data-ttu-id="0d223-203">但是，这将忽略的实际情况之前，必须运行代码，以及该运行时，可能会出现错误。</span><span class="sxs-lookup"><span data-stu-id="0d223-203">However, this ignores the reality of where code must run, and that runtime errors can occur.</span></span> <span data-ttu-id="0d223-204">一般情况下，假定在大多数情况下是既不纯，也不是总，尽量少的意外事件中编写代码。</span><span class="sxs-lookup"><span data-stu-id="0d223-204">In general, write code on the assumption that most things are neither pure nor total, to minimize unpleasant surprises.</span></span>

<span data-ttu-id="0d223-205">请务必考虑以下核心优势/方面的异常其相关性和.NET 运行时和跨语言生态系统中作为一个整体的适合程度方面：</span><span class="sxs-lookup"><span data-stu-id="0d223-205">It is important to consider the following core strengths/aspects of Exceptions with respect to their relevance and appropriateness in the .NET runtime and cross-language ecosystem as a whole:</span></span>

1. <span data-ttu-id="0d223-206">它们包含详细的诊断信息，这将非常有用，在调试问题时。</span><span class="sxs-lookup"><span data-stu-id="0d223-206">They contain detailed diagnostic information, which is very helpful when debugging an issue.</span></span>
2. <span data-ttu-id="0d223-207">它们是由运行时和其他.NET 语言易于理解。</span><span class="sxs-lookup"><span data-stu-id="0d223-207">They are well-understood by the runtime and other .NET languages.</span></span>
3. <span data-ttu-id="0d223-208">它们可以降低与超出其方法的代码进行比较时的重要样本*避免*通过即席基础上实现其语义的某个子集的异常。</span><span class="sxs-lookup"><span data-stu-id="0d223-208">They can reduce significant boilerplate when compared with code that goes out of its way to *avoid* exceptions by implementing some subset of their semantics on an ad-hoc basis.</span></span>

<span data-ttu-id="0d223-209">此第三个点至关重要。</span><span class="sxs-lookup"><span data-stu-id="0d223-209">This third point is critical.</span></span> <span data-ttu-id="0d223-210">对于不常用的复杂操作，无法使用异常可能会导致处理结构如下：</span><span class="sxs-lookup"><span data-stu-id="0d223-210">For nontrivial complex operations, failing to use exceptions can result in dealing with structures like this:</span></span>

```fsharp
Result<Result<MyType, string>, string list>
```

<span data-ttu-id="0d223-211">这很容易导致脆弱代码与在"stringly 类型化"的错误进行匹配的模式一样：</span><span class="sxs-lookup"><span data-stu-id="0d223-211">Which can easily lead to fragile code like pattern matching on "stringly-typed" errors:</span></span>

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

<span data-ttu-id="0d223-212">此外，它可以是容易让人想到吞并"简单"返回"不用去涉猎"类型的函数所需的任何异常：</span><span class="sxs-lookup"><span data-stu-id="0d223-212">Additionally, it can be tempting to swallow any exception in the desire for a "simple" function that returns a "nicer" type:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

<span data-ttu-id="0d223-213">遗憾的是，`tryReadAllText`可以引发基于花费更多的文件系统，可能发生的事情的大量异常和此代码离开放弃有关可能实际上什么问题在你的环境中的任何信息。</span><span class="sxs-lookup"><span data-stu-id="0d223-213">Unfortunately, `tryReadAllText` can throw numerous exceptions based on the myriad of things that can happen on a file system, and this code discards away any information about what might actually be going wrong in your environment.</span></span> <span data-ttu-id="0d223-214">如果将此代码替换的结果类型，然后你返回到"stringly 类型化"错误消息分析：</span><span class="sxs-lookup"><span data-stu-id="0d223-214">If you replace this code with a result type, then you're back to "stringly-typed" error message parsing:</span></span>

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

<span data-ttu-id="0d223-215">并将放入异常对象本身中`Error`构造函数仅仅是强制您能够正确处理在调用站点，而不在函数中的异常类型。</span><span class="sxs-lookup"><span data-stu-id="0d223-215">And placing the exception object itself in the `Error` constructor just forces you to properly deal with the exception type at the call site rather than in the function.</span></span> <span data-ttu-id="0d223-216">有效地执行此操作创建选中是非常 unfun 作为 API 的调用方处理的异常。</span><span class="sxs-lookup"><span data-stu-id="0d223-216">Doing this effectively creates checked exceptions, which are notoriously unfun to deal with as a caller of an API.</span></span>

<span data-ttu-id="0d223-217">与上述示例的良好替代方法是捕获*特定*异常并返回该异常的上下文中有意义的值。</span><span class="sxs-lookup"><span data-stu-id="0d223-217">A good alternative to the above examples is to catch *specific* exceptions and return a meaningful value in the context of that exception.</span></span> <span data-ttu-id="0d223-218">如果你修改`tryReadAllText`函数，如下所示，`None`具有多个含义：</span><span class="sxs-lookup"><span data-stu-id="0d223-218">If you modify the `tryReadAllText` function as follows, `None` has more meaning:</span></span>

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

<span data-ttu-id="0d223-219">而不是用作全部捕获时，此函数现在正确地处理这种情况时文件未找到，然后将该含义分配给返回。</span><span class="sxs-lookup"><span data-stu-id="0d223-219">Instead of functioning as a catch-all, this function will now properly handle the case when a file was not found and assign that meaning to a return.</span></span> <span data-ttu-id="0d223-220">此返回值可以将映射到错误这种情况下，在不放弃任何上下文的信息或强制调用方以处理可能不在该点在代码中相关情况。</span><span class="sxs-lookup"><span data-stu-id="0d223-220">This return value can map to that error case, while not discarding any contextual information or forcing callers to deal with a case that may not be relevant at that point in the code.</span></span>

<span data-ttu-id="0d223-221">类型，如`Result<'Success, 'Error>`适用于基本操作，它们不嵌套的且 F # 可选类型也特别适合于表示当内容无法任一返回*内容*或*执行任何操作*.</span><span class="sxs-lookup"><span data-stu-id="0d223-221">Types such as `Result<'Success, 'Error>` are appropriate for basic operations where they aren't nested, and F# optional types are perfect for representing when something could either return *something* or *nothing*.</span></span> <span data-ttu-id="0d223-222">它们不取代异常，不过，且参数不应尝试使用，以替换异常。</span><span class="sxs-lookup"><span data-stu-id="0d223-222">They are not a replacement for exceptions, though, and should not be used in an attempt to replace exceptions.</span></span> <span data-ttu-id="0d223-223">相反，它们应谨慎地到地址的异常和错误管理策略的特定方面采用目标的方式应用。</span><span class="sxs-lookup"><span data-stu-id="0d223-223">Rather, they should be applied judiciously to address specific aspects of exception and error management policy in targeted ways.</span></span>

## <a name="partial-application-and-point-free-programming"></a><span data-ttu-id="0d223-224">部分应用和免点编程</span><span class="sxs-lookup"><span data-stu-id="0d223-224">Partial application and point-free programming</span></span>

<span data-ttu-id="0d223-225">F # 点释放样式，支持部分应用，从而对程序的各种方法。</span><span class="sxs-lookup"><span data-stu-id="0d223-225">F# supports partial application, and thus, various ways to program in a point-free style.</span></span> <span data-ttu-id="0d223-226">这可以对在模块或事物的实现代码重用有用，但通常不是以公开公开。</span><span class="sxs-lookup"><span data-stu-id="0d223-226">This can be beneficial for code reuse within a module or the implementation of something, but it is generally not something to expose publicly.</span></span> <span data-ttu-id="0d223-227">一般情况下，点释放编程不是本身，并可以添加一个巨大的认知障碍的用户不深陷样式。</span><span class="sxs-lookup"><span data-stu-id="0d223-227">In general, point-free programming is not a virtue in and of itself, and can add a significant cognitive barrier for people who are not immersed in the style.</span></span>

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a><span data-ttu-id="0d223-228">不要使用部分应用和扩充中公共 Api</span><span class="sxs-lookup"><span data-stu-id="0d223-228">Do not use partial application and currying in public APIs</span></span>

<span data-ttu-id="0d223-229">很少有例外，在公共 Api 中的部分应用程序的使用可以让使用者感到困惑。</span><span class="sxs-lookup"><span data-stu-id="0d223-229">With little exception, the use of partial application in public APIs can be confusing for consumers.</span></span> <span data-ttu-id="0d223-230">通常情况下， `let`-F # 代码中的绑定的值为**值**，而不**函数值**。</span><span class="sxs-lookup"><span data-stu-id="0d223-230">Usually, `let`-bound values in F# code are **values**, not **function values**.</span></span> <span data-ttu-id="0d223-231">将混合在一起的值和函数值可能导致保存少量的代码以认知开销，相当多的位交换的行尤其是结合运算符如`>>`编写函数。</span><span class="sxs-lookup"><span data-stu-id="0d223-231">Mixing together values and function values can result in saving a small number of lines of code in exchange for quite a bit of cognitive overhead, especially if combined with operators such as `>>` to compose functions.</span></span>

### <a name="consider-the-tooling-implications-for-point-free-programming"></a><span data-ttu-id="0d223-232">请考虑点释放编程的工具含义</span><span class="sxs-lookup"><span data-stu-id="0d223-232">Consider the tooling implications for point-free programming</span></span>

<span data-ttu-id="0d223-233">扩充的函数不标记其参数。</span><span class="sxs-lookup"><span data-stu-id="0d223-233">Curried functions do not label their arguments.</span></span> <span data-ttu-id="0d223-234">这具有工具影响。</span><span class="sxs-lookup"><span data-stu-id="0d223-234">This has tooling implications.</span></span> <span data-ttu-id="0d223-235">请考虑以下两个函数：</span><span class="sxs-lookup"><span data-stu-id="0d223-235">Consider the following two functions:</span></span>

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

<span data-ttu-id="0d223-236">都有效函数，但`funcWithApplication`是扩充的函数。</span><span class="sxs-lookup"><span data-stu-id="0d223-236">Both are valid functions, but `funcWithApplication` is a curried function.</span></span> <span data-ttu-id="0d223-237">当你将鼠标悬停在其类型在编辑器中时，你将看到以下内容：</span><span class="sxs-lookup"><span data-stu-id="0d223-237">When you hover over their types in an editor, you see this:</span></span>

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

<span data-ttu-id="0d223-238">在调用站点上，如 Visual Studio 工具中的工具提示将不为你提供有意义信息关于什么`string`和`int`实际表示输入的类型。</span><span class="sxs-lookup"><span data-stu-id="0d223-238">At the call site, tooltips in tooling such as Visual Studio will not give you meaningful information as to what the `string` and `int` input types actually represent.</span></span>

<span data-ttu-id="0d223-239">如果你遇到类似点释放代码`funcWithApplication`公开可耗用，建议执行完全的 η 扩展，以便工具可以选取在自变量有意义的名称。</span><span class="sxs-lookup"><span data-stu-id="0d223-239">If you encounter point-free code like `funcWithApplication` that is publicly consumable, it is recommended to do a full η-expansion so that tooling can pick up on meaningful names for arguments.</span></span>

<span data-ttu-id="0d223-240">此外，调试点无代码会有点困难，如果不是不可能。</span><span class="sxs-lookup"><span data-stu-id="0d223-240">Furthermore, debugging point-free code can be challenging, if not impossible.</span></span> <span data-ttu-id="0d223-241">调试工具依赖值绑定到名称 (例如，`let`绑定)，以便你可以检查中间值中途执行。</span><span class="sxs-lookup"><span data-stu-id="0d223-241">Debugging tools rely on values bound to names (for example, `let` bindings) so that you can inspect intermediate values midway through execution.</span></span> <span data-ttu-id="0d223-242">当你的代码具有要检查的值时，没有要调试的内容。</span><span class="sxs-lookup"><span data-stu-id="0d223-242">When your code has no values to inspect, there is nothing to debug.</span></span> <span data-ttu-id="0d223-243">将来，调试工具可演变以便综合这些值基于以前执行的路径，但它不是 hedge 你匹配上一个好办法*潜在*调试功能。</span><span class="sxs-lookup"><span data-stu-id="0d223-243">In the future, debugging tools may evolve to synthesize these values based on previously executed paths, but it's not a good idea to hedge your bets on *potential* debugging functionality.</span></span>

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a><span data-ttu-id="0d223-244">请考虑部分应用程序作为一种技术来减少内部样本</span><span class="sxs-lookup"><span data-stu-id="0d223-244">Consider partial application as a technique to reduce internal boilerplate</span></span>

<span data-ttu-id="0d223-245">与上一个点，部分应用程序是一个用于减少应用程序或 API 的更深层次的内部结构内的样本的曾经工具。</span><span class="sxs-lookup"><span data-stu-id="0d223-245">In contrast to the previous point, partial application is a wonderful tool for reducing boilerplate inside of an application or the deeper internals of an API.</span></span> <span data-ttu-id="0d223-246">它可以帮助进行单元测试的更复杂的 Api，样本通常是处理困难的实现。</span><span class="sxs-lookup"><span data-stu-id="0d223-246">It can be helpful for unit testing the implementation of more complicated APIs, where boilerplate is often a pain to deal with.</span></span> <span data-ttu-id="0d223-247">例如，下面的代码演示如何实现什么最模拟框架为你提供不在此类的框架执行的外部依赖关系并无需了解相关订货的 API。</span><span class="sxs-lookup"><span data-stu-id="0d223-247">For example, the following code shows how you can accomplish what most mocking frameworks give you without taking an external dependency on such a framework and having to learn a related bespoke API.</span></span>

<span data-ttu-id="0d223-248">例如，考虑以下解决方案拓扑：</span><span class="sxs-lookup"><span data-stu-id="0d223-248">For example, consider the following solution topography:</span></span>

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

<span data-ttu-id="0d223-249">`ImplementationLogic.fsproj` 例如，可能会公开代码：</span><span class="sxs-lookup"><span data-stu-id="0d223-249">`ImplementationLogic.fsproj` might expose code such as:</span></span>

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member __.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

<span data-ttu-id="0d223-250">单元测试`Transactions.doTransaction`中`ImplementationLogic.Tests.fspoj`很容易：</span><span class="sxs-lookup"><span data-stu-id="0d223-250">Unit testing `Transactions.doTransaction` in `ImplementationLogic.Tests.fspoj` is easy:</span></span>

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

<span data-ttu-id="0d223-251">部分应用`doTransaction`与模拟上下文对象，可以在你的单元测试的所有调用函数，而无需每次构造模拟的上下文：</span><span class="sxs-lookup"><span data-stu-id="0d223-251">Partially applying `doTransaction` with a mocking context object lets you call the function in all of your unit tests without needing to construct a mocked context each time:</span></span>

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

<span data-ttu-id="0d223-252">不应将此技术普遍应用到整个基本代码，但它是一种好方法，以减少复杂的内部结构和单元测试这些内部结构的样本。</span><span class="sxs-lookup"><span data-stu-id="0d223-252">This technique should not be universally applied to your entire codebase, but it is a good way to reduce boilerplate for complicated internals and unit testing those internals.</span></span>

## <a name="access-control"></a><span data-ttu-id="0d223-253">访问控制</span><span class="sxs-lookup"><span data-stu-id="0d223-253">Access control</span></span>

<span data-ttu-id="0d223-254">F # 包含多个选项[访问控制](../language-reference/access-control.md)，从可用的.NET 运行时中继承。</span><span class="sxs-lookup"><span data-stu-id="0d223-254">F# has multiple options for [Access control](../language-reference/access-control.md), inherited from what is available in the .NET runtime.</span></span> <span data-ttu-id="0d223-255">这些并不是只可用于类型-你可以使用它们对于函数，太。</span><span class="sxs-lookup"><span data-stu-id="0d223-255">These are not just usable for types - you can use them for functions, too.</span></span>

* <span data-ttu-id="0d223-256">首选非`public`类型和成员之前你需要对其可以公开使用。</span><span class="sxs-lookup"><span data-stu-id="0d223-256">Prefer non-`public` types and members until you need them to be publicly consumable.</span></span> <span data-ttu-id="0d223-257">这还将减少到何种使用者几</span><span class="sxs-lookup"><span data-stu-id="0d223-257">This also minimizes what consumers couple to</span></span>
* <span data-ttu-id="0d223-258">尽可能将所有的帮助器功能`private`。</span><span class="sxs-lookup"><span data-stu-id="0d223-258">Strive to keep all helper functionality `private`.</span></span>
* <span data-ttu-id="0d223-259">请考虑使用`[<AutoOpen>]`在专用模块的帮助器函数，如果趋于大量上。</span><span class="sxs-lookup"><span data-stu-id="0d223-259">Consider the use of `[<AutoOpen>]` on a private module of helper functions if they become numerous.</span></span>

## <a name="type-inference-and-generics"></a><span data-ttu-id="0d223-260">类型推理和泛型</span><span class="sxs-lookup"><span data-stu-id="0d223-260">Type inference and generics</span></span>

<span data-ttu-id="0d223-261">类型推理可为你节省键入大量的样本。</span><span class="sxs-lookup"><span data-stu-id="0d223-261">Type inference can save you from typing a lot of boilerplate.</span></span> <span data-ttu-id="0d223-262">和 F # 编译器中的自动泛化可帮助你编写对您来说几乎没有任何额外的工作量的更通用代码。</span><span class="sxs-lookup"><span data-stu-id="0d223-262">And automatic generalization in the F# compiler can help you write more generic code with almost no extra effort on your part.</span></span> <span data-ttu-id="0d223-263">但是，这些功能不是全局完好的。</span><span class="sxs-lookup"><span data-stu-id="0d223-263">However, these features are not universally good.</span></span>

* <span data-ttu-id="0d223-264">考虑与公共 Api 中的显式类型标记自变量名称并不依赖此类型推理。</span><span class="sxs-lookup"><span data-stu-id="0d223-264">Consider labeling argument names with explicit types in public APIs and do not rely on type inference for this.</span></span>

    <span data-ttu-id="0d223-265">这样做的原因在于**你**应在控件中的形状的你的 API，不编译器。</span><span class="sxs-lookup"><span data-stu-id="0d223-265">The reason for this is that **you** should be in control of the shape of your API, not the compiler.</span></span> <span data-ttu-id="0d223-266">虽然编译器可以执行在为你推理类型了很好，很可能有的 API 更改形状，如果它依赖于内部结构已更改类型。</span><span class="sxs-lookup"><span data-stu-id="0d223-266">Although the compiler can do a fine job at inferring types for you, it is possible to have the shape of your API change if the internals it relies on have changed types.</span></span> <span data-ttu-id="0d223-267">这可能是你的想，但它几乎可以肯定将导致下游使用者随后必须处理的重大 API 更改。</span><span class="sxs-lookup"><span data-stu-id="0d223-267">This may be what you want, but it will almost certainly result in a breaking API change that downstream consumers will then have to deal with.</span></span> <span data-ttu-id="0d223-268">相反，若要显式控制形状的公共 API，你可以控制这些重大更改。</span><span class="sxs-lookup"><span data-stu-id="0d223-268">Instead, if you explicitly control the shape of your public API, then you can control these breaking changes.</span></span> <span data-ttu-id="0d223-269">在 DDD 术语中，这被想象的作为防损坏层。</span><span class="sxs-lookup"><span data-stu-id="0d223-269">In DDD terms, this can be thought of as an Anti-corruption layer.</span></span>

* <span data-ttu-id="0d223-270">请考虑为泛型参数指定有意义的名称。</span><span class="sxs-lookup"><span data-stu-id="0d223-270">Consider giving a meaningful name to your generic arguments.</span></span>

    <span data-ttu-id="0d223-271">你正在编写的并不特定于特定域真正泛型代码，除非有意义的名称可帮助其他程序员了解他们正在使用的域。</span><span class="sxs-lookup"><span data-stu-id="0d223-271">Unless you are writing truly generic code that is not specific to a particular domain, a meaningful name can help other programmers understanding the domain they're working in.</span></span> <span data-ttu-id="0d223-272">例如，一个名为的类型参数`'Document`文档与之进行交互的上下文中数据库使它清楚地了解泛型文档类型，可以接受由该函数或你正在使用的成员。</span><span class="sxs-lookup"><span data-stu-id="0d223-272">For example, a type parameter named `'Document` in the context of interacting with a document database makes it clearer that generic document types can be accepted by the function or member you are working with.</span></span>

* <span data-ttu-id="0d223-273">请考虑命名 PascalCase 泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="0d223-273">Consider naming generic type parameters with PascalCase.</span></span>

    <span data-ttu-id="0d223-274">这是常见的方式进行某些操作在.NET 中，因此建议你使用 PascalCase 而不是 snake_case 或驼峰匹配。</span><span class="sxs-lookup"><span data-stu-id="0d223-274">This is the general way to do things in .NET, so it's recommended that you use PascalCase rather than snake_case or camelCase.</span></span>

<span data-ttu-id="0d223-275">最后，自动泛化并不总是熟悉 F # 或大型基本代码的人员一件好事。</span><span class="sxs-lookup"><span data-stu-id="0d223-275">Finally, automatic generalization is not always a boon for people who are new to F# or a large codebase.</span></span> <span data-ttu-id="0d223-276">使用都是泛型方法的组件处于认知开销。</span><span class="sxs-lookup"><span data-stu-id="0d223-276">There is cognitive overhead in using components that are generic.</span></span> <span data-ttu-id="0d223-277">此外，如果自动通用的函数不用于不同的输入类型 （让单独如果它们旨在用于这种情况下），则它们正在泛型时间中此点处没有实际的好处。</span><span class="sxs-lookup"><span data-stu-id="0d223-277">Furthermore, if automatically generalized functions are not used with different input types (let alone if they are intended to be used as such), then there is no real benefit to them being generic at that point in time.</span></span> <span data-ttu-id="0d223-278">应始终考虑是否你正在编写的代码实际上将从正在泛型受益。</span><span class="sxs-lookup"><span data-stu-id="0d223-278">Always consider if the code you are writing will actually benefit from being generic.</span></span>

## <a name="performance"></a><span data-ttu-id="0d223-279">性能</span><span class="sxs-lookup"><span data-stu-id="0d223-279">Performance</span></span>

<span data-ttu-id="0d223-280">F # 的值为默认情况下，你可以避免 bug （尤其是那些涉及并发和并行） 的某些类不可变。</span><span class="sxs-lookup"><span data-stu-id="0d223-280">F# values are immutable by default, which allows you to avoid certain classes of bugs (especially those involving concurrency and parallelism).</span></span> <span data-ttu-id="0d223-281">但是，在某些情况下，以便实现最佳 （或甚至合理） 效率的执行时间或内存分配的工作范围可能最实现使用就地转变的状态。</span><span class="sxs-lookup"><span data-stu-id="0d223-281">However, in certain cases, in order to achieve optimal (or even reasonable) efficiency of execution time or memory allocations, a span of work may best be implemented by using in-place mutation of state.</span></span> <span data-ttu-id="0d223-282">这是在 F # 使用可以选择使用的基础可能`mutable`关键字。</span><span class="sxs-lookup"><span data-stu-id="0d223-282">This is possible in an opt-in basis with F# with the `mutable` keyword.</span></span>

<span data-ttu-id="0d223-283">但是，使用`mutable`F # 中可能觉得功能纯度一致。</span><span class="sxs-lookup"><span data-stu-id="0d223-283">However, use of `mutable` in F# may feel at odds with functional purity.</span></span> <span data-ttu-id="0d223-284">这没什么关系，如果调整到的颜色纯度上预期[引用透明度](https://en.wikipedia.org/wiki/Referential_transparency)。</span><span class="sxs-lookup"><span data-stu-id="0d223-284">This is fine, if you adjust expectations from purity to [referential transparency](https://en.wikipedia.org/wiki/Referential_transparency).</span></span> <span data-ttu-id="0d223-285">在编写 F # 函数时，引用透明度-而不是颜色纯度-很最终目标。</span><span class="sxs-lookup"><span data-stu-id="0d223-285">Referential transparency - not purity - is the end goal when writing F# functions.</span></span> <span data-ttu-id="0d223-286">这样，您可以编写通过性能关键代码的基于转变的实现的功能的接口。</span><span class="sxs-lookup"><span data-stu-id="0d223-286">This allows you to write a functional interface over a mutation-based implementation for performance critical code.</span></span>

### <a name="wrap-mutable-code-in-immutable-interfaces"></a><span data-ttu-id="0d223-287">在不可变的接口中包装可变代码</span><span class="sxs-lookup"><span data-stu-id="0d223-287">Wrap mutable code in immutable interfaces</span></span>

<span data-ttu-id="0d223-288">具有为目标的引用透明度，编写代码，不会公开性能关键函数可变 underbelly 至关重要。</span><span class="sxs-lookup"><span data-stu-id="0d223-288">With referential transparency as a goal, it is critical to write code that does not expose the mutable underbelly of performance-critical functions.</span></span> <span data-ttu-id="0d223-289">例如，下面的代码实现`Array.contains`F # 核心库中的函数：</span><span class="sxs-lookup"><span data-stu-id="0d223-289">For example, the following code implements the `Array.contains` function in the F# core library:</span></span>

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

<span data-ttu-id="0d223-290">多次调用此函数不会更改基础的数组，也不会要求你维护在使用它的任何可变状态。</span><span class="sxs-lookup"><span data-stu-id="0d223-290">Calling this function multiple times does not change the underlying array, nor does it require you to maintain any mutable state in consuming it.</span></span> <span data-ttu-id="0d223-291">它是代码的 referentially 透明的即使中它几乎每个行使用转变。</span><span class="sxs-lookup"><span data-stu-id="0d223-291">It is referentially transparent, even though almost every line of code within it uses mutation.</span></span>

### <a name="consider-encapsulating-mutable-data-in-classes"></a><span data-ttu-id="0d223-292">请考虑将封装在类中的可变数据</span><span class="sxs-lookup"><span data-stu-id="0d223-292">Consider encapsulating mutable data in classes</span></span>

<span data-ttu-id="0d223-293">前面的示例使用单个函数封装使用可变数据操作。</span><span class="sxs-lookup"><span data-stu-id="0d223-293">The previous example used a single function to encapsulate operations using mutable data.</span></span> <span data-ttu-id="0d223-294">这并不总是能够满足更复杂的数据集。</span><span class="sxs-lookup"><span data-stu-id="0d223-294">This is not always sufficient for more complex sets of data.</span></span> <span data-ttu-id="0d223-295">请考虑以下几组函数：</span><span class="sxs-lookup"><span data-stu-id="0d223-295">Consider the following sets of functions:</span></span>

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

<span data-ttu-id="0d223-296">此代码是高性能，但它公开调用方负责维护的基于变化的数据结构。</span><span class="sxs-lookup"><span data-stu-id="0d223-296">This code is performant, but it exposes the mutation-based data structure that callers are responsible for maintaining.</span></span> <span data-ttu-id="0d223-297">这可以在不包含可以更改任何基础成员类内部包装：</span><span class="sxs-lookup"><span data-stu-id="0d223-297">This can be wrapped inside of a class with no underlying members that can change:</span></span>

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

<span data-ttu-id="0d223-298">`Closure1Table` 封装的基础的基于变化的数据结构，因此无法强制调用方来维护的基础数据结构。</span><span class="sxs-lookup"><span data-stu-id="0d223-298">`Closure1Table` encapsulates the underlying mutation-based data structure, thereby not forcing callers to maintain the underlying data structure.</span></span> <span data-ttu-id="0d223-299">类是一种强大方法封装了数据以及可以基于变化的而公开给调用方的详细信息的例程。</span><span class="sxs-lookup"><span data-stu-id="0d223-299">Classes are a powerful way to encapsulate data and routines that are mutation-based without exposing the details to callers.</span></span>

### <a name="prefer-let-mutable-to-reference-cells"></a><span data-ttu-id="0d223-300">首选`let mutable`引用单元格</span><span class="sxs-lookup"><span data-stu-id="0d223-300">Prefer `let mutable` to reference cells</span></span>

<span data-ttu-id="0d223-301">引用单元格是表示对一个值，而不是值本身的引用的方式。</span><span class="sxs-lookup"><span data-stu-id="0d223-301">Reference cells are a way to represent the reference to a value rather than the value itself.</span></span> <span data-ttu-id="0d223-302">虽然它们可以使用性能关键代码，但通常不建议将其。</span><span class="sxs-lookup"><span data-stu-id="0d223-302">Although they can be used for performance-critical code, they are generally not recommended.</span></span> <span data-ttu-id="0d223-303">请看下面的示例：</span><span class="sxs-lookup"><span data-stu-id="0d223-303">Consider the following example:</span></span>

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

<span data-ttu-id="0d223-304">使用引用单元格现在"破坏"与无需取消引用和重新引用基础数据的所有后续代码。</span><span class="sxs-lookup"><span data-stu-id="0d223-304">The use of a reference cell now "pollutes" all subsequent code with having to dereference and re-reference the underlying data.</span></span> <span data-ttu-id="0d223-305">相反，请考虑`let mutable`:</span><span class="sxs-lookup"><span data-stu-id="0d223-305">Instead, consider `let mutable`:</span></span>

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

<span data-ttu-id="0d223-306">除了转变中间 lambda 表达式的单个点，所有其他代码的接触`acc`可以这样的常规用法没有什么不同的方式`let`-绑定不可变的值。</span><span class="sxs-lookup"><span data-stu-id="0d223-306">Aside from the single point of mutation in the middle of the lambda expression, all other code that touches `acc` can do so in a manner that is no different to the usage of a normal `let`-bound immutable value.</span></span> <span data-ttu-id="0d223-307">这将使更轻松地随时间而变化。</span><span class="sxs-lookup"><span data-stu-id="0d223-307">This will make it easier to change over time.</span></span>

## <a name="object-programming"></a><span data-ttu-id="0d223-308">对象编程</span><span class="sxs-lookup"><span data-stu-id="0d223-308">Object programming</span></span>

<span data-ttu-id="0d223-309">F # 包含对对象和面向对象的 (OO) 概念的完整支持。</span><span class="sxs-lookup"><span data-stu-id="0d223-309">F# has full support for objects and object-oriented (OO) concepts.</span></span> <span data-ttu-id="0d223-310">尽管许多 OO 概念是功能强大且有用，但不是所有进行使用。</span><span class="sxs-lookup"><span data-stu-id="0d223-310">Although many OO concepts are powerful and useful, not all of them are ideal to use.</span></span> <span data-ttu-id="0d223-311">以下列表提供的类别的较高层面 OO 功能的指南。</span><span class="sxs-lookup"><span data-stu-id="0d223-311">The following lists offer guidance on categories of OO features at a high level.</span></span>

<span data-ttu-id="0d223-312">**请考虑在许多情况下使用这些功能：**</span><span class="sxs-lookup"><span data-stu-id="0d223-312">**Consider using these features in many situations:**</span></span>

* <span data-ttu-id="0d223-313">点表示法 (`x.Length`)</span><span class="sxs-lookup"><span data-stu-id="0d223-313">Dot notation (`x.Length`)</span></span>
* <span data-ttu-id="0d223-314">实例成员</span><span class="sxs-lookup"><span data-stu-id="0d223-314">Instance members</span></span>
* <span data-ttu-id="0d223-315">隐式构造函数</span><span class="sxs-lookup"><span data-stu-id="0d223-315">Implicit constructors</span></span>
* <span data-ttu-id="0d223-316">静态成员</span><span class="sxs-lookup"><span data-stu-id="0d223-316">Static members</span></span>
* <span data-ttu-id="0d223-317">索引器表示法 (`arr.[x]`)</span><span class="sxs-lookup"><span data-stu-id="0d223-317">Indexer notation (`arr.[x]`)</span></span>
* <span data-ttu-id="0d223-318">命名参数和可选参数</span><span class="sxs-lookup"><span data-stu-id="0d223-318">Named and Optional arguments</span></span>
* <span data-ttu-id="0d223-319">接口和接口实现</span><span class="sxs-lookup"><span data-stu-id="0d223-319">Interfaces and interface implementations</span></span>

<span data-ttu-id="0d223-320">**首先，不达到为这些功能，但不要谨慎地将其应用时方便地解决问题：**</span><span class="sxs-lookup"><span data-stu-id="0d223-320">**Don't reach for these features first, but do judiciously apply them when they are convenient to solve a problem:**</span></span>

* <span data-ttu-id="0d223-321">方法重载</span><span class="sxs-lookup"><span data-stu-id="0d223-321">Method overloading</span></span>
* <span data-ttu-id="0d223-322">封装的可变数据</span><span class="sxs-lookup"><span data-stu-id="0d223-322">Encapsulated mutable data</span></span>
* <span data-ttu-id="0d223-323">对类型的运算符</span><span class="sxs-lookup"><span data-stu-id="0d223-323">Operators on types</span></span>
* <span data-ttu-id="0d223-324">自动属性</span><span class="sxs-lookup"><span data-stu-id="0d223-324">Auto properties</span></span>
* <span data-ttu-id="0d223-325">实现`IDisposable`和 `IEnumerable`</span><span class="sxs-lookup"><span data-stu-id="0d223-325">Implementing `IDisposable` and `IEnumerable`</span></span>
* <span data-ttu-id="0d223-326">类型扩展</span><span class="sxs-lookup"><span data-stu-id="0d223-326">Type extensions</span></span>
* <span data-ttu-id="0d223-327">事件</span><span class="sxs-lookup"><span data-stu-id="0d223-327">Events</span></span>
* <span data-ttu-id="0d223-328">结构</span><span class="sxs-lookup"><span data-stu-id="0d223-328">Structs</span></span>
* <span data-ttu-id="0d223-329">委托</span><span class="sxs-lookup"><span data-stu-id="0d223-329">Delegates</span></span>
* <span data-ttu-id="0d223-330">枚举</span><span class="sxs-lookup"><span data-stu-id="0d223-330">Enums</span></span>

<span data-ttu-id="0d223-331">**除非你必须使用它们，通常避免这些功能：**</span><span class="sxs-lookup"><span data-stu-id="0d223-331">**Generally avoid these features unless you must use them:**</span></span>

* <span data-ttu-id="0d223-332">基于继承的类型层次结构和实现继承</span><span class="sxs-lookup"><span data-stu-id="0d223-332">Inheritance-based type hierarchies and implementation inheritance</span></span>
* <span data-ttu-id="0d223-333">Null 值和 `Unchecked.defaultof<_>`</span><span class="sxs-lookup"><span data-stu-id="0d223-333">Nulls and `Unchecked.defaultof<_>`</span></span>

### <a name="prefer-composition-over-inheritance"></a><span data-ttu-id="0d223-334">更愿意组合，而继承</span><span class="sxs-lookup"><span data-stu-id="0d223-334">Prefer composition over inheritance</span></span>

<span data-ttu-id="0d223-335">[通过继承组合](https://en.wikipedia.org/wiki/Composition_over_inheritance)是一种长期存在的方法，可以遵循良好的 F # 代码。</span><span class="sxs-lookup"><span data-stu-id="0d223-335">[Composition over inheritance](https://en.wikipedia.org/wiki/Composition_over_inheritance) is a long-standing idiom that good F# code can adhere to.</span></span> <span data-ttu-id="0d223-336">基本原则是，不应公开的基本类和强制调用方继承自该基类，以获取的功能。</span><span class="sxs-lookup"><span data-stu-id="0d223-336">The fundamental principle is that you should not expose a base class and force callers to inherit from that base class to get functionality.</span></span>

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a><span data-ttu-id="0d223-337">使用对象表达式实现接口，如果你不需要一个类</span><span class="sxs-lookup"><span data-stu-id="0d223-337">Use object expressions to implement interfaces if you don't need a class</span></span>

<span data-ttu-id="0d223-338">[对象表达式](../language-reference/object-expressions.md)允许你动态，实现接口在无需为此，在类内部实现的接口绑定到的值。</span><span class="sxs-lookup"><span data-stu-id="0d223-338">[Object Expressions](../language-reference/object-expressions.md) allow you to implement interfaces on the fly, binding the implemented interface to a value without needing to do so inside of a class.</span></span> <span data-ttu-id="0d223-339">此方法很方便，尤其是如果你_仅_需要实现接口，并且无需完整的类。</span><span class="sxs-lookup"><span data-stu-id="0d223-339">This is convenient, especially if you _only_ need to implement the interface and have no need for a full class.</span></span>

<span data-ttu-id="0d223-340">例如，以下是在中运行的代码[Ionide](http://ionide.io/)提供的代码修复操作，如果你已添加你没有的符号`open`语句：</span><span class="sxs-lookup"><span data-stu-id="0d223-340">For example, here is the code that is run in [Ionide](http://ionide.io/) to provide a code fix action if you've added a symbol that you don't have an `open` statement for:</span></span>

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

<span data-ttu-id="0d223-341">由于没有为类无需与 Visual Studio 代码 API 交互时，对象表达式是此的理想工具。</span><span class="sxs-lookup"><span data-stu-id="0d223-341">Because there is no need for a class when interacting with the Visual Studio Code API, Object Expressions are an ideal tool for this.</span></span> <span data-ttu-id="0d223-342">此外，还为单元测试，如果你想要与测试例程接口存根以即席方式有价值。</span><span class="sxs-lookup"><span data-stu-id="0d223-342">They are also valuable for unit testing, when you want to stub out an interface with test routines in an ad hoc manner.</span></span>

## <a name="type-abbreviations"></a><span data-ttu-id="0d223-343">类型缩写</span><span class="sxs-lookup"><span data-stu-id="0d223-343">Type Abbreviations</span></span>

<span data-ttu-id="0d223-344">[类型缩写，用](../language-reference/type-abbreviations.md)是一种简便的方法，以将标签分配给另一个类型，例如函数签名或更复杂的类型。</span><span class="sxs-lookup"><span data-stu-id="0d223-344">[Type Abbreviations](../language-reference/type-abbreviations.md) are a convenient way to assign a label to another type, such as a function signature or a more complex type.</span></span> <span data-ttu-id="0d223-345">例如，以下别名将标签分配给需要定义与计算哪些[CNTK](https://www.microsoft.com/cognitive-toolkit/)、 深入学习库：</span><span class="sxs-lookup"><span data-stu-id="0d223-345">For example, the following alias assigns a label to what's needed to define a computation with [CNTK](https://www.microsoft.com/cognitive-toolkit/), a deep learning library:</span></span>

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

<span data-ttu-id="0d223-346">`Computation`名称是一种简便的方法来表示它是别名的签名匹配的任何函数。</span><span class="sxs-lookup"><span data-stu-id="0d223-346">The `Computation` name is a convenient way to denote any function that matches the signature it is aliasing.</span></span> <span data-ttu-id="0d223-347">此类使用类型缩写是方便，允许进行更简洁的代码。</span><span class="sxs-lookup"><span data-stu-id="0d223-347">Using Type Abbreviations like this is convenient and allows for more succinct code.</span></span>

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a><span data-ttu-id="0d223-348">避免使用类型缩写来表示你的域</span><span class="sxs-lookup"><span data-stu-id="0d223-348">Avoid using Type Abbreviations to represent your domain</span></span>

<span data-ttu-id="0d223-349">虽然类型缩写很方便，将交给函数的签名的名称，它们可能容易引起混淆时 abbreviating 其他类型。</span><span class="sxs-lookup"><span data-stu-id="0d223-349">Although Type Abbreviations are convenient for giving a name to function signatures, they can be confusing when abbreviating other types.</span></span> <span data-ttu-id="0d223-350">请考虑此缩写：</span><span class="sxs-lookup"><span data-stu-id="0d223-350">Consider this abbreviation:</span></span>

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

<span data-ttu-id="0d223-351">这可能容易引起混淆采用多种方式：</span><span class="sxs-lookup"><span data-stu-id="0d223-351">This can be confusing in multiple ways:</span></span>

* <span data-ttu-id="0d223-352">`BufferSize` 不是一个抽象概念。它是一个整数的另一个名称。</span><span class="sxs-lookup"><span data-stu-id="0d223-352">`BufferSize` is not an abstraction; it is just another name for an integer.</span></span>
* <span data-ttu-id="0d223-353">如果`BufferSize`公开在公共 API 中，它可以轻松地被错误解释不仅仅表示`int`。</span><span class="sxs-lookup"><span data-stu-id="0d223-353">If `BufferSize` is exposed in a public API, it can easily be misinterpreted to mean more than just `int`.</span></span> <span data-ttu-id="0d223-354">通常情况下，域类型具有到它们的多个属性，以及是否不等的基元类型`int`。</span><span class="sxs-lookup"><span data-stu-id="0d223-354">Generally, domain types have multiple attributes to them and are not primitive types like `int`.</span></span> <span data-ttu-id="0d223-355">此缩写违反这一假定。</span><span class="sxs-lookup"><span data-stu-id="0d223-355">This abbreviation violates that assumption.</span></span>
* <span data-ttu-id="0d223-356">大小写`BufferSize`(PascalCase) 表示此类型包含更多的数据。</span><span class="sxs-lookup"><span data-stu-id="0d223-356">The casing of `BufferSize` (PascalCase) implies that this type holds more data.</span></span>
* <span data-ttu-id="0d223-357">此别名不提供起见与提供给函数的命名自变量进行比较。</span><span class="sxs-lookup"><span data-stu-id="0d223-357">This alias does not offer increased clarity compared with providing a named argument to a function.</span></span>
* <span data-ttu-id="0d223-358">缩写不将清单中编译的 IL;它是只是一个整数，此别名是一个编译时构造。</span><span class="sxs-lookup"><span data-stu-id="0d223-358">The abbreviation will not manifest in compiled IL; it is just an integer and this alias is a compile-time construct.</span></span>

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) =
        ...
```

<span data-ttu-id="0d223-359">总之，与类型缩写缺陷就是它们是**不**它们 abbreviating 类型的抽象。</span><span class="sxs-lookup"><span data-stu-id="0d223-359">In summary, the pitfall with Type Abbreviations is that they are **not** abstractions over the types they are abbreviating.</span></span> <span data-ttu-id="0d223-360">在前面的示例中，`BufferSize`只有`int`事实上，与任何其他数据，也不从除了新增功能的类型系统带来的好处`int`已有。</span><span class="sxs-lookup"><span data-stu-id="0d223-360">In the previous example, `BufferSize` is just an `int` under the covers, with no additional data, nor any benefits from the type system besides what `int` already has.</span></span>
