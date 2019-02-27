---
title: .NET Core 3.0 的新增功能
description: 了解 .NET Core 3.0 的新增功能。
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 12/31/2018
ms.openlocfilehash: 47a5ae3e81b0320a094ecc79e6b08035de66e785
ms.sourcegitcommit: acd8ed14fe94e9d4e3a7fb685fe83d05e941073c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2019
ms.locfileid: "56443070"
---
# <a name="whats-new-in-net-core-30-preview-2"></a><span data-ttu-id="833e1-103">.NET Core 3.0（预览版 2）的新增功能</span><span class="sxs-lookup"><span data-stu-id="833e1-103">What's new in .NET Core 3.0 (Preview 2)</span></span>

<span data-ttu-id="833e1-104">本文介绍 .NET Core 3.0（预览版 2）的新增功能。</span><span class="sxs-lookup"><span data-stu-id="833e1-104">This article describes what is new in .NET Core 3.0 (preview 2).</span></span> <span data-ttu-id="833e1-105">最大的增强功能之一是对 Windows 桌面应用程序（仅限 Windows）的支持。</span><span class="sxs-lookup"><span data-stu-id="833e1-105">One of the biggest enhancements is support for Windows desktop applications (Windows only).</span></span> <span data-ttu-id="833e1-106">通过利用名为“Windows 桌面”的 .NET Core 3.0 SDK 组件，可以移植 Windows 窗体和 Windows Presentation Foundation (WPF) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="833e1-106">By utilizing a .NET Core 3.0 SDK component called Windows Desktop, you can port your Windows Forms and Windows Presentation Foundation (WPF) applications.</span></span> <span data-ttu-id="833e1-107">为清楚起见，Windows 桌面组件仅在 Windows 上受支持，且仅在 Windows 中包含。</span><span class="sxs-lookup"><span data-stu-id="833e1-107">To be clear, the Windows Desktop component is only supported and included on Windows.</span></span> <span data-ttu-id="833e1-108">有关详细信息，请参阅下面的 [Window 桌面](#windows-desktop)一节。</span><span class="sxs-lookup"><span data-stu-id="833e1-108">For more information, see the section [Windows desktop](#windows-desktop) below.</span></span>

<span data-ttu-id="833e1-109">.NET Core 3.0 添加了对 C#8.0 的支持。</span><span class="sxs-lookup"><span data-stu-id="833e1-109">.NET Core 3.0 adds support for C# 8.0.</span></span>

<span data-ttu-id="833e1-110">立即在 Windows、Mac 和 Linux 上[下载并开始使用 .NET Core 3.0 预览版 2](https://aka.ms/netcore3download)。</span><span class="sxs-lookup"><span data-stu-id="833e1-110">[Download and get started with .NET Core 3.0 Preview 2](https://aka.ms/netcore3download) right now on Windows, Mac and Linux.</span></span> <span data-ttu-id="833e1-111">有关版本的完整详细信息，请参阅 [.NET Core 3.0 预览版 2 发行说明](https://aka.ms/netcore3releasenotes)。</span><span class="sxs-lookup"><span data-stu-id="833e1-111">You can see complete details of the release in the [.NET Core 3.0 Preview 2 release notes](https://aka.ms/netcore3releasenotes).</span></span>

<span data-ttu-id="833e1-112">要详细了解每个版本的发布内容，请参阅以下文档：</span><span class="sxs-lookup"><span data-stu-id="833e1-112">For more information about what was released with each version, see the following announcements:</span></span>

- [<span data-ttu-id="833e1-113">.NET Core 3.0 预览版 1 公告</span><span class="sxs-lookup"><span data-stu-id="833e1-113">.NET Core 3.0 Preview 1 announcement</span></span>](https://blogs.msdn.microsoft.com/dotnet/2018/12/04/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/)
- [<span data-ttu-id="833e1-114">.NET Core 3.0 预览版 2 公告</span><span class="sxs-lookup"><span data-stu-id="833e1-114">.NET Core 3.0 Preview 2 announcement</span></span>](https://blogs.msdn.microsoft.com/dotnet/2019/01/29/announcing-net-core-3-preview-2/)

## <a name="c-8"></a><span data-ttu-id="833e1-115">C# 8</span><span class="sxs-lookup"><span data-stu-id="833e1-115">C# 8</span></span>

<span data-ttu-id="833e1-116">.NET Core 3.0 支持 C#8，从 .NET Core 3.0 预览版 2 开始支持这些新功能。</span><span class="sxs-lookup"><span data-stu-id="833e1-116">.NET Core 3.0 supports C# 8, and as of .NET Core 3.0 Preview 2, supports these new features.</span></span> <span data-ttu-id="833e1-117">有关 C# 8.0 功能的详细信息，请参阅以下博客文章：</span><span class="sxs-lookup"><span data-stu-id="833e1-117">For more information about C# 8.0 features, see the following blog posts:</span></span>

- [<span data-ttu-id="833e1-118">使用 C# 8.0 中的模式执行更多操作</span><span class="sxs-lookup"><span data-stu-id="833e1-118">Do more with patterns in C# 8.0</span></span>](https://blogs.msdn.microsoft.com/dotnet/2019/01/24/do-more-with-patterns-in-c-8-0/)
- [<span data-ttu-id="833e1-119">尝试使用 C# 8.0</span><span class="sxs-lookup"><span data-stu-id="833e1-119">Take C# 8.0 for a spin</span></span>](https://blogs.msdn.microsoft.com/dotnet/2018/12/05/take-c-8-0-for-a-spin/)
- [<span data-ttu-id="833e1-120">生成 C# 8.0</span><span class="sxs-lookup"><span data-stu-id="833e1-120">Building C# 8.0</span></span>](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/)


### <a name="ranges-and-indices"></a><span data-ttu-id="833e1-121">范围和索引</span><span class="sxs-lookup"><span data-stu-id="833e1-121">Ranges and indices</span></span>

<span data-ttu-id="833e1-122">新 `Index` 类型可用于编制索引。</span><span class="sxs-lookup"><span data-stu-id="833e1-122">The new `Index` type can be used for indexing.</span></span> <span data-ttu-id="833e1-123">可以从从开头开始计数的 `int` 中创建一个类型，也可以使用从末尾开始计数的前缀 `^` 运算符 (C#) 创建一个：</span><span class="sxs-lookup"><span data-stu-id="833e1-123">You can create one from an `int` that counts from the beginning, or with a prefix `^` operator (C#) that counts from the end:</span></span>

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

<span data-ttu-id="833e1-124">此外，还有 `Range` 类型，它包含两个 `Index` 值，一个用于开头一个用于结尾，可以使用 `x..y` 范围表达式 (C#) 进行编写。</span><span class="sxs-lookup"><span data-stu-id="833e1-124">There is also a `Range` type, which consists of two `Index` values, one for the start and one for the end, and can be written with a `x..y` range expression (C#).</span></span> <span data-ttu-id="833e1-125">然后可以使用 `Range` 进行索引以便生成一个切片：</span><span class="sxs-lookup"><span data-stu-id="833e1-125">You can then index with a `Range` in order to produce a slice:</span></span>

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

### <a name="async-streams"></a><span data-ttu-id="833e1-126">异步流</span><span class="sxs-lookup"><span data-stu-id="833e1-126">Async streams</span></span>

<span data-ttu-id="833e1-127">`IAsyncEnumerable<T>` 类型是 `IEnumerable<T>` 的新异步版本。</span><span class="sxs-lookup"><span data-stu-id="833e1-127">The `IAsyncEnumerable<T>` type is a new asynchronous version of `IEnumerable<T>`.</span></span> <span data-ttu-id="833e1-128">该语言允许通过 `IAsyncEnumerable<T>` 执行 `await foreach` 操作来使用其元素，并对其使用 `yield return` 操作来生成元素。</span><span class="sxs-lookup"><span data-stu-id="833e1-128">The language lets you `await foreach` over `IAsyncEnumerable<T>` to consume their elements, and use `yield return` to them to produce elements.</span></span>

<span data-ttu-id="833e1-129">下面的示例演示如何生成和使用异步流。</span><span class="sxs-lookup"><span data-stu-id="833e1-129">The following example demonstrates both production and consumption of async streams.</span></span> <span data-ttu-id="833e1-130">`foreach` 语句为异步语句，它本身使用 `yield return` 为调用方生成异步流。</span><span class="sxs-lookup"><span data-stu-id="833e1-130">The `foreach` statement is async and itself uses `yield return` to produce an async stream for callers.</span></span> <span data-ttu-id="833e1-131">此模式（使用 `yield return`）是生成异步流的建议模型。</span><span class="sxs-lookup"><span data-stu-id="833e1-131">This pattern (using `yield return`) is the recommended model for producing async streams.</span></span>

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result; 
    }
}
```

<span data-ttu-id="833e1-132">除了能够 `await foreach`，还可以创建异步迭代器，例如，一个返回 `IAsyncEnumerable/IAsyncEnumerator` 的迭代器，可以在其中进行 `await` 和 `yield` 操作。</span><span class="sxs-lookup"><span data-stu-id="833e1-132">In addition to being able to `await foreach`, you can also create async iterators, for example, an iterator that returns an `IAsyncEnumerable/IAsyncEnumerator` that you can both `await` and `yield` in.</span></span> <span data-ttu-id="833e1-133">对于需要处理的对象，可以使用各种 BCL 类型（如 `Stream` 和 `Timer`）实现的 `IAsyncDisposable`。</span><span class="sxs-lookup"><span data-stu-id="833e1-133">For objects that need to be disposed, you can use `IAsyncDisposable`, which various BCL types implement, such as `Stream` and `Timer`.</span></span>

>[!NOTE]
><span data-ttu-id="833e1-134">如果要使用 Visual Studio 2019 预览版 2 或[适用于 Visual Studio Code 的 C# 扩展](https://github.com/OmniSharp/omnisharp-vscode/releases/tag/v1.18.0-beta5)的最新预览版进行开发，则需要 .NET Core 3.0 预览版 2，因为要使用异步流。</span><span class="sxs-lookup"><span data-stu-id="833e1-134">You need .NET Core 3.0 Preview 2 to use async streams if you want to develop with either Visual Studio 2019 Preview 2 or the latest preview of the [C# extension for Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/releases/tag/v1.18.0-beta5).</span></span> <span data-ttu-id="833e1-135">如果在命令行处使用 .NET Core 3.0 预览版 2，所有内容将按预期工作。</span><span class="sxs-lookup"><span data-stu-id="833e1-135">If you are using .NET Core 3.0 Preview 2 at the command line, then everything will work as expected.</span></span>

### <a name="using-declarations"></a><span data-ttu-id="833e1-136">Using 声明</span><span class="sxs-lookup"><span data-stu-id="833e1-136">Using Declarations</span></span>

<span data-ttu-id="833e1-137">Using 声明是确保正确释放对象的新方法。</span><span class="sxs-lookup"><span data-stu-id="833e1-137">*Using declarations* are a new way to ensure your object is properly disposed.</span></span> <span data-ttu-id="833e1-138">Using 声明可使对象在作用域内时保持活动状态。</span><span class="sxs-lookup"><span data-stu-id="833e1-138">A *using declaration* keeps the object alive while it is still in scope.</span></span> <span data-ttu-id="833e1-139">如果对象已不在作用域内，将自动释放对象。</span><span class="sxs-lookup"><span data-stu-id="833e1-139">Once the object becomes out of scope, it is automatically disposed.</span></span> <span data-ttu-id="833e1-140">这将减少嵌套的 Using 语句，并使代码更简洁。</span><span class="sxs-lookup"><span data-stu-id="833e1-140">This will reduce nested *using statements* and make your code cleaner.</span></span>

```csharp
static void Main(string[] args)
{
    using var options = Parse(args);
    if (options["verbose"]) { WriteLine("Logging..."); }

} // options disposed here
```

### <a name="switch-expressions"></a><span data-ttu-id="833e1-141">Switch 表达式</span><span class="sxs-lookup"><span data-stu-id="833e1-141">Switch Expressions</span></span>

<span data-ttu-id="833e1-142">Switch 表达式是执行 Switch 语句更简洁的方式，但由于它是表达式，因此将返回值。</span><span class="sxs-lookup"><span data-stu-id="833e1-142">*Switch expressions* are a cleaner way of doing a *switch statement* but, since it's an expression, returns a value.</span></span> <span data-ttu-id="833e1-143">Switch 表达式还与模式匹配完全集成，并使用放弃模式 `_`，表示 `default` 值。</span><span class="sxs-lookup"><span data-stu-id="833e1-143">*Switch expressions* are also fully integrated with pattern matching, and use the discard pattern, `_`, to represent the `default` value.</span></span>

<span data-ttu-id="833e1-144">可在以下示例中查看 Switch 表达式的语法：</span><span class="sxs-lookup"><span data-stu-id="833e1-144">You can see the syntax for *switch expressions* in the following example:</span></span>

```csharp
static string Display(object o) => o switch
{
    Point { X: 0, Y: 0 }         => "origin",
    Point { X: var x, Y: var y } => $"({x}, {y})",
    _                            => "unknown"
};
```

<span data-ttu-id="833e1-145">此示例中有两种模式发挥作用。</span><span class="sxs-lookup"><span data-stu-id="833e1-145">There are two patterns at play in this example.</span></span> <span data-ttu-id="833e1-146">`o` 首先匹配 `Point` 类型模式，然后匹配{大括号}内部的属性模式。</span><span class="sxs-lookup"><span data-stu-id="833e1-146">`o` first matches with the `Point` *type pattern* and then with the *property pattern* inside the *{curly braces}*.</span></span> <span data-ttu-id="833e1-147">`_` 描述 `discard pattern`，与 Switch 语句的 `default` 相同。</span><span class="sxs-lookup"><span data-stu-id="833e1-147">The `_` describes the `discard pattern`, which is the same as `default` for *switch statements*.</span></span>

<span data-ttu-id="833e1-148">通过模式，可以编写捕获意图的声明性代码，而不是相关测试的过程化代码。</span><span class="sxs-lookup"><span data-stu-id="833e1-148">Patterns enable you to write declarative code that captures your intent instead of procedural code that implements tests for it.</span></span> <span data-ttu-id="833e1-149">编译器负责实现这些令人乏味的过程化代码，并保证操作始终正确。</span><span class="sxs-lookup"><span data-stu-id="833e1-149">The compiler becomes responsible for implementing that boring procedural code and is guaranteed to always do it correctly.</span></span>

<span data-ttu-id="833e1-150">在某些情况下，Switch 语句仍然是比 Switch 表达式更好的选择，并且模式可同时用于这两种语法形式。</span><span class="sxs-lookup"><span data-stu-id="833e1-150">There will still be cases where *switch statements* will be a better choice than *switch expressions* and patterns can be used with both syntax styles.</span></span>

<span data-ttu-id="833e1-151">有关详细信息，请参阅[使用 C# 8.0 中的模式执行更多操作](https://blogs.msdn.microsoft.com/dotnet/2019/01/24/do-more-with-patterns-in-c-8-0/)。</span><span class="sxs-lookup"><span data-stu-id="833e1-151">For more information, see [Do more with patterns in C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2019/01/24/do-more-with-patterns-in-c-8-0/).</span></span>

## <a name="ieee-floating-point-improvements"></a><span data-ttu-id="833e1-152">IEEE 浮点改进</span><span class="sxs-lookup"><span data-stu-id="833e1-152">IEEE Floating-point improvements</span></span>

<span data-ttu-id="833e1-153">正在更新浮点 API，以符合 [IEEE 754-2008 修订](https://en.wikipedia.org/wiki/IEEE_754-2008_revision)。</span><span class="sxs-lookup"><span data-stu-id="833e1-153">Floating point APIs are in the process of being updated to comply with [IEEE 754-2008 revision](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span></span> <span data-ttu-id="833e1-154">这些更改旨在公开所有“必需”操作并确保这些操作在行为上符合 IEEE 规范。</span><span class="sxs-lookup"><span data-stu-id="833e1-154">The goal of these changes is to expose all "required" operations and ensure that they are behaviorally compliant with the IEEE spec.</span></span>

<span data-ttu-id="833e1-155">分析和格式化修补程序：</span><span class="sxs-lookup"><span data-stu-id="833e1-155">Parsing and formatting fixes:</span></span>

* <span data-ttu-id="833e1-156">正确分析并舍入任何输入长度。</span><span class="sxs-lookup"><span data-stu-id="833e1-156">Correctly parse and round inputs of any length.</span></span>
* <span data-ttu-id="833e1-157">正确分析并格式化负零。</span><span class="sxs-lookup"><span data-stu-id="833e1-157">Correctly parse and format negative zero.</span></span>
* <span data-ttu-id="833e1-158">通过执行不区分大小写的检查并允许在前面使用可选的 `+`（如果适用），正确分析无穷大和 NaN。</span><span class="sxs-lookup"><span data-stu-id="833e1-158">Correctly parse Infinity and NaN by performing a case-insensitive check and allowing an optional preceding `+` where applicable.</span></span>

<span data-ttu-id="833e1-159">新的数学 API 有：</span><span class="sxs-lookup"><span data-stu-id="833e1-159">New Math APIs have:</span></span>

* `BitIncrement/BitDecrement`\
<span data-ttu-id="833e1-160">相当于 `nextUp` 和 `nextDown` IEEE 运算。</span><span class="sxs-lookup"><span data-stu-id="833e1-160">Corresponds to the `nextUp` and `nextDown` IEEE operations.</span></span> <span data-ttu-id="833e1-161">它们将返回最小的浮点数，该数字大于或小于输入值（分别）。</span><span class="sxs-lookup"><span data-stu-id="833e1-161">They return the smallest floating-point number that compares greater or lesser than the input (respectively).</span></span> <span data-ttu-id="833e1-162">例如，`Math.BitIncrement(0.0)` 将返回 `double.Epsilon`。</span><span class="sxs-lookup"><span data-stu-id="833e1-162">For example, `Math.BitIncrement(0.0)` would return `double.Epsilon`.</span></span>

* `MaxMagnitude/MinMagnitude`\
<span data-ttu-id="833e1-163">相当于 `maxNumMag` 和 `minNumMag` IEEE 运算，它们将（分别）返回大于或小于两个输入的量值的值。</span><span class="sxs-lookup"><span data-stu-id="833e1-163">Corresponds to the `maxNumMag` and `minNumMag` IEEE operations, they return the value that is greater or lesser in magnitude of the two inputs (respectively).</span></span> <span data-ttu-id="833e1-164">例如，`Math.MaxMagnitude(2.0, -3.0)` 将返回 `-3.0`。</span><span class="sxs-lookup"><span data-stu-id="833e1-164">For example, `Math.MaxMagnitude(2.0, -3.0)` would return `-3.0`.</span></span>

* `ILogB`\
<span data-ttu-id="833e1-165">相当于返回整数值的 `logB` IEEE 运算，它将返回输入参数的整数对数（以 2 为底）。</span><span class="sxs-lookup"><span data-stu-id="833e1-165">Corresponds to the `logB` IEEE operation which returns an integral value, it returns the integral base-2 log of the input parameter.</span></span> <span data-ttu-id="833e1-166">这实际上与 `floor(log2(x))` 相同，但完成后出现最小舍入错误。</span><span class="sxs-lookup"><span data-stu-id="833e1-166">This is effectively the same as `floor(log2(x))`, but done with minimal rounding error.</span></span>

* `ScaleB`\
<span data-ttu-id="833e1-167">相当于采用整数值的 `scaleB` IEEE 运算，它实际返回 `x * pow(2, n)`，但完成后出现最小舍入错误。</span><span class="sxs-lookup"><span data-stu-id="833e1-167">Corresponds to the `scaleB` IEEE operation which takes an integral value, it returns effectively `x * pow(2, n)`, but is done with minimal rounding error.</span></span>

* `Log2`\
<span data-ttu-id="833e1-168">相当于返回（以 2 为底）对数的 `log2` IEEE 运算。</span><span class="sxs-lookup"><span data-stu-id="833e1-168">Corresponds to the `log2` IEEE operation, it returns the base-2 logarithm.</span></span> <span data-ttu-id="833e1-169">它会最小化舍入错误。</span><span class="sxs-lookup"><span data-stu-id="833e1-169">It minimizes rounding error.</span></span>

* `FusedMultiplyAdd`\
<span data-ttu-id="833e1-170">相当于执行乘法加法混合的 `fma` IEEE 运算。</span><span class="sxs-lookup"><span data-stu-id="833e1-170">Corresponds to the `fma` IEEE operation, it performs a fused multiply add.</span></span> <span data-ttu-id="833e1-171">也就是说，它以单个运算的形式执行 `(x * y) + z`，从而最小化舍入错误。</span><span class="sxs-lookup"><span data-stu-id="833e1-171">That is, it does `(x * y) + z` as a single operation, there-by minimizing the rounding error.</span></span> <span data-ttu-id="833e1-172">有关示例是返回 `1e308` 的 `FusedMultiplyAdd(1e308, 2.0, -1e308)`。</span><span class="sxs-lookup"><span data-stu-id="833e1-172">An example would be `FusedMultiplyAdd(1e308, 2.0, -1e308)` which returns `1e308`.</span></span> <span data-ttu-id="833e1-173">常规 `(1e308 * 2.0) - 1e308` 返回 `double.PositiveInfinity`。</span><span class="sxs-lookup"><span data-stu-id="833e1-173">The regular `(1e308 * 2.0) - 1e308` returns `double.PositiveInfinity`.</span></span>

* `CopySign`\
<span data-ttu-id="833e1-174">相当于 `copySign` IEEE 运算，它返回 `x` 的值但带有符号 `y`。</span><span class="sxs-lookup"><span data-stu-id="833e1-174">Corresponds to the `copySign` IEEE operation, it returns the value of `x`, but with the sign of `y`.</span></span>

## <a name="net-platform-dependent-intrinsics"></a><span data-ttu-id="833e1-175">.NET 平台依赖内部函数</span><span class="sxs-lookup"><span data-stu-id="833e1-175">.NET Platform Dependent Intrinsics</span></span>

<span data-ttu-id="833e1-176">已添加 API，允许访问某些性能导向的 CPU 指令，例如 SIMD 或位操作指令集。</span><span class="sxs-lookup"><span data-stu-id="833e1-176">APIs have been added that allow access to certain perf-oriented CPU instructions, such as the **SIMD** or **Bit Manipulation instruction** sets.</span></span> <span data-ttu-id="833e1-177">这些指令有助于在某些情况下实现显著的性能改进，例如高效地并行处理数据。</span><span class="sxs-lookup"><span data-stu-id="833e1-177">These instructions can help achieve big performance improvements in certain scenarios, such as processing data efficiently in parallel.</span></span> <span data-ttu-id="833e1-178">除公开供程序使用的 API 外，.NET 库已开始使用这些指令改进性能。</span><span class="sxs-lookup"><span data-stu-id="833e1-178">In addition to exposing the APIs for your programs to use, the .NET libraries have begun using these instructions to improve performance.</span></span>

<span data-ttu-id="833e1-179">以下 CoreCLR PR 通过实现或以下相关应用演示了几个内部函数：</span><span class="sxs-lookup"><span data-stu-id="833e1-179">The following CoreCLR PRs demonstrate a few of the intrinsics, either via implementation or use:</span></span>

* [<span data-ttu-id="833e1-180">实现简单的 SSE2 硬件内部函数</span><span class="sxs-lookup"><span data-stu-id="833e1-180">Implement simple SSE2 hardware intrinsics</span></span>](https://github.com/dotnet/coreclr/pull/15585)
* [<span data-ttu-id="833e1-181">实现 SSE 硬件内部函数</span><span class="sxs-lookup"><span data-stu-id="833e1-181">Implement the SSE hardware intrinsics</span></span>](https://github.com/dotnet/coreclr/pull/15538)
* [<span data-ttu-id="833e1-182">Arm64 基 HW 内部函数</span><span class="sxs-lookup"><span data-stu-id="833e1-182">Arm64 Base HW Intrinsics</span></span>](https://github.com/dotnet/coreclr/pull/16822)
* [<span data-ttu-id="833e1-183">对 Locate{First|Last}Found{Byte|Char} 使用 TZCNT 和 LZCNT</span><span class="sxs-lookup"><span data-stu-id="833e1-183">Use TZCNT and LZCNT for Locate{First|Last}Found{Byte|Char}</span></span>](https://github.com/dotnet/coreclr/pull/21073)

<span data-ttu-id="833e1-184">有关详细信息，请参阅[依赖 .NET 平台的内部函数](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md)，它定义了用于定义此硬件基础结构的方法，允许 Microsoft、芯片供应商或其他任何公司或个人定义应向 .NET 代码公开的硬件/芯片 API。</span><span class="sxs-lookup"><span data-stu-id="833e1-184">For more information, see [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md), which defines an approach for defining this hardware infrastructure, allowing Microsoft, chip vendors, or any other company or individual to define hardware/chip APIs that should be exposed to .NET code.</span></span>

## <a name="default-executables"></a><span data-ttu-id="833e1-185">默认可执行文件</span><span class="sxs-lookup"><span data-stu-id="833e1-185">Default executables</span></span>

<span data-ttu-id="833e1-186">.NET Core 现在将默认生成[依赖于框架的可执行文件](../deploying/index.md#framework-dependent-executables-fde)。</span><span class="sxs-lookup"><span data-stu-id="833e1-186">.NET Core will now build [framework-dependent executables](../deploying/index.md#framework-dependent-executables-fde) by default.</span></span> <span data-ttu-id="833e1-187">对于使用全局安装的 .NET Core 版本的应用程序而言，这是一项新功能。</span><span class="sxs-lookup"><span data-stu-id="833e1-187">This is new for applications that use a globally installed version of .NET Core.</span></span> <span data-ttu-id="833e1-188">到目前为止，仅[自包含部署](../deploying/index.md#self-contained-deployments-scd)会生成可执行文件。</span><span class="sxs-lookup"><span data-stu-id="833e1-188">Until now, only [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) would produce an executable.</span></span>

<span data-ttu-id="833e1-189">在 `dotnet build` 或 `dotnet publish` 期间，将创建一个假设与你使用的 SDK 的环境和平台相匹配的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="833e1-189">During `dotnet build` or `dotnet publish`, an executable is created provided that matches the environment and platform of the SDK you are using.</span></span> <span data-ttu-id="833e1-190">和其他本机可执行文件一样，可以使用这些可执行文件执行相同操作，例如：</span><span class="sxs-lookup"><span data-stu-id="833e1-190">You can expect the same things with these executables as you would other native executables, such as:</span></span>

* <span data-ttu-id="833e1-191">可以双击可执行文件。</span><span class="sxs-lookup"><span data-stu-id="833e1-191">You can double-click on the executable.</span></span>
* <span data-ttu-id="833e1-192">可以直接从命令提示符启用应用程序，如 Windows 上的 `myapp.exe`，以及 Linux 和 macOS 上的 `./myapp`。</span><span class="sxs-lookup"><span data-stu-id="833e1-192">You can launch the application from a command prompt directly, such as `myapp.exe` on Windows, and `./myapp` on Linux and macOS.</span></span>

## <a name="build-copies-dependencies"></a><span data-ttu-id="833e1-193">生成副本依赖项</span><span class="sxs-lookup"><span data-stu-id="833e1-193">Build copies dependencies</span></span>

<span data-ttu-id="833e1-194">`dotnet build` 现将应用程序的 NuGet 依赖项从 NuGet 缓存复制到生成输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="833e1-194">`dotnet build` now copies NuGet dependencies for your application from the NuGet cache to the build output folder.</span></span> <span data-ttu-id="833e1-195">此前，依赖项仅作为 `dotnet publish` 的一部分复制。</span><span class="sxs-lookup"><span data-stu-id="833e1-195">Previously, dependencies were only copied as part of `dotnet publish`.</span></span> 

<span data-ttu-id="833e1-196">有些操作，比如链接和 razor 页面发布仍需要发布。</span><span class="sxs-lookup"><span data-stu-id="833e1-196">There are some operations, like linking and razor page publishing that will still require publishing.</span></span>


## <a name="local-dotnet-tools"></a><span data-ttu-id="833e1-197">本地 dotnet 工具</span><span class="sxs-lookup"><span data-stu-id="833e1-197">Local dotnet tools</span></span>

>[!WARNING]
><span data-ttu-id="833e1-198">.NET Core 3.0 预览版 1 至 .NET Core 3.0 预览版 2 中的 .NET Core 本地工具发生了更改。</span><span class="sxs-lookup"><span data-stu-id="833e1-198">There was a change in .NET Core Local Tools between .NET Core 3.0 Preview 1 and .NET Core 3.0 Preview 2.</span></span>  <span data-ttu-id="833e1-199">如果在预览版 1 中通过运行 `dotnet tool restore` 或 `dotnet tool install` 等命令试用本地工具，则需要删除本地工具缓存文件夹，然后本地工具才能在预览版 2 中正常工作。</span><span class="sxs-lookup"><span data-stu-id="833e1-199">If you tried out local tools in Preview 1 by running a command like `dotnet tool restore` or `dotnet tool install`, you need to delete your local tools cache folder before local tools will work correctly in Preview 2.</span></span> <span data-ttu-id="833e1-200">此文件夹位于：</span><span class="sxs-lookup"><span data-stu-id="833e1-200">This folder is located at:</span></span>
>
><span data-ttu-id="833e1-201">在 mac、Linux 上：`rm -r $HOME/.dotnet/toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="833e1-201">On mac, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span></span>
>
><span data-ttu-id="833e1-202">在 Windows 上：`rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="833e1-202">On Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span></span>
>
><span data-ttu-id="833e1-203">如果不删除此文件夹，将收到错误。</span><span class="sxs-lookup"><span data-stu-id="833e1-203">If you do not delete this folder, you will receive an error.</span></span>

<span data-ttu-id="833e1-204">虽然 .NET Core 2.1 支持全局工具，.NET Core 3.0 现在使用本地工具。</span><span class="sxs-lookup"><span data-stu-id="833e1-204">While .NET Core 2.1 supported global tools, .NET Core 3.0 now has local tools.</span></span> <span data-ttu-id="833e1-205">本地工具类似于全局工具，但与磁盘上的特定位置相关联。</span><span class="sxs-lookup"><span data-stu-id="833e1-205">Local tools are similar to global tools but are associated with a particular location on disk.</span></span> <span data-ttu-id="833e1-206">这支持每个项目和每个存储库工具。</span><span class="sxs-lookup"><span data-stu-id="833e1-206">This enables per-project and per-repository tooling.</span></span> <span data-ttu-id="833e1-207">本地安装的任何工具都不可在全局范围使用。</span><span class="sxs-lookup"><span data-stu-id="833e1-207">Any tool installed locally isn't available globally.</span></span> <span data-ttu-id="833e1-208">工具是作为 NuGet 包分发的。</span><span class="sxs-lookup"><span data-stu-id="833e1-208">Tools are distributed as NuGet packages.</span></span>

<span data-ttu-id="833e1-209">本地工具依赖于当前目录中的清单文件名称 `dotnet-tools.json`。</span><span class="sxs-lookup"><span data-stu-id="833e1-209">Local tools rely on a manifest file name `dotnet-tools.json` in your current directory.</span></span> <span data-ttu-id="833e1-210">此清单文件定义在该文件夹和以下文件夹中可用的工具。</span><span class="sxs-lookup"><span data-stu-id="833e1-210">This manifest file defines the tools to be available at that folder and below.</span></span> <span data-ttu-id="833e1-211">通过在存储库的根目录中创建此清单文件，可确保克隆代码的任何人都可以恢复和使用所需的工具，以便成功使用代码。</span><span class="sxs-lookup"><span data-stu-id="833e1-211">By creating this manifest file at the root of your repository, you ensure anyone cloning your code can restore and use the tools that are needed to successfully work with your code.</span></span>

<span data-ttu-id="833e1-212">若要创建 `dotnet-tools.json` 清单文件，请使用：</span><span class="sxs-lookup"><span data-stu-id="833e1-212">To create a `dotnet-tools.json` manifest file, use:</span></span>

```console
dotnet new tool-manifest
```

<span data-ttu-id="833e1-213">使用以下命令向本地清单添加新的工具：</span><span class="sxs-lookup"><span data-stu-id="833e1-213">Add a new tool to the local manifest with:</span></span>

```console
dotnet tool install <packageId>
```

<span data-ttu-id="833e1-214">此外，还可以使用以下命令列出本地清单中的工具：</span><span class="sxs-lookup"><span data-stu-id="833e1-214">You can also list the tools in the local manifest with:</span></span>

```console
dotnet tool list
```

<span data-ttu-id="833e1-215">若要查看全局安装的工具，请使用：</span><span class="sxs-lookup"><span data-stu-id="833e1-215">To see what tools are installed globally, use:</span></span>

```console
dotnet tool list -g
```

<span data-ttu-id="833e1-216">当本地工具清单文件可用，但清单中定义的工具尚未安装时，请使用以下命令自动下载和安装这些工具：</span><span class="sxs-lookup"><span data-stu-id="833e1-216">When the local tools manifest file is available, but the tools defined in the manifest have not been installed, use the following command to automatically download and install those tools:</span></span>

```console
dotnet tool restore
```

<span data-ttu-id="833e1-217">使用以下命令运行本地工具：</span><span class="sxs-lookup"><span data-stu-id="833e1-217">Run a local tool with the following command:</span></span>

```console
dotnet tool run <tool-command-name>
```

<span data-ttu-id="833e1-218">本地工具运行时，dotnet 将搜索当前目录结构中的清单。</span><span class="sxs-lookup"><span data-stu-id="833e1-218">When a local tool is run, dotnet searches for a manifest up the current directory structure.</span></span> <span data-ttu-id="833e1-219">找到工具清单文件时，将在其中搜索请求的工具。</span><span class="sxs-lookup"><span data-stu-id="833e1-219">When a tool manifest file is found, it is searched for the requested tool.</span></span> <span data-ttu-id="833e1-220">如果在清单中找到工具，但没有缓存，用户将收到一个错误并需要运行 `dotnet tool restore`。</span><span class="sxs-lookup"><span data-stu-id="833e1-220">If the tool is found in the manifest, but not the cache, the user receives an error and needs to run `dotnet tool restore`.</span></span>

<span data-ttu-id="833e1-221">要从本地工具清单文件中删除工具，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="833e1-221">To remove a tool from the local tool manifest file, run the following command:</span></span>

```console
dotnet tool uninstall <packageId>
```

<span data-ttu-id="833e1-222">工具清单文件旨在允许手动编辑，你可能会执行此操作来更新使用存储库所需的版本。</span><span class="sxs-lookup"><span data-stu-id="833e1-222">The tool manifest file is designed to allow hand editing – which you might do to update the required version for working with the repository.</span></span> <span data-ttu-id="833e1-223">下面是 `dotnet-tools.json` 示例文件：</span><span class="sxs-lookup"><span data-stu-id="833e1-223">Here is an example `dotnet-tools.json` file:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "dotnetsay": {
      "version": "2.1.4",
      "commands": [
        "dotnetsay"
      ]
    },
    "t-rex": {
      "version": "1.0.103",
      "commands": [
        "t-rex"
      ]
    }
  }
}
```

<span data-ttu-id="833e1-224">对于全局工具和本地工具，需要一个兼容的运行时版本。</span><span class="sxs-lookup"><span data-stu-id="833e1-224">For both global and local tools, a compatible version of the runtime is required.</span></span> <span data-ttu-id="833e1-225">目前，NuGet.org 上的许多工具都面向 .NET Core Runtime 2.1。</span><span class="sxs-lookup"><span data-stu-id="833e1-225">Many tools currently on NuGet.org target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="833e1-226">要在全局范围或本地安装这些工具，仍需要安装 [NET Core 2.1 运行时](https://dotnet.microsoft.com/download/dotnet-core/2.1)。</span><span class="sxs-lookup"><span data-stu-id="833e1-226">To install those globally or locally, you would still need to install the [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

## <a name="windows-desktop"></a><span data-ttu-id="833e1-227">Windows 桌面</span><span class="sxs-lookup"><span data-stu-id="833e1-227">Windows desktop</span></span>

<span data-ttu-id="833e1-228">从 .NET Core 3.0 预览版 1 开始，可以使用 WPF 和 Windows 窗体来生成 Windows 桌面应用程序。</span><span class="sxs-lookup"><span data-stu-id="833e1-228">Starting with .NET Core 3.0 Preview 1, you can build Windows desktop applications using WPF and Windows Forms.</span></span> <span data-ttu-id="833e1-229">这些框架还支持通过 [XAML 岛](/windows/uwp/xaml-platform/xaml-host-controls)从 Windows UI XAML 库 (WinUI) 使用新式控件和 Fluent 样式。</span><span class="sxs-lookup"><span data-stu-id="833e1-229">These frameworks also support using modern controls and Fluent styling from the Windows UI XAML Library (WinUI) via [XAML islands](/windows/uwp/xaml-platform/xaml-host-controls).</span></span>

<span data-ttu-id="833e1-230">Windows 桌面部件是 Windows .NET Core 3.0 SDK 的一部分。</span><span class="sxs-lookup"><span data-stu-id="833e1-230">The Windows Desktop component is part of the Windows .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="833e1-231">可以使用以下 `dotnet` 命令创建新的 WPF 或 Windows 窗体应用：</span><span class="sxs-lookup"><span data-stu-id="833e1-231">You can create a new WPF or Windows Forms app with the following `dotnet` commands:</span></span>

```console
dotnet new wpf
dotnet new winforms
```

<span data-ttu-id="833e1-232">Visual Studio 2019 预览版 2 添加了适用于 .NET Core 3.0 Windows 窗体和 WPF 的“新建项目”模板。</span><span class="sxs-lookup"><span data-stu-id="833e1-232">Visual Studio 2019 Preview 2 adds **New Project** templates for .NET Core 3.0 Windows Forms and WPF.</span></span> <span data-ttu-id="833e1-233">设计器仍然不受支持。</span><span class="sxs-lookup"><span data-stu-id="833e1-233">Designers are still not yet supported.</span></span> <span data-ttu-id="833e1-234">可以在 Visual Studio 2019 中打开、启动和调试这些项目。</span><span class="sxs-lookup"><span data-stu-id="833e1-234">And you can open, launch, and debug these projects in Visual Studio 2019.</span></span>

<span data-ttu-id="833e1-235">Visual Studio 2017 15.9 添加了[支持 .NET Core 预览版](https://blogs.msdn.microsoft.com/dotnet/2018/11/13/net-core-tooling-update-for-visual-studio-2017-version-15-9/)的功能，但用户需要先启用该功能，而此操作不受支持。</span><span class="sxs-lookup"><span data-stu-id="833e1-235">Visual Studio 2017 15.9 adds the ability to [enable .NET Core previews](https://blogs.msdn.microsoft.com/dotnet/2018/11/13/net-core-tooling-update-for-visual-studio-2017-version-15-9/), but you need to turn that feature on, and it's not a supported scenario.</span></span>

<span data-ttu-id="833e1-236">新项目与现有的 .NET Core 项目相同，其中有一些附加内容。</span><span class="sxs-lookup"><span data-stu-id="833e1-236">The new projects are the same as existing .NET Core projects, with a couple additions.</span></span> <span data-ttu-id="833e1-237">下面是基本 .NET Core 控制台项目与基本 Windows 窗体以及 WPF 项目之间的比较。</span><span class="sxs-lookup"><span data-stu-id="833e1-237">Here is the comparison of the basic .NET Core console project and a basic Windows Forms and WPF project.</span></span>

<span data-ttu-id="833e1-238">在 .NET Core 控制台项目中，该项目使用 `Microsoft.NET.Sdk` SDK 并通过 `netcoreapp3.0` 目标框架在 .NET Core 3.0 上声明依赖项。</span><span class="sxs-lookup"><span data-stu-id="833e1-238">In a .NET Core console project, the project uses the `Microsoft.NET.Sdk` SDK and declares a dependency on .NET Core 3.0 via the `netcoreapp3.0` target framework.</span></span> <span data-ttu-id="833e1-239">要创建 Windows Desktop 应用，请使用 `Microsoft.NET.Sdk.WindowsDesktop` SDK 并选择要使用的 UI 框架：</span><span class="sxs-lookup"><span data-stu-id="833e1-239">To create a Windows Desktop app, use the `Microsoft.NET.Sdk.WindowsDesktop` SDK and choose which UI framework to use:</span></span>

```diff
-<Project Sdk="Microsoft.NET.Sdk">
+<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
+   <UseWPF>true</UseWPF>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="833e1-240">若要选择 Windows 窗体而不是 WPF，请设置 `UseWindowsForms` 而不是 `UseWPF`：</span><span class="sxs-lookup"><span data-stu-id="833e1-240">To choose Windows Forms over WPF, set `UseWindowsForms` instead of `UseWPF`:</span></span>

```diff
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
-   <UseWPF>true</UseWPF>
+   <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="833e1-241">如果应用同时使用这两个框架，则 `UseWPF` 和 `UseWindowsForms` 可以同时设置为 `true`，例如，当 Windows 窗体对话框托管 WPF 控件。</span><span class="sxs-lookup"><span data-stu-id="833e1-241">Both `UseWPF` and `UseWindowsForms` can be set to `true` if the app uses both frameworks, for example when a Windows Forms dialog is hosting a WPF control.</span></span>

<span data-ttu-id="833e1-242">请在 [dotnet/winforms](https://github.com/dotnet/winforms/issues)、[dotnet/wpf](https://github.com/dotnet/wpf/issues) 和 [dotnet/core](https://github.com/dotnet/core/issues) 存储库上共享反馈。</span><span class="sxs-lookup"><span data-stu-id="833e1-242">Please share your feedback on the [dotnet/winforms](https://github.com/dotnet/winforms/issues),  [dotnet/wpf](https://github.com/dotnet/wpf/issues) and [dotnet/core](https://github.com/dotnet/core/issues) repos.</span></span>

## <a name="msix-deployment-for-windows-desktop"></a><span data-ttu-id="833e1-243">Windows 桌面的 MSIX 部署</span><span class="sxs-lookup"><span data-stu-id="833e1-243">MSIX Deployment for Windows Desktop</span></span>

<span data-ttu-id="833e1-244">[MSIX](https://docs.microsoft.com/windows/msix/) 是新的 Windows 应用包格式。</span><span class="sxs-lookup"><span data-stu-id="833e1-244">[MSIX](https://docs.microsoft.com/windows/msix/) is a new Windows app package format.</span></span> <span data-ttu-id="833e1-245">可以使用它将 .NET Core 3.0 桌面应用程序部署到 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="833e1-245">It can be used to deploy .NET Core 3.0 desktop applications to Windows 10.</span></span>

<span data-ttu-id="833e1-246">Visual Studio 2019 预览版 2 中提供 [Windows 应用程序打包项目](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net)，允许用户使用[独立式](../deploying/index.md#self-contained-deployments-scd) .NET Core 应用程序创建 MSIX 包。</span><span class="sxs-lookup"><span data-stu-id="833e1-246">The [Windows Application Packaging Project](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), available in Visual Studio 2019 Preview 2, allows you to create MSIX packages with [self-contained](../deploying/index.md#self-contained-deployments-scd) .NET Core applications.</span></span>

><span data-ttu-id="833e1-247">注意:.NET Core 项目文件必须在 `<RuntimeIdentifiers>` 属性中指定支持的运行时：</span><span class="sxs-lookup"><span data-stu-id="833e1-247">Note: The .NET Core project file must specify the supported runtimes in the `<RuntimeIdentifiers>` property:</span></span>
```xml
<RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
```

## <a name="fast-built-in-json-support"></a><span data-ttu-id="833e1-248">快速内置的 JSON 支持</span><span class="sxs-lookup"><span data-stu-id="833e1-248">Fast built-in JSON support</span></span>

<span data-ttu-id="833e1-249">.NET 生态系统依赖于 [Json.NET](https://www.newtonsoft.com/json) 和其他常用的 JSON 库，它们仍是很好的选择。</span><span class="sxs-lookup"><span data-stu-id="833e1-249">The .NET ecosystem has relied on [**Json.NET**](https://www.newtonsoft.com/json) and other popular JSON libraries, which continue to be good choices.</span></span> <span data-ttu-id="833e1-250">Json.NET 使用 .NET 字符串作为其基本数据类型，它实际上是 UTF-16。</span><span class="sxs-lookup"><span data-stu-id="833e1-250">**Json.NET** uses .NET strings as its base datatype, which are UTF-16 under the hood.</span></span>

<span data-ttu-id="833e1-251">新的内置 JSON 支持具有高性能、低分配的特点，并基于 `Span<byte>`。</span><span class="sxs-lookup"><span data-stu-id="833e1-251">The new built-in JSON support is high-performance, low allocation, and based on `Span<byte>`.</span></span> <span data-ttu-id="833e1-252">已向 .NET Core 3.0 `System.Text.Json` 命名空间添加三个新的与 JSON 相关的主类型。</span><span class="sxs-lookup"><span data-stu-id="833e1-252">Three new main JSON-related types have been added to .NET Core 3.0 the `System.Text.Json` namespace.</span></span>

### <a name="utf8jsonreader"></a><span data-ttu-id="833e1-253">Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="833e1-253">Utf8JsonReader</span></span>

<span data-ttu-id="833e1-254">`System.Text.Json.Utf8JsonReader` 是面向 UTF-8 编码 JSON 文本的一个高性能、低分配、只进读取器，从 `ReadOnlySpan<byte>` 读取信息。</span><span class="sxs-lookup"><span data-stu-id="833e1-254">`System.Text.Json.Utf8JsonReader` is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="833e1-255">`Utf8JsonReader` 是一种基本的低级类型，可用于构建自定义分析器和反序列化程序。</span><span class="sxs-lookup"><span data-stu-id="833e1-255">The `Utf8JsonReader` is a foundational, low-level type, that can be leveraged to build custom parsers and deserializers.</span></span> <span data-ttu-id="833e1-256">使用新的 `Utf8JsonReader` 读取 JSON 有效负载要比使用 **Json.NET** 的读取器快 2 倍。</span><span class="sxs-lookup"><span data-stu-id="833e1-256">Reading through a JSON payload using the new `Utf8JsonReader` is 2x faster than using the reader from **Json.NET**.</span></span> <span data-ttu-id="833e1-257">在需要将 JSON 令牌实现为 (UTF-16) 字符串之前，它不会进行分配。</span><span class="sxs-lookup"><span data-stu-id="833e1-257">It does not allocate until you need to actualize JSON tokens as (UTF-16) strings.</span></span>

<span data-ttu-id="833e1-258">此新 API 将包含以下部件：</span><span class="sxs-lookup"><span data-stu-id="833e1-258">This new API will include the following components:</span></span>

* <span data-ttu-id="833e1-259">在预览版 1 中：JSON 读取器（顺序访问）</span><span class="sxs-lookup"><span data-stu-id="833e1-259">In Preview 1: JSON reader (sequential access)</span></span>
* <span data-ttu-id="833e1-260">接下来推出：JSON 编写器、DOM（随机访问）、poco 序列化程序、poco 反序列化程序</span><span class="sxs-lookup"><span data-stu-id="833e1-260">Coming next: JSON writer, DOM (random access), poco serializer, poco deserializer</span></span>

<span data-ttu-id="833e1-261">下面是基本的 `Utf8JsonReader` 读取器循环，可以作为起点：</span><span class="sxs-lookup"><span data-stu-id="833e1-261">Here is the basic reader loop for the `Utf8JsonReader` that can be used as a starting point:</span></span>

```csharp
using System.Text.Json;

public static void Utf8JsonReaderLoop(ReadOnlySpan<byte> dataUtf8)
{
    var json = new Utf8JsonReader(dataUtf8, isFinalBlock: true, state: default);

    while (json.Read())
    {
        JsonTokenType tokenType = json.TokenType;
        ReadOnlySpan<byte> valueSpan = json.ValueSpan;
        switch (tokenType)
        {
            case JsonTokenType.StartObject:
            case JsonTokenType.EndObject:
                break;
            case JsonTokenType.StartArray:
            case JsonTokenType.EndArray:
                break;
            case JsonTokenType.PropertyName:
                break;
            case JsonTokenType.String:
                string valueString = json.GetStringValue();
                break;
            case JsonTokenType.Number:
                if (!json.TryGetInt32Value(out int valueInteger))
                {
                    throw new FormatException();
                }
                break;
            case JsonTokenType.True:
            case JsonTokenType.False:
                bool valueBool = json.GetBooleanValue();
                break;
            case JsonTokenType.Null:
                break;
            default:
                throw new ArgumentException();
        }
    }

    dataUtf8 = dataUtf8.Slice((int)json.BytesConsumed);
    JsonReaderState state = json.CurrentState;
}
```

### <a name="utf8jsonwriter"></a><span data-ttu-id="833e1-262">Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="833e1-262">Utf8JsonWriter</span></span>

<span data-ttu-id="833e1-263">`System.Text.Json.Utf8JsonWriter` 提供了一种高性能、非缓存的只进方式，通过常见 .NET 类型（例如，`String`、`Int32` 和 `DateTime`）编写 UTF-8 编码的 JSON 文本。</span><span class="sxs-lookup"><span data-stu-id="833e1-263">`System.Text.Json.Utf8JsonWriter` provides a high-performance, non-cached, forward-only way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="833e1-264">与阅读器一样，编写器是一种基本的低级类型，可用于构建自定义序列化程序。</span><span class="sxs-lookup"><span data-stu-id="833e1-264">Like the reader, the writer is a foundational, low-level type, that can be leveraged to build custom serializers.</span></span> <span data-ttu-id="833e1-265">使用新的 `Utf8JsonWriter` 编写 JSON 有效负载比通过 Json.NET 使用编写器快 30-80%，且无需分配。</span><span class="sxs-lookup"><span data-stu-id="833e1-265">Writing a JSON payload using the new `Utf8JsonWriter` is 30-80% faster than using the writer from **Json.NET** and does not allocate.</span></span>

<span data-ttu-id="833e1-266">下面是可用作起始点的 `Utf8JsonWriter` 的示例用法：</span><span class="sxs-lookup"><span data-stu-id="833e1-266">Here is a sample usage of the `Utf8JsonWriter` that can be used as a starting point:</span></span>

```csharp
static int WriteJson(IBufferWriter<byte> output, long[] extraData)
{
    var json = new Utf8JsonWriter(output, state: default);

    json.WriteStartObject();

    json.WriteNumber("age", 15, escape: false);
    json.WriteString("date", DateTime.Now);
    json.WriteString("first", "John");
    json.WriteString("last", "Smith");

    json.WriteStartArray("phoneNumbers", escape: false);
    json.WriteStringValue("425-000-1212", escape: false);
    json.WriteStringValue("425-000-1213");
    json.WriteEndArray();

    json.WriteStartObject("address");
    json.WriteString("street", "1 Microsoft Way");
    json.WriteString("city", "Redmond");
    json.WriteNumber("zip", 98052);
    json.WriteEndObject();

    json.WriteStartArray("ExtraArray");
    for (var i = 0; i < extraData.Length; i++)
    {
        json.WriteNumberValue(extraData[i]);
    }
    json.WriteEndArray();

    json.WriteEndObject();

    json.Flush(isFinalBlock: true);

    return (int)json.BytesWritten;
}
```

<span data-ttu-id="833e1-267">`Utf8JsonWriter` 接受 `IBufferWriter<byte>` 作为输出位置，用于异步写入 json 数据，而作为调用方，你需要提供具体实现。</span><span class="sxs-lookup"><span data-stu-id="833e1-267">The `Utf8JsonWriter` accepts `IBufferWriter<byte>` as the output location to synchronously write the json data into, and you as the caller need to provide a concrete implementation.</span></span> <span data-ttu-id="833e1-268">平台目前不包括此接口的实现。</span><span class="sxs-lookup"><span data-stu-id="833e1-268">The platform does not currently include an implementation of this interface.</span></span> <span data-ttu-id="833e1-269">有关 `IBufferWriter<byte>` 的示例，请参阅[https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35](https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35)。</span><span class="sxs-lookup"><span data-stu-id="833e1-269">For an example of `IBufferWriter<byte>`, see [https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35](https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35)</span></span>

### <a name="jsondocument"></a><span data-ttu-id="833e1-270">JsonDocument</span><span class="sxs-lookup"><span data-stu-id="833e1-270">JsonDocument</span></span>

<span data-ttu-id="833e1-271">`System.Text.Json.JsonDocument` 是基于 `Utf8JsonReader` 构建的。</span><span class="sxs-lookup"><span data-stu-id="833e1-271">`System.Text.Json.JsonDocument` is built on top of the `Utf8JsonReader`.</span></span> <span data-ttu-id="833e1-272">`JsonDocument` 可分析 JSON 数据并生成只读文档对象模型 (DOM)，可对模型进行查询，以支持随机访问和枚举。</span><span class="sxs-lookup"><span data-stu-id="833e1-272">The `JsonDocument` provides the ability to parse JSON data and build a read-only Document Object Model (DOM) that can be queried to support random access and enumeration.</span></span> <span data-ttu-id="833e1-273">可以通过 `JsonElement` 类型（由 `JsonDocument` 公开为名为 `RootElement` 的属性）访问构成数据的 JSON 元素。</span><span class="sxs-lookup"><span data-stu-id="833e1-273">The JSON elements that compose the data can be accessed via the `JsonElement` type which is exposed by the `JsonDocument` as a property called `RootElement`.</span></span> <span data-ttu-id="833e1-274">`JsonElement` 包含 JSON 数组和对象枚举器，以及用于将 JSON 文本转换为常见 .NET 类型的 API。</span><span class="sxs-lookup"><span data-stu-id="833e1-274">The `JsonElement` contains the JSON array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="833e1-275">使用 `JsonDocument` 分析常规 JSON 有效负载并访问其所有成员比使用 Json.NET 快 2-3 倍，且为合理大小（即 < 1 MB）的数据所分配的量非常少。</span><span class="sxs-lookup"><span data-stu-id="833e1-275">Parsing a typical JSON payload and accessing all its members using the `JsonDocument` is 2-3x faster than **Json.NET** with very little allocations for data that is reasonably sized (i.e. < 1 MB).</span></span>

<span data-ttu-id="833e1-276">下面是可用作起始点的 `JsonDocument` 和 `JsonElement` 的示例用法：</span><span class="sxs-lookup"><span data-stu-id="833e1-276">Here is a sample usage of the `JsonDocument` and `JsonElement` that can be used as a starting point:</span></span>

```csharp
static double ParseJson()
{
    const string json = " [ { \"name\": \"John\" }, [ \"425-000-1212\", 15 ], { \"grades\": [ 90, 80, 100, 75 ] } ]";

    double average = -1;

    using (JsonDocument doc = JsonDocument.Parse(json))
    {
        JsonElement root = doc.RootElement;
        JsonElement info = root[1];

        string phoneNumber = info[0].GetString();
        int age = info[1].GetInt32();

        JsonElement grades = root[2].GetProperty("grades");

        double sum = 0;
        foreach (JsonElement grade in grades.EnumerateArray())
        {
            sum += grade.GetInt32();
        }

        int numberOfCourses = grades.GetArrayLength();
        average = sum / numberOfCourses;
    }

    return average;
}
```

## <a name="assembly-unloadability"></a><span data-ttu-id="833e1-277">程序集卸载功能</span><span class="sxs-lookup"><span data-stu-id="833e1-277">Assembly Unloadability</span></span>

<span data-ttu-id="833e1-278">程序集卸载功能是 `AssemblyLoadContext` 的一项新功能。</span><span class="sxs-lookup"><span data-stu-id="833e1-278">Assembly unloadability is a new capability of `AssemblyLoadContext`.</span></span> <span data-ttu-id="833e1-279">这项新功能从 API 的角度来看，很大程度上是透明的，公开时只有几个新的 API。</span><span class="sxs-lookup"><span data-stu-id="833e1-279">This new feature is largely transparent from an API perspective, exposed with just a few new APIs.</span></span> <span data-ttu-id="833e1-280">它支持卸载加载程序上下文，为实例化类型、静态字段和程序集本身释放所有内存。</span><span class="sxs-lookup"><span data-stu-id="833e1-280">It enables a loader context to be unloaded, releasing all memory for instantiated types, static fields and for the assembly itself.</span></span> <span data-ttu-id="833e1-281">应用程序应该能够永久通过此机制加载和卸载程序集，而不会发生内容泄露。</span><span class="sxs-lookup"><span data-stu-id="833e1-281">An application should be able to load and unload assemblies via this mechanism forever without experiencing a memory leak.</span></span>

<span data-ttu-id="833e1-282">该新功能可用于类似如下的方案：</span><span class="sxs-lookup"><span data-stu-id="833e1-282">This new capability can be used for scenarios similar to:</span></span>

* <span data-ttu-id="833e1-283">需要动态插件加载和卸载的插件方案。</span><span class="sxs-lookup"><span data-stu-id="833e1-283">Plugin scenarios where dynamic plugin loading and unloading is required.</span></span> 
* <span data-ttu-id="833e1-284">动态编译、运行，然后刷新代码。</span><span class="sxs-lookup"><span data-stu-id="833e1-284">Dynamically compiling, running and then flushing code.</span></span> <span data-ttu-id="833e1-285">可用于网站，脚本编写引擎等。</span><span class="sxs-lookup"><span data-stu-id="833e1-285">Useful for web sites, scripting engines, etc.</span></span>
* <span data-ttu-id="833e1-286">加载程序集进行自检（例如，ReflectionOnlyLoad），尽管在很多情况下，[MetadataLoadContext](#type-metadataloadcontext)（发布于预览版 1）是个更好的选择。</span><span class="sxs-lookup"><span data-stu-id="833e1-286">Loading assemblies for introspection (like ReflectionOnlyLoad), although [MetadataLoadContext](#type-metadataloadcontext) (released in Preview 1) will be a better choice in many cases.</span></span>

<span data-ttu-id="833e1-287">有关详细信息，请参阅[使用卸载功能](https://github.com/dotnet/coreclr/pull/22221)文档。</span><span class="sxs-lookup"><span data-stu-id="833e1-287">For more information, see the [Using Unloadability](https://github.com/dotnet/coreclr/pull/22221) document.</span></span>

<span data-ttu-id="833e1-288">程序集卸载需要非常小心，因为要确保理解对加载程序上下文以外的托管对象的所有引用，并且这些引用均处于管理中。</span><span class="sxs-lookup"><span data-stu-id="833e1-288">Assembly unloading requires significant care to ensure that all references to managed objects from outside a loader context are understood and managed.</span></span> <span data-ttu-id="833e1-289">请求卸载加载程序上下文时，任何外部引用都需要解除引用，以便加载程序上下文其自身实现一致性即可。</span><span class="sxs-lookup"><span data-stu-id="833e1-289">When the loader context is requested to be unloaded, any outside references need to have been unreferenced so that the loader context is self-consistent only to itself.</span></span>

<span data-ttu-id="833e1-290">.NET Framework 中通过应用程序域 (AppDomain) 提供程序集卸载功能，而 .NET Core 不支持该功能。</span><span class="sxs-lookup"><span data-stu-id="833e1-290">Assembly unloadability was provided in the .NET Framework by Application Domains (AppDomains), which are not supported with .NET Core.</span></span> <span data-ttu-id="833e1-291">相比于这个新模型，AppDomain 既有优势又有局限。</span><span class="sxs-lookup"><span data-stu-id="833e1-291">AppDomains had both benefits and limitations compared to this new model.</span></span> <span data-ttu-id="833e1-292">与 AppDomain 相比，这个新的加载程序模型更具灵活性、性能更高。</span><span class="sxs-lookup"><span data-stu-id="833e1-292">Consider this new loader model to be more flexible and higher performant when compared to AppDomains.</span></span>

## <a name="windows-native-interop"></a><span data-ttu-id="833e1-293">Windows 本机互操作</span><span class="sxs-lookup"><span data-stu-id="833e1-293">Windows Native Interop</span></span>

<span data-ttu-id="833e1-294">Windows 提供丰富的本机 API，包括平面 C API、COM 和 WinRT 的形式。</span><span class="sxs-lookup"><span data-stu-id="833e1-294">Windows offers a rich native API, in the form of flat C APIs, COM, and WinRT.</span></span> <span data-ttu-id="833e1-295">从 .NET Core 1.0 开始，一直支持 P/Invoke。</span><span class="sxs-lookup"><span data-stu-id="833e1-295">Since .NET Core 1.0, **P/Invoke** has been supported.</span></span> <span data-ttu-id="833e1-296">现在，.NET Core 3.0 支持共同创建 COM API 和激活 WinRT API。</span><span class="sxs-lookup"><span data-stu-id="833e1-296">Now with .NET Core 3.0, support for the ability to **CoCreate COM APIs** and **Activate WinRT APIs** has been added.</span></span>

<span data-ttu-id="833e1-297">可参阅结合使用 COM 和 [Excel 演示源代码](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo)的示例。</span><span class="sxs-lookup"><span data-stu-id="833e1-297">You can see an example of using COM with the [Excel Demo source code](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span></span>


## <a name="type-sequencereader"></a><span data-ttu-id="833e1-298">类型：SequenceReader</span><span class="sxs-lookup"><span data-stu-id="833e1-298">Type: SequenceReader</span></span>

<span data-ttu-id="833e1-299">在 .NET Core 3.0 中，已添加可用作 `ReadOnlySequence<T>` 读取器的 `System.Buffers.SequenceReader`。</span><span class="sxs-lookup"><span data-stu-id="833e1-299">In .NET Core 3.0, `System.Buffers.SequenceReader` has been added which can be used as a reader for `ReadOnlySequence<T>`.</span></span> <span data-ttu-id="833e1-300">这样可以对跨多个支持缓冲区的 `System.IO.Pipelines` 数据进行简单、高性能、低分配分析。</span><span class="sxs-lookup"><span data-stu-id="833e1-300">This allows easy, high performance, low allocation parsing of `System.IO.Pipelines` data that can cross multiple backing buffers.</span></span> 

<span data-ttu-id="833e1-301">以下示例将输入 `Sequence` 分解为有效的 `CR/LF` 分隔行：</span><span class="sxs-lookup"><span data-stu-id="833e1-301">The following example breaks an input `Sequence` into valid `CR/LF` delimited lines:</span></span>

```csharp
private static ReadOnlySpan<byte> CRLF => new byte[] { (byte)'\r', (byte)'\n' };

public static void ReadLines(ReadOnlySequence<byte> sequence)
{
    SequenceReader<byte> reader = new SequenceReader<byte>(sequence);

    while (!reader.End)
    {
        if (!reader.TryReadToAny(out ReadOnlySpan<byte> line, CRLF, advancePastDelimiter:false))
        {
            // Couldn't find another delimiter
            // ...
        }

        if (!reader.IsNext(CRLF, advancePast: true))
        {
            // Not a good CR/LF pair
            // ...
        }

        // line is valid, process
        ProcessLine(line);
    }
}
```

## <a name="type-metadataloadcontext"></a><span data-ttu-id="833e1-302">类型：MetadataLoadContext</span><span class="sxs-lookup"><span data-stu-id="833e1-302">Type: MetadataLoadContext</span></span>

<span data-ttu-id="833e1-303">添加了 `MetadataLoadContext` 类型，该类型支持读取程序集元数据，而不会影响调用方的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="833e1-303">The `MetadataLoadContext` type has been added that enables reading assembly metadata without affecting the caller’s application domain.</span></span> <span data-ttu-id="833e1-304">程序集作为数据读取，包括为与当前运行时环境不同的体系结构和平台构建的程序集。</span><span class="sxs-lookup"><span data-stu-id="833e1-304">Assemblies are read as data, including assemblies built for different architectures and platforms than the current runtime environment.</span></span> <span data-ttu-id="833e1-305">`MetadataLoadContext` 与 <xref:System.Reflection.Assembly.ReflectionOnlyLoad*> 重叠，后者仅在 .NET Framework 中可用。</span><span class="sxs-lookup"><span data-stu-id="833e1-305">`MetadataLoadContext` overlaps with the <xref:System.Reflection.Assembly.ReflectionOnlyLoad*>, which is only available in the .NET Framework.</span></span>

<span data-ttu-id="833e1-306">[System.Reflection.MetadataLoadContext 包](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext) 现已推出 `MetdataLoadContext`。</span><span class="sxs-lookup"><span data-stu-id="833e1-306">`MetdataLoadContext` is available in the [System.Reflection.MetadataLoadContext package](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext).</span></span> <span data-ttu-id="833e1-307">它是一个 .NET Standard 2.0 包。</span><span class="sxs-lookup"><span data-stu-id="833e1-307">It is a .NET Standard 2.0 package.</span></span>

<span data-ttu-id="833e1-308">`MetadataLoadContext` 公开的 API 类似于 <xref:System.Runtime.Loader.AssemblyLoadContext> 类型，但不是基于该类型。</span><span class="sxs-lookup"><span data-stu-id="833e1-308">The `MetadataLoadContext` exposes APIs similar to the <xref:System.Runtime.Loader.AssemblyLoadContext> type, but is not based on that type.</span></span> <span data-ttu-id="833e1-309">与 <xref:System.Runtime.Loader.AssemblyLoadContext> 非常相似，`MetadataLoadContext` 支持在一个独立的程序集加载范围内加载程序集。</span><span class="sxs-lookup"><span data-stu-id="833e1-309">Much like <xref:System.Runtime.Loader.AssemblyLoadContext>, the `MetadataLoadContext` enables loading assemblies within an isolated assembly loading universe.</span></span> <span data-ttu-id="833e1-310">`MetdataLoadContext` API 返回 <xref:System.Reflection.Assembly> 对象，支持使用熟悉的反射 API。</span><span class="sxs-lookup"><span data-stu-id="833e1-310">`MetdataLoadContext` APIs return <xref:System.Reflection.Assembly> objects, enabling the use of familiar reflection APIs.</span></span> <span data-ttu-id="833e1-311">不允许以执行为导向的 API，如 [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127)，并将引发 InvalidOperationException。</span><span class="sxs-lookup"><span data-stu-id="833e1-311">Execution-oriented APIs, such as [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127), are not allowed and will throw InvalidOperationException.</span></span>

<span data-ttu-id="833e1-312">下面的示例演示如何在实现给定接口的程序集中找到具体类型：</span><span class="sxs-lookup"><span data-stu-id="833e1-312">The following sample demonstrates how to find concrete types in an assembly that implements a given interface:</span></span>

```csharp
var paths = new string[] {@"C:\myapp\mscorlib.dll", @"C:\myapp\myapp.dll"};
var resolver = new PathAssemblyResolver(paths);
using (var lc = new MetadataLoadContext(resolver))
{
    Assembly a = lc.LoadFromAssemblyName("myapp");
    Type myInterface = a.GetType("MyApp.IPluginInterface");
    foreach (Type t in a.GetTypes())
    {
        if (t.IsClass && myInterface.IsAssignableFrom(t))
            Console.WriteLine($"Class {t.FullName} implements IPluginInterface");
    }
}
```

<span data-ttu-id="833e1-313">`MetadataLoadContext` 场景包括设计时功能、生成时工具和运行时启动功能，这些功能需要将一组程序集作为数据进行检查，并在执行检查后释放所有文件锁和内存。</span><span class="sxs-lookup"><span data-stu-id="833e1-313">Scenarios for `MetadataLoadContext` include design-time features, build-time tooling, and runtime light-up features that need to inspect a set of assemblies as data and have all file locks and memory freed after inspection is performed.</span></span>

<span data-ttu-id="833e1-314">`MetadataLoadContext` 有一个解析程序类传递给其构造函数。</span><span class="sxs-lookup"><span data-stu-id="833e1-314">The `MetadataLoadContext` has a resolver class passed to its constructor.</span></span> <span data-ttu-id="833e1-315">解析程序的工作是在给定 `AssemblyName` 条件下加载 `Assembly`。</span><span class="sxs-lookup"><span data-stu-id="833e1-315">The resolver's job is to load an `Assembly` given its `AssemblyName`.</span></span> <span data-ttu-id="833e1-316">解析程序类派生自抽象 `MetadataAssemblyResolver` 类。</span><span class="sxs-lookup"><span data-stu-id="833e1-316">The resolver class derives from the abstract `MetadataAssemblyResolver` class.</span></span> <span data-ttu-id="833e1-317">`PathAssemblyResolver` 提供了基于路径场景的解析程序的实现。</span><span class="sxs-lookup"><span data-stu-id="833e1-317">An implementation of the resolver for path-based scenarios is provided with `PathAssemblyResolver`.</span></span>

<span data-ttu-id="833e1-318">[MetadataLoadContext 测试](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests)演示了许多用例。</span><span class="sxs-lookup"><span data-stu-id="833e1-318">The [MetadataLoadContext tests](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests) demonstrate many use cases.</span></span> <span data-ttu-id="833e1-319">[程序集测试](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs)是一个很好的起点。</span><span class="sxs-lookup"><span data-stu-id="833e1-319">The [Assembly tests](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs) are a good place to start.</span></span>

## <a name="tls-13--openssl-111-on-linux"></a><span data-ttu-id="833e1-320">Linux 上的 TLS 1.3 和 OpenSSL 1.1.1</span><span class="sxs-lookup"><span data-stu-id="833e1-320">TLS 1.3 & OpenSSL 1.1.1 on Linux</span></span>

<span data-ttu-id="833e1-321">.NET Core 现在可以在给定环境中使用 [OpenSSL 1.1.1 中的 TLS 1.3 支持](https://www.openssl.org/blog/blog/2018/09/11/release111/)。</span><span class="sxs-lookup"><span data-stu-id="833e1-321">.NET Core will now take advantage of [TLS 1.3 support in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), when it is available in a given environment.</span></span> <span data-ttu-id="833e1-322">对于 [OpenSSL 团队](https://www.openssl.org/blog/blog/2018/09/11/release111/)来说，TLS 1.3 有许多好处：</span><span class="sxs-lookup"><span data-stu-id="833e1-322">There are multiple benefits of TLS 1.3, per the [OpenSSL team](https://www.openssl.org/blog/blog/2018/09/11/release111/):</span></span>

* <span data-ttu-id="833e1-323">由于减少了客户端和服务器之间所需的往返次数，从而提高了连接时间。</span><span class="sxs-lookup"><span data-stu-id="833e1-323">Improved connection times due to a reduction in the number of round trips required between the client and server.</span></span>

* <span data-ttu-id="833e1-324">由于消除了各种过时和不安全的加密算法和加密了更多连接握手，从而提高了安全性。</span><span class="sxs-lookup"><span data-stu-id="833e1-324">Improved security due to the removal of various obsolete and insecure cryptographic algorithms and encryption of more of the connection handshake.</span></span>

<span data-ttu-id="833e1-325">.NET Core 3.0 预览版 1 能够利用 OpenSSL 1.1.1、OpenSSL 1.1.0 或 OpenSSL 1.0.2（无论在 Linux 系统上找到的最佳版本是什么）。</span><span class="sxs-lookup"><span data-stu-id="833e1-325">.NET Core 3.0 Preview 1 is capable of utilizing **OpenSSL 1.1.1**, **OpenSSL 1.1.0**, or **OpenSSL 1.0.2** (whatever the best version found is, on a Linux system).</span></span>  <span data-ttu-id="833e1-326">当 OpenSSL 1.1.1 可用时，SslStream 和 HttpClient 类型将在使用 `SslProtocols.None`（系统默认协议）时使用 TLS 1.3，假定客户端和服务器都支持 TLS 1.3。</span><span class="sxs-lookup"><span data-stu-id="833e1-326">When **OpenSSL 1.1.1** is available the SslStream and HttpClient types will use **TLS 1.3** when using `SslProtocols.None` (system default protocols), assuming both the client and server support **TLS 1.3**.</span></span>

<span data-ttu-id="833e1-327">下面的示例演示在 Ubuntu 18.10 上 .NET Core 3.0 预览版 1 如何连接到 <https://www.cloudflare.com>：</span><span class="sxs-lookup"><span data-stu-id="833e1-327">The following sample demonstrates .NET Core 3.0 Preview 1 on Ubuntu 18.10 connecting to <https://www.cloudflare.com>:</span></span>

```csharp
using System;
using System.Net.Security;
using System.Net.Sockets;
using System.Threading.Tasks;

namespace tlstest
{
    class Program
    {
        static async Task Main()
        {
            using (TcpClient tcpClient = new TcpClient())
            {
                string targetHost = "www.cloudflare.com";

                await tcpClient.ConnectAsync(targetHost, 443);

                using (SslStream sslStream = new SslStream(tcpClient.GetStream()))
                {
                    await sslStream.AuthenticateAsClientAsync(targetHost);
                    await Console.Out.WriteLineAsync($"Connected to {targetHost} with {sslStream.SslProtocol}");
                }
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/tlstest$ dotnet run
Connected to www.cloudflare.com with Tls13
user@comp-ubuntu1810:~/tlstest$ openssl version
OpenSSL 1.1.1  11 Sep 2018
```

>[!IMPORTANT]
><span data-ttu-id="833e1-328">Windows 和 macOS 尚不支持 TLS 1.3。</span><span class="sxs-lookup"><span data-stu-id="833e1-328">Windows and macOS do not yet support **TLS 1.3**.</span></span> <span data-ttu-id="833e1-329">当支持可用时，.NET Core 3.0 将在这些操作系统上支持 TLS 1.3。</span><span class="sxs-lookup"><span data-stu-id="833e1-329">.NET Core 3.0 will support **TLS 1.3** on these operating systems when support becomes available.</span></span>

## <a name="cryptography"></a><span data-ttu-id="833e1-330">密码</span><span class="sxs-lookup"><span data-stu-id="833e1-330">Cryptography</span></span>

<span data-ttu-id="833e1-331">添加了对 AES-GCM 和 AES-CCM 密码的支持，通过 `System.Security.Cryptography.AesGcm` 和 `System.Security.Cryptography.AesCcm` 实现。</span><span class="sxs-lookup"><span data-stu-id="833e1-331">Support has been added for **AES-GCM** and **AES-CCM** ciphers, implemented via `System.Security.Cryptography.AesGcm` and `System.Security.Cryptography.AesCcm`.</span></span> <span data-ttu-id="833e1-332">这些算法都是[使用关联数据的验证加密 (AEAD) 算法](https://en.wikipedia.org/wiki/Authenticated_encryption)，以及第一个添加到 .NET Core 的验证加密 (AE) 算法。</span><span class="sxs-lookup"><span data-stu-id="833e1-332">These algorithms are both [Authenticated Encryption with Association Data (AEAD) algorithms](https://en.wikipedia.org/wiki/Authenticated_encryption), and the first Authenticated Encryption (AE) algorithms added to .NET Core.</span></span>

<span data-ttu-id="833e1-333">下面的代码演示了如何使用 AesGcm 密码加密和解密随机数据。</span><span class="sxs-lookup"><span data-stu-id="833e1-333">The following code demonstrates using **AesGcm** cipher to encrypt and decrypt random data.</span></span>

<span data-ttu-id="833e1-334">AesCcm 代码几乎完全相同（仅类变量名称不同）。</span><span class="sxs-lookup"><span data-stu-id="833e1-334">The code for **AesCcm** would look almost identical (only the class variable names would be different).</span></span>

```csharp
// key should be: pre-known, derived, or transported via another channel, such as RSA encryption
byte[] key = new byte[16];
RandomNumberGenerator.Fill(key);

byte[] nonce = new byte[12];
RandomNumberGenerator.Fill(nonce);

// normally this would be your data
byte[] dataToEncrypt = new byte[1234];
byte[] associatedData = new byte[333];
RandomNumberGenerator.Fill(dataToEncrypt);
RandomNumberGenerator.Fill(associatedData);

// these will be filled during the encryption
byte[] tag = new byte[16];
byte[] ciphertext = new byte[dataToEncrypt.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Encrypt(nonce, dataToEncrypt, ciphertext, tag, associatedData);
}

// tag, nonce, ciphertext, associatedData should be sent to the other part

byte[] decryptedData = new byte[ciphertext.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Decrypt(nonce, ciphertext, tag, decryptedData, associatedData);
}

// do something with the data
// this should always print that data is the same
Console.WriteLine($"AES-GCM: Decrypted data is{(dataToEncrypt.SequenceEqual(decryptedData) ? "the same as" : "different than")} original data.");
```

## <a name="cryptographic-key-importexport"></a><span data-ttu-id="833e1-335">加密密钥导入/导出</span><span class="sxs-lookup"><span data-stu-id="833e1-335">Cryptographic Key Import/Export</span></span>

<span data-ttu-id="833e1-336">.NET Core 3.0 预览版 1 支持从标准格式导入和导出非对称公钥和私钥，而不需要使用 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="833e1-336">.NET Core 3.0 Preview 1 supports the import and export of asymmetric public and private keys from standard formats, without needing to use an X.509 certificate.</span></span>

<span data-ttu-id="833e1-337">所有密钥类型（RSA、DSA、ECDsa、ECDiffieHellman）都支持公钥的 X.509 SubjectPublicKeyInfo 格式，以及私钥的 PKCS#8 PrivateKeyInfo 和 PKCS#8 EncryptedPrivateKeyInfo 格式。</span><span class="sxs-lookup"><span data-stu-id="833e1-337">All key types (RSA, DSA, ECDsa, ECDiffieHellman) support the **X.509 SubjectPublicKeyInfo** format for public keys, and the **PKCS#8 PrivateKeyInfo** and **PKCS#8 EncryptedPrivateKeyInfo** formats for private keys.</span></span> <span data-ttu-id="833e1-338">RSA 此外还支持 PKCS#1 RSAPublicKey 和 PKCS#1 RSAPrivateKey。</span><span class="sxs-lookup"><span data-stu-id="833e1-338">RSA additionally supports **PKCS#1 RSAPublicKey** and **PKCS#1 RSAPrivateKey**.</span></span> <span data-ttu-id="833e1-339">所有导出方法都生成 DER 编码的二进制数据，导入方法也是如此。</span><span class="sxs-lookup"><span data-stu-id="833e1-339">The export methods all produce DER-encoded binary data, and the import methods expect the same.</span></span> <span data-ttu-id="833e1-340">如果密钥以文本友好的 PEM 格式存储，调用方需要在调用导入方法之前对内容进行 base64 解码。</span><span class="sxs-lookup"><span data-stu-id="833e1-340">If a key is stored in the text-friendly PEM format, the caller will need to base64-decode the content before calling an import method.</span></span>

```csharp
using System;
using System.IO;
using System.Security.Cryptography;

namespace rsakeyprint
{
    class Program
    {
        static void Main(string[] args)
        {
            using (RSA rsa = RSA.Create())
            {
                byte[] keyBytes = File.ReadAllBytes(args[0]);
                rsa.ImportRSAPrivateKey(keyBytes, out int bytesRead);
 
                Console.WriteLine($"Read {bytesRead} bytes, {keyBytes.Length-bytesRead} extra byte(s) in file.");
                RSAParameters rsaParameters = rsa.ExportParameters(true);
                Console.WriteLine(BitConverter.ToString(rsaParameters.D));
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/rsakeyprint$ echo Making a small key to save on screen space.
Making a small key to save on screen space.
user@comp-ubuntu1810:~/rsakeyprint$ openssl genrsa 768 | openssl rsa -outform der -out rsa.key
Generating RSA private key, 768 bit long modulus (2 primes)
..+++++++
........+++++++
e is 65537 (0x010001)
writing RSA key
user@comp-ubuntu1810:~/rsakeyprint$ dotnet run rsa.key
Read 461 bytes, 0 extra byte(s) in file.
0F-D0-82-34-F8-13-38-4A-7F-C7-52-4A-F6-93-F8-FB-6D-98-7A-6A-04-3B-BC-35-8C-7D-AC-A5-A3-6E-AD-C1-66-30-81-2C-2A-DE-DA-60-03-6A-2C-D9-76-15-7F-61-97-57-
79-E1-6E-45-62-C3-83-04-97-CB-32-EF-C5-17-5F-99-60-92-AE-B6-34-6F-30-06-03-AC-BF-15-24-43-84-EB-83-60-EF-4D-3B-BD-D9-5D-56-26-F0-51-CE-F1
user@comp-ubuntu1810:~/rsakeyprint$ openssl rsa -in rsa.key -inform der -text -noout | grep -A7 private
privateExponent:
    0f:d0:82:34:f8:13:38:4a:7f:c7:52:4a:f6:93:f8:
    fb:6d:98:7a:6a:04:3b:bc:35:8c:7d:ac:a5:a3:6e:
    ad:c1:66:30:81:2c:2a:de:da:60:03:6a:2c:d9:76:
    15:7f:61:97:57:79:e1:6e:45:62:c3:83:04:97:cb:
    32:ef:c5:17:5f:99:60:92:ae:b6:34:6f:30:06:03:
    ac:bf:15:24:43:84:eb:83:60:ef:4d:3b:bd:d9:5d:
    56:26:f0:51:ce:f1
```

<span data-ttu-id="833e1-341">可以使用 `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo` 类检查 PKCS#8 文件。</span><span class="sxs-lookup"><span data-stu-id="833e1-341">PKCS#8 files can be inspected with the `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo` class.</span></span>

<span data-ttu-id="833e1-342">可以分别使用 `System.Security.Cryptography.Pkcs.Pkcs12Info` 和 `System.Security.Cryptography.Pkcs.Pkcs12Builder` 检查和操作 PFX/PKCS#12 文件。</span><span class="sxs-lookup"><span data-stu-id="833e1-342">PFX/PKCS#12 files can be inspected and manipulated with `System.Security.Cryptography.Pkcs.Pkcs12Info` and `System.Security.Cryptography.Pkcs.Pkcs12Builder`, respectively.</span></span>

## <a name="serialport-for-linux"></a><span data-ttu-id="833e1-343">适用于 Linux 的 SerialPort</span><span class="sxs-lookup"><span data-stu-id="833e1-343">SerialPort for Linux</span></span>

<span data-ttu-id="833e1-344">.NET Core 3.0 现在在 Linux 上支持 <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="833e1-344">.NET Core 3.0 now supports <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> on Linux.</span></span>

<span data-ttu-id="833e1-345">以前，.NET Core 只支持在 Windows 上使用 `SerialPort` 类型。</span><span class="sxs-lookup"><span data-stu-id="833e1-345">Previously, .NET Core only supported using the `SerialPort` type on Windows.</span></span>

## <a name="more-bcl-improvements"></a><span data-ttu-id="833e1-346">更多的 BCL 改进</span><span class="sxs-lookup"><span data-stu-id="833e1-346">More BCL Improvements</span></span>

<span data-ttu-id="833e1-347">.NET Core 2.1 中引入的 `Span<T>`、`Memory<T>` 和相关类型已在 .NET Core 3.0 中优化。</span><span class="sxs-lookup"><span data-stu-id="833e1-347">The `Span<T>`, `Memory<T>`, and related types that were introduced in .NET Core 2.1, have been optimized in .NET Core 3.0.</span></span> <span data-ttu-id="833e1-348">常见操作（例如跨越构造、切片、分析和格式化）现在可以更好地执行。</span><span class="sxs-lookup"><span data-stu-id="833e1-348">Common operations such as span construction, slicing, parsing, and formatting now perform better.</span></span> 

<span data-ttu-id="833e1-349">此外，像 `String` 这样的类型已经看到了一些潜在的改进，使它们在与 `Dictionary<TKey, TValue>` 和其他集合一起用作键时更有效。</span><span class="sxs-lookup"><span data-stu-id="833e1-349">Additionally, types like `String` have seen under-the-cover improvements to make them more efficient when used as keys with `Dictionary<TKey, TValue>` and other collections.</span></span> <span data-ttu-id="833e1-350">不需要更改代码就可以从这些改进中获益。</span><span class="sxs-lookup"><span data-stu-id="833e1-350">No code changes are required to benefit from these improvements.</span></span>

<span data-ttu-id="833e1-351">以下改进也是 .NET Core 3 预览版 1 中的新增功能：</span><span class="sxs-lookup"><span data-stu-id="833e1-351">The following improvements are also new in .NET Core 3 Preview 1:</span></span>

* <span data-ttu-id="833e1-352">内置于 HttpClient 的 Brotli 支持</span><span class="sxs-lookup"><span data-stu-id="833e1-352">Brotli support built in to HttpClient</span></span>
* <span data-ttu-id="833e1-353">ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)</span><span class="sxs-lookup"><span data-stu-id="833e1-353">ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)</span></span>
* <span data-ttu-id="833e1-354">Unsafe.Unbox</span><span class="sxs-lookup"><span data-stu-id="833e1-354">Unsafe.Unbox</span></span>
* <span data-ttu-id="833e1-355">CancellationToken.Unregister</span><span class="sxs-lookup"><span data-stu-id="833e1-355">CancellationToken.Unregister</span></span>
* <span data-ttu-id="833e1-356">复杂算术运算符</span><span class="sxs-lookup"><span data-stu-id="833e1-356">Complex arithmetic operators</span></span>
* <span data-ttu-id="833e1-357">TCP 套接字 API 保持活动状态</span><span class="sxs-lookup"><span data-stu-id="833e1-357">Socket APIs for TCP keep alive</span></span>
* <span data-ttu-id="833e1-358">StringBuilder.GetChunks</span><span class="sxs-lookup"><span data-stu-id="833e1-358">StringBuilder.GetChunks</span></span>
* <span data-ttu-id="833e1-359">IPEndPoint 分析</span><span class="sxs-lookup"><span data-stu-id="833e1-359">IPEndPoint parsing</span></span>
* <span data-ttu-id="833e1-360">RandomNumberGenerator.GetInt32</span><span class="sxs-lookup"><span data-stu-id="833e1-360">RandomNumberGenerator.GetInt32</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="833e1-361">分层编译</span><span class="sxs-lookup"><span data-stu-id="833e1-361">Tiered compilation</span></span>

<span data-ttu-id="833e1-362">仅在 .NET Core 3.0 中默认启用[分层编译](https://blogs.msdn.microsoft.com/dotnet/2018/08/02/tiered-compilation-preview-in-net-core-2-1/)。</span><span class="sxs-lookup"><span data-stu-id="833e1-362">[Tiered compilation](https://blogs.msdn.microsoft.com/dotnet/2018/08/02/tiered-compilation-preview-in-net-core-2-1/) is on by default with .NET Core 3.0.</span></span> <span data-ttu-id="833e1-363">它是一项功能，使运行时能够更适应地使用实时 (JIT) 编译器，从而在启动时获得更好的性能，并最大限度地提高吞吐量。</span><span class="sxs-lookup"><span data-stu-id="833e1-363">It is a feature that enables the runtime to more adaptively use the Just-In-Time (JIT) compiler to get better performance, both at startup and to maximize throughput.</span></span>

<span data-ttu-id="833e1-364">此功能已作为一项可选功能添加到 [.NET Core 2.1](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/)，然后在 [.NET Core 2.2 预览版 2](https://blogs.msdn.microsoft.com/dotnet/2018/09/12/announcing-net-core-2-2-preview-2/) 中默认启用。</span><span class="sxs-lookup"><span data-stu-id="833e1-364">This feature was added as an opt-in feature in [.NET Core 2.1](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) and then was enabled by default in [.NET Core 2.2 Preview 2](https://blogs.msdn.microsoft.com/dotnet/2018/09/12/announcing-net-core-2-2-preview-2/).</span></span> <span data-ttu-id="833e1-365">随后，它在 .NET Core 2.2 版本中还原回可选功能。</span><span class="sxs-lookup"><span data-stu-id="833e1-365">Subsequently, it has been reverted back to opt in with the .NET Core 2.2 release.</span></span>

## <a name="arm64-linux-support"></a><span data-ttu-id="833e1-366">ARM64 Linux 支持</span><span class="sxs-lookup"><span data-stu-id="833e1-366">ARM64 Linux support</span></span>

<span data-ttu-id="833e1-367">添加了适用于 Linux 的 ARM64 支持。</span><span class="sxs-lookup"><span data-stu-id="833e1-367">Support has been added for ARM64 for Linux.</span></span> <span data-ttu-id="833e1-368">ARM64 的主要用例是当前的 IoT 场景。</span><span class="sxs-lookup"><span data-stu-id="833e1-368">The primary use case for ARM64 is currently with IoT scenarios.</span></span>

<span data-ttu-id="833e1-369">Alpine、Debian 和 Ubuntu [Docker 映像均适用于 .NET Core for ARM64](https://hub.docker.com/r/microsoft/dotnet/)。</span><span class="sxs-lookup"><span data-stu-id="833e1-369">Alpine, Debian and Ubuntu [Docker images are available for .NET Core for ARM64](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

<span data-ttu-id="833e1-370">有关详细信息，请查看 [.NET Core ARM64 状态](https://github.com/dotnet/announcements/issues/82)。</span><span class="sxs-lookup"><span data-stu-id="833e1-370">Please check [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82) for more information.</span></span>

>[!NOTE]
> <span data-ttu-id="833e1-371">**ARM64** 尚未提供 Windows 支持。</span><span class="sxs-lookup"><span data-stu-id="833e1-371">**ARM64** Windows support isn't yet available.</span></span>

## <a name="install-net-core-30-previews-on-linux-with-snap"></a><span data-ttu-id="833e1-372">通过 Snap 在 Linux 上安装 .NET Core 3.0 预览版</span><span class="sxs-lookup"><span data-stu-id="833e1-372">Install .NET Core 3.0 Previews on Linux with Snap</span></span>

<span data-ttu-id="833e1-373">Snap 是在[支持 Snap 的 Linux 分发](https://docs.snapcraft.io/installing-snapd/6735)上安装和试用 .NET Core 预览版的首选方式。</span><span class="sxs-lookup"><span data-stu-id="833e1-373">Snap is the preferred way to install and try .NET Core previews on [Linux distributions that support Snap](https://docs.snapcraft.io/installing-snapd/6735).</span></span>

<span data-ttu-id="833e1-374">在系统上配置 Snap 后，运行以下命令安装 [.NET Core SDK 3.0 预览版 SDK](https://snapcraft.io/dotnet-sdk)。</span><span class="sxs-lookup"><span data-stu-id="833e1-374">After configuring Snap on your system, run the following command to install the [.NET Core SDK 3.0 Preview SDK](https://snapcraft.io/dotnet-sdk).</span></span>

```console
sudo snap install dotnet-sdk --beta --classic
```
 
<span data-ttu-id="833e1-375">如果使用 Snap 包安装 .NET Core，则默认的 .NET Core 命令为 `dotnet-sdk.dotnet`，而不是直接的 `dotnet`。</span><span class="sxs-lookup"><span data-stu-id="833e1-375">When .NET Core in installed using the Snap package, the default .NET Core command is `dotnet-sdk.dotnet`, as opposed to just `dotnet`.</span></span> <span data-ttu-id="833e1-376">命名空间命令的好处是，不会与全局安装的 .NET Core 版本发生冲突。</span><span class="sxs-lookup"><span data-stu-id="833e1-376">The benefit of the namespaced command is that it will not conflict with a globally installed .NET Core version you may have.</span></span> <span data-ttu-id="833e1-377">此命令可以使用以下命令化名为 `dotnet`：</span><span class="sxs-lookup"><span data-stu-id="833e1-377">This command can be aliased to `dotnet` with:</span></span>

```console
sudo snap alias dotnet-sdk.dotnet dotnet
```

<span data-ttu-id="833e1-378">某些发行版需要执行额外步骤来实现对 SSL 证书的访问。</span><span class="sxs-lookup"><span data-stu-id="833e1-378">Some distros require an additional step to enable access to the SSL certificate.</span></span> <span data-ttu-id="833e1-379">请参阅 [Linux 安装程序](https://github.com/dotnet/core/blob/master/Documentation/linux-setup.md)，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="833e1-379">See our [Linux Setup](https://github.com/dotnet/core/blob/master/Documentation/linux-setup.md) for details.</span></span>

## <a name="gpio-support-for-raspberry-pi"></a><span data-ttu-id="833e1-380">对 Raspberry Pi 的 GPIO 支持</span><span class="sxs-lookup"><span data-stu-id="833e1-380">GPIO Support for Raspberry Pi</span></span>

<span data-ttu-id="833e1-381">已向 NuGet 发布了两个新的程序包，可用于 GPIO 编程。</span><span class="sxs-lookup"><span data-stu-id="833e1-381">Two new packages have been released to NuGet that you can use for GPIO programming.</span></span>

* [<span data-ttu-id="833e1-382">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="833e1-382">System.Device.Gpio</span></span>](https://www.nuget.org/packages/System.Device.Gpio/0.1.0-prerelease.19078.2)
* [<span data-ttu-id="833e1-383">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="833e1-383">Iot.Device.Bindings</span></span>](https://www.nuget.org/packages/Iot.Device.Bindings/0.1.0-prerelease.19078.2)

<span data-ttu-id="833e1-384">GPIO 包包括用于 GPIO、SPI、I2C 和 PWM 设备的 API。</span><span class="sxs-lookup"><span data-stu-id="833e1-384">The GPIO Packages includes APIs for GPIO, SPI, I2C and PWM devices.</span></span> <span data-ttu-id="833e1-385">IoT 绑定包包括针对各种芯片和传感器的[设备绑定](https://github.com/dotnet/iot/blob/master/src/devices/README.md)，与 [dotnet/iot - src/devices](https://github.com/dotnet/iot/tree/master/src/devices) 提供的相同。</span><span class="sxs-lookup"><span data-stu-id="833e1-385">The IoT bindings package includes [device bindings](https://github.com/dotnet/iot/blob/master/src/devices/README.md) for various chips and sensors, the same ones available at [dotnet/iot - src/devices](https://github.com/dotnet/iot/tree/master/src/devices).</span></span>

<span data-ttu-id="833e1-386">这些包中不包含作为 .NET Core 3.0 预览版 1 一部分的已更新的串行端口 API，但这些 API 可作为 .NET Core 平台的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="833e1-386">The updated serial port APIs that were announced as part of .NET Core 3.0 Preview 1 are not part of these packages but are available as part of the .NET Core platform.</span></span>


## <a name="platform-support"></a><span data-ttu-id="833e1-387">平台支持</span><span class="sxs-lookup"><span data-stu-id="833e1-387">Platform Support</span></span>

<span data-ttu-id="833e1-388">以下操作系统支持 .NET Core 3：</span><span class="sxs-lookup"><span data-stu-id="833e1-388">.NET Core 3 will be supported on the following operating systems:</span></span>

* <span data-ttu-id="833e1-389">Windows 客户端：7、8.1、10（1607 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="833e1-389">Windows Client: 7, 8.1, 10 (1607+)</span></span>
* <span data-ttu-id="833e1-390">Windows Server：2012 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="833e1-390">Windows Server: 2012 R2 SP1+</span></span>
* <span data-ttu-id="833e1-391">macOS：10.12+</span><span class="sxs-lookup"><span data-stu-id="833e1-391">macOS: 10.12+</span></span>
* <span data-ttu-id="833e1-392">RHEL：6+</span><span class="sxs-lookup"><span data-stu-id="833e1-392">RHEL: 6+</span></span>
* <span data-ttu-id="833e1-393">Fedora：26+</span><span class="sxs-lookup"><span data-stu-id="833e1-393">Fedora: 26+</span></span>
* <span data-ttu-id="833e1-394">Ubuntu：16.04+</span><span class="sxs-lookup"><span data-stu-id="833e1-394">Ubuntu: 16.04+</span></span>
* <span data-ttu-id="833e1-395">Debian：9+</span><span class="sxs-lookup"><span data-stu-id="833e1-395">Debian: 9+</span></span>
* <span data-ttu-id="833e1-396">SLES：12+</span><span class="sxs-lookup"><span data-stu-id="833e1-396">SLES: 12+</span></span>
* <span data-ttu-id="833e1-397">openSUSE：42.3+</span><span class="sxs-lookup"><span data-stu-id="833e1-397">openSUSE: 42.3+</span></span>
* <span data-ttu-id="833e1-398">Alpine：3.8+</span><span class="sxs-lookup"><span data-stu-id="833e1-398">Alpine: 3.8+</span></span>

<span data-ttu-id="833e1-399">芯片支持如下所示：</span><span class="sxs-lookup"><span data-stu-id="833e1-399">Chip support follows:</span></span>

* <span data-ttu-id="833e1-400">Windows、macOS 和 Linux 上的 x64</span><span class="sxs-lookup"><span data-stu-id="833e1-400">x64 on Windows, macOS, and Linux</span></span>
* <span data-ttu-id="833e1-401">Windows 上的 x86</span><span class="sxs-lookup"><span data-stu-id="833e1-401">x86 on Windows</span></span>
* <span data-ttu-id="833e1-402">Windows 和 Linux 上的 ARM32</span><span class="sxs-lookup"><span data-stu-id="833e1-402">ARM32 on Windows and Linux</span></span>
* <span data-ttu-id="833e1-403">Linux 上的 ARM64</span><span class="sxs-lookup"><span data-stu-id="833e1-403">ARM64 on Linux</span></span>

<span data-ttu-id="833e1-404">对于 Linux，ARM32 在 Debian 9+ 和 Ubuntu 16.04+ 上受支持。</span><span class="sxs-lookup"><span data-stu-id="833e1-404">For Linux, ARM32 is supported on Debian 9+ and Ubuntu 16.04+.</span></span> <span data-ttu-id="833e1-405">对于 ARM64，它与 ARM32 搭载 Alpine 3.8 等效。</span><span class="sxs-lookup"><span data-stu-id="833e1-405">For ARM64, it is the same as ARM32 with the addition of Alpine 3.8.</span></span> <span data-ttu-id="833e1-406">这些版本与支持 X64 的发行版相同。</span><span class="sxs-lookup"><span data-stu-id="833e1-406">These are the same versions of those distros as is supported for X64.</span></span>

<span data-ttu-id="833e1-407">[Docker 中心的 microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) 提供适用于 .NET Core 3.0 的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="833e1-407">Docker images for .NET Core 3.0 are available at [microsoft/dotnet on Docker Hub](https://hub.docker.com/r/microsoft/dotnet/).</span></span> <span data-ttu-id="833e1-408">Microsoft 目前正在采用 [Microsoft 容器注册表 (MCR)](https://cloudblogs.microsoft.com/opensource/2019/01/17/improved-discovery-experience-microsoft-containers-docker-hub/)，预计最终的 .NET Core 3.0 映像将仅发布到 MCR。</span><span class="sxs-lookup"><span data-stu-id="833e1-408">Microsoft is currently in the process of adopting [Microsoft Container Registry (MCR)](https://cloudblogs.microsoft.com/opensource/2019/01/17/improved-discovery-experience-microsoft-containers-docker-hub/) and it is expected that the final .NET Core 3.0 images will only be published to MCR.</span></span>
