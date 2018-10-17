---
title: 跨平台目标
description: 有关创建跨平台.NET 库的最佳做法建议。
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 72fa891d5b1054af485a98d89b4efb11d6b0018b
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374880"
---
# <a name="cross-platform-targeting"></a><span data-ttu-id="60ea5-103">跨平台目标</span><span class="sxs-lookup"><span data-stu-id="60ea5-103">Cross-platform targeting</span></span>

<span data-ttu-id="60ea5-104">新式.NET 支持多个操作系统和设备。</span><span class="sxs-lookup"><span data-stu-id="60ea5-104">Modern .NET supports multiple operating systems and devices.</span></span> <span data-ttu-id="60ea5-105">无论它们是在构建 ASP.NET 网站托管在 Azure 中或.NET 游戏在 Unity 中的.NET 开放源代码库来支持尽可能多的开发人员至关重要。</span><span class="sxs-lookup"><span data-stu-id="60ea5-105">It's important for .NET open-source libraries to support as many developers as possible, whether they're building an ASP.NET website hosted in Azure, or a .NET game in Unity.</span></span>

## <a name="net-standard"></a><span data-ttu-id="60ea5-106">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="60ea5-106">.NET Standard</span></span>

<span data-ttu-id="60ea5-107">.NET standard 是将跨平台支持添加到.NET 库的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="60ea5-107">.NET Standard is the best way to add cross-platform support to a .NET library.</span></span> <span data-ttu-id="60ea5-108">[.NET standard](../net-standard.md)是一种规范的所有.NET 实现可用的.NET Api。</span><span class="sxs-lookup"><span data-stu-id="60ea5-108">[.NET Standard](../net-standard.md) is a specification of .NET APIs that are available on all .NET implementations.</span></span> <span data-ttu-id="60ea5-109">面向.NET Standard，可以生成约束使用的.NET Standard，这意味着可以使用实现该版本的.NET Standard 的所有平台的给定版本中的 Api 的库。</span><span class="sxs-lookup"><span data-stu-id="60ea5-109">Targeting .NET Standard lets you produce libraries that are constrained to use APIs that are in a given version of .NET Standard, which means it's usable by all platforms that implement that version of the .NET Standard.</span></span>

<span data-ttu-id="60ea5-110">![.NET 标准](./media/cross-platform-targeting/platforms-netstandard.png ".NET 标准")</span><span class="sxs-lookup"><span data-stu-id="60ea5-110">![.NET Standard](./media/cross-platform-targeting/platforms-netstandard.png ".NET Standard")</span></span>

<span data-ttu-id="60ea5-111">定目标到.NET Standard，并已成功编译你的项目，并不能保证库将在所有平台上成功运行：</span><span class="sxs-lookup"><span data-stu-id="60ea5-111">Targeting .NET Standard, and successfully compiling your project, doesn't guarantee the library will run successfully on all platforms:</span></span>

1. <span data-ttu-id="60ea5-112">特定于平台的 Api 将在其他平台上失败。</span><span class="sxs-lookup"><span data-stu-id="60ea5-112">Platform-specific APIs will fail on other platforms.</span></span> <span data-ttu-id="60ea5-113">例如，<xref:Microsoft.Win32.Registry?displayProperty=nameWithType>将在 Windows 上成功并引发<xref:System.PlatformNotSupportedException>任何其他操作系统上使用时。</span><span class="sxs-lookup"><span data-stu-id="60ea5-113">For example, <xref:Microsoft.Win32.Registry?displayProperty=nameWithType> will succeed on Windows and throw <xref:System.PlatformNotSupportedException> when used on any other OS.</span></span>
2. <span data-ttu-id="60ea5-114">Api 的行为可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="60ea5-114">APIs can behave differently.</span></span> <span data-ttu-id="60ea5-115">例如，反射 Api 都具有不同的性能特征时应用程序使用 iOS 或 UWP 预的实时编译。</span><span class="sxs-lookup"><span data-stu-id="60ea5-115">For example, reflection APIs have different performance characteristics when an application uses ahead-of-time compilation on iOS or UWP.</span></span>

> [!TIP]
> <span data-ttu-id="60ea5-116">.NET 团队[提供了 Roslyn 分析器](../analyzers/api-analyzer.md)来帮助您发现可能存在的问题。</span><span class="sxs-lookup"><span data-stu-id="60ea5-116">The .NET team [offers a Roslyn analyzer](../analyzers/api-analyzer.md) to help you discover possible issues.</span></span>

<span data-ttu-id="60ea5-117">**执行 ✔️**开头包括`netstandard2.0`目标。</span><span class="sxs-lookup"><span data-stu-id="60ea5-117">**✔️ DO** start with including a `netstandard2.0` target.</span></span>

