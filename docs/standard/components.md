---
title: ".NET 体系结构组件"
description: "描述 .NET 体系结构组件，例如 .NET Standard、.NET 实现和工具。"
author: cartermp
ms.author: mairaw
ms.date: 08/23/2017
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.openlocfilehash: ce3368f4c34a8e4b20a7deb2a6c6e4d163927cd4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="net-architectural-components"></a><span data-ttu-id="e7486-103">.NET 体系结构组件</span><span class="sxs-lookup"><span data-stu-id="e7486-103">.NET architectural components</span></span>

<span data-ttu-id="e7486-104">.NET 应用开发用于并运行于一个或多个 .NET 实现。</span><span class="sxs-lookup"><span data-stu-id="e7486-104">A .NET app is developed for and runs in one or more *implementations of .NET*.</span></span>  <span data-ttu-id="e7486-105">.NET 实现包括 .NET Framework、.NET Core 和 Mono。</span><span class="sxs-lookup"><span data-stu-id="e7486-105">Implementations of .NET include the .NET Framework, .NET Core, and Mono.</span></span> <span data-ttu-id="e7486-106">.NET 的所有实现都有一个名为 .NET Standard 的通用 API 规范。</span><span class="sxs-lookup"><span data-stu-id="e7486-106">There is an API specification common to all implementations of .NET that's called the .NET Standard.</span></span> <span data-ttu-id="e7486-107">本文简要介绍了每个概念。</span><span class="sxs-lookup"><span data-stu-id="e7486-107">This article gives a brief introduction to each of these concepts.</span></span>

## <a name="net-standard"></a><span data-ttu-id="e7486-108">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="e7486-108">.NET Standard</span></span>

<span data-ttu-id="e7486-109">.NET Standard 是一组由 .NET 实现的基类库实现的 API。</span><span class="sxs-lookup"><span data-stu-id="e7486-109">The .NET Standard is a set of APIs that are implemented by the Base Class Library of a .NET implementation.</span></span> <span data-ttu-id="e7486-110">更正式地说，它是构成协定统一集（这些协定是编写代码的依据）的特定 .NET API 组。</span><span class="sxs-lookup"><span data-stu-id="e7486-110">More formally, it's a specification of .NET APIs that make up a uniform set of contracts that you compile your code against.</span></span> <span data-ttu-id="e7486-111">这些协定在每个 .NET 实现中实现。</span><span class="sxs-lookup"><span data-stu-id="e7486-111">These contracts are implemented in each .NET implementation.</span></span> <span data-ttu-id="e7486-112">这可实现不同 .NET 实现间的可移植性，有效地使代码可在任何位置运行。</span><span class="sxs-lookup"><span data-stu-id="e7486-112">This enables portability across different .NET implementations, effectively allowing your code to run everywhere.</span></span>

