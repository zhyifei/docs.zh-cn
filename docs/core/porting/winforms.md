---
title: 将 Windows 窗体应用程序移植到 .NET Core 3.0
description: 了解如何将 .NET Framework Windows 窗体应用程序移植到适用于 Windows 的 .NET Core 3.0。
author: Thraka
ms.author: adegeo
ms.date: 03/01/2019
ms.custom: ''
ms.openlocfilehash: aebfaa85338e014ca47256b85a1bd6529ad803bb
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59327160"
---
# <a name="how-to-port-a-windows-forms-desktop-app-to-net-core"></a><span data-ttu-id="1e5f9-103">如何：将 Windows 窗体桌面应用程序移植到 .NET Core</span><span class="sxs-lookup"><span data-stu-id="1e5f9-103">How to: Port a Windows Forms desktop app to .NET Core</span></span>

<span data-ttu-id="1e5f9-104">本文介绍如何将基于 Windows 窗体的桌面应用程序从 .NET Framework 移植到 .NET Core 3.0。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-104">This article describes how to port your Windows Forms-based desktop app from .NET Framework to .NET Core 3.0.</span></span> <span data-ttu-id="1e5f9-105">.NET Core 3.0 SDK 支持 Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-105">The .NET Core 3.0 SDK includes support for Windows Forms applications.</span></span> <span data-ttu-id="1e5f9-106">Windows 窗体仍是仅适用于 Windows 的框架，并且只能在 Windows 上运行。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-106">Windows Forms is still a Windows-only framework and only runs on Windows.</span></span> <span data-ttu-id="1e5f9-107">示例使用 .NET Core SDK CLI 创建和管理项目。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-107">This example uses the .NET Core SDK CLI to create and manage your project.</span></span>

<span data-ttu-id="1e5f9-108">本文中的各种名称用于标识迁移所用的文件类型。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-108">In this article, various names are used to identify types of files used for migration.</span></span> <span data-ttu-id="1e5f9-109">迁移项目时，你的文件将以不同的名称命名，因此，请自行在心里将它们与下面列出的文件进行匹配：</span><span class="sxs-lookup"><span data-stu-id="1e5f9-109">When migrating your project, your files will be named differently, so mentally match them to the ones listed below:</span></span>

| <span data-ttu-id="1e5f9-110">文件</span><span class="sxs-lookup"><span data-stu-id="1e5f9-110">File</span></span> | <span data-ttu-id="1e5f9-111">说明</span><span class="sxs-lookup"><span data-stu-id="1e5f9-111">Description</span></span> |
| ---- | ----------- |
| **<span data-ttu-id="1e5f9-112">MyApps.sln</span><span class="sxs-lookup"><span data-stu-id="1e5f9-112">MyApps.sln</span></span>** | <span data-ttu-id="1e5f9-113">解决方案文件的名称。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-113">The name of the solution file.</span></span> |
| **<span data-ttu-id="1e5f9-114">MyForms.csproj</span><span class="sxs-lookup"><span data-stu-id="1e5f9-114">MyForms.csproj</span></span>** | <span data-ttu-id="1e5f9-115">要移植的 .NET Framework Windows 窗体项目的名称。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-115">The name of the .NET Framework Windows Forms project to port.</span></span> |
| **<span data-ttu-id="1e5f9-116">MyFormsCore.csproj</span><span class="sxs-lookup"><span data-stu-id="1e5f9-116">MyFormsCore.csproj</span></span>** | <span data-ttu-id="1e5f9-117">创建的新 .NET Core 项目的名称。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-117">The name of the new .NET Core project you create.</span></span> |
| **<span data-ttu-id="1e5f9-118">MyAppCore.exe</span><span class="sxs-lookup"><span data-stu-id="1e5f9-118">MyAppCore.exe</span></span>** | <span data-ttu-id="1e5f9-119">.NET Core Windows 窗体应用程序的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-119">The .NET Core Windows Forms app executable.</span></span> |

## <a name="prerequisites"></a><span data-ttu-id="1e5f9-120">系统必备</span><span class="sxs-lookup"><span data-stu-id="1e5f9-120">Prerequisites</span></span>