> <span data-ttu-id="60ea5-118">最常规用途库不应需要之外.NET Standard 2.0 的 Api。</span><span class="sxs-lookup"><span data-stu-id="60ea5-118">Most general-purpose libraries should not need APIs outside of .NET Standard 2.0.</span></span> <span data-ttu-id="60ea5-119">.NET standard 2.0 支持的所有新式平台，支持多个平台使用一个目标的建议的方法。</span><span class="sxs-lookup"><span data-stu-id="60ea5-119">.NET Standard 2.0 is supported by all modern platforms and is the recommended way to support multiple platforms with one target.</span></span>

<span data-ttu-id="60ea5-120">**请避免 ❌**包括`netstandard1.x`目标。</span><span class="sxs-lookup"><span data-stu-id="60ea5-120">**❌ AVOID** including a `netstandard1.x` target.</span></span>

> <span data-ttu-id="60ea5-121">.NET standard 1.x 分布式为一组精细的 NuGet 包，将创建大型包依赖项关系图并导致生成时下载的包大量的开发人员。</span><span class="sxs-lookup"><span data-stu-id="60ea5-121">.NET Standard 1.x is distributed as a granular set of NuGet packages, which creates a large package dependency graph and results in developers downloading a lot of packages when building.</span></span> <span data-ttu-id="60ea5-122">新式.NET 平台，包括.NET Framework 4.6.1、 UWP 和 Xamarin，所有支持.NET Standard 2.0。</span><span class="sxs-lookup"><span data-stu-id="60ea5-122">Modern .NET platforms, including .NET Framework 4.6.1, UWP and Xamarin, all support .NET Standard 2.0.</span></span> <span data-ttu-id="60ea5-123">您应仅面向.NET Standard 1.x 如果需要专门面向较旧的平台。</span><span class="sxs-lookup"><span data-stu-id="60ea5-123">You should only target .NET Standard 1.x if you specifically need to target an older platform.</span></span>

<span data-ttu-id="60ea5-124">**执行 ✔️**包括`netstandard2.0`如果需要面向`netstandard1.x`目标。</span><span class="sxs-lookup"><span data-stu-id="60ea5-124">**✔️ DO** include a `netstandard2.0` target if you require a `netstandard1.x` target.</span></span>

> <span data-ttu-id="60ea5-125">将使用所有平台支持.NET Standard 2.0`netstandard2.0`目标并且受益于具有较小的包关系图，而较旧的平台仍将起作用并回退为使用`netstandard1.x`目标。</span><span class="sxs-lookup"><span data-stu-id="60ea5-125">All platforms supporting .NET Standard 2.0 will use the `netstandard2.0` target and benefit from having a smaller package graph while older platforms will still work and fall back to using the `netstandard1.x` target.</span></span>

<span data-ttu-id="60ea5-126">**不这样做 ❌**包括.NET Standard 目标，如果库依赖于特定于平台的应用程序模型。</span><span class="sxs-lookup"><span data-stu-id="60ea5-126">**❌ DO NOT** include a .NET Standard target if the library relies on a platform-specific app model.</span></span>

> <span data-ttu-id="60ea5-127">例如，UWP 控件工具包库依赖于才可在 UWP 上的应用程序模型。</span><span class="sxs-lookup"><span data-stu-id="60ea5-127">For example, a UWP control toolkit library depends on an app model that is only available on UWP.</span></span> <span data-ttu-id="60ea5-128">特定于应用模型 Api 不会使用.NET Standard 中可用。</span><span class="sxs-lookup"><span data-stu-id="60ea5-128">App model specific APIs will not be available in .NET Standard.</span></span>

## <a name="multi-targeting"></a><span data-ttu-id="60ea5-129">多目标</span><span class="sxs-lookup"><span data-stu-id="60ea5-129">Multi-targeting</span></span>

<span data-ttu-id="60ea5-130">有时您需要从库中访问特定于框架的 Api。</span><span class="sxs-lookup"><span data-stu-id="60ea5-130">Sometimes you need to access framework-specific APIs from your libraries.</span></span> <span data-ttu-id="60ea5-131">若要调用特定于框架的 Api 的最佳方法使用多目标，这对于许多生成你的项目[.NET 目标框架](../frameworks.md)而不是仅为其中一个。</span><span class="sxs-lookup"><span data-stu-id="60ea5-131">The best way to call framework-specific APIs is using multi-targeting, which builds your project for many [.NET target frameworks](../frameworks.md) rather than for just one.</span></span>

