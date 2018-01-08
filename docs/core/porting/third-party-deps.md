---
title: "移植到 .NET Core - 分析第三方依赖项"
description: "移植到 .NET Core - 分析第三方依赖项"
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: b446e9e0-72f6-48f6-92c6-70ad0ce3f86a
ms.workload: dotnetcore
ms.openlocfilehash: 70b39c9762e4ee7450d0f59455bace0ac728844c
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="porting-to-net-core---analyzing-your-third-party-party-dependencies"></a><span data-ttu-id="c801c-104">移植到 .NET Core - 分析第三方依赖项</span><span class="sxs-lookup"><span data-stu-id="c801c-104">Porting to .NET Core - Analyzing your Third-Party Party Dependencies</span></span>

<span data-ttu-id="c801c-105">移植过程的第一步是了解第三方依赖项。</span><span class="sxs-lookup"><span data-stu-id="c801c-105">The first step in the porting process is to understand your third party dependencies.</span></span>  <span data-ttu-id="c801c-106">需要找出尚未在 .NET Core 上运行的依赖项（如果有），并为这些没有在 .Net Core 上运行的依赖项制定应变计划。</span><span class="sxs-lookup"><span data-stu-id="c801c-106">You need to figure out which of them, if any, don't yet run on .NET Core, and develop a contingency plan for those which don't run on .NET Core.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c801c-107">系统必备</span><span class="sxs-lookup"><span data-stu-id="c801c-107">Prerequisites</span></span>

<span data-ttu-id="c801c-108">今天，本文假定使用 Windows 和 Visual Studio，并拥有在 .NET Framework 上运行的代码。</span><span class="sxs-lookup"><span data-stu-id="c801c-108">This article will assume you are using Windows and Visual Studio, and that you have code which runs on the .NET Framework today.</span></span>

## <a name="analyzing-nuget-packages"></a><span data-ttu-id="c801c-109">分析 NuGet 包</span><span class="sxs-lookup"><span data-stu-id="c801c-109">Analyzing NuGet Packages</span></span>

<span data-ttu-id="c801c-110">分析 NuGet 包的可移植性非常简单。</span><span class="sxs-lookup"><span data-stu-id="c801c-110">Analyzing NuGet packages for portability is very easy.</span></span>  <span data-ttu-id="c801c-111">因为 NuGet 包本身是一组包含特定于平台的程序集的文件夹，因此仅需检查确认是否存在包含 .NET Core 程序集的文件夹即可。</span><span class="sxs-lookup"><span data-stu-id="c801c-111">Because a NuGet package is itself a set of folders which contain platform-specific assemblies, all you have to do is check to see if there is a folder which contains a .NET Core assembly.</span></span>

<span data-ttu-id="c801c-112">检查 NuGet 包文件夹最简单的方法是使用 [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) 工具。</span><span class="sxs-lookup"><span data-stu-id="c801c-112">Inspecting NuGet Package folders is easiest with the [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) tool.</span></span>  <span data-ttu-id="c801c-113">以下是使用方法。</span><span class="sxs-lookup"><span data-stu-id="c801c-113">Here's how to do it.</span></span>

1. <span data-ttu-id="c801c-114">下载并打开 NuGet Package Explorer。</span><span class="sxs-lookup"><span data-stu-id="c801c-114">Download and open the NuGet Package Explorer.</span></span>
2. <span data-ttu-id="c801c-115">单击“从在线源打开包”。</span><span class="sxs-lookup"><span data-stu-id="c801c-115">Click "Open package from online feed".</span></span>
3. <span data-ttu-id="c801c-116">搜索包的名称。</span><span class="sxs-lookup"><span data-stu-id="c801c-116">Search for the name of the package.</span></span>
4. <span data-ttu-id="c801c-117">展开右侧的“lib”文件夹并查看文件夹名称。</span><span class="sxs-lookup"><span data-stu-id="c801c-117">Expand the "lib" folder on the right-hand side and look at folder names.</span></span>