<span data-ttu-id="e7486-113">.NET Standard 也是一个[目标框架](glossary.md#target-framework)。</span><span class="sxs-lookup"><span data-stu-id="e7486-113">The .NET Standard is also a [target framework](glossary.md#target-framework).</span></span> <span data-ttu-id="e7486-114">如果代码面向 .NET Standard 版本，则它可在支持该 .NET Standard 版本的任何 .NET 实现上运行。</span><span class="sxs-lookup"><span data-stu-id="e7486-114">If your code targets a version of the .NET Standard, it can run on any .NET implementation which supports that version of the .NET Standard.</span></span>

<span data-ttu-id="e7486-115">若要详细了解 .NET Standard 以及如何将其作为目标，请参阅 [.NET Standard](net-standard.md) 主题。</span><span class="sxs-lookup"><span data-stu-id="e7486-115">To learn more about the .NET Standard and how to target it, see the [.NET Standard](net-standard.md) topic.</span></span>

## <a name="net-implementations"></a><span data-ttu-id="e7486-116">.NET 实现</span><span class="sxs-lookup"><span data-stu-id="e7486-116">.NET implementations</span></span>

<span data-ttu-id="e7486-117">.NET 的每个实现都具有以下组件：</span><span class="sxs-lookup"><span data-stu-id="e7486-117">Each implementation of .NET includes the following components:</span></span>

- <span data-ttu-id="e7486-118">一个或多个运行时。</span><span class="sxs-lookup"><span data-stu-id="e7486-118">One or more runtimes.</span></span> <span data-ttu-id="e7486-119">示例：用于 .NET Framework 的 CLR、CoreCLR 和用于 .NET Core 的 CoreRT。</span><span class="sxs-lookup"><span data-stu-id="e7486-119">Examples: CLR for .NET Framework, CoreCLR and CoreRT for .NET Core.</span></span>
- <span data-ttu-id="e7486-120">实现 .NET Standard 并且可实现其他 API 的类库。</span><span class="sxs-lookup"><span data-stu-id="e7486-120">A class library that implements the .NET Standard and may implement additional APIs.</span></span> <span data-ttu-id="e7486-121">示例：.NET Framework 基类库、.NET Core 基类库。</span><span class="sxs-lookup"><span data-stu-id="e7486-121">Examples: .NET Framework Base Class Library, .NET Core Base Class Library.</span></span>
- <span data-ttu-id="e7486-122">可选择包含一个或多个应用程序框架。</span><span class="sxs-lookup"><span data-stu-id="e7486-122">Optionally, one or more application frameworks.</span></span> <span data-ttu-id="e7486-123">示例： [ASP.NET](https://www.asp.net/)、[Windows 窗体](../framework/winforms/windows-forms-overview.md)和 [Windows Presentation Foundation (WPF)](../framework/wpf/index.md) 包含在 .NET Framework 中。</span><span class="sxs-lookup"><span data-stu-id="e7486-123">Examples: [ASP.NET](https://www.asp.net/), [Windows Forms](../framework/winforms/windows-forms-overview.md), and [Windows Presentation Foundation (WPF)](../framework/wpf/index.md) are included in the .NET Framework.</span></span>
- <span data-ttu-id="e7486-124">可包含开发工具。</span><span class="sxs-lookup"><span data-stu-id="e7486-124">Optionally, development tools.</span></span> <span data-ttu-id="e7486-125">某些开发工具在多个实现之间共享。</span><span class="sxs-lookup"><span data-stu-id="e7486-125">Some development tools are shared among multiple implementations.</span></span>

<span data-ttu-id="e7486-126">Microsoft 积极开发和维护的主要 .NET 实现有 4 个：.NET Core、.NET Framework、Mono 和 UWP。</span><span class="sxs-lookup"><span data-stu-id="e7486-126">There are four primary .NET implementations that Microsoft actively develops and maintains: .NET Core, .NET Framework, Mono, and UWP.</span></span>

### <a name="net-core"></a><span data-ttu-id="e7486-127">.NET 核心</span><span class="sxs-lookup"><span data-stu-id="e7486-127">.NET Core</span></span>

<span data-ttu-id="e7486-128">.NET Core 是 .NET 的跨平台实现，专用于处理大规模的服务器和云工作负荷。</span><span class="sxs-lookup"><span data-stu-id="e7486-128">.NET Core is a cross-platform implementation of .NET and designed to handle server and cloud workloads at scale.</span></span> <span data-ttu-id="e7486-129">可在 Windows、macOS 和 Linux 上运行。</span><span class="sxs-lookup"><span data-stu-id="e7486-129">It runs on Windows, macOS and Linux.</span></span> <span data-ttu-id="e7486-130">它实现 .NET Standard，因此面向 .NET Standard 的代码都可在 .NET Core 上运行。</span><span class="sxs-lookup"><span data-stu-id="e7486-130">It implements the .NET Standard, so code that targets the .NET Standard can run on .NET Core.</span></span> <span data-ttu-id="e7486-131">ASP.NET Core 在 .NET Core 上运行。</span><span class="sxs-lookup"><span data-stu-id="e7486-131">ASP.NET Core runs on .NET Core.</span></span> 

<span data-ttu-id="e7486-132">要了解有关 .NET Core 的详细信息，请参阅 [.NET Core 指南](../core/index.md)和[为服务器应用选择 .NET Core 或 .NET Framework](choosing-core-framework-server.md)。</span><span class="sxs-lookup"><span data-stu-id="e7486-132">To learn more about .NET Core, see the [.NET Core Guide](../core/index.md) and [Choosing between .NET Core and .NET Framework for server apps](choosing-core-framework-server.md).</span></span>

### <a name="net-framework"></a><span data-ttu-id="e7486-133">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="e7486-133">.NET Framework</span></span>

<span data-ttu-id="e7486-134">.Net Framework 是自 2002 年起就已存在的原始 .NET 实现。</span><span class="sxs-lookup"><span data-stu-id="e7486-134">The.NET Framework is the original .NET implementation that has existed since 2002.</span></span> <span data-ttu-id="e7486-135">它是当前 .NET 开发人员经常使用的 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="e7486-135">It's the same .NET Framework that existing .NET developers have always used.</span></span> <span data-ttu-id="e7486-136">4.5 版以及更高版本实现 .NET Standard，因此面向 .NET Standard 的代码都可在这些版本的 .NET Framework 上运行。</span><span class="sxs-lookup"><span data-stu-id="e7486-136">Versions 4.5 and later implement the .NET Standard, so code that targets the .NET Standard can run on those versions of the .NET Framework.</span></span> <span data-ttu-id="e7486-137">它还包含一些特定于 Windows 的 API，如通过 Windows 窗体和 WPF 进行 Windows 桌面开发的 API。</span><span class="sxs-lookup"><span data-stu-id="e7486-137">It contains additional Windows-specific APIs, such as APIs for Windows desktop development with Windows Forms and WPF.</span></span> <span data-ttu-id="e7486-138">.NET Framework 非常适合用于生成 Windows 桌面应用程序。</span><span class="sxs-lookup"><span data-stu-id="e7486-138">The .NET Framework is optimized for building Windows desktop applications.</span></span>

<span data-ttu-id="e7486-139">若要了解有关 .NET Framework 的详细信息，请参阅 [.NET Framework 指南](../framework/index.md)。</span><span class="sxs-lookup"><span data-stu-id="e7486-139">To learn more about the .NET Framework, see the [.NET Framework Guide](../framework/index.md).</span></span>

### <a name="mono"></a><span data-ttu-id="e7486-140">Mono</span><span class="sxs-lookup"><span data-stu-id="e7486-140">Mono</span></span>

<span data-ttu-id="e7486-141">Mono 是主要在需要小型运行时使用的 .NET 实现。</span><span class="sxs-lookup"><span data-stu-id="e7486-141">Mono is a .NET implementation that is mainly used when a small runtime is required.</span></span> <span data-ttu-id="e7486-142">它是在 Android、Mac、iOS、tvOS 和 watchOS 上驱动 Xamarin 应用程序的运行时，且主要针对小内存占用。</span><span class="sxs-lookup"><span data-stu-id="e7486-142">It is the runtime that powers Xamarin applications on Android, Mac, iOS, tvOS and watchOS and is focused primarily on a small footprint.</span></span>

<span data-ttu-id="e7486-143">它支持所有当前已发布的 .NET Standard 版本。</span><span class="sxs-lookup"><span data-stu-id="e7486-143">It supports all of the currently published .NET Standard versions.</span></span>

<span data-ttu-id="e7486-144">以前，Mono 实现更大的 .NET Framework API 并模拟一些 Unix 上最常用的功能。</span><span class="sxs-lookup"><span data-stu-id="e7486-144">Historically, Mono implemented the larger API of the .NET Framework and emulated some of the most popular capabilities on Unix.</span></span> <span data-ttu-id="e7486-145">有时使用它运行依赖 Unix 上的这些功能的 .NET 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e7486-145">It is sometimes used to run .NET applications that rely on those capabilities on Unix.</span></span>

<span data-ttu-id="e7486-146">Mono 通常与实时编译器一起使用，但它也提供在 iOS 之类的平台使用的完整静态编译器（预先编译）。</span><span class="sxs-lookup"><span data-stu-id="e7486-146">Mono is typically used with a just-in-time compiler, but it also features a full static compiler (ahead-of-time compilation) that is used on platforms like iOS.</span></span>

<span data-ttu-id="e7486-147">若要了解有关 Mono 的详细信息，请参阅 [Mono 文档](http://www.mono-project.com/docs/)。</span><span class="sxs-lookup"><span data-stu-id="e7486-147">To learn more about Mono, see the [Mono documentation](http://www.mono-project.com/docs/).</span></span>

### <a name="universal-windows-platform-uwp"></a><span data-ttu-id="e7486-148">通用 Windows 平台 (UWP)</span><span class="sxs-lookup"><span data-stu-id="e7486-148">Universal Windows Platform (UWP)</span></span>

<span data-ttu-id="e7486-149">UWP 是用于为物联网 (IoT) 生成新式触控 Windows 应用程序和软件的 .NET 实现。</span><span class="sxs-lookup"><span data-stu-id="e7486-149">UWP is an implementation of .NET that is used for building modern, touch-enabled Windows applications and software for the Internet of Things (IoT).</span></span> <span data-ttu-id="e7486-150">它旨在统一可能想要以其为目标的不同类型的设备，包括电脑、平板电脑、平板手机、电话，甚至 Xbox。</span><span class="sxs-lookup"><span data-stu-id="e7486-150">It's designed to unify the different types of devices that you may want to target, including PCs, tablets, phablets, phones, and even the Xbox.</span></span> <span data-ttu-id="e7486-151">UWP 提供许多服务，如集中式应用商店、执行环境 (AppContainer) 和一组 Windows API（用于代替 Win32 (WinRT)）。</span><span class="sxs-lookup"><span data-stu-id="e7486-151">UWP provides many services, such as a centralized app store, an execution environment (AppContainer), and a set of Windows APIs to use instead of Win32 (WinRT).</span></span> <span data-ttu-id="e7486-152">应用可采用 C++、C#、VB.NET 和 JavaScript 编写。</span><span class="sxs-lookup"><span data-stu-id="e7486-152">Apps can be written in C++, C#, VB.NET, and JavaScript.</span></span> <span data-ttu-id="e7486-153">使用 C# 和 VB.NET 时，.NET API 由 .NET Core 提供。</span><span class="sxs-lookup"><span data-stu-id="e7486-153">When using C# and VB.NET, the .NET APIs are provided by .NET Core.</span></span>

<span data-ttu-id="e7486-154">若要详细了解 UWP，请参阅[通用 Windows 平台简介](https://docs.microsoft.com/windows/uwp/get-started/universal-application-platform-guide)。</span><span class="sxs-lookup"><span data-stu-id="e7486-154">To learn more about UWP, see [Intro to the Universal Windows Platform](https://docs.microsoft.com/windows/uwp/get-started/universal-application-platform-guide).</span></span>

## <a name="net-runtimes"></a><span data-ttu-id="e7486-155">.NET 运行时</span><span class="sxs-lookup"><span data-stu-id="e7486-155">.NET runtimes</span></span>

<span data-ttu-id="e7486-156">运行时是用于托管程序的执行环境。</span><span class="sxs-lookup"><span data-stu-id="e7486-156">A runtime is the execution environment for a managed program.</span></span> <span data-ttu-id="e7486-157">OS 属于运行时环境，但不属于 .NET 运行时。</span><span class="sxs-lookup"><span data-stu-id="e7486-157">The OS is part of the runtime environment but is not part of the .NET runtime.</span></span> <span data-ttu-id="e7486-158">下面是 .NET 运行时的一些示例：</span><span class="sxs-lookup"><span data-stu-id="e7486-158">Here are some examples of .NET runtimes:</span></span>
 
 - <span data-ttu-id="e7486-159">.NET Framework 公共语言运行时 (CLR)</span><span class="sxs-lookup"><span data-stu-id="e7486-159">Common Language Runtime (CLR) for the .NET Framework</span></span>
 - <span data-ttu-id="e7486-160">.NET Core 核心公共语言运行时 (CoreCLR)</span><span class="sxs-lookup"><span data-stu-id="e7486-160">Core Common Language Runtime (CoreCLR) for .NET Core</span></span>
 - <span data-ttu-id="e7486-161">适用于通用 Windows 平台的 .NET Native</span><span class="sxs-lookup"><span data-stu-id="e7486-161">.NET Native for Universal Windows Platform</span></span> 
 - <span data-ttu-id="e7486-162">用于 Xamarin.iOS、Xamarin.Android、Xamarin.Mac 和 Mono 桌面框架的 Mono 运行时</span><span class="sxs-lookup"><span data-stu-id="e7486-162">The Mono runtime for Xamarin.iOS, Xamarin.Android, Xamarin.Mac, and the Mono desktop framework</span></span>

## <a name="net-tooling-and-common-infrastructure"></a><span data-ttu-id="e7486-163">.NET 工具和常见基础结构</span><span class="sxs-lookup"><span data-stu-id="e7486-163">.NET tooling and common infrastructure</span></span>

<span data-ttu-id="e7486-164">可访问一整套适用于每种 .NET 实现的工具和基础结构组件。</span><span class="sxs-lookup"><span data-stu-id="e7486-164">You have access to an extensive set of tools and infrastructure components that work with every implementation of .NET.</span></span> <span data-ttu-id="e7486-165">包括（但不限于）以下几种：</span><span class="sxs-lookup"><span data-stu-id="e7486-165">These include, but are not limited to the following:</span></span>

- <span data-ttu-id="e7486-166">.NET 语言及其编译器</span><span class="sxs-lookup"><span data-stu-id="e7486-166">The .NET languages and their compilers</span></span>
- <span data-ttu-id="e7486-167">.NET 项目系统（基于 .csproj.vbproj 和 .fsproj 文件）</span><span class="sxs-lookup"><span data-stu-id="e7486-167">The .NET project system (based on *.csproj*, *.vbproj*, and *.fsproj* files)</span></span>
- <span data-ttu-id="e7486-168">[MSBuild](/visualstudio/msbuild/msbuild)（用于生成项目的生成引擎）</span><span class="sxs-lookup"><span data-stu-id="e7486-168">[MSBuild](/visualstudio/msbuild/msbuild), the build engine used to build projects</span></span>
- <span data-ttu-id="e7486-169">[NuGet](/nuget/)（适用于.NET 的 Microsoft 程序包管理器）</span><span class="sxs-lookup"><span data-stu-id="e7486-169">[NuGet](/nuget/), Microsoft's package manager for .NET</span></span>
- <span data-ttu-id="e7486-170">开放源生成业务流程工具，例如 [CAKE](http://cakebuild.net/) 和 [FAKE](https://fake.build/)</span><span class="sxs-lookup"><span data-stu-id="e7486-170">Open-source build orchestration tools, such as [CAKE](http://cakebuild.net/) and [FAKE](https://fake.build/)</span></span>

## <a name="see-also"></a><span data-ttu-id="e7486-171">请参阅</span><span class="sxs-lookup"><span data-stu-id="e7486-171">See also</span></span>
<span data-ttu-id="e7486-172">[为服务器应用选择 .NET Core 或 .NET Framework](choosing-core-framework-server.md) </span><span class="sxs-lookup"><span data-stu-id="e7486-172">[Choosing between .NET Core and .NET Framework for server apps](choosing-core-framework-server.md) </span></span>  
[<span data-ttu-id="e7486-173">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="e7486-173">.NET Standard</span></span>](net-standard.md)  
[<span data-ttu-id="e7486-174">.NET Core 指南</span><span class="sxs-lookup"><span data-stu-id="e7486-174">.NET Core Guide</span></span>](../core/index.md)  
[<span data-ttu-id="e7486-175">.NET Framework 指南</span><span class="sxs-lookup"><span data-stu-id="e7486-175">.NET Framework Guide</span></span>](../framework/index.md)  
[<span data-ttu-id="e7486-176">C# 指南</span><span class="sxs-lookup"><span data-stu-id="e7486-176">C# Guide</span></span>](../csharp/index.md)  
[<span data-ttu-id="e7486-177">F# 指南</span><span class="sxs-lookup"><span data-stu-id="e7486-177">F# Guide</span></span>](../fsharp/index.md)  
[<span data-ttu-id="e7486-178">VB.NET 指南</span><span class="sxs-lookup"><span data-stu-id="e7486-178">VB.NET Guide</span></span>](../visual-basic/index.md)  

