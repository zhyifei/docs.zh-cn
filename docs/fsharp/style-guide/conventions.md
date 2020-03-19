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
# <a name="f-coding-conventions"></a><span data-ttu-id="05ce3-103">F# 编码约定</span><span class="sxs-lookup"><span data-stu-id="05ce3-103">F# coding conventions</span></span>

<span data-ttu-id="05ce3-104">以下约定是从使用大型 F# 代码库的经验中制定的。</span><span class="sxs-lookup"><span data-stu-id="05ce3-104">The following conventions are formulated from experience working with large F# codebases.</span></span> <span data-ttu-id="05ce3-105">[好的 F# 代码的五个原则](index.md#five-principles-of-good-f-code)是每个建议的基础。</span><span class="sxs-lookup"><span data-stu-id="05ce3-105">The [Five principles of good F# code](index.md#five-principles-of-good-f-code) are the foundation of each recommendation.</span></span> <span data-ttu-id="05ce3-106">它们与[F# 组件设计指南](component-design-guidelines.md)相关，但适用于任何 F# 代码，而不仅仅是库等组件。</span><span class="sxs-lookup"><span data-stu-id="05ce3-106">They are related to the [F# component design guidelines](component-design-guidelines.md), but are applicable for any F# code, not just components such as libraries.</span></span>

## <a name="organizing-code"></a><span data-ttu-id="05ce3-107">组织代码</span><span class="sxs-lookup"><span data-stu-id="05ce3-107">Organizing code</span></span>

<span data-ttu-id="05ce3-108">F# 具有两种组织代码的主要方法：模块和命名空间。</span><span class="sxs-lookup"><span data-stu-id="05ce3-108">F# features two primary ways to organize code: modules and namespaces.</span></span> <span data-ttu-id="05ce3-109">这些相似，但确实有以下差异：</span><span class="sxs-lookup"><span data-stu-id="05ce3-109">These are similar, but do have the following differences:</span></span>

* <span data-ttu-id="05ce3-110">命名空间编译为 .NET 命名空间。</span><span class="sxs-lookup"><span data-stu-id="05ce3-110">Namespaces are compiled as .NET namespaces.</span></span> <span data-ttu-id="05ce3-111">模块编译为静态类。</span><span class="sxs-lookup"><span data-stu-id="05ce3-111">Modules are compiled as static classes.</span></span>
* <span data-ttu-id="05ce3-112">命名空间始终是顶层。</span><span class="sxs-lookup"><span data-stu-id="05ce3-112">Namespaces are always top level.</span></span> <span data-ttu-id="05ce3-113">模块可以是顶级的，可以嵌套在其他模块中。</span><span class="sxs-lookup"><span data-stu-id="05ce3-113">Modules can be top-level and nested within other modules.</span></span>
* <span data-ttu-id="05ce3-114">命名空间可以跨多个文件。</span><span class="sxs-lookup"><span data-stu-id="05ce3-114">Namespaces can span multiple files.</span></span> <span data-ttu-id="05ce3-115">模块不能。</span><span class="sxs-lookup"><span data-stu-id="05ce3-115">Modules cannot.</span></span>
* <span data-ttu-id="05ce3-116">模块可以使用`[<RequireQualifiedAccess>]`和`[<AutoOpen>]`进行修饰。</span><span class="sxs-lookup"><span data-stu-id="05ce3-116">Modules can be decorated with `[<RequireQualifiedAccess>]` and `[<AutoOpen>]`.</span></span>

<span data-ttu-id="05ce3-117">以下指南将帮助您使用这些准则来组织代码。</span><span class="sxs-lookup"><span data-stu-id="05ce3-117">The following guidelines will help you use these to organize your code.</span></span>

### <a name="prefer-namespaces-at-the-top-level"></a><span data-ttu-id="05ce3-118">首选顶层的命名空间</span><span class="sxs-lookup"><span data-stu-id="05ce3-118">Prefer namespaces at the top level</span></span>

<span data-ttu-id="05ce3-119">对于任何公共易用代码，命名空间优先支持顶层模块。</span><span class="sxs-lookup"><span data-stu-id="05ce3-119">For any publicly consumable code, namespaces are preferential to modules at the top level.</span></span> <span data-ttu-id="05ce3-120">因为它们编译为 .NET 命名空间，因此它们可消耗来自 C#，没有问题。</span><span class="sxs-lookup"><span data-stu-id="05ce3-120">Because they are compiled as .NET namespaces, they are consumable from C# with no issue.</span></span>

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

<span data-ttu-id="05ce3-121">仅从 F# 调用时，使用顶级模块可能看起来不同，但对于 C# 使用者，调用方可能会因为必须符合`MyClass``MyCode`该模块的资格而感到惊讶。</span><span class="sxs-lookup"><span data-stu-id="05ce3-121">Using a top-level module may not appear different when called only from F#, but for C# consumers, callers may be surprised by having to qualify `MyClass` with the `MyCode` module.</span></span>

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a><span data-ttu-id="05ce3-122">小心涂抹`[<AutoOpen>]`</span><span class="sxs-lookup"><span data-stu-id="05ce3-122">Carefully apply `[<AutoOpen>]`</span></span>

<span data-ttu-id="05ce3-123">构造`[<AutoOpen>]`会污染调用方可用的范围，而对事物来源的答案是"神奇"。</span><span class="sxs-lookup"><span data-stu-id="05ce3-123">The `[<AutoOpen>]` construct can pollute the scope of what is available to callers, and the answer to where something comes from is "magic".</span></span> <span data-ttu-id="05ce3-124">这不是一件好事。</span><span class="sxs-lookup"><span data-stu-id="05ce3-124">This is not a good thing.</span></span> <span data-ttu-id="05ce3-125">此规则的一个例外是 F# 核心库本身（尽管这一事实也有点争议）。</span><span class="sxs-lookup"><span data-stu-id="05ce3-125">An exception to this rule is the F# Core Library itself (though this fact is also a bit controversial).</span></span>

<span data-ttu-id="05ce3-126">但是，如果您具有公共 API 的帮助器功能，您希望独立于该公共 API 进行组织，则这样做会很方便。</span><span class="sxs-lookup"><span data-stu-id="05ce3-126">However, it is a convenience if you have helper functionality for a public API that you wish to organize separately from that public API.</span></span>

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

<span data-ttu-id="05ce3-127">这样，您就可以将实现详细信息与函数的公共 API 进行干净分离，而无需在每次调用帮助程序时完全限定帮助程序。</span><span class="sxs-lookup"><span data-stu-id="05ce3-127">This lets you cleanly separate implementation details from the public API of a function without having to fully qualify a helper each time you call it.</span></span>

<span data-ttu-id="05ce3-128">此外，在命名空间级别公开扩展方法和表达式生成器可以使用 整齐地表示。 `[<AutoOpen>]`</span><span class="sxs-lookup"><span data-stu-id="05ce3-128">Additionally, exposing extension methods and expression builders at the namespace level can be neatly expressed with `[<AutoOpen>]`.</span></span>

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a><span data-ttu-id="05ce3-129">每当`[<RequireQualifiedAccess>]`名称可能发生冲突或您觉得它有助于可读性时使用</span><span class="sxs-lookup"><span data-stu-id="05ce3-129">Use `[<RequireQualifiedAccess>]` whenever names could conflict or you feel it helps with readability</span></span>

<span data-ttu-id="05ce3-130">将`[<RequireQualifiedAccess>]`属性添加到模块表示可能无法打开模块，并且对模块元素的引用需要显式限定访问。</span><span class="sxs-lookup"><span data-stu-id="05ce3-130">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="05ce3-131">例如，`Microsoft.FSharp.Collections.List`模块具有此属性。</span><span class="sxs-lookup"><span data-stu-id="05ce3-131">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="05ce3-132">当模块中的函数和值具有可能与其他模块中的名称冲突的名称时，这非常有用。</span><span class="sxs-lookup"><span data-stu-id="05ce3-132">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="05ce3-133">要求合格的访问可以大大提高库的长期可维护性和可进化性。</span><span class="sxs-lookup"><span data-stu-id="05ce3-133">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a><span data-ttu-id="05ce3-134">从`open`拓扑上对语句进行排序</span><span class="sxs-lookup"><span data-stu-id="05ce3-134">Sort `open` statements topologically</span></span>

<span data-ttu-id="05ce3-135">在 F#中，声明的顺序很重要，包括与语句一`open`起。</span><span class="sxs-lookup"><span data-stu-id="05ce3-135">In F#, the order of declarations matters, including with `open` statements.</span></span> <span data-ttu-id="05ce3-136">这与 C# 不同，C#`using``using static`的影响与文件中这些语句的顺序无关。</span><span class="sxs-lookup"><span data-stu-id="05ce3-136">This is unlike C#, where the effect of `using` and `using static` is independent of the ordering of those statements in a file.</span></span>

<span data-ttu-id="05ce3-137">在 F# 中，打开到作用域中的元素可能会隐藏其他已经存在的元素。</span><span class="sxs-lookup"><span data-stu-id="05ce3-137">In F#, elements opened into a scope can shadow others already present.</span></span> <span data-ttu-id="05ce3-138">这意味着重新排序`open`语句可能会更改代码的含义。</span><span class="sxs-lookup"><span data-stu-id="05ce3-138">This means that reordering `open` statements could alter the meaning of code.</span></span> <span data-ttu-id="05ce3-139">因此，不建议对所有`open`语句进行任何任意排序（例如，以 alpha 数字方式排序），以免生成您可能期望的不同行为。</span><span class="sxs-lookup"><span data-stu-id="05ce3-139">As a result, any arbitrary sorting of all `open` statements (for example, alphanumerically) is not recommended, lest you generate different behavior that you might expect.</span></span>

