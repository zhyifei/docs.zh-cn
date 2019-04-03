---
title: 将 WPF 应用移植到 .NET Core 3.0
description: 介绍如何将 .NET Framework Windows Presentation Foundation 应用程序移植到适用于 Windows 的 .NET Core 3.0。
author: Thraka
ms.author: adegeo
ms.date: 03/27/2019
ms.custom: ''
ms.openlocfilehash: 29ea308ee5147cfb18df312887e933615e349803
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2019
ms.locfileid: "58677545"
---
# <a name="how-to-port-a-wpf-desktop-app-to-net-core"></a><span data-ttu-id="a22b6-103">如何：将 WPF 桌面应用移植到 .NET Core</span><span class="sxs-lookup"><span data-stu-id="a22b6-103">How to: Port a WPF desktop app to .NET Core</span></span>

<span data-ttu-id="a22b6-104">本文介绍如何将基于 Windows Presentation Foundation (WPF) 的桌面应用从 .NET Framework 移植到 .NET Core 3.0。</span><span class="sxs-lookup"><span data-stu-id="a22b6-104">This article describes how to port your Windows Presentation Foundation-based (WPF) desktop app from .NET Framework to .NET Core 3.0.</span></span> <span data-ttu-id="a22b6-105">.NET Core 3.0 SDK 支持 WPF 应用程序。</span><span class="sxs-lookup"><span data-stu-id="a22b6-105">The .NET Core 3.0 SDK includes support for WPF applications.</span></span> <span data-ttu-id="a22b6-106">WPF 仍是仅适用于 Windows 的框架，并且只能在 Windows 上运行。</span><span class="sxs-lookup"><span data-stu-id="a22b6-106">WPF is still a Windows-only framework and only runs on Windows.</span></span> <span data-ttu-id="a22b6-107">示例使用 .NET Core SDK CLI 创建和管理项目。</span><span class="sxs-lookup"><span data-stu-id="a22b6-107">This example uses the .NET Core SDK CLI to create and manage your project.</span></span>

<span data-ttu-id="a22b6-108">本文中的各种名称用于标识迁移所用的文件类型。</span><span class="sxs-lookup"><span data-stu-id="a22b6-108">In this article, various names are used to identify types of files used for migration.</span></span> <span data-ttu-id="a22b6-109">迁移项目时，你的文件将以不同的名称命名，因此，请自行在心里将它们与下面列出的文件进行匹配：</span><span class="sxs-lookup"><span data-stu-id="a22b6-109">When migrating your project, your files will be named differently, so mentally match them to the ones listed below:</span></span>

| <span data-ttu-id="a22b6-110">文件</span><span class="sxs-lookup"><span data-stu-id="a22b6-110">File</span></span> | <span data-ttu-id="a22b6-111">说明</span><span class="sxs-lookup"><span data-stu-id="a22b6-111">Description</span></span> |
| ---- | ----------- |
| <span data-ttu-id="a22b6-112">**MyApps.sln**</span><span class="sxs-lookup"><span data-stu-id="a22b6-112">**MyApps.sln**</span></span> | <span data-ttu-id="a22b6-113">解决方案文件的名称。</span><span class="sxs-lookup"><span data-stu-id="a22b6-113">The name of the solution file.</span></span> |
| <span data-ttu-id="a22b6-114">**MyWPF.csproj**</span><span class="sxs-lookup"><span data-stu-id="a22b6-114">**MyWPF.csproj**</span></span> | <span data-ttu-id="a22b6-115">要移植的 .NET Framework WPF 项目的名称。</span><span class="sxs-lookup"><span data-stu-id="a22b6-115">The name of the .NET Framework WPF project to port.</span></span> |
| <span data-ttu-id="a22b6-116">**MyWPFCore.csproj**</span><span class="sxs-lookup"><span data-stu-id="a22b6-116">**MyWPFCore.csproj**</span></span> | <span data-ttu-id="a22b6-117">创建的新 .NET Core 项目的名称。</span><span class="sxs-lookup"><span data-stu-id="a22b6-117">The name of the new .NET Core project you create.</span></span> |
| <span data-ttu-id="a22b6-118">**MyAppCore.exe**</span><span class="sxs-lookup"><span data-stu-id="a22b6-118">**MyAppCore.exe**</span></span> | <span data-ttu-id="a22b6-119">.NET Core WPF 应用可执行文件。</span><span class="sxs-lookup"><span data-stu-id="a22b6-119">The .NET Core WPF app executable.</span></span> |

