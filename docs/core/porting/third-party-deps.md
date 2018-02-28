---
title: "移植到 .NET Core - 分析第三方依赖项"
description: "了解如何分析第三方依赖项，以便将项目从 .NET Framework 移植到 .NET Core。"
author: cartermp
ms.author: mairaw
ms.date: 02/15/2018
ms.topic: article
ms.prod: .net-core
ms.assetid: b446e9e0-72f6-48f6-92c6-70ad0ce3f86a
ms.workload:
- dotnetcore
ms.openlocfilehash: 365aff32de75d0658027c35675ed58a2b23691c5
ms.sourcegitcommit: 96cc82cac4650adfb65ba351506d8a8fbcd17b5c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
# <a name="analyze-your-third-party-dependencies"></a><span data-ttu-id="96ef5-103">分析第三方依赖项</span><span class="sxs-lookup"><span data-stu-id="96ef5-103">Analyze your third-party dependencies</span></span>

<span data-ttu-id="96ef5-104">如果希望将代码移植到 .NET Core 或 .NET Standard，移植过程的第一步是了解第三方依赖项。</span><span class="sxs-lookup"><span data-stu-id="96ef5-104">If you're looking to port your code to .NET Core or .NET Standard, the first step in the porting process is to understand your third-party dependencies.</span></span> <span data-ttu-id="96ef5-105">第三方依赖项是在项目中引用的 [NuGet 包](#analyze-referenced-nuget-packages-on-your-project)或 [DLL](#analyze-dependencies-that-arent-nuget-packages)。</span><span class="sxs-lookup"><span data-stu-id="96ef5-105">Third-party dependencies are either [NuGet packages](#analyze-referenced-nuget-packages-on-your-project) or [DLLs](#analyze-dependencies-that-arent-nuget-packages) you're referencing in your project.</span></span> <span data-ttu-id="96ef5-106">评估每个依赖项并为与 .NET Core 不兼容的依赖项制定应变计划。</span><span class="sxs-lookup"><span data-stu-id="96ef5-106">Evaluate each dependency and develop a contingency plan for the dependencies that aren't compatible with .NET Core.</span></span> <span data-ttu-id="96ef5-107">本文介绍了如何确定依赖项是否与 .NET Core 兼容。</span><span class="sxs-lookup"><span data-stu-id="96ef5-107">This article shows you how to determine if the dependency is compatible with .NET Core.</span></span>

## <a name="analyze-referenced-nuget-packages-in-your-project"></a><span data-ttu-id="96ef5-108">分析项目中引用的 NuGet 包</span><span class="sxs-lookup"><span data-stu-id="96ef5-108">Analyze referenced NuGet packages in your project</span></span>

<span data-ttu-id="96ef5-109">如果正在项目中引用 NuGet 包，需要验证它们是否与 .NET Core 兼容。</span><span class="sxs-lookup"><span data-stu-id="96ef5-109">If you're referencing NuGet packages in your project, you need to verify if they're compatible with .NET Core.</span></span>
<span data-ttu-id="96ef5-110">可通过两种方式来实现此目的：</span><span class="sxs-lookup"><span data-stu-id="96ef5-110">There are two ways to accomplish that:</span></span>

