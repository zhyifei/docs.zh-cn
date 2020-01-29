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
# <a name="f-coding-conventions"></a><span data-ttu-id="79fd6-103">F# 코딩 규칙</span><span class="sxs-lookup"><span data-stu-id="79fd6-103">F# coding conventions</span></span>

<span data-ttu-id="79fd6-104">以下约定是从使用大型F#基本代码的经验中制定的。</span><span class="sxs-lookup"><span data-stu-id="79fd6-104">The following conventions are formulated from experience working with large F# codebases.</span></span> <span data-ttu-id="79fd6-105">[好F#代码的五大原则](index.md#five-principles-of-good-f-code)是每个建议的基础。</span><span class="sxs-lookup"><span data-stu-id="79fd6-105">The [Five principles of good F# code](index.md#five-principles-of-good-f-code) are the foundation of each recommendation.</span></span> <span data-ttu-id="79fd6-106">它们与[ F#组件设计准则](component-design-guidelines.md)相关，但适用于任何F#代码，不仅仅是库等组件。</span><span class="sxs-lookup"><span data-stu-id="79fd6-106">They are related to the [F# component design guidelines](component-design-guidelines.md), but are applicable for any F# code, not just components such as libraries.</span></span>

## <a name="organizing-code"></a><span data-ttu-id="79fd6-107">组织代码</span><span class="sxs-lookup"><span data-stu-id="79fd6-107">Organizing code</span></span>

<span data-ttu-id="79fd6-108">F#提供两种主要方法来组织代码：模块和命名空间。</span><span class="sxs-lookup"><span data-stu-id="79fd6-108">F# features two primary ways to organize code: modules and namespaces.</span></span> <span data-ttu-id="79fd6-109">这与此类似，但有以下差异：</span><span class="sxs-lookup"><span data-stu-id="79fd6-109">These are similar, but do have the following differences:</span></span>

* <span data-ttu-id="79fd6-110">命名空间编译为 .NET 命名空间。</span><span class="sxs-lookup"><span data-stu-id="79fd6-110">Namespaces are compiled as .NET namespaces.</span></span> <span data-ttu-id="79fd6-111">模块编译为静态类。</span><span class="sxs-lookup"><span data-stu-id="79fd6-111">Modules are compiled as static classes.</span></span>
* <span data-ttu-id="79fd6-112">命名空间始终为顶级。</span><span class="sxs-lookup"><span data-stu-id="79fd6-112">Namespaces are always top level.</span></span> <span data-ttu-id="79fd6-113">模块可以是顶级的，也可以嵌套在其他模块中。</span><span class="sxs-lookup"><span data-stu-id="79fd6-113">Modules can be top-level and nested within other modules.</span></span>
* <span data-ttu-id="79fd6-114">命名空间可以跨多个文件。</span><span class="sxs-lookup"><span data-stu-id="79fd6-114">Namespaces can span multiple files.</span></span> <span data-ttu-id="79fd6-115">模块不能。</span><span class="sxs-lookup"><span data-stu-id="79fd6-115">Modules cannot.</span></span>
* <span data-ttu-id="79fd6-116">可以通过 `[<RequireQualifiedAccess>]` 和 `[<AutoOpen>]`修饰模块。</span><span class="sxs-lookup"><span data-stu-id="79fd6-116">Modules can be decorated with `[<RequireQualifiedAccess>]` and `[<AutoOpen>]`.</span></span>

<span data-ttu-id="79fd6-117">以下准则将帮助你使用它们来组织你的代码。</span><span class="sxs-lookup"><span data-stu-id="79fd6-117">The following guidelines will help you use these to organize your code.</span></span>

### <a name="prefer-namespaces-at-the-top-level"></a><span data-ttu-id="79fd6-118">首选顶级命名空间</span><span class="sxs-lookup"><span data-stu-id="79fd6-118">Prefer namespaces at the top level</span></span>

<span data-ttu-id="79fd6-119">对于任何公开的可执行代码，命名空间优先于顶层的模块。</span><span class="sxs-lookup"><span data-stu-id="79fd6-119">For any publicly consumable code, namespaces are preferential to modules at the top level.</span></span> <span data-ttu-id="79fd6-120">由于这些命名空间被编译为 .NET 命名空间，因此C#它们可从中利用，无问题。</span><span class="sxs-lookup"><span data-stu-id="79fd6-120">Because they are compiled as .NET namespaces, they are consumable from C# with no issue.</span></span>

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

<span data-ttu-id="79fd6-121">仅从F#调用时，使用顶级模块可能不会出现差异，但是对于C#使用者来说，必须使用 `MyCode` 模块限定 `MyClass`。</span><span class="sxs-lookup"><span data-stu-id="79fd6-121">Using a top-level module may not appear different when called only from F#, but for C# consumers, callers may be surprised by having to qualify `MyClass` with the `MyCode` module.</span></span>

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a><span data-ttu-id="79fd6-122">仔细应用 `[<AutoOpen>]`</span><span class="sxs-lookup"><span data-stu-id="79fd6-122">Carefully apply `[<AutoOpen>]`</span></span>

<span data-ttu-id="79fd6-123">`[<AutoOpen>]` 构造可以污染可供调用方使用的作用域，并且从何处获得答案是 "神奇的"。</span><span class="sxs-lookup"><span data-stu-id="79fd6-123">The `[<AutoOpen>]` construct can pollute the scope of what is available to callers, and the answer to where something comes from is "magic".</span></span> <span data-ttu-id="79fd6-124">这并不是件好事。</span><span class="sxs-lookup"><span data-stu-id="79fd6-124">This is not a good thing.</span></span> <span data-ttu-id="79fd6-125">此规则的例外情况是F#核心库本身（尽管这种情况也有争议）。</span><span class="sxs-lookup"><span data-stu-id="79fd6-125">An exception to this rule is the F# Core Library itself (though this fact is also a bit controversial).</span></span>

<span data-ttu-id="79fd6-126">但是，如果你想要从该公共 API 单独组织的公共 API 具有 helper 功能，则此功能非常方便。</span><span class="sxs-lookup"><span data-stu-id="79fd6-126">However, it is a convenience if you have helper functionality for a public API that you wish to organize separately from that public API.</span></span>

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

<span data-ttu-id="79fd6-127">这使你可以从函数的公共 API 中完全分离实现详细信息，而无需在每次调用时都对其进行完全限定。</span><span class="sxs-lookup"><span data-stu-id="79fd6-127">This lets you cleanly separate implementation details from the public API of a function without having to fully qualify a helper each time you call it.</span></span>

<span data-ttu-id="79fd6-128">此外，还可以在命名空间级别公开扩展方法和表达式生成器，以 `[<AutoOpen>]`。</span><span class="sxs-lookup"><span data-stu-id="79fd6-128">Additionally, exposing extension methods and expression builders at the namespace level can be neatly expressed with `[<AutoOpen>]`.</span></span>

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a><span data-ttu-id="79fd6-129">当名称可能发生冲突时使用 `[<RequireQualifiedAccess>]`，你觉得这有助于提高可读性</span><span class="sxs-lookup"><span data-stu-id="79fd6-129">Use `[<RequireQualifiedAccess>]` whenever names could conflict or you feel it helps with readability</span></span>

<span data-ttu-id="79fd6-130">将 `[<RequireQualifiedAccess>]` 特性添加到模块指示可能未打开该模块，并且对该模块中的元素的引用需要显式限定访问权限。</span><span class="sxs-lookup"><span data-stu-id="79fd6-130">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="79fd6-131">例如，`Microsoft.FSharp.Collections.List` 模块具有此属性。</span><span class="sxs-lookup"><span data-stu-id="79fd6-131">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="79fd6-132">当模块中的函数和值有可能与其他模块中的名称冲突的名称时，这将非常有用。</span><span class="sxs-lookup"><span data-stu-id="79fd6-132">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="79fd6-133">要求限定访问权限可大大增加库的长期可维护性和可进化性。</span><span class="sxs-lookup"><span data-stu-id="79fd6-133">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a><span data-ttu-id="79fd6-134">Sort `open` 语句界定闭合</span><span class="sxs-lookup"><span data-stu-id="79fd6-134">Sort `open` statements topologically</span></span>

<span data-ttu-id="79fd6-135">在F#中，声明的顺序很重要，包括 `open` 语句。</span><span class="sxs-lookup"><span data-stu-id="79fd6-135">In F#, the order of declarations matters, including with `open` statements.</span></span> <span data-ttu-id="79fd6-136">这不同于C#，`using` 和 `using static` 的影响与文件中这些语句的排序无关。</span><span class="sxs-lookup"><span data-stu-id="79fd6-136">This is unlike C#, where the effect of `using` and `using static` is independent of the ordering of those statements in a file.</span></span>

<span data-ttu-id="79fd6-137">在F#中，在范围中打开的元素可以隐藏已存在的其他元素。</span><span class="sxs-lookup"><span data-stu-id="79fd6-137">In F#, elements opened into a scope can shadow others already present.</span></span> <span data-ttu-id="79fd6-138">这意味着重新排序 `open` 语句可能会改变代码的含义。</span><span class="sxs-lookup"><span data-stu-id="79fd6-138">This means that reordering `open` statements could alter the meaning of code.</span></span> <span data-ttu-id="79fd6-139">因此，不建议对所有 `open` 语句（例如 alphanumerically）进行任意排序，避免会生成您可能需要的不同行为。</span><span class="sxs-lookup"><span data-stu-id="79fd6-139">As a result, any arbitrary sorting of all `open` statements (for example, alphanumerically) is not recommended, lest you generate different behavior that you might expect.</span></span>