<span data-ttu-id="60ea5-132">若要屏蔽使用者无需为单个框架构建，您应该努力拥有.NET 标准输出以及一个或多个特定于框架的输出。</span><span class="sxs-lookup"><span data-stu-id="60ea5-132">To shield your consumers from having to build for individual frameworks, you should strive to have a .NET Standard output plus one or more framework-specific outputs.</span></span> <span data-ttu-id="60ea5-133">利用多重目标的所有程序集被打包到一个 NuGet 包内。</span><span class="sxs-lookup"><span data-stu-id="60ea5-133">With multi-targeting, all assemblies are packaged inside a single NuGet package.</span></span> <span data-ttu-id="60ea5-134">然后，使用者可以引用同一个包，NuGet 将选择相应的实现。</span><span class="sxs-lookup"><span data-stu-id="60ea5-134">Consumers can then reference the same package and NuGet will pick the appropriate implementation.</span></span> <span data-ttu-id="60ea5-135">.NET Standard 库可用作回退库使用无处不在但其中将 NuGet 包提供特定于框架的实现情况除外。</span><span class="sxs-lookup"><span data-stu-id="60ea5-135">Your .NET Standard library serves as the fallback library that is used everywhere, except for the cases where your NuGet package offers a framework-specific implementation.</span></span> <span data-ttu-id="60ea5-136">多目标，可在代码中使用条件编译，并调用特定于框架的 Api。</span><span class="sxs-lookup"><span data-stu-id="60ea5-136">Multi-targeting allows you to use conditional compilation in your code and call framework-specific APIs.</span></span>

<span data-ttu-id="60ea5-137">![具有多个程序集的 NuGet 包](./media/cross-platform-targeting/nuget-package-multiple-assemblies.png "具有多个程序集的 NuGet 包")</span><span class="sxs-lookup"><span data-stu-id="60ea5-137">![NuGet package with multiple assemblies](./media/cross-platform-targeting/nuget-package-multiple-assemblies.png "NuGet package with multiple assemblies")</span></span>

<span data-ttu-id="60ea5-138">**请考虑 ✔️**面向除了.NET Standard 的.NET 实现。</span><span class="sxs-lookup"><span data-stu-id="60ea5-138">**✔️ CONSIDER** targeting .NET implementations in addition to .NET Standard.</span></span>

> <span data-ttu-id="60ea5-139">面向.NET 实现可以调用外部.NET Standard 的特定于平台的 Api。</span><span class="sxs-lookup"><span data-stu-id="60ea5-139">Targeting .NET implementations allows you to call platform-specific APIs that are outside of .NET Standard.</span></span>
>
> <span data-ttu-id="60ea5-140">执行此操作时不删除对.NET Standard 的支持。</span><span class="sxs-lookup"><span data-stu-id="60ea5-140">Do not drop support for .NET Standard when you do this.</span></span> <span data-ttu-id="60ea5-141">相反，引发的实现，提供功能的 Api。</span><span class="sxs-lookup"><span data-stu-id="60ea5-141">Instead, throw from the implementation and offer capability APIs.</span></span> <span data-ttu-id="60ea5-142">这样一来，你的库可以在任意位置，并支持运行时启动的功能。</span><span class="sxs-lookup"><span data-stu-id="60ea5-142">This way, your library can be used anywhere and supports runtime light-up of features.</span></span>

<span data-ttu-id="60ea5-143">**请避免 ❌**使用面向多个与.NET Standard，如果你的源代码的所有目标相同。</span><span class="sxs-lookup"><span data-stu-id="60ea5-143">**❌ AVOID** using multi-targeting with .NET Standard if your source code is the same for all targets.</span></span>

> <span data-ttu-id="60ea5-144">.NET 标准的程序集将自动供 NuGet。</span><span class="sxs-lookup"><span data-stu-id="60ea5-144">The .NET Standard assembly will automatically be used by NuGet.</span></span> <span data-ttu-id="60ea5-145">面向单个.NET 实现会增加`*.nupkg`大小无任何好处。</span><span class="sxs-lookup"><span data-stu-id="60ea5-145">Targeting individual .NET implementations increases the `*.nupkg` size for no benefit.</span></span>

<span data-ttu-id="60ea5-146">**请考虑 ✔️**添加的目标`net461`时，您能够提供`netstandard2.0`目标。</span><span class="sxs-lookup"><span data-stu-id="60ea5-146">**✔️ CONSIDER** adding a target for `net461` when you're offering a `netstandard2.0` target.</span></span> 

