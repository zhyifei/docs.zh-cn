---
title: .NET Core 2.0 的新增功能
description: 了解 .NET Core 的新增功能。
keywords: .NET, .NET Core
author: rpetrusha
ms.author: ronpet
ms.date: 08/13/2017
ms.topic: article
ms.prod: .net-core
ms.workload:
- dotnetcore
ms.openlocfilehash: 749f0502b5c80ed3d6b81d2036e7591e3f1fe08a
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="whats-new-in-net-core"></a><span data-ttu-id="bf393-104">.NET Core 的新增功能</span><span class="sxs-lookup"><span data-stu-id="bf393-104">What's new in .NET Core</span></span>

<span data-ttu-id="bf393-105">.NET Core 2.0 提供以下几个方面的增强功能和新功能：</span><span class="sxs-lookup"><span data-stu-id="bf393-105">.NET Core 2.0 includes enhancements and new features in the following areas:</span></span>

- [<span data-ttu-id="bf393-106">工具</span><span class="sxs-lookup"><span data-stu-id="bf393-106">Tooling</span></span>](#tooling)
- [<span data-ttu-id="bf393-107">语言支持</span><span class="sxs-lookup"><span data-stu-id="bf393-107">Language support</span></span>](#language-support)
- [<span data-ttu-id="bf393-108">平台改进</span><span class="sxs-lookup"><span data-stu-id="bf393-108">Platform improvements</span></span>](#platform-improvements)
- [<span data-ttu-id="bf393-109">API 更改</span><span class="sxs-lookup"><span data-stu-id="bf393-109">API changes</span></span>](#api-changes-and-library-support)
- [<span data-ttu-id="bf393-110">Visual Studio 集成</span><span class="sxs-lookup"><span data-stu-id="bf393-110">Visual Studio integration</span></span>](#visual-studio-integration)
- [<span data-ttu-id="bf393-111">文档改进</span><span class="sxs-lookup"><span data-stu-id="bf393-111">Documentation improvements</span></span>](#documentation-improvements)

## <a name="tooling"></a><span data-ttu-id="bf393-112">工具</span><span class="sxs-lookup"><span data-stu-id="bf393-112">Tooling</span></span>

### <a name="dotnet-restore-runs-implicitly"></a><span data-ttu-id="bf393-113">dotnet restore 隐式运行</span><span class="sxs-lookup"><span data-stu-id="bf393-113">dotnet restore runs implicitly</span></span>

<span data-ttu-id="bf393-114">在旧版 .NET Core 中，在使用 [dotnet new](../tools/dotnet-new.md) 命令新建项目后，以及每当向项目添加新的依赖项时，都必须立即运行 [dotnet restore](../tools/dotnet-restore.md) 命令，以便下载依赖项。</span><span class="sxs-lookup"><span data-stu-id="bf393-114">In previous versions of .NET Core, you had to run the [dotnet restore](../tools/dotnet-restore.md) command to download dependencies immediately after you created a new project with the [dotnet new](../tools/dotnet-new.md) command, as well as whenever you added a new dependency to your project.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="bf393-115">还可以将 `--no-restore` 开关传递到 `new`、`run`、`build`、`publish`、`pack` 和 `test` 命令，从而禁用自动调用 `dotnet restore`。</span><span class="sxs-lookup"><span data-stu-id="bf393-115">You can also disable the automatic invocation of `dotnet restore` by passing the `--no-restore` switch to the `new`, `run`, `build`, `publish`, `pack`, and `test` commands.</span></span> 

### <a name="retargeting-to-net-core-20"></a><span data-ttu-id="bf393-116">重定目标到 .NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="bf393-116">Retargeting to .NET Core 2.0</span></span>

<span data-ttu-id="bf393-117">如果已安装 .NET Core 2.0 SDK，那么定目标到 .NET Core 1.x 的项目可以重定目标到 .NET Core 2.0。</span><span class="sxs-lookup"><span data-stu-id="bf393-117">If the .NET Core 2.0 SDK is installed, projects that target .NET Core 1.x can be retargeted to .NET Core 2.0.</span></span>

<span data-ttu-id="bf393-118">若要重定目标到 .NET Core 2.0，请将 `<TargetFramework>` 元素（或 `<TargetFrameworks>` 元素，如果项目文件中有多个目标的话）值从 1.x 更改为 2.0，从而编辑项目文件：</span><span class="sxs-lookup"><span data-stu-id="bf393-118">To retarget to .NET Core 2.0, edit your project file by changing the value of the `<TargetFramework>` element (or the `<TargetFrameworks>` element if you have more than one target in your project file) from 1.x to 2.0:</span></span>

```xml
<PropertyGroup>
    <TargetFramework>netcoreapp2.0</TargetFramework>
 </PropertyGroup>
```

<span data-ttu-id="bf393-119">还可以用同样的方式，将 .NET Standard 库重定目标到 .NET Standard 2.0：</span><span class="sxs-lookup"><span data-stu-id="bf393-119">You can also retarget .NET Standard libraries to .NET Standard 2.0 the same way:</span></span>

```xml
<PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
 </PropertyGroup>
```

<span data-ttu-id="bf393-120">若要详细了解如何将项目迁移到 .NET Core 2.0，请参阅[从 ASP.NET Core 1.x 迁移到 ASP.NET Core 2.0](/aspnet/core/migration/1x-to-2x/index)。</span><span class="sxs-lookup"><span data-stu-id="bf393-120">For more information about migrating your project to .NET Core 2.0, see [Migrating from ASP.NET Core 1.x to ASP.NET Core 2.0](/aspnet/core/migration/1x-to-2x/index).</span></span>

## <a name="language-support"></a><span data-ttu-id="bf393-121">语言支持</span><span class="sxs-lookup"><span data-stu-id="bf393-121">Language support</span></span>

<span data-ttu-id="bf393-122">除了支持 C# 和 F# 外，.NET Core 2.0 还支持 Visual Basic。</span><span class="sxs-lookup"><span data-stu-id="bf393-122">In addition to supporting C# and F#, .NET Core 2.0 also supports Visual Basic.</span></span>

### <a name="visual-basic"></a><span data-ttu-id="bf393-123">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bf393-123">Visual Basic</span></span>

<span data-ttu-id="bf393-124">在版本 2.0 发布后，.NET Core 现在支持 Visual Basic 2017。</span><span class="sxs-lookup"><span data-stu-id="bf393-124">With version 2.0, .NET Core now supports Visual Basic 2017.</span></span> <span data-ttu-id="bf393-125">可使用 Visual Basic 创建以下类型项目：</span><span class="sxs-lookup"><span data-stu-id="bf393-125">You can use Visual Basic to create the following project types:</span></span>

- <span data-ttu-id="bf393-126">.NET Core 控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="bf393-126">.NET Core console apps</span></span>
- <span data-ttu-id="bf393-127">.NET Core 类库</span><span class="sxs-lookup"><span data-stu-id="bf393-127">.NET Core class libraries</span></span>
- <span data-ttu-id="bf393-128">.NET Standard 类库</span><span class="sxs-lookup"><span data-stu-id="bf393-128">.NET Standard class libraries</span></span>
- <span data-ttu-id="bf393-129">.NET Core 单元测试项目</span><span class="sxs-lookup"><span data-stu-id="bf393-129">.NET Core unit test projects</span></span>
- <span data-ttu-id="bf393-130">.NET Core xUnit 测试项目</span><span class="sxs-lookup"><span data-stu-id="bf393-130">.NET Core xUnit test projects</span></span>

<span data-ttu-id="bf393-131">例如，若要创建 Visual Basic“Hello World”应用程序，请通过命令行按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="bf393-131">For example, to create a Visual Basic "Hello World" application, do the following steps from the command line:</span></span>

1. <span data-ttu-id="bf393-132">打开控制台窗口，创建项目目录，并将它设为当前目录。</span><span class="sxs-lookup"><span data-stu-id="bf393-132">Open a console window, create a directory for your project, and make it the current directory.</span></span>

1. <span data-ttu-id="bf393-133">输入命令 `dotnet new console -lang vb`。</span><span class="sxs-lookup"><span data-stu-id="bf393-133">Enter the command `dotnet new console -lang vb`.</span></span>

   <span data-ttu-id="bf393-134">此命令创建文件扩展名为 `.vbproj` 的项目文件，以及名为 Program.vb 的 Visual Basic 源代码文件。</span><span class="sxs-lookup"><span data-stu-id="bf393-134">The command creates a project file with a `.vbproj` file extension, along with a Visual Basic source code file named *Program.vb*.</span></span> <span data-ttu-id="bf393-135">此文件包含用于将字符串“Hello World!”写入控制台窗口的源代码</span><span class="sxs-lookup"><span data-stu-id="bf393-135">This file contains the source code to write the string "Hello World!"</span></span> <span data-ttu-id="bf393-136">。</span><span class="sxs-lookup"><span data-stu-id="bf393-136">to the console window.</span></span>

1.  <span data-ttu-id="bf393-137">输入命令 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="bf393-137">Enter the command `dotnet run`.</span></span> <span data-ttu-id="bf393-138">[.NET Core CLI 工具](../tools/index.md)自动编译并执行应用程序，在控制台窗口中</span><span class="sxs-lookup"><span data-stu-id="bf393-138">The [.NET Core CLI tools](../tools/index.md) automatically compile and execute the application, which displays the message "Hello World!"</span></span> <span data-ttu-id="bf393-139">显示文本字符串“Hello World!”。</span><span class="sxs-lookup"><span data-stu-id="bf393-139">in the console window.</span></span>

### <a name="support-for-c-71"></a><span data-ttu-id="bf393-140">支持 C# 7.1</span><span class="sxs-lookup"><span data-stu-id="bf393-140">Support for C# 7.1</span></span>

<span data-ttu-id="bf393-141">.NET Core 2.0 支持 C# 7.1，其中新增了大量功能，具体包括：</span><span class="sxs-lookup"><span data-stu-id="bf393-141">.NET Core 2.0 supports C# 7.1, which adds a number of new features, including:</span></span>

- <span data-ttu-id="bf393-142">可以使用 [async](../../csharp/language-reference/keywords/async.md) 关键字标记 `Main` 方法（应用程序入口点）。</span><span class="sxs-lookup"><span data-stu-id="bf393-142">The `Main` method, the application entry point, can be marked with the [async](../../csharp/language-reference/keywords/async.md) keyword.</span></span>
- <span data-ttu-id="bf393-143">推断的元组名称。</span><span class="sxs-lookup"><span data-stu-id="bf393-143">Inferred tuple names.</span></span>
- <span data-ttu-id="bf393-144">默认表达式。</span><span class="sxs-lookup"><span data-stu-id="bf393-144">Default expressions.</span></span>

<!-- For more information see [link to C# what's new](url). -->

## <a name="platform-improvements"></a><span data-ttu-id="bf393-145">平台改进</span><span class="sxs-lookup"><span data-stu-id="bf393-145">Platform improvements</span></span>

<span data-ttu-id="bf393-146">.NET Core 2.0 包括许多功能，可便于用户更轻松地在支持的操作系统上安装并使用 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="bf393-146">.NET Core 2.0 includes a number of features that make it easier to install .NET Core and to use it on supported operating systems.</span></span>

### <a name="net-core-for-linux-is-a-single-implementation"></a><span data-ttu-id="bf393-147">.NET Core for Linux 是一个实现代码</span><span class="sxs-lookup"><span data-stu-id="bf393-147">.NET Core for Linux is a single implementation</span></span>

<span data-ttu-id="bf393-148">.NET Core 2.0 提供一个 Linux 实现代码，适用于多个 Linux 发行版本。</span><span class="sxs-lookup"><span data-stu-id="bf393-148">.NET Core 2.0 offers a single Linux implementation that works on multiple Linux distributions.</span></span> <span data-ttu-id="bf393-149">.NET Core 1.x 要求下载发行版本专属的 Linux 实现代码。</span><span class="sxs-lookup"><span data-stu-id="bf393-149">.NET Core 1.x required that you download a distribution-specific Linux implementation.</span></span>

<span data-ttu-id="bf393-150">还可以开发定目标到 Linux 一个操作系统的应用程序。</span><span class="sxs-lookup"><span data-stu-id="bf393-150">You can also develop apps that target Linux as a single operating system.</span></span> <span data-ttu-id="bf393-151">.NET Core 1.x 要求分别定目标到每个 Linux 发行版本。</span><span class="sxs-lookup"><span data-stu-id="bf393-151">.NET Core 1.x required that you target each Linux distribution separately.</span></span>

### <a name="support-for-the-apple-cryptographic-libraries"></a><span data-ttu-id="bf393-152">支持 Apple 加密库</span><span class="sxs-lookup"><span data-stu-id="bf393-152">Support for the Apple cryptographic libraries</span></span>

<span data-ttu-id="bf393-153">macOS 上的 .NET Core 1.x 要求使用 OpenSSL 工具包的加密库。</span><span class="sxs-lookup"><span data-stu-id="bf393-153">.NET Core 1.x on macOS required the OpenSSL toolkit's cryptographic library.</span></span> <span data-ttu-id="bf393-154">.NET Core 2.0 使用 Apple 加密库，不要求使用 OpenSSL，因此不再需要安装它。</span><span class="sxs-lookup"><span data-stu-id="bf393-154">.NET Core 2.0 uses the Apple cryptographic libraries and doesn't require OpenSSL, so you no longer need to install it.</span></span>

## <a name="api-changes-and-library-support"></a><span data-ttu-id="bf393-155">API 更改和库支持</span><span class="sxs-lookup"><span data-stu-id="bf393-155">API changes and library support</span></span>

### <a name="support-for-net-standard-20"></a><span data-ttu-id="bf393-156">支持 .NET Standard 2.0</span><span class="sxs-lookup"><span data-stu-id="bf393-156">Support for .NET Standard 2.0</span></span>

<span data-ttu-id="bf393-157">.NET Standard 定义了一组版本化 API，这些 API 必须可用于符合相应 Standard 版本要求的 .NET 实现代码。</span><span class="sxs-lookup"><span data-stu-id="bf393-157">The .NET Standard defines a versioned set of APIs that must be available on .NET implementations that comply with that version of the standard.</span></span> <span data-ttu-id="bf393-158">.NET Standard 面向库开发者。</span><span class="sxs-lookup"><span data-stu-id="bf393-158">The .NET Standard is targeted at library developers.</span></span> <span data-ttu-id="bf393-159">旨在保证功能对每个 .NET 实现代码中定目标到 .NET Standard 版本的库可用。</span><span class="sxs-lookup"><span data-stu-id="bf393-159">It aims to guarantee the functionality that is available to a library that targets a version of the .NET Standard on each .NET implementation.</span></span> <span data-ttu-id="bf393-160">.NET Core 1.x 支持 .NET Standard 版本 1.6；.NET Core 2.0 支持最新版 .NET Core 2.0。</span><span class="sxs-lookup"><span data-stu-id="bf393-160">.NET Core 1.x supports the .NET Standard version 1.6; .NET Core 2.0 supports the latest version, .NET Standard 2.0.</span></span> <span data-ttu-id="bf393-161">有关详细信息，请参阅 [.NET Standard](../../standard/net-standard.md)。</span><span class="sxs-lookup"><span data-stu-id="bf393-161">For more information, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="bf393-162">.NET Standard 2.0 比 .NET Standard 1.6 多包含 20,000 多个 API。</span><span class="sxs-lookup"><span data-stu-id="bf393-162">.NET Standard 2.0 includes over 20,000 more APIs than were available in the .NET Standard 1.6.</span></span> <span data-ttu-id="bf393-163">此扩展的外围应用的大部分来自于，将 .NET Framework 和 Xamarin 的通用 API 合并到 .NET Standard。</span><span class="sxs-lookup"><span data-stu-id="bf393-163">Much of this expanded surface area results from incorporating APIs that are common to the .NET Framework and Xamarin into .NET Standard.</span></span>

<span data-ttu-id="bf393-164">.NET Standard 2.0 类库还可以引用 .NET Framework 类库，但前提是它们调用 .NET Standard 2.0 中的 API。</span><span class="sxs-lookup"><span data-stu-id="bf393-164">.NET Standard 2.0 class libraries can also reference .NET Framework class libraries, provided that they call APIs that are present in the .NET Standard 2.0.</span></span> <span data-ttu-id="bf393-165">不需要重新编译 .NET Framework 库。</span><span class="sxs-lookup"><span data-stu-id="bf393-165">No recompilation of the .NET Framework libraries is required.</span></span>

<span data-ttu-id="bf393-166">有关自上一版本 (.NET Standard 1.6) 起添加到 .NET Standard 的 API 列表，请参阅 [.NET Standard 2.0 与 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md)。</span><span class="sxs-lookup"><span data-stu-id="bf393-166">For a list of the APIs that have been added to the .NET Standard since its last version, the .NET Standard 1.6, see [.NET Standard 2.0 vs. 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span></span>

### <a name="expanded-surface-area"></a><span data-ttu-id="bf393-167">扩展的外围应用</span><span class="sxs-lookup"><span data-stu-id="bf393-167">Expanded surface area</span></span>

<span data-ttu-id="bf393-168">与 .NET Core 1.1 相比，.NET Core 2.0 中的可用 API 总数增加了一倍以上。</span><span class="sxs-lookup"><span data-stu-id="bf393-168">The total number of APIs available on .NET Core 2.0 has more than doubled in comparison with .NET Core 1.1.</span></span>

<span data-ttu-id="bf393-169">借助 [Windows 兼容包](../porting/windows-compat-pack.md)，从 .NET Framework 移植也简单了很多。</span><span class="sxs-lookup"><span data-stu-id="bf393-169">And with the [Windows Compatibility Pack](../porting/windows-compat-pack.md) porting from .NET Framework has also become much simpler.</span></span>

### <a name="support-for-net-framework-libraries"></a><span data-ttu-id="bf393-170">支持 .NET Framework 库</span><span class="sxs-lookup"><span data-stu-id="bf393-170">Support for .NET Framework libraries</span></span>

<span data-ttu-id="bf393-171">.NET Core 代码可以引用现有的 .NET Framework 库，包括现有的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="bf393-171">.NET Core code can reference existing .NET Framework libraries, including existing NuGet packages.</span></span> <span data-ttu-id="bf393-172">请注意，库必须使用 .NET Standard 中的 API。</span><span class="sxs-lookup"><span data-stu-id="bf393-172">Note that the libraries must use APIs that are found in .NET Standard.</span></span>

## <a name="visual-studio-integration"></a><span data-ttu-id="bf393-173">Visual Studio 集成</span><span class="sxs-lookup"><span data-stu-id="bf393-173">Visual Studio integration</span></span>

<span data-ttu-id="bf393-174">Visual Studio 2017 版本 15.3 和（在某些情况下）Visual Studio for Mac 提供了大量面向 .NET Core 开发者的重大增强功能。</span><span class="sxs-lookup"><span data-stu-id="bf393-174">Visual Studio 2017 version 15.3 and in some cases Visual Studio for Mac offer a number of significant enhancements for .NET Core developers.</span></span>

### <a name="retargeting-net-core-apps-and-net-standard-libraries"></a><span data-ttu-id="bf393-175">重定目标 .NET Core 应用程序和 .NET Standard 库</span><span class="sxs-lookup"><span data-stu-id="bf393-175">Retargeting .NET Core apps and .NET Standard libraries</span></span>

<span data-ttu-id="bf393-176">如果已安装 .NET Core 2.0 SDK，可以将 .NET Core 1.x 项目重定目标到 .NET Core 2.0，并将 .NET Standard 1.x 库重定目标到 .NET Standard 2.0。</span><span class="sxs-lookup"><span data-stu-id="bf393-176">If the .NET Core 2.0 SDK is installed, you can retarget .NET Core 1.x projects to .NET Core 2.0 and .NET Standard 1.x libraries to .NET Standard 2.0.</span></span>

<span data-ttu-id="bf393-177">若要在 Visual Studio 中重定目标项目，可以打开项目属性对话框的“应用程序”选项卡，再将“目标框架”值更改为“.NET Core 2.0”或“.NET Standard 2.0”。</span><span class="sxs-lookup"><span data-stu-id="bf393-177">To retarget your project in Visual Studio, you open the **Application** tab of the project's properties dialog and change the **Target framework** value to **.NET Core 2.0** or **.NET Standard 2.0**.</span></span> <span data-ttu-id="bf393-178">还可以通过右键单击项目并选择“编辑 \*.csproj 文件”选项进行更改。</span><span class="sxs-lookup"><span data-stu-id="bf393-178">You can also change it by right-clicking on the project and selecting the **Edit \*.csproj file** option.</span></span> <span data-ttu-id="bf393-179">有关详细信息，请参阅本主题前面的[工具](#tooling)部分。</span><span class="sxs-lookup"><span data-stu-id="bf393-179">For more information, see the [Tooling](#tooling) section earlier in this topic.</span></span>

### <a name="live-unit-testing-support-for-net-core"></a><span data-ttu-id="bf393-180">.NET Core 的 Live Unit Testing 支持</span><span class="sxs-lookup"><span data-stu-id="bf393-180">Live Unit Testing support for .NET Core</span></span>

<span data-ttu-id="bf393-181">修改代码时，Live Unit Testing 在后台自动运行任何受影响的单元测试，并在 Visual Studio 环境中实时显示结果和代码覆盖率。</span><span class="sxs-lookup"><span data-stu-id="bf393-181">Whenever you modify your code, Live Unit Testing automatically runs any affected unit tests in the background and displays the results and code coverage live in the Visual Studio environment.</span></span> <span data-ttu-id="bf393-182">.NET Core 2.0 现在支持 Live Unit Testing。</span><span class="sxs-lookup"><span data-stu-id="bf393-182">.NET Core 2.0 now supports Live Unit Testing.</span></span> <span data-ttu-id="bf393-183">以前，Live Unit Testing 仅适用于 .NET Framework 应用程序。</span><span class="sxs-lookup"><span data-stu-id="bf393-183">Previously, Live Unit Testing was available only for .NET Framework applications.</span></span>

<span data-ttu-id="bf393-184">有关详细信息，请参阅[结合使用 Live Unit Testing 和 Visual Studio 2017](/visualstudio/test/live-unit-testing) 和 [Live Unit Testing FAQ](/visualstudio/test/live-unit-testing-faq)。</span><span class="sxs-lookup"><span data-stu-id="bf393-184">For more information, see [Live Unit Testing with Visual Studio 2017](/visualstudio/test/live-unit-testing) and the [Live Unit Testing FAQ](/visualstudio/test/live-unit-testing-faq).</span></span>

### <a name="better-support-for-multiple-target-frameworks"></a><span data-ttu-id="bf393-185">更好地支持多个目标框架</span><span class="sxs-lookup"><span data-stu-id="bf393-185">Better support for multiple target frameworks</span></span>

<span data-ttu-id="bf393-186">若要为多个目标框架生成项目，现在可以从顶级菜单中选择目标平台。</span><span class="sxs-lookup"><span data-stu-id="bf393-186">If you're building a project for multiple target frameworks, you can now select the target platform from the top-level menu.</span></span> <span data-ttu-id="bf393-187">在下图中，名为 SCD1 的项目定目标到 64 位 Mac OS X 10.11 (`osx.10.11-x64`) 和 64 位 Windows 10/Windows Server 2016 (`win10-x64`)。</span><span class="sxs-lookup"><span data-stu-id="bf393-187">In the following figure, a project named SCD1 targets 64-bit Mac OS X 10.11 (`osx.10.11-x64`) and 64-bit Windows 10/Windows Server 2016 (`win10-x64`).</span></span> <span data-ttu-id="bf393-188">可以先选择目标框架，再选择项目按钮（在此示例中是为了要运行调试版本）。</span><span class="sxs-lookup"><span data-stu-id="bf393-188">You can select the target framework before selecting the project button, in this case to run a debug build.</span></span>

![生成项目时选择目标框架](media/multitarget.png)

### <a name="side-by-side-support-for-net-core-sdks"></a><span data-ttu-id="bf393-190">对 .NET Core SDK 的并行支持</span><span class="sxs-lookup"><span data-stu-id="bf393-190">Side-by-side support for .NET Core SDKs</span></span>

<span data-ttu-id="bf393-191">现在可以安装 .NET Core SDK，与 Visual Studio 互不影响。</span><span class="sxs-lookup"><span data-stu-id="bf393-191">You can now install the .NET Core SDK independently of Visual Studio.</span></span> <span data-ttu-id="bf393-192">这样，单版本 Visual Studio 可以生成定目标到不同 .NET Core 版本的项目。</span><span class="sxs-lookup"><span data-stu-id="bf393-192">This makes it possible for a single version of Visual Studio to build projects that target different versions of .NET Core.</span></span> <span data-ttu-id="bf393-193">以前，Visual Studio 和 .NET Core SDK 紧密结合在一起；特定版本的 SDK 附带了特定版本的 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="bf393-193">Previously, Visual Studio and the .NET Core SDK were tightly coupled; a particular version of the SDK accompanied a particular version of Visual Studio.</span></span>

## <a name="documentation-improvements"></a><span data-ttu-id="bf393-194">文档改进</span><span class="sxs-lookup"><span data-stu-id="bf393-194">Documentation improvements</span></span>

### <a name="net-application-architecture"></a><span data-ttu-id="bf393-195">.NET 应用程序体系结构</span><span class="sxs-lookup"><span data-stu-id="bf393-195">.NET Application Architecture</span></span>

<span data-ttu-id="bf393-196">通过 [.NET 应用程序体系结构](https://www.microsoft.com/net/learn/architecture)，可以查看一系列电子图书，其中提供了有关如何使用 .NET 生成内容的指导、最佳做法和示例应用程序：</span><span class="sxs-lookup"><span data-stu-id="bf393-196">[.NET Application Architecture](https://www.microsoft.com/net/learn/architecture) gives you access to a set of e-books that provide guidance, best practices, and sample applications when using .NET to build:</span></span>

- <span data-ttu-id="bf393-197">微服务和 Docker 容器。</span><span class="sxs-lookup"><span data-stu-id="bf393-197">Microservices and Docker containers.</span></span>
- <span data-ttu-id="bf393-198">使用 ASP.NET 的 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="bf393-198">Web applications with ASP.NET.</span></span>
- <span data-ttu-id="bf393-199">使用 Xamarin 的移动应用。</span><span class="sxs-lookup"><span data-stu-id="bf393-199">Mobile applications with Xamarin.</span></span>
- <span data-ttu-id="bf393-200">使用 Azure 部署到云的应用程序。</span><span class="sxs-lookup"><span data-stu-id="bf393-200">Applications that are deployed to the Cloud with Azure.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf393-201">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf393-201">See also</span></span>
 [<span data-ttu-id="bf393-202">ASP.NET Core 2.0 的新增功能</span><span class="sxs-lookup"><span data-stu-id="bf393-202">What's new in ASP.NET Core 2.0</span></span>](/aspnet/core/aspnetcore-2.0)