<span data-ttu-id="05ce3-140">相反，我们建议您[按拓扑分类](https://en.wikipedia.org/wiki/Topological_sorting)它们;也就是说，按定义系统`open`_图层_的顺序对语句进行排序。</span><span class="sxs-lookup"><span data-stu-id="05ce3-140">Instead, we recommend that you sort them [topologically](https://en.wikipedia.org/wiki/Topological_sorting); that is, order your `open` statements in the order in which _layers_ of your system are defined.</span></span> <span data-ttu-id="05ce3-141">也可以考虑在不同的拓扑层内进行字母数字排序。</span><span class="sxs-lookup"><span data-stu-id="05ce3-141">Doing alphanumeric sorting within different topological layers may also be considered.</span></span>

<span data-ttu-id="05ce3-142">例如，下面是 F# 编译器服务公共 API 文件的拓扑排序：</span><span class="sxs-lookup"><span data-stu-id="05ce3-142">As an example, here is the topological sorting for the F# compiler service public API file:</span></span>

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

<span data-ttu-id="05ce3-143">请注意，换行符将拓扑图层分开，之后将按字母数字对每一层进行排序。</span><span class="sxs-lookup"><span data-stu-id="05ce3-143">Note that a line break separates topological layers, with each layer being sorted alphanumerically afterwards.</span></span> <span data-ttu-id="05ce3-144">这样可以干净地组织代码，而不会意外地隐藏值。</span><span class="sxs-lookup"><span data-stu-id="05ce3-144">This cleanly organizes code without accidentally shadowing values.</span></span>

## <a name="use-classes-to-contain-values-that-have-side-effects"></a><span data-ttu-id="05ce3-145">使用类包含具有副作用的值</span><span class="sxs-lookup"><span data-stu-id="05ce3-145">Use classes to contain values that have side effects</span></span>

<span data-ttu-id="05ce3-146">初始化值很多时候会产生副作用，例如将上下文实例化到数据库或其他远程资源。</span><span class="sxs-lookup"><span data-stu-id="05ce3-146">There are many times when initializing a value can have side effects, such as instantiating a context to a database or other remote resource.</span></span> <span data-ttu-id="05ce3-147">在模块中初始化此类内容并将其用于后续函数是很有诱惑力的：</span><span class="sxs-lookup"><span data-stu-id="05ce3-147">It is tempting to initialize such things in a module and use it in subsequent functions:</span></span>

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

<span data-ttu-id="05ce3-148">由于几个原因，这通常是一个坏主意：</span><span class="sxs-lookup"><span data-stu-id="05ce3-148">This is frequently a bad idea for a few reasons:</span></span>

<span data-ttu-id="05ce3-149">首先，应用程序配置被推送到 代码库中`dep1`， `dep2`</span><span class="sxs-lookup"><span data-stu-id="05ce3-149">First, application configuration is pushed into the codebase with `dep1` and `dep2`.</span></span> <span data-ttu-id="05ce3-150">这在较大的代码库中很难维护。</span><span class="sxs-lookup"><span data-stu-id="05ce3-150">This is difficult to maintain in larger codebases.</span></span>

<span data-ttu-id="05ce3-151">其次，静态初始化数据不应包括不安全的线程值（如果组件本身将使用多个线程）。</span><span class="sxs-lookup"><span data-stu-id="05ce3-151">Second, statically initialized data should not include values that are not thread safe if your component will itself use multiple threads.</span></span> <span data-ttu-id="05ce3-152">这显然被`dep3`违反。</span><span class="sxs-lookup"><span data-stu-id="05ce3-152">This is clearly violated by `dep3`.</span></span>

<span data-ttu-id="05ce3-153">最后，模块初始化编译为整个编译单元的静态构造函数。</span><span class="sxs-lookup"><span data-stu-id="05ce3-153">Finally, module initialization compiles into a static constructor for the entire compilation unit.</span></span> <span data-ttu-id="05ce3-154">如果该模块中的允许绑定值初始化中出现任何错误，则该初始化将表现为`TypeInitializationException`然后缓存整个应用程序的生存期。</span><span class="sxs-lookup"><span data-stu-id="05ce3-154">If any error occurs in let-bound value initialization in that module, it manifests as a `TypeInitializationException` that is then cached for the entire lifetime of the application.</span></span> <span data-ttu-id="05ce3-155">这可能很难诊断。</span><span class="sxs-lookup"><span data-stu-id="05ce3-155">This can be difficult to diagnose.</span></span> <span data-ttu-id="05ce3-156">通常有一个内部异常，你可以尝试推理，但如果没有，那么没有告诉根本原因是什么。</span><span class="sxs-lookup"><span data-stu-id="05ce3-156">There is usually an inner exception that you can attempt to reason about, but if there is not, then there is no telling what the root cause is.</span></span>

<span data-ttu-id="05ce3-157">相反，只需使用简单类来保存依赖项：</span><span class="sxs-lookup"><span data-stu-id="05ce3-157">Instead, just use a simple class to hold dependencies:</span></span>

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member _.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member _.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

<span data-ttu-id="05ce3-158">这支持以下功能：</span><span class="sxs-lookup"><span data-stu-id="05ce3-158">This enables the following:</span></span>

1. <span data-ttu-id="05ce3-159">将任何从属状态推送到 API 本身之外。</span><span class="sxs-lookup"><span data-stu-id="05ce3-159">Pushing any dependent state outside of the API itself.</span></span>
2. <span data-ttu-id="05ce3-160">配置现在可以在 API 之外完成。</span><span class="sxs-lookup"><span data-stu-id="05ce3-160">Configuration can now be done outside of the API.</span></span>
3. <span data-ttu-id="05ce3-161">从属值的初始化错误不太可能表现为`TypeInitializationException`。</span><span class="sxs-lookup"><span data-stu-id="05ce3-161">Errors in initialization for dependent values are not likely to manifest as a `TypeInitializationException`.</span></span>
4. <span data-ttu-id="05ce3-162">API 现在更易于测试。</span><span class="sxs-lookup"><span data-stu-id="05ce3-162">The API is now easier to test.</span></span>

## <a name="error-management"></a><span data-ttu-id="05ce3-163">错误管理</span><span class="sxs-lookup"><span data-stu-id="05ce3-163">Error management</span></span>

<span data-ttu-id="05ce3-164">大型系统中的错误管理是一项复杂而细致的工作，在确保系统具有容错性和良好行为方面没有银弹。</span><span class="sxs-lookup"><span data-stu-id="05ce3-164">Error management in large systems is a complex and nuanced endeavor, and there are no silver bullets in ensuring your systems are fault-tolerant and behave well.</span></span> <span data-ttu-id="05ce3-165">以下指南应为导航此困难空间提供指导。</span><span class="sxs-lookup"><span data-stu-id="05ce3-165">The following guidelines should offer guidance in navigating this difficult space.</span></span>

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a><span data-ttu-id="05ce3-166">在域固有的类型中表示错误案例和非法状态</span><span class="sxs-lookup"><span data-stu-id="05ce3-166">Represent error cases and illegal state in types intrinsic to your domain</span></span>

<span data-ttu-id="05ce3-167">使用["歧视联合"，F#](../language-reference/discriminated-unions.md)使您能够在类型系统中表示错误的程序状态。</span><span class="sxs-lookup"><span data-stu-id="05ce3-167">With [Discriminated Unions](../language-reference/discriminated-unions.md), F# gives you the ability to represent faulty program state in your type system.</span></span> <span data-ttu-id="05ce3-168">例如：</span><span class="sxs-lookup"><span data-stu-id="05ce3-168">For example:</span></span>

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

<span data-ttu-id="05ce3-169">在这种情况下，有三种已知方式从银行帐户提取资金可能会失败。</span><span class="sxs-lookup"><span data-stu-id="05ce3-169">In this case, there are three known ways that withdrawing money from a bank account can fail.</span></span> <span data-ttu-id="05ce3-170">每个错误案例都以类型表示，因此可以在整个程序中安全地处理。</span><span class="sxs-lookup"><span data-stu-id="05ce3-170">Each error case is represented in the type, and can thus be dealt with safely throughout the program.</span></span>

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

<span data-ttu-id="05ce3-171">通常，如果可以对域中某些内容可能**失败**的不同方式进行建模，则错误处理代码不再被视为除常规程序流之外必须处理的内容。</span><span class="sxs-lookup"><span data-stu-id="05ce3-171">In general, if you can model the different ways that something can **fail** in your domain, then error handling code is no longer treated as something you must deal with in addition to regular program flow.</span></span> <span data-ttu-id="05ce3-172">它只是正常程序流的一部分，不被认为是**例外**。</span><span class="sxs-lookup"><span data-stu-id="05ce3-172">It is simply a part of normal program flow, and not considered **exceptional**.</span></span> <span data-ttu-id="05ce3-173">这有两个主要好处：</span><span class="sxs-lookup"><span data-stu-id="05ce3-173">There are two primary benefits to this:</span></span>

1. <span data-ttu-id="05ce3-174">随着域随时间的变化而更易于维护。</span><span class="sxs-lookup"><span data-stu-id="05ce3-174">It is easier to maintain as your domain changes over time.</span></span>
2. <span data-ttu-id="05ce3-175">错误案例更易于单元测试。</span><span class="sxs-lookup"><span data-stu-id="05ce3-175">Error cases are easier to unit test.</span></span>

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a><span data-ttu-id="05ce3-176">当无法用类型表示错误时，请使用异常</span><span class="sxs-lookup"><span data-stu-id="05ce3-176">Use exceptions when errors cannot be represented with types</span></span>

<span data-ttu-id="05ce3-177">并非所有错误都可以在问题域中表示。</span><span class="sxs-lookup"><span data-stu-id="05ce3-177">Not all errors can be represented in a problem domain.</span></span> <span data-ttu-id="05ce3-178">这些类型的故障在性质上*是例外*的，因此能够提高和捕获 F# 中的异常。</span><span class="sxs-lookup"><span data-stu-id="05ce3-178">These kinds of faults are *exceptional* in nature, hence the ability to raise and catch exceptions in F#.</span></span>

<span data-ttu-id="05ce3-179">首先，建议您阅读[例外设计指南](../../standard/design-guidelines/exceptions.md)。</span><span class="sxs-lookup"><span data-stu-id="05ce3-179">First, it is recommended that you read the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md).</span></span> <span data-ttu-id="05ce3-180">这些也适用于 F#。</span><span class="sxs-lookup"><span data-stu-id="05ce3-180">These are also applicable to F#.</span></span>

<span data-ttu-id="05ce3-181">F# 中用于引发异常的主要构造应考虑以下首选项顺序：</span><span class="sxs-lookup"><span data-stu-id="05ce3-181">The main constructs available in F# for the purposes of raising exceptions should be considered in the following order of preference:</span></span>

| <span data-ttu-id="05ce3-182">函数</span><span class="sxs-lookup"><span data-stu-id="05ce3-182">Function</span></span> | <span data-ttu-id="05ce3-183">语法</span><span class="sxs-lookup"><span data-stu-id="05ce3-183">Syntax</span></span> | <span data-ttu-id="05ce3-184">目的</span><span class="sxs-lookup"><span data-stu-id="05ce3-184">Purpose</span></span> |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | <span data-ttu-id="05ce3-185">使用指定的`System.ArgumentNullException`参数名称引发 a。</span><span class="sxs-lookup"><span data-stu-id="05ce3-185">Raises a `System.ArgumentNullException` with the specified argument name.</span></span> |
| `invalidArg` | `invalidArg "argumentName" "message"` | <span data-ttu-id="05ce3-186">使用指定的`System.ArgumentException`参数名称和消息引发 。</span><span class="sxs-lookup"><span data-stu-id="05ce3-186">Raises a `System.ArgumentException` with a specified argument name and message.</span></span> |
| `invalidOp` | `invalidOp "message"` | <span data-ttu-id="05ce3-187">使用指定`System.InvalidOperationException`的消息引发 a。</span><span class="sxs-lookup"><span data-stu-id="05ce3-187">Raises a `System.InvalidOperationException` with the specified message.</span></span> |
|`raise`| `raise (ExceptionType("message"))` | <span data-ttu-id="05ce3-188">用于引发异常的通用机制。</span><span class="sxs-lookup"><span data-stu-id="05ce3-188">General-purpose mechanism for throwing exceptions.</span></span> |
| `failwith` | `failwith "message"` | <span data-ttu-id="05ce3-189">使用指定`System.Exception`的消息引发 a。</span><span class="sxs-lookup"><span data-stu-id="05ce3-189">Raises a `System.Exception` with the specified message.</span></span> |
| `failwithf` | `failwithf "format string" argForFormatString` | <span data-ttu-id="05ce3-190">使用格式`System.Exception`字符串及其输入确定的消息引发 。</span><span class="sxs-lookup"><span data-stu-id="05ce3-190">Raises a `System.Exception` with a message determined by the format string and its inputs.</span></span> |

<span data-ttu-id="05ce3-191">使用`nullArg` `invalidArg` ，`invalidOp`并作为投掷`ArgumentNullException`的机制，`ArgumentException`并在`InvalidOperationException`适当时使用 。</span><span class="sxs-lookup"><span data-stu-id="05ce3-191">Use `nullArg`, `invalidArg` and `invalidOp` as the mechanism to throw `ArgumentNullException`, `ArgumentException` and `InvalidOperationException` when appropriate.</span></span>

<span data-ttu-id="05ce3-192">通常`failwith`应避免`failwithf`和 函数，因为它们会引发基`Exception`类型，而不是特定的异常。</span><span class="sxs-lookup"><span data-stu-id="05ce3-192">The `failwith` and `failwithf` functions should generally be avoided because they raise the base `Exception` type, not a specific exception.</span></span> <span data-ttu-id="05ce3-193">根据[例外设计指南](../../standard/design-guidelines/exceptions.md)，您希望在可以时提出更具体的异常。</span><span class="sxs-lookup"><span data-stu-id="05ce3-193">As per the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md), you want to raise more specific exceptions when you can.</span></span>