<span data-ttu-id="79fd6-140">相反，我们建议对它们进行排序[界定闭合](https://en.wikipedia.org/wiki/Topological_sorting);也就是说，按定义系统_层_的顺序对 `open` 语句排序。</span><span class="sxs-lookup"><span data-stu-id="79fd6-140">Instead, we recommend that you sort them [topologically](https://en.wikipedia.org/wiki/Topological_sorting); that is, order your `open` statements in the order in which _layers_ of your system are defined.</span></span> <span data-ttu-id="79fd6-141">还可以考虑在不同的拓扑层中执行字母数字排序。</span><span class="sxs-lookup"><span data-stu-id="79fd6-141">Doing alphanumeric sorting within different topological layers may also be considered.</span></span>

<span data-ttu-id="79fd6-142">例如，下面是针对F#编译器服务公共 API 文件的拓扑排序：</span><span class="sxs-lookup"><span data-stu-id="79fd6-142">As an example, here is the topological sorting for the F# compiler service public API file:</span></span>

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

<span data-ttu-id="79fd6-143">请注意，分行符分隔拓扑层，每个层将在 alphanumerically 之后进行排序。</span><span class="sxs-lookup"><span data-stu-id="79fd6-143">Note that a line break separates topological layers, with each layer being sorted alphanumerically afterwards.</span></span> <span data-ttu-id="79fd6-144">这将完全组织代码，而不会意外地隐藏值。</span><span class="sxs-lookup"><span data-stu-id="79fd6-144">This cleanly organizes code without accidentally shadowing values.</span></span>

## <a name="use-classes-to-contain-values-that-have-side-effects"></a><span data-ttu-id="79fd6-145">使用类来包含具有副作用的值</span><span class="sxs-lookup"><span data-stu-id="79fd6-145">Use classes to contain values that have side effects</span></span>

<span data-ttu-id="79fd6-146">在许多情况下，初始化某个值可能会有副作用，如将上下文实例化到数据库或其他远程资源。</span><span class="sxs-lookup"><span data-stu-id="79fd6-146">There are many times when initializing a value can have side effects, such as instantiating a context to a database or other remote resource.</span></span> <span data-ttu-id="79fd6-147">在模块中初始化此类东西并在后续函数中使用它非常有吸引力：</span><span class="sxs-lookup"><span data-stu-id="79fd6-147">It is tempting to initialize such things in a module and use it in subsequent functions:</span></span>

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

<span data-ttu-id="79fd6-148">出于以下几个原因，这通常是一种不好的做法：</span><span class="sxs-lookup"><span data-stu-id="79fd6-148">This is frequently a bad idea for a few reasons:</span></span>

<span data-ttu-id="79fd6-149">首先，将应用程序配置推送到带有 `dep1` 和 `dep2`的基本代码。</span><span class="sxs-lookup"><span data-stu-id="79fd6-149">First, application configuration is pushed into the codebase with `dep1` and `dep2`.</span></span> <span data-ttu-id="79fd6-150">这在更大的基本代码中很难维护。</span><span class="sxs-lookup"><span data-stu-id="79fd6-150">This is difficult to maintain in larger codebases.</span></span>

<span data-ttu-id="79fd6-151">其次，静态初始化的数据不应包含不是线程安全的值（如果组件自身将使用多个线程）。</span><span class="sxs-lookup"><span data-stu-id="79fd6-151">Second, statically initialized data should not include values that are not thread safe if your component will itself use multiple threads.</span></span> <span data-ttu-id="79fd6-152">`dep3`清楚地违反了此情况。</span><span class="sxs-lookup"><span data-stu-id="79fd6-152">This is clearly violated by `dep3`.</span></span>

<span data-ttu-id="79fd6-153">最后，模块初始化为整个编译单元编译为静态构造函数。</span><span class="sxs-lookup"><span data-stu-id="79fd6-153">Finally, module initialization compiles into a static constructor for the entire compilation unit.</span></span> <span data-ttu-id="79fd6-154">如果在该模块中的 let 绑定值初始化中出现任何错误，则会将其视为一个 `TypeInitializationException`，然后在应用程序的整个生存期内对其进行缓存。</span><span class="sxs-lookup"><span data-stu-id="79fd6-154">If any error occurs in let-bound value initialization in that module, it manifests as a `TypeInitializationException` that is then cached for the entire lifetime of the application.</span></span> <span data-ttu-id="79fd6-155">这可能很难诊断。</span><span class="sxs-lookup"><span data-stu-id="79fd6-155">This can be difficult to diagnose.</span></span> <span data-ttu-id="79fd6-156">通常情况下，你可以尝试原因，但如果没有，则不会告诉根本原因是什么。</span><span class="sxs-lookup"><span data-stu-id="79fd6-156">There is usually an inner exception that you can attempt to reason about, but if there is not, then there is no telling what the root cause is.</span></span>

<span data-ttu-id="79fd6-157">相反，只需使用简单的类来保存依赖项：</span><span class="sxs-lookup"><span data-stu-id="79fd6-157">Instead, just use a simple class to hold dependencies:</span></span>

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member _.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member _.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

<span data-ttu-id="79fd6-158">这会启用以下功能：</span><span class="sxs-lookup"><span data-stu-id="79fd6-158">This enables the following:</span></span>

1. <span data-ttu-id="79fd6-159">将任何依赖状态推送到 API 自身之外。</span><span class="sxs-lookup"><span data-stu-id="79fd6-159">Pushing any dependent state outside of the API itself.</span></span>
2. <span data-ttu-id="79fd6-160">现在可以在 API 外完成配置。</span><span class="sxs-lookup"><span data-stu-id="79fd6-160">Configuration can now be done outside of the API.</span></span>
3. <span data-ttu-id="79fd6-161">依赖值初始化中的错误不可能作为 `TypeInitializationException`清单。</span><span class="sxs-lookup"><span data-stu-id="79fd6-161">Errors in initialization for dependent values are not likely to manifest as a `TypeInitializationException`.</span></span>
4. <span data-ttu-id="79fd6-162">API 现在更易于测试。</span><span class="sxs-lookup"><span data-stu-id="79fd6-162">The API is now easier to test.</span></span>

## <a name="error-management"></a><span data-ttu-id="79fd6-163">错误管理</span><span class="sxs-lookup"><span data-stu-id="79fd6-163">Error management</span></span>

<span data-ttu-id="79fd6-164">大型系统中的错误管理是一项复杂且微妙的工作，在确保系统容错和行为良好的情况下没有任何银的项目符号。</span><span class="sxs-lookup"><span data-stu-id="79fd6-164">Error management in large systems is a complex and nuanced endeavor, and there are no silver bullets in ensuring your systems are fault-tolerant and behave well.</span></span> <span data-ttu-id="79fd6-165">以下准则应提供有关导航此困难空间的指导。</span><span class="sxs-lookup"><span data-stu-id="79fd6-165">The following guidelines should offer guidance in navigating this difficult space.</span></span>

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a><span data-ttu-id="79fd6-166">表示域内部类型的错误事例和非法状态</span><span class="sxs-lookup"><span data-stu-id="79fd6-166">Represent error cases and illegal state in types intrinsic to your domain</span></span>

<span data-ttu-id="79fd6-167">利用可[区分联合](../language-reference/discriminated-unions.md)， F#可以在类型系统中表示有问题的程序状态。</span><span class="sxs-lookup"><span data-stu-id="79fd6-167">With [Discriminated Unions](../language-reference/discriminated-unions.md), F# gives you the ability to represent faulty program state in your type system.</span></span> <span data-ttu-id="79fd6-168">예를 들면 다음과 같습니다.:</span><span class="sxs-lookup"><span data-stu-id="79fd6-168">For example:</span></span>

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

<span data-ttu-id="79fd6-169">在这种情况下，有三种已知的方法可以取出银行帐户的资金。</span><span class="sxs-lookup"><span data-stu-id="79fd6-169">In this case, there are three known ways that withdrawing money from a bank account can fail.</span></span> <span data-ttu-id="79fd6-170">每个错误事例均以类型表示，因而可在整个程序中安全地处理。</span><span class="sxs-lookup"><span data-stu-id="79fd6-170">Each error case is represented in the type, and can thus be dealt with safely throughout the program.</span></span>

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

<span data-ttu-id="79fd6-171">通常情况下，如果可以在域中对某些可能会**失败**的方法建模，则不再将错误处理代码视为除常规程序流之外必须处理的内容。</span><span class="sxs-lookup"><span data-stu-id="79fd6-171">In general, if you can model the different ways that something can **fail** in your domain, then error handling code is no longer treated as something you must deal with in addition to regular program flow.</span></span> <span data-ttu-id="79fd6-172">它只是正常程序流程的一部分，不被视为**例外**。</span><span class="sxs-lookup"><span data-stu-id="79fd6-172">It is simply a part of normal program flow, and not considered **exceptional**.</span></span> <span data-ttu-id="79fd6-173">此操作主要有两个优点：</span><span class="sxs-lookup"><span data-stu-id="79fd6-173">There are two primary benefits to this:</span></span>

1. <span data-ttu-id="79fd6-174">随着域的不断变化，更易于维护。</span><span class="sxs-lookup"><span data-stu-id="79fd6-174">It is easier to maintain as your domain changes over time.</span></span>
2. <span data-ttu-id="79fd6-175">错误事例更易于进行单元测试。</span><span class="sxs-lookup"><span data-stu-id="79fd6-175">Error cases are easier to unit test.</span></span>

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a><span data-ttu-id="79fd6-176">当错误无法用类型表示时使用异常</span><span class="sxs-lookup"><span data-stu-id="79fd6-176">Use exceptions when errors cannot be represented with types</span></span>

<span data-ttu-id="79fd6-177">不是所有的错误都可以在问题域中表示。</span><span class="sxs-lookup"><span data-stu-id="79fd6-177">Not all errors can be represented in a problem domain.</span></span> <span data-ttu-id="79fd6-178">这些类型的错误在本质上是不*例外*的，因此能够在中F#引发和捕获异常。</span><span class="sxs-lookup"><span data-stu-id="79fd6-178">These kinds of faults are *exceptional* in nature, hence the ability to raise and catch exceptions in F#.</span></span>

<span data-ttu-id="79fd6-179">首先，建议您阅读[异常设计准则](../../standard/design-guidelines/exceptions.md)。</span><span class="sxs-lookup"><span data-stu-id="79fd6-179">First, it is recommended that you read the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md).</span></span> <span data-ttu-id="79fd6-180">它们还适用于F#。</span><span class="sxs-lookup"><span data-stu-id="79fd6-180">These are also applicable to F#.</span></span>

