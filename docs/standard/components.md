---
title: ".NET 体系结构组件"
description: "描述 .NET 体系结构组件，例如 .NET Standard、.NET 实现和工具。"
keywords: ".NET, .NET Standard, .NET Core, .NET Framework, Xamarin, MSBuild, C#, F#, VB, 编译器"
author: cartermp
ms.author: mairaw
ms.date: 08/10/2017
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 2e38e9d9-8284-46ee-a15f-199adc4f26f4
ms.translationtype: HT
ms.sourcegitcommit: 14522f165b22a7b1bb2a717a7c9f293a265f4eb0
ms.openlocfilehash: 8934febe77b30fb318b06e4d8d297282368438a5
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---

# <a name="net-architectural-components"></a><span data-ttu-id="52bb1-104">.NET 体系结构组件</span><span class="sxs-lookup"><span data-stu-id="52bb1-104">.NET architectural components</span></span>

<span data-ttu-id="52bb1-105">.NET 应用开发用于并运行于一个或多个 .NET 实现。</span><span class="sxs-lookup"><span data-stu-id="52bb1-105">A .NET app is developed for and runs in one or more *implementations of .NET*.</span></span>  <span data-ttu-id="52bb1-106">.NET 实现包括 .NET Framework、.NET Core 和 Mono。</span><span class="sxs-lookup"><span data-stu-id="52bb1-106">Implementations of .NET include the .NET Framework, .NET Core, and Mono.</span></span> <span data-ttu-id="52bb1-107">.NET 的所有实现都有一个名为 .NET Standard 的通用 API 规范。</span><span class="sxs-lookup"><span data-stu-id="52bb1-107">There is an API specification common to all implementations of .NET that's called the .NET Standard.</span></span> <span data-ttu-id="52bb1-108">本文简要介绍了每个概念。</span><span class="sxs-lookup"><span data-stu-id="52bb1-108">This article gives a brief introduction to each of these concepts.</span></span>

## <a name="net-standard"></a><span data-ttu-id="52bb1-109">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="52bb1-109">.NET Standard</span></span>

<span data-ttu-id="52bb1-110">.NET Standard 是一组由 .NET 实现的基类库实现的 API。</span><span class="sxs-lookup"><span data-stu-id="52bb1-110">The .NET Standard is a set of APIs that are implemented by the Base Class Library of a .NET implementation.</span></span> <span data-ttu-id="52bb1-111">更正式地说，它是构成协定统一集（这些协定是编写代码的依据）的特定 .NET API 组。</span><span class="sxs-lookup"><span data-stu-id="52bb1-111">More formally, it's a specification of .NET APIs that make up a uniform set of contracts that you compile your code against.</span></span> <span data-ttu-id="52bb1-112">这些协定在每个 .NET 实现中实现。</span><span class="sxs-lookup"><span data-stu-id="52bb1-112">These contracts are implemented in each .NET implementation.</span></span> <span data-ttu-id="52bb1-113">这可实现不同 .NET 实现间的可移植性，有效地使代码可在任何位置运行。</span><span class="sxs-lookup"><span data-stu-id="52bb1-113">This enables portability across different .NET implementations, effectively allowing your code to run everywhere.</span></span>