### <a name="using-exception-handling-syntax"></a><span data-ttu-id="05ce3-194">使用异常处理语法</span><span class="sxs-lookup"><span data-stu-id="05ce3-194">Using exception-handling syntax</span></span>

<span data-ttu-id="05ce3-195">F# 通过`try...with`语法支持异常模式：</span><span class="sxs-lookup"><span data-stu-id="05ce3-195">F# supports exception patterns via the `try...with` syntax:</span></span>

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

<span data-ttu-id="05ce3-196">如果要保持代码整洁，在面对模式匹配的异常时要执行的功能可能会有点棘手。</span><span class="sxs-lookup"><span data-stu-id="05ce3-196">Reconciling functionality to perform in the face of an exception with pattern matching can be a bit tricky if you wish to keep the code clean.</span></span> <span data-ttu-id="05ce3-197">处理这种情况的一种方法是使用[活动模式](../language-reference/active-patterns.md)作为将围绕错误案例的功能分组具有异常本身的方法。</span><span class="sxs-lookup"><span data-stu-id="05ce3-197">One such way to handle this is to use [active patterns](../language-reference/active-patterns.md) as a means to group functionality surrounding an error case with an exception itself.</span></span> <span data-ttu-id="05ce3-198">例如，您可能正在使用 API，当它引发异常时，该 API 会将有价值的信息包含在异常元数据中。</span><span class="sxs-lookup"><span data-stu-id="05ce3-198">For example, you may be consuming an API that, when it throws an exception, encloses valuable information in the exception metadata.</span></span> <span data-ttu-id="05ce3-199">在某些情况下，在活动模式内展开捕获的异常正文中的有用值并返回该值可能会有所帮助。</span><span class="sxs-lookup"><span data-stu-id="05ce3-199">Unwrapping a useful value in the body of the captured exception inside the Active Pattern and returning that value can be helpful in some situations.</span></span>

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a><span data-ttu-id="05ce3-200">请勿使用单体错误处理来替换异常</span><span class="sxs-lookup"><span data-stu-id="05ce3-200">Do not use monadic error handling to replace exceptions</span></span>

<span data-ttu-id="05ce3-201">异常在函数式编程中被视为一些禁忌。</span><span class="sxs-lookup"><span data-stu-id="05ce3-201">Exceptions are seen as somewhat taboo in functional programming.</span></span> <span data-ttu-id="05ce3-202">事实上，异常会侵犯纯度，因此可以放心地考虑它们不太有效。</span><span class="sxs-lookup"><span data-stu-id="05ce3-202">Indeed, exceptions violate purity, so it's safe to consider them not-quite functional.</span></span> <span data-ttu-id="05ce3-203">但是，这忽略了代码必须运行的位置，并且可能发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="05ce3-203">However, this ignores the reality of where code must run, and that runtime errors can occur.</span></span> <span data-ttu-id="05ce3-204">通常，编写代码时假定大多数事物既不是纯的也不是完全的，以尽量减少令人不快的意外。</span><span class="sxs-lookup"><span data-stu-id="05ce3-204">In general, write code on the assumption that most things are neither pure nor total, to minimize unpleasant surprises.</span></span>

<span data-ttu-id="05ce3-205">在 .NET 运行时和整个跨语言生态系统中的相关性和适当性方面，必须考虑异常的以下核心优势/方面：</span><span class="sxs-lookup"><span data-stu-id="05ce3-205">It is important to consider the following core strengths/aspects of Exceptions with respect to their relevance and appropriateness in the .NET runtime and cross-language ecosystem as a whole:</span></span>

1. <span data-ttu-id="05ce3-206">它们包含详细的诊断信息，这在调试问题时非常有用。</span><span class="sxs-lookup"><span data-stu-id="05ce3-206">They contain detailed diagnostic information, which is very helpful when debugging an issue.</span></span>
2. <span data-ttu-id="05ce3-207">运行时和其他 .NET 语言都很好地理解它们。</span><span class="sxs-lookup"><span data-stu-id="05ce3-207">They are well-understood by the runtime and other .NET languages.</span></span>
3. <span data-ttu-id="05ce3-208">与通过临时实现语义的某些子集来*避免*异常的代码相比，它们可以减少重要的样板。</span><span class="sxs-lookup"><span data-stu-id="05ce3-208">They can reduce significant boilerplate when compared with code that goes out of its way to *avoid* exceptions by implementing some subset of their semantics on an ad-hoc basis.</span></span>

<span data-ttu-id="05ce3-209">第三点至关重要。</span><span class="sxs-lookup"><span data-stu-id="05ce3-209">This third point is critical.</span></span> <span data-ttu-id="05ce3-210">对于不处理非大型复杂操作，不使用异常可能会导致处理这样的结构：</span><span class="sxs-lookup"><span data-stu-id="05ce3-210">For nontrivial complex operations, failing to use exceptions can result in dealing with structures like this:</span></span>

```fsharp
Result<Result<MyType, string>, string list>
```

<span data-ttu-id="05ce3-211">这很容易导致脆弱的代码，如模式匹配的"字符串类型"错误：</span><span class="sxs-lookup"><span data-stu-id="05ce3-211">Which can easily lead to fragile code like pattern matching on "stringly-typed" errors:</span></span>

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

<span data-ttu-id="05ce3-212">此外，对于返回"更好"类型的"简单"函数的渴望，可以接受任何异常是很有诱惑力的：</span><span class="sxs-lookup"><span data-stu-id="05ce3-212">Additionally, it can be tempting to swallow any exception in the desire for a "simple" function that returns a "nicer" type:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

<span data-ttu-id="05ce3-213">遗憾的是，`tryReadAllText`可以基于文件系统上可能发生的无数事情引发大量异常，并且此代码会丢弃有关环境中实际出错的任何信息。</span><span class="sxs-lookup"><span data-stu-id="05ce3-213">Unfortunately, `tryReadAllText` can throw numerous exceptions based on the myriad of things that can happen on a file system, and this code discards away any information about what might actually be going wrong in your environment.</span></span> <span data-ttu-id="05ce3-214">如果使用此代码类型替换此代码，则返回"字符串键入"错误消息分析：</span><span class="sxs-lookup"><span data-stu-id="05ce3-214">If you replace this code with a result type, then you're back to "stringly-typed" error message parsing:</span></span>

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