<span data-ttu-id="c801c-118">还可以在该包页面的“依赖项”部分下的 [nuget.org](https://www.nuget.org/) 上查看包所支持的内容。</span><span class="sxs-lookup"><span data-stu-id="c801c-118">You can also see what a package supports on [nuget.org](https://www.nuget.org/) under the **Dependencies** section of the page for that package.</span></span>

<span data-ttu-id="c801c-119">无论哪种情况都需要在 [nuget.org](https://www.nuget.org/) 上查找具有以下任何名称的文件夹或项：</span><span class="sxs-lookup"><span data-stu-id="c801c-119">In either case, you'll need to look for a folder or entry on [nuget.org](https://www.nuget.org/) with any of the following names:</span></span>

```
netstandard1.0
netstandard1.1
netstandard1.2
netstandard1.3
netstandard1.4
netstandard1.5
netstandard1.6
netcoreapp1.0
portable-net45-win8
portable-win8-wpa8
portable-net451-win81
portable-net45-win8-wpa8-wpa81
```

<span data-ttu-id="c801c-120">这些是映射到 [.NET Standard](../../standard/net-standard.md) 版本的目标框架名字对象 (TFM) 以及与 .NET Core 兼容的传统可移植类库 (PCL) 配置文件。</span><span class="sxs-lookup"><span data-stu-id="c801c-120">These are the Target Framework Monikers (TFM) which map to versions of the [.NET Standard](../../standard/net-standard.md) and traditional Portable Class Library (PCL) profiles which are compatible with .NET Core.</span></span>  <span data-ttu-id="c801c-121">请注意，兼容的 `netcoreapp1.0` 适用于应用程序，而非库。</span><span class="sxs-lookup"><span data-stu-id="c801c-121">Note that `netcoreapp1.0`, while compatible, is for applications and not libraries.</span></span>  <span data-ttu-id="c801c-122">尽管使用基于 `netcoreapp1.0` 的库没有任何不妥，但该库可能不适用于*不是*由其他 `netcoreapp1.0` 应用程序所使用的任何内容。</span><span class="sxs-lookup"><span data-stu-id="c801c-122">Although there's nothing wrong with using a library which is `netcoreapp1.0`-based, that library may not be intended for anything *other* than consumption by other `netcoreapp1.0` applications.</span></span>

<span data-ttu-id="c801c-123">.NET Core 预发行版本中使用的某些旧 TFM 也可能兼容：</span><span class="sxs-lookup"><span data-stu-id="c801c-123">There are also some legacy TFMs used in pre-release versions of .NET Core that may also be compatible:</span></span>

```
dnxcore50
dotnet5.0
dotnet5.1
dotnet5.2
dotnet5.3
dotnet5.4
dotnet5.5
```

<span data-ttu-id="c801c-124">**尽管这些可能适用于代码，但不保证其兼容性**。</span><span class="sxs-lookup"><span data-stu-id="c801c-124">**While these will likely work with your code, there is no guarantee of compatibility**.</span></span>  <span data-ttu-id="c801c-125">使用预发行的 .NET Core 包生成内含这些 TFM 的包。</span><span class="sxs-lookup"><span data-stu-id="c801c-125">Packages with these TFMs were built with pre-release .NET Core packages.</span></span>  <span data-ttu-id="c801c-126">请注意此类包更新为基于 `netstandard` 的包的情况。</span><span class="sxs-lookup"><span data-stu-id="c801c-126">Take note of when (or if) packages like this are updated to be `netstandard`-based.</span></span>

> [!NOTE]
> <span data-ttu-id="c801c-127">若要使用以传统 PCL 或预发行的 .NET Core 目标为目标的包，必须使用 `project.json` 文件中的 `imports` 指令。</span><span class="sxs-lookup"><span data-stu-id="c801c-127">To use a package targeting a traditional PCL or pre-release .NET Core target, you must use the `imports` directive in your `project.json` file.</span></span>

### <a name="what-to-do-when-your-nuget-package-dependency-doesnt-run-on-net-core"></a><span data-ttu-id="c801c-128">NuGet 包依赖项未在.NET Core 上运行时应执行的操作</span><span class="sxs-lookup"><span data-stu-id="c801c-128">What to do when your NuGet package dependency doesn't run on .NET Core</span></span>

<span data-ttu-id="c801c-129">如果所依赖的 NuGet 包无法在 .NET Core 上运行，可以执行以下几项操作。</span><span class="sxs-lookup"><span data-stu-id="c801c-129">There are a few things you can do if a NuGet package you depend on won't run on .NET Core.</span></span>

1. <span data-ttu-id="c801c-130">如果项目是开放源代码并托管在诸如 GitHub 中，则可以直接与开发人员交流。</span><span class="sxs-lookup"><span data-stu-id="c801c-130">If the project is open source and hosted somewhere like GitHub, you can engage the developer(s) directly.</span></span>
2. <span data-ttu-id="c801c-131">可以通过搜索包并单击该包页面左侧的“联系所有者”即可直接在 [nuget.org](https://www.nuget.org/) 上与作者取得联系。</span><span class="sxs-lookup"><span data-stu-id="c801c-131">You can contact the author directly on [nuget.org](https://www.nuget.org/) by searching for the package and clicking "Contact Owners" on the left hand side of the package's page.</span></span>
3. <span data-ttu-id="c801c-132">可以查找在.NET Core 上运行的其他包，这些包与所使用的包进行的是相同的任务。</span><span class="sxs-lookup"><span data-stu-id="c801c-132">You can look for another package that runs on .NET Core which accomplishes the same task as the package you were using.</span></span>
4. <span data-ttu-id="c801c-133">可以尝试自己编写包所执行的代码。</span><span class="sxs-lookup"><span data-stu-id="c801c-133">You can attempt to write the code the package was doing yourself.</span></span>
5. <span data-ttu-id="c801c-134">可以通过更改应用的功能来清除对包的依赖性，至少在该包有可用的兼容性版本之前都能这样做。</span><span class="sxs-lookup"><span data-stu-id="c801c-134">You could eliminate the dependency on the package by changing the functionality of your app, at least until a compatible version of the package becomes available.</span></span>

<span data-ttu-id="c801c-135">请记住，开放源代码项目维护者和 NuGet 包发布者通常是因对给定域感兴趣且拥有不同的正常工作而免费参与的志愿者。</span><span class="sxs-lookup"><span data-stu-id="c801c-135">Please remember that open source project maintainers and NuGet package publishers are often volunteers who contribute because they care about a given domain, do it for free, and often have a different daytime job.</span></span> <span data-ttu-id="c801c-136">如果确实要参与，可能首先需要写一份关于库的积极声明，然后才能咨询有关 .NET Core 支持团队的内容。</span><span class="sxs-lookup"><span data-stu-id="c801c-136">If you do reach out, you might start with a positive statement about the library before asking about .NET Core support.</span></span>

<span data-ttu-id="c801c-137">如果采取上述任何操作都无法解决问题，则可能需要移植到最近版本的 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="c801c-137">If you're unable to resolve your issue with any of the above, you may have to port to .NET Core at a later date.</span></span>

<span data-ttu-id="c801c-138">.NET 团队需要了解下次使用.NET Core 时哪些是需要支持的最重要的库。</span><span class="sxs-lookup"><span data-stu-id="c801c-138">The .NET Team would like to know which libraries are the most important to support next with .NET Core.</span></span> <span data-ttu-id="c801c-139">还可发送邮件到 dotnet@microsoft.com，告知我们希望使用的库。</span><span class="sxs-lookup"><span data-stu-id="c801c-139">You can also send us mail at dotnet@microsoft.com about the libraries you'd like to use.</span></span>

## <a name="analyzing-dependencies-which-arent-nuget-packages"></a><span data-ttu-id="c801c-140">分析不是 NuGet 包的依赖项</span><span class="sxs-lookup"><span data-stu-id="c801c-140">Analyzing Dependencies which aren't NuGet Packages</span></span>

<span data-ttu-id="c801c-141">用户可能拥有不是 NuGet 包的依赖项，如文件系统中的 DLL。</span><span class="sxs-lookup"><span data-stu-id="c801c-141">You may have a dependency that isn't a NuGet package, such as a DLL in the filesystem.</span></span>  <span data-ttu-id="c801c-142">因此确定依赖项是否可移植的唯一方法是运行 [ApiPort 工具](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/)。</span><span class="sxs-lookup"><span data-stu-id="c801c-142">The only way to determine the portability of that dependency is to run the [ApiPort tool](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c801c-143">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c801c-143">Next steps</span></span>

<span data-ttu-id="c801c-144">若要移植库，请参阅 [Porting your Libraries](libraries.md)（移植库）。</span><span class="sxs-lookup"><span data-stu-id="c801c-144">If you're porting a library, check out [Porting your Libraries](libraries.md).</span></span>