<span data-ttu-id="79fd6-181">中F#可用于引发异常的主构造应按以下优先顺序考虑：</span><span class="sxs-lookup"><span data-stu-id="79fd6-181">The main constructs available in F# for the purposes of raising exceptions should be considered in the following order of preference:</span></span>

| <span data-ttu-id="79fd6-182">기능</span><span class="sxs-lookup"><span data-stu-id="79fd6-182">Function</span></span> | <span data-ttu-id="79fd6-183">구문</span><span class="sxs-lookup"><span data-stu-id="79fd6-183">Syntax</span></span> | <span data-ttu-id="79fd6-184">용도</span><span class="sxs-lookup"><span data-stu-id="79fd6-184">Purpose</span></span> |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | <span data-ttu-id="79fd6-185">使用指定的参数名引发 `System.ArgumentNullException`。</span><span class="sxs-lookup"><span data-stu-id="79fd6-185">Raises a `System.ArgumentNullException` with the specified argument name.</span></span> |
| `invalidArg` | `invalidArg "argumentName" "message"` | <span data-ttu-id="79fd6-186">使用指定的参数名称和消息引发 `System.ArgumentException`。</span><span class="sxs-lookup"><span data-stu-id="79fd6-186">Raises a `System.ArgumentException` with a specified argument name and message.</span></span> |
| `invalidOp` | `invalidOp "message"` | <span data-ttu-id="79fd6-187">使用指定的消息引发 `System.InvalidOperationException`。</span><span class="sxs-lookup"><span data-stu-id="79fd6-187">Raises a `System.InvalidOperationException` with the specified message.</span></span> |
|`raise`| `raise (ExceptionType("message"))` | <span data-ttu-id="79fd6-188">用于引发异常的通用机制。</span><span class="sxs-lookup"><span data-stu-id="79fd6-188">General-purpose mechanism for throwing exceptions.</span></span> |
| `failwith` | `failwith "message"` | <span data-ttu-id="79fd6-189">使用指定的消息引发 `System.Exception`。</span><span class="sxs-lookup"><span data-stu-id="79fd6-189">Raises a `System.Exception` with the specified message.</span></span> |
| `failwithf` | `failwithf "format string" argForFormatString` | <span data-ttu-id="79fd6-190">使用由格式字符串及其输入确定的消息引发 `System.Exception`。</span><span class="sxs-lookup"><span data-stu-id="79fd6-190">Raises a `System.Exception` with a message determined by the format string and its inputs.</span></span> |

<span data-ttu-id="79fd6-191">使用 `nullArg`、`invalidArg` 和 `invalidOp` 作为在适当的情况下引发 `ArgumentNullException`、`ArgumentException` 和 `InvalidOperationException` 的机制。</span><span class="sxs-lookup"><span data-stu-id="79fd6-191">Use `nullArg`, `invalidArg` and `invalidOp` as the mechanism to throw `ArgumentNullException`, `ArgumentException` and `InvalidOperationException` when appropriate.</span></span>

<span data-ttu-id="79fd6-192">通常应避免使用 `failwith` 和 `failwithf` 函数，因为它们会引发基 `Exception` 类型，而不是特定异常。</span><span class="sxs-lookup"><span data-stu-id="79fd6-192">The `failwith` and `failwithf` functions should generally be avoided because they raise the base `Exception` type, not a specific exception.</span></span> <span data-ttu-id="79fd6-193">根据[异常设计准则](../../standard/design-guidelines/exceptions.md)，你希望在可以时引发更具体的异常。</span><span class="sxs-lookup"><span data-stu-id="79fd6-193">As per the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md), you want to raise more specific exceptions when you can.</span></span>

### <a name="using-exception-handling-syntax"></a><span data-ttu-id="79fd6-194">使用异常处理语法</span><span class="sxs-lookup"><span data-stu-id="79fd6-194">Using exception-handling syntax</span></span>

<span data-ttu-id="79fd6-195">F#通过 `try...with` 语法支持异常模式：</span><span class="sxs-lookup"><span data-stu-id="79fd6-195">F# supports exception patterns via the `try...with` syntax:</span></span>

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

<span data-ttu-id="79fd6-196">如果要使代码更清晰，则在面对具有模式匹配的异常时协调要执行的功能可能有点棘手。</span><span class="sxs-lookup"><span data-stu-id="79fd6-196">Reconciling functionality to perform in the face of an exception with pattern matching can be a bit tricky if you wish to keep the code clean.</span></span> <span data-ttu-id="79fd6-197">处理此问题的一种方法是使用[活动模式](../language-reference/active-patterns.md)作为一种将错误情况的功能分组，并引发异常本身。</span><span class="sxs-lookup"><span data-stu-id="79fd6-197">One such way to handle this is to use [active patterns](../language-reference/active-patterns.md) as a means to group functionality surrounding an error case with an exception itself.</span></span> <span data-ttu-id="79fd6-198">例如，你可能正在使用一个 API，该 API 在引发异常时，将有价值的信息包含在异常元数据中。</span><span class="sxs-lookup"><span data-stu-id="79fd6-198">For example, you may be consuming an API that, when it throws an exception, encloses valuable information in the exception metadata.</span></span> <span data-ttu-id="79fd6-199">将有用的值解包到活动模式内捕获的异常的正文中，并在某些情况下返回该值会很有用。</span><span class="sxs-lookup"><span data-stu-id="79fd6-199">Unwrapping a useful value in the body of the captured exception inside the Active Pattern and returning that value can be helpful in some situations.</span></span>

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a><span data-ttu-id="79fd6-200">不要使用一元错误处理来替换异常</span><span class="sxs-lookup"><span data-stu-id="79fd6-200">Do not use monadic error handling to replace exceptions</span></span>

<span data-ttu-id="79fd6-201">在函数编程中，异常会被视为有点 taboo。</span><span class="sxs-lookup"><span data-stu-id="79fd6-201">Exceptions are seen as somewhat taboo in functional programming.</span></span> <span data-ttu-id="79fd6-202">事实上，例外违反了纯度，因此可以放心地将其视为不太有效。</span><span class="sxs-lookup"><span data-stu-id="79fd6-202">Indeed, exceptions violate purity, so it's safe to consider them not-quite functional.</span></span> <span data-ttu-id="79fd6-203">但是，这会忽略必须运行代码的事实，并且可能会发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="79fd6-203">However, this ignores the reality of where code must run, and that runtime errors can occur.</span></span> <span data-ttu-id="79fd6-204">一般情况下，编写代码假设大多数功能都既不是纯也不是总计，以最大程度减少意外的意外情况。</span><span class="sxs-lookup"><span data-stu-id="79fd6-204">In general, write code on the assumption that most things are neither pure nor total, to minimize unpleasant surprises.</span></span>

<span data-ttu-id="79fd6-205">在 .NET 运行时和跨语言生态系统中，请务必考虑以下有关异常的核心优势/方面：</span><span class="sxs-lookup"><span data-stu-id="79fd6-205">It is important to consider the following core strengths/aspects of Exceptions with respect to their relevance and appropriateness in the .NET runtime and cross-language ecosystem as a whole:</span></span>

1. <span data-ttu-id="79fd6-206">它们包含详细的诊断信息，这在调试问题时非常有用。</span><span class="sxs-lookup"><span data-stu-id="79fd6-206">They contain detailed diagnostic information, which is very helpful when debugging an issue.</span></span>
2. <span data-ttu-id="79fd6-207">它们非常易于由运行时和其他 .NET 语言使用。</span><span class="sxs-lookup"><span data-stu-id="79fd6-207">They are well-understood by the runtime and other .NET languages.</span></span>
3. <span data-ttu-id="79fd6-208">与代码相比，在临时实现其语义的某些子集时，它们可以减少重大的样本，以*避免*异常。</span><span class="sxs-lookup"><span data-stu-id="79fd6-208">They can reduce significant boilerplate when compared with code that goes out of its way to *avoid* exceptions by implementing some subset of their semantics on an ad-hoc basis.</span></span>

<span data-ttu-id="79fd6-209">这第三个要点非常重要。</span><span class="sxs-lookup"><span data-stu-id="79fd6-209">This third point is critical.</span></span> <span data-ttu-id="79fd6-210">对于重要复杂的操作，无法使用异常可能导致处理如下结构：</span><span class="sxs-lookup"><span data-stu-id="79fd6-210">For nontrivial complex operations, failing to use exceptions can result in dealing with structures like this:</span></span>

```fsharp
Result<Result<MyType, string>, string list>
```

<span data-ttu-id="79fd6-211">这可以轻松地在 "stringly 类型" 错误上导致类似模式的代码，如模式匹配：</span><span class="sxs-lookup"><span data-stu-id="79fd6-211">Which can easily lead to fragile code like pattern matching on "stringly-typed" errors:</span></span>

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

<span data-ttu-id="79fd6-212">此外，在吞并返回 "更好" 类型的 "简单" 函数所需的任何异常时，可能会很有吸引力。</span><span class="sxs-lookup"><span data-stu-id="79fd6-212">Additionally, it can be tempting to swallow any exception in the desire for a "simple" function that returns a "nicer" type:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

<span data-ttu-id="79fd6-213">遗憾的是，`tryReadAllText` 可能会根据在文件系统上可能发生的许多事情引发许多异常，而此代码放弃了有关环境中实际出现错误的任何信息。</span><span class="sxs-lookup"><span data-stu-id="79fd6-213">Unfortunately, `tryReadAllText` can throw numerous exceptions based on the myriad of things that can happen on a file system, and this code discards away any information about what might actually be going wrong in your environment.</span></span> <span data-ttu-id="79fd6-214">如果将此代码替换为结果类型，则返回 "stringly 类型" 错误消息分析：</span><span class="sxs-lookup"><span data-stu-id="79fd6-214">If you replace this code with a result type, then you're back to "stringly-typed" error message parsing:</span></span>

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