<span data-ttu-id="05ce3-215">将异常对象本身放在构造函数中`Error`只会强制您在调用站点而不是函数中正确处理异常类型。</span><span class="sxs-lookup"><span data-stu-id="05ce3-215">And placing the exception object itself in the `Error` constructor just forces you to properly deal with the exception type at the call site rather than in the function.</span></span> <span data-ttu-id="05ce3-216">这样做可以有效地创建已检查的异常，这些异常作为 API 的调用方处理起来非常不有趣。</span><span class="sxs-lookup"><span data-stu-id="05ce3-216">Doing this effectively creates checked exceptions, which are notoriously unfun to deal with as a caller of an API.</span></span>

<span data-ttu-id="05ce3-217">上述示例的一个很好的替代方法是在该异常上下文中捕获*特定*异常并返回有意义的值。</span><span class="sxs-lookup"><span data-stu-id="05ce3-217">A good alternative to the above examples is to catch *specific* exceptions and return a meaningful value in the context of that exception.</span></span> <span data-ttu-id="05ce3-218">如果修改函数`tryReadAllText`如下所示，`None`则具有更多含义：</span><span class="sxs-lookup"><span data-stu-id="05ce3-218">If you modify the `tryReadAllText` function as follows, `None` has more meaning:</span></span>

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

<span data-ttu-id="05ce3-219">现在，当找不到文件并将该含义分配给返回时，此函数将正确处理案例，而不是充当"全部捕获"功能。</span><span class="sxs-lookup"><span data-stu-id="05ce3-219">Instead of functioning as a catch-all, this function will now properly handle the case when a file was not found and assign that meaning to a return.</span></span> <span data-ttu-id="05ce3-220">此返回值可以映射到该错误情况，同时不会放弃任何上下文信息或强制调用方处理代码中此时可能不相关的案例。</span><span class="sxs-lookup"><span data-stu-id="05ce3-220">This return value can map to that error case, while not discarding any contextual information or forcing callers to deal with a case that may not be relevant at that point in the code.</span></span>

<span data-ttu-id="05ce3-221">类型（如`Result<'Success, 'Error>`适用于未嵌套的基本操作）和 F# 可选类型非常适合表示某些内容可以返回*或\*\*什么都不*返回时。</span><span class="sxs-lookup"><span data-stu-id="05ce3-221">Types such as `Result<'Success, 'Error>` are appropriate for basic operations where they aren't nested, and F# optional types are perfect for representing when something could either return *something* or *nothing*.</span></span> <span data-ttu-id="05ce3-222">但是，它们不是异常的替换，不应用于尝试替换异常。</span><span class="sxs-lookup"><span data-stu-id="05ce3-222">They are not a replacement for exceptions, though, and should not be used in an attempt to replace exceptions.</span></span> <span data-ttu-id="05ce3-223">相反，应明智地应用它们，以有针对性的方式处理异常和错误管理政策的具体方面。</span><span class="sxs-lookup"><span data-stu-id="05ce3-223">Rather, they should be applied judiciously to address specific aspects of exception and error management policy in targeted ways.</span></span>

## <a name="partial-application-and-point-free-programming"></a><span data-ttu-id="05ce3-224">部分应用和无点编程</span><span class="sxs-lookup"><span data-stu-id="05ce3-224">Partial application and point-free programming</span></span>

<span data-ttu-id="05ce3-225">F# 支持部分应用程序，因此，以各种方式以无点样式进行编程。</span><span class="sxs-lookup"><span data-stu-id="05ce3-225">F# supports partial application, and thus, various ways to program in a point-free style.</span></span> <span data-ttu-id="05ce3-226">这有利于模块内的代码重用或某些内容的实现，但这不是公开的内容。</span><span class="sxs-lookup"><span data-stu-id="05ce3-226">This can be beneficial for code reuse within a module or the implementation of something, but it is not something to expose publicly.</span></span> <span data-ttu-id="05ce3-227">一般来说，无点编程本身并不是一种美德，它可以为不沉浸于这种风格的人增加一个重大的认知障碍。</span><span class="sxs-lookup"><span data-stu-id="05ce3-227">In general, point-free programming is not a virtue in and of itself, and can add a significant cognitive barrier for people who are not immersed in the style.</span></span>

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a><span data-ttu-id="05ce3-228">请勿在公共 API 中使用部分应用程序和咖喱</span><span class="sxs-lookup"><span data-stu-id="05ce3-228">Do not use partial application and currying in public APIs</span></span>

<span data-ttu-id="05ce3-229">除了很少的情况外，在公共 API 中使用部分应用程序可能会令使用者感到困惑。</span><span class="sxs-lookup"><span data-stu-id="05ce3-229">With little exception, the use of partial application in public APIs can be confusing for consumers.</span></span> <span data-ttu-id="05ce3-230">通常，F#`let`代码中的绑定值是**值**，而不是**函数值**。</span><span class="sxs-lookup"><span data-stu-id="05ce3-230">Usually, `let`-bound values in F# code are **values**, not **function values**.</span></span> <span data-ttu-id="05ce3-231">将值和函数值混合在一起可以节省少量代码行，以换取相当多的认知开销，特别是如果与组合函数等`>>`运算符结合使用时。</span><span class="sxs-lookup"><span data-stu-id="05ce3-231">Mixing together values and function values can result in saving a small number of lines of code in exchange for quite a bit of cognitive overhead, especially if combined with operators such as `>>` to compose functions.</span></span>

### <a name="consider-the-tooling-implications-for-point-free-programming"></a><span data-ttu-id="05ce3-232">考虑无点编程的工具含义</span><span class="sxs-lookup"><span data-stu-id="05ce3-232">Consider the tooling implications for point-free programming</span></span>

<span data-ttu-id="05ce3-233">库瑞德函数不标记其参数。</span><span class="sxs-lookup"><span data-stu-id="05ce3-233">Curried functions do not label their arguments.</span></span> <span data-ttu-id="05ce3-234">这具有工具含义。</span><span class="sxs-lookup"><span data-stu-id="05ce3-234">This has tooling implications.</span></span> <span data-ttu-id="05ce3-235">请考虑以下两个函数：</span><span class="sxs-lookup"><span data-stu-id="05ce3-235">Consider the following two functions:</span></span>

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

<span data-ttu-id="05ce3-236">两者都是有效的函数，`funcWithApplication`但都是一个咖喱函数。</span><span class="sxs-lookup"><span data-stu-id="05ce3-236">Both are valid functions, but `funcWithApplication` is a curried function.</span></span> <span data-ttu-id="05ce3-237">当您在编辑器中悬停在它们的类型上时，您将看到：</span><span class="sxs-lookup"><span data-stu-id="05ce3-237">When you hover over their types in an editor, you see this:</span></span>

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

<span data-ttu-id="05ce3-238">在呼叫站点，Visual Studio 等工具工具提示不会为您提供有关`string`和`int`输入类型实际表示的内容的有意义的信息。</span><span class="sxs-lookup"><span data-stu-id="05ce3-238">At the call site, tooltips in tooling such as Visual Studio will not give you meaningful information as to what the `string` and `int` input types actually represent.</span></span>

<span data-ttu-id="05ce3-239">如果您遇到这样的`funcWithApplication`无点代码是公共易用的，建议执行完全 +扩展，以便工具可以获取有意义的参数名称。</span><span class="sxs-lookup"><span data-stu-id="05ce3-239">If you encounter point-free code like `funcWithApplication` that is publicly consumable, it is recommended to do a full η-expansion so that tooling can pick up on meaningful names for arguments.</span></span>

<span data-ttu-id="05ce3-240">此外，调试无点代码可能具有挑战性，如果不是不可能的话。</span><span class="sxs-lookup"><span data-stu-id="05ce3-240">Furthermore, debugging point-free code can be challenging, if not impossible.</span></span> <span data-ttu-id="05ce3-241">调试工具依赖于绑定到名称的值（例如绑定`let`），以便在执行中途检查中间值。</span><span class="sxs-lookup"><span data-stu-id="05ce3-241">Debugging tools rely on values bound to names (for example, `let` bindings) so that you can inspect intermediate values midway through execution.</span></span> <span data-ttu-id="05ce3-242">当代码没有要检查的值时，将没有任何要调试的值。</span><span class="sxs-lookup"><span data-stu-id="05ce3-242">When your code has no values to inspect, there is nothing to debug.</span></span> <span data-ttu-id="05ce3-243">将来，调试工具可能会根据以前执行的路径来合成这些值，但最好对*潜在的*调试功能进行对冲。</span><span class="sxs-lookup"><span data-stu-id="05ce3-243">In the future, debugging tools may evolve to synthesize these values based on previously executed paths, but it's not a good idea to hedge your bets on *potential* debugging functionality.</span></span>

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a><span data-ttu-id="05ce3-244">将部分应用视为减少内部样板的技术</span><span class="sxs-lookup"><span data-stu-id="05ce3-244">Consider partial application as a technique to reduce internal boilerplate</span></span>

<span data-ttu-id="05ce3-245">与前一点不同，部分应用程序是减少应用程序内部的样板或 API 的深层内部的绝妙工具。</span><span class="sxs-lookup"><span data-stu-id="05ce3-245">In contrast to the previous point, partial application is a wonderful tool for reducing boilerplate inside of an application or the deeper internals of an API.</span></span> <span data-ttu-id="05ce3-246">对于单元测试更复杂的 API 的实现很有帮助，其中样板通常需要处理。</span><span class="sxs-lookup"><span data-stu-id="05ce3-246">It can be helpful for unit testing the implementation of more complicated APIs, where boilerplate is often a pain to deal with.</span></span> <span data-ttu-id="05ce3-247">例如，以下代码演示如何完成大多数模拟框架所赋予您的内容，而无需对此类框架进行外部依赖，并且必须学习相关的定制 API。</span><span class="sxs-lookup"><span data-stu-id="05ce3-247">For example, the following code shows how you can accomplish what most mocking frameworks give you without taking an external dependency on such a framework and having to learn a related bespoke API.</span></span>

<span data-ttu-id="05ce3-248">例如，请考虑以下解决方案地形：</span><span class="sxs-lookup"><span data-stu-id="05ce3-248">For example, consider the following solution topography:</span></span>

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