## <a name="prerequisites"></a><span data-ttu-id="a22b6-120">系统必备</span><span class="sxs-lookup"><span data-stu-id="a22b6-120">Prerequisites</span></span>

- <span data-ttu-id="a22b6-121">适用于要执行的任何设计器工作的 [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=wpf+core)。</span><span class="sxs-lookup"><span data-stu-id="a22b6-121">[Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=wpf+core) for any designer work you want to do.</span></span>

  <span data-ttu-id="a22b6-122">安装以下 Visual Studio 工作负载：</span><span class="sxs-lookup"><span data-stu-id="a22b6-122">Install the following Visual Studio workloads:</span></span>
  - <span data-ttu-id="a22b6-123">.NET 桌面开发</span><span class="sxs-lookup"><span data-stu-id="a22b6-123">.NET desktop development</span></span>
  - <span data-ttu-id="a22b6-124">.NET 跨平台开发</span><span class="sxs-lookup"><span data-stu-id="a22b6-124">.NET cross-platform development</span></span>

- <span data-ttu-id="a22b6-125">在解决方案中顺利生成和运行的有效 WPF 项目。</span><span class="sxs-lookup"><span data-stu-id="a22b6-125">A working WPF project in a solution that builds and runs without issue.</span></span>
- <span data-ttu-id="a22b6-126">项目必须使用 C# 进行编码。</span><span class="sxs-lookup"><span data-stu-id="a22b6-126">Your project must be coded in C#.</span></span> 
- <span data-ttu-id="a22b6-127">安装最新 [.NET Core 3.0](https://aka.ms/netcore3download) 预览版。</span><span class="sxs-lookup"><span data-stu-id="a22b6-127">Install the latest [.NET Core 3.0](https://aka.ms/netcore3download) preview.</span></span>


>[!NOTE]
><span data-ttu-id="a22b6-128">Visual Studio 2017 不支持 .NET Core 3.0 项目。</span><span class="sxs-lookup"><span data-stu-id="a22b6-128">**Visual Studio 2017** doesn't support .NET Core 3.0 projects.</span></span> <span data-ttu-id="a22b6-129">“Visual Studio 2019 预览版/RC”支持 .NET Core 3.0 项目，但尚不支持适用于 .NET Core 3.0 WPF 项目的可视化设计器。</span><span class="sxs-lookup"><span data-stu-id="a22b6-129">**Visual Studio 2019 Preview/RC** supports .NET Core 3.0 projects but doesn't yet support the visual designer for .NET Core 3.0 WPF projects.</span></span> <span data-ttu-id="a22b6-130">要使用可视化设计器，解决方案中必须包含可与 .NET Core 项目共享其文件的 .NET WPF 项目。</span><span class="sxs-lookup"><span data-stu-id="a22b6-130">To use the visual designer, you must have a .NET WPF project in your solution that shares its files with the .NET Core project.</span></span>

### <a name="consider"></a><span data-ttu-id="a22b6-131">考虑</span><span class="sxs-lookup"><span data-stu-id="a22b6-131">Consider</span></span>

<span data-ttu-id="a22b6-132">移植 .NET Framework WPF 应用程序时，必须考虑以下几个事项。</span><span class="sxs-lookup"><span data-stu-id="a22b6-132">When porting a .NET Framework WPF application, there are a few things you must consider.</span></span>

01. <span data-ttu-id="a22b6-133">检查应用程序是否适合迁移。</span><span class="sxs-lookup"><span data-stu-id="a22b6-133">Check that your application is a good candidate for migration.</span></span>

    <span data-ttu-id="a22b6-134">使用 [.NET 可移植性分析器](../../standard/analyzers/portability-analyzer.md)确定项目将会迁移到 .NET Core 3.0。</span><span class="sxs-lookup"><span data-stu-id="a22b6-134">Use the [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) to determine if your project will migrate to .NET Core 3.0.</span></span> <span data-ttu-id="a22b6-135">如果项目存在 .NET Core 3.0 相关问题，分析器可帮助你识别这些问题。</span><span class="sxs-lookup"><span data-stu-id="a22b6-135">If your project has issues with .NET Core 3.0, the analyzer helps you identify those problems.</span></span>

01. <span data-ttu-id="a22b6-136">使用的是不同版本的 WPF。</span><span class="sxs-lookup"><span data-stu-id="a22b6-136">You're using a different version of WPF.</span></span>

    <span data-ttu-id="a22b6-137">发布 .NET Core 3.0 预览版 1 时，WPF 在 GitHub 上公布了开放源代码。</span><span class="sxs-lookup"><span data-stu-id="a22b6-137">When .NET Core 3.0 Preview 1 was released, WPF went open-source on GitHub.</span></span> <span data-ttu-id="a22b6-138">.NET Core WPF 的代码是 .NET Framework WPF 基本代码的一个分支。</span><span class="sxs-lookup"><span data-stu-id="a22b6-138">The code for .NET Core WPF is a fork of the .NET Framework WPF code base.</span></span> <span data-ttu-id="a22b6-139">可能存在一些差异导致应用程序无法移植。</span><span class="sxs-lookup"><span data-stu-id="a22b6-139">It's possible some differences exist and your app won't port.</span></span>

01. <span data-ttu-id="a22b6-140">使用 [Windows 兼容包][compat-pack]可能有助于进行迁移。</span><span class="sxs-lookup"><span data-stu-id="a22b6-140">The [Windows Compatibility Pack][compat-pack] may help you migrate.</span></span>

    <span data-ttu-id="a22b6-141">某些 API 可在 .NET Framework 中使用，但不可用于 .NET Core 3.0。</span><span class="sxs-lookup"><span data-stu-id="a22b6-141">Some APIs that are available in .NET Framework aren't available in .NET Core 3.0.</span></span> <span data-ttu-id="a22b6-142">[Windows 兼容包][compat-pack] 增加了很多此类 API，有助于使 WPF 应用与 .NET Core 兼容。</span><span class="sxs-lookup"><span data-stu-id="a22b6-142">The [Windows Compatibility Pack][compat-pack] adds many of these APIs and may help your WPF app become compatible with .NET Core.</span></span>

01. <span data-ttu-id="a22b6-143">更新项目使用的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="a22b6-143">Update the NuGet packages used by your project.</span></span>

    <span data-ttu-id="a22b6-144">在执行任何迁移之前使用最新版 NuGet 包始终是一个不错的做法。</span><span class="sxs-lookup"><span data-stu-id="a22b6-144">It's always a good practice to use the latest versions of NuGet packages before any migration.</span></span> <span data-ttu-id="a22b6-145">如果应用程序引用任何 NuGet 包，请将它们更新到最新版本。</span><span class="sxs-lookup"><span data-stu-id="a22b6-145">If your application is referencing any NuGet packages, update them to the latest version.</span></span> <span data-ttu-id="a22b6-146">确保成功生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="a22b6-146">Ensure your application builds successfully.</span></span> <span data-ttu-id="a22b6-147">升级后，如果存在任何包错误，请将包降级到不会破坏代码的最新版本。</span><span class="sxs-lookup"><span data-stu-id="a22b6-147">After upgrading, if there are any package errors, downgrade the package to the latest version that doesn't break your code.</span></span>

01. <span data-ttu-id="a22b6-148">Visual Studio 2019 预览版/RC 尚不支持适用于 .NET Core 3.0 的 WPF 设计器</span><span class="sxs-lookup"><span data-stu-id="a22b6-148">Visual Studio 2019 Preview/RC doesn't yet support the WPF Designer for .NET Core 3.0</span></span>

    <span data-ttu-id="a22b6-149">目前，如果要从 Visual Studio 中使用 WPF 设计器，需要保留现有的 .NET Framework WPF 项目文件。</span><span class="sxs-lookup"><span data-stu-id="a22b6-149">Currently, you need to keep your existing .NET Framework WPF project file if you want to use the WPF Designer from Visual Studio.</span></span>

## <a name="create-a-new-sdk-project"></a><span data-ttu-id="a22b6-150">创建新的 SDK 项目</span><span class="sxs-lookup"><span data-stu-id="a22b6-150">Create a new SDK project</span></span>

<span data-ttu-id="a22b6-151">创建的新 .NET Core 3.0 项目必须位于不同于 .NET Framework 项目的目录中。</span><span class="sxs-lookup"><span data-stu-id="a22b6-151">The new .NET Core 3.0 project you create must be in a different directory from your .NET Framework project.</span></span> <span data-ttu-id="a22b6-152">如果它们位于同一目录中，可能会与 obj 目录中生成的文件发生冲突。</span><span class="sxs-lookup"><span data-stu-id="a22b6-152">If they're both in the same directory, you may run into conflicts with the files that are generated in the **obj** directory.</span></span> <span data-ttu-id="a22b6-153">本例中，你将在“SolutionFolder”目录中创建一个名为“MyWPFAppCore”的目录：</span><span class="sxs-lookup"><span data-stu-id="a22b6-153">In this example, you'll create a directory named **MyWPFAppCore** in the **SolutionFolder** directory:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyWPFApp
│   └───MyWPF.csproj
└───MyWPFAppCore      <--- New folder for core project
```

<span data-ttu-id="a22b6-154">接下来，需要在“MyWPFAppCore”目录中创建“MyWPFCore.csproj”项目。</span><span class="sxs-lookup"><span data-stu-id="a22b6-154">Next, you need to create the **MyWPFCore.csproj** project in the **MyWPFAppCore** directory.</span></span> <span data-ttu-id="a22b6-155">可以使用所选的文本编辑器手动创建此文件。</span><span class="sxs-lookup"><span data-stu-id="a22b6-155">You can create this file manually by using the text editor of choice.</span></span> <span data-ttu-id="a22b6-156">粘贴以下 XML：</span><span class="sxs-lookup"><span data-stu-id="a22b6-156">Paste in the following XML:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="a22b6-157">如果不想手动创建项目文件，可以使用 Visual Studio 或 .NET Core SDK 生成项目。</span><span class="sxs-lookup"><span data-stu-id="a22b6-157">If you don't want to create the project file manually, you can use Visual Studio or the .NET Core SDK to generate the project.</span></span> <span data-ttu-id="a22b6-158">但是，必须删除项目模板生成的所有其他文件（项目文件除外）。</span><span class="sxs-lookup"><span data-stu-id="a22b6-158">However, you must delete all other files generated by the project template except for the project file.</span></span> <span data-ttu-id="a22b6-159">若要使用 SDK，请从 SolutionFolder 目录运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a22b6-159">To use the SDK, run the following command from the **SolutionFolder** directory:</span></span>

```cli
dotnet new wpf -o MyWPFAppCore -n MyWPFCore
```

<span data-ttu-id="a22b6-160">创建“MyWPFCore.csproj”后，目录结构应如下所示：</span><span class="sxs-lookup"><span data-stu-id="a22b6-160">After you create the **MyWPFCore.csproj**, your directory structure should look like the following:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyWPFApp
│   └───MyWPF.csproj
└───MyWPFAppCore
    └───MyWPFCore.csproj
```

<span data-ttu-id="a22b6-161">需要使用 Visual Studio 或“SolutionFolder”目录中的 .NET Core CLI 将“MyWPFCore.csproj”项目添加到“MyApps.sln”：</span><span class="sxs-lookup"><span data-stu-id="a22b6-161">You'll want to add the **MyWPFCore.csproj** project to **MyApps.sln** with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```cli
dotnet sln add .\MyWPFAppCore\MyWPFCore.csproj
```

## <a name="fix-assembly-info-generation"></a><span data-ttu-id="a22b6-162">修复程序集信息生成</span><span class="sxs-lookup"><span data-stu-id="a22b6-162">Fix assembly info generation</span></span>

<span data-ttu-id="a22b6-163">使用 .NET Framework 创建的 Windows Presentation Foundation 项目包含一个 `AssemblyInfo.cs` 文件，该文件包含诸如要生成的程序集的版本等程序集特性。</span><span class="sxs-lookup"><span data-stu-id="a22b6-163">Windows Presentation Foundation projects that were created with .NET Framework include an `AssemblyInfo.cs` file, which contains assembly attributes such as the version of the assembly to be generated.</span></span> <span data-ttu-id="a22b6-164">SDK 样式的项目会根据 SDK 项目文件自动生成此信息。</span><span class="sxs-lookup"><span data-stu-id="a22b6-164">SDK-style projects automatically generate this information for you based on the SDK project file.</span></span> <span data-ttu-id="a22b6-165">同时具有两种类型的“程序集信息”时，会产生冲突。</span><span class="sxs-lookup"><span data-stu-id="a22b6-165">Having both types of "assembly info" creates a conflict.</span></span> <span data-ttu-id="a22b6-166">通过禁用自动生成可以解决此问题，这会强制项目使用现有的 `AssemblyInfo.cs` 文件。</span><span class="sxs-lookup"><span data-stu-id="a22b6-166">Resolve this problem by disabling automatic generation, which forces the project to use your existing `AssemblyInfo.cs` file.</span></span>

<span data-ttu-id="a22b6-167">若要添加到主 `<PropertyGroup>` 节点，有三个设置项。</span><span class="sxs-lookup"><span data-stu-id="a22b6-167">There are three settings to add to the main `<PropertyGroup>` node.</span></span> 

- <span data-ttu-id="a22b6-168">**GenerateAssemblyInfo**\\</span><span class="sxs-lookup"><span data-stu-id="a22b6-168">**GenerateAssemblyInfo**\\</span></span>
<span data-ttu-id="a22b6-169">将此属性设置为 `false` 时，它不会生成程序集特性。</span><span class="sxs-lookup"><span data-stu-id="a22b6-169">When you set this property to `false`, it won't generate the assembly attributes.</span></span> <span data-ttu-id="a22b6-170">这可以避免与 .NET Framework 项目中的现有 `AssemblyInfo.cs` 文件冲突。</span><span class="sxs-lookup"><span data-stu-id="a22b6-170">This avoids the conflict with the existing `AssemblyInfo.cs` file from the .NET Framework project.</span></span>

- <span data-ttu-id="a22b6-171">**AssemblyName**\\</span><span class="sxs-lookup"><span data-stu-id="a22b6-171">**AssemblyName**\\</span></span>
<span data-ttu-id="a22b6-172">此属性的值是编译时创建的输出二进制。</span><span class="sxs-lookup"><span data-stu-id="a22b6-172">The value of this property is the output binary created when you compile.</span></span> <span data-ttu-id="a22b6-173">该名称不需要添加扩展名。</span><span class="sxs-lookup"><span data-stu-id="a22b6-173">The name doesn't need an extension added to it.</span></span> <span data-ttu-id="a22b6-174">例如，使用 `MyCoreApp` 生成 `MyCoreApp.exe`。</span><span class="sxs-lookup"><span data-stu-id="a22b6-174">For example, using `MyCoreApp` produces `MyCoreApp.exe`.</span></span>

- <span data-ttu-id="a22b6-175">**RootNamespace**\\</span><span class="sxs-lookup"><span data-stu-id="a22b6-175">**RootNamespace**\\</span></span>
<span data-ttu-id="a22b6-176">项目使用的默认命名空间。</span><span class="sxs-lookup"><span data-stu-id="a22b6-176">The default namespace used by your project.</span></span> <span data-ttu-id="a22b6-177">它应该与 .NET Framework 项目的默认命名空间匹配。</span><span class="sxs-lookup"><span data-stu-id="a22b6-177">This should match the default namespace of the .NET Framework project.</span></span>

<span data-ttu-id="a22b6-178">将这三个元素添加到 `MyWPFCore.csproj` 文件中的 `<PropertyGroup>` 节点：</span><span class="sxs-lookup"><span data-stu-id="a22b6-178">Add these three elements to the `<PropertyGroup>` node in the `MyWPFCore.csproj` file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWPF>true</UseWPF>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreApp</AssemblyName>
    <RootNamespace>MyWPF</RootNamespace>
  </PropertyGroup>

</Project>
```

## <a name="add-source-code"></a><span data-ttu-id="a22b6-179">添加源代码</span><span class="sxs-lookup"><span data-stu-id="a22b6-179">Add source code</span></span>
<span data-ttu-id="a22b6-180">现在，“MyWPFCore.csproj”项目不编译任何代码。</span><span class="sxs-lookup"><span data-stu-id="a22b6-180">Right now, the **MyWPFCore.csproj** project doesn't compile any code.</span></span> <span data-ttu-id="a22b6-181">默认情况下，.NET Core 项目会自动包含当前目录和所有子目录中的所有源代码。</span><span class="sxs-lookup"><span data-stu-id="a22b6-181">By default, .NET Core projects automatically include all source code in the current directory and any child directories.</span></span> <span data-ttu-id="a22b6-182">必须使用相对路径配置项目以包含 .NET Framework 项目中的代码。</span><span class="sxs-lookup"><span data-stu-id="a22b6-182">You must configure the project to include code from the .NET Framework project using a relative path.</span></span> <span data-ttu-id="a22b6-183">如果 .NET Framework 项目使用了“.resx”文件作为窗口和控件的图标和资源，则也需要包含这些文件。</span><span class="sxs-lookup"><span data-stu-id="a22b6-183">If your .NET Framework project used **.resx** files for icons and resources for your windows and controls, you'll need to include those too.</span></span> 

<span data-ttu-id="a22b6-184">需要添加到项目中的第一个 `<ItemGroup>` 节点将包括“App.xaml”文件，该文件代表你的应用使用的启动配置和资源。</span><span class="sxs-lookup"><span data-stu-id="a22b6-184">The first `<ItemGroup>` node you need to add to your project includes the **App.xaml** file that represents the startup config and resources your app uses.</span></span> <span data-ttu-id="a22b6-185">“App.xaml”文件还会附带“App.xaml.cs”文件，但它将自动包含在不同的 `<ItemGroup>` 中。</span><span class="sxs-lookup"><span data-stu-id="a22b6-185">The **App.xaml** file also has an accompanying **App.xaml.cs** file, but it will be automatically included in a different `<ItemGroup>`.</span></span>

```xml
  <ItemGroup>
    <ApplicationDefinition Include="..\MyWPFApp\App.xaml">
      <Generator>MSBuild:Compile</Generator>
    </ApplicationDefinition>
  </ItemGroup>
```

<span data-ttu-id="a22b6-186">接下来，将以下 `<ItemGroup>` 节点添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="a22b6-186">Next, add the following `<ItemGroup>` node to your project.</span></span> <span data-ttu-id="a22b6-187">每个语句都包含一个文件 glob 模式，其中包含子目录。</span><span class="sxs-lookup"><span data-stu-id="a22b6-187">Each statement includes a file glob pattern that includes child directories.</span></span> <span data-ttu-id="a22b6-188">它包括项目的源代码、任何设置文件和任何资源。</span><span class="sxs-lookup"><span data-stu-id="a22b6-188">It includes the source code for your project, any settings files, and any resources.</span></span> <span data-ttu-id="a22b6-189">将会显式排除“obj”目录。</span><span class="sxs-lookup"><span data-stu-id="a22b6-189">The **obj** directory is explicitly excluded.</span></span>

```xml
  <ItemGroup>
    <Compile Include="..\MyWPFApp\**\*.cs" Exclude="..\MyWPFApp\obj\**" />
    <None Include="..\MyWPFApp\**\*.settings" />
    <EmbeddedResource Include="..\MyWPFApp\**\*.resx" />
  </ItemGroup>
```

<span data-ttu-id="a22b6-190">接下来，包括另一个 `<ItemGroup>` 节点，该节点包含项目中每个“xaml”文件（“App.xaml”文件除外）的 `<Page>` 条目。</span><span class="sxs-lookup"><span data-stu-id="a22b6-190">Next, include another `<ItemGroup>` node that contains a `<Page>` entry for every **xaml** file in your project except the **App.xaml** file.</span></span> <span data-ttu-id="a22b6-191">它们包含“xaml”格式的所有窗口、页面和资源。</span><span class="sxs-lookup"><span data-stu-id="a22b6-191">These contain all of the windows, pages, and resources that are in **xaml** format.</span></span> <span data-ttu-id="a22b6-192">不能在此处使用 glob 模式，必须为每个文件添加一个条目并指出使用的 `<Generator>`。</span><span class="sxs-lookup"><span data-stu-id="a22b6-192">You cannot use a glob pattern here and must add an entry for every file and indicate the `<Generator>` used.</span></span>

```xml
  <ItemGroup>
    <Page Include="..\MyWPFApp\MainWindow.xaml">
      <Generator>MSBuild:Compile</Generator>
    </Page>
  </ItemGroup>
```

## <a name="add-nuget-packages"></a><span data-ttu-id="a22b6-193">添加 NuGet 包</span><span class="sxs-lookup"><span data-stu-id="a22b6-193">Add NuGet packages</span></span>

<span data-ttu-id="a22b6-194">将 .NET Framework 项目引用的每个 NuGet 包添加到 .NET Core 项目。</span><span class="sxs-lookup"><span data-stu-id="a22b6-194">Add each NuGet package referenced by the .NET Framework project to the .NET Core project.</span></span> 

<span data-ttu-id="a22b6-195">你的 .NET Framework WPF 应用很可能有一个“packages.config”文件，其中包含项目引用的所有 NuGet 包的列表。</span><span class="sxs-lookup"><span data-stu-id="a22b6-195">Most likely your .NET Framework WPF app has a **packages.config** file that contains a list of all of the NuGet packages that are referenced by your project.</span></span> <span data-ttu-id="a22b6-196">可以查看此列表以确定要添加到 .NET Core 项目的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="a22b6-196">You can look at this list to determine which NuGet packages to add to the .NET Core project.</span></span> <span data-ttu-id="a22b6-197">例如，如果 .NET Framework 项目引用了 `MahApps.Metro` NuGet 包，请使用 Visual Studio 将其添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="a22b6-197">For example, if the .NET Framework project references the `MahApps.Metro` NuGet package, add it to the project with Visual Studio.</span></span> <span data-ttu-id="a22b6-198">还可以使用 Visual Studio 从 SolutionFolder 目录添加包引用：</span><span class="sxs-lookup"><span data-stu-id="a22b6-198">You can also add the package reference with the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```cli
dotnet add .\MyWPFAppCore\MyWPFCore.csproj package MahApps.Metro -v 2.0.0-alpha0262
```

<span data-ttu-id="a22b6-199">之前的命令会将以下 NuGet 引用添加到 MyWPFCore.csproj 项目：</span><span class="sxs-lookup"><span data-stu-id="a22b6-199">The previous command would add the following NuGet reference to the **MyWPFCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="MahApps.Metro" Version="2.0.0-alpha0262" />
  </ItemGroup>
```

## <a name="problems-compiling"></a><span data-ttu-id="a22b6-200">编译问题</span><span class="sxs-lookup"><span data-stu-id="a22b6-200">Problems compiling</span></span>

<span data-ttu-id="a22b6-201">如果在编译项目时遇到问题，可能是由于正在使用的一些仅适用于 Windows 的 API 在 .NET Framework 中可用，但在 .NET Core 中不可用。</span><span class="sxs-lookup"><span data-stu-id="a22b6-201">If you have problems compiling your projects, you may be using some Windows-only APIs that are available in .NET Framework but not available in .NET Core.</span></span> <span data-ttu-id="a22b6-202">可以尝试将 [Windows 兼容包][compat-pack] NuGet 包添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="a22b6-202">You can try adding the [Windows Compatibility Pack][compat-pack] NuGet package to your project.</span></span> <span data-ttu-id="a22b6-203">此包仅在 Windows 上运行，为 .NET Core 和 .NET Standard 项目添加了大约 20,000 个 Windows API。</span><span class="sxs-lookup"><span data-stu-id="a22b6-203">This package only runs on Windows and adds about 20,000 Windows APIs to .NET Core and .NET Standard projects.</span></span>

```cli
dotnet add .\MyWPFAppCore\MyWPFCore.csproj package Microsoft.Windows.Compatibility
```

<span data-ttu-id="a22b6-204">上一个命令会将以下内容添加到 MyWPFCore.csproj 项目：</span><span class="sxs-lookup"><span data-stu-id="a22b6-204">The previous command adds the following to the **MyWPFCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.Windows.Compatibility" Version="2.0.1" />
  </ItemGroup>
```

## <a name="wpf-designer"></a><span data-ttu-id="a22b6-205">WPF 设计器</span><span class="sxs-lookup"><span data-stu-id="a22b6-205">WPF Designer</span></span>

<span data-ttu-id="a22b6-206">如本文所述，Visual Studio 2019 预览版/RC 仅支持 .NET Framework 项目中的 WPF 设计器。</span><span class="sxs-lookup"><span data-stu-id="a22b6-206">As detailed in this article, Visual Studio 2019 Preview/RC only supports the WPF Designer in .NET Framework projects.</span></span> <span data-ttu-id="a22b6-207">通过创建并行 .NET Core 项目，可以在使用 .NET Framework 项目设计窗体时通过 .NET Core 测试项目。</span><span class="sxs-lookup"><span data-stu-id="a22b6-207">By creating a side-by-side .NET Core project, you can test your project with .NET Core while you use the .NET Framework project to design forms.</span></span> <span data-ttu-id="a22b6-208">解决方案文件包括 .NET Framework 和 .NET Core 项目。</span><span class="sxs-lookup"><span data-stu-id="a22b6-208">Your solution file includes both the .NET Framework and .NET Core projects.</span></span> <span data-ttu-id="a22b6-209">在 .NET Framework 项目中添加和设计窗体和控件，并且根据添加到 .NET Core 项目的文件 glob 模式，任何新的或更改的文件将自动包含在 .NET Core 项目中。</span><span class="sxs-lookup"><span data-stu-id="a22b6-209">Add and design your forms and controls in the .NET Framework project, and based on the file glob patterns we added to the .NET Core projects, any new or changed files will automatically be included in the .NET Core projects.</span></span>

<span data-ttu-id="a22b6-210">一旦 Visual Studio 2019 支持 WPF 设计器，就可以将 .NET Core 项目文件的内容复制/粘贴到 .NET Framework 项目文件中。</span><span class="sxs-lookup"><span data-stu-id="a22b6-210">Once Visual Studio 2019 supports the WPF Designer, you can copy/paste the content of your .NET Core project file into the .NET Framework project file.</span></span> <span data-ttu-id="a22b6-211">然后删除使用 `<Source>` 和 `<EmbeddedResource>` 项添加的文件 glob 模式。</span><span class="sxs-lookup"><span data-stu-id="a22b6-211">Then delete the file glob patterns added with the `<Source>` and `<EmbeddedResource>` items.</span></span> <span data-ttu-id="a22b6-212">修复由应用程序使用的任何项目引用的路径。</span><span class="sxs-lookup"><span data-stu-id="a22b6-212">Fix the paths to any project reference used by your app.</span></span> <span data-ttu-id="a22b6-213">这可以有效地将 .NET Framework 项目升级到 .NET Core 项目。</span><span class="sxs-lookup"><span data-stu-id="a22b6-213">This effectively upgrades the .NET Framework project to a .NET Core project.</span></span>
 
## <a name="next-steps"></a><span data-ttu-id="a22b6-214">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a22b6-214">Next steps</span></span>

* <span data-ttu-id="a22b6-215">详细了解 [Windows 兼容包][compat-pack]。</span><span class="sxs-lookup"><span data-stu-id="a22b6-215">Read more about the [Windows Compatibility Pack][compat-pack].</span></span>
* <span data-ttu-id="a22b6-216">观看关于将 .NET Framework WPF 项目移植到 .NET Core 的[视频](https://www.youtube.com/watch?v=5MomsgkWkVw&list=PLS__JrkRveTMiWxG-Lv4cBwYfMQ6m2gmt)。</span><span class="sxs-lookup"><span data-stu-id="a22b6-216">Watch a [video on porting](https://www.youtube.com/watch?v=5MomsgkWkVw&list=PLS__JrkRveTMiWxG-Lv4cBwYfMQ6m2gmt) your .NET Framework WPF project to .NET Core.</span></span>

[compat-pack]: windows-compat-pack.md
