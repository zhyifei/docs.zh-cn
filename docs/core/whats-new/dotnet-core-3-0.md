---
title: .NET Core 3.0 的新增功能
description: 了解 .NET Core 3.0 的新增功能。
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 07/25/2019
ms.openlocfilehash: f1fce2899e9e11b1007d6c270180b27a29eaa167
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039436"
---
# <a name="whats-new-in-net-core-30-preview-7"></a><span data-ttu-id="100e0-103">.NET Core 3.0（预览版 7）中的新增功能</span><span class="sxs-lookup"><span data-stu-id="100e0-103">What's new in .NET Core 3.0 (Preview 7)</span></span>

<span data-ttu-id="100e0-104">本文介绍 .NET Core 3.0（预览版 7）的新增功能。</span><span class="sxs-lookup"><span data-stu-id="100e0-104">This article describes what is new in .NET Core 3.0 (through preview 7).</span></span> <span data-ttu-id="100e0-105">最大的增强功能之一是对 Windows 桌面应用程序的支持（仅限 Windows）。</span><span class="sxs-lookup"><span data-stu-id="100e0-105">One of the biggest enhancements is support for Windows desktop applications (Windows only).</span></span> <span data-ttu-id="100e0-106">通过使用 .NET Core 3.0 SDK Windows 桌面组件，可移植 Windows 窗体和 Windows Presentation Foundation (WPF) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="100e0-106">By using the .NET Core 3.0 SDK component Windows Desktop, you can port your Windows Forms and Windows Presentation Foundation (WPF) applications.</span></span> <span data-ttu-id="100e0-107">明确地说，只有在 Windows 上才支持和包含 Windows 桌面组件。</span><span class="sxs-lookup"><span data-stu-id="100e0-107">To be clear, the Windows Desktop component is only supported and included on Windows.</span></span> <span data-ttu-id="100e0-108">有关详细信息，请参阅本文后面的 [Windows 桌面](#windows-desktop)部分。</span><span class="sxs-lookup"><span data-stu-id="100e0-108">For more information, see the [Windows desktop](#windows-desktop) section later in this article.</span></span>

<span data-ttu-id="100e0-109">.NET Core 3.0 添加了对 C#8.0 的支持。</span><span class="sxs-lookup"><span data-stu-id="100e0-109">.NET Core 3.0 adds support for C# 8.0.</span></span> <span data-ttu-id="100e0-110">强烈建议使用[最新版本的 Visual Studio 预览版](https://visualstudio.microsoft.com/vs/preview/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+preview)或带有 OmniSharp 扩展的 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="100e0-110">It's highly recommended that you use the [latest release of Visual Studio Preview](https://visualstudio.microsoft.com/vs/preview/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+preview), or Visual Studio Code with the OmniSharp extension.</span></span>

<span data-ttu-id="100e0-111">立即在 Windows、Mac 和 Linux 上[下载并开始使用 .NET Core 3.0 预览版 7](https://aka.ms/netcore3download)。</span><span class="sxs-lookup"><span data-stu-id="100e0-111">[Download and get started with .NET Core 3.0 preview 7](https://aka.ms/netcore3download) right now on Windows, Mac, and Linux.</span></span>

<span data-ttu-id="100e0-112">有关每个预览版本的详细信息，请参阅以下公告：</span><span class="sxs-lookup"><span data-stu-id="100e0-112">For more information about each preview release, see the following announcements:</span></span>

- [<span data-ttu-id="100e0-113">.NET Core 3.0 预览版 7 公告</span><span class="sxs-lookup"><span data-stu-id="100e0-113">.NET Core 3.0 Preview 7 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-7/)
- [<span data-ttu-id="100e0-114">.NET Core 3.0 预览版 6 公告</span><span class="sxs-lookup"><span data-stu-id="100e0-114">.NET Core 3.0 Preview 6 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-6/)
- [<span data-ttu-id="100e0-115">.NET Core 3.0 预览版 5 公告</span><span class="sxs-lookup"><span data-stu-id="100e0-115">.NET Core 3.0 Preview 5 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-5/)
- [<span data-ttu-id="100e0-116">.NET Core 3.0 预览版 4 公告</span><span class="sxs-lookup"><span data-stu-id="100e0-116">.NET Core 3.0 Preview 4 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-4/)
- [<span data-ttu-id="100e0-117">.NET Core 3.0 预览版 3 公告</span><span class="sxs-lookup"><span data-stu-id="100e0-117">.NET Core 3.0 Preview 3 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-3/)
- [<span data-ttu-id="100e0-118">.NET Core 3.0 预览版 2 公告</span><span class="sxs-lookup"><span data-stu-id="100e0-118">.NET Core 3.0 Preview 2 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-2/)
- [<span data-ttu-id="100e0-119">.NET Core 3.0 预览版 1 公告</span><span class="sxs-lookup"><span data-stu-id="100e0-119">.NET Core 3.0 Preview 1 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/)

## <a name="production-supported-preview"></a><span data-ttu-id="100e0-120">生产支持（预览版）</span><span class="sxs-lookup"><span data-stu-id="100e0-120">Production supported preview</span></span>

<span data-ttu-id="100e0-121">.NET Core 预览版 7 已由 Microsoft 准备就绪，可用于生产环境并且完全受支持。</span><span class="sxs-lookup"><span data-stu-id="100e0-121">.NET Core Preview 7 is considered production ready by Microsoft and is fully supported.</span></span> <span data-ttu-id="100e0-122">从预览版 7 开始，版本将侧重于改进 .NET Core 3.0，而不是添加新功能。</span><span class="sxs-lookup"><span data-stu-id="100e0-122">Starting with preview 7, releases will focus on polishing .NET Core 3.0 instead of adding new features.</span></span> <span data-ttu-id="100e0-123">有关预览版 7 的改进内容的详细信息，请参阅[预览版 7 公告](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-7/)。</span><span class="sxs-lookup"><span data-stu-id="100e0-123">For more information about what has changed in preview 7, see the [preview 7 announcement](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-7/).</span></span>

## <a name="net-core-sdk-windows-installer"></a><span data-ttu-id="100e0-124">.NET Core SDK Windows Installer</span><span class="sxs-lookup"><span data-stu-id="100e0-124">.NET Core SDK Windows Installer</span></span>

<span data-ttu-id="100e0-125">用于 Windows 的 MSI 安装程序已从 .NET Core 3.0 开始更改。</span><span class="sxs-lookup"><span data-stu-id="100e0-125">The MSI installer for Windows has changed starting with .NET Core 3.0.</span></span> <span data-ttu-id="100e0-126">SDK 安装程序现在将对 SDK 功能区段版本进行就地升级。</span><span class="sxs-lookup"><span data-stu-id="100e0-126">The SDK installers will now upgrade SDK feature-band releases in place.</span></span> <span data-ttu-id="100e0-127">功能区段在版本号的*补丁*部分中的*数百个*组中定义。</span><span class="sxs-lookup"><span data-stu-id="100e0-127">Feature bands are defined in the *hundreds* groups in the *patch* section of the version number.</span></span> <span data-ttu-id="100e0-128">例如，**3.0._101_** 和 **3.0._201_** 是两个不同功能区段中的版本，而 **3.0._101_** 和 **3.0._199_** 则属于同一个功能区段。</span><span class="sxs-lookup"><span data-stu-id="100e0-128">For example, **3.0._101_** and **3.0._201_** are versions in two different feature bands while **3.0._101_** and **3.0._199_** are in the same feature band.</span></span> <span data-ttu-id="100e0-129">并且，当安装 .NET Core SDK **3.0._101_** 时，将从计算机中删除 .NET Core SDK **3.0._100_** （如果存在）。</span><span class="sxs-lookup"><span data-stu-id="100e0-129">And, when .NET Core SDK **3.0._101_** is installed, .NET Core SDK **3.0._100_** will be removed from the machine if it exists.</span></span> <span data-ttu-id="100e0-130">当 .NET Core SDK **3.0._200_** 安装在同一台计算机上时，不会删除 .NET Core SDK **3.0._101_** 。</span><span class="sxs-lookup"><span data-stu-id="100e0-130">When .NET Core SDK **3.0._200_** is installed on the same machine, .NET Core SDK **3.0._101_** won't be removed.</span></span>

<span data-ttu-id="100e0-131">有关版本控制的详细信息，请参阅 [.NET Core 的版本控制方式概述](../versions/index.md)。</span><span class="sxs-lookup"><span data-stu-id="100e0-131">For more information about versioning, see [Overview of how .NET Core is versioned](../versions/index.md).</span></span>

## <a name="c-80-preview"></a><span data-ttu-id="100e0-132">C# 8.0 预览版</span><span class="sxs-lookup"><span data-stu-id="100e0-132">C# 8.0 preview</span></span>

<span data-ttu-id="100e0-133">.NET Core 3.0 支持 C# 8 预览版。</span><span class="sxs-lookup"><span data-stu-id="100e0-133">.NET Core 3.0 supports C# 8 preview.</span></span> <span data-ttu-id="100e0-134">有关 C# 8.0 功能的详细信息，请参阅 [C# 8.0 中的新增功能](../../csharp/whats-new/csharp-8.md)。</span><span class="sxs-lookup"><span data-stu-id="100e0-134">For more information about C# 8.0 features, see [What's new in C# 8.0](../../csharp/whats-new/csharp-8.md).</span></span>

## <a name="net-standard-21"></a><span data-ttu-id="100e0-135">.NET Standard 2.1</span><span class="sxs-lookup"><span data-stu-id="100e0-135">.NET Standard 2.1</span></span>

<span data-ttu-id="100e0-136">尽管 .NET Core 3.0 支持 **.NET Standard 2.1**，默认的 `dotnet new classlib` 模板还是会生成一个面向 **.NET Standard 2.0** 的项目。</span><span class="sxs-lookup"><span data-stu-id="100e0-136">Even though .NET Core 3.0 supports **.NET Standard 2.1**, the default `dotnet new classlib` template generates a project that targets **.NET Standard 2.0**.</span></span> <span data-ttu-id="100e0-137">若要面向 **.NET Standard 2.1**，请编辑项目文件并将 `TargetFramework` 属性更改为 `netstandard2.1`：</span><span class="sxs-lookup"><span data-stu-id="100e0-137">To target **.NET Standard 2.1**, edit your project file and change the `TargetFramework` property to `netstandard2.1`:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
 
  <PropertyGroup>
    <TargetFramework>netstandard2.1</TargetFramework>
  </PropertyGroup>
 
</Project>
```

<span data-ttu-id="100e0-138">如果使用 Visual Studio，则需要 [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)，这是因为 Visual Studio 2017 不支持 .NET Standard 2.1 或 .NET Core 3.0   。</span><span class="sxs-lookup"><span data-stu-id="100e0-138">If you're using Visual Studio, you need [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), as Visual Studio 2017 doesn't support **.NET Standard 2.1** or **.NET Core 3.0**.</span></span>

## <a name="improved-net-core-version-apis"></a><span data-ttu-id="100e0-139">改进的 .NET Core 版本 API</span><span class="sxs-lookup"><span data-stu-id="100e0-139">Improved .NET Core Version APIs</span></span>

<span data-ttu-id="100e0-140">从 .NET Core 3.0 开始，.NET Core 提供的版本 API 现在可以返回你预期的信息。</span><span class="sxs-lookup"><span data-stu-id="100e0-140">Starting with .NET Core 3.0, the version APIs provided with .NET Core now return the information you expect.</span></span> <span data-ttu-id="100e0-141">例如:</span><span class="sxs-lookup"><span data-stu-id="100e0-141">For example:</span></span>

```csharp
System.Console.WriteLine($"Environment.Version: {System.Environment.Version}");

// Old result
//   Environment.Version: 4.0.30319.42000
//
// New result
//   Environment.Version: 3.0.0
```

```csharp
System.Console.WriteLine($"RuntimeInformation.FrameworkDescription: {System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription}");

// Old result
//   RuntimeInformation.FrameworkDescription: .NET Core 4.6.27415.71
//
// New result
//   RuntimeInformation.FrameworkDescription: .NET Core 3.0.0-preview4-27615-11
```

> [!WARNING]
> <span data-ttu-id="100e0-142">重大更改。</span><span class="sxs-lookup"><span data-stu-id="100e0-142">Breaking change.</span></span> <span data-ttu-id="100e0-143">这在技术上是一个突破性的改变，因为版本控制方案已发生变化。</span><span class="sxs-lookup"><span data-stu-id="100e0-143">This is technically a breaking change because the versioning scheme has changed.</span></span>

## <a name="net-platform-dependent-intrinsics"></a><span data-ttu-id="100e0-144">依赖于 .NET 平台的内部函数</span><span class="sxs-lookup"><span data-stu-id="100e0-144">.NET Platform-Dependent Intrinsics</span></span>

<span data-ttu-id="100e0-145">已添加 API，允许访问某些性能导向的 CPU 指令，例如 SIMD 或位操作指令集   。</span><span class="sxs-lookup"><span data-stu-id="100e0-145">APIs have been added that allow access to certain perf-oriented CPU instructions, such as the **SIMD** or **Bit Manipulation instruction** sets.</span></span> <span data-ttu-id="100e0-146">这些指令有助于在某些情况下实现显著的性能改进，例如高效地并行处理数据。</span><span class="sxs-lookup"><span data-stu-id="100e0-146">These instructions can help achieve significant performance improvements in certain scenarios, such as processing data efficiently in parallel.</span></span> 

<span data-ttu-id="100e0-147">在适当的情况下，.NET 库已开始使用这些指令来改进性能。</span><span class="sxs-lookup"><span data-stu-id="100e0-147">Where appropriate, the .NET libraries have begun using these instructions to improve performance.</span></span>

<span data-ttu-id="100e0-148">有关详细信息，请参阅 [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md)（依赖于 .NET 平台的内部函数）。</span><span class="sxs-lookup"><span data-stu-id="100e0-148">For more information, see [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md).</span></span>

## <a name="default-executables"></a><span data-ttu-id="100e0-149">默认可执行文件</span><span class="sxs-lookup"><span data-stu-id="100e0-149">Default executables</span></span>

<span data-ttu-id="100e0-150">.NET Core 现在默认生成[依赖于框架的可执行文件](../deploying/index.md#framework-dependent-executables-fde)。</span><span class="sxs-lookup"><span data-stu-id="100e0-150">.NET Core now builds [framework-dependent executables](../deploying/index.md#framework-dependent-executables-fde) by default.</span></span> <span data-ttu-id="100e0-151">对于使用全局安装的 .NET Core 版本的应用程序而言，这是一种新行为。</span><span class="sxs-lookup"><span data-stu-id="100e0-151">This behavior is new for applications that use a globally installed version of .NET Core.</span></span> <span data-ttu-id="100e0-152">以前，仅[独立部署](../deploying/index.md#self-contained-deployments-scd)会生成可执行文件。</span><span class="sxs-lookup"><span data-stu-id="100e0-152">Previously, only [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) would produce an executable.</span></span>

<span data-ttu-id="100e0-153">在 `dotnet build` 或 `dotnet publish` 期间，将创建一个与你使用的 SDK 的环境和平台相匹配的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="100e0-153">During `dotnet build` or `dotnet publish`, an executable is created that matches the environment and platform of the SDK you're using.</span></span> <span data-ttu-id="100e0-154">和其他本机可执行文件一样，可以使用这些可执行文件执行相同操作，例如：</span><span class="sxs-lookup"><span data-stu-id="100e0-154">You can expect the same things with these executables as you would other native executables, such as:</span></span>

* <span data-ttu-id="100e0-155">可以双击可执行文件。</span><span class="sxs-lookup"><span data-stu-id="100e0-155">You can double-click on the executable.</span></span>
* <span data-ttu-id="100e0-156">可以直接从命令提示符启用应用程序，如 Windows 上的 `myapp.exe`，以及 Linux 和 macOS 上的 `./myapp`。</span><span class="sxs-lookup"><span data-stu-id="100e0-156">You can launch the application from a command prompt directly, such as `myapp.exe` on Windows, and `./myapp` on Linux and macOS.</span></span>

## <a name="single-file-executables"></a><span data-ttu-id="100e0-157">单文件可执行文件</span><span class="sxs-lookup"><span data-stu-id="100e0-157">Single-file executables</span></span>

<span data-ttu-id="100e0-158">`dotnet publish` 命令支持将应用打包为特定于平台的单文件可执行文件。</span><span class="sxs-lookup"><span data-stu-id="100e0-158">The `dotnet publish` command supports packaging your app into a platform-specific single-file executable.</span></span> <span data-ttu-id="100e0-159">该可执行文件是自提取文件，包含运行应用所需的所有依赖项（包括本机依赖项）。</span><span class="sxs-lookup"><span data-stu-id="100e0-159">The executable is self-extracting and contains all dependencies (including native) that are required to run your app.</span></span> <span data-ttu-id="100e0-160">首次运行应用时，应用程序将根据应用名称和生成标识符提取到目录中。</span><span class="sxs-lookup"><span data-stu-id="100e0-160">When the app is first run, the application is extracted to a directory based on the app name and build identifier.</span></span> <span data-ttu-id="100e0-161">再次运行应用程序时，启动速度将变快。</span><span class="sxs-lookup"><span data-stu-id="100e0-161">Startup is faster when the application is run again.</span></span> <span data-ttu-id="100e0-162">除非使用新版本，否则应用程序不需要第二次提取自身。</span><span class="sxs-lookup"><span data-stu-id="100e0-162">The application doesn't need to extract itself a second time unless a new version was used.</span></span>

<span data-ttu-id="100e0-163">若要发布单文件可执行文件，请使用 `dotnet publish` 命令在项目或命令行中设置 `PublishSingleFile`：</span><span class="sxs-lookup"><span data-stu-id="100e0-163">To publish a single-file executable, set the `PublishSingleFile` in your project or on the command line with the `dotnet publish` command:</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>win10-x64</RuntimeIdentifier>
  <PublishSingleFile>true</PublishSingleFile>
</PropertyGroup>
```

<span data-ttu-id="100e0-164">-或-</span><span class="sxs-lookup"><span data-stu-id="100e0-164">-or-</span></span>

```console
dotnet publish -r win10-x64 /p:PublishSingleFile=true
```

<span data-ttu-id="100e0-165">有关单文件发布的详细信息，请参阅[单文件捆绑程序设计文档](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md)。</span><span class="sxs-lookup"><span data-stu-id="100e0-165">For more information about single-file publishing, see the [single-file bundler design document](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md).</span></span>

## <a name="assembly-linking"></a><span data-ttu-id="100e0-166">程序集链接</span><span class="sxs-lookup"><span data-stu-id="100e0-166">Assembly linking</span></span>

<span data-ttu-id="100e0-167">.NET core 3.0 SDK 随附了一种工具，可以通过分析 IL 并剪裁未使用的程序集来减小应用的大小。</span><span class="sxs-lookup"><span data-stu-id="100e0-167">The .NET core 3.0 SDK comes with a tool that can reduce the size of apps by analyzing IL and trimming unused assemblies.</span></span>

<span data-ttu-id="100e0-168">自包含应用包括运行代码所需的所有内容，而无需在主机计算机上安装 .NET。</span><span class="sxs-lookup"><span data-stu-id="100e0-168">Self-contained apps include everything needed to run your code, without requiring .NET to be installed on the host computer.</span></span> <span data-ttu-id="100e0-169">但是，很多时候应用只需要框架的一小部分即可运行，而未使用的其他库可以删除。</span><span class="sxs-lookup"><span data-stu-id="100e0-169">However, many times the app only requires a small subset of the framework to function, and other unused libraries could be removed.</span></span>

<span data-ttu-id="100e0-170">.NET Core 现在包含一个设置，将使用 [IL 链接器](https://github.com/mono/linker)工具扫描应用的 IL。</span><span class="sxs-lookup"><span data-stu-id="100e0-170">.NET Core now includes a setting that will use the [IL linker](https://github.com/mono/linker) tool to scan the IL of your app.</span></span> <span data-ttu-id="100e0-171">此工具将检测哪些代码是必需的，然后剪裁未使用的库。</span><span class="sxs-lookup"><span data-stu-id="100e0-171">this tool detects what code is required, and then trims unused libraries.</span></span> <span data-ttu-id="100e0-172">此工具可以显著减少某些应用的部署大小。</span><span class="sxs-lookup"><span data-stu-id="100e0-172">This tool can significantly reduce the deployment size of some apps.</span></span>

<span data-ttu-id="100e0-173">要启用此工具，请使用项目中的 `<PublishTrimmed>` 设置并发布自包含应用：</span><span class="sxs-lookup"><span data-stu-id="100e0-173">To enable this tool, add the `<PublishTrimmed>` setting in your project and publish a self-contained app:</span></span>

```xml
<PropertyGroup>
  <PublishTrimmed>true</PublishTrimmed>
</PropertyGroup>
```

```console
dotnet publish -r <rid> -c Release
```

<span data-ttu-id="100e0-174">例如，包含的基本“hello world”新控制台项目模板在发布时命中大小约为 70 MB。</span><span class="sxs-lookup"><span data-stu-id="100e0-174">As an example, the basic "hello world" new console project template that is included, when published, hits about 70 MB in size.</span></span> <span data-ttu-id="100e0-175">通过使用 `<PublishTrimmed>`，其大小将减少到约 30 MB。</span><span class="sxs-lookup"><span data-stu-id="100e0-175">By using `<PublishTrimmed>`, that size is reduced to about 30 MB.</span></span>

<span data-ttu-id="100e0-176">请务必考虑到使用反射或相关动态功能的应用程序或框架（包括 ASP.NET Core 和 WPF）通常会在剪裁时损坏。</span><span class="sxs-lookup"><span data-stu-id="100e0-176">It's important to consider that applications or frameworks (including ASP.NET Core and WPF) that use reflection or related dynamic features, will often break when trimmed.</span></span> <span data-ttu-id="100e0-177">发生此损坏是因为链接器不知道此动态行为，并且不能确定反射需要哪些框架类型。</span><span class="sxs-lookup"><span data-stu-id="100e0-177">This breakage occurs because the linker doesn't know about this dynamic behavior and can't determine which framework types are required for reflection.</span></span> <span data-ttu-id="100e0-178">可配置 IL 链接器工具以发现这种情况。</span><span class="sxs-lookup"><span data-stu-id="100e0-178">The IL Linker tool can be configured to be aware of this scenario.</span></span>

<span data-ttu-id="100e0-179">最重要的是，剪裁后务必对应用进行测试。</span><span class="sxs-lookup"><span data-stu-id="100e0-179">Above all else, be sure to test your app after trimming.</span></span>

<span data-ttu-id="100e0-180">有关 IL 链接器工具的详细信息，请参阅[文档](https://aka.ms/dotnet-illink)，或访问 [mono/linker]( https://github.com/mono/linker) 存储库。</span><span class="sxs-lookup"><span data-stu-id="100e0-180">For more information about the IL Linker tool, see the [documentation](https://aka.ms/dotnet-illink) or visit the [mono/linker]( https://github.com/mono/linker) repo.</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="100e0-181">分层编译</span><span class="sxs-lookup"><span data-stu-id="100e0-181">Tiered compilation</span></span>

<span data-ttu-id="100e0-182">.NET Core 3.0 中默认启用了[分层编译](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/) (TC)。</span><span class="sxs-lookup"><span data-stu-id="100e0-182">[Tiered compilation](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/) (TC) is on by default with .NET Core 3.0.</span></span> <span data-ttu-id="100e0-183">此功能使运行时能够更适应地使用实时 (JIT) 编译器来获得更好的性能。</span><span class="sxs-lookup"><span data-stu-id="100e0-183">This feature enables the runtime to more adaptively use the Just-In-Time (JIT) compiler to get better performance.</span></span>

<span data-ttu-id="100e0-184">TC 的主要优势是使（重新）实时编译方法能够牺牲代码质量，更快地生成层，或者以较慢的速度生成更高质量的层。</span><span class="sxs-lookup"><span data-stu-id="100e0-184">The main benefit of TC is to enable (re-)jitting methods with a lower-quality-but-faster tier or a higher-quality-but-slower tier.</span></span> <span data-ttu-id="100e0-185">这有助于提高应用程序在从启动到稳定状态的各个执行阶段的性能。</span><span class="sxs-lookup"><span data-stu-id="100e0-185">This helps increase performance of an application as it goes through various stages of execution, from startup through steady-state.</span></span> <span data-ttu-id="100e0-186">这与非 TC 方法完全不同，其中每种方法均以单一方式进行编译（与高质量层相同），这种方法偏向于稳定状态而不是启动性能。</span><span class="sxs-lookup"><span data-stu-id="100e0-186">This contrasts with the non-TC approach, where every method is compiled a single way (the same as the high-quality tier), which is biased to steady-state over startup performance.</span></span>

<span data-ttu-id="100e0-187">若要启用快速 JIT（第 0 层实时编译的代码），请在项目文件中使用此设置：</span><span class="sxs-lookup"><span data-stu-id="100e0-187">To enable Quick JIT (tier 0 jitted code), use this setting in your project file:</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>true</TieredCompilationQuickJit>
</PropertyGroup>
```

<span data-ttu-id="100e0-188">若要完全禁用 TC，请在项目文件中使用此设置：</span><span class="sxs-lookup"><span data-stu-id="100e0-188">To disable TC completely, use this setting in your project file:</span></span>

```xml
<TieredCompilation>false</TieredCompilation>
```

## <a name="readytorun-images"></a><span data-ttu-id="100e0-189">ReadyToRun 映像</span><span class="sxs-lookup"><span data-stu-id="100e0-189">ReadyToRun images</span></span>

<span data-ttu-id="100e0-190">可以通过将应用程序集编译为 ReadyToRun (R2R) 格式来改进.NET Core 应用程序的启动时间。</span><span class="sxs-lookup"><span data-stu-id="100e0-190">You can improve the startup time of your .NET Core application by compiling your application assemblies as ReadyToRun (R2R) format.</span></span> <span data-ttu-id="100e0-191">R2R 是一种预先 (AOT) 编译形式。</span><span class="sxs-lookup"><span data-stu-id="100e0-191">R2R is a form of ahead-of-time (AOT) compilation.</span></span>

<span data-ttu-id="100e0-192">R2R 二进制文件通过减少应用程序加载时实时 (JIT) 编译器需要执行的工作量来改进启动性能。</span><span class="sxs-lookup"><span data-stu-id="100e0-192">R2R binaries improve startup performance by reducing the amount of work the just-in-time (JIT) compiler needs to do as your application loads.</span></span> <span data-ttu-id="100e0-193">二进制文件包含与 JIT 将生成的内容类似的本机代码。</span><span class="sxs-lookup"><span data-stu-id="100e0-193">The binaries contain similar native code compared to what the JIT would produce.</span></span> <span data-ttu-id="100e0-194">但是，R2R 二进制文件更大，因为它们包含中间语言 (IL) 代码（某些情况下仍需要此代码）和相同代码的本机版本。</span><span class="sxs-lookup"><span data-stu-id="100e0-194">However, R2R binaries are larger because they contain both intermediate language (IL) code, which is still needed for some scenarios, and the native version of the same code.</span></span> <span data-ttu-id="100e0-195">仅当发布面向特定运行时环境 (RID)（如 Linux x64 或 Windows x64）的自包含应用时 R2R 才可用。</span><span class="sxs-lookup"><span data-stu-id="100e0-195">R2R is only available when you publish a self-contained app that targets specific runtime environments (RID) such as Linux x64 or Windows x64.</span></span>

<span data-ttu-id="100e0-196">若要将项目编译为 ReadyToRun，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="100e0-196">To compile your project as ReadyToRun, do the following:</span></span>

01. <span data-ttu-id="100e0-197">向项目中添加 `<PublishReadyToRun>` 设置</span><span class="sxs-lookup"><span data-stu-id="100e0-197">Add the `<PublishReadyToRun>` setting to your project</span></span>

    ```xml
    <PropertyGroup>
      <PublishReadyToRun>true</PublishReadyToRun>
    </PropertyGroup>
    ```

01. <span data-ttu-id="100e0-198">发布自包含应用。</span><span class="sxs-lookup"><span data-stu-id="100e0-198">Publish a self-contained app.</span></span> <span data-ttu-id="100e0-199">例如，此命令将创建适用于 Windows 64 位版本的自包含应用：</span><span class="sxs-lookup"><span data-stu-id="100e0-199">For example, this command creates a self-contained app for the 64-bit version of Windows:</span></span>

    ```console
    dotnet publish -c Release -r win-x64 --self-contained true
    ```

### <a name="cross-platformarchitecture-restrictions"></a><span data-ttu-id="100e0-200">跨平台/体系结构限制</span><span class="sxs-lookup"><span data-stu-id="100e0-200">Cross platform/architecture restrictions</span></span>

<span data-ttu-id="100e0-201">ReadyToRun 编译器当前不支持跨目标。</span><span class="sxs-lookup"><span data-stu-id="100e0-201">The ReadyToRun compiler doesn't currently support cross-targeting.</span></span> <span data-ttu-id="100e0-202">必须在给定的目标上编译。</span><span class="sxs-lookup"><span data-stu-id="100e0-202">You must compile on a given target.</span></span> <span data-ttu-id="100e0-203">例如，如果想要 Windows x64 R2R 映像，需要在该环境中运行发布命令。</span><span class="sxs-lookup"><span data-stu-id="100e0-203">For example, if you want R2R images for Windows x64, you need to run the publish command on that environment.</span></span>

<span data-ttu-id="100e0-204">跨目标的例外情况：</span><span class="sxs-lookup"><span data-stu-id="100e0-204">Exceptions to cross-targeting:</span></span>

- <span data-ttu-id="100e0-205">可以使用 Windows x64 编译 Windows ARM32、ARM64 和 x86 映像。</span><span class="sxs-lookup"><span data-stu-id="100e0-205">Windows x64 can be used to compile Windows ARM32, ARM64, and x86 images.</span></span>
- <span data-ttu-id="100e0-206">可以使用 Windows x86 编译 Windows ARM32 映像。</span><span class="sxs-lookup"><span data-stu-id="100e0-206">Windows x86 can be used to compile Windows ARM32 images.</span></span>
- <span data-ttu-id="100e0-207">可以使用 Linux x64 编译 Linux ARM32 和 ARM64 映像。</span><span class="sxs-lookup"><span data-stu-id="100e0-207">Linux x64 can be used to compile Linux ARM32 and ARM64 images.</span></span>

## <a name="build-copies-dependencies"></a><span data-ttu-id="100e0-208">生成会复制依赖项</span><span class="sxs-lookup"><span data-stu-id="100e0-208">Build copies dependencies</span></span>

<span data-ttu-id="100e0-209">`dotnet build` 命令现在将应用程序的 NuGet 依赖项从 NuGet 缓存复制到生成输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="100e0-209">The `dotnet build` command now copies NuGet dependencies for your application from the NuGet cache to the build output folder.</span></span> <span data-ttu-id="100e0-210">此前，依赖项仅作为 `dotnet publish` 的一部分复制。</span><span class="sxs-lookup"><span data-stu-id="100e0-210">Previously, dependencies were only copied as part of `dotnet publish`.</span></span>

<span data-ttu-id="100e0-211">有些操作，比如链接和 razor 页面发布仍需要发布。</span><span class="sxs-lookup"><span data-stu-id="100e0-211">There are some operations, like linking and razor page publishing that will still require publishing.</span></span>

## <a name="local-tools"></a><span data-ttu-id="100e0-212">本地工具</span><span class="sxs-lookup"><span data-stu-id="100e0-212">Local tools</span></span>

<span data-ttu-id="100e0-213">.NET Core 3.0 引入了本地工具。</span><span class="sxs-lookup"><span data-stu-id="100e0-213">.NET Core 3.0 introduces local tools.</span></span> <span data-ttu-id="100e0-214">本地工具类似于[全局工具](../tools/global-tools.md)，但与磁盘上的特定位置相关联。</span><span class="sxs-lookup"><span data-stu-id="100e0-214">Local tools are similar to [global tools](../tools/global-tools.md) but are associated with a particular location on disk.</span></span> <span data-ttu-id="100e0-215">本地工具在全局范围内不可用，并作为 NuGet 包进行分发。</span><span class="sxs-lookup"><span data-stu-id="100e0-215">Local tools aren't available globally and are distributed as NuGet packages.</span></span>

> [!WARNING]
> <span data-ttu-id="100e0-216">如果尝试使用过 .NET Core 3.0 预览版 1 中的本地工具，例如运行 `dotnet tool restore` 或 `dotnet tool install`，请删除本地工具缓存文件夹。</span><span class="sxs-lookup"><span data-stu-id="100e0-216">If you tried local tools in .NET Core 3.0 Preview 1, such as running `dotnet tool restore` or `dotnet tool install`, delete the local tools cache folder.</span></span> <span data-ttu-id="100e0-217">否则，本地工具将无法在任何较新的版本上运行。</span><span class="sxs-lookup"><span data-stu-id="100e0-217">Otherwise, local tools won't work on any newer release.</span></span> <span data-ttu-id="100e0-218">此文件夹位于：</span><span class="sxs-lookup"><span data-stu-id="100e0-218">This folder is located at:</span></span>
>
> <span data-ttu-id="100e0-219">在 macOS、Linux 上：`rm -r $HOME/.dotnet/toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="100e0-219">On macOS, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span></span>
>
> <span data-ttu-id="100e0-220">在 Windows 上：`rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="100e0-220">On Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span></span>

<span data-ttu-id="100e0-221">本地工具依赖于当前目录中名为 `dotnet-tools.json` 的清单文件。</span><span class="sxs-lookup"><span data-stu-id="100e0-221">Local tools rely on a manifest file name `dotnet-tools.json` in your current directory.</span></span> <span data-ttu-id="100e0-222">此清单文件定义在该文件夹和以下文件夹中可用的工具。</span><span class="sxs-lookup"><span data-stu-id="100e0-222">This manifest file defines the tools to be available at that folder and below.</span></span> <span data-ttu-id="100e0-223">你可以随代码一起分发清单文件，以确保使用代码的任何人都可以还原和使用相同的工具。</span><span class="sxs-lookup"><span data-stu-id="100e0-223">You can distribute the manifest file with your code to ensure that anyone who works with your code can restore and use the same tools.</span></span>

<span data-ttu-id="100e0-224">对于全局工具和本地工具，需要一个兼容的运行时版本。</span><span class="sxs-lookup"><span data-stu-id="100e0-224">For both global and local tools, a compatible version of the runtime is required.</span></span> <span data-ttu-id="100e0-225">目前，NuGet.org 上的许多工具都面向 .NET Core Runtime 2.1。</span><span class="sxs-lookup"><span data-stu-id="100e0-225">Many tools currently on NuGet.org target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="100e0-226">若要在全局范围或本地安装这些工具，仍需要安装 [NET Core 2.1 运行时](https://dotnet.microsoft.com/download/dotnet-core/2.1)。</span><span class="sxs-lookup"><span data-stu-id="100e0-226">To install these tools globally or locally, you would still need to install the [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

## <a name="major-version-roll-forward"></a><span data-ttu-id="100e0-227">主要版本前滚</span><span class="sxs-lookup"><span data-stu-id="100e0-227">Major-version Roll Forward</span></span>

<span data-ttu-id="100e0-228">.NET Core 3.0 引入了一项选择加入功能，该功能允许应用前滚到 .NET Core 最新的主要版本。</span><span class="sxs-lookup"><span data-stu-id="100e0-228">.NET Core 3.0 introduces an opt-in feature that allows your app to roll forward to the latest major version of .NET Core.</span></span> <span data-ttu-id="100e0-229">此外，还添加了一项新设置来控制如何将前滚应用于应用。</span><span class="sxs-lookup"><span data-stu-id="100e0-229">Additionally, a new setting has been added to control how roll forward is applied to your app.</span></span> <span data-ttu-id="100e0-230">这可以通过以下方式配置：</span><span class="sxs-lookup"><span data-stu-id="100e0-230">This can be configured in the following ways:</span></span>

- <span data-ttu-id="100e0-231">项目文件属性：`RollForward`</span><span class="sxs-lookup"><span data-stu-id="100e0-231">Project file property: `RollForward`</span></span>
- <span data-ttu-id="100e0-232">运行时配置文件属性：`rollForward`</span><span class="sxs-lookup"><span data-stu-id="100e0-232">Runtime configuration file property: `rollForward`</span></span>
- <span data-ttu-id="100e0-233">环境变量：`DOTNET_ROLL_FORWARD`</span><span class="sxs-lookup"><span data-stu-id="100e0-233">Environment variable: `DOTNET_ROLL_FORWARD`</span></span>
- <span data-ttu-id="100e0-234">命令行参数：`--roll-forward`</span><span class="sxs-lookup"><span data-stu-id="100e0-234">Command-line argument: `--roll-forward`</span></span>

<span data-ttu-id="100e0-235">必须指定以下值之一。</span><span class="sxs-lookup"><span data-stu-id="100e0-235">One of the following values must be specified.</span></span> <span data-ttu-id="100e0-236">如果省略该设置，则默认值为“Minor”  。</span><span class="sxs-lookup"><span data-stu-id="100e0-236">If the setting is omitted, **Minor** is the default.</span></span>

- <span data-ttu-id="100e0-237">**LatestPatch**</span><span class="sxs-lookup"><span data-stu-id="100e0-237">**LatestPatch**</span></span>\
<span data-ttu-id="100e0-238">前滚到最高补丁版本。</span><span class="sxs-lookup"><span data-stu-id="100e0-238">Roll forward to the highest patch version.</span></span> <span data-ttu-id="100e0-239">这会禁用次要版本前滚。</span><span class="sxs-lookup"><span data-stu-id="100e0-239">This disables minor version roll forward.</span></span>
- <span data-ttu-id="100e0-240">**Minor**</span><span class="sxs-lookup"><span data-stu-id="100e0-240">**Minor**</span></span>\
<span data-ttu-id="100e0-241">如果缺少所请求的次要版本，则前滚到最低的较高次要版本。</span><span class="sxs-lookup"><span data-stu-id="100e0-241">Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="100e0-242">如果存在所请求的次要版本，则使用 **LatestPatch** 策略。</span><span class="sxs-lookup"><span data-stu-id="100e0-242">If the requested minor version is present, then the **LatestPatch** policy is used.</span></span>
- <span data-ttu-id="100e0-243">**Major**</span><span class="sxs-lookup"><span data-stu-id="100e0-243">**Major**</span></span>\
<span data-ttu-id="100e0-244">如果缺少所请求的主要版本，则前滚到最低的较高主要版本和最低的次要版本。</span><span class="sxs-lookup"><span data-stu-id="100e0-244">Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="100e0-245">如果存在所请求的主要版本，则使用 **Minor** 策略。</span><span class="sxs-lookup"><span data-stu-id="100e0-245">If the requested major version is present, then the **Minor** policy is used.</span></span>
- <span data-ttu-id="100e0-246">**LatestMinor**</span><span class="sxs-lookup"><span data-stu-id="100e0-246">**LatestMinor**</span></span>\
<span data-ttu-id="100e0-247">即使存在所请求的次要版本，仍前滚到最高次要版本。</span><span class="sxs-lookup"><span data-stu-id="100e0-247">Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="100e0-248">适用于组件托管方案。</span><span class="sxs-lookup"><span data-stu-id="100e0-248">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="100e0-249">**LatestMajor**</span><span class="sxs-lookup"><span data-stu-id="100e0-249">**LatestMajor**</span></span>\
<span data-ttu-id="100e0-250">即使存在所请求的主要版本，仍前滚到最高主要版本和最高次要版本。</span><span class="sxs-lookup"><span data-stu-id="100e0-250">Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="100e0-251">适用于组件托管方案。</span><span class="sxs-lookup"><span data-stu-id="100e0-251">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="100e0-252">**Disable**</span><span class="sxs-lookup"><span data-stu-id="100e0-252">**Disable**</span></span>\
<span data-ttu-id="100e0-253">不前滚。</span><span class="sxs-lookup"><span data-stu-id="100e0-253">Don't roll forward.</span></span> <span data-ttu-id="100e0-254">仅绑定到指定的版本。</span><span class="sxs-lookup"><span data-stu-id="100e0-254">Only bind to specified version.</span></span> <span data-ttu-id="100e0-255">建议不要将此策略用于一般用途，因为它会禁用前滚到最新补丁的功能。</span><span class="sxs-lookup"><span data-stu-id="100e0-255">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="100e0-256">该值仅建议用于测试。</span><span class="sxs-lookup"><span data-stu-id="100e0-256">This value is only recommended for testing.</span></span>

<span data-ttu-id="100e0-257">除“Disable”设置外，所有设置都将使用可用的最高补丁版本  。</span><span class="sxs-lookup"><span data-stu-id="100e0-257">Besides the **Disable** setting, all settings will use the highest available patch version.</span></span>

## <a name="windows-desktop"></a><span data-ttu-id="100e0-258">Windows 桌面</span><span class="sxs-lookup"><span data-stu-id="100e0-258">Windows desktop</span></span>

<span data-ttu-id="100e0-259">.NET Core 3.0 支持使用 Windows Presentation Foundation (WPF) 和 Windows 窗体的 Windows 桌面应用程序。</span><span class="sxs-lookup"><span data-stu-id="100e0-259">.NET Core 3.0 supports Windows desktop applications using Windows Presentation Foundation (WPF) and Windows Forms.</span></span> <span data-ttu-id="100e0-260">这些框架还支持通过 [XAML 岛](/windows/uwp/xaml-platform/xaml-host-controls)从 Windows UI XAML 库 (WinUI) 使用新式控件和 Fluent 样式。</span><span class="sxs-lookup"><span data-stu-id="100e0-260">These frameworks also support using modern controls and Fluent styling from the Windows UI XAML Library (WinUI) via [XAML islands](/windows/uwp/xaml-platform/xaml-host-controls).</span></span>

<span data-ttu-id="100e0-261">Windows 桌面部件是 Windows .NET Core 3.0 SDK 的一部分。</span><span class="sxs-lookup"><span data-stu-id="100e0-261">The Windows Desktop component is part of the Windows .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="100e0-262">可以使用以下 `dotnet` 命令创建新的 WPF 或 Windows 窗体应用：</span><span class="sxs-lookup"><span data-stu-id="100e0-262">You can create a new WPF or Windows Forms app with the following `dotnet` commands:</span></span>

```console
dotnet new wpf
dotnet new winforms
```

<span data-ttu-id="100e0-263">Visual Studio 2019 添加了适用于 .NET Core 3.0 Windows 窗体和 WPF 的“新建项目”  模板。</span><span class="sxs-lookup"><span data-stu-id="100e0-263">Visual Studio 2019 adds **New Project** templates for .NET Core 3.0 Windows Forms and WPF.</span></span>

<span data-ttu-id="100e0-264">有关如何移植现有 .NET Framework 应用程序的详细信息，请参阅[移植 WPF 项目](../porting/wpf.md)和[移植 Windows 窗体项目](../porting/winforms.md)。</span><span class="sxs-lookup"><span data-stu-id="100e0-264">For more information about how to port an existing .NET Framework application, see [Port WPF projects](../porting/wpf.md) and [Port Windows Forms projects](../porting/winforms.md).</span></span>

## <a name="com-callable-components---windows-desktop"></a><span data-ttu-id="100e0-265">可调用 COM 的组件 - Windows 桌面</span><span class="sxs-lookup"><span data-stu-id="100e0-265">COM-callable components - Windows Desktop</span></span>

<span data-ttu-id="100e0-266">在 Windows 上，现在可以创建可调用 COM 的托管组件。</span><span class="sxs-lookup"><span data-stu-id="100e0-266">On Windows, you can now create COM-callable managed components.</span></span> <span data-ttu-id="100e0-267">在将 .NET Core 与 COM 加载项模型结合使用，以及使用 .NET Framework 提供奇偶校验时，此功能至关重要。</span><span class="sxs-lookup"><span data-stu-id="100e0-267">This capability is critical to use .NET Core with COM add-in models and also to provide parity with .NET Framework.</span></span>

<span data-ttu-id="100e0-268">与将 *mscoree.dll* 用作 COM 服务器的 .NET Framework 不同，.NET Core 将在生成 COM 组件时向 *bin* 目录添加本机启动程序 dll。</span><span class="sxs-lookup"><span data-stu-id="100e0-268">Unlike .NET Framework where the *mscoree.dll* was used as the COM server, .NET Core will add a native launcher dll to the *bin* directory when you build your COM component.</span></span>

<span data-ttu-id="100e0-269">有关如何创建 COM 组件并使用它的示例，请参阅 [COM 演示](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo)。</span><span class="sxs-lookup"><span data-stu-id="100e0-269">For an example of how to create a COM component and consume it, see the [COM Demo](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).</span></span>

## <a name="msix-deployment---windows-desktop"></a><span data-ttu-id="100e0-270">MSIX 部署 - Windows 桌面</span><span class="sxs-lookup"><span data-stu-id="100e0-270">MSIX Deployment - Windows Desktop</span></span>

<span data-ttu-id="100e0-271">[MSIX](https://docs.microsoft.com/windows/msix/) 是新的 Windows 应用程序包格式。</span><span class="sxs-lookup"><span data-stu-id="100e0-271">[MSIX](https://docs.microsoft.com/windows/msix/) is a new Windows application package format.</span></span> <span data-ttu-id="100e0-272">可以使用它将 .NET Core 3.0 桌面应用程序部署到 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="100e0-272">It can be used to deploy .NET Core 3.0 desktop applications to Windows 10.</span></span>

<span data-ttu-id="100e0-273">使用 Visual Studio 2019 中的 [Windows 应用打包项目](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net)，可以创建包含[独立式](../deploying/index.md#self-contained-deployments-scd) .NET Core 应用的 MSIX 包。</span><span class="sxs-lookup"><span data-stu-id="100e0-273">The [Windows Application Packaging Project](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), available in Visual Studio 2019, allows you to create MSIX packages with [self-contained](../deploying/index.md#self-contained-deployments-scd) .NET Core applications.</span></span>

<span data-ttu-id="100e0-274">.NET Core 项目文件必须在 `<RuntimeIdentifiers>` 属性中指定支持的运行时：</span><span class="sxs-lookup"><span data-stu-id="100e0-274">The .NET Core project file must specify the supported runtimes in the `<RuntimeIdentifiers>` property:</span></span>

```xml
<RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
```

## <a name="winforms-high-dpi"></a><span data-ttu-id="100e0-275">WinForms 高 DPI</span><span class="sxs-lookup"><span data-stu-id="100e0-275">WinForms high DPI</span></span>

<span data-ttu-id="100e0-276">.NET Core Windows 窗体应用程序可以使用 <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType> 设置高 DPI 模式。</span><span class="sxs-lookup"><span data-stu-id="100e0-276">.NET Core Windows Forms applications can set high DPI mode with <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType>.</span></span> <span data-ttu-id="100e0-277">`SetHighDpiMode` 方法可设置相应的高 DPI 模式，除非该设置已通过其他方式（例如使用 `App.Manifest` 或在 `Application.Run` 前面使用 P/Invoke）进行设置。</span><span class="sxs-lookup"><span data-stu-id="100e0-277">The `SetHighDpiMode` method sets the corresponding high DPI mode unless the setting has been set by other means like `App.Manifest` or P/Invoke before `Application.Run`.</span></span>

<span data-ttu-id="100e0-278">由 <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType> 枚举表示的可能的 `highDpiMode` 值包括：</span><span class="sxs-lookup"><span data-stu-id="100e0-278">The possible `highDpiMode` values, as expressed by the <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType> enum are:</span></span>

* `DpiUnaware`
* `SystemAware`
* `PerMonitor`
* `PerMonitorV2`
* `DpiUnawareGdiScaled`

<span data-ttu-id="100e0-279">有关高 DPI 模式的详细信息，请参阅[在 Windows 上开发高 DPI 桌面应用程序](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows)。</span><span class="sxs-lookup"><span data-stu-id="100e0-279">For more information about high DPI modes, see [High DPI Desktop Application Development on Windows](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).</span></span>

## <a name="ranges-and-indices"></a><span data-ttu-id="100e0-280">范围和索引</span><span class="sxs-lookup"><span data-stu-id="100e0-280">Ranges and indices</span></span>

<span data-ttu-id="100e0-281">新 <xref:System.Index?displayProperty=nameWithType> 类型可用于编制索引。</span><span class="sxs-lookup"><span data-stu-id="100e0-281">The new <xref:System.Index?displayProperty=nameWithType> type can be used for indexing.</span></span> <span data-ttu-id="100e0-282">可以从从开头开始计数的 `int` 中创建一个类型，也可以使用从末尾开始计数的前缀 `^` 运算符 (C#) 创建一个：</span><span class="sxs-lookup"><span data-stu-id="100e0-282">You can create one from an `int` that counts from the beginning, or with a prefix `^` operator (C#) that counts from the end:</span></span>

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

<span data-ttu-id="100e0-283">此外，还有 <xref:System.Range?displayProperty=nameWithType> 类型，它包含两个 `Index` 值，一个用于开头一个用于结尾，可以使用 `x..y` 范围表达式 (C#) 进行编写。</span><span class="sxs-lookup"><span data-stu-id="100e0-283">There's also the <xref:System.Range?displayProperty=nameWithType> type, which consists of two `Index` values, one for the start and one for the end, and can be written with a `x..y` range expression (C#).</span></span> <span data-ttu-id="100e0-284">然后可以使用 `Range` 编制索引，以便生成一个切片：</span><span class="sxs-lookup"><span data-stu-id="100e0-284">You can then index with a `Range`, which produces a slice:</span></span>

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

<span data-ttu-id="100e0-285">有关详细信息，请参阅[范围和索引教程](../../csharp/tutorials/ranges-indexes.md)。</span><span class="sxs-lookup"><span data-stu-id="100e0-285">For more information, see the [ranges and indices tutorial](../../csharp/tutorials/ranges-indexes.md).</span></span>

## <a name="async-streams"></a><span data-ttu-id="100e0-286">异步流</span><span class="sxs-lookup"><span data-stu-id="100e0-286">Async streams</span></span>

<span data-ttu-id="100e0-287"><xref:System.Collections.Generic.IAsyncEnumerable%601> 类型是 <xref:System.Collections.Generic.IEnumerable%601> 的新异步版本。</span><span class="sxs-lookup"><span data-stu-id="100e0-287">The <xref:System.Collections.Generic.IAsyncEnumerable%601> type is a new asynchronous version of <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="100e0-288">通过该语言，可通过 `IAsyncEnumerable<T>` 执行 `await foreach` 操作来使用其元素，并对其使用 `yield return` 操作来生成元素。</span><span class="sxs-lookup"><span data-stu-id="100e0-288">The language lets you `await foreach` over `IAsyncEnumerable<T>` to consume their elements, and use `yield return` to them to produce elements.</span></span>

<span data-ttu-id="100e0-289">下面的示例演示如何生成和使用异步流。</span><span class="sxs-lookup"><span data-stu-id="100e0-289">The following example demonstrates both production and consumption of async streams.</span></span> <span data-ttu-id="100e0-290">`foreach` 语句为异步语句，它本身使用 `yield return` 为调用方生成异步流。</span><span class="sxs-lookup"><span data-stu-id="100e0-290">The `foreach` statement is async and itself uses `yield return` to produce an async stream for callers.</span></span> <span data-ttu-id="100e0-291">此模式（使用 `yield return`）是生成异步流的建议模型。</span><span class="sxs-lookup"><span data-stu-id="100e0-291">This pattern (using `yield return`) is the recommended model for producing async streams.</span></span>

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result; 
    }
}
```

<span data-ttu-id="100e0-292">除了能够 `await foreach`，还可以创建异步迭代器，例如，一个返回 `IAsyncEnumerable/IAsyncEnumerator` 的迭代器，可以在其中进行 `await` 和 `yield` 操作。</span><span class="sxs-lookup"><span data-stu-id="100e0-292">In addition to being able to `await foreach`, you can also create async iterators, for example, an iterator that returns an `IAsyncEnumerable/IAsyncEnumerator` that you can both `await` and `yield` in.</span></span> <span data-ttu-id="100e0-293">对于需要处理的对象，可以使用各种 BCL 类型（如 `Stream` 和 `Timer`）实现的 `IAsyncDisposable`。</span><span class="sxs-lookup"><span data-stu-id="100e0-293">For objects that need to be disposed, you can use `IAsyncDisposable`, which various BCL types implement, such as `Stream` and `Timer`.</span></span>

<span data-ttu-id="100e0-294">有关详细信息，请参阅[异步流教程](../../csharp/tutorials/generate-consume-asynchronous-stream.md)。</span><span class="sxs-lookup"><span data-stu-id="100e0-294">For more information, see the [async streams tutorial](../../csharp/tutorials/generate-consume-asynchronous-stream.md).</span></span>

## <a name="ieee-floating-point-improvements"></a><span data-ttu-id="100e0-295">IEEE 浮点改进</span><span class="sxs-lookup"><span data-stu-id="100e0-295">IEEE Floating-point improvements</span></span>

<span data-ttu-id="100e0-296">正在更新浮点 API，以符合 [IEEE 754-2008 修订](https://en.wikipedia.org/wiki/IEEE_754-2008_revision)。</span><span class="sxs-lookup"><span data-stu-id="100e0-296">Floating point APIs are being updated to comply with [IEEE 754-2008 revision](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span></span> <span data-ttu-id="100e0-297">这些更改旨在公开所有**必需**操作并确保这些操作在行为上符合 IEEE 规范。有关浮点改进的详细信息，请参阅 [.NET Core 3.0 中的浮点分析和格式化改进](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/)博客文章。</span><span class="sxs-lookup"><span data-stu-id="100e0-297">The goal of these changes is to expose all **required** operations and ensure that they're behaviorally compliant with the IEEE spec. For more information about floating-point improvements, see the [Floating-Point Parsing and Formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) blog post.</span></span>

<span data-ttu-id="100e0-298">分析和格式化修复包括：</span><span class="sxs-lookup"><span data-stu-id="100e0-298">Parsing and formatting fixes include:</span></span>

* <span data-ttu-id="100e0-299">正确分析并舍入任何输入长度。</span><span class="sxs-lookup"><span data-stu-id="100e0-299">Correctly parse and round inputs of any length.</span></span>
* <span data-ttu-id="100e0-300">正确分析并格式化负零。</span><span class="sxs-lookup"><span data-stu-id="100e0-300">Correctly parse and format negative zero.</span></span>
* <span data-ttu-id="100e0-301">通过执行不区分大小写的检查并允许在前面使用可选的 `+`（如果适用），正确分析 `Infinity` 和 `NaN`。</span><span class="sxs-lookup"><span data-stu-id="100e0-301">Correctly parse `Infinity` and `NaN` by doing a case-insensitive check and allowing an optional preceding `+` where applicable.</span></span>

<span data-ttu-id="100e0-302">新的 <xref:System.Math?displayProperty=nameWithType> API 包括：</span><span class="sxs-lookup"><span data-stu-id="100e0-302">New <xref:System.Math?displayProperty=nameWithType> APIs include:</span></span>

* <span data-ttu-id="100e0-303"><xref:System.Math.BitIncrement(System.Double)> 和 <xref:System.Math.BitDecrement(System.Double)></span><span class="sxs-lookup"><span data-stu-id="100e0-303"><xref:System.Math.BitIncrement(System.Double)> and <xref:System.Math.BitDecrement(System.Double)></span></span>\
<span data-ttu-id="100e0-304">相当于 `nextUp` 和 `nextDown` IEEE 运算。</span><span class="sxs-lookup"><span data-stu-id="100e0-304">Corresponds to the `nextUp` and `nextDown` IEEE operations.</span></span> <span data-ttu-id="100e0-305">它们将返回最小的浮点数，该数字大于或小于输入值（分别）。</span><span class="sxs-lookup"><span data-stu-id="100e0-305">They return the smallest floating-point number that compares greater or lesser than the input (respectively).</span></span> <span data-ttu-id="100e0-306">例如，`Math.BitIncrement(0.0)` 将返回 `double.Epsilon`。</span><span class="sxs-lookup"><span data-stu-id="100e0-306">For example, `Math.BitIncrement(0.0)` would return `double.Epsilon`.</span></span>

* <span data-ttu-id="100e0-307"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> 和 <xref:System.Math.MinMagnitude(System.Double,System.Double)></span><span class="sxs-lookup"><span data-stu-id="100e0-307"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> and <xref:System.Math.MinMagnitude(System.Double,System.Double)></span></span>\
<span data-ttu-id="100e0-308">相当于 `maxNumMag` 和 `minNumMag` IEEE 运算，它们将（分别）返回大于或小于两个输入的量值的值。</span><span class="sxs-lookup"><span data-stu-id="100e0-308">Corresponds to the `maxNumMag` and `minNumMag` IEEE operations, they return the value that is greater or lesser in magnitude of the two inputs (respectively).</span></span> <span data-ttu-id="100e0-309">例如，`Math.MaxMagnitude(2.0, -3.0)` 将返回 `-3.0`。</span><span class="sxs-lookup"><span data-stu-id="100e0-309">For example, `Math.MaxMagnitude(2.0, -3.0)` would return `-3.0`.</span></span>

* <xref:System.Math.ILogB(System.Double)>\
<span data-ttu-id="100e0-310">相当于返回整数值的 `logB` IEEE 运算，它将返回输入参数的整数对数（以 2 为底）。</span><span class="sxs-lookup"><span data-stu-id="100e0-310">Corresponds to the `logB` IEEE operation that returns an integral value, it returns the integral base-2 log of the input parameter.</span></span> <span data-ttu-id="100e0-311">此方法实际上与 `floor(log2(x))` 相同，但完成后出现最小舍入错误。</span><span class="sxs-lookup"><span data-stu-id="100e0-311">This method is effectively the same as `floor(log2(x))`, but done with minimal rounding error.</span></span>

* <xref:System.Math.ScaleB(System.Double,System.Int32)>\
<span data-ttu-id="100e0-312">相当于采用整数值的 `scaleB` IEEE 运算，它实际返回 `x * pow(2, n)`，但完成后出现最小舍入错误。</span><span class="sxs-lookup"><span data-stu-id="100e0-312">Corresponds to the `scaleB` IEEE operation that takes an integral value, it returns effectively `x * pow(2, n)`, but is done with minimal rounding error.</span></span>

* <xref:System.Math.Log2(System.Double)>\
<span data-ttu-id="100e0-313">相当于返回（以 2 为底）对数的 `log2` IEEE 运算。</span><span class="sxs-lookup"><span data-stu-id="100e0-313">Corresponds to the `log2` IEEE operation, it returns the base-2 logarithm.</span></span> <span data-ttu-id="100e0-314">它会最小化舍入错误。</span><span class="sxs-lookup"><span data-stu-id="100e0-314">It minimizes rounding error.</span></span>

* <xref:System.Math.FusedMultiplyAdd(System.Double,System.Double,System.Double)>\
<span data-ttu-id="100e0-315">相当于执行乘法加法混合的 `fma` IEEE 运算。</span><span class="sxs-lookup"><span data-stu-id="100e0-315">Corresponds to the `fma` IEEE operation, it performs a fused multiply add.</span></span> <span data-ttu-id="100e0-316">也就是说，它以单个运算的形式执行 `(x * y) + z`，从而最小化舍入错误。</span><span class="sxs-lookup"><span data-stu-id="100e0-316">That is, it does `(x * y) + z` as a single operation, thereby minimizing the rounding error.</span></span> <span data-ttu-id="100e0-317">有关示例是返回 `1e308` 的 `FusedMultiplyAdd(1e308, 2.0, -1e308)`。</span><span class="sxs-lookup"><span data-stu-id="100e0-317">An example would be `FusedMultiplyAdd(1e308, 2.0, -1e308)` which returns `1e308`.</span></span> <span data-ttu-id="100e0-318">常规 `(1e308 * 2.0) - 1e308` 返回 `double.PositiveInfinity`。</span><span class="sxs-lookup"><span data-stu-id="100e0-318">The regular `(1e308 * 2.0) - 1e308` returns `double.PositiveInfinity`.</span></span>

* <xref:System.Math.CopySign(System.Double,System.Double)>\
<span data-ttu-id="100e0-319">相当于 `copySign` IEEE 运算，它返回 `x` 的值但带有符号 `y`。</span><span class="sxs-lookup"><span data-stu-id="100e0-319">Corresponds to the `copySign` IEEE operation, it returns the value of `x`, but with the sign of `y`.</span></span>

## <a name="fast-built-in-json-support"></a><span data-ttu-id="100e0-320">内置的快速 JSON 支持</span><span class="sxs-lookup"><span data-stu-id="100e0-320">Fast built-in JSON support</span></span>

<span data-ttu-id="100e0-321">.NET 用户在很大程度上依赖于 [**Json.NET**](https://www.newtonsoft.com/json) 和其他常用的 JSON 库，它们仍是很好的选择。</span><span class="sxs-lookup"><span data-stu-id="100e0-321">.NET users have largely relied on [**Json.NET**](https://www.newtonsoft.com/json) and other popular JSON libraries, which continue to be good choices.</span></span> <span data-ttu-id="100e0-322">**Json.NET** 使用 .NET 字符串作为其基本数据类型，它实际上是 UTF-16。</span><span class="sxs-lookup"><span data-stu-id="100e0-322">**Json.NET** uses .NET strings as its base datatype, which is UTF-16 under the hood.</span></span>

<span data-ttu-id="100e0-323">新的内置 JSON 支持具有高性能、低分配的特点，并基于 `Span<byte>`。</span><span class="sxs-lookup"><span data-stu-id="100e0-323">The new built-in JSON support is high-performance, low allocation, and based on `Span<byte>`.</span></span> <span data-ttu-id="100e0-324">已向 .NET Core 3.0 <xref:System.Text.Json?displayProperty=nameWithType> 命名空间添加三个新的与 JSON 相关的主类型。</span><span class="sxs-lookup"><span data-stu-id="100e0-324">Three new main JSON-related types have been added to .NET Core 3.0 the <xref:System.Text.Json?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="100e0-325">这些类型*尚*不支持普通旧 CLR 对象 (POCO) 序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="100e0-325">These types don't *yet* support plain old CLR object (POCO) serialization and deserialization.</span></span>

### <a name="utf8jsonreader"></a><span data-ttu-id="100e0-326">Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="100e0-326">Utf8JsonReader</span></span>

<span data-ttu-id="100e0-327"><xref:System.Text.Json.Utf8JsonReader?displayProperty=nameWithType> 是面向 UTF-8 编码 JSON 文本的一个高性能、低分配、只进读取器，从 `ReadOnlySpan<byte>` 读取信息。</span><span class="sxs-lookup"><span data-stu-id="100e0-327"><xref:System.Text.Json.Utf8JsonReader?displayProperty=nameWithType> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="100e0-328">`Utf8JsonReader` 是一种基本的低级类型，可用于生成自定义分析器和反序列化程序。</span><span class="sxs-lookup"><span data-stu-id="100e0-328">The `Utf8JsonReader` is a foundational, low-level type, that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="100e0-329">使用新的 `Utf8JsonReader` 读取 JSON 有效负载要比使用 **Json.NET** 的读取器快 2 倍。</span><span class="sxs-lookup"><span data-stu-id="100e0-329">Reading through a JSON payload using the new `Utf8JsonReader` is 2x faster than using the reader from **Json.NET**.</span></span> <span data-ttu-id="100e0-330">在需要将 JSON 令牌实现为 (UTF-16) 字符串之前，它不会进行分配。</span><span class="sxs-lookup"><span data-stu-id="100e0-330">It doesn't allocate until you need to actualize JSON tokens as (UTF-16) strings.</span></span>

<span data-ttu-id="100e0-331">下面的示例展示了如何读取 Visual Studio Code 创建的 [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) 文件：</span><span class="sxs-lookup"><span data-stu-id="100e0-331">Here is an example of reading through the [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) file created by Visual Studio Code:</span></span>

[!CODE-csharp[Utf8JsonReader](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#PrintJson)]

[!CODE-csharp[Utf8JsonReader](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#PrintJsonCall)]

### <a name="utf8jsonwriter"></a><span data-ttu-id="100e0-332">Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="100e0-332">Utf8JsonWriter</span></span>

<span data-ttu-id="100e0-333"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType> 提供了一种高性能、非缓存的只进方式，通过常见 .NET 类型（例如，`String`、`Int32` 和 `DateTime`）编写 UTF-8 编码的 JSON 文本。</span><span class="sxs-lookup"><span data-stu-id="100e0-333"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType> provides a high-performance, non-cached, forward-only way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="100e0-334">与阅读器一样，编写器是一种基本的低级类型，可用于生成自定义序列化程序。</span><span class="sxs-lookup"><span data-stu-id="100e0-334">Like the reader, the writer is a foundational, low-level type, that can be used to build custom serializers.</span></span> <span data-ttu-id="100e0-335">使用新的 `Utf8JsonWriter` 编写 JSON 有效负载比通过 **Json.NET** 使用编写器快 30-80%，且无需分配。</span><span class="sxs-lookup"><span data-stu-id="100e0-335">Writing a JSON payload using the new `Utf8JsonWriter` is 30-80% faster than using the writer from **Json.NET** and doesn't allocate.</span></span>

### <a name="jsondocument"></a><span data-ttu-id="100e0-336">JsonDocument</span><span class="sxs-lookup"><span data-stu-id="100e0-336">JsonDocument</span></span>

<span data-ttu-id="100e0-337"><xref:System.Text.Json.JsonDocument?displayProperty=nameWithType> 是基于 `Utf8JsonReader` 构建的。</span><span class="sxs-lookup"><span data-stu-id="100e0-337"><xref:System.Text.Json.JsonDocument?displayProperty=nameWithType> is built on top of the `Utf8JsonReader`.</span></span> <span data-ttu-id="100e0-338">`JsonDocument` 可分析 JSON 数据并生成只读文档对象模型 (DOM)，可对模型进行查询，以支持随机访问和枚举。</span><span class="sxs-lookup"><span data-stu-id="100e0-338">The `JsonDocument` provides the ability to parse JSON data and build a read-only Document Object Model (DOM) that can be queried to support random access and enumeration.</span></span> <span data-ttu-id="100e0-339">可以通过 <xref:System.Text.Json.JsonElement> 类型（由 `JsonDocument` 公开为名为 `RootElement` 的属性）访问构成数据的 JSON 元素。</span><span class="sxs-lookup"><span data-stu-id="100e0-339">The JSON elements that compose the data can be accessed via the <xref:System.Text.Json.JsonElement> type that is exposed by the `JsonDocument` as a property called `RootElement`.</span></span> <span data-ttu-id="100e0-340">`JsonElement` 包含 JSON 数组和对象枚举器，以及用于将 JSON 文本转换为常见 .NET 类型的 API。</span><span class="sxs-lookup"><span data-stu-id="100e0-340">The `JsonElement` contains the JSON array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="100e0-341">使用 `JsonDocument` 分析常规 JSON 有效负载并访问其所有成员比使用 **Json.NET** 快 2-3 倍，且为合理大小（即 < 1 MB）的数据所分配的量非常少。</span><span class="sxs-lookup"><span data-stu-id="100e0-341">Parsing a typical JSON payload and accessing all its members using the `JsonDocument` is 2-3x faster than **Json.NET** with little allocations for data that is reasonably sized (that is, < 1 MB).</span></span>

<span data-ttu-id="100e0-342">下面是可用作起始点的 `JsonDocument` 和 `JsonElement` 的示例用法：</span><span class="sxs-lookup"><span data-stu-id="100e0-342">Here is a sample usage of the `JsonDocument` and `JsonElement` that can be used as a starting point:</span></span>

[!CODE-csharp[JsonDocument](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#ReadJson)]

<span data-ttu-id="100e0-343">下面的 C# 8.0 示例展示了如何读取 Visual Studio Code 创建的 [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) 文件：</span><span class="sxs-lookup"><span data-stu-id="100e0-343">Here is a C# 8.0 example of reading through the [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) file created by Visual Studio Code:</span></span>

[!CODE-csharp[JsonDocument](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#ReadJsonCall)]

### <a name="jsonserializer"></a><span data-ttu-id="100e0-344">JsonSerializer</span><span class="sxs-lookup"><span data-stu-id="100e0-344">JsonSerializer</span></span>

<span data-ttu-id="100e0-345"><xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> 在 <xref:System.Text.Json.Utf8JsonReader> 和 <xref:System.Text.Json.Utf8JsonWriter> 的基础上生成，可在处理 JSON 文档和片段时提供快速的低内存序列化选项。</span><span class="sxs-lookup"><span data-stu-id="100e0-345"><xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> is built on top of <xref:System.Text.Json.Utf8JsonReader> and <xref:System.Text.Json.Utf8JsonWriter> to provide a fast, low-memory serialization option when working with JSON documents and fragments.</span></span>

<span data-ttu-id="100e0-346">下面是一个将对象序列化为 JSON 的示例：</span><span class="sxs-lookup"><span data-stu-id="100e0-346">Here is an example of serializing an object to JSON:</span></span>

[!CODE-csharp[JsonSerializer](~/samples/snippets/core/whats-new/whats-new-in-30/cs/JSON.cs#JsonSerialize)]

<span data-ttu-id="100e0-347">下面是一个将 JSON 字符串反序列化为对象的示例。</span><span class="sxs-lookup"><span data-stu-id="100e0-347">Here is an example of deserializing a JSON string to an object.</span></span> <span data-ttu-id="100e0-348">可以使用上一个示例生成的 JSON 字符串：</span><span class="sxs-lookup"><span data-stu-id="100e0-348">You can use the JSON string produced by the previous example:</span></span>

[!CODE-csharp[JsonDeserializer](~/samples/snippets/core/whats-new/whats-new-in-30/cs/JSON.cs#JsonDeserialize)]

## <a name="interop-improvements"></a><span data-ttu-id="100e0-349">互操作性改进</span><span class="sxs-lookup"><span data-stu-id="100e0-349">Interop improvements</span></span>

<span data-ttu-id="100e0-350">.NET Core 3.0 改进了本机 API 互操作性。</span><span class="sxs-lookup"><span data-stu-id="100e0-350">.NET Core 3.0 improves native API interop.</span></span>

### <a name="type-nativelibrary"></a><span data-ttu-id="100e0-351">类型：NativeLibrary</span><span class="sxs-lookup"><span data-stu-id="100e0-351">Type: NativeLibrary</span></span>

<span data-ttu-id="100e0-352"><xref:System.Runtime.InteropServices.NativeLibrary?displayProperty=nameWithType> 提供一个封装，用于加载本机库（使用与 .NET Core P/Invoke 相同的加载逻辑）并提供相关的帮助程序函数，例如 `getSymbol`。</span><span class="sxs-lookup"><span data-stu-id="100e0-352"><xref:System.Runtime.InteropServices.NativeLibrary?displayProperty=nameWithType> provides an encapsulation for loading a native library (using the same load logic as .NET Core P/Invoke) and providing the relevant helper functions such as `getSymbol`.</span></span> <span data-ttu-id="100e0-353">有关代码示例，请参阅 [DLLMap 演示](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin)。</span><span class="sxs-lookup"><span data-stu-id="100e0-353">For a code example, see the [DLLMap Demo](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin).</span></span>

### <a name="windows-native-interop"></a><span data-ttu-id="100e0-354">Windows 本机互操作</span><span class="sxs-lookup"><span data-stu-id="100e0-354">Windows Native Interop</span></span>

<span data-ttu-id="100e0-355">Windows 提供丰富的本机 API，包括平面 C API、COM 和 WinRT 的形式。</span><span class="sxs-lookup"><span data-stu-id="100e0-355">Windows offers a rich native API in the form of flat C APIs, COM, and WinRT.</span></span> <span data-ttu-id="100e0-356">.NET Core 支持 **P/Invoke**，.NET Core 3.0 则增加了**共同创建 COM API** 和**激活 WinRT API** 的功能。</span><span class="sxs-lookup"><span data-stu-id="100e0-356">While .NET Core supports **P/Invoke**, .NET Core 3.0 adds the ability to **CoCreate COM APIs** and **Activate WinRT APIs**.</span></span> <span data-ttu-id="100e0-357">有关代码示例，请参阅 [Excel 演示](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo)。</span><span class="sxs-lookup"><span data-stu-id="100e0-357">For a code example, see the [Excel Demo](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span></span>

## <a name="http2-support"></a><span data-ttu-id="100e0-358">HTTP/2 支持</span><span class="sxs-lookup"><span data-stu-id="100e0-358">HTTP/2 support</span></span>

<span data-ttu-id="100e0-359"><xref:System.Net.Http.HttpClient?displayProperty=nameWithType> 类型支持 HTTP/2 协议。</span><span class="sxs-lookup"><span data-stu-id="100e0-359">The <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> type supports the HTTP/2 protocol.</span></span> <span data-ttu-id="100e0-360">如果启用 HTTP/2，则将通过 TLS/ALPN 协商 HTTP 协议版本，并在服务器选择使用 HTTP/2 时使用。</span><span class="sxs-lookup"><span data-stu-id="100e0-360">If HTTP/2 is enabled, the HTTP protocol version is negotiated via TLS/ALPN, and HTTP/2 is used if the server elects to use it.</span></span>

<span data-ttu-id="100e0-361">默认协议将保留 HTTP/1.1，但可以在两种不同方法中启用 HTTP/2。</span><span class="sxs-lookup"><span data-stu-id="100e0-361">The default protocol remains HTTP/1.1, but HTTP/2 can be enabled in two different ways.</span></span> <span data-ttu-id="100e0-362">首先，可以将 HTTP 请求消息设置为使用 HTTP/2：</span><span class="sxs-lookup"><span data-stu-id="100e0-362">First, you can set the HTTP request message to use HTTP/2:</span></span>

[!CODE-csharp[Http2Request](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#Request)]

<span data-ttu-id="100e0-363">其次，可以更改 <xref:System.Net.Http.HttpClient> 以默认使用 HTTP/2：</span><span class="sxs-lookup"><span data-stu-id="100e0-363">Second, you can change <xref:System.Net.Http.HttpClient> to use HTTP/2 by default:</span></span>

[!CODE-csharp[Http2Client](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#Client)]

<span data-ttu-id="100e0-364">很多时候，在你开发应用程序时要使用未加密的连接。</span><span class="sxs-lookup"><span data-stu-id="100e0-364">Many times when you're developing an application, you want to use an unencrypted connection.</span></span> <span data-ttu-id="100e0-365">如果你知道目标终结点将使用 HTTP/2，你可以为 HTTP/2 打开未加密的连接。</span><span class="sxs-lookup"><span data-stu-id="100e0-365">If you know the target endpoint will be using HTTP/2, you can turn on unencrypted connections for HTTP/2.</span></span> <span data-ttu-id="100e0-366">可以通过将 `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` 环境变量设置为 `1` 或通过在应用上下文中启用它来将其打开：</span><span class="sxs-lookup"><span data-stu-id="100e0-366">You can turn it on by setting the `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` environment variable to `1` or by enabling it in the app context:</span></span>

[!CODE-csharp[Http2Context](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#AppContext)]

## <a name="tls-13--openssl-111-on-linux"></a><span data-ttu-id="100e0-367">Linux 上的 TLS 1.3 和 OpenSSL 1.1.1</span><span class="sxs-lookup"><span data-stu-id="100e0-367">TLS 1.3 & OpenSSL 1.1.1 on Linux</span></span>

<span data-ttu-id="100e0-368">.NET Core 现在可以在给定环境中使用 [OpenSSL 1.1.1 中的 TLS 1.3 支持](https://www.openssl.org/blog/blog/2018/09/11/release111/)。</span><span class="sxs-lookup"><span data-stu-id="100e0-368">.NET Core now takes advantage of [TLS 1.3 support in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), when it's available in a given environment.</span></span> <span data-ttu-id="100e0-369">使用 TLS 1.3：</span><span class="sxs-lookup"><span data-stu-id="100e0-369">With TLS 1.3:</span></span>

* <span data-ttu-id="100e0-370">通过减少客户端和服务器之间所需的往返次数，提高了连接时间。</span><span class="sxs-lookup"><span data-stu-id="100e0-370">Connection times are improved with reduced round trips required between the client and server.</span></span>
* <span data-ttu-id="100e0-371">由于删除了各种过时和不安全的加密算法，提高了安全性。</span><span class="sxs-lookup"><span data-stu-id="100e0-371">Improved security because of the removal of various obsolete and insecure cryptographic algorithms.</span></span>

<span data-ttu-id="100e0-372">.NET Core 3.0 在 Linux 系统上使用 **OpenSSL 1.1.1**、**OpenSSL 1.1.0** 或 **OpenSSL 1.0.2**（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="100e0-372">When available, .NET Core 3.0 uses **OpenSSL 1.1.1**, **OpenSSL 1.1.0**, or **OpenSSL 1.0.2** on a Linux system.</span></span> <span data-ttu-id="100e0-373">当 **OpenSSL 1.1.1** 可用时，<xref:System.Net.Security.SslStream?displayProperty=nameWithType> 和 <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> 类型都将使用 **TLS 1.3**（假定客户端和服务器都支持 **TLS 1.3**）。</span><span class="sxs-lookup"><span data-stu-id="100e0-373">When **OpenSSL 1.1.1** is available, both <xref:System.Net.Security.SslStream?displayProperty=nameWithType> and <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> types will use **TLS 1.3** (assuming both the client and server support **TLS 1.3**).</span></span>

>[!IMPORTANT]
><span data-ttu-id="100e0-374">Windows 和 macOS 尚不支持 TLS 1.3  。</span><span class="sxs-lookup"><span data-stu-id="100e0-374">Windows and macOS do not yet support **TLS 1.3**.</span></span> <span data-ttu-id="100e0-375">当支持可用时，.NET Core 3.0 将在这些操作系统上支持 TLS 1.3  。</span><span class="sxs-lookup"><span data-stu-id="100e0-375">.NET Core 3.0 will support **TLS 1.3** on these operating systems when support becomes available.</span></span>

<span data-ttu-id="100e0-376">下面的 C# 8.0 示例演示在 Ubuntu 18.10 上 .NET Core 3.0 如何连接到 <https://www.cloudflare.com>：</span><span class="sxs-lookup"><span data-stu-id="100e0-376">The following C# 8.0 example demonstrates .NET Core 3.0 on Ubuntu 18.10 connecting to <https://www.cloudflare.com>:</span></span>

[!CODE-csharp[TLSExample](~/samples/snippets/core/whats-new/whats-new-in-30/cs/TLS.cs#TLS)]

## <a name="cryptography-ciphers"></a><span data-ttu-id="100e0-377">加密密码</span><span class="sxs-lookup"><span data-stu-id="100e0-377">Cryptography ciphers</span></span>

<span data-ttu-id="100e0-378">.NET 3.0 增加了对 **AES-GCM** 和 **AES-CCM** 密码的支持（分别使用 <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> 和 <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType> 实现）。</span><span class="sxs-lookup"><span data-stu-id="100e0-378">.NET 3.0 adds support for **AES-GCM** and **AES-CCM** ciphers, implemented with <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> and <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType> respectively.</span></span> <span data-ttu-id="100e0-379">这些算法都是[用于关联数据的认证加密 (AEAD) 算法](https://en.wikipedia.org/wiki/Authenticated_encryption)。</span><span class="sxs-lookup"><span data-stu-id="100e0-379">These algorithms are both [Authenticated Encryption with Association Data (AEAD) algorithms](https://en.wikipedia.org/wiki/Authenticated_encryption).</span></span>

<span data-ttu-id="100e0-380">下面的代码演示了如何使用 `AesGcm` 密码加密和解密随机数据。</span><span class="sxs-lookup"><span data-stu-id="100e0-380">The following code demonstrates using `AesGcm` cipher to encrypt and decrypt random data.</span></span>

[!CODE-csharp[AesGcm](~/samples/snippets/core/whats-new/whats-new-in-30/cs/Cipher.cs#AesGcm)]

## <a name="cryptographic-key-importexport"></a><span data-ttu-id="100e0-381">加密密钥导入/导出</span><span class="sxs-lookup"><span data-stu-id="100e0-381">Cryptographic Key Import/Export</span></span>

<span data-ttu-id="100e0-382">.NET Core 3.0 支持从标准格式导入和导出非对称公钥和私钥。</span><span class="sxs-lookup"><span data-stu-id="100e0-382">.NET Core 3.0 supports the import and export of asymmetric public and private keys from standard formats.</span></span> <span data-ttu-id="100e0-383">你不需要使用 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="100e0-383">You don't need to use an X.509 certificate.</span></span>

<span data-ttu-id="100e0-384">所有密钥类型（例如 *RSA*、*DSA*、*ECDsa* 和 *ECDiffieHellman*）都支持以下格式：</span><span class="sxs-lookup"><span data-stu-id="100e0-384">All key types, such as *RSA*, *DSA*, *ECDsa*, and *ECDiffieHellman*, support the following formats:</span></span>

* <span data-ttu-id="100e0-385">**公钥**</span><span class="sxs-lookup"><span data-stu-id="100e0-385">**Public Key**</span></span>
  * <span data-ttu-id="100e0-386">X.509 SubjectPublicKeyInfo</span><span class="sxs-lookup"><span data-stu-id="100e0-386">X.509 SubjectPublicKeyInfo</span></span>

* <span data-ttu-id="100e0-387">**私钥**</span><span class="sxs-lookup"><span data-stu-id="100e0-387">**Private key**</span></span>
  * <span data-ttu-id="100e0-388">PKCS#8 PrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="100e0-388">PKCS#8 PrivateKeyInfo</span></span>
  * <span data-ttu-id="100e0-389">PKCS#8 EncryptedPrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="100e0-389">PKCS#8 EncryptedPrivateKeyInfo</span></span>

<span data-ttu-id="100e0-390">RSA 密钥还支持：</span><span class="sxs-lookup"><span data-stu-id="100e0-390">RSA keys also support:</span></span>

* <span data-ttu-id="100e0-391">**公钥**</span><span class="sxs-lookup"><span data-stu-id="100e0-391">**Public Key**</span></span>
  * <span data-ttu-id="100e0-392">PKCS#1 RSAPublicKey</span><span class="sxs-lookup"><span data-stu-id="100e0-392">PKCS#1 RSAPublicKey</span></span>

* <span data-ttu-id="100e0-393">**私钥**</span><span class="sxs-lookup"><span data-stu-id="100e0-393">**Private key**</span></span>
  * <span data-ttu-id="100e0-394">PKCS#1 RSAPrivateKey</span><span class="sxs-lookup"><span data-stu-id="100e0-394">PKCS#1 RSAPrivateKey</span></span>

<span data-ttu-id="100e0-395">导出方法生成 DER 编码的二进制数据，导入方法也是如此。</span><span class="sxs-lookup"><span data-stu-id="100e0-395">The export methods produce DER-encoded binary data, and the import methods expect the same.</span></span> <span data-ttu-id="100e0-396">如果密钥以文本友好的 PEM 格式存储，调用方需要在调用导入方法之前对内容进行 base64 解码。</span><span class="sxs-lookup"><span data-stu-id="100e0-396">If a key is stored in the text-friendly PEM format, the caller will need to base64-decode the content before calling an import method.</span></span>

[!CODE-csharp[RSA](~/samples/snippets/core/whats-new/whats-new-in-30/cs/RSA.cs#Rsa)]

<span data-ttu-id="100e0-397">可以使用 <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> 检查 **PKCS#8** 文件，使用 <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType> 检查 **PFX/PKCS#12** 文件。</span><span class="sxs-lookup"><span data-stu-id="100e0-397">**PKCS#8** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> and **PFX/PKCS#12** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>.</span></span> <span data-ttu-id="100e0-398">可以使用 <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType> 操作 **PFX/PKCS#12** 文件。</span><span class="sxs-lookup"><span data-stu-id="100e0-398">**PFX/PKCS#12** files can be manipulated with <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType>.</span></span>

## <a name="serialport-for-linux"></a><span data-ttu-id="100e0-399">适用于 Linux 的 SerialPort</span><span class="sxs-lookup"><span data-stu-id="100e0-399">SerialPort for Linux</span></span>

<span data-ttu-id="100e0-400">.NET Core 3.0 在 Linux 上支持 <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="100e0-400">.NET Core 3.0 supports <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> on Linux.</span></span>

<span data-ttu-id="100e0-401">以前，.NET Core 只支持在 Windows 上使用 `SerialPort`。</span><span class="sxs-lookup"><span data-stu-id="100e0-401">Previously, .NET Core only supported using `SerialPort` on Windows.</span></span>

## <a name="docker-and-cgroup-memory-limits"></a><span data-ttu-id="100e0-402">Docker 和 cgroup 内存限制</span><span class="sxs-lookup"><span data-stu-id="100e0-402">Docker and cgroup memory Limits</span></span>

<span data-ttu-id="100e0-403">从预览版 3 开始，在 Linux 上使用 Docker 运行 .NET Core 3.0 时，可以更好地处理 cgroup 内存限制。</span><span class="sxs-lookup"><span data-stu-id="100e0-403">Starting with Preview 3, running .NET Core 3.0 on Linux with Docker works better with cgroup memory limits.</span></span> <span data-ttu-id="100e0-404">运行具有内存限制的 Docker 容器（例如使用 `docker run -m`）会更改 .NET Core 的行为方式。</span><span class="sxs-lookup"><span data-stu-id="100e0-404">Running a Docker container with memory limits, such as with `docker run -m`, changes how .NET Core behaves.</span></span>

* <span data-ttu-id="100e0-405">默认垃圾回收器 (GC) 堆大小：最大为 20 MB 或容器内存限制的 75%。</span><span class="sxs-lookup"><span data-stu-id="100e0-405">Default Garbage Collector (GC) heap size: maximum of 20 mb or 75% of the memory limit on the container.</span></span>
* <span data-ttu-id="100e0-406">可以将显式大小设置为绝对数或 cgroup 限制的百分比。</span><span class="sxs-lookup"><span data-stu-id="100e0-406">Explicit size can be set as an absolute number or percentage of cgroup limit.</span></span>
* <span data-ttu-id="100e0-407">每个 GC 堆的最小保留段大小为 16 MB。</span><span class="sxs-lookup"><span data-stu-id="100e0-407">Minimum reserved segment size per GC heap is 16 mb.</span></span> <span data-ttu-id="100e0-408">此大小可减少在计算机上创建的堆数量。</span><span class="sxs-lookup"><span data-stu-id="100e0-408">This size reduces the number of heaps that are created on machines.</span></span>

## <a name="smaller-garbage-collection-heap-sizes"></a><span data-ttu-id="100e0-409">垃圾回收堆大小减小</span><span class="sxs-lookup"><span data-stu-id="100e0-409">Smaller Garbage Collection heap sizes</span></span>

<span data-ttu-id="100e0-410">垃圾回收器的默认堆大小已减小，以使 .NET Core 使用更少的内存。</span><span class="sxs-lookup"><span data-stu-id="100e0-410">The Garbage Collector's default heap size has been reduced resulting in .NET Core using less memory.</span></span> <span data-ttu-id="100e0-411">此更改更符合具有现代处理器缓存大小的第 0 代分配预算。</span><span class="sxs-lookup"><span data-stu-id="100e0-411">This change better aligns with the generation 0 allocation budget with modern processor cache sizes.</span></span>

## <a name="garbage-collection-large-page-support"></a><span data-ttu-id="100e0-412">垃圾回收大型页面支持</span><span class="sxs-lookup"><span data-stu-id="100e0-412">Garbage Collection Large Page support</span></span>

<span data-ttu-id="100e0-413">大型页面（也称为 Linux 上的巨型页面）是一项功能，其中操作系统能够建立大于本机页面大小（通常为 4K）的内存区域，以提高请求这些大型页面的应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="100e0-413">Large Pages (also known as Huge Pages on Linux) is a feature where the operating system is able to establish memory regions larger than the native page size (often 4K) to improve performance of the application requesting these large pages.</span></span>

<span data-ttu-id="100e0-414">现在可以使用 **GCLargePages** 设置将垃圾回收器配置为一项选择加入功能，以选择在 Windows 上分配大型页面。</span><span class="sxs-lookup"><span data-stu-id="100e0-414">The Garbage Collector can now be configured with the **GCLargePages** setting as an opt-in feature to choose to allocate large pages on Windows.</span></span>

## <a name="gpio-support-for-raspberry-pi"></a><span data-ttu-id="100e0-415">对 Raspberry Pi 的 GPIO 支持</span><span class="sxs-lookup"><span data-stu-id="100e0-415">GPIO Support for Raspberry Pi</span></span>

<span data-ttu-id="100e0-416">已向 NuGet 发布了两个可用于 GPIO 编程的包：</span><span class="sxs-lookup"><span data-stu-id="100e0-416">Two packages have been released to NuGet that you can use for GPIO programming:</span></span>

* [<span data-ttu-id="100e0-417">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="100e0-417">System.Device.Gpio</span></span>](https://www.nuget.org/packages/System.Device.Gpio)
* [<span data-ttu-id="100e0-418">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="100e0-418">Iot.Device.Bindings</span></span>](https://www.nuget.org/packages/Iot.Device.Bindings)

<span data-ttu-id="100e0-419">GPIO 包包括用于 *GPIO*、*SPI*、*I2C* 和 *PWM* 设备的 API。</span><span class="sxs-lookup"><span data-stu-id="100e0-419">The GPIO packages include APIs for *GPIO*, *SPI*, *I2C*, and *PWM* devices.</span></span> <span data-ttu-id="100e0-420">IoT 绑定包包括设备绑定。</span><span class="sxs-lookup"><span data-stu-id="100e0-420">The IoT bindings package includes device bindings.</span></span> <span data-ttu-id="100e0-421">有关详细信息，请参阅[设备 GitHub 存储库](https://github.com/dotnet/iot/blob/master/src/devices/)。</span><span class="sxs-lookup"><span data-stu-id="100e0-421">For more information, see the [devices GitHub repo](https://github.com/dotnet/iot/blob/master/src/devices/).</span></span>

## <a name="arm64-linux-support"></a><span data-ttu-id="100e0-422">ARM64 Linux 支持</span><span class="sxs-lookup"><span data-stu-id="100e0-422">ARM64 Linux support</span></span>

<span data-ttu-id="100e0-423">.NET Core 3.0 增加了对 ARM64 for Linux 的支持。</span><span class="sxs-lookup"><span data-stu-id="100e0-423">.NET Core 3.0 adds support for ARM64 for Linux.</span></span> <span data-ttu-id="100e0-424">ARM64 的主要用例是当前的 IoT 场景。</span><span class="sxs-lookup"><span data-stu-id="100e0-424">The primary use case for ARM64 is currently with IoT scenarios.</span></span> <span data-ttu-id="100e0-425">有关详细信息，请参阅 [.NET Core ARM64 状态](https://github.com/dotnet/announcements/issues/82)。</span><span class="sxs-lookup"><span data-stu-id="100e0-425">For more information, see [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82).</span></span>

<span data-ttu-id="100e0-426">[ARM64 上适用于 .NET Core 的 Docker 映像](https://hub.docker.com/r/microsoft/dotnet/)可用于 Alpine、Debian 和 Ubuntu。</span><span class="sxs-lookup"><span data-stu-id="100e0-426">[Docker images for .NET Core on ARM64](https://hub.docker.com/r/microsoft/dotnet/) are available for Alpine, Debian, and Ubuntu.</span></span>

> [!NOTE]
> <span data-ttu-id="100e0-427">**ARM64** 尚未提供 Windows 支持。</span><span class="sxs-lookup"><span data-stu-id="100e0-427">**ARM64** Windows support isn't yet available.</span></span>