<span data-ttu-id="05ce3-249">`ImplementationLogic.fsproj`可能会公开代码，例如：</span><span class="sxs-lookup"><span data-stu-id="05ce3-249">`ImplementationLogic.fsproj` might expose code such as:</span></span>

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member _.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

<span data-ttu-id="05ce3-250">单元`ImplementationLogic.Tests.fsproj`测试`Transactions.doTransaction`非常简单：</span><span class="sxs-lookup"><span data-stu-id="05ce3-250">Unit testing `Transactions.doTransaction` in `ImplementationLogic.Tests.fsproj` is easy:</span></span>

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

<span data-ttu-id="05ce3-251">使用模拟`doTransaction`上下文对象进行部分应用允许您在所有单元测试中调用函数，而无需每次都构造模拟上下文：</span><span class="sxs-lookup"><span data-stu-id="05ce3-251">Partially applying `doTransaction` with a mocking context object lets you call the function in all of your unit tests without needing to construct a mocked context each time:</span></span>

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

<span data-ttu-id="05ce3-252">此技术不应普遍应用于整个代码库，但它是减少复杂内部和单元测试这些内部的样板的好方法。</span><span class="sxs-lookup"><span data-stu-id="05ce3-252">This technique should not be universally applied to your entire codebase, but it is a good way to reduce boilerplate for complicated internals and unit testing those internals.</span></span>

## <a name="access-control"></a><span data-ttu-id="05ce3-253">访问控制</span><span class="sxs-lookup"><span data-stu-id="05ce3-253">Access control</span></span>

<span data-ttu-id="05ce3-254">F# 具有多个[访问控制](../language-reference/access-control.md)选项，从 .NET 运行时中可用的选项继承。</span><span class="sxs-lookup"><span data-stu-id="05ce3-254">F# has multiple options for [Access control](../language-reference/access-control.md), inherited from what is available in the .NET runtime.</span></span> <span data-ttu-id="05ce3-255">这些不仅可用于类型 - 您也可以将它们用于函数。</span><span class="sxs-lookup"><span data-stu-id="05ce3-255">These are not just usable for types - you can use them for functions, too.</span></span>

* <span data-ttu-id="05ce3-256">首选非`public`类型和成员，直到您需要它们是公共消耗品。</span><span class="sxs-lookup"><span data-stu-id="05ce3-256">Prefer non-`public` types and members until you need them to be publicly consumable.</span></span> <span data-ttu-id="05ce3-257">这也最大限度地减少了消费者对之的耦合。</span><span class="sxs-lookup"><span data-stu-id="05ce3-257">This also minimizes what consumers couple to.</span></span>
* <span data-ttu-id="05ce3-258">努力保持所有帮助器的功能`private`。</span><span class="sxs-lookup"><span data-stu-id="05ce3-258">Strive to keep all helper functionality `private`.</span></span>
* <span data-ttu-id="05ce3-259">请考虑在帮助器`[<AutoOpen>]`函数的专用模块上使用这些函数（如果它们变为大量）。</span><span class="sxs-lookup"><span data-stu-id="05ce3-259">Consider the use of `[<AutoOpen>]` on a private module of helper functions if they become numerous.</span></span>

## <a name="type-inference-and-generics"></a><span data-ttu-id="05ce3-260">类型推理和泛型</span><span class="sxs-lookup"><span data-stu-id="05ce3-260">Type inference and generics</span></span>

<span data-ttu-id="05ce3-261">类型推理可以节省您输入大量样板。</span><span class="sxs-lookup"><span data-stu-id="05ce3-261">Type inference can save you from typing a lot of boilerplate.</span></span> <span data-ttu-id="05ce3-262">F# 编译器中的自动泛化可以帮助您编写更通用的代码，而您几乎不需要额外的工作。</span><span class="sxs-lookup"><span data-stu-id="05ce3-262">And automatic generalization in the F# compiler can help you write more generic code with almost no extra effort on your part.</span></span> <span data-ttu-id="05ce3-263">但是，这些功能并非普遍良好。</span><span class="sxs-lookup"><span data-stu-id="05ce3-263">However, these features are not universally good.</span></span>

* <span data-ttu-id="05ce3-264">请考虑在公共 API 中标记具有显式类型的参数名称，并且不要为此依赖类型推断。</span><span class="sxs-lookup"><span data-stu-id="05ce3-264">Consider labeling argument names with explicit types in public APIs and do not rely on type inference for this.</span></span>

    <span data-ttu-id="05ce3-265">原因是**您应该**控制 API 的形状，而不是编译器。</span><span class="sxs-lookup"><span data-stu-id="05ce3-265">The reason for this is that **you** should be in control of the shape of your API, not the compiler.</span></span> <span data-ttu-id="05ce3-266">尽管编译器可以出色地推断类型，但如果它所依赖的内部类型已更改，则 API 的形状可能会发生变化。</span><span class="sxs-lookup"><span data-stu-id="05ce3-266">Although the compiler can do a fine job at inferring types for you, it is possible to have the shape of your API change if the internals it relies on have changed types.</span></span> <span data-ttu-id="05ce3-267">这可能是你想要的，但它几乎肯定会导致一个突破的API更改，然后下游使用者将不得不处理。</span><span class="sxs-lookup"><span data-stu-id="05ce3-267">This may be what you want, but it will almost certainly result in a breaking API change that downstream consumers will then have to deal with.</span></span> <span data-ttu-id="05ce3-268">相反，如果您显式控制公共 API 的形状，则可以控制这些重大更改。</span><span class="sxs-lookup"><span data-stu-id="05ce3-268">Instead, if you explicitly control the shape of your public API, then you can control these breaking changes.</span></span> <span data-ttu-id="05ce3-269">用 DDD 术语来说，这可以被视为反腐败层。</span><span class="sxs-lookup"><span data-stu-id="05ce3-269">In DDD terms, this can be thought of as an Anti-corruption layer.</span></span>

* <span data-ttu-id="05ce3-270">请考虑为泛型参数指定一个有意义的名称。</span><span class="sxs-lookup"><span data-stu-id="05ce3-270">Consider giving a meaningful name to your generic arguments.</span></span>

    <span data-ttu-id="05ce3-271">除非您正在编写不特定于特定域的真正通用代码，否则有意义的名称可以帮助其他程序员了解他们正在处理的域。</span><span class="sxs-lookup"><span data-stu-id="05ce3-271">Unless you are writing truly generic code that is not specific to a particular domain, a meaningful name can help other programmers understanding the domain they're working in.</span></span> <span data-ttu-id="05ce3-272">例如，在与文档数据库交互的`'Document`上下文中命名的类型参数使正在使用的函数或成员可以接受通用文档类型更加清晰。</span><span class="sxs-lookup"><span data-stu-id="05ce3-272">For example, a type parameter named `'Document` in the context of interacting with a document database makes it clearer that generic document types can be accepted by the function or member you are working with.</span></span>

* <span data-ttu-id="05ce3-273">请考虑使用 PascalCase 命名泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="05ce3-273">Consider naming generic type parameters with PascalCase.</span></span>

    <span data-ttu-id="05ce3-274">这是在 .NET 中执行操作的一般方法，因此建议您使用 PascalCase 而不是snake_case或骆驼Case。</span><span class="sxs-lookup"><span data-stu-id="05ce3-274">This is the general way to do things in .NET, so it's recommended that you use PascalCase rather than snake_case or camelCase.</span></span>

<span data-ttu-id="05ce3-275">最后，对于 F# 或大型代码库的新增人员而言，自动泛化并不总是一个福音。</span><span class="sxs-lookup"><span data-stu-id="05ce3-275">Finally, automatic generalization is not always a boon for people who are new to F# or a large codebase.</span></span> <span data-ttu-id="05ce3-276">使用通用组件存在认知开销。</span><span class="sxs-lookup"><span data-stu-id="05ce3-276">There is cognitive overhead in using components that are generic.</span></span> <span data-ttu-id="05ce3-277">此外，如果自动通用化函数不用于不同的输入类型（更不用说它们打算用作此类函数），那么在那个时间点，它们是泛型函数没有实际的好处。</span><span class="sxs-lookup"><span data-stu-id="05ce3-277">Furthermore, if automatically generalized functions are not used with different input types (let alone if they are intended to be used as such), then there is no real benefit to them being generic at that point in time.</span></span> <span data-ttu-id="05ce3-278">始终考虑您编写的代码是否实际上将受益于泛型。</span><span class="sxs-lookup"><span data-stu-id="05ce3-278">Always consider if the code you are writing will actually benefit from being generic.</span></span>

## <a name="performance"></a><span data-ttu-id="05ce3-279">性能</span><span class="sxs-lookup"><span data-stu-id="05ce3-279">Performance</span></span>

### <a name="prefer-structs-for-small-data-types"></a><span data-ttu-id="05ce3-280">首选小型数据类型的结构</span><span class="sxs-lookup"><span data-stu-id="05ce3-280">Prefer structs for small data types</span></span>

<span data-ttu-id="05ce3-281">使用结构（也称为值类型）通常会导致某些代码的性能更高，因为它通常避免分配对象。</span><span class="sxs-lookup"><span data-stu-id="05ce3-281">Using structs (also called Value Types) can often result in higher performance for some code because it typically avoids allocating objects.</span></span> <span data-ttu-id="05ce3-282">但是，结构并不总是一个"更快"按钮：如果结构中的数据大小超过 16 个字节，则复制数据通常会导致比使用引用类型花费更多的 CPU 时间。</span><span class="sxs-lookup"><span data-stu-id="05ce3-282">However, structs are not always a "go faster" button: if the size of the data in a struct exceeds 16 bytes, copying the data can often result in more CPU time spend than using a reference type.</span></span>

<span data-ttu-id="05ce3-283">要确定是否应使用结构，请考虑以下条件：</span><span class="sxs-lookup"><span data-stu-id="05ce3-283">To determine if you should use a struct, consider the following conditions:</span></span>