> <span data-ttu-id="60ea5-147">使用.NET Framework 中的.NET Standard 2.0 已在.NET Framework 4.7.2 中已解决一些问题。</span><span class="sxs-lookup"><span data-stu-id="60ea5-147">Using .NET Standard 2.0 from .NET Framework has some issues that were addressed in .NET Framework 4.7.2.</span></span> <span data-ttu-id="60ea5-148">可以改进仍在使用.NET Framework 4.6.1-4.7.1 通过为其提供专为.NET Framework 4.6.1 的二进制文件的开发人员的体验。</span><span class="sxs-lookup"><span data-stu-id="60ea5-148">You can improve the experience for developers that are still on .NET Framework 4.6.1 - 4.7.1 by offering them a binary that is built for .NET Framework 4.6.1.</span></span>

<span data-ttu-id="60ea5-149">**✔️ 执行**分发你的库使用 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="60ea5-149">**✔️ DO** distribute your library using a NuGet package.</span></span>

> <span data-ttu-id="60ea5-150">NuGet 将为开发人员选择最佳的目标和防护它们无需选择相应的实现。</span><span class="sxs-lookup"><span data-stu-id="60ea5-150">NuGet will select the best target for the developer and shield them having to pick the appropriate implementation.</span></span>

<span data-ttu-id="60ea5-151">**执行 ✔️**使用项目文件的`TargetFrameworks`时面向多个属性。</span><span class="sxs-lookup"><span data-stu-id="60ea5-151">**✔️ DO** use a project file's `TargetFrameworks` property when multi-targeting.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <!-- This project will output netstandard2.0 and net461 assemblies -->
    <TargetFrameworks>netstandard2.0;net461</TargetFrameworks>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="60ea5-152">**请考虑 ✔️**使用[MSBuild.Sdk.Extras](https://github.com/onovotny/MSBuildSdkExtras)时面向多个 UWP 和 Xamarin 如极大地简化了你的项目文件。</span><span class="sxs-lookup"><span data-stu-id="60ea5-152">**✔️ CONSIDER** using [MSBuild.Sdk.Extras](https://github.com/onovotny/MSBuildSdkExtras) when multi-targeting for UWP and Xamarin as it greatly simplifies your project file.</span></span>

## <a name="older-targets"></a><span data-ttu-id="60ea5-153">较旧的目标</span><span class="sxs-lookup"><span data-stu-id="60ea5-153">Older targets</span></span>

<span data-ttu-id="60ea5-154">.NET 支持.NET Framework 的目标是长时间超出不再常用的平台以及支持的版本。</span><span class="sxs-lookup"><span data-stu-id="60ea5-154">.NET supports targeting versions of the .NET Framework that are long out of support as well as platforms that are no longer commonly used.</span></span> <span data-ttu-id="60ea5-155">虽然让您库的工作上无需解决缺少 Api 的多个目标，可以添加大量开销不存在值。</span><span class="sxs-lookup"><span data-stu-id="60ea5-155">While there's value in making your library work on as many targets as possible, having to work around missing APIs can add significant overhead.</span></span> <span data-ttu-id="60ea5-156">我们相信某些框架，也无法再以目标，值得考虑其范围和限制。</span><span class="sxs-lookup"><span data-stu-id="60ea5-156">We believe certain frameworks are no longer worth targeting, considering their reach and limitations.</span></span>

<span data-ttu-id="60ea5-157">**不这样做 ❌**包括可移植类库 (PCL) 目标。</span><span class="sxs-lookup"><span data-stu-id="60ea5-157">**❌ DO NOT** include a Portable Class Library (PCL) target.</span></span> <span data-ttu-id="60ea5-158">例如 `portable-net45+win8+wpa81+wp8`。</span><span class="sxs-lookup"><span data-stu-id="60ea5-158">For example, `portable-net45+win8+wpa81+wp8`.</span></span>

> <span data-ttu-id="60ea5-159">.NET standard 是支持跨平台.NET 库的最新方法，并替换 Pcl。</span><span class="sxs-lookup"><span data-stu-id="60ea5-159">.NET Standard is the modern way to support cross-platform .NET libraries and replaces PCLs.</span></span>

<span data-ttu-id="60ea5-160">**不这样做 ❌**包括不再受支持的.NET 平台的目标。</span><span class="sxs-lookup"><span data-stu-id="60ea5-160">**❌ DO NOT** include targets for .NET platforms that are no longer supported.</span></span> <span data-ttu-id="60ea5-161">例如：`SL4`、`WP`。</span><span class="sxs-lookup"><span data-stu-id="60ea5-161">For example, `SL4`, `WP`.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="60ea5-162">[上一页](./get-started.md)
[下一页](./strong-naming.md)</span><span class="sxs-lookup"><span data-stu-id="60ea5-162">[Previous](./get-started.md)
[Next](./strong-naming.md)</span></span>