<span data-ttu-id="52bb1-114">.NET Standard 也是一个[目标框架](glossary.md#target-framework)。</span><span class="sxs-lookup"><span data-stu-id="52bb1-114">The .NET Standard is also a [target framework](glossary.md#target-framework).</span></span> <span data-ttu-id="52bb1-115">如果代码面向 .NET Standard 版本，则它可在支持该 .NET Standard 版本的任何 .NET 实现上运行。</span><span class="sxs-lookup"><span data-stu-id="52bb1-115">If your code targets a version of the .NET Standard, it can run on any .NET implementation which supports that version of the .NET Standard.</span></span>

<span data-ttu-id="52bb1-116">若要详细了解 .NET Standard 以及如何将其作为目标，请参阅 [.NET Standard](net-standard.md) 主题。</span><span class="sxs-lookup"><span data-stu-id="52bb1-116">To learn more about the .NET Standard and how to target it, see the [.NET Standard](net-standard.md) topic.</span></span>

## <a name="net-implementations"></a><span data-ttu-id="52bb1-117">.NET 实现</span><span class="sxs-lookup"><span data-stu-id="52bb1-117">.NET implementations</span></span>

<span data-ttu-id="52bb1-118">.NET 的每个实现都具有以下组件：</span><span class="sxs-lookup"><span data-stu-id="52bb1-118">Each implementation of .NET includes the following components:</span></span>

- <span data-ttu-id="52bb1-119">一个或多个运行时。</span><span class="sxs-lookup"><span data-stu-id="52bb1-119">One or more runtimes.</span></span> <span data-ttu-id="52bb1-120">示例：用于 .NET Framework 的 CLR、CoreCLR 和用于 .NET Core 的 CoreRT。</span><span class="sxs-lookup"><span data-stu-id="52bb1-120">Examples: CLR for .NET Framework, CoreCLR and CoreRT for .NET Core.</span></span>
- <span data-ttu-id="52bb1-121">实现 .NET Standard 并且可实现其他 API 的类库。</span><span class="sxs-lookup"><span data-stu-id="52bb1-121">A class library that implements the .NET Standard and may implement additional APIs.</span></span> <span data-ttu-id="52bb1-122">示例：.NET Framework 基类库、.NET Core 基类库。</span><span class="sxs-lookup"><span data-stu-id="52bb1-122">Examples: .NET Framework Base Class Library, .NET Core Base Class Library.</span></span>
- <span data-ttu-id="52bb1-123">可选择包含一个或多个应用程序框架。</span><span class="sxs-lookup"><span data-stu-id="52bb1-123">Optionally, one or more application frameworks.</span></span> <span data-ttu-id="52bb1-124">示例： [ASP.NET](https://www.asp.net/)、[Windows 窗体](../framework/winforms/windows-forms-overview.md)和 [Windows Presentation Foundation (WPF)](../framework/wpf/index.md) 包含在 .NET Framework 中。</span><span class="sxs-lookup"><span data-stu-id="52bb1-124">Examples: [ASP.NET](https://www.asp.net/), [Windows Forms](../framework/winforms/windows-forms-overview.md), and [Windows Presentation Foundation (WPF)](../framework/wpf/index.md) are included in the .NET Framework.</span></span>
- <span data-ttu-id="52bb1-125">可包含开发工具。</span><span class="sxs-lookup"><span data-stu-id="52bb1-125">Optionally, development tools.</span></span> <span data-ttu-id="52bb1-126">某些开发工具在多个实现之间共享。</span><span class="sxs-lookup"><span data-stu-id="52bb1-126">Some development tools are shared among multiple implementations.</span></span>

<span data-ttu-id="52bb1-127">Microsoft 积极开发和维护的主要 .NET 实现有 4 个：.NET Core、.NET Framework、Mono 和 UWP。</span><span class="sxs-lookup"><span data-stu-id="52bb1-127">There are four primary .NET implementations that Microsoft actively develops and maintains: .NET Core, .NET Framework, Mono, and UWP.</span></span>

### <a name="net-core"></a><span data-ttu-id="52bb1-128">.NET 核心</span><span class="sxs-lookup"><span data-stu-id="52bb1-128">.NET Core</span></span>

<span data-ttu-id="52bb1-129">.NET Core 是一个经优化用于服务器工作负荷的跨平台实现。</span><span class="sxs-lookup"><span data-stu-id="52bb1-129">.NET Core is a cross-platform implementation of .NET optimized for server workloads.</span></span> <span data-ttu-id="52bb1-130">它新式、高效，专用于处理大规模的服务器和云工作负荷。</span><span class="sxs-lookup"><span data-stu-id="52bb1-130">It's modern, efficient, and designed to handle server and cloud workloads at scale.</span></span> <span data-ttu-id="52bb1-131">它实现 .NET Standard，因此面向 .NET Standard 的代码都可在 .NET Core 上运行。</span><span class="sxs-lookup"><span data-stu-id="52bb1-131">It implements the .NET Standard, so code that targets the .NET Standard can run on .NET Core.</span></span> <span data-ttu-id="52bb1-132">ASP.NET Core 在 .NET Core 上运行。</span><span class="sxs-lookup"><span data-stu-id="52bb1-132">ASP.NET Core runs on .NET Core.</span></span>

<span data-ttu-id="52bb1-133">若要了解有关 .NET Core 的详细信息，请参阅 [.NET Core 指南](../core/index.md)。</span><span class="sxs-lookup"><span data-stu-id="52bb1-133">To learn more about .NET Core, see the [.NET Core Guide](../core/index.md).</span></span>

### <a name="net-framework"></a><span data-ttu-id="52bb1-134">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="52bb1-134">.NET Framework</span></span>

<span data-ttu-id="52bb1-135">.Net Framework 是自 2002 年起就已存在的原始 .NET 实现。</span><span class="sxs-lookup"><span data-stu-id="52bb1-135">The.NET Framework is the original .NET implementation that has existed since 2002.</span></span> <span data-ttu-id="52bb1-136">它是当前 .NET 开发人员经常使用的 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="52bb1-136">It's the same .NET Framework that existing .NET developers have always used.</span></span> <span data-ttu-id="52bb1-137">4.5 版以及更高版本实现 .NET Standard，因此面向 .NET Standard 的代码都可在这些版本的 .NET Framework 上运行。</span><span class="sxs-lookup"><span data-stu-id="52bb1-137">Versions 4.5 and later implement the .NET Standard, so code that targets the .NET Standard can run on those versions of the .NET Framework.</span></span> <span data-ttu-id="52bb1-138">它还包含一些特定于 Windows 的 API，如通过 Windows 窗体和 WPF 进行 Windows 桌面开发的 API。</span><span class="sxs-lookup"><span data-stu-id="52bb1-138">It contains additional Windows-specific APIs, such as APIs for Windows desktop development with Windows Forms and WPF.</span></span> <span data-ttu-id="52bb1-139">.NET Framework 非常适合用于生成 Windows 桌面应用程序。</span><span class="sxs-lookup"><span data-stu-id="52bb1-139">The .NET Framework is optimized for building Windows desktop applications.</span></span>

<span data-ttu-id="52bb1-140">若要了解有关 .NET Framework 的详细信息，请参阅 [.NET Framework 指南](../framework/index.md)。</span><span class="sxs-lookup"><span data-stu-id="52bb1-140">To learn more about the .NET Framework, see the [.NET Framework Guide](../framework/index.md).</span></span>

### <a name="mono"></a><span data-ttu-id="52bb1-141">Mono</span><span class="sxs-lookup"><span data-stu-id="52bb1-141">Mono</span></span>

<span data-ttu-id="52bb1-142">Mono 是主要在需要小型运行时使用的 .NET 实现。</span><span class="sxs-lookup"><span data-stu-id="52bb1-142">Mono is a .NET implementation that is mainly used when a small runtime is required.</span></span> <span data-ttu-id="52bb1-143">它是在 Android、Mac、iOS、tvOS 和 watchOS 上驱动 Xamarin 应用程序的运行时，且主要针对小内存占用。</span><span class="sxs-lookup"><span data-stu-id="52bb1-143">It is the runtime that powers Xamarin applications on Android, Mac, iOS, tvOS and watchOS and is focused primarily on a small footprint.</span></span>

<span data-ttu-id="52bb1-144">它支持所有当前已发布的 .NET Standard 版本。</span><span class="sxs-lookup"><span data-stu-id="52bb1-144">It supports all of the currently published .NET Standard versions.</span></span>

<span data-ttu-id="52bb1-145">以前，Mono 实现更大的 .NET Framework API 并模拟一些 Unix 上最常用的功能。</span><span class="sxs-lookup"><span data-stu-id="52bb1-145">Historically, Mono implemented the larger API of the .NET Framework and emulated some of the most popular capabilities on Unix.</span></span> <span data-ttu-id="52bb1-146">有时使用它运行依赖 Unix 上的这些功能的 .NET 应用程序。</span><span class="sxs-lookup"><span data-stu-id="52bb1-146">It is sometimes used to run .NET applications that rely on those capabilities on Unix.</span></span>

<span data-ttu-id="52bb1-147">Mono 通常与实时编译器一起使用，但它也提供在 iOS 之类的平台使用的完整静态编译器（预先编译）。</span><span class="sxs-lookup"><span data-stu-id="52bb1-147">Mono is typically used with a just-in-time compiler, but it also features a full static compiler (ahead-of-time compilation) that is used on platforms like iOS.</span></span>

<span data-ttu-id="52bb1-148">若要了解有关 Mono 的详细信息，请参阅 [Mono 文档](http://www.mono-project.com/docs/)。</span><span class="sxs-lookup"><span data-stu-id="52bb1-148">To learn more about Mono, see the [Mono documentation](http://www.mono-project.com/docs/).</span></span>

### <a name="universal-windows-platform-uwp"></a><span data-ttu-id="52bb1-149">通用 Windows 平台 (UWP)</span><span class="sxs-lookup"><span data-stu-id="52bb1-149">Universal Windows Platform (UWP)</span></span>

<span data-ttu-id="52bb1-150">UWP 是用于为物联网 (IoT) 生成新式触控 Windows 应用程序和软件的 .NET 实现。</span><span class="sxs-lookup"><span data-stu-id="52bb1-150">UWP is an implementation of .NET that is used for building modern, touch-enabled Windows applications and software for the Internet of Things (IoT).</span></span> <span data-ttu-id="52bb1-151">它旨在统一可能想要以其为目标的不同类型的设备，包括电脑、平板电脑、平板手机、电话，甚至 Xbox。</span><span class="sxs-lookup"><span data-stu-id="52bb1-151">It's designed to unify the different types of devices that you may want to target, including PCs, tablets, phablets, phones, and even the Xbox.</span></span> <span data-ttu-id="52bb1-152">UWP 提供许多服务，如集中式应用商店、执行环境 (AppContainer) 和一组 Windows API（用于代替 Win32 (WinRT)）。</span><span class="sxs-lookup"><span data-stu-id="52bb1-152">UWP provides many services, such as a centralized app store, an execution environment (AppContainer), and a set of Windows APIs to use instead of Win32 (WinRT).</span></span> <span data-ttu-id="52bb1-153">应用可采用 C++、C#、VB.NET 和 JavaScript 编写。</span><span class="sxs-lookup"><span data-stu-id="52bb1-153">Apps can be written in C++, C#, VB.NET, and JavaScript.</span></span> <span data-ttu-id="52bb1-154">使用 C# 和 VB.NET 时，.NET API 由 .NET Core 提供。</span><span class="sxs-lookup"><span data-stu-id="52bb1-154">When using C# and VB.NET, the .NET APIs are provided by .NET Core.</span></span>

<span data-ttu-id="52bb1-155">若要详细了解 UWP，请参阅[通用 Windows 平台简介](https://docs.microsoft.com/windows/uwp/get-started/universal-application-platform-guide)。</span><span class="sxs-lookup"><span data-stu-id="52bb1-155">To learn more about UWP, see [Intro to the Universal Windows Platform](https://docs.microsoft.com/windows/uwp/get-started/universal-application-platform-guide).</span></span>

## <a name="net-runtimes"></a><span data-ttu-id="52bb1-156">.NET 运行时</span><span class="sxs-lookup"><span data-stu-id="52bb1-156">.NET runtimes</span></span>

<span data-ttu-id="52bb1-157">运行时是用于托管程序的执行环境。</span><span class="sxs-lookup"><span data-stu-id="52bb1-157">A runtime is the execution environment for a managed program.</span></span> <span data-ttu-id="52bb1-158">OS 属于运行时环境，但不属于 .NET 运行时。</span><span class="sxs-lookup"><span data-stu-id="52bb1-158">The OS is part of the runtime environment but is not part of the .NET runtime.</span></span> <span data-ttu-id="52bb1-159">下面是 .NET 运行时的一些示例：</span><span class="sxs-lookup"><span data-stu-id="52bb1-159">Here are some examples of .NET runtimes:</span></span>
 
 - <span data-ttu-id="52bb1-160">.NET Framework 公共语言运行时 (CLR)</span><span class="sxs-lookup"><span data-stu-id="52bb1-160">Common Language Runtime (CLR) for the .NET Framework</span></span>
 - <span data-ttu-id="52bb1-161">.NET Core 核心公共语言运行时 (CoreCLR)</span><span class="sxs-lookup"><span data-stu-id="52bb1-161">Core Common Language Runtime (CoreCLR) for .NET Core</span></span>
 - <span data-ttu-id="52bb1-162">适用于通用 Windows 平台的 .NET Native</span><span class="sxs-lookup"><span data-stu-id="52bb1-162">.NET Native for Universal Windows Platform</span></span> 
 - <span data-ttu-id="52bb1-163">用于 Xamarin.iOS、Xamarin.Android、Xamarin.Mac 和 Mono 桌面框架的 Mono 运行时</span><span class="sxs-lookup"><span data-stu-id="52bb1-163">The Mono runtime for Xamarin.iOS, Xamarin.Android, Xamarin.Mac, and the Mono desktop framework</span></span>

## <a name="net-tooling-and-common-infrastructure"></a><span data-ttu-id="52bb1-164">.NET 工具和常见基础结构</span><span class="sxs-lookup"><span data-stu-id="52bb1-164">.NET tooling and common infrastructure</span></span>

<span data-ttu-id="52bb1-165">可访问一整套适用于每种 .NET 实现的工具和基础结构组件。</span><span class="sxs-lookup"><span data-stu-id="52bb1-165">You have access to an extensive set of tools and infrastructure components that work with every implementation of .NET.</span></span> <span data-ttu-id="52bb1-166">包括（但不限于）以下几种：</span><span class="sxs-lookup"><span data-stu-id="52bb1-166">These include, but are not limited to the following:</span></span>

- <span data-ttu-id="52bb1-167">.NET 语言及其编译器</span><span class="sxs-lookup"><span data-stu-id="52bb1-167">The .NET languages and their compilers</span></span>
- <span data-ttu-id="52bb1-168">.NET 项目系统（基于 .csproj.vbproj 和 .fsproj 文件）</span><span class="sxs-lookup"><span data-stu-id="52bb1-168">The .NET project system (based on *.csproj*, *.vbproj*, and *.fsproj* files)</span></span>
- <span data-ttu-id="52bb1-169">[MSBuild](/visualstudio/msbuild/msbuild)（用于生成项目的生成引擎）</span><span class="sxs-lookup"><span data-stu-id="52bb1-169">[MSBuild](/visualstudio/msbuild/msbuild), the build engine used to build projects</span></span>
- <span data-ttu-id="52bb1-170">[NuGet](/nuget/)（适用于.NET 的 Microsoft 程序包管理器）</span><span class="sxs-lookup"><span data-stu-id="52bb1-170">[NuGet](/nuget/), Microsoft's package manager for .NET</span></span>
- <span data-ttu-id="52bb1-171">开放源生成业务流程工具，例如 [CAKE](http://cakebuild.net/) 和 [FAKE](https://fake.build/)</span><span class="sxs-lookup"><span data-stu-id="52bb1-171">Open-source build orchestration tools, such as [CAKE](http://cakebuild.net/) and [FAKE](https://fake.build/)</span></span>

## <a name="see-also"></a><span data-ttu-id="52bb1-172">请参阅</span><span class="sxs-lookup"><span data-stu-id="52bb1-172">See also</span></span>

[<span data-ttu-id="52bb1-173">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="52bb1-173">.NET Standard</span></span>](net-standard.md)  
[<span data-ttu-id="52bb1-174">.NET Core 指南</span><span class="sxs-lookup"><span data-stu-id="52bb1-174">.NET Core Guide</span></span>](../core/index.md)  
[<span data-ttu-id="52bb1-175">.NET Framework 指南</span><span class="sxs-lookup"><span data-stu-id="52bb1-175">.NET Framework Guide</span></span>](../framework/index.md)  
[<span data-ttu-id="52bb1-176">C# 指南</span><span class="sxs-lookup"><span data-stu-id="52bb1-176">C# Guide</span></span>](../csharp/index.md)  
[<span data-ttu-id="52bb1-177">F# 指南</span><span class="sxs-lookup"><span data-stu-id="52bb1-177">F# Guide</span></span>](../fsharp/index.md)  
[<span data-ttu-id="52bb1-178">VB.NET 指南</span><span class="sxs-lookup"><span data-stu-id="52bb1-178">VB.NET Guide</span></span>](../visual-basic/index.md)  