- <span data-ttu-id="05ce3-284">如果数据的大小为 16 字节或更小。</span><span class="sxs-lookup"><span data-stu-id="05ce3-284">If the size of your data is 16 bytes or smaller.</span></span>
- <span data-ttu-id="05ce3-285">如果运行程序中的内存中可能有许多此类数据类型驻留在内存中。</span><span class="sxs-lookup"><span data-stu-id="05ce3-285">If you're likely to have many of these data types resident in memory in a running program.</span></span>

<span data-ttu-id="05ce3-286">如果应用第一个条件，通常应使用结构。</span><span class="sxs-lookup"><span data-stu-id="05ce3-286">If the first condition applies, you should generally use a struct.</span></span> <span data-ttu-id="05ce3-287">如果两者都适用，您几乎总是应该使用结构。</span><span class="sxs-lookup"><span data-stu-id="05ce3-287">If both apply, you should almost always use a struct.</span></span> <span data-ttu-id="05ce3-288">可能在某些情况下，应用前面的条件，但使用结构并不比使用引用类型更好或更差，但它们可能很少见。</span><span class="sxs-lookup"><span data-stu-id="05ce3-288">There may be some cases where the previous conditions apply, but using a struct is no better or worse than using a reference type, but they are likely to be rare.</span></span> <span data-ttu-id="05ce3-289">但是，在进行这样的更改时，始终要衡量，而不是根据假设或直觉行事，这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="05ce3-289">It's important to always measure when making changes like this, though, and not operate on assumption or intuition.</span></span>

#### <a name="prefer-struct-tuples-when-grouping-small-value-types"></a><span data-ttu-id="05ce3-290">在分组小值类型时，首选结构组合</span><span class="sxs-lookup"><span data-stu-id="05ce3-290">Prefer struct tuples when grouping small value types</span></span>

<span data-ttu-id="05ce3-291">请考虑以下两个函数：</span><span class="sxs-lookup"><span data-stu-id="05ce3-291">Consider the following two functions:</span></span>

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