<span data-ttu-id="79fd6-215">然后，将异常对象本身放置在 `Error` 构造函数中，只会强制在调用站点（而非函数）正确处理异常类型。</span><span class="sxs-lookup"><span data-stu-id="79fd6-215">And placing the exception object itself in the `Error` constructor just forces you to properly deal with the exception type at the call site rather than in the function.</span></span> <span data-ttu-id="79fd6-216">这样做会有效地创建检查的异常，这是一项非常 unfun 的操作，可以作为 API 的调用方处理。</span><span class="sxs-lookup"><span data-stu-id="79fd6-216">Doing this effectively creates checked exceptions, which are notoriously unfun to deal with as a caller of an API.</span></span>

<span data-ttu-id="79fd6-217">在上述示例中，一种很好的替代方法是捕获*特定*的异常，并在该异常的上下文中返回有意义的值。</span><span class="sxs-lookup"><span data-stu-id="79fd6-217">A good alternative to the above examples is to catch *specific* exceptions and return a meaningful value in the context of that exception.</span></span> <span data-ttu-id="79fd6-218">如果按如下所述修改 `tryReadAllText` 函数，`None` 具有更多含义：</span><span class="sxs-lookup"><span data-stu-id="79fd6-218">If you modify the `tryReadAllText` function as follows, `None` has more meaning:</span></span>

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

<span data-ttu-id="79fd6-219">此函数现在会正确地处理找不到文件的情况，并将这种含义赋给返回，而不是作为全部捕获。</span><span class="sxs-lookup"><span data-stu-id="79fd6-219">Instead of functioning as a catch-all, this function will now properly handle the case when a file was not found and assign that meaning to a return.</span></span> <span data-ttu-id="79fd6-220">此返回值可以映射到该错误情况，同时不会丢弃任何上下文信息或强制调用方处理可能在代码中不相关的情况。</span><span class="sxs-lookup"><span data-stu-id="79fd6-220">This return value can map to that error case, while not discarding any contextual information or forcing callers to deal with a case that may not be relevant at that point in the code.</span></span>

<span data-ttu-id="79fd6-221">诸如 `Result<'Success, 'Error>` 之类的类型适用于不在其中嵌套的基本操作， F#可选类型适用于在某些情况下可能返回*内容*或不返回*任何*内容。</span><span class="sxs-lookup"><span data-stu-id="79fd6-221">Types such as `Result<'Success, 'Error>` are appropriate for basic operations where they aren't nested, and F# optional types are perfect for representing when something could either return *something* or *nothing*.</span></span> <span data-ttu-id="79fd6-222">尽管它们不是异常的替代项，但不应在尝试替换异常时使用。</span><span class="sxs-lookup"><span data-stu-id="79fd6-222">They are not a replacement for exceptions, though, and should not be used in an attempt to replace exceptions.</span></span> <span data-ttu-id="79fd6-223">相反，它们应该谨慎地按目标方式处理异常和错误管理策略的特定方面。</span><span class="sxs-lookup"><span data-stu-id="79fd6-223">Rather, they should be applied judiciously to address specific aspects of exception and error management policy in targeted ways.</span></span>

## <a name="partial-application-and-point-free-programming"></a><span data-ttu-id="79fd6-224">部分应用和无点编程</span><span class="sxs-lookup"><span data-stu-id="79fd6-224">Partial application and point-free programming</span></span>

<span data-ttu-id="79fd6-225">F#支持部分应用程序，并因此使用各种方法来编程无点样式。</span><span class="sxs-lookup"><span data-stu-id="79fd6-225">F# supports partial application, and thus, various ways to program in a point-free style.</span></span> <span data-ttu-id="79fd6-226">这对于模块内的代码重用或某些内容的实现非常有用，但它并不是公开公开的内容。</span><span class="sxs-lookup"><span data-stu-id="79fd6-226">This can be beneficial for code reuse within a module or the implementation of something, but it is not something to expose publicly.</span></span> <span data-ttu-id="79fd6-227">通常情况下，无点编程不是本身，也不能为不沉浸样式的人员添加重要认知障碍。</span><span class="sxs-lookup"><span data-stu-id="79fd6-227">In general, point-free programming is not a virtue in and of itself, and can add a significant cognitive barrier for people who are not immersed in the style.</span></span>

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a><span data-ttu-id="79fd6-228">不要在公共 Api 中使用部分应用程序和 currying</span><span class="sxs-lookup"><span data-stu-id="79fd6-228">Do not use partial application and currying in public APIs</span></span>

<span data-ttu-id="79fd6-229">几乎不例外，在公共 Api 中使用部分应用程序可能会给使用者造成混淆。</span><span class="sxs-lookup"><span data-stu-id="79fd6-229">With little exception, the use of partial application in public APIs can be confusing for consumers.</span></span> <span data-ttu-id="79fd6-230">通常，代码中F# `let`绑定值是**值**而不是**函数值**。</span><span class="sxs-lookup"><span data-stu-id="79fd6-230">Usually, `let`-bound values in F# code are **values**, not **function values**.</span></span> <span data-ttu-id="79fd6-231">混合值和函数值可能会导致在 exchange 中保存少量的代码行，以实现很多认知开销，尤其是在与运算符（如 `>>` 结合使用以编写函数时）。</span><span class="sxs-lookup"><span data-stu-id="79fd6-231">Mixing together values and function values can result in saving a small number of lines of code in exchange for quite a bit of cognitive overhead, especially if combined with operators such as `>>` to compose functions.</span></span>

### <a name="consider-the-tooling-implications-for-point-free-programming"></a><span data-ttu-id="79fd6-232">考虑无点编程的工具含义</span><span class="sxs-lookup"><span data-stu-id="79fd6-232">Consider the tooling implications for point-free programming</span></span>

<span data-ttu-id="79fd6-233">扩充函数不会标记其参数。</span><span class="sxs-lookup"><span data-stu-id="79fd6-233">Curried functions do not label their arguments.</span></span> <span data-ttu-id="79fd6-234">这会影响工具。</span><span class="sxs-lookup"><span data-stu-id="79fd6-234">This has tooling implications.</span></span> <span data-ttu-id="79fd6-235">请考虑以下两个函数：</span><span class="sxs-lookup"><span data-stu-id="79fd6-235">Consider the following two functions:</span></span>

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

<span data-ttu-id="79fd6-236">两者都是有效的函数，但 `funcWithApplication` 是一个扩充函数。</span><span class="sxs-lookup"><span data-stu-id="79fd6-236">Both are valid functions, but `funcWithApplication` is a curried function.</span></span> <span data-ttu-id="79fd6-237">当你将鼠标悬停在编辑器中的类型上时，将看到以下内容：</span><span class="sxs-lookup"><span data-stu-id="79fd6-237">When you hover over their types in an editor, you see this:</span></span>

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

<span data-ttu-id="79fd6-238">在调用站点，工具（如 Visual Studio）中的工具提示将不会向你显示 `string` 和 `int` 输入类型实际表示的内容的有用信息。</span><span class="sxs-lookup"><span data-stu-id="79fd6-238">At the call site, tooltips in tooling such as Visual Studio will not give you meaningful information as to what the `string` and `int` input types actually represent.</span></span>

<span data-ttu-id="79fd6-239">如果遇到可公开使用的无点代码（如 `funcWithApplication`），则建议执行完全η的扩展，以便工具可以获取有意义的参数名称。</span><span class="sxs-lookup"><span data-stu-id="79fd6-239">If you encounter point-free code like `funcWithApplication` that is publicly consumable, it is recommended to do a full η-expansion so that tooling can pick up on meaningful names for arguments.</span></span>

<span data-ttu-id="79fd6-240">而且，如果不可能，调试无点代码可能会很难。</span><span class="sxs-lookup"><span data-stu-id="79fd6-240">Furthermore, debugging point-free code can be challenging, if not impossible.</span></span> <span data-ttu-id="79fd6-241">调试工具依赖于绑定到名称（例如 `let` 绑定）的值，以便您可以在执行中间检查中间值。</span><span class="sxs-lookup"><span data-stu-id="79fd6-241">Debugging tools rely on values bound to names (for example, `let` bindings) so that you can inspect intermediate values midway through execution.</span></span> <span data-ttu-id="79fd6-242">如果你的代码没有要检查的值，则没有要调试的内容。</span><span class="sxs-lookup"><span data-stu-id="79fd6-242">When your code has no values to inspect, there is nothing to debug.</span></span> <span data-ttu-id="79fd6-243">将来，调试工具可以根据以前执行的路径来合成这些值，但不是最好地将您的匹配情况篱到*可能*的调试功能。</span><span class="sxs-lookup"><span data-stu-id="79fd6-243">In the future, debugging tools may evolve to synthesize these values based on previously executed paths, but it's not a good idea to hedge your bets on *potential* debugging functionality.</span></span>

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a><span data-ttu-id="79fd6-244">考虑使用部分应用程序作为一项技术来减少内部样本</span><span class="sxs-lookup"><span data-stu-id="79fd6-244">Consider partial application as a technique to reduce internal boilerplate</span></span>

<span data-ttu-id="79fd6-245">与前一个要点相比，部分应用程序是一种非常棒的工具，可用于减少应用程序内的样本或 API 的更深层次使用。</span><span class="sxs-lookup"><span data-stu-id="79fd6-245">In contrast to the previous point, partial application is a wonderful tool for reducing boilerplate inside of an application or the deeper internals of an API.</span></span> <span data-ttu-id="79fd6-246">它对于实现更复杂的 Api 的单元测试非常有用，在这种情况下，样板通常是处理问题的难点。</span><span class="sxs-lookup"><span data-stu-id="79fd6-246">It can be helpful for unit testing the implementation of more complicated APIs, where boilerplate is often a pain to deal with.</span></span> <span data-ttu-id="79fd6-247">例如，下面的代码演示了如何实现最模拟的框架，而无需对此类框架进行外部依赖并了解相关的订购 API。</span><span class="sxs-lookup"><span data-stu-id="79fd6-247">For example, the following code shows how you can accomplish what most mocking frameworks give you without taking an external dependency on such a framework and having to learn a related bespoke API.</span></span>

