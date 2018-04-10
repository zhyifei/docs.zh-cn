---
title: C# 中的新增功能 - C# 指南
description: C# 语言是如何不断发展的
keywords: C#, 最新功能, 新增功能, Roslyn
author: BillWagner
ms.author: wiwagn
ms.date: 11/13/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 77deec51-a14d-46d4-9bb3-faf449477149
ms.openlocfilehash: 719fbe826b0b115b19067dbaf0d04f14e6534890
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="whats-new-in-c"></a><span data-ttu-id="39680-104">C# 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="39680-104">What's new in C#</span></span> #

<span data-ttu-id="39680-105">本页介绍了 C# 语言每个主要版本中新增功能的路线图。</span><span class="sxs-lookup"><span data-stu-id="39680-105">This page provides a roadmap of new features in each major release of the C# language.</span></span> <span data-ttu-id="39680-106">若要详细了解每个版本中增加的主要功能，请单击下面的链接。</span><span class="sxs-lookup"><span data-stu-id="39680-106">The following links provide detailed information on the major features added in each release.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="39680-107">为了提供一些功能，C# 语言依赖标准库中的类型和方法。</span><span class="sxs-lookup"><span data-stu-id="39680-107">The C# language relies on types and methods in a *standard library* for some of the features.</span></span> <span data-ttu-id="39680-108">例如，异常处理。</span><span class="sxs-lookup"><span data-stu-id="39680-108">One example is exception processing.</span></span> <span data-ttu-id="39680-109">为了确保引发的对象派生自 <xref:System.Exception>，将会检查每个 `throw` 语句或表达式。</span><span class="sxs-lookup"><span data-stu-id="39680-109">Every `throw` statement or expression is checked to ensure the object being thrown is derived from <xref:System.Exception>.</span></span> <span data-ttu-id="39680-110">同样，还会检查每个 `catch`，以确保捕获的类型派生自 <xref:System.Exception>。</span><span class="sxs-lookup"><span data-stu-id="39680-110">Similarly, every `catch` is checked to ensure that the type being caught is derived from <xref:System.Exception>.</span></span> <span data-ttu-id="39680-111">每个版本都可能会新增要求。</span><span class="sxs-lookup"><span data-stu-id="39680-111">Each version may add new requirements.</span></span> <span data-ttu-id="39680-112">若要在旧版环境中使用最新语言功能，可能需要安装特定库。</span><span class="sxs-lookup"><span data-stu-id="39680-112">To use the latest language features in older environments, you may need to install specific libraries.</span></span> <span data-ttu-id="39680-113">每个特定版本的页面中记录了这些依赖项。</span><span class="sxs-lookup"><span data-stu-id="39680-113">These dependencies are documented in the page for each specific version.</span></span> <span data-ttu-id="39680-114">若要了解此依赖项的背景信息，可以详细了解[语言与库的关系](relationships-between-language-and-library.md)。</span><span class="sxs-lookup"><span data-stu-id="39680-114">You can learn more about the [relationships between language and library](relationships-between-language-and-library.md) for background on this dependency.</span></span> 