<span data-ttu-id="05ce3-292">当您使用基准数据测试工具（如[基准点网](https://benchmarkdotnet.org/)）对这些函数进行基准测试时，您会发现使用`runWithStructTuple`结构元数的函数运行速度要快 40%，并且不分配内存。</span><span class="sxs-lookup"><span data-stu-id="05ce3-292">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that the `runWithStructTuple` function that uses struct tuples runs 40% faster and allocates no memory.</span></span>

<span data-ttu-id="05ce3-293">但是，这些结果并不总是在您自己的代码中如此。</span><span class="sxs-lookup"><span data-stu-id="05ce3-293">However, these results won't always be the case in your own code.</span></span> <span data-ttu-id="05ce3-294">如果将函数标记为`inline`，使用参考元数的代码可能会获得一些额外的优化，或者分配的代码可以简单地进行优化。</span><span class="sxs-lookup"><span data-stu-id="05ce3-294">If you mark a function as `inline`, code that uses reference tuples may get some additional optimizations, or code that would allocate could simply be optimized away.</span></span> <span data-ttu-id="05ce3-295">您应该始终在绩效方面衡量结果，并且绝不基于假设或直觉操作。</span><span class="sxs-lookup"><span data-stu-id="05ce3-295">You should always measure results whenever performance is concerned, and never operate based on assumption or intuition.</span></span>

#### <a name="prefer-struct-records-when-the-data-type-is-small"></a><span data-ttu-id="05ce3-296">数据类型较小时更喜欢结构记录</span><span class="sxs-lookup"><span data-stu-id="05ce3-296">Prefer struct records when the data type is small</span></span>

<span data-ttu-id="05ce3-297">前面描述的经验法则也适用于[F# 记录类型](../language-reference/records.md)。</span><span class="sxs-lookup"><span data-stu-id="05ce3-297">The rule of thumb described earlier also holds for [F# record types](../language-reference/records.md).</span></span> <span data-ttu-id="05ce3-298">请考虑处理它们的以下数据类型和函数：</span><span class="sxs-lookup"><span data-stu-id="05ce3-298">Consider the following data types and functions that process them:</span></span>

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

<span data-ttu-id="05ce3-299">这与前面的元组代码类似，但这次示例使用记录和内联内部函数。</span><span class="sxs-lookup"><span data-stu-id="05ce3-299">This is similar to the previous tuple code, but this time the example uses records and an inlined inner function.</span></span>

<span data-ttu-id="05ce3-300">当您使用基准数据测试工具（如[基准点网](https://benchmarkdotnet.org/)）对这些函数进行基准测试时，您会发现`processStructPoint`运行速度接近 60%，并且在托管堆上不分配任何内容。</span><span class="sxs-lookup"><span data-stu-id="05ce3-300">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that `processStructPoint` runs nearly 60% faster and allocates nothing on the managed heap.</span></span>

#### <a name="prefer-struct-discriminated-unions-when-the-data-type-is-small"></a><span data-ttu-id="05ce3-301">在数据类型较小时，首选结构区分结合</span><span class="sxs-lookup"><span data-stu-id="05ce3-301">Prefer struct discriminated unions when the data type is small</span></span>

<span data-ttu-id="05ce3-302">以前关于具有结构元数和记录的表现的观察也适用于[F_ 歧视联盟](../language-reference/discriminated-unions.md)。</span><span class="sxs-lookup"><span data-stu-id="05ce3-302">The previous observations about performance with struct tuples and records also holds for [F# Discriminated Unions](../language-reference/discriminated-unions.md).</span></span> <span data-ttu-id="05ce3-303">考虑下列代码：</span><span class="sxs-lookup"><span data-stu-id="05ce3-303">Consider the following code:</span></span>

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

<span data-ttu-id="05ce3-304">为域建模定义像这样的单一案例"歧视联合"很常见。</span><span class="sxs-lookup"><span data-stu-id="05ce3-304">It's common to define single-case Discriminated Unions like this for domain modeling.</span></span> <span data-ttu-id="05ce3-305">当您使用基准数据测试工具（如[基准点网](https://benchmarkdotnet.org/)）对这些函数进行基准测试时，您会发现`structReverseName`运行速度比`reverseName`小字符串快 25%。</span><span class="sxs-lookup"><span data-stu-id="05ce3-305">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that `structReverseName` runs about 25% faster than `reverseName` for small strings.</span></span> <span data-ttu-id="05ce3-306">对于大字符串，两者执行大致相同。</span><span class="sxs-lookup"><span data-stu-id="05ce3-306">For large strings, both perform about the same.</span></span> <span data-ttu-id="05ce3-307">因此，在这种情况下，最好使用结构。</span><span class="sxs-lookup"><span data-stu-id="05ce3-307">So, in this case, it's always preferable to use a struct.</span></span> <span data-ttu-id="05ce3-308">如前所述，始终根据假设或直觉进行测量和操作。</span><span class="sxs-lookup"><span data-stu-id="05ce3-308">As previously mentioned, always measure and do not operate on assumptions or intuition.</span></span>

<span data-ttu-id="05ce3-309">尽管前面的示例显示结构歧视联合产生了更好的性能，但建模域时通常具有较大的"歧视联合"。</span><span class="sxs-lookup"><span data-stu-id="05ce3-309">Although the previous example showed that a struct Discriminated Union yielded better performance, it is common to have larger Discriminated Unions when modeling a domain.</span></span> <span data-ttu-id="05ce3-310">如果较大的数据类型根据它们的操作进行结构，则它们可能无法很好地执行，因为可能涉及更多的复制。</span><span class="sxs-lookup"><span data-stu-id="05ce3-310">Larger data types like that may not perform as well if they are structs depending on the operations on them, since more copying could be involved.</span></span>

### <a name="functional-programming-and-mutation"></a><span data-ttu-id="05ce3-311">函数编程和突变</span><span class="sxs-lookup"><span data-stu-id="05ce3-311">Functional programming and mutation</span></span>

<span data-ttu-id="05ce3-312">默认情况下，F# 值是不可变的，这允许您避免某些类 bug（尤其是涉及并发和并行性的错误类）。</span><span class="sxs-lookup"><span data-stu-id="05ce3-312">F# values are immutable by default, which allows you to avoid certain classes of bugs (especially those involving concurrency and parallelism).</span></span> <span data-ttu-id="05ce3-313">但是，在某些情况下，为了实现执行时间或内存分配的最佳（甚至合理）效率，最好使用就地状态突变来实现工作跨度。</span><span class="sxs-lookup"><span data-stu-id="05ce3-313">However, in certain cases, in order to achieve optimal (or even reasonable) efficiency of execution time or memory allocations, a span of work may best be implemented by using in-place mutation of state.</span></span> <span data-ttu-id="05ce3-314">这在选择加入的基础上是可能的，F# 与`mutable`关键字。</span><span class="sxs-lookup"><span data-stu-id="05ce3-314">This is possible in an opt-in basis with F# with the `mutable` keyword.</span></span>

<span data-ttu-id="05ce3-315">`mutable`在 F# 中使用可能会感觉与功能纯度不一致。</span><span class="sxs-lookup"><span data-stu-id="05ce3-315">Use of `mutable` in F# may feel at odds with functional purity.</span></span> <span data-ttu-id="05ce3-316">这是可以理解的，但无处不在的功能纯度可能与性能目标相悖。</span><span class="sxs-lookup"><span data-stu-id="05ce3-316">This is understandable, but functional purity everywhere can be at odds with performance goals.</span></span> <span data-ttu-id="05ce3-317">一种妥协是封装突变，这样调用方就不必关心调用函数时会发生什么。</span><span class="sxs-lookup"><span data-stu-id="05ce3-317">A compromise is to encapsulate mutation such that callers need not care about what happens when they call a function.</span></span> <span data-ttu-id="05ce3-318">这允许您通过基于突变的实现为性能关键代码编写功能接口。</span><span class="sxs-lookup"><span data-stu-id="05ce3-318">This allows you to write a functional interface over a mutation-based implementation for performance-critical code.</span></span>

#### <a name="wrap-mutable-code-in-immutable-interfaces"></a><span data-ttu-id="05ce3-319">在不可变接口中包装可变代码</span><span class="sxs-lookup"><span data-stu-id="05ce3-319">Wrap mutable code in immutable interfaces</span></span>

<span data-ttu-id="05ce3-320">以参考透明度为目标，编写不公开性能关键函数可变下层代码至关重要。</span><span class="sxs-lookup"><span data-stu-id="05ce3-320">With referential transparency as a goal, it is critical to write code that does not expose the mutable underbelly of performance-critical functions.</span></span> <span data-ttu-id="05ce3-321">例如，以下代码在`Array.contains`F# 核心库中实现函数：</span><span class="sxs-lookup"><span data-stu-id="05ce3-321">For example, the following code implements the `Array.contains` function in the F# core library:</span></span>

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

<span data-ttu-id="05ce3-322">多次调用此函数不会更改基础数组，也不要求您在使用该函数时保持任何可变状态。</span><span class="sxs-lookup"><span data-stu-id="05ce3-322">Calling this function multiple times does not change the underlying array, nor does it require you to maintain any mutable state in consuming it.</span></span> <span data-ttu-id="05ce3-323">它具有参考性透明，即使其中几乎每行代码都使用突变。</span><span class="sxs-lookup"><span data-stu-id="05ce3-323">It is referentially transparent, even though almost every line of code within it uses mutation.</span></span>

#### <a name="consider-encapsulating-mutable-data-in-classes"></a><span data-ttu-id="05ce3-324">考虑在类中封装可变数据</span><span class="sxs-lookup"><span data-stu-id="05ce3-324">Consider encapsulating mutable data in classes</span></span>

<span data-ttu-id="05ce3-325">前面的示例使用单个函数来使用可变数据封装操作。</span><span class="sxs-lookup"><span data-stu-id="05ce3-325">The previous example used a single function to encapsulate operations using mutable data.</span></span> <span data-ttu-id="05ce3-326">对于更复杂的数据集，这并不总是足够。</span><span class="sxs-lookup"><span data-stu-id="05ce3-326">This is not always sufficient for more complex sets of data.</span></span> <span data-ttu-id="05ce3-327">请考虑以下函数集：</span><span class="sxs-lookup"><span data-stu-id="05ce3-327">Consider the following sets of functions:</span></span>

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

<span data-ttu-id="05ce3-328">此代码是执行的，但它公开调用方负责维护的基于突变的数据结构。</span><span class="sxs-lookup"><span data-stu-id="05ce3-328">This code is performant, but it exposes the mutation-based data structure that callers are responsible for maintaining.</span></span> <span data-ttu-id="05ce3-329">这可以包装在类中，而没有可以更改的基础成员：</span><span class="sxs-lookup"><span data-stu-id="05ce3-329">This can be wrapped inside of a class with no underlying members that can change:</span></span>

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

<span data-ttu-id="05ce3-330">`Closure1Table`封装基于突变的基础数据结构，从而不强制调用方维护基础数据结构。</span><span class="sxs-lookup"><span data-stu-id="05ce3-330">`Closure1Table` encapsulates the underlying mutation-based data structure, thereby not forcing callers to maintain the underlying data structure.</span></span> <span data-ttu-id="05ce3-331">类是封装基于突变的数据和例程而不向调用方公开详细信息的强大方法。</span><span class="sxs-lookup"><span data-stu-id="05ce3-331">Classes are a powerful way to encapsulate data and routines that are mutation-based without exposing the details to callers.</span></span>

#### <a name="prefer-let-mutable-to-reference-cells"></a><span data-ttu-id="05ce3-332">更喜欢`let mutable`引用单元格</span><span class="sxs-lookup"><span data-stu-id="05ce3-332">Prefer `let mutable` to reference cells</span></span>

<span data-ttu-id="05ce3-333">引用单元格是表示对值的引用而不是值本身的一种方式。</span><span class="sxs-lookup"><span data-stu-id="05ce3-333">Reference cells are a way to represent the reference to a value rather than the value itself.</span></span> <span data-ttu-id="05ce3-334">尽管它们可用于性能关键型代码，但不建议它们。</span><span class="sxs-lookup"><span data-stu-id="05ce3-334">Although they can be used for performance-critical code, they are not recommended.</span></span> <span data-ttu-id="05ce3-335">请考虑以下示例：</span><span class="sxs-lookup"><span data-stu-id="05ce3-335">Consider the following example:</span></span>

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

<span data-ttu-id="05ce3-336">使用引用单元格现在"污染"所有后续代码，必须取消引用和重新引用基础数据。</span><span class="sxs-lookup"><span data-stu-id="05ce3-336">The use of a reference cell now "pollutes" all subsequent code with having to dereference and re-reference the underlying data.</span></span> <span data-ttu-id="05ce3-337">相反，请考虑`let mutable`：</span><span class="sxs-lookup"><span data-stu-id="05ce3-337">Instead, consider `let mutable`:</span></span>

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

<span data-ttu-id="05ce3-338">除了 lambda 表达式中间的单点突变之外，所有其他涉及`acc`的代码都可以以与正常`let`绑定不可变值的使用没有什么不同的方式执行此操作。</span><span class="sxs-lookup"><span data-stu-id="05ce3-338">Aside from the single point of mutation in the middle of the lambda expression, all other code that touches `acc` can do so in a manner that is no different to the usage of a normal `let`-bound immutable value.</span></span> <span data-ttu-id="05ce3-339">这将使随着时间的推移更容易改变。</span><span class="sxs-lookup"><span data-stu-id="05ce3-339">This will make it easier to change over time.</span></span>

## <a name="object-programming"></a><span data-ttu-id="05ce3-340">对象编程</span><span class="sxs-lookup"><span data-stu-id="05ce3-340">Object programming</span></span>

<span data-ttu-id="05ce3-341">F# 完全支持对象和面向对象 （OO） 概念。</span><span class="sxs-lookup"><span data-stu-id="05ce3-341">F# has full support for objects and object-oriented (OO) concepts.</span></span> <span data-ttu-id="05ce3-342">尽管许多 OO 概念功能强大且有用，但并非所有概念都是理想的使用。</span><span class="sxs-lookup"><span data-stu-id="05ce3-342">Although many OO concepts are powerful and useful, not all of them are ideal to use.</span></span> <span data-ttu-id="05ce3-343">以下列表提供了有关高级别 OO 功能类别的指导。</span><span class="sxs-lookup"><span data-stu-id="05ce3-343">The following lists offer guidance on categories of OO features at a high level.</span></span>

<span data-ttu-id="05ce3-344">**考虑在许多情况下使用这些功能：**</span><span class="sxs-lookup"><span data-stu-id="05ce3-344">**Consider using these features in many situations:**</span></span>

* <span data-ttu-id="05ce3-345">点表示法`x.Length`（ ）</span><span class="sxs-lookup"><span data-stu-id="05ce3-345">Dot notation (`x.Length`)</span></span>
* <span data-ttu-id="05ce3-346">实例成员</span><span class="sxs-lookup"><span data-stu-id="05ce3-346">Instance members</span></span>
* <span data-ttu-id="05ce3-347">隐式构造函数</span><span class="sxs-lookup"><span data-stu-id="05ce3-347">Implicit constructors</span></span>
* <span data-ttu-id="05ce3-348">静态成员</span><span class="sxs-lookup"><span data-stu-id="05ce3-348">Static members</span></span>
* <span data-ttu-id="05ce3-349">索引器表示法`arr.[x]`（ ）</span><span class="sxs-lookup"><span data-stu-id="05ce3-349">Indexer notation (`arr.[x]`)</span></span>
* <span data-ttu-id="05ce3-350">命名和可选参数</span><span class="sxs-lookup"><span data-stu-id="05ce3-350">Named and Optional arguments</span></span>
* <span data-ttu-id="05ce3-351">接口和接口实现</span><span class="sxs-lookup"><span data-stu-id="05ce3-351">Interfaces and interface implementations</span></span>

<span data-ttu-id="05ce3-352">**不要首先访问这些功能，但在它们方便解决问题时，请明智地应用它们：**</span><span class="sxs-lookup"><span data-stu-id="05ce3-352">**Don't reach for these features first, but do judiciously apply them when they are convenient to solve a problem:**</span></span>

* <span data-ttu-id="05ce3-353">方法重载</span><span class="sxs-lookup"><span data-stu-id="05ce3-353">Method overloading</span></span>
* <span data-ttu-id="05ce3-354">封装的可变数据</span><span class="sxs-lookup"><span data-stu-id="05ce3-354">Encapsulated mutable data</span></span>
* <span data-ttu-id="05ce3-355">类型上的运算符</span><span class="sxs-lookup"><span data-stu-id="05ce3-355">Operators on types</span></span>
* <span data-ttu-id="05ce3-356">自动属性</span><span class="sxs-lookup"><span data-stu-id="05ce3-356">Auto properties</span></span>
* <span data-ttu-id="05ce3-357">实施`IDisposable`和`IEnumerable`</span><span class="sxs-lookup"><span data-stu-id="05ce3-357">Implementing `IDisposable` and `IEnumerable`</span></span>
* <span data-ttu-id="05ce3-358">类型扩展</span><span class="sxs-lookup"><span data-stu-id="05ce3-358">Type extensions</span></span>
* <span data-ttu-id="05ce3-359">事件</span><span class="sxs-lookup"><span data-stu-id="05ce3-359">Events</span></span>
* <span data-ttu-id="05ce3-360">结构</span><span class="sxs-lookup"><span data-stu-id="05ce3-360">Structs</span></span>
* <span data-ttu-id="05ce3-361">委派</span><span class="sxs-lookup"><span data-stu-id="05ce3-361">Delegates</span></span>
* <span data-ttu-id="05ce3-362">枚举</span><span class="sxs-lookup"><span data-stu-id="05ce3-362">Enums</span></span>

<span data-ttu-id="05ce3-363">**通常避免这些功能，除非您必须使用它们：**</span><span class="sxs-lookup"><span data-stu-id="05ce3-363">**Generally avoid these features unless you must use them:**</span></span>

* <span data-ttu-id="05ce3-364">基于继承的类型层次结构和实现继承</span><span class="sxs-lookup"><span data-stu-id="05ce3-364">Inheritance-based type hierarchies and implementation inheritance</span></span>
* <span data-ttu-id="05ce3-365">空和`Unchecked.defaultof<_>`</span><span class="sxs-lookup"><span data-stu-id="05ce3-365">Nulls and `Unchecked.defaultof<_>`</span></span>

### <a name="prefer-composition-over-inheritance"></a><span data-ttu-id="05ce3-366">首选组合而不是继承</span><span class="sxs-lookup"><span data-stu-id="05ce3-366">Prefer composition over inheritance</span></span>

<span data-ttu-id="05ce3-367">[继承的组成](https://en.wikipedia.org/wiki/Composition_over_inheritance)是一个长期存在的习惯用法，好的 F# 代码可以遵循。</span><span class="sxs-lookup"><span data-stu-id="05ce3-367">[Composition over inheritance](https://en.wikipedia.org/wiki/Composition_over_inheritance) is a long-standing idiom that good F# code can adhere to.</span></span> <span data-ttu-id="05ce3-368">基本原则是，不应公开基类，并强制调用方从该基类继承以获取功能。</span><span class="sxs-lookup"><span data-stu-id="05ce3-368">The fundamental principle is that you should not expose a base class and force callers to inherit from that base class to get functionality.</span></span>

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a><span data-ttu-id="05ce3-369">如果不需要类，请使用对象表达式实现接口</span><span class="sxs-lookup"><span data-stu-id="05ce3-369">Use object expressions to implement interfaces if you don't need a class</span></span>

<span data-ttu-id="05ce3-370">[对象表达式](../language-reference/object-expressions.md)允许您动态实现接口，将实现的接口绑定到值，而无需在类内部执行此操作。</span><span class="sxs-lookup"><span data-stu-id="05ce3-370">[Object Expressions](../language-reference/object-expressions.md) allow you to implement interfaces on the fly, binding the implemented interface to a value without needing to do so inside of a class.</span></span> <span data-ttu-id="05ce3-371">这很方便，特别是当您_只需要_实现接口，并且不需要完整类时。</span><span class="sxs-lookup"><span data-stu-id="05ce3-371">This is convenient, especially if you _only_ need to implement the interface and have no need for a full class.</span></span>

<span data-ttu-id="05ce3-372">例如，如果您添加了没有用于以下语句的`open`符号，则下面是在[Ionide](http://ionide.io/)中运行的代码，以提供代码修复操作：</span><span class="sxs-lookup"><span data-stu-id="05ce3-372">For example, here is the code that is run in [Ionide](http://ionide.io/) to provide a code fix action if you've added a symbol that you don't have an `open` statement for:</span></span>

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

<span data-ttu-id="05ce3-373">由于与 Visual Studio 代码 API 交互时不需要类，因此对象表达式是理想的工具。</span><span class="sxs-lookup"><span data-stu-id="05ce3-373">Because there is no need for a class when interacting with the Visual Studio Code API, Object Expressions are an ideal tool for this.</span></span> <span data-ttu-id="05ce3-374">当您想要以临时方式与测试例程建立接口时，它们对于单元测试也很有价值。</span><span class="sxs-lookup"><span data-stu-id="05ce3-374">They are also valuable for unit testing, when you want to stub out an interface with test routines in an ad hoc manner.</span></span>

## <a name="consider-type-abbreviations-to-shorten-signatures"></a><span data-ttu-id="05ce3-375">考虑类型缩写以缩短签名</span><span class="sxs-lookup"><span data-stu-id="05ce3-375">Consider Type Abbreviations to shorten signatures</span></span>

<span data-ttu-id="05ce3-376">[类型缩写](../language-reference/type-abbreviations.md)是将标签分配给另一种类型（如函数签名或更复杂的类型）的便捷方法。</span><span class="sxs-lookup"><span data-stu-id="05ce3-376">[Type Abbreviations](../language-reference/type-abbreviations.md) are a convenient way to assign a label to another type, such as a function signature or a more complex type.</span></span> <span data-ttu-id="05ce3-377">例如，以下别名将标签分配给使用[CNTK（](https://docs.microsoft.com/cognitive-toolkit/)深度学习库）定义计算所需的内容：</span><span class="sxs-lookup"><span data-stu-id="05ce3-377">For example, the following alias assigns a label to what's needed to define a computation with [CNTK](https://docs.microsoft.com/cognitive-toolkit/), a deep learning library:</span></span>

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

<span data-ttu-id="05ce3-378">该`Computation`名称是表示与它所混叠的签名匹配的任何函数的便捷方式。</span><span class="sxs-lookup"><span data-stu-id="05ce3-378">The `Computation` name is a convenient way to denote any function that matches the signature it is aliasing.</span></span> <span data-ttu-id="05ce3-379">使用像这样的类型缩写很方便，并允许更简洁的代码。</span><span class="sxs-lookup"><span data-stu-id="05ce3-379">Using Type Abbreviations like this is convenient and allows for more succinct code.</span></span>

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a><span data-ttu-id="05ce3-380">避免使用类型缩写来表示您的域</span><span class="sxs-lookup"><span data-stu-id="05ce3-380">Avoid using Type Abbreviations to represent your domain</span></span>

<span data-ttu-id="05ce3-381">尽管类型缩写对于为函数签名指定名称很方便，但当缩写其他类型时，它们可能会令人困惑。</span><span class="sxs-lookup"><span data-stu-id="05ce3-381">Although Type Abbreviations are convenient for giving a name to function signatures, they can be confusing when abbreviating other types.</span></span> <span data-ttu-id="05ce3-382">请考虑此缩写：</span><span class="sxs-lookup"><span data-stu-id="05ce3-382">Consider this abbreviation:</span></span>

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

<span data-ttu-id="05ce3-383">这可以通过多种方式令人困惑：</span><span class="sxs-lookup"><span data-stu-id="05ce3-383">This can be confusing in multiple ways:</span></span>

* <span data-ttu-id="05ce3-384">`BufferSize`不是抽象的;不是抽象的。它只是整数的另一个名称。</span><span class="sxs-lookup"><span data-stu-id="05ce3-384">`BufferSize` is not an abstraction; it is just another name for an integer.</span></span>
* <span data-ttu-id="05ce3-385">如果在`BufferSize`公共 API 中公开，很容易被误解为不仅仅是`int`。</span><span class="sxs-lookup"><span data-stu-id="05ce3-385">If `BufferSize` is exposed in a public API, it can easily be misinterpreted to mean more than just `int`.</span></span> <span data-ttu-id="05ce3-386">通常，域类型具有多个属性，并且不是基元类型，如`int`。</span><span class="sxs-lookup"><span data-stu-id="05ce3-386">Generally, domain types have multiple attributes to them and are not primitive types like `int`.</span></span> <span data-ttu-id="05ce3-387">此缩写违反了这一假设。</span><span class="sxs-lookup"><span data-stu-id="05ce3-387">This abbreviation violates that assumption.</span></span>
* <span data-ttu-id="05ce3-388">（PascalCase） 的`BufferSize`套管意味着此类型包含更多数据。</span><span class="sxs-lookup"><span data-stu-id="05ce3-388">The casing of `BufferSize` (PascalCase) implies that this type holds more data.</span></span>
* <span data-ttu-id="05ce3-389">与向函数提供命名参数相比，此别名的清晰度不会提高。</span><span class="sxs-lookup"><span data-stu-id="05ce3-389">This alias does not offer increased clarity compared with providing a named argument to a function.</span></span>
* <span data-ttu-id="05ce3-390">缩写不会在编译的 IL 中体现;因此，缩写不会以 IL 表示。它只是一个整数，这个别名是一个编译时构造。</span><span class="sxs-lookup"><span data-stu-id="05ce3-390">The abbreviation will not manifest in compiled IL; it is just an integer and this alias is a compile-time construct.</span></span>

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) = ...
```

<span data-ttu-id="05ce3-391">总之，类型缩写的陷阱是，**它们不是**对缩写类型的抽象。</span><span class="sxs-lookup"><span data-stu-id="05ce3-391">In summary, the pitfall with Type Abbreviations is that they are **not** abstractions over the types they are abbreviating.</span></span> <span data-ttu-id="05ce3-392">在前面的示例中，`BufferSize`只是一个`int`封面，没有额外的数据，也没有从类型系统的任何好处，除了`int`已经拥有。</span><span class="sxs-lookup"><span data-stu-id="05ce3-392">In the previous example, `BufferSize` is just an `int` under the covers, with no additional data, nor any benefits from the type system besides what `int` already has.</span></span>

<span data-ttu-id="05ce3-393">使用类型缩写来表示域的另一种方法是使用单一案例区分结合。</span><span class="sxs-lookup"><span data-stu-id="05ce3-393">An alternative approach to using type abbreviations to represent a domain is to use single-case discriminated unions.</span></span> <span data-ttu-id="05ce3-394">前面的示例可以建模如下：</span><span class="sxs-lookup"><span data-stu-id="05ce3-394">The previous sample can be modeled as follows:</span></span>

```fsharp
type BufferSize = BufferSize of int
```

<span data-ttu-id="05ce3-395">如果编写的代码按`BufferSize`及其基础值运行，则需要构造一个代码，而不是传递任何任意整数：</span><span class="sxs-lookup"><span data-stu-id="05ce3-395">If you write code that operates in terms of `BufferSize` and its underlying value, you need to construct one rather than pass in any arbitrary integer:</span></span>

```fsharp
module Networking =
    ...
    let send data (BufferSize size) =
    ...
```

<span data-ttu-id="05ce3-396">这降低了错误地将任意整数传递到`send`函数的可能性，因为调用方必须在调用函数之前构造一个`BufferSize`类型来包装值。</span><span class="sxs-lookup"><span data-stu-id="05ce3-396">This reduces the likelihood of mistakenly passing an arbitrary integer into the `send` function, because the caller must construct a `BufferSize` type to wrap a value before calling the function.</span></span>