<span data-ttu-id="79fd6-248">例如，请考虑以下解决方案拓扑：</span><span class="sxs-lookup"><span data-stu-id="79fd6-248">For example, consider the following solution topography:</span></span>

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

<span data-ttu-id="79fd6-249">`ImplementationLogic.fsproj` 可能会公开如下代码：</span><span class="sxs-lookup"><span data-stu-id="79fd6-249">`ImplementationLogic.fsproj` might expose code such as:</span></span>

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member _.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

<span data-ttu-id="79fd6-250">`ImplementationLogic.Tests.fsproj` 中的单元测试 `Transactions.doTransaction` 很简单：</span><span class="sxs-lookup"><span data-stu-id="79fd6-250">Unit testing `Transactions.doTransaction` in `ImplementationLogic.Tests.fsproj` is easy:</span></span>

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

<span data-ttu-id="79fd6-251">使用模拟上下文对象部分应用 `doTransaction`，可以在所有单元测试中调用函数，而无需每次都构造模拟上下文：</span><span class="sxs-lookup"><span data-stu-id="79fd6-251">Partially applying `doTransaction` with a mocking context object lets you call the function in all of your unit tests without needing to construct a mocked context each time:</span></span>

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

<span data-ttu-id="79fd6-252">不应将此方法广泛应用于整个基本代码，但这是减少复杂内部和这些内部测试单元的样本的好办法。</span><span class="sxs-lookup"><span data-stu-id="79fd6-252">This technique should not be universally applied to your entire codebase, but it is a good way to reduce boilerplate for complicated internals and unit testing those internals.</span></span>

## <a name="access-control"></a><span data-ttu-id="79fd6-253">액세스 제어</span><span class="sxs-lookup"><span data-stu-id="79fd6-253">Access control</span></span>

<span data-ttu-id="79fd6-254">F#具有多个用于[访问控制](../language-reference/access-control.md)的选项，这些选项是从 .net 运行时中的可用项继承而来的。</span><span class="sxs-lookup"><span data-stu-id="79fd6-254">F# has multiple options for [Access control](../language-reference/access-control.md), inherited from what is available in the .NET runtime.</span></span> <span data-ttu-id="79fd6-255">这些类型不仅可用于类型，还可以将它们用于函数。</span><span class="sxs-lookup"><span data-stu-id="79fd6-255">These are not just usable for types - you can use them for functions, too.</span></span>

* <span data-ttu-id="79fd6-256">首选非`public` 类型和成员，直到你需要它们可公开使用。</span><span class="sxs-lookup"><span data-stu-id="79fd6-256">Prefer non-`public` types and members until you need them to be publicly consumable.</span></span> <span data-ttu-id="79fd6-257">这还可以最大程度地减少使用者。</span><span class="sxs-lookup"><span data-stu-id="79fd6-257">This also minimizes what consumers couple to.</span></span>
* <span data-ttu-id="79fd6-258">努力保持所有帮助程序功能 `private`。</span><span class="sxs-lookup"><span data-stu-id="79fd6-258">Strive to keep all helper functionality `private`.</span></span>
* <span data-ttu-id="79fd6-259">如果在 helper 函数的私有模块上使用 `[<AutoOpen>]`，请考虑使用这些功能。</span><span class="sxs-lookup"><span data-stu-id="79fd6-259">Consider the use of `[<AutoOpen>]` on a private module of helper functions if they become numerous.</span></span>

## <a name="type-inference-and-generics"></a><span data-ttu-id="79fd6-260">类型推理和泛型</span><span class="sxs-lookup"><span data-stu-id="79fd6-260">Type inference and generics</span></span>

<span data-ttu-id="79fd6-261">类型推理可以省去您键入大量样板。</span><span class="sxs-lookup"><span data-stu-id="79fd6-261">Type inference can save you from typing a lot of boilerplate.</span></span> <span data-ttu-id="79fd6-262">编译器中的F#自动泛化可帮助你编写更通用的代码，几乎不需要额外的工作。</span><span class="sxs-lookup"><span data-stu-id="79fd6-262">And automatic generalization in the F# compiler can help you write more generic code with almost no extra effort on your part.</span></span> <span data-ttu-id="79fd6-263">不过，这些功能并不是普遍适用的。</span><span class="sxs-lookup"><span data-stu-id="79fd6-263">However, these features are not universally good.</span></span>

* <span data-ttu-id="79fd6-264">考虑在公共 Api 中用显式类型标记参数名称，并且不要依赖于此的类型推理。</span><span class="sxs-lookup"><span data-stu-id="79fd6-264">Consider labeling argument names with explicit types in public APIs and do not rely on type inference for this.</span></span>

    <span data-ttu-id="79fd6-265">原因在于，**您**应该控制 API 的形状，而不是编译器的形式。</span><span class="sxs-lookup"><span data-stu-id="79fd6-265">The reason for this is that **you** should be in control of the shape of your API, not the compiler.</span></span> <span data-ttu-id="79fd6-266">尽管编译器可以在推断类型时执行精细作业，但是，如果它依赖的内部机制已更改类型，则可能会更改 API 的形状。</span><span class="sxs-lookup"><span data-stu-id="79fd6-266">Although the compiler can do a fine job at inferring types for you, it is possible to have the shape of your API change if the internals it relies on have changed types.</span></span> <span data-ttu-id="79fd6-267">这可能是你想要的，但几乎肯定会导致下游使用者需要处理的重大 API 更改。</span><span class="sxs-lookup"><span data-stu-id="79fd6-267">This may be what you want, but it will almost certainly result in a breaking API change that downstream consumers will then have to deal with.</span></span> <span data-ttu-id="79fd6-268">相反，如果你显式控制公共 API 的形状，则可以控制这些重大更改。</span><span class="sxs-lookup"><span data-stu-id="79fd6-268">Instead, if you explicitly control the shape of your public API, then you can control these breaking changes.</span></span> <span data-ttu-id="79fd6-269">在 DDD 术语中，这可以被视为反损坏层。</span><span class="sxs-lookup"><span data-stu-id="79fd6-269">In DDD terms, this can be thought of as an Anti-corruption layer.</span></span>

* <span data-ttu-id="79fd6-270">请考虑为泛型参数提供有意义的名称。</span><span class="sxs-lookup"><span data-stu-id="79fd6-270">Consider giving a meaningful name to your generic arguments.</span></span>

    <span data-ttu-id="79fd6-271">除非您正在编写不特定于特定域的真正的泛型代码，否则，有意义的名称可以帮助其他程序员了解他们所使用的域。</span><span class="sxs-lookup"><span data-stu-id="79fd6-271">Unless you are writing truly generic code that is not specific to a particular domain, a meaningful name can help other programmers understanding the domain they're working in.</span></span> <span data-ttu-id="79fd6-272">例如，在与文档数据库交互的上下文中，名为 `'Document` 的类型参数使你可以更清楚地了解你正在使用的函数或成员可以接受的通用文档类型。</span><span class="sxs-lookup"><span data-stu-id="79fd6-272">For example, a type parameter named `'Document` in the context of interacting with a document database makes it clearer that generic document types can be accepted by the function or member you are working with.</span></span>

* <span data-ttu-id="79fd6-273">考虑将泛型类型参数命名为 PascalCase。</span><span class="sxs-lookup"><span data-stu-id="79fd6-273">Consider naming generic type parameters with PascalCase.</span></span>

    <span data-ttu-id="79fd6-274">这是在 .NET 中执行操作的常规方法，因此建议使用 PascalCase，而不是 snake_case 或 camelCase。</span><span class="sxs-lookup"><span data-stu-id="79fd6-274">This is the general way to do things in .NET, so it's recommended that you use PascalCase rather than snake_case or camelCase.</span></span>

<span data-ttu-id="79fd6-275">最后，对于新的F#或大的基本代码，自动通用化并非始终是 boon 的。</span><span class="sxs-lookup"><span data-stu-id="79fd6-275">Finally, automatic generalization is not always a boon for people who are new to F# or a large codebase.</span></span> <span data-ttu-id="79fd6-276">使用通用组件时存在认知开销。</span><span class="sxs-lookup"><span data-stu-id="79fd6-276">There is cognitive overhead in using components that are generic.</span></span> <span data-ttu-id="79fd6-277">此外，如果自动通用化的函数不用于不同的输入类型（如果打算将其用作这样的类型），则这些函数在该时间点是泛型的。</span><span class="sxs-lookup"><span data-stu-id="79fd6-277">Furthermore, if automatically generalized functions are not used with different input types (let alone if they are intended to be used as such), then there is no real benefit to them being generic at that point in time.</span></span> <span data-ttu-id="79fd6-278">如果要编写的代码实际上是泛型的，则应始终考虑。</span><span class="sxs-lookup"><span data-stu-id="79fd6-278">Always consider if the code you are writing will actually benefit from being generic.</span></span>

## <a name="performance"></a><span data-ttu-id="79fd6-279">성능</span><span class="sxs-lookup"><span data-stu-id="79fd6-279">Performance</span></span>

### <a name="prefer-structs-for-small-data-types"></a><span data-ttu-id="79fd6-280">更倾向于小型数据类型的结构</span><span class="sxs-lookup"><span data-stu-id="79fd6-280">Prefer structs for small data types</span></span>

<span data-ttu-id="79fd6-281">使用结构（也称为值类型）通常可以提高某些代码的性能，因为这通常会避免分配对象。</span><span class="sxs-lookup"><span data-stu-id="79fd6-281">Using structs (also called Value Types) can often result in higher performance for some code because it typically avoids allocating objects.</span></span> <span data-ttu-id="79fd6-282">但结构并不总是 "更快" 按钮：如果结构中的数据大小超过16个字节，则复制数据通常会导致比使用引用类型更多的 CPU 时间。</span><span class="sxs-lookup"><span data-stu-id="79fd6-282">However, structs are not always a "go faster" button: if the size of the data in a struct exceeds 16 bytes, copying the data can often result in more CPU time spend than using a reference type.</span></span>