- <span data-ttu-id="1e5f9-121">适用于要执行的任何设计器工作的 [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-121">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) for any designer work you want to do.</span></span>

  <span data-ttu-id="1e5f9-122">安装以下 Visual Studio 工作负载：</span><span class="sxs-lookup"><span data-stu-id="1e5f9-122">Install the following Visual Studio workloads:</span></span>
  - <span data-ttu-id="1e5f9-123">.NET 桌面开发</span><span class="sxs-lookup"><span data-stu-id="1e5f9-123">.NET desktop development</span></span>
  - <span data-ttu-id="1e5f9-124">.NET 跨平台开发</span><span class="sxs-lookup"><span data-stu-id="1e5f9-124">.NET cross-platform development</span></span>

- <span data-ttu-id="1e5f9-125">在解决方案中顺利生成和运行的有效 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-125">A working Windows Forms project in a solution that builds and runs without issue.</span></span>
- <span data-ttu-id="1e5f9-126">项目必须使用 C# 进行编码。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-126">Your project must be coded in C#.</span></span> 
- <span data-ttu-id="1e5f9-127">安装最新 [.NET Core 3.0](https://aka.ms/netcore3download) 预览版。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-127">Install the latest [.NET Core 3.0](https://aka.ms/netcore3download) preview.</span></span>

>[!NOTE]
><span data-ttu-id="1e5f9-128">Visual Studio 2017 不支持 .NET Core 3.0 项目。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-128">**Visual Studio 2017** doesn't support .NET Core 3.0 projects.</span></span> <span data-ttu-id="1e5f9-129">Visual Studio 2019 支持 .NET Core 3.0 项目，但尚不支持适用于 .NET Core 3.0 Windows 窗体项目的可视化设计器。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-129">**Visual Studio 2019** supports .NET Core 3.0 projects but doesn't yet support the visual designer for .NET Core 3.0 Windows Forms projects.</span></span> <span data-ttu-id="1e5f9-130">要使用可视化设计器，解决方案中必须包含可与 .NET Core 项目共享窗体文件的 .NET Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-130">To use the visual designer, you must have a .NET Windows Forms project in your solution that shares the forms files with the .NET Core project.</span></span>

### <a name="consider"></a><span data-ttu-id="1e5f9-131">考虑</span><span class="sxs-lookup"><span data-stu-id="1e5f9-131">Consider</span></span>

<span data-ttu-id="1e5f9-132">移植 .NET Framework Windows 窗体应用程序时，必须考虑以下几个事项。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-132">When porting a .NET Framework Windows Forms application, there are a few things you must consider.</span></span>

01. <span data-ttu-id="1e5f9-133">检查应用程序是否适合迁移。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-133">Check that your application is a good candidate for migration.</span></span>

    <span data-ttu-id="1e5f9-134">使用 [.NET 可移植性分析器](../../standard/analyzers/portability-analyzer.md)确定项目将会迁移到 .NET Core 3.0。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-134">Use the [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) to determine if your project will migrate to .NET Core 3.0.</span></span> <span data-ttu-id="1e5f9-135">如果项目存在 .NET Core 3.0 相关问题，分析器可帮助你识别这些问题。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-135">If your project has issues with .NET Core 3.0, the analyzer helps you identify those problems.</span></span>

01. <span data-ttu-id="1e5f9-136">使用的是不同版本的 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-136">You're using a different version of Windows Forms.</span></span>

    <span data-ttu-id="1e5f9-137">发布 .NET Core 3.0 预览版 1 时，Windows 窗体在 GitHub 上公布了开放源代码。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-137">When .NET Core 3.0 Preview 1 was released, Windows Forms went open-source on GitHub.</span></span> <span data-ttu-id="1e5f9-138">.NET Core Windows 窗体的代码是 .NET Framework Windows 窗体基本代码的一个分支。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-138">The code for .NET Core Windows Forms is a fork of the .NET Framework Windows Forms code base.</span></span> <span data-ttu-id="1e5f9-139">可能存在一些差异导致应用程序无法移植。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-139">It's possible some differences exist and your app won't port.</span></span>

01. <span data-ttu-id="1e5f9-140">使用 [Windows 兼容包][compat-pack]可能有助于进行迁移。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-140">The [Windows Compatibility Pack][compat-pack] may help you migrate.</span></span>

    <span data-ttu-id="1e5f9-141">某些 API 可在 .NET Framework 中使用，但不可用于 .NET Core 3.0。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-141">Some APIs that are available in .NET Framework aren't available in .NET Core 3.0.</span></span> <span data-ttu-id="1e5f9-142">[Windows 兼容包][compat-pack] 增加了很多这些 API，有助于使 Windows 窗体应用程序与 .NET Core 兼容。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-142">The [Windows Compatibility Pack][compat-pack] adds many of these APIs and may help your Windows Forms app become compatible with .NET Core.</span></span>

01. <span data-ttu-id="1e5f9-143">更新项目使用的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-143">Update the NuGet packages used by your project.</span></span>

    <span data-ttu-id="1e5f9-144">在执行任何迁移之前使用最新版 NuGet 包始终是一个不错的做法。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-144">It's always a good practice to use the latest versions of NuGet packages before any migration.</span></span> <span data-ttu-id="1e5f9-145">如果应用程序引用任何 NuGet 包，请将它们更新到最新版本。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-145">If your application is referencing any NuGet packages, update them to the latest version.</span></span> <span data-ttu-id="1e5f9-146">确保成功生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-146">Ensure your application builds successfully.</span></span> <span data-ttu-id="1e5f9-147">升级后，如果存在任何包错误，请将包降级到不会破坏代码的最新版本。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-147">After upgrading, if there are any package errors, downgrade the package to the latest version that doesn't break your code.</span></span>

01. <span data-ttu-id="1e5f9-148">Visual Studio 2019 尚不支持适用于 .NET Core 3.0 的窗体设计器</span><span class="sxs-lookup"><span data-stu-id="1e5f9-148">Visual Studio 2019 doesn't yet support the Forms Designer for .NET Core 3.0</span></span>

    <span data-ttu-id="1e5f9-149">目前，如果要从 Visual Studio 中使用窗体设计器，需要保留现有的 .NET Framework Windows 窗体项目文件。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-149">Currently, you need to keep your existing .NET Framework Windows Forms project file if you want to use the Forms Designer from Visual Studio.</span></span>

## <a name="create-a-new-sdk-project"></a><span data-ttu-id="1e5f9-150">创建新的 SDK 项目</span><span class="sxs-lookup"><span data-stu-id="1e5f9-150">Create a new SDK project</span></span>

<span data-ttu-id="1e5f9-151">创建的新 .NET Core 3.0 项目必须位于不同于 .NET Framework 项目的目录中。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-151">The new .NET Core 3.0 project you create must be in a different directory from your .NET Framework project.</span></span> <span data-ttu-id="1e5f9-152">如果它们位于同一目录中，可能会与 obj 目录中生成的文件发生冲突。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-152">If they're both in the same directory, you may run into conflicts with the files that are generated in the **obj** directory.</span></span> <span data-ttu-id="1e5f9-153">本例中，我们将在 SolutionFolder 目录中创建一个名为 MyFormsAppCore 的目录：</span><span class="sxs-lookup"><span data-stu-id="1e5f9-153">In this example, we'll create a directory named **MyFormsAppCore** in the **SolutionFolder** directory:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
└───MyFormsAppCore      <--- New folder for core project
```

<span data-ttu-id="1e5f9-154">接下来，需要在 MyFormsAppCore 目录中创建 MyFormsCore.csproj 项目。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-154">Next, you need to create the **MyFormsCore.csproj** project in the **MyFormsAppCore** directory.</span></span> <span data-ttu-id="1e5f9-155">可以使用所选的文本编辑器手动创建此文件。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-155">You can create this file manually by using the text editor of choice.</span></span> <span data-ttu-id="1e5f9-156">粘贴以下 XML：</span><span class="sxs-lookup"><span data-stu-id="1e5f9-156">Paste in the following XML:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="1e5f9-157">如果不想手动创建项目文件，可以使用 Visual Studio 或 .NET Core SDK 生成项目。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-157">If you don't want to create the project file manually, you can use Visual Studio or the .NET Core SDK to generate the project.</span></span> <span data-ttu-id="1e5f9-158">但是，必须删除项目模板生成的所有其他文件（项目文件除外）。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-158">However, you must delete all other files generated by the project template except for the project file.</span></span> <span data-ttu-id="1e5f9-159">若要使用 SDK，请从 SolutionFolder 目录运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1e5f9-159">To use the SDK, run the following command from the **SolutionFolder** directory:</span></span>

```cli
dotnet new winforms -o MyFormsAppCore -n MyFormsCore
```

<span data-ttu-id="1e5f9-160">创建 MyFormsCore.csproj 后，目录结构应如下所示：</span><span class="sxs-lookup"><span data-stu-id="1e5f9-160">After you create the **MyFormsCore.csproj**, your directory structure should look like the following:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
└───MyFormsAppCore
    └───MyFormsCore.csproj
```

<span data-ttu-id="1e5f9-161">需要使用 Visual Studio 或 SolutionFolder 目录中的 .NET Core CLI 将 MyFormsCore.csproj 项目添加到 MyApps.sln：</span><span class="sxs-lookup"><span data-stu-id="1e5f9-161">You'll want to add the **MyFormsCore.csproj** project to **MyApps.sln** with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```cli
dotnet sln add .\MyFormsAppCore\MyFormsCore.csproj
```

## <a name="fix-assembly-info-generation"></a><span data-ttu-id="1e5f9-162">修复程序集信息生成</span><span class="sxs-lookup"><span data-stu-id="1e5f9-162">Fix assembly info generation</span></span>

<span data-ttu-id="1e5f9-163">使用 .NET Framework 创建的 Windows 窗体项目包含一个 `AssemblyInfo.cs` 文件，该文件包含诸如要生成的程序集的版本等程序集特性。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-163">Windows Forms projects that were created with .NET Framework include an `AssemblyInfo.cs` file, which contains assembly attributes such as the version of the assembly to be generated.</span></span> <span data-ttu-id="1e5f9-164">SDK 样式的项目会根据 SDK 项目文件自动生成此信息。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-164">SDK-style projects automatically generate this information for you based on the SDK project file.</span></span> <span data-ttu-id="1e5f9-165">同时具有两种类型的“程序集信息”时，会产生冲突。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-165">Having both types of "assembly info" creates a conflict.</span></span> <span data-ttu-id="1e5f9-166">通过禁用自动生成可以解决此问题，这会强制项目使用现有的 `AssemblyInfo.cs` 文件。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-166">Resolve this problem by disabling automatic generation, which forces the project to use your existing `AssemblyInfo.cs` file.</span></span>

<span data-ttu-id="1e5f9-167">若要添加到主 `<PropertyGroup>` 节点，有三个设置项。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-167">There are three settings to add to the main `<PropertyGroup>` node.</span></span> 

- **<span data-ttu-id="1e5f9-168">GenerateAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="1e5f9-168">GenerateAssemblyInfo</span></span>**\
<span data-ttu-id="1e5f9-169">将此属性设置为 `false` 时，它不会生成程序集特性。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-169">When you set this property to `false`, it won't generate the assembly attributes.</span></span> <span data-ttu-id="1e5f9-170">这可以避免与 .NET Framework 项目中的现有 `AssemblyInfo.cs` 文件冲突。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-170">This avoids the conflict with the existing `AssemblyInfo.cs` file from the .NET Framework project.</span></span>

- **<span data-ttu-id="1e5f9-171">AssemblyName</span><span class="sxs-lookup"><span data-stu-id="1e5f9-171">AssemblyName</span></span>**\
<span data-ttu-id="1e5f9-172">此属性的值是编译时创建的输出二进制。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-172">The value of this property is the output binary created when you compile.</span></span> <span data-ttu-id="1e5f9-173">该名称不需要添加扩展名。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-173">The name doesn't need an extension added to it.</span></span> <span data-ttu-id="1e5f9-174">例如，使用 `MyCoreApp` 生成 `MyCoreApp.exe`。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-174">For example, using `MyCoreApp` produces `MyCoreApp.exe`.</span></span>

- **<span data-ttu-id="1e5f9-175">RootNamespace</span><span class="sxs-lookup"><span data-stu-id="1e5f9-175">RootNamespace</span></span>**\
<span data-ttu-id="1e5f9-176">项目使用的默认命名空间。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-176">The default namespace used by your project.</span></span> <span data-ttu-id="1e5f9-177">它应该与 .NET Framework 项目的默认命名空间匹配。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-177">This should match the default namespace of the .NET Framework project.</span></span>

<span data-ttu-id="1e5f9-178">将这三个元素添加到 `MyFormsCore.csproj` 文件中的 `<PropertyGroup>` 节点：</span><span class="sxs-lookup"><span data-stu-id="1e5f9-178">Add these three elements to the `<PropertyGroup>` node in the `MyFormsCore.csproj` file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreApp</AssemblyName>
    <RootNamespace>WindowsFormsApp1</RootNamespace>
  </PropertyGroup>

</Project>
```

## <a name="add-source-code"></a><span data-ttu-id="1e5f9-179">添加源代码</span><span class="sxs-lookup"><span data-stu-id="1e5f9-179">Add source code</span></span>

<span data-ttu-id="1e5f9-180">现在，MyFormsCore.csproj 项目不编译任何代码。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-180">Right now, the **MyFormsCore.csproj** project doesn't compile any code.</span></span> <span data-ttu-id="1e5f9-181">默认情况下，.NET Core 项目会自动包含当前目录和所有子目录中的所有源代码。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-181">By default, .NET Core projects automatically include all source code in the current directory and any child directories.</span></span> <span data-ttu-id="1e5f9-182">必须使用相对路径配置项目以包含 .NET Framework 项目中的代码。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-182">You must configure the project to include code from the .NET Framework project using a relative path.</span></span> <span data-ttu-id="1e5f9-183">如果 .NET Framework 项目使用了 .resx 文件作为窗体的图标和资源，则还需要包含这些文件。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-183">If your .NET Framework project used **.resx** files for icons and resources for your forms, you'll need to include those too.</span></span> 

<span data-ttu-id="1e5f9-184">将以下 `<ItemGroup>` 节点添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-184">Add the following `<ItemGroup>` node to your project.</span></span> <span data-ttu-id="1e5f9-185">每个语句都包含一个文件 glob 模式，其中包含子目录。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-185">Each statement includes a file glob pattern that includes child directories.</span></span>

```xml
  <ItemGroup>
    <Compile Include="..\MyFormsApp\**\*.cs" />
    <EmbeddedResource Include="..\MyFormsApp\**\*.resx" />
  </ItemGroup>
```

<span data-ttu-id="1e5f9-186">或者，可以为 .NET Framework 项目中的每个文件创建一个 `<Compile>` 或 `<EmbeddedResource>` 条目。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-186">Alternatively, you can create a `<Compile>` or `<EmbeddedResource>` entry for each file in your .NET Framework project.</span></span>

## <a name="add-nuget-packages"></a><span data-ttu-id="1e5f9-187">添加 NuGet 包</span><span class="sxs-lookup"><span data-stu-id="1e5f9-187">Add NuGet packages</span></span>

<span data-ttu-id="1e5f9-188">将 .NET Framework 项目引用的每个 NuGet 包添加到 .NET Core 项目。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-188">Add each NuGet package referenced by the .NET Framework project to the .NET Core project.</span></span> 

<span data-ttu-id="1e5f9-189">很可能你的 .NET Framework Windows 窗体应用程序有一个 packages.config 文件，其中包含项目引用的所有 NuGet 包的列表。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-189">Most likely your .NET Framework Windows Forms app has a **packages.config** file that contains a list of all of the NuGet packages that are referenced by your project.</span></span> <span data-ttu-id="1e5f9-190">可以查看此列表以确定要添加到 .NET Core 项目的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-190">You can look at this list to determine which NuGet packages to add to the .NET Core project.</span></span> <span data-ttu-id="1e5f9-191">例如，如果 .NET Framework 项目引用了 `MetroFramework`、`MetroFramework.Design` 和 `MetroFramework.Fonts` NuGet 包，则使用 Visual Studio 或 SolutionFolder 目录中的 .NET Core CLI 将每个包添加到项目中：</span><span class="sxs-lookup"><span data-stu-id="1e5f9-191">For example, if the .NET Framework project referenced the `MetroFramework`, `MetroFramework.Design`, and `MetroFramework.Fonts` NuGet packages, add each to the project with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```cli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework.Design
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework.Fonts
```

<span data-ttu-id="1e5f9-192">之前的命令会将以下 NuGet 引用添加到 MyFormsCore.csproj 项目：</span><span class="sxs-lookup"><span data-stu-id="1e5f9-192">The previous commands would add the following NuGet references to the **MyFormsCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="MetroFramework" Version="1.2.0.3" />
    <PackageReference Include="MetroFramework.Design" Version="1.2.0.3" />
    <PackageReference Include="MetroFramework.Fonts" Version="1.2.0.3" />
  </ItemGroup>
```

## <a name="port-control-libraries"></a><span data-ttu-id="1e5f9-193">移植控件库</span><span class="sxs-lookup"><span data-stu-id="1e5f9-193">Port control libraries</span></span>

<span data-ttu-id="1e5f9-194">如果要移植 Windows 窗体控件库项目，操作说明与移植 .NET Framework Windows 窗体应用程序项目相同，只不过在一些设置上存在差异。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-194">If you have a Windows Forms Controls library project to port, the directions are the same as porting a .NET Framework Windows Forms app project, except for a few settings.</span></span> <span data-ttu-id="1e5f9-195">并且此操作中不编译到可执行文件，而是编译到库。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-195">And instead of compiling to an executable, you compile to a library.</span></span> <span data-ttu-id="1e5f9-196">除了包含源代码的文件 glob 的路径之外，可执行项目和库项目之间的区别也很小。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-196">The difference between the executable project and the library project, besides paths for the file globs that include your source code, is minimal.</span></span>

<span data-ttu-id="1e5f9-197">借助上一步的示例，详细介绍正在处理的项目和文件。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-197">Using the previous step's example, lets expand what projects and files we're working with.</span></span>

| <span data-ttu-id="1e5f9-198">文件</span><span class="sxs-lookup"><span data-stu-id="1e5f9-198">File</span></span> | <span data-ttu-id="1e5f9-199">说明</span><span class="sxs-lookup"><span data-stu-id="1e5f9-199">Description</span></span> |
| ---- | ----------- |
| **<span data-ttu-id="1e5f9-200">MyApps.sln</span><span class="sxs-lookup"><span data-stu-id="1e5f9-200">MyApps.sln</span></span>** | <span data-ttu-id="1e5f9-201">解决方案文件的名称。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-201">The name of the solution file.</span></span> |
| **<span data-ttu-id="1e5f9-202">MyControls.csproj</span><span class="sxs-lookup"><span data-stu-id="1e5f9-202">MyControls.csproj</span></span>** | <span data-ttu-id="1e5f9-203">要移植的 .NET Framework Windows 窗体控件项目的名称。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-203">The name of the .NET Framework Windows Forms Controls project to port.</span></span> |
| **<span data-ttu-id="1e5f9-204">MyControlsCore.csproj</span><span class="sxs-lookup"><span data-stu-id="1e5f9-204">MyControlsCore.csproj</span></span>** | <span data-ttu-id="1e5f9-205">创建的新 .NET Core 库项目的名称。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-205">The name of the new .NET Core library project you create.</span></span> |
| **<span data-ttu-id="1e5f9-206">MyCoreControls.dll</span><span class="sxs-lookup"><span data-stu-id="1e5f9-206">MyCoreControls.dll</span></span>** | <span data-ttu-id="1e5f9-207">.NET Core Windows 窗体控件库。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-207">The .NET Core Windows Forms Controls library.</span></span> |

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
├───MyFormsAppCore
│   └───MyFormsCore.csproj
│
├───MyFormsControls
│   └───MyControls.csproj
└───MyFormsControlsCore
    └───MyControlsCore.csproj   <--- New project for core controls
```

<span data-ttu-id="1e5f9-208">请考虑 `MyControlsCore.csproj` 项目与先前创建的 `MyFormsCore.csproj` 项目之间的差异。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-208">Consider the differences between the `MyControlsCore.csproj` project and the previously created `MyFormsCore.csproj` project.</span></span>

```diff
 <Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

   <PropertyGroup>
-    <OutputType>WinExe</OutputType>
     <TargetFramework>netcoreapp3.0</TargetFramework>
     <UseWindowsForms>true</UseWindowsForms>

     <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
-    <AssemblyName>MyCoreApp</AssemblyName>
-    <RootNamespace>WindowsFormsApp1</RootNamespace>
+    <AssemblyName>MyControlsCore</AssemblyName>
+    <RootNamespace>WindowsFormsControlLibrary1</RootNamespace>
   </PropertyGroup>

   <ItemGroup>
-    <Compile Include="..\MyFormsApp\**\*.cs" />
-    <EmbeddedResource Include="..\MyFormsApp\**\*.resx" />
+    <Compile Include="..\MyFormsControls\**\*.cs" />
+    <EmbeddedResource Include="..\MyFormsControls\**\*.resx" />
   </ItemGroup>

 </Project>
```

<span data-ttu-id="1e5f9-209">以下是 .NET Core Windows 窗体控件库项目文件的示例：</span><span class="sxs-lookup"><span data-stu-id="1e5f9-209">Here is an example of what the .NET Core Windows Forms Controls library project file would look like:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreControls</AssemblyName>
    <RootNamespace>WindowsFormsControlLibrary1</RootNamespace>
  </PropertyGroup>
  
  <ItemGroup>
    <Compile Include="..\MyFormsControls\**\*.cs" />
    <EmbeddedResource Include="..\MyFormsControls\**\*.resx" />
  </ItemGroup>
  
</Project>
```

<span data-ttu-id="1e5f9-210">如你所见，`<OutputType>` 节点已被删除，默认使编译器生成库而不是可执行文件。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-210">As you can see, the `<OutputType>` node was removed, which defaults the compiler to produce a library instead of an executable.</span></span> <span data-ttu-id="1e5f9-211">`<AssemblyName>` 和 `<RootNamespace>` 已更改。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-211">The `<AssemblyName>` and `<RootNamespace>` were changed.</span></span> <span data-ttu-id="1e5f9-212">具体来说，`<RootNamespace>` 应匹配正在移植的 Windows 窗体控件库的命名空间。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-212">Specifically the `<RootNamespace>` should match the namespace of the Windows Forms Controls library you are porting.</span></span> <span data-ttu-id="1e5f9-213">最后，`<Compile>` 和 `<EmbeddedResource>` 节点已调整为指向要移植的 Windows 窗体控件库的文件夹。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-213">And finally, the `<Compile>` and `<EmbeddedResource>` nodes were adjusted to point to the folder of the Windows Forms Controls library you are porting.</span></span>

<span data-ttu-id="1e5f9-214">接下来，在主要的 .NET Core MyFormsCore.csproj 项目中，添加对新 .NET Core Windows 窗体控件库的引用。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-214">Next, in the main .NET Core **MyFormsCore.csproj** project add reference to the new .NET Core Windows Forms Control library.</span></span> <span data-ttu-id="1e5f9-215">使用 Visual Studio 或 .NET Core CLI 从 SolutionFolder 目录添加引用：</span><span class="sxs-lookup"><span data-stu-id="1e5f9-215">Add a reference with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```cli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj reference .\MyFormsControlsCore\MyControlsCore.csproj
```

<span data-ttu-id="1e5f9-216">上一个命令将以下内容添加到 MyFormsCore.csproj 项目中：</span><span class="sxs-lookup"><span data-stu-id="1e5f9-216">The previous command adds the following to the **MyFormsCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <ProjectReference Include="..\MyFormsControlsCore\MyControlsCore.csproj" />
  </ItemGroup>
```

## <a name="problems-compiling"></a><span data-ttu-id="1e5f9-217">编译问题</span><span class="sxs-lookup"><span data-stu-id="1e5f9-217">Problems compiling</span></span>

<span data-ttu-id="1e5f9-218">如果在编译项目时遇到问题，可能是由于正在使用的一些仅适用于 Windows 的 API 在 .NET Framework 中可用，但在 .NET Core 中不可用。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-218">If you have problems compiling your projects, you may be using some Windows-only APIs that are available in .NET Framework but not available in .NET Core.</span></span> <span data-ttu-id="1e5f9-219">可以尝试将 [Windows 兼容包][compat-pack] NuGet 包添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-219">You can try adding the [Windows Compatibility Pack][compat-pack] NuGet package to your project.</span></span> <span data-ttu-id="1e5f9-220">此包仅在 Windows 上运行，为 .NET Core 和 .NET Standard 项目添加了大约 20,000 个 Windows API。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-220">This package only runs on Windows and adds about 20,000 Windows APIs to .NET Core and .NET Standard projects.</span></span>

```cli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package Microsoft.Windows.Compatibility
```

<span data-ttu-id="1e5f9-221">上一个命令将以下内容添加到 MyFormsCore.csproj 项目中：</span><span class="sxs-lookup"><span data-stu-id="1e5f9-221">The previous command adds the following to the **MyFormsCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.Windows.Compatibility" Version="2.0.1" />
  </ItemGroup>
```

## <a name="windows-forms-designer"></a><span data-ttu-id="1e5f9-222">Windows Forms Designer — Windows 窗体设计器</span><span class="sxs-lookup"><span data-stu-id="1e5f9-222">Windows Forms Designer</span></span>

<span data-ttu-id="1e5f9-223">如本文所述，Visual Studio 2019 仅支持 .NET Framework 项目中的窗体设计器。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-223">As detailed in this article, Visual Studio 2019 only supports the Forms Designer in .NET Framework projects.</span></span> <span data-ttu-id="1e5f9-224">通过创建并行 .NET Core 项目，可以在使用 .NET Framework 项目设计窗体时通过 .NET Core 测试项目。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-224">By creating a side-by-side .NET Core project, you can test your project with .NET Core while you use the .NET Framework project to design forms.</span></span> <span data-ttu-id="1e5f9-225">解决方案文件包括 .NET Framework 和 .NET Core 项目。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-225">Your solution file includes both the .NET Framework and .NET Core projects.</span></span> <span data-ttu-id="1e5f9-226">在 .NET Framework 项目中添加和设计窗体和控件，并且根据添加到 .NET Core 项目的文件 glob 模式，任何新的或更改的文件将自动包含在 .NET Core 项目中。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-226">Add and design your forms and controls in the .NET Framework project, and based on the file glob patterns we added to the .NET Core projects, any new or changed files will automatically be included in the .NET Core projects.</span></span>

<span data-ttu-id="1e5f9-227">一旦 Visual Studio 2019 支持 Windows 窗体设计器，就可以将 .NET Core 项目文件的内容复制/粘贴到 .NET Framework 项目文件中。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-227">Once Visual Studio 2019 supports the Windows Forms Designer, you can copy/paste the content of your .NET Core project file into the .NET Framework project file.</span></span> <span data-ttu-id="1e5f9-228">然后删除使用 `<Source>` 和 `<EmbeddedResource>` 项添加的文件 glob 模式。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-228">Then delete the file glob patterns added with the `<Source>` and `<EmbeddedResource>` items.</span></span> <span data-ttu-id="1e5f9-229">修复由应用程序使用的任何项目引用的路径。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-229">Fix the paths to any project reference used by your app.</span></span> <span data-ttu-id="1e5f9-230">这可以有效地将 .NET Framework 项目升级到 .NET Core 项目。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-230">This effectively upgrades the .NET Framework project to a .NET Core project.</span></span>
 
## <a name="next-steps"></a><span data-ttu-id="1e5f9-231">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1e5f9-231">Next steps</span></span>

* <span data-ttu-id="1e5f9-232">详细了解 [Windows 兼容包][compat-pack]。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-232">Read more about the [Windows Compatibility Pack][compat-pack].</span></span>
* <span data-ttu-id="1e5f9-233">观看将 .NET Framework Windows 窗体项目移植到 .NET Core 的[视频](https://www.youtube.com/watch?v=upVQEUc_KwU)。</span><span class="sxs-lookup"><span data-stu-id="1e5f9-233">Watch a [video on porting](https://www.youtube.com/watch?v=upVQEUc_KwU) your .NET Framework Windows Forms project to .NET Core.</span></span>

[compat-pack]: windows-compat-pack.md