* <span data-ttu-id="96ef5-111">[使用 NuGet 包资源管理器应用](#analyze-nuget-packages-using-nuget-package-explorer)（最可靠的方法）。</span><span class="sxs-lookup"><span data-stu-id="96ef5-111">[Using the NuGet Package Explorer app](#analyze-nuget-packages-using-nuget-package-explorer) (the most reliable method).</span></span>
* <span data-ttu-id="96ef5-112">[使用 nuget.org 站点](#analyze-nuget-packages-using-nugetorg)。</span><span class="sxs-lookup"><span data-stu-id="96ef5-112">[Using the nuget.org site](#analyze-nuget-packages-using-nugetorg).</span></span>

<span data-ttu-id="96ef5-113">分析包后，如果它们与 .NET Core 不兼容并且仅面向 .NET Framework，则可检查 [.NET Framework 兼容性模式](#net-framework-compatibility-mode)是否能有助于移植过程。</span><span class="sxs-lookup"><span data-stu-id="96ef5-113">After analyzing the packages, if they're not compatible with .NET Core and only target .NET Framework, you can check if the [.NET Framework compatibility mode](#net-framework-compatibility-mode) can help with your porting process.</span></span>

### <a name="analyze-nuget-packages-using-nuget-package-explorer"></a><span data-ttu-id="96ef5-114">使用 NuGet 包资源管理器分析 NuGet 包</span><span class="sxs-lookup"><span data-stu-id="96ef5-114">Analyze NuGet packages using NuGet Package Explorer</span></span>

<span data-ttu-id="96ef5-115">NuGet 包本身就是一组包含特定于平台的程序集的文件夹。</span><span class="sxs-lookup"><span data-stu-id="96ef5-115">A NuGet package is itself a set of folders that contain platform-specific assemblies.</span></span> <span data-ttu-id="96ef5-116">所以需要检查包中是否有包含兼容程序集的文件夹。</span><span class="sxs-lookup"><span data-stu-id="96ef5-116">So you need to check if there's a folder that contains a compatible assembly inside the package.</span></span>

<span data-ttu-id="96ef5-117">检查 NuGet 包文件夹最简单方法是使用 [NuGet 包资源管理器](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer)工具。</span><span class="sxs-lookup"><span data-stu-id="96ef5-117">The easiest way to inspect NuGet Package folders is to use the [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) tool.</span></span> <span data-ttu-id="96ef5-118">安装完成后，使用以下步骤查看文件夹名称：</span><span class="sxs-lookup"><span data-stu-id="96ef5-118">After installing it, use the following steps to see the folder names:</span></span>

1. <span data-ttu-id="96ef5-119">打开 NuGet 包资源管理器。</span><span class="sxs-lookup"><span data-stu-id="96ef5-119">Open the NuGet Package Explorer.</span></span>
2. <span data-ttu-id="96ef5-120">单击“从在线源打开包”。</span><span class="sxs-lookup"><span data-stu-id="96ef5-120">Click **Open package from online feed**.</span></span>
3. <span data-ttu-id="96ef5-121">搜索包的名称。</span><span class="sxs-lookup"><span data-stu-id="96ef5-121">Search for the name of the package.</span></span>
4. <span data-ttu-id="96ef5-122">从搜索结果中选择包的名称，然后点击“打开”。</span><span class="sxs-lookup"><span data-stu-id="96ef5-122">Select the package name from the search results and click **open**.</span></span>
5. <span data-ttu-id="96ef5-123">展开右侧的“lib”文件夹并查看文件夹名称。</span><span class="sxs-lookup"><span data-stu-id="96ef5-123">Expand the *lib* folder on the right-hand side and look at folder names.</span></span>

<span data-ttu-id="96ef5-124">查找具有以下任意名称的文件夹：</span><span class="sxs-lookup"><span data-stu-id="96ef5-124">Look for a folder with any of the following names:</span></span>

```
netstandard1.0
netstandard1.1
netstandard1.2
netstandard1.3
netstandard1.4
netstandard1.5
netstandard1.6
netstandard2.0
netcoreapp1.0
netcoreapp1.1
netcoreapp2.0
portable-net45-win8
portable-win8-wpa8
portable-net451-win81
portable-net45-win8-wpa8-wpa81
```

<span data-ttu-id="96ef5-125">这些值是映射到 [.NET Standard](../../standard/net-standard.md) 版本的[目标框架名字对象 (TFM)](../../standard/frameworks.md)、.NET Core 以及与 .NET Core 兼容的传统可移植类库 (PCL) 配置文件。</span><span class="sxs-lookup"><span data-stu-id="96ef5-125">These values are the [Target Framework Monikers (TFMs)](../../standard/frameworks.md) that map to versions of the [.NET Standard](../../standard/net-standard.md), .NET Core, and traditional Portable Class Library (PCL) profiles that are compatible with .NET Core.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96ef5-126">查看包支持的 TFM 时，请注意 `netcoreapp*`，它在兼容时，仅适用于 .NET Core 项目，不适用于 .NET Standard 项目。</span><span class="sxs-lookup"><span data-stu-id="96ef5-126">When looking at the TFMs that a package supports, note that `netcoreapp*`, while compatible, is for .NET Core projects only and not for .NET Standard projects.</span></span>
> <span data-ttu-id="96ef5-127">仅面向 `netcoreapp*` 而不是 `netstandard*` 的库只能用于其他 .NET Core 应用。</span><span class="sxs-lookup"><span data-stu-id="96ef5-127">A library that only targets `netcoreapp*` and not `netstandard*` can only be consumed by other .NET Core apps.</span></span>

<span data-ttu-id="96ef5-128">.NET Core 预发行版本中使用的某些旧 TFM 也可能兼容：</span><span class="sxs-lookup"><span data-stu-id="96ef5-128">There are also some legacy TFMs used in pre-release versions of .NET Core that may also be compatible:</span></span>

```
dnxcore50
dotnet5.0
dotnet5.1
dotnet5.2
dotnet5.3
dotnet5.4
dotnet5.5
```

<span data-ttu-id="96ef5-129">尽管这些 TFM 也许可以使用代码，但不保证其兼容性。</span><span class="sxs-lookup"><span data-stu-id="96ef5-129">While these TFMs likely work with your code, there is no guarantee of compatibility.</span></span> <span data-ttu-id="96ef5-130">使用预发行的 .NET Core 包生成内含这些 TFM 的包。</span><span class="sxs-lookup"><span data-stu-id="96ef5-130">Packages with these TFMs were built with pre-release .NET Core packages.</span></span> <span data-ttu-id="96ef5-131">请记下使用这些 TFM 的包何时（或是否）更新为基于 .NET 标准。</span><span class="sxs-lookup"><span data-stu-id="96ef5-131">Take note of when (or if) packages using these TFMs are updated to be .NET Standard-based.</span></span>

> [!NOTE]
> <span data-ttu-id="96ef5-132">若要使用面向传统 PCL 或预发行的 .NET Core 目标的包，必须在项目文件中使用 `PackageTargetFallback` MSBuild 元素。</span><span class="sxs-lookup"><span data-stu-id="96ef5-132">To use a package targeting a traditional PCL or pre-release .NET Core target, you must use the `PackageTargetFallback` MSBuild element in your project file.</span></span>
> <span data-ttu-id="96ef5-133">有关此 MSBuild 元素的详细信息，请参阅 [`PackageTargetFallback`](../tools/csproj.md#packagetargetfallback)。</span><span class="sxs-lookup"><span data-stu-id="96ef5-133">For more information about this MSBuild element, see [`PackageTargetFallback`](../tools/csproj.md#packagetargetfallback).</span></span>

### <a name="analyze-nuget-packages-using-nugetorg"></a><span data-ttu-id="96ef5-134">使用 nuget.org 分析 NuGet 包</span><span class="sxs-lookup"><span data-stu-id="96ef5-134">Analyze NuGet packages using nuget.org</span></span>

<span data-ttu-id="96ef5-135">或者，可在包页面“依赖项”部分下的 [nuget.org](https://www.nuget.org/) 上查看每个包支持的 TFM。</span><span class="sxs-lookup"><span data-stu-id="96ef5-135">Alternatively, you can see the TFMs that each package supports on [nuget.org](https://www.nuget.org/) under the **Dependencies** section of the package page.</span></span>

<span data-ttu-id="96ef5-136">尽管使用该站点可以比较简单地验证兼容性，但站点上并未提供所有包的“依赖项”信息。</span><span class="sxs-lookup"><span data-stu-id="96ef5-136">Although using the site is an easier method to verify the compatibility, **Dependencies** information is not available on the site for all packages.</span></span>

### <a name="net-framework-compatibility-mode"></a><span data-ttu-id="96ef5-137">.NET Framework 兼容性模式</span><span class="sxs-lookup"><span data-stu-id="96ef5-137">.NET Framework compatibility mode</span></span>

<span data-ttu-id="96ef5-138">在分析完 NuGet 包之后，你可能会发现它们仅面向 .NET Framework，就像大多数 NuGet 包一样。</span><span class="sxs-lookup"><span data-stu-id="96ef5-138">After analyzing the NuGet packages, you might find that they only target the .NET Framework, as most NuGet packages do.</span></span>

<span data-ttu-id="96ef5-139">从 .NET Standard 2.0 开始，引入了 .NET Framework 兼容性模式。</span><span class="sxs-lookup"><span data-stu-id="96ef5-139">Starting with .NET Standard 2.0, the .NET Framework compatibility mode was introduced.</span></span> <span data-ttu-id="96ef5-140">此兼容性模式允许 .NET Standard 和 .NET Core 项目引用 .NET Framework 库。</span><span class="sxs-lookup"><span data-stu-id="96ef5-140">This compatibility mode allows .NET Standard and .NET Core projects to reference .NET Framework libraries.</span></span> <span data-ttu-id="96ef5-141">引用 .NET Framework 库不适用于所有项目（如库使用 Windows Presentation Foundation (WPF) API 时），但它的开启了很多移植方案。</span><span class="sxs-lookup"><span data-stu-id="96ef5-141">Referencing .NET Framework libraries doesn't work for all projects, such as if the library uses Windows Presentation Foundation (WPF) APIs, but it does unblock many porting scenarios.</span></span>

<span data-ttu-id="96ef5-142">在项目中引用面向 .NET Framework 的 NuGet 包时（如 [Huitian.PowerCollections](https://www.nuget.org/packages/Huitian.PowerCollections)），会收到与以下示例类似的包回退警告 ([NU1701](/nuget/reference/errors-and-warnings#nu1701))：</span><span class="sxs-lookup"><span data-stu-id="96ef5-142">When you reference NuGet packages that target the .NET Framework in your project, such as [Huitian.PowerCollections](https://www.nuget.org/packages/Huitian.PowerCollections), you get a package fallback warning ([NU1701](/nuget/reference/errors-and-warnings#nu1701)) similar to the following example:</span></span>

`NU1701: Package ‘Huitian.PowerCollections 1.0.0’ was restored using ‘.NETFramework,Version=v4.6.1’ instead of the project target framework ‘.NETStandard,Version=v2.0’. This package may not be fully compatible with your project.`

<span data-ttu-id="96ef5-143">当添加包以及每次生成时都会显示该警告，以确保在项目中测试该包。</span><span class="sxs-lookup"><span data-stu-id="96ef5-143">That warning is displayed when you add the package and every time you build to make sure you test that package with your project.</span></span> <span data-ttu-id="96ef5-144">如果项目按预期工作，可通过在 Visual Studio 中编辑包属性或在最喜欢的代码编辑器中手动编辑项目文件来取消该警告。</span><span class="sxs-lookup"><span data-stu-id="96ef5-144">If your project is working as expected, you can suppress that warning by editing the package properties in Visual Studio or by manually editing the project file in your favorite code editor.</span></span>

<span data-ttu-id="96ef5-145">若要通过编辑项目文件来取消警告，请找到要取消警告的包的 `PackageReference` 条目并添加 `NoWarn` 属性。</span><span class="sxs-lookup"><span data-stu-id="96ef5-145">To suppress the warning by editing the project file, find the `PackageReference` entry for the package you want to suppress the warning for and add the `NoWarn` attribute.</span></span> <span data-ttu-id="96ef5-146">`NoWarn` 属性接受所有警告 ID 的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="96ef5-146">The `NoWarn` attribute accepts a comma-separated list of all the warning IDs.</span></span> <span data-ttu-id="96ef5-147">以下示例显示如何通过手动编辑项目文件来取消 `Huitian.PowerCollections` 包的 `NU1701` 警告：</span><span class="sxs-lookup"><span data-stu-id="96ef5-147">The following example shows how to suppress the `NU1701` warning for the `Huitian.PowerCollections` package by editing your project file manually:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Huitian.PowerCollections" Version="1.0.0" NoWarn="NU1701" />
</ItemGroup>
```

<span data-ttu-id="96ef5-148">有关如何在 Visual Studio 中取消编译器警告的详细信息，请参阅[取消 NuGet 包的警告](/visualstudio/ide/how-to-suppress-compiler-warnings#suppressing-warnings-for-nuget-packages)。</span><span class="sxs-lookup"><span data-stu-id="96ef5-148">For more information on how to suppress compiler warnings in Visual Studio, see [Suppressing warnings for NuGet packages](/visualstudio/ide/how-to-suppress-compiler-warnings#suppressing-warnings-for-nuget-packages).</span></span>

### <a name="what-to-do-when-your-nuget-package-dependency-doesnt-run-on-net-core"></a><span data-ttu-id="96ef5-149">NuGet 包依赖项未在.NET Core 上运行时应执行的操作</span><span class="sxs-lookup"><span data-stu-id="96ef5-149">What to do when your NuGet package dependency doesn't run on .NET Core</span></span>

<span data-ttu-id="96ef5-150">如果所依赖的 NuGet 包无法在 .NET Core 上运行，可以执行以下几项操作：</span><span class="sxs-lookup"><span data-stu-id="96ef5-150">There are a few things you can do if a NuGet package you depend on doesn't run on .NET Core:</span></span>

1. <span data-ttu-id="96ef5-151">如果项目是开放源代码并托管在诸如 GitHub 中，则可以直接与开发人员交流。</span><span class="sxs-lookup"><span data-stu-id="96ef5-151">If the project is open source and hosted somewhere like GitHub, you can engage the developers directly.</span></span>
2. <span data-ttu-id="96ef5-152">可直接在 [nuget.org](https://www.nuget.org/) 上联系作者。搜索包并单击包页面左侧的“联系所有者”。</span><span class="sxs-lookup"><span data-stu-id="96ef5-152">You can contact the author directly on [nuget.org](https://www.nuget.org/). Search for the package and click **Contact Owners** on the left-hand side of the package's page.</span></span>
3. <span data-ttu-id="96ef5-153">可以搜索在 .NET Core 上运行的其他包，它与所使用的包进行的是相同的任务。</span><span class="sxs-lookup"><span data-stu-id="96ef5-153">You can search for another package that runs on .NET Core that accomplishes the same task as the package you were using.</span></span>
4. <span data-ttu-id="96ef5-154">可以尝试自己编写包所执行的代码。</span><span class="sxs-lookup"><span data-stu-id="96ef5-154">You can attempt to write the code the package was doing yourself.</span></span>
5. <span data-ttu-id="96ef5-155">可以通过更改应用的功能来清除对包的依赖性，至少在该包有可用的兼容性版本之前都能这样做。</span><span class="sxs-lookup"><span data-stu-id="96ef5-155">You could eliminate the dependency on the package by changing the functionality of your app, at least until a compatible version of the package becomes available.</span></span>

<span data-ttu-id="96ef5-156">请注意，开源项目维护人员和 NuGet 包发布者通常是志愿者。</span><span class="sxs-lookup"><span data-stu-id="96ef5-156">Remember that open-source project maintainers and NuGet package publishers are often volunteers.</span></span> <span data-ttu-id="96ef5-157">他们因为关注某个特定领域而免费提供服务，通常从事另外一份职业。</span><span class="sxs-lookup"><span data-stu-id="96ef5-157">They contribute because they care about a given domain, do it for free, and often have a different daytime job.</span></span> <span data-ttu-id="96ef5-158">因此，当联系他们请求 .NET Core 支持时请注意这点。</span><span class="sxs-lookup"><span data-stu-id="96ef5-158">So be mindful of that when contacting them to ask for .NET Core support.</span></span>

<span data-ttu-id="96ef5-159">如果采取上述任何操作都无法解决问题，则可能需要移植到最近版本的 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="96ef5-159">If you can't resolve your issue with any of the above, you may have to port to .NET Core at a later date.</span></span>

<span data-ttu-id="96ef5-160">.NET 团队需要了解哪些库最需要使用 .NET Core 支持。</span><span class="sxs-lookup"><span data-stu-id="96ef5-160">The .NET Team would like to know which libraries are the most important to support with .NET Core.</span></span> <span data-ttu-id="96ef5-161">你可以发送电子邮件到 dotnet@microsoft.com，谈谈你想要使用的库。</span><span class="sxs-lookup"><span data-stu-id="96ef5-161">You can send an email to dotnet@microsoft.com about the libraries you'd like to use.</span></span>

## <a name="analyze-dependencies-that-arent-nuget-packages"></a><span data-ttu-id="96ef5-162">分析不是 NuGet 包的依赖项</span><span class="sxs-lookup"><span data-stu-id="96ef5-162">Analyze dependencies that aren't NuGet packages</span></span>

<span data-ttu-id="96ef5-163">用户可能拥有不是 NuGet 包的依赖项，如文件系统中的 DLL。</span><span class="sxs-lookup"><span data-stu-id="96ef5-163">You may have a dependency that isn't a NuGet package, such as a DLL in the file system.</span></span> <span data-ttu-id="96ef5-164">确定该依赖项是否可移植的唯一方法是运行 [.NET 可移植性分析器](https://github.com/Microsoft/dotnet-apiport)工具。</span><span class="sxs-lookup"><span data-stu-id="96ef5-164">The only way to determine the portability of that dependency is to run the [.NET Portability Analyzer](https://github.com/Microsoft/dotnet-apiport) tool.</span></span> <span data-ttu-id="96ef5-165">该工具可以分析面向 .NET Framework 的程序集，并识别不可移植到其他 .NET 平台（如 .NET Core）的 API。</span><span class="sxs-lookup"><span data-stu-id="96ef5-165">The tool can analyze assemblies that target the .NET Framework and identify APIs that aren't portable to other .NET platforms such as .NET Core.</span></span> <span data-ttu-id="96ef5-166">可将该工具作为控制台应用程序或作为 [Visual Studio 扩展](../../standard/analyzers/portability-analyzer.md)来运行。</span><span class="sxs-lookup"><span data-stu-id="96ef5-166">You can run the tool as a console application or as a [Visual Studio extension](../../standard/analyzers/portability-analyzer.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="96ef5-167">后续步骤</span><span class="sxs-lookup"><span data-stu-id="96ef5-167">Next steps</span></span>

<span data-ttu-id="96ef5-168">若要移植库，请参阅 [Porting your Libraries](libraries.md)（移植库）。</span><span class="sxs-lookup"><span data-stu-id="96ef5-168">If you're porting a library, check out [Porting your Libraries](libraries.md).</span></span>