<span data-ttu-id="79fd6-283">若要确定是否应使用结构，请考虑以下情况：</span><span class="sxs-lookup"><span data-stu-id="79fd6-283">To determine if you should use a struct, consider the following conditions:</span></span>

- <span data-ttu-id="79fd6-284">如果数据的大小为16字节或更小。</span><span class="sxs-lookup"><span data-stu-id="79fd6-284">If the size of your data is 16 bytes or smaller.</span></span>
- <span data-ttu-id="79fd6-285">如果有很多这样的数据类型存在于正在运行的程序中的内存中。</span><span class="sxs-lookup"><span data-stu-id="79fd6-285">If you're likely to have many of these data types resident in memory in a running program.</span></span>

<span data-ttu-id="79fd6-286">如果第一个条件适用，则通常应使用结构。</span><span class="sxs-lookup"><span data-stu-id="79fd6-286">If the first condition applies, you should generally use a struct.</span></span> <span data-ttu-id="79fd6-287">如果这两个均适用，则几乎始终使用结构。</span><span class="sxs-lookup"><span data-stu-id="79fd6-287">If both apply, you should almost always use a struct.</span></span> <span data-ttu-id="79fd6-288">在某些情况下，上述条件适用，但使用结构并不比使用引用类型更好或更糟，但这种情况很少发生。</span><span class="sxs-lookup"><span data-stu-id="79fd6-288">There may be some cases where the previous conditions apply, but using a struct is no better or worse than using a reference type, but they are likely to be rare.</span></span> <span data-ttu-id="79fd6-289">但一定要在进行更改时始终度量，而不是在假设或直觉上操作。</span><span class="sxs-lookup"><span data-stu-id="79fd6-289">It's important to always measure when making changes like this, though, and not operate on assumption or intuition.</span></span>

#### <a name="prefer-struct-tuples-when-grouping-small-value-types"></a><span data-ttu-id="79fd6-290">分组小值类型时首选结构元组</span><span class="sxs-lookup"><span data-stu-id="79fd6-290">Prefer struct tuples when grouping small value types</span></span>

<span data-ttu-id="79fd6-291">请考虑以下两个函数：</span><span class="sxs-lookup"><span data-stu-id="79fd6-291">Consider the following two functions:</span></span>

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