* <span data-ttu-id="39680-115">[C# 7.2](csharp-7-2.md)：</span><span class="sxs-lookup"><span data-stu-id="39680-115">[C# 7.2](csharp-7-2.md):</span></span>
    - <span data-ttu-id="39680-116">此页介绍了 C# 语言的最新功能。</span><span class="sxs-lookup"><span data-stu-id="39680-116">This page describes the latest features in the C# language.</span></span> <span data-ttu-id="39680-117">C# 7.2 目前在 [Visual Studio 2017 版本 15.5](https://www.visualstudio.com/vs/whatsnew/), 和 [.NET Core 2.0 SDK](../../core/whats-new/index.md) 中可用。</span><span class="sxs-lookup"><span data-stu-id="39680-117">C# 7.2 is currently available in [Visual Studio 2017 version 15.5](https://www.visualstudio.com/vs/whatsnew/), and in the [.NET Core 2.0 SDK](../../core/whats-new/index.md).</span></span>

* <span data-ttu-id="39680-118">[C# 7.1](csharp-7-1.md)：</span><span class="sxs-lookup"><span data-stu-id="39680-118">[C# 7.1](csharp-7-1.md):</span></span>
    - <span data-ttu-id="39680-119">本页介绍 C# 7.1 中的功能。</span><span class="sxs-lookup"><span data-stu-id="39680-119">This page describes the features in C# 7.1.</span></span> <span data-ttu-id="39680-120">[Visual Studio 2017 版本 15.3](https://www.visualstudio.com/vs/whatsnew/), 和 [.NET Core 2.0 SDK](../../core/whats-new/index.md) 中增加了这些功能。</span><span class="sxs-lookup"><span data-stu-id="39680-120">These features were added in [Visual Studio 2017 version 15.3](https://www.visualstudio.com/vs/whatsnew/), and in the [.NET Core 2.0 SDK](../../core/whats-new/index.md).</span></span>

* <span data-ttu-id="39680-121">[C# 7](csharp-7.md)：</span><span class="sxs-lookup"><span data-stu-id="39680-121">[C# 7](csharp-7.md):</span></span>
    - <span data-ttu-id="39680-122">此页介绍 C# 7 中添加的功能。</span><span class="sxs-lookup"><span data-stu-id="39680-122">This page describes the features added in C# 7.</span></span> <span data-ttu-id="39680-123">[Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) 和 [.NET Core 1.0](../../core/whats-new/index.md) 及更高版本中增加了这些功能。</span><span class="sxs-lookup"><span data-stu-id="39680-123">These features were added in [Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) and [.NET Core 1.0](../../core/whats-new/index.md) and later</span></span>
     
* <span data-ttu-id="39680-124">[C# 6](csharp-6.md)：</span><span class="sxs-lookup"><span data-stu-id="39680-124">[C# 6](csharp-6.md):</span></span>
    - <span data-ttu-id="39680-125">此页介绍 C# 6 中添加的功能。</span><span class="sxs-lookup"><span data-stu-id="39680-125">This page describes the features that were added in C# 6.</span></span> <span data-ttu-id="39680-126">这些功能可供 Windows 开发者在 Visual Studio 2015 中使用，并可供开发者在 macOS 和 Linux 上的 .NET Core 1.0 中探索 C# 时使用。</span><span class="sxs-lookup"><span data-stu-id="39680-126">These features are available in Visual Studio 2015 for Windows developers, and on .NET Core 1.0 for developers exploring C# on macOS and Linux.</span></span>

<!--* [C# Interactive](../interactive/index.md): 
    - This page describes C# Interactive, an interactive Read Eval Print Loop (REPL) that you can use to explore the C# language. You can use it to write code interactively and see it execute immediately, without any compile or build step.
-->
* <span data-ttu-id="39680-127">[跨平台支持](../../core/index.md)：</span><span class="sxs-lookup"><span data-stu-id="39680-127">[Cross Platform Support](../../core/index.md):</span></span>
    - <span data-ttu-id="39680-128">借助 .NET Core 支持，C# 可以在多个平台上运行。</span><span class="sxs-lookup"><span data-stu-id="39680-128">C#, through .NET Core support, runs on multiple platforms.</span></span> <span data-ttu-id="39680-129">如果希望在 macOS 或众多受支持的 Linux 发行版上使用 C#，请了解有关 .NET Core 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="39680-129">If you are interested in trying C# on macOS, or on one of the many supported Linux distributions, learn more about .NET Core.</span></span>

<!--
- [.NET Compiler Platform SDK](../roslyn/index.md):
    - The .NET Compiler Platform SDK enables you to write code that performs static analysis on C# code. You can use these APIs to find potential errors, or bad practices, suggest fixes, and even implement those fixes.
-->
  
## <a name="previous-versions"></a><span data-ttu-id="39680-130">早期版本</span><span class="sxs-lookup"><span data-stu-id="39680-130">Previous Versions</span></span>
<span data-ttu-id="39680-131">下面列出了在以前版本的 C# 语言和 Visual Studio.NET 中引入的主要功能。</span><span class="sxs-lookup"><span data-stu-id="39680-131">The following lists key features that were introduced in previous versions of the C# language and Visual Studio .NET.</span></span>  
  
 * <span data-ttu-id="39680-132">Visual Studio .NET 2013：</span><span class="sxs-lookup"><span data-stu-id="39680-132">Visual Studio .NET 2013:</span></span> 
     - <span data-ttu-id="39680-133">此版本的 Visual Studio 包含 .NET 编译器平台（“Roslyn”）的 Bug 修复、性能改进和技术预览，Roslyn 是 .NET 编译器平台 SDK 的前身<!--Link to ../roslyn/index.md-->。</span><span class="sxs-lookup"><span data-stu-id="39680-133">This version of Visual Studio included bug fixes, performance improvements, and technology previews of .NET Compiler Platform ("Roslyn") which became the .NET Compiler Platform SDK<!--Link to ../roslyn/index.md-->.</span></span>

 * <span data-ttu-id="39680-134">C# 5，Visual Studio .NET 2012：</span><span class="sxs-lookup"><span data-stu-id="39680-134">C# 5, Visual Studio .NET 2012:</span></span> 
     - <span data-ttu-id="39680-135">`Async` / `await` 和[调用方信息](../programming-guide/concepts/caller-information.md)特性。</span><span class="sxs-lookup"><span data-stu-id="39680-135">`Async` / `await`, and [caller information](../programming-guide/concepts/caller-information.md) attributes.</span></span>

 * <span data-ttu-id="39680-136">C# 4，Visual Studio .NET 2010：</span><span class="sxs-lookup"><span data-stu-id="39680-136">C# 4, Visual Studio .NET 2010:</span></span> 
     - <span data-ttu-id="39680-137">`Dynamic`、[命名自变量](../programming-guide/classes-and-structs/named-and-optional-arguments.md)、可选参数、泛型[协变和逆变](../programming-guide/concepts/covariance-contravariance/index.md)。</span><span class="sxs-lookup"><span data-stu-id="39680-137">`Dynamic`, [named arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md), optional parameters, and generic [covariance and contra variance](../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

 * <span data-ttu-id="39680-138">C# 3，Visual Studio .NET 2008：</span><span class="sxs-lookup"><span data-stu-id="39680-138">C# 3, Visual Studio .NET 2008:</span></span> 
     - <span data-ttu-id="39680-139">对象和集合初始值设定项、lambda 表达式、扩展方法、匿名类型、自动属性、本地 `var` 类型推理和[语言集成查询 (LINQ)](../programming-guide/concepts/linq/index.md)。</span><span class="sxs-lookup"><span data-stu-id="39680-139">Object and collection initializers, lambda expressions, extension methods, anonymous types, automatic properties, local `var` type inference, and [Language Integrated Query (LINQ)](../programming-guide/concepts/linq/index.md).</span></span>

 * <span data-ttu-id="39680-140">C# 2，Visual Studio .NET 2005：</span><span class="sxs-lookup"><span data-stu-id="39680-140">C# 2, Visual Studio .NET 2005:</span></span> 
     - <span data-ttu-id="39680-141">匿名方法、泛型、可以为 null 的类型、迭代器/yield、`static` 类、委托的协变和逆变。</span><span class="sxs-lookup"><span data-stu-id="39680-141">Anonymous methods, generics, nullable types, iterators/yield, `static` classes, and covariance and contra variance for delegates.</span></span>

 * <span data-ttu-id="39680-142">C# 1.1，Visual Studio .NET 2003：</span><span class="sxs-lookup"><span data-stu-id="39680-142">C# 1.1, Visual Studio .NET 2003:</span></span> 
     - <span data-ttu-id="39680-143">`#line` 杂注和 xml 文档注释。</span><span class="sxs-lookup"><span data-stu-id="39680-143">`#line` pragma and xml doc comments.</span></span>

 * <span data-ttu-id="39680-144">C# 1，Visual Studio .NET 2002：</span><span class="sxs-lookup"><span data-stu-id="39680-144">C# 1, Visual Studio .NET 2002:</span></span> 
     - <span data-ttu-id="39680-145">[C#](../csharp.md) 初版。</span><span class="sxs-lookup"><span data-stu-id="39680-145">The first release of [C#](../csharp.md).</span></span>   