<span data-ttu-id="79fd6-292">当使用[BenchmarkDotNet](https://benchmarkdotnet.org/)等统计基准工具来对这些函数进行基准测试时，会发现使用结构元组的 `runWithStructTuple` 函数的运行速度40%，并且不会分配内存。</span><span class="sxs-lookup"><span data-stu-id="79fd6-292">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that the `runWithStructTuple` function that uses struct tuples runs 40% faster and allocates no memory.</span></span>

<span data-ttu-id="79fd6-293">不过，这些结果在您自己的代码中并不总是如此。</span><span class="sxs-lookup"><span data-stu-id="79fd6-293">However, these results won't always be the case in your own code.</span></span> <span data-ttu-id="79fd6-294">如果将某个函数标记为 `inline`，则使用引用元组的代码可能会获得一些额外的优化，否则，将分配的代码只需进行优化即可。</span><span class="sxs-lookup"><span data-stu-id="79fd6-294">If you mark a function as `inline`, code that uses reference tuples may get some additional optimizations, or code that would allocate could simply be optimized away.</span></span> <span data-ttu-id="79fd6-295">应始终在性能考虑时测量结果，而永远不会根据假设或直觉来操作结果。</span><span class="sxs-lookup"><span data-stu-id="79fd6-295">You should always measure results whenever performance is concerned, and never operate based on assumption or intuition.</span></span>

#### <a name="prefer-struct-records-when-the-data-type-is-small"></a><span data-ttu-id="79fd6-296">当数据类型为小型时，首选结构记录</span><span class="sxs-lookup"><span data-stu-id="79fd6-296">Prefer struct records when the data type is small</span></span>

<span data-ttu-id="79fd6-297">前面所述的经验法则也包含在[ F#记录类型](../language-reference/records.md)中。</span><span class="sxs-lookup"><span data-stu-id="79fd6-297">The rule of thumb described earlier also holds for [F# record types](../language-reference/records.md).</span></span> <span data-ttu-id="79fd6-298">请考虑以下数据类型和处理这些数据类型的函数：</span><span class="sxs-lookup"><span data-stu-id="79fd6-298">Consider the following data types and functions that process them:</span></span>

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

<span data-ttu-id="79fd6-299">这类似于以前的元组代码，但这次此示例使用记录和内联的内部函数。</span><span class="sxs-lookup"><span data-stu-id="79fd6-299">This is similar to the previous tuple code, but this time the example uses records and an inlined inner function.</span></span>

<span data-ttu-id="79fd6-300">当使用[BenchmarkDotNet](https://benchmarkdotnet.org/)等统计基准工具对这些函数进行基准测试时，会发现 `processStructPoint` 的运行速度几乎60%，并且不会在托管堆上分配任何内容。</span><span class="sxs-lookup"><span data-stu-id="79fd6-300">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that `processStructPoint` runs nearly 60% faster and allocates nothing on the managed heap.</span></span>

#### <a name="prefer-struct-discriminated-unions-when-the-data-type-is-small"></a><span data-ttu-id="79fd6-301">当数据类型为小时，首选结构可区分联合</span><span class="sxs-lookup"><span data-stu-id="79fd6-301">Prefer struct discriminated unions when the data type is small</span></span>

<span data-ttu-id="79fd6-302">前面对结构元组和记录的性能的观测值还适用于[ F#可区分联合](../language-reference/discriminated-unions.md)。</span><span class="sxs-lookup"><span data-stu-id="79fd6-302">The previous observations about performance with struct tuples and records also holds for [F# Discriminated Unions](../language-reference/discriminated-unions.md).</span></span> <span data-ttu-id="79fd6-303">다음 코드를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="79fd6-303">Consider the following code:</span></span>

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

<span data-ttu-id="79fd6-304">通常为域建模定义单一用例可区分的联合。</span><span class="sxs-lookup"><span data-stu-id="79fd6-304">It's common to define single-case Discriminated Unions like this for domain modeling.</span></span> <span data-ttu-id="79fd6-305">当你使用[BenchmarkDotNet](https://benchmarkdotnet.org/)等统计基准工具来基准这些函数时，你会发现 `structReverseName` 比 `reverseName` 小字符串的速度要快25%。</span><span class="sxs-lookup"><span data-stu-id="79fd6-305">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that `structReverseName` runs about 25% faster than `reverseName` for small strings.</span></span> <span data-ttu-id="79fd6-306">对于大型字符串，这两个方法都执行相同的。</span><span class="sxs-lookup"><span data-stu-id="79fd6-306">For large strings, both perform about the same.</span></span> <span data-ttu-id="79fd6-307">因此，在这种情况下，最好使用结构。</span><span class="sxs-lookup"><span data-stu-id="79fd6-307">So, in this case, it's always preferable to use a struct.</span></span> <span data-ttu-id="79fd6-308">如前文所述，请始终度量，而不是在假设或直觉上操作。</span><span class="sxs-lookup"><span data-stu-id="79fd6-308">As previously mentioned, always measure and do not operate on assumptions or intuition.</span></span>

<span data-ttu-id="79fd6-309">尽管上面的示例演示了结构可区分联合生成了更好的性能，但在对域进行建模时，有一个很常见的可区分联合。</span><span class="sxs-lookup"><span data-stu-id="79fd6-309">Although the previous example showed that a struct Discriminated Union yielded better performance, it is common to have larger Discriminated Unions when modeling a domain.</span></span> <span data-ttu-id="79fd6-310">更大的数据类型（如这样的数据类型）可能不会执行，因为这些数据类型取决于其结构，因为这样做可能会涉及更多的复制操作。</span><span class="sxs-lookup"><span data-stu-id="79fd6-310">Larger data types like that may not perform as well if they are structs depending on the operations on them, since more copying could be involved.</span></span>

### <a name="functional-programming-and-mutation"></a><span data-ttu-id="79fd6-311">函数编程和变化</span><span class="sxs-lookup"><span data-stu-id="79fd6-311">Functional programming and mutation</span></span>

<span data-ttu-id="79fd6-312">F#默认情况下，值是不可变的，这使你可以避免某些类 bug （尤其是涉及并发和并行的类）。</span><span class="sxs-lookup"><span data-stu-id="79fd6-312">F# values are immutable by default, which allows you to avoid certain classes of bugs (especially those involving concurrency and parallelism).</span></span> <span data-ttu-id="79fd6-313">但是，在某些情况下，为了实现执行时间或内存分配的最佳（甚至合理）的效率，可以通过使用状态的就地转变来最佳地实现一段工作量。</span><span class="sxs-lookup"><span data-stu-id="79fd6-313">However, in certain cases, in order to achieve optimal (or even reasonable) efficiency of execution time or memory allocations, a span of work may best be implemented by using in-place mutation of state.</span></span> <span data-ttu-id="79fd6-314">这可以通过F#使用 `mutable` 关键字来选择。</span><span class="sxs-lookup"><span data-stu-id="79fd6-314">This is possible in an opt-in basis with F# with the `mutable` keyword.</span></span>

<span data-ttu-id="79fd6-315">在中F#使用 `mutable` 可能会受到功能纯度的干扰。</span><span class="sxs-lookup"><span data-stu-id="79fd6-315">Use of `mutable` in F# may feel at odds with functional purity.</span></span> <span data-ttu-id="79fd6-316">这是可理解的，但任何位置的功能纯度都有可能与性能目标相同。</span><span class="sxs-lookup"><span data-stu-id="79fd6-316">This is understandable, but functional purity everywhere can be at odds with performance goals.</span></span> <span data-ttu-id="79fd6-317">一种折衷是封装变化，使调用方不必关心调用函数时所发生的情况。</span><span class="sxs-lookup"><span data-stu-id="79fd6-317">A compromise is to encapsulate mutation such that callers need not care about what happens when they call a function.</span></span> <span data-ttu-id="79fd6-318">这样，便可以在性能关键代码的基于变化的实现上编写功能接口。</span><span class="sxs-lookup"><span data-stu-id="79fd6-318">This allows you to write a functional interface over a mutation-based implementation for performance-critical code.</span></span>

#### <a name="wrap-mutable-code-in-immutable-interfaces"></a><span data-ttu-id="79fd6-319">在不可变接口中包装可变代码</span><span class="sxs-lookup"><span data-stu-id="79fd6-319">Wrap mutable code in immutable interfaces</span></span>

<span data-ttu-id="79fd6-320">使用引用透明度作为目标，编写不公开性能关键函数的可变 underbelly 的代码至关重要。</span><span class="sxs-lookup"><span data-stu-id="79fd6-320">With referential transparency as a goal, it is critical to write code that does not expose the mutable underbelly of performance-critical functions.</span></span> <span data-ttu-id="79fd6-321">例如，下面的代码实现F#核心库中的 `Array.contains` 函数：</span><span class="sxs-lookup"><span data-stu-id="79fd6-321">For example, the following code implements the `Array.contains` function in the F# core library:</span></span>

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

<span data-ttu-id="79fd6-322">多次调用此函数不会更改基础数组，也不需要您维护任何使用它的可变状态。</span><span class="sxs-lookup"><span data-stu-id="79fd6-322">Calling this function multiple times does not change the underlying array, nor does it require you to maintain any mutable state in consuming it.</span></span> <span data-ttu-id="79fd6-323">尽管几乎每个代码行都使用变化，但它是引用的。</span><span class="sxs-lookup"><span data-stu-id="79fd6-323">It is referentially transparent, even though almost every line of code within it uses mutation.</span></span>

#### <a name="consider-encapsulating-mutable-data-in-classes"></a><span data-ttu-id="79fd6-324">考虑在类中封装可变数据</span><span class="sxs-lookup"><span data-stu-id="79fd6-324">Consider encapsulating mutable data in classes</span></span>

<span data-ttu-id="79fd6-325">前面的示例使用了一个函数来封装使用可变数据的操作。</span><span class="sxs-lookup"><span data-stu-id="79fd6-325">The previous example used a single function to encapsulate operations using mutable data.</span></span> <span data-ttu-id="79fd6-326">对于更复杂的数据集，这并不总是足够的。</span><span class="sxs-lookup"><span data-stu-id="79fd6-326">This is not always sufficient for more complex sets of data.</span></span> <span data-ttu-id="79fd6-327">请考虑以下几组函数：</span><span class="sxs-lookup"><span data-stu-id="79fd6-327">Consider the following sets of functions:</span></span>

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

<span data-ttu-id="79fd6-328">此代码具有高性能，但它公开了调用方负责维护的基于变化的数据结构。</span><span class="sxs-lookup"><span data-stu-id="79fd6-328">This code is performant, but it exposes the mutation-based data structure that callers are responsible for maintaining.</span></span> <span data-ttu-id="79fd6-329">这可以包装在类的内部，没有可更改的基础成员：</span><span class="sxs-lookup"><span data-stu-id="79fd6-329">This can be wrapped inside of a class with no underlying members that can change:</span></span>

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

<span data-ttu-id="79fd6-330">`Closure1Table` 封装基于变化的基础数据结构，因此不强制调用方维护基础数据结构。</span><span class="sxs-lookup"><span data-stu-id="79fd6-330">`Closure1Table` encapsulates the underlying mutation-based data structure, thereby not forcing callers to maintain the underlying data structure.</span></span> <span data-ttu-id="79fd6-331">类是一种强大的方法，用于封装基于变化的数据和例程，而不会向调用方公开详细信息。</span><span class="sxs-lookup"><span data-stu-id="79fd6-331">Classes are a powerful way to encapsulate data and routines that are mutation-based without exposing the details to callers.</span></span>

#### <a name="prefer-let-mutable-to-reference-cells"></a><span data-ttu-id="79fd6-332">首选 `let mutable` 引用单元格</span><span class="sxs-lookup"><span data-stu-id="79fd6-332">Prefer `let mutable` to reference cells</span></span>

<span data-ttu-id="79fd6-333">引用单元是表示对值（而不是值本身）的引用的一种方法。</span><span class="sxs-lookup"><span data-stu-id="79fd6-333">Reference cells are a way to represent the reference to a value rather than the value itself.</span></span> <span data-ttu-id="79fd6-334">尽管它们可用于性能关键代码，但不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="79fd6-334">Although they can be used for performance-critical code, they are not recommended.</span></span> <span data-ttu-id="79fd6-335">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79fd6-335">Consider the following example:</span></span>

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

<span data-ttu-id="79fd6-336">现在，使用引用单元格 "pollutes" 的所有后续代码都必须取消引用并重新引用基础数据。</span><span class="sxs-lookup"><span data-stu-id="79fd6-336">The use of a reference cell now "pollutes" all subsequent code with having to dereference and re-reference the underlying data.</span></span> <span data-ttu-id="79fd6-337">相反，请考虑 `let mutable`：</span><span class="sxs-lookup"><span data-stu-id="79fd6-337">Instead, consider `let mutable`:</span></span>

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

<span data-ttu-id="79fd6-338">除了 lambda 表达式中间的单点变化外，接触 `acc` 的所有其他代码都可以通过与正常的 `let`绑定不可变值的使用不相同的方式来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="79fd6-338">Aside from the single point of mutation in the middle of the lambda expression, all other code that touches `acc` can do so in a manner that is no different to the usage of a normal `let`-bound immutable value.</span></span> <span data-ttu-id="79fd6-339">这可以更轻松地随时间推移而变化。</span><span class="sxs-lookup"><span data-stu-id="79fd6-339">This will make it easier to change over time.</span></span>

## <a name="object-programming"></a><span data-ttu-id="79fd6-340">对象编程</span><span class="sxs-lookup"><span data-stu-id="79fd6-340">Object programming</span></span>

<span data-ttu-id="79fd6-341">F#完全支持对象和面向对象的（OO）概念。</span><span class="sxs-lookup"><span data-stu-id="79fd6-341">F# has full support for objects and object-oriented (OO) concepts.</span></span> <span data-ttu-id="79fd6-342">尽管许多 OO 概念非常强大且有用，但并非所有这些概念都是理想使用。</span><span class="sxs-lookup"><span data-stu-id="79fd6-342">Although many OO concepts are powerful and useful, not all of them are ideal to use.</span></span> <span data-ttu-id="79fd6-343">以下列表提供了有关高级别 OO 功能的指南。</span><span class="sxs-lookup"><span data-stu-id="79fd6-343">The following lists offer guidance on categories of OO features at a high level.</span></span>

<span data-ttu-id="79fd6-344">**在许多情况下，请考虑使用这些功能：**</span><span class="sxs-lookup"><span data-stu-id="79fd6-344">**Consider using these features in many situations:**</span></span>

* <span data-ttu-id="79fd6-345">点表示法（`x.Length`）</span><span class="sxs-lookup"><span data-stu-id="79fd6-345">Dot notation (`x.Length`)</span></span>
* <span data-ttu-id="79fd6-346">实例成员</span><span class="sxs-lookup"><span data-stu-id="79fd6-346">Instance members</span></span>
* <span data-ttu-id="79fd6-347">隐式构造函数</span><span class="sxs-lookup"><span data-stu-id="79fd6-347">Implicit constructors</span></span>
* <span data-ttu-id="79fd6-348">정적 멤버</span><span class="sxs-lookup"><span data-stu-id="79fd6-348">Static members</span></span>
* <span data-ttu-id="79fd6-349">索引器表示法（`arr.[x]`）</span><span class="sxs-lookup"><span data-stu-id="79fd6-349">Indexer notation (`arr.[x]`)</span></span>
* <span data-ttu-id="79fd6-350">命名参数和可选参数</span><span class="sxs-lookup"><span data-stu-id="79fd6-350">Named and Optional arguments</span></span>
* <span data-ttu-id="79fd6-351">接口和接口实现</span><span class="sxs-lookup"><span data-stu-id="79fd6-351">Interfaces and interface implementations</span></span>

<span data-ttu-id="79fd6-352">**不要首先接触这些功能，但在解决问题时，请慎用这些功能：**</span><span class="sxs-lookup"><span data-stu-id="79fd6-352">**Don't reach for these features first, but do judiciously apply them when they are convenient to solve a problem:**</span></span>

* <span data-ttu-id="79fd6-353">메서드 오버로드</span><span class="sxs-lookup"><span data-stu-id="79fd6-353">Method overloading</span></span>
* <span data-ttu-id="79fd6-354">封装的可变数据</span><span class="sxs-lookup"><span data-stu-id="79fd6-354">Encapsulated mutable data</span></span>
* <span data-ttu-id="79fd6-355">类型上的运算符</span><span class="sxs-lookup"><span data-stu-id="79fd6-355">Operators on types</span></span>
* <span data-ttu-id="79fd6-356">自动属性</span><span class="sxs-lookup"><span data-stu-id="79fd6-356">Auto properties</span></span>
* <span data-ttu-id="79fd6-357">实现 `IDisposable` 和 `IEnumerable`</span><span class="sxs-lookup"><span data-stu-id="79fd6-357">Implementing `IDisposable` and `IEnumerable`</span></span>
* <span data-ttu-id="79fd6-358">类型扩展</span><span class="sxs-lookup"><span data-stu-id="79fd6-358">Type extensions</span></span>
* <span data-ttu-id="79fd6-359">이벤트</span><span class="sxs-lookup"><span data-stu-id="79fd6-359">Events</span></span>
* <span data-ttu-id="79fd6-360">Structs</span><span class="sxs-lookup"><span data-stu-id="79fd6-360">Structs</span></span>
* <span data-ttu-id="79fd6-361">대리자</span><span class="sxs-lookup"><span data-stu-id="79fd6-361">Delegates</span></span>
* <span data-ttu-id="79fd6-362">열거형</span><span class="sxs-lookup"><span data-stu-id="79fd6-362">Enums</span></span>

<span data-ttu-id="79fd6-363">**通常，请避免使用这些功能，除非您必须使用这些功能：**</span><span class="sxs-lookup"><span data-stu-id="79fd6-363">**Generally avoid these features unless you must use them:**</span></span>

* <span data-ttu-id="79fd6-364">基于继承的类型层次结构和实现继承</span><span class="sxs-lookup"><span data-stu-id="79fd6-364">Inheritance-based type hierarchies and implementation inheritance</span></span>
* <span data-ttu-id="79fd6-365">Null 和 `Unchecked.defaultof<_>`</span><span class="sxs-lookup"><span data-stu-id="79fd6-365">Nulls and `Unchecked.defaultof<_>`</span></span>

### <a name="prefer-composition-over-inheritance"></a><span data-ttu-id="79fd6-366">优先使用继承</span><span class="sxs-lookup"><span data-stu-id="79fd6-366">Prefer composition over inheritance</span></span>

<span data-ttu-id="79fd6-367">[继承性之上的组合](https://en.wikipedia.org/wiki/Composition_over_inheritance)是一种长期可供使用F#的代码。</span><span class="sxs-lookup"><span data-stu-id="79fd6-367">[Composition over inheritance](https://en.wikipedia.org/wiki/Composition_over_inheritance) is a long-standing idiom that good F# code can adhere to.</span></span> <span data-ttu-id="79fd6-368">基本原则是，不应公开基类并强制调用方从该基类继承以获得功能。</span><span class="sxs-lookup"><span data-stu-id="79fd6-368">The fundamental principle is that you should not expose a base class and force callers to inherit from that base class to get functionality.</span></span>

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a><span data-ttu-id="79fd6-369">如果不需要类，请使用对象表达式来实现接口</span><span class="sxs-lookup"><span data-stu-id="79fd6-369">Use object expressions to implement interfaces if you don't need a class</span></span>

<span data-ttu-id="79fd6-370">[对象表达式](../language-reference/object-expressions.md)允许您动态实现接口，将实现的接口绑定到一个值，而无需在类中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="79fd6-370">[Object Expressions](../language-reference/object-expressions.md) allow you to implement interfaces on the fly, binding the implemented interface to a value without needing to do so inside of a class.</span></span> <span data-ttu-id="79fd6-371">这非常方便，尤其是在_只_需要实现接口且无需完整类的情况下。</span><span class="sxs-lookup"><span data-stu-id="79fd6-371">This is convenient, especially if you _only_ need to implement the interface and have no need for a full class.</span></span>

<span data-ttu-id="79fd6-372">例如，如果添加了一个没有 `open` 语句的符号，则在[ionide 入门](http://ionide.io/)中运行的代码可提供代码修复操作：</span><span class="sxs-lookup"><span data-stu-id="79fd6-372">For example, here is the code that is run in [Ionide](http://ionide.io/) to provide a code fix action if you've added a symbol that you don't have an `open` statement for:</span></span>

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

<span data-ttu-id="79fd6-373">由于与 Visual Studio Code API 交互时不需要类，因此对象表达式是适用于此的理想工具。</span><span class="sxs-lookup"><span data-stu-id="79fd6-373">Because there is no need for a class when interacting with the Visual Studio Code API, Object Expressions are an ideal tool for this.</span></span> <span data-ttu-id="79fd6-374">如果要以即席方式使用测试例程来围绕某个接口，则它们对于单元测试也很有用。</span><span class="sxs-lookup"><span data-stu-id="79fd6-374">They are also valuable for unit testing, when you want to stub out an interface with test routines in an ad hoc manner.</span></span>

## <a name="consider-type-abbreviations-to-shorten-signatures"></a><span data-ttu-id="79fd6-375">考虑键入缩写以缩短签名</span><span class="sxs-lookup"><span data-stu-id="79fd6-375">Consider Type Abbreviations to shorten signatures</span></span>

<span data-ttu-id="79fd6-376">[类型缩写](../language-reference/type-abbreviations.md)是将标签分配给其他类型的一种简便方法，例如函数签名或更复杂的类型。</span><span class="sxs-lookup"><span data-stu-id="79fd6-376">[Type Abbreviations](../language-reference/type-abbreviations.md) are a convenient way to assign a label to another type, such as a function signature or a more complex type.</span></span> <span data-ttu-id="79fd6-377">例如，以下别名为使用[CNTK](https://docs.microsoft.com/cognitive-toolkit/)（深度学习库）定义计算所需的内容分配一个标签：</span><span class="sxs-lookup"><span data-stu-id="79fd6-377">For example, the following alias assigns a label to what's needed to define a computation with [CNTK](https://docs.microsoft.com/cognitive-toolkit/), a deep learning library:</span></span>

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

<span data-ttu-id="79fd6-378">`Computation` 名称是一种方便的方法，用于表示与它所别名的签名相匹配的任何函数。</span><span class="sxs-lookup"><span data-stu-id="79fd6-378">The `Computation` name is a convenient way to denote any function that matches the signature it is aliasing.</span></span> <span data-ttu-id="79fd6-379">使用类似于这样的类型缩写词是非常方便的，可实现更简洁的代码。</span><span class="sxs-lookup"><span data-stu-id="79fd6-379">Using Type Abbreviations like this is convenient and allows for more succinct code.</span></span>

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a><span data-ttu-id="79fd6-380">避免使用类型缩写来表示域</span><span class="sxs-lookup"><span data-stu-id="79fd6-380">Avoid using Type Abbreviations to represent your domain</span></span>

<span data-ttu-id="79fd6-381">尽管类型缩写词在为函数签名提供名称时很方便，但在 abbreviating 其他类型时可能会造成混淆。</span><span class="sxs-lookup"><span data-stu-id="79fd6-381">Although Type Abbreviations are convenient for giving a name to function signatures, they can be confusing when abbreviating other types.</span></span> <span data-ttu-id="79fd6-382">请考虑此缩写：</span><span class="sxs-lookup"><span data-stu-id="79fd6-382">Consider this abbreviation:</span></span>

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

<span data-ttu-id="79fd6-383">这可能会造成混淆：</span><span class="sxs-lookup"><span data-stu-id="79fd6-383">This can be confusing in multiple ways:</span></span>

* <span data-ttu-id="79fd6-384">`BufferSize` 不是抽象;它只是一个整数的另一个名称。</span><span class="sxs-lookup"><span data-stu-id="79fd6-384">`BufferSize` is not an abstraction; it is just another name for an integer.</span></span>
* <span data-ttu-id="79fd6-385">如果 `BufferSize` 在公共 API 中公开，则可以轻松地对其进行误解，使其只是 `int`。</span><span class="sxs-lookup"><span data-stu-id="79fd6-385">If `BufferSize` is exposed in a public API, it can easily be misinterpreted to mean more than just `int`.</span></span> <span data-ttu-id="79fd6-386">通常，域类型具有多个属性，而不是基元类型，如 `int`。</span><span class="sxs-lookup"><span data-stu-id="79fd6-386">Generally, domain types have multiple attributes to them and are not primitive types like `int`.</span></span> <span data-ttu-id="79fd6-387">此缩写违反了假设。</span><span class="sxs-lookup"><span data-stu-id="79fd6-387">This abbreviation violates that assumption.</span></span>
* <span data-ttu-id="79fd6-388">`BufferSize` 的大小写（PascalCase）表示此类型包含更多数据。</span><span class="sxs-lookup"><span data-stu-id="79fd6-388">The casing of `BufferSize` (PascalCase) implies that this type holds more data.</span></span>
* <span data-ttu-id="79fd6-389">与为函数提供命名参数相比，此别名不会提高清晰度。</span><span class="sxs-lookup"><span data-stu-id="79fd6-389">This alias does not offer increased clarity compared with providing a named argument to a function.</span></span>
* <span data-ttu-id="79fd6-390">缩写词不会在编译的 IL 中列出;它只是一个整数，而此别名是编译时构造。</span><span class="sxs-lookup"><span data-stu-id="79fd6-390">The abbreviation will not manifest in compiled IL; it is just an integer and this alias is a compile-time construct.</span></span>

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) = ...
```

<span data-ttu-id="79fd6-391">总而言之，类型缩写的缺陷在于它们**不**是其所 abbreviating 的类型的抽象。</span><span class="sxs-lookup"><span data-stu-id="79fd6-391">In summary, the pitfall with Type Abbreviations is that they are **not** abstractions over the types they are abbreviating.</span></span> <span data-ttu-id="79fd6-392">在上面的示例中，`BufferSize` 只是覆盖下的 `int`，不包含任何其他数据，也不包括 `int` 已有的任何权益。</span><span class="sxs-lookup"><span data-stu-id="79fd6-392">In the previous example, `BufferSize` is just an `int` under the covers, with no additional data, nor any benefits from the type system besides what `int` already has.</span></span>

<span data-ttu-id="79fd6-393">使用类型缩写来表示域的另一种方法是使用单个用例可区分联合。</span><span class="sxs-lookup"><span data-stu-id="79fd6-393">An alternative approach to using type abbreviations to represent a domain is to use single-case discriminated unions.</span></span> <span data-ttu-id="79fd6-394">前面的示例可以建模，如下所示：</span><span class="sxs-lookup"><span data-stu-id="79fd6-394">The previous sample can be modeled as follows:</span></span>

```fsharp
type BufferSize = BufferSize of int
```

<span data-ttu-id="79fd6-395">如果你编写的代码在 `BufferSize` 及其基础值的基础上运行，则需要构造一个，而不是传入任意整数：</span><span class="sxs-lookup"><span data-stu-id="79fd6-395">If you write code that operates in terms of `BufferSize` and its underlying value, you need to construct one rather than pass in any arbitrary integer:</span></span>

```fsharp
module Networking =
    ...
    let send data (BufferSize size) =
    ...
```

<span data-ttu-id="79fd6-396">这会减少错误地将任意整数传递到 `send` 函数的可能性，因为调用方必须构造 `BufferSize` 类型以在调用函数之前包装值。</span><span class="sxs-lookup"><span data-stu-id="79fd6-396">This reduces the likelihood of mistakenly passing an arbitrary integer into the `send` function, because the caller must construct a `BufferSize` type to wrap a value before calling the function.</span></span>
