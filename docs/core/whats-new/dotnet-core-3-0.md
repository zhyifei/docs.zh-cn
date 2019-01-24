---
title: .NET Core 3.0 的新增功能
description: 了解 .NET Core 3.0 的新增功能。
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 12/04/2018
ms.openlocfilehash: 26fb7cb25b9bf7f00f87059fbe1848763f7f175d
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2019
ms.locfileid: "54415541"
---
# <a name="whats-new-in-net-core-30-preview-1"></a><span data-ttu-id="0d31f-103">.NET Core 3.0（预览版 1）的新增功能</span><span class="sxs-lookup"><span data-stu-id="0d31f-103">What's new in .NET Core 3.0 (Preview 1)</span></span>

<span data-ttu-id="0d31f-104">本文介绍 .NET Core 3.0（预览版 1）的新增功能。</span><span class="sxs-lookup"><span data-stu-id="0d31f-104">This article describes what is new in .NET Core 3.0 (preview 1).</span></span> <span data-ttu-id="0d31f-105">最大的增强功能之一是对 Windows 桌面应用程序（仅限 Windows）的支持。</span><span class="sxs-lookup"><span data-stu-id="0d31f-105">One of the biggest enhancements is support for Windows desktop applications (Windows only).</span></span> <span data-ttu-id="0d31f-106">通过利用名为“Windows 桌面”的 .NET Core 3.0 组件，可以移植 Windows 窗体 Windows Presentation Foundation (WPF) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="0d31f-106">By utilizing a .NET Core 3.0 component called Windows Desktop, you can port your Windows Forms Windows Presentation Foundation (WPF) applications.</span></span> <span data-ttu-id="0d31f-107">为清楚起见，Windows 桌面组件仅在 Windows 上受支持。</span><span class="sxs-lookup"><span data-stu-id="0d31f-107">To be clear, the Windows Desktop component is only supported on Windows.</span></span> <span data-ttu-id="0d31f-108">有关详细信息，请参阅下面的 [Window 桌面](#windows-desktop)一节。</span><span class="sxs-lookup"><span data-stu-id="0d31f-108">For more information, see the section [Windows desktop](#windows-desktop) below.</span></span>

<span data-ttu-id="0d31f-109">.NET Core 3.0 添加了对 C#8.0 的支持。</span><span class="sxs-lookup"><span data-stu-id="0d31f-109">.NET Core 3.0 adds support for C# 8.0.</span></span>

<span data-ttu-id="0d31f-110">在 Windows、Mac 和 Linux 上立即[下载并开始使用 .NET Core 3 预览版 1](https://aka.ms/netcore3download)。</span><span class="sxs-lookup"><span data-stu-id="0d31f-110">[Download and get started with .NET Core 3 Preview 1](https://aka.ms/netcore3download) right now on Windows, Mac and Linux.</span></span> <span data-ttu-id="0d31f-111">有关版本的完整详细信息，请参阅 [.NET Core 3 预览版 1 发行说明](https://aka.ms/netcore3releasenotes)。</span><span class="sxs-lookup"><span data-stu-id="0d31f-111">You can see complete details of the release in the [.NET Core 3 Preview 1 release notes](https://aka.ms/netcore3releasenotes).</span></span>

<span data-ttu-id="0d31f-112">有关详细信息，请参阅 [.NET Core 3.0 预览版 1 公告](https://blogs.msdn.microsoft.com/dotnet/2018/12/04/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/)。</span><span class="sxs-lookup"><span data-stu-id="0d31f-112">For more information, see the [.NET Core 3.0 Preview 1 announcement](https://blogs.msdn.microsoft.com/dotnet/2018/12/04/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/).</span></span>

## <a name="net-standard-21"></a><span data-ttu-id="0d31f-113">.NET Standard 2.1</span><span class="sxs-lookup"><span data-stu-id="0d31f-113">.NET Standard 2.1</span></span>

<span data-ttu-id="0d31f-114">.NET Core 3.0 实现 .NET Standard 2.1。</span><span class="sxs-lookup"><span data-stu-id="0d31f-114">.NET Core 3.0 implements .NET Standard 2.1.</span></span>

## <a name="default-executables"></a><span data-ttu-id="0d31f-115">默认可执行文件</span><span class="sxs-lookup"><span data-stu-id="0d31f-115">Default executables</span></span>

<span data-ttu-id="0d31f-116">.NET Core 现在将默认生成[依赖于框架的可执行文件](../deploying/index.md#framework-dependent-executables-fde)。</span><span class="sxs-lookup"><span data-stu-id="0d31f-116">.NET Core will now build [framework-dependent executables](../deploying/index.md#framework-dependent-executables-fde) by default.</span></span> <span data-ttu-id="0d31f-117">对于使用全局安装的 .NET Core 版本的应用程序而言，这是一项新功能。</span><span class="sxs-lookup"><span data-stu-id="0d31f-117">This is new for applications that use a globally installed version of .NET Core.</span></span> <span data-ttu-id="0d31f-118">到目前为止，仅[自包含部署](../deploying/index.md#self-contained-deployments-scd)会生成可执行文件。</span><span class="sxs-lookup"><span data-stu-id="0d31f-118">Until now, only [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) would produce an executable.</span></span>

<span data-ttu-id="0d31f-119">在 `dotnet build` 或 `dotnet publish` 期间，将创建一个假设与你使用的 SDK 的环境和平台相匹配的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="0d31f-119">During `dotnet build` or `dotnet publish`, an executable is created provided that matches the environment and platform of the SDK you are using.</span></span> <span data-ttu-id="0d31f-120">和其他本机可执行文件一样，可以使用这些可执行文件执行相同操作，例如：</span><span class="sxs-lookup"><span data-stu-id="0d31f-120">You can expect the same things with these executables as you would other native executables, such as:</span></span>

* <span data-ttu-id="0d31f-121">可以双击可执行文件。</span><span class="sxs-lookup"><span data-stu-id="0d31f-121">You can double-click on the executable.</span></span>
* <span data-ttu-id="0d31f-122">可以直接从命令提示符启用应用程序，如 Windows 上的 `myapp.exe`，以及 Linux 和 macOS 上的 `./myapp`。</span><span class="sxs-lookup"><span data-stu-id="0d31f-122">You can launch the application from a command prompt directly, such as `myapp.exe` on Windows, and `./myapp` on Linux and macOS.</span></span>

## <a name="build-copies-dependencies"></a><span data-ttu-id="0d31f-123">生成副本依赖项</span><span class="sxs-lookup"><span data-stu-id="0d31f-123">Build copies dependencies</span></span>

<span data-ttu-id="0d31f-124">`dotnet build` 现将应用程序的 NuGet 依赖项从 NuGet 缓存复制到生成输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="0d31f-124">`dotnet build` now copies NuGet dependencies for your application from the NuGet cache to the build output folder.</span></span> <span data-ttu-id="0d31f-125">此前，依赖项仅作为 `dotnet publish` 的一部分复制。</span><span class="sxs-lookup"><span data-stu-id="0d31f-125">Previously, dependencies were only copied as part of `dotnet publish`.</span></span> 

<span data-ttu-id="0d31f-126">有些操作，比如链接和 razor 页面发布仍需要发布。</span><span class="sxs-lookup"><span data-stu-id="0d31f-126">There are some operations, like linking and razor page publishing that will still require publishing.</span></span>


## <a name="local-dotnet-tools"></a><span data-ttu-id="0d31f-127">本地 dotnet 工具</span><span class="sxs-lookup"><span data-stu-id="0d31f-127">Local dotnet tools</span></span>

<span data-ttu-id="0d31f-128">虽然 .NET Core 2.1 支持全局工具，.NET Core 3.0 现在使用本地工具。</span><span class="sxs-lookup"><span data-stu-id="0d31f-128">While .NET Core 2.1 supported global tools, .NET Core 3.0 now has local tools.</span></span> <span data-ttu-id="0d31f-129">本地工具类似于全局工具，但与磁盘上的特定位置相关联。</span><span class="sxs-lookup"><span data-stu-id="0d31f-129">Local tools are similar to global tools but are associated with a particular location on disk.</span></span> <span data-ttu-id="0d31f-130">这支持每个项目和每个存储库工具。</span><span class="sxs-lookup"><span data-stu-id="0d31f-130">This enables per-project and per-repository tooling.</span></span> <span data-ttu-id="0d31f-131">本地安装的任何工具都不可在全局范围使用。</span><span class="sxs-lookup"><span data-stu-id="0d31f-131">Any tool installed locally isn't available globally.</span></span>

<span data-ttu-id="0d31f-132">本地工具依赖于当前目录中的清单文件名称 `dotnet-tools.json`。</span><span class="sxs-lookup"><span data-stu-id="0d31f-132">Local tools rely on a manifest file name `dotnet-tools.json` in your current directory.</span></span> <span data-ttu-id="0d31f-133">此清单文件定义即将推出的工具。</span><span class="sxs-lookup"><span data-stu-id="0d31f-133">This manifest file defines the tools to be available.</span></span> <span data-ttu-id="0d31f-134">通过在存储库的根目录中创建此清单文件，可确保克隆代码的任何人都可以恢复和使用所需的工具，以便成功使用代码。</span><span class="sxs-lookup"><span data-stu-id="0d31f-134">By creating this manifest file at the root of your repository, you ensure anyone cloning your code can restore and use the tools that are needed to successfully work with your code.</span></span>

<span data-ttu-id="0d31f-135">当本地工具清单文件可用，请使用以下命令在本地自动下载和安装这些工具：</span><span class="sxs-lookup"><span data-stu-id="0d31f-135">When the local tools manifest file is available, use the following command to automatically download and install those tools locally:</span></span>

```console
dotnet tool restore
```

<span data-ttu-id="0d31f-136">使用以下命令运行本地工具：</span><span class="sxs-lookup"><span data-stu-id="0d31f-136">Run a local tool with the following command:</span></span>

```console
dotnet tool run <tool-command-name>
```

<span data-ttu-id="0d31f-137">调用本地工具时，dotnet 将搜索目录结构清单。</span><span class="sxs-lookup"><span data-stu-id="0d31f-137">When a local tool is called, dotnet searches for a manifest up the directory structure.</span></span> <span data-ttu-id="0d31f-138">找到工具清单文件时，将在其中搜索请求的工具。</span><span class="sxs-lookup"><span data-stu-id="0d31f-138">When a tool manifest file is found, it is searched for the requested tool.</span></span> <span data-ttu-id="0d31f-139">如果找到工具，它包含在 NuGet 全局包位置查找工具所需的信息。</span><span class="sxs-lookup"><span data-stu-id="0d31f-139">If the tool is found, it includes the information needed to find the tool in the NuGet global packages location.</span></span> 

<span data-ttu-id="0d31f-140">如果在清单中找到工具，但没有缓存，用户将收到一个错误。</span><span class="sxs-lookup"><span data-stu-id="0d31f-140">If the tool is found in the manifest, but not the cache, the user receives an error.</span></span> <span data-ttu-id="0d31f-141">将在预览版 1 后改进此消息，以请求用户运行 `dotnet tool restore`。</span><span class="sxs-lookup"><span data-stu-id="0d31f-141">The message will be improved after Preview 1 to request the user run `dotnet tool restore`.</span></span>

<span data-ttu-id="0d31f-142">要向目录添加本地工具，需要首先创建工具清单文件。</span><span class="sxs-lookup"><span data-stu-id="0d31f-142">To add local tools to a directory, you need to first create the tool manifest file.</span></span> <span data-ttu-id="0d31f-143">在预览版 1 之后，我们将提供机制创建工具清单文件，如 dotnet 新模板。</span><span class="sxs-lookup"><span data-stu-id="0d31f-143">After Preview 1, we will offer a mechanism for creating tool manifest files, such as a dotnet new template.</span></span> <span data-ttu-id="0d31f-144">对于预览版 1，必须创建名为 `dotnet-tools.json` 的文件，同时包含以下内容：</span><span class="sxs-lookup"><span data-stu-id="0d31f-144">For Preview 1 you must create the file named `dotnet-tools.json` with the following contents:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {}
}
```

<span data-ttu-id="0d31f-145">一旦创建清单，可以使用以下命令向其添加本地工具：</span><span class="sxs-lookup"><span data-stu-id="0d31f-145">Once the manifest is created, you can add local tools to it using:</span></span>

```console
dotnet tool install <toolPackageId>
```

<span data-ttu-id="0d31f-146">此命令安装最新版本的工具，除非指定其他版本。</span><span class="sxs-lookup"><span data-stu-id="0d31f-146">This command installs the latest version of the tool, unless another version is specified.</span></span>  <span data-ttu-id="0d31f-147">即使已自动选择最新版本，工具版本也会写入工具清单文件，以便恢复或运行正确版本的工具。</span><span class="sxs-lookup"><span data-stu-id="0d31f-147">Even if the latest version was automatically chosen, the version of the tool is written into the tool manifest file to allow the correct version of the tool to be restored or run.</span></span>

<span data-ttu-id="0d31f-148">工具清单文件旨在允许手动编辑，你可能会执行此操作来更新使用存储库所需的版本。</span><span class="sxs-lookup"><span data-stu-id="0d31f-148">The tool manifest file is designed to allow hand editing – which you might do to update the required version for working with the repository.</span></span>

<span data-ttu-id="0d31f-149">下面是 `dotnet-tools.json` 示例文件：</span><span class="sxs-lookup"><span data-stu-id="0d31f-149">Here is an example `dotnet-tools.json` file:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "dotnetsay": {
      "version": "2.1.4",
      "commands": [
        "dotnetsay"
      ]
    },
    "t-rex": {
      "version": "1.0.103",
      "commands": [
        "t-rex"
      ]
    }
  }
}
```

<span data-ttu-id="0d31f-150">要从工具清单文件中删除工具，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0d31f-150">To remove a tool from the tool manifest file, run the following command:</span></span>

```console
dotnet tool uninstall <toolPackageId>
```

<span data-ttu-id="0d31f-151">对于全局工具和本地工具，需要一个兼容的运行时版本。</span><span class="sxs-lookup"><span data-stu-id="0d31f-151">For both global and local tools, a compatible version of the runtime is required.</span></span> <span data-ttu-id="0d31f-152">目前，NuGet.org 上的许多工具都面向 .NET Core Runtime 2.1。</span><span class="sxs-lookup"><span data-stu-id="0d31f-152">Many tools currently on NuGet.org target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="0d31f-153">要在全局范围或本地安装这些工具，仍需要安装 [NET Core 2.1 运行时](https://dotnet.microsoft.com/download/dotnet-core/2.1)。</span><span class="sxs-lookup"><span data-stu-id="0d31f-153">To install those globally or locally, you would still need to install the [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

<span data-ttu-id="0d31f-154">有关详细信息，请参阅[本地工具的早期预览文档](https://github.com/dotnet/cli/issues/10288)。</span><span class="sxs-lookup"><span data-stu-id="0d31f-154">For more information, see [Local Tools Early Preview Documentation](https://github.com/dotnet/cli/issues/10288).</span></span>

## <a name="windows-desktop"></a><span data-ttu-id="0d31f-155">Windows 桌面</span><span class="sxs-lookup"><span data-stu-id="0d31f-155">Windows desktop</span></span>

<span data-ttu-id="0d31f-156">从 .NET Core 3.0 预览版 1 开始，可以使用 WPF 和 Windows 窗体来生成 Windows 桌面应用程序。</span><span class="sxs-lookup"><span data-stu-id="0d31f-156">Starting with .NET Core 3.0 Preview 1, you can build Windows desktop applications using WPF and Windows Forms.</span></span> <span data-ttu-id="0d31f-157">这些框架还支持通过 [XAML 岛](/windows/uwp/xaml-platform/xaml-host-controls)从 Windows UI XAML 库 (WinUI) 使用新式控件和 Fluent 样式。</span><span class="sxs-lookup"><span data-stu-id="0d31f-157">These frameworks also support using modern controls and Fluent styling from the Windows UI XAML Library (WinUI) via [XAML islands](/windows/uwp/xaml-platform/xaml-host-controls).</span></span>

<span data-ttu-id="0d31f-158">Windows 桌面部件是 Windows .NET Core 3.0 SDK 的一部分。</span><span class="sxs-lookup"><span data-stu-id="0d31f-158">The Windows Desktop component is part of the Windows .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="0d31f-159">可以使用以下 `dotnet` 命令创建新的 WPF 或 Windows 窗体应用：</span><span class="sxs-lookup"><span data-stu-id="0d31f-159">You can create a new WPF or Windows Forms app with the following `dotnet` commands:</span></span>

```console
dotnet new wpf
dotnet new winforms
```

<span data-ttu-id="0d31f-160">还可以在 Visual Studio 2019 预览版 1 中打开、启用和调试 .NET Core 3.0 WPF 和 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="0d31f-160">You can also open, launch, and debug .NET Core 3.0 WPF and Windows Forms projects in Visual Studio 2019 Preview 1.</span></span> <span data-ttu-id="0d31f-161">目前可以在 Visual Studio 2017 15.9 中打开这些项目，然而，它并不是受支持的方案（而且需要[启用预览](https://blogs.msdn.microsoft.com/dotnet/2018/11/13/net-core-tooling-update-for-visual-studio-2017-version-15-9/)）。</span><span class="sxs-lookup"><span data-stu-id="0d31f-161">It's currently possible to open these projects in Visual Studio 2017 15.9, however, it isn't a supported scenario (and you need to [enable previews](https://blogs.msdn.microsoft.com/dotnet/2018/11/13/net-core-tooling-update-for-visual-studio-2017-version-15-9/)).</span></span>

<span data-ttu-id="0d31f-162">新项目与现有的 .NET Core 项目相同，其中有一些附加内容。</span><span class="sxs-lookup"><span data-stu-id="0d31f-162">The new projects are the same as existing .NET Core projects, with a couple additions.</span></span> <span data-ttu-id="0d31f-163">下面是基本 .NET Core 控制台项目与基本 Windows 窗体以及 WPF 项目之间的比较。</span><span class="sxs-lookup"><span data-stu-id="0d31f-163">Here is the comparison of the basic .NET Core console project and a basic Windows Forms and WPF project.</span></span>

<span data-ttu-id="0d31f-164">在 .NET Core 控制台项目中，该项目使用 `Microsoft.NET.Sdk` SDK 并通过 `netcoreapp3.0` 目标框架在 .NET Core 3.0 上声明依赖项。</span><span class="sxs-lookup"><span data-stu-id="0d31f-164">In a .NET Core console project, the project uses the `Microsoft.NET.Sdk` SDK and declares a dependency on .NET Core 3.0 via the `netcoreapp3.0` target framework.</span></span> <span data-ttu-id="0d31f-165">要创建 Windows Desktop 应用，请使用 `Microsoft.NET.Sdk.WindowsDesktop` SDK 并选择要使用的 UI 框架：</span><span class="sxs-lookup"><span data-stu-id="0d31f-165">To create a Windows Desktop app, use the `Microsoft.NET.Sdk.WindowsDesktop` SDK and choose which UI framework to use:</span></span>

```diff
-<Project Sdk="Microsoft.NET.Sdk">
+<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
+   <UseWPF>true</UseWPF>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="0d31f-166">若要选择 Windows 窗体而不是 WPF，请设置 `UseWindowsForms` 而不是 `UseWPF`：</span><span class="sxs-lookup"><span data-stu-id="0d31f-166">To choose Windows Forms over WPF, set `UseWindowsForms` instead of `UseWPF`:</span></span>

```diff
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
-   <UseWPF>true</UseWPF>
+   <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="0d31f-167">如果应用同时使用这两个框架，则 `UseWPF` 和 `UseWindowsForms` 可以同时设置为 `true`，例如，当 Windows 窗体对话框托管 WPF 控件。</span><span class="sxs-lookup"><span data-stu-id="0d31f-167">Both `UseWPF` and `UseWindowsForms` can be set to `true` if the app uses both frameworks, for example when a Windows Forms dialog is hosting a WPF control.</span></span>

<span data-ttu-id="0d31f-168">请在 [dotnet/winforms](https://github.com/dotnet/winforms/issues)、[dotnet/wpf](https://github.com/dotnet/wpf/issues) 和 [dotnet/core](https://github.com/dotnet/core/issues) 存储库上共享反馈。</span><span class="sxs-lookup"><span data-stu-id="0d31f-168">Please share your feedback on the [dotnet/winforms](https://github.com/dotnet/winforms/issues),  [dotnet/wpf](https://github.com/dotnet/wpf/issues) and [dotnet/core](https://github.com/dotnet/core/issues) repos.</span></span>

## <a name="fast-built-in-json-support"></a><span data-ttu-id="0d31f-169">快速内置的 JSON 支持</span><span class="sxs-lookup"><span data-stu-id="0d31f-169">Fast built-in JSON support</span></span>

<span data-ttu-id="0d31f-170">`System.Text.Json.Utf8JsonReader` 是面向 UTF-8 编码 JSON 文本的一个高性能、低分配、只进读取器，从 `ReadOnlySpan<byte>` 读取信息。</span><span class="sxs-lookup"><span data-stu-id="0d31f-170">`System.Text.Json.Utf8JsonReader` is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="0d31f-171">`Utf8JsonReader` 是一种基本的低级类型，可用于构建自定义分析器和反序列化程序。</span><span class="sxs-lookup"><span data-stu-id="0d31f-171">The `Utf8JsonReader` is a foundational, low-level type, that can be leveraged to build custom parsers and deserializers.</span></span> <span data-ttu-id="0d31f-172">使用新的 `Utf8JsonReader` 读取 JSON 有效负载要比使用 [Json.NET](https://www.newtonsoft.com/json) 的读取器快 2 倍。</span><span class="sxs-lookup"><span data-stu-id="0d31f-172">Reading through a JSON payload using the new `Utf8JsonReader` is 2x faster than using the reader from [Json.NET](https://www.newtonsoft.com/json).</span></span> <span data-ttu-id="0d31f-173">在需要将 JSON 令牌实现为 (UTF-16) 字符串之前，它不会进行分配。</span><span class="sxs-lookup"><span data-stu-id="0d31f-173">It does not allocate until you need to actualize JSON tokens as (UTF-16) strings.</span></span>

<span data-ttu-id="0d31f-174">此新 API 将包含以下部件：</span><span class="sxs-lookup"><span data-stu-id="0d31f-174">This new API will include the following components:</span></span>

* <span data-ttu-id="0d31f-175">在预览版 1 中：JSON 读取器（顺序访问）</span><span class="sxs-lookup"><span data-stu-id="0d31f-175">In Preview 1: JSON reader (sequential access)</span></span>
* <span data-ttu-id="0d31f-176">接下来推出：JSON 编写器、DOM（随机访问）、poco 序列化程序、poco 反序列化程序</span><span class="sxs-lookup"><span data-stu-id="0d31f-176">Coming next: JSON writer, DOM (random access), poco serializer, poco deserializer</span></span>

<span data-ttu-id="0d31f-177">下面是基本的 `Utf8JsonReader` 读取器循环，可以作为起点：</span><span class="sxs-lookup"><span data-stu-id="0d31f-177">Here is the basic reader loop for the `Utf8JsonReader` that can be used as a starting point:</span></span>

```csharp
using System.Text.Json;

public static void Utf8JsonReaderLoop(ReadOnlySpan<byte> dataUtf8)
{
    var json = new Utf8JsonReader(dataUtf8, isFinalBlock: true, state: default);

    while (json.Read())
    {
        JsonTokenType tokenType = json.TokenType;
        ReadOnlySpan<byte> valueSpan = json.ValueSpan;
        switch (tokenType)
        {
            case JsonTokenType.StartObject:
            case JsonTokenType.EndObject:
                break;
            case JsonTokenType.StartArray:
            case JsonTokenType.EndArray:
                break;
            case JsonTokenType.PropertyName:
                break;
            case JsonTokenType.String:
                string valueString = json.GetStringValue();
                break;
            case JsonTokenType.Number:
                if (!json.TryGetInt32Value(out int valueInteger))
                {
                    throw new FormatException();
                }
                break;
            case JsonTokenType.True:
            case JsonTokenType.False:
                bool valueBool = json.GetBooleanValue();
                break;
            case JsonTokenType.Null:
                break;
            default:
                throw new ArgumentException();
        }
    }

    dataUtf8 = dataUtf8.Slice((int)json.BytesConsumed);
    JsonReaderState state = json.CurrentState;
}
```

<span data-ttu-id="0d31f-178">.NET 生态系统依赖于 [Json.NET](https://www.newtonsoft.com/json) 和其他常用的 JSON 库，它们仍是很好的选择。</span><span class="sxs-lookup"><span data-stu-id="0d31f-178">The .NET ecosystem has relied on [Json.NET](https://www.newtonsoft.com/json) and other popular JSON libraries, which continue to be good choices.</span></span> <span data-ttu-id="0d31f-179">JSON.NET 使用 .NET 字符串作为其基本数据类型，它实际上是 UTF-16。</span><span class="sxs-lookup"><span data-stu-id="0d31f-179">JSON.NET uses .NET strings as its base datatype, which are UTF-16 under the hood.</span></span> 

<span data-ttu-id="0d31f-180">在 .NET Core 2.1 和 3.0 中，我们添加了新的 API，基于使用 `Span<T>` 和 UTF-8 字符串，可以编写需要更少内存的 JSON API (如 `Utf8JsonReader`)，同时更好地满足 Kestrel、ASP.NET Core Web 服务器等高吞吐量应用程序的需求。</span><span class="sxs-lookup"><span data-stu-id="0d31f-180">In .NET Core 2.1 and 3.0, we added new APIs that makes it possible to write JSON APIs (such as `Utf8JsonReader`) that require much less memory, based on using `Span<T>` and UTF-8 strings, and better serve the needs of high-throughput applications like Kestrel, ASP.NET Core web server.</span></span>

## <a name="ranges-and-indices"></a><span data-ttu-id="0d31f-181">范围和索引</span><span class="sxs-lookup"><span data-stu-id="0d31f-181">Ranges and indices</span></span>

<span data-ttu-id="0d31f-182">新 `Index` 类型可用于编制索引。</span><span class="sxs-lookup"><span data-stu-id="0d31f-182">The new `Index` type can be used for indexing.</span></span> <span data-ttu-id="0d31f-183">可以从从开头开始计数的 `int` 中创建一个类型，也可以使用从末尾开始计数的前缀 `^` 运算符 (C#) 创建一个：</span><span class="sxs-lookup"><span data-stu-id="0d31f-183">You can create one from an `int` that counts from the beginning, or with a prefix `^` operator (C#) that counts from the end:</span></span>

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

<span data-ttu-id="0d31f-184">此外，还有 `Range` 类型，它包含两个 `Index` 值，一个用于开头一个用于结尾，可以使用 `x..y` 范围表达式 (C#) 进行编写。</span><span class="sxs-lookup"><span data-stu-id="0d31f-184">There is also a `Range` type, which consists of two `Index` values, one for the start and one for the end, and can be written with a `x..y` range expression (C#).</span></span> <span data-ttu-id="0d31f-185">然后可以使用 `Range` 进行索引以便生成一个切片：</span><span class="sxs-lookup"><span data-stu-id="0d31f-185">You can then index with a `Range` in order to produce a slice:</span></span>

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

> [!NOTE]
> <span data-ttu-id="0d31f-186">仅 [C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) 支持 `Range` 和 `Index` 语法。</span><span class="sxs-lookup"><span data-stu-id="0d31f-186">Only [C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) supports syntax for `Range` and `Index`.</span></span>

## <a name="async-streams"></a><span data-ttu-id="0d31f-187">异步流</span><span class="sxs-lookup"><span data-stu-id="0d31f-187">Async streams</span></span>

<span data-ttu-id="0d31f-188">`IAsyncEnumerable<T>` 类型是 `IEnumerable<T>` 的新异步版本。</span><span class="sxs-lookup"><span data-stu-id="0d31f-188">The `IAsyncEnumerable<T>` type is a new asynchronous version of `IEnumerable<T>`.</span></span> <span data-ttu-id="0d31f-189">该语言允许你在其中执行 `await foreach` 操作来使用这些元素，并对其执行 `yield return` 操作以生成元素。</span><span class="sxs-lookup"><span data-stu-id="0d31f-189">The language lets you `await foreach` over these to consume their elements, and `yield return` to them to produce elements.</span></span>

<span data-ttu-id="0d31f-190">下面的示例演示如何生成和使用异步流。</span><span class="sxs-lookup"><span data-stu-id="0d31f-190">The following example demonstrates both production and consumption of async streams.</span></span> <span data-ttu-id="0d31f-191">`foreach` 语句为异步语句，它本身使用 `yield return` 为调用方生成异步流。</span><span class="sxs-lookup"><span data-stu-id="0d31f-191">The `foreach` statement is async and itself uses `yield return` to produce an async stream for callers.</span></span> <span data-ttu-id="0d31f-192">此模式（使用 `yield return`）是生成异步流的建议模型。</span><span class="sxs-lookup"><span data-stu-id="0d31f-192">This pattern (using `yield return`) is the recommended model for producing async streams.</span></span>

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result; 
    }
}
```

> [!WARNING]
> <span data-ttu-id="0d31f-193">.NET Core 3.0 预览版 1 当前存在有关 `await foreach` 的 bug。</span><span class="sxs-lookup"><span data-stu-id="0d31f-193">.NET Core 3.0 Preview 1 currently has a bug with `await foreach`.</span></span> <span data-ttu-id="0d31f-194">请改用 `GetEnumerator` 和 `MoveNext` 来处理元素。</span><span class="sxs-lookup"><span data-stu-id="0d31f-194">Instead, use `GetEnumerator` and `MoveNext` to process elements.</span></span> <span data-ttu-id="0d31f-195">有关详细信息，请参见 [roslyn/#31268](https://github.com/dotnet/roslyn/issues/31268)。</span><span class="sxs-lookup"><span data-stu-id="0d31f-195">For more information, see [roslyn/#31268](https://github.com/dotnet/roslyn/issues/31268).</span></span>

<span data-ttu-id="0d31f-196">除了能够 `await foreach`，还可以创建异步迭代器，例如，一个返回 `IAsyncEnumerable/IAsyncEnumerator` 的迭代器，可以在其中进行 `await` 和 `yield` 操作。</span><span class="sxs-lookup"><span data-stu-id="0d31f-196">In addition to being able to `await foreach`, you can also create async iterators, for example, an iterator that returns an `IAsyncEnumerable/IAsyncEnumerator` that you can both `await` and `yield` in.</span></span> <span data-ttu-id="0d31f-197">对于需要处理的对象，可以使用各种 BCL 类型（如 `Stream` 和 `Timer`）实现的 `IAsyncDisposable`。</span><span class="sxs-lookup"><span data-stu-id="0d31f-197">For objects that need to be disposed, you can use `IAsyncDisposable`, which various BCL types implement, such as `Stream` and `Timer`.</span></span>

> [!NOTE]
> <span data-ttu-id="0d31f-198">仅 [C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) 支持 `await foreach` 语法。</span><span class="sxs-lookup"><span data-stu-id="0d31f-198">Only [C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) supports `await foreach` syntax.</span></span>

## <a name="type-sequencereader"></a><span data-ttu-id="0d31f-199">类型：SequenceReader</span><span class="sxs-lookup"><span data-stu-id="0d31f-199">Type: SequenceReader</span></span>

<span data-ttu-id="0d31f-200">在 .NET Core 3.0 中，已添加可用作 `ReadOnlySequence<T>` 读取器的 `System.Buffers.SequenceReader`。</span><span class="sxs-lookup"><span data-stu-id="0d31f-200">In .NET Core 3.0, `System.Buffers.SequenceReader` has been added which can be used as a reader for `ReadOnlySequence<T>`.</span></span> <span data-ttu-id="0d31f-201">这样可以对跨多个支持缓冲区的 `System.IO.Pipelines` 数据进行简单、高性能、低分配分析。</span><span class="sxs-lookup"><span data-stu-id="0d31f-201">This allows easy, high performance, low allocation parsing of `System.IO.Pipelines` data that can cross multiple backing buffers.</span></span> 

<span data-ttu-id="0d31f-202">以下示例将输入 `Sequence` 分解为有效的 `CR/LF` 分隔行：</span><span class="sxs-lookup"><span data-stu-id="0d31f-202">The following example breaks an input `Sequence` into valid `CR/LF` delimited lines:</span></span>

```csharp
private static ReadOnlySpan<byte> CRLF => new byte[] { (byte)'\r', (byte)'\n' };

public static void ReadLines(ReadOnlySequence<byte> sequence)
{
    SequenceReader<byte> reader = new SequenceReader<byte>(sequence);

    while (!reader.End)
    {
        if (!reader.TryReadToAny(out ReadOnlySpan<byte> line, CRLF, advancePastDelimiter:false))
        {
            // Couldn't find another delimiter
            // ...
        }

        if (!reader.IsNext(CRLF, advancePast: true))
        {
            // Not a good CR/LF pair
            // ...
        }

        // line is valid, process
        ProcessLine(line);
    }
}
```

## <a name="type-metadataloadcontext"></a><span data-ttu-id="0d31f-203">类型：MetadataLoadContext</span><span class="sxs-lookup"><span data-stu-id="0d31f-203">Type: MetadataLoadContext</span></span>

<span data-ttu-id="0d31f-204">添加了 `MetadataLoadContext` 类型，该类型支持读取程序集元数据，而不会影响调用方的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="0d31f-204">The `MetadataLoadContext` type has been added that enables reading assembly metadata without affecting the caller’s application domain.</span></span> <span data-ttu-id="0d31f-205">程序集作为数据读取，包括为与当前运行时环境不同的体系结构和平台构建的程序集。</span><span class="sxs-lookup"><span data-stu-id="0d31f-205">Assemblies are read as data, including assemblies built for different architectures and platforms than the current runtime environment.</span></span> <span data-ttu-id="0d31f-206">`MetadataLoadContext` 与 <xref:System.Reflection.Assembly.ReflectionOnlyLoad*> 重叠，后者仅在 .NET Framework 中可用。</span><span class="sxs-lookup"><span data-stu-id="0d31f-206">`MetadataLoadContext` overlaps with the <xref:System.Reflection.Assembly.ReflectionOnlyLoad*>, which is only available in the .NET Framework.</span></span>

<span data-ttu-id="0d31f-207">[System.Reflection.MetadataLoadContext 包](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext) 现已推出 `MetdataLoadContext`。</span><span class="sxs-lookup"><span data-stu-id="0d31f-207">`MetdataLoadContext` is available in the [System.Reflection.MetadataLoadContext package](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext).</span></span> <span data-ttu-id="0d31f-208">它是一个 .NET Standard 2.0 包。</span><span class="sxs-lookup"><span data-stu-id="0d31f-208">It is a .NET Standard 2.0 package.</span></span>

<span data-ttu-id="0d31f-209">`MetadataLoadContext` 公开的 API 类似于 <xref:System.Runtime.Loader.AssemblyLoadContext> 类型，但不是基于该类型。</span><span class="sxs-lookup"><span data-stu-id="0d31f-209">The `MetadataLoadContext` exposes APIs similar to the <xref:System.Runtime.Loader.AssemblyLoadContext> type, but is not based on that type.</span></span> <span data-ttu-id="0d31f-210">与 <xref:System.Runtime.Loader.AssemblyLoadContext> 非常相似，`MetadataLoadContext` 支持在一个独立的程序集加载范围内加载程序集。</span><span class="sxs-lookup"><span data-stu-id="0d31f-210">Much like <xref:System.Runtime.Loader.AssemblyLoadContext>, the `MetadataLoadContext` enables loading assemblies within an isolated assembly loading universe.</span></span> <span data-ttu-id="0d31f-211">`MetdataLoadContext` API 返回 <xref:System.Reflection.Assembly> 对象，支持使用熟悉的反射 API。</span><span class="sxs-lookup"><span data-stu-id="0d31f-211">`MetdataLoadContext` APIs return <xref:System.Reflection.Assembly> objects, enabling the use of familiar reflection APIs.</span></span> <span data-ttu-id="0d31f-212">不允许以执行为导向的 API，如 [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127)，并将引发 InvalidOperationException。</span><span class="sxs-lookup"><span data-stu-id="0d31f-212">Execution-oriented APIs, such as [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127), are not allowed and will throw InvalidOperationException.</span></span>

<span data-ttu-id="0d31f-213">下面的示例演示如何在实现给定接口的程序集中找到具体类型：</span><span class="sxs-lookup"><span data-stu-id="0d31f-213">The following sample demonstrates how to find concrete types in an assembly that implements a given interface:</span></span>

```csharp
var paths = new string[] {@"C:\myapp\mscorlib.dll", @"C:\myapp\myapp.dll"};
var resolver = new PathAssemblyResolver(paths);
using (var lc = new MetadataLoadContext(resolver))
{
    Assembly a = lc.LoadFromAssemblyName("myapp");
    Type myInterface = a.GetType("MyApp.IPluginInterface");
    foreach (Type t in a.GetTypes())
    {
        if (t.IsClass && myInterface.IsAssignableFrom(t))
            Console.WriteLine($"Class {t.FullName} implements IPluginInterface");
    }
}
```

<span data-ttu-id="0d31f-214">`MetadataLoadContext` 场景包括设计时功能、生成时工具和运行时启动功能，这些功能需要将一组程序集作为数据进行检查，并在执行检查后释放所有文件锁和内存。</span><span class="sxs-lookup"><span data-stu-id="0d31f-214">Scenarios for `MetadataLoadContext` include design-time features, build-time tooling, and runtime light-up features that need to inspect a set of assemblies as data and have all file locks and memory freed after inspection is performed.</span></span>

<span data-ttu-id="0d31f-215">`MetadataLoadContext` 有一个解析程序类传递给其构造函数。</span><span class="sxs-lookup"><span data-stu-id="0d31f-215">The `MetadataLoadContext` has a resolver class passed to its constructor.</span></span> <span data-ttu-id="0d31f-216">解析程序的工作是在给定 `AssemblyName` 条件下加载 `Assembly`。</span><span class="sxs-lookup"><span data-stu-id="0d31f-216">The resolver's job is to load an `Assembly` given its `AssemblyName`.</span></span> <span data-ttu-id="0d31f-217">解析程序类派生自抽象 `MetadataAssemblyResolver` 类。</span><span class="sxs-lookup"><span data-stu-id="0d31f-217">The resolver class derives from the abstract `MetadataAssemblyResolver` class.</span></span> <span data-ttu-id="0d31f-218">`PathAssemblyResolver` 提供了基于路径场景的解析程序的实现。</span><span class="sxs-lookup"><span data-stu-id="0d31f-218">An implementation of the resolver for path-based scenarios is provided with `PathAssemblyResolver`.</span></span>

<span data-ttu-id="0d31f-219">[MetadataLoadContext 测试](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests)演示了许多用例。</span><span class="sxs-lookup"><span data-stu-id="0d31f-219">The [MetadataLoadContext tests](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests) demonstrate many use cases.</span></span> <span data-ttu-id="0d31f-220">[程序集测试](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs)是一个很好的起点。</span><span class="sxs-lookup"><span data-stu-id="0d31f-220">The [Assembly tests](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs) are a good place to start.</span></span>

## <a name="tls-13--openssl-111-on-linux"></a><span data-ttu-id="0d31f-221">Linux 上的 TLS 1.3 和 OpenSSL 1.1.1</span><span class="sxs-lookup"><span data-stu-id="0d31f-221">TLS 1.3 & OpenSSL 1.1.1 on Linux</span></span>

<span data-ttu-id="0d31f-222">.NET Core 现在可以在给定环境中使用 [OpenSSL 1.1.1 中的 TLS 1.3 支持](https://www.openssl.org/blog/blog/2018/09/11/release111/)。</span><span class="sxs-lookup"><span data-stu-id="0d31f-222">.NET Core will now take advantage of [TLS 1.3 support in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), when it is available in a given environment.</span></span> <span data-ttu-id="0d31f-223">对于 [OpenSSL 团队](https://www.openssl.org/blog/blog/2018/09/11/release111/)来说，TLS 1.3 有许多好处：</span><span class="sxs-lookup"><span data-stu-id="0d31f-223">There are multiple benefits of TLS 1.3, per the [OpenSSL team](https://www.openssl.org/blog/blog/2018/09/11/release111/):</span></span>

* <span data-ttu-id="0d31f-224">由于减少了客户端和服务器之间所需的往返次数，从而提高了连接时间。</span><span class="sxs-lookup"><span data-stu-id="0d31f-224">Improved connection times due to a reduction in the number of round trips required between the client and server.</span></span>

* <span data-ttu-id="0d31f-225">由于消除了各种过时和不安全的加密算法和加密了更多连接握手，从而提高了安全性。</span><span class="sxs-lookup"><span data-stu-id="0d31f-225">Improved security due to the removal of various obsolete and insecure cryptographic algorithms and encryption of more of the connection handshake.</span></span>

<span data-ttu-id="0d31f-226">.NET Core 3.0 预览版 1 能够利用 OpenSSL 1.1.1、OpenSSL 1.1.0 或 OpenSSL 1.0.2（无论在 Linux 系统上找到的最佳版本是什么）。</span><span class="sxs-lookup"><span data-stu-id="0d31f-226">.NET Core 3.0 Preview 1 is capable of utilizing **OpenSSL 1.1.1**, **OpenSSL 1.1.0**, or **OpenSSL 1.0.2** (whatever the best version found is, on a Linux system).</span></span>  <span data-ttu-id="0d31f-227">当 OpenSSL 1.1.1 可用时，SslStream 和 HttpClient 类型将在使用 `SslProtocols.None`（系统默认协议）时使用 TLS 1.3，假定客户端和服务器都支持 TLS 1.3。</span><span class="sxs-lookup"><span data-stu-id="0d31f-227">When **OpenSSL 1.1.1** is available the SslStream and HttpClient types will use **TLS 1.3** when using `SslProtocols.None` (system default protocols), assuming both the client and server support **TLS 1.3**.</span></span>

<span data-ttu-id="0d31f-228">下面的示例演示在 Ubuntu 18.10 上 .NET Core 3.0 预览版 1 如何连接到 <https://www.cloudflare.com>：</span><span class="sxs-lookup"><span data-stu-id="0d31f-228">The following sample demonstrates .NET Core 3.0 Preview 1 on Ubuntu 18.10 connecting to <https://www.cloudflare.com>:</span></span>

```csharp
using System;
using System.Net.Security;
using System.Net.Sockets;
using System.Threading.Tasks;

namespace tlstest
{
    class Program
    {
        static async Task Main()
        {
            using (TcpClient tcpClient = new TcpClient())
            {
                string targetHost = "www.cloudflare.com";

                await tcpClient.ConnectAsync(targetHost, 443);

                using (SslStream sslStream = new SslStream(tcpClient.GetStream()))
                {
                    await sslStream.AuthenticateAsClientAsync(targetHost);
                    await Console.Out.WriteLineAsync($"Connected to {targetHost} with {sslStream.SslProtocol}");
                }
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/tlstest$ dotnet run
Connected to www.cloudflare.com with Tls13
user@comp-ubuntu1810:~/tlstest$ openssl version
OpenSSL 1.1.1  11 Sep 2018
```

>[!IMPORTANT]
><span data-ttu-id="0d31f-229">Windows 和 macOS 尚不支持 TLS 1.3。</span><span class="sxs-lookup"><span data-stu-id="0d31f-229">Windows and macOS do not yet support **TLS 1.3**.</span></span> <span data-ttu-id="0d31f-230">当支持可用时，.NET Core 3.0 将在这些操作系统上支持 TLS 1.3。</span><span class="sxs-lookup"><span data-stu-id="0d31f-230">.NET Core 3.0 will support **TLS 1.3** on these operating systems when support becomes available.</span></span>

## <a name="cryptography"></a><span data-ttu-id="0d31f-231">密码</span><span class="sxs-lookup"><span data-stu-id="0d31f-231">Cryptography</span></span>

<span data-ttu-id="0d31f-232">添加了对 AES-GCM 和 AES-CCM 密码的支持，通过 `System.Security.Cryptography.AesGcm` 和 `System.Security.Cryptography.AesCcm` 实现。</span><span class="sxs-lookup"><span data-stu-id="0d31f-232">Support has been added for **AES-GCM** and **AES-CCM** ciphers, implemented via `System.Security.Cryptography.AesGcm` and `System.Security.Cryptography.AesCcm`.</span></span> <span data-ttu-id="0d31f-233">这些算法都是[使用关联数据的验证加密 (AEAD) 算法](https://en.wikipedia.org/wiki/Authenticated_encryption)，以及第一个添加到 .NET Core 的验证加密 (AE) 算法。</span><span class="sxs-lookup"><span data-stu-id="0d31f-233">These algorithms are both [Authenticated Encryption with Association Data (AEAD) algorithms](https://en.wikipedia.org/wiki/Authenticated_encryption), and the first Authenticated Encryption (AE) algorithms added to .NET Core.</span></span>

<span data-ttu-id="0d31f-234">下面的代码演示了如何使用 AesGcm 密码加密和解密随机数据。</span><span class="sxs-lookup"><span data-stu-id="0d31f-234">The following code demonstrates using **AesGcm** cipher to encrypt and decrypt random data.</span></span>

<span data-ttu-id="0d31f-235">AesCcm 代码几乎完全相同（仅类变量名称不同）。</span><span class="sxs-lookup"><span data-stu-id="0d31f-235">The code for **AesCcm** would look almost identical (only the class variable names would be different).</span></span>

```csharp
// key should be: pre-known, derived, or transported via another channel, such as RSA encryption
byte[] key = new byte[16];
RandomNumberGenerator.Fill(key);

byte[] nonce = new byte[12];
RandomNumberGenerator.Fill(nonce);

// normally this would be your data
byte[] dataToEncrypt = new byte[1234];
byte[] associatedData = new byte[333];
RandomNumberGenerator.Fill(dataToEncrypt);
RandomNumberGenerator.Fill(associatedData);

// these will be filled during the encryption
byte[] tag = new byte[16];
byte[] ciphertext = new byte[dataToEncrypt.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Encrypt(nonce, dataToEncrypt, ciphertext, tag, associatedData);
}

// tag, nonce, ciphertext, associatedData should be sent to the other part

byte[] decryptedData = new byte[ciphertext.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Decrypt(nonce, ciphertext, tag, decryptedData, associatedData);
}

// do something with the data
// this should always print that data is the same
Console.WriteLine($"AES-GCM: Decrypted data is{(dataToEncrypt.SequenceEqual(decryptedData) ? "the same as" : "different than")} original data.");
```

## <a name="cryptographic-key-importexport"></a><span data-ttu-id="0d31f-236">加密密钥导入/导出</span><span class="sxs-lookup"><span data-stu-id="0d31f-236">Cryptographic Key Import/Export</span></span>

<span data-ttu-id="0d31f-237">.NET Core 3.0 预览版 1 支持从标准格式导入和导出非对称公钥和私钥，而不需要使用 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="0d31f-237">.NET Core 3.0 Preview 1 supports the import and export of asymmetric public and private keys from standard formats, without needing to use an X.509 certificate.</span></span>

<span data-ttu-id="0d31f-238">所有密钥类型（RSA、DSA、ECDsa、ECDiffieHellman）都支持公钥的 X.509 SubjectPublicKeyInfo 格式，以及私钥的 PKCS#8 PrivateKeyInfo 和 PKCS#8 EncryptedPrivateKeyInfo 格式。</span><span class="sxs-lookup"><span data-stu-id="0d31f-238">All key types (RSA, DSA, ECDsa, ECDiffieHellman) support the **X.509 SubjectPublicKeyInfo** format for public keys, and the **PKCS#8 PrivateKeyInfo** and **PKCS#8 EncryptedPrivateKeyInfo** formats for private keys.</span></span> <span data-ttu-id="0d31f-239">RSA 此外还支持 PKCS#1 RSAPublicKey 和 PKCS#1 RSAPrivateKey。</span><span class="sxs-lookup"><span data-stu-id="0d31f-239">RSA additionally supports **PKCS#1 RSAPublicKey** and **PKCS#1 RSAPrivateKey**.</span></span> <span data-ttu-id="0d31f-240">所有导出方法都生成 DER 编码的二进制数据，导入方法也是如此。</span><span class="sxs-lookup"><span data-stu-id="0d31f-240">The export methods all produce DER-encoded binary data, and the import methods expect the same.</span></span> <span data-ttu-id="0d31f-241">如果密钥以文本友好的 PEM 格式存储，调用方需要在调用导入方法之前对内容进行 base64 解码。</span><span class="sxs-lookup"><span data-stu-id="0d31f-241">If a key is stored in the text-friendly PEM format, the caller will need to base64-decode the content before calling an import method.</span></span>

```csharp
using System;
using System.IO;
using System.Security.Cryptography;

namespace rsakeyprint
{
    class Program
    {
        static void Main(string[] args)
        {
            using (RSA rsa = RSA.Create())
            {
                byte[] keyBytes = File.ReadAllBytes(args[0]);
                rsa.ImportRSAPrivateKey(keyBytes, out int bytesRead);
 
                Console.WriteLine($"Read {bytesRead} bytes, {keyBytes.Length-bytesRead} extra byte(s) in file.");
                RSAParameters rsaParameters = rsa.ExportParameters(true);
                Console.WriteLine(BitConverter.ToString(rsaParameters.D));
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/rsakeyprint$ echo Making a small key to save on screen space.
Making a small key to save on screen space.
user@comp-ubuntu1810:~/rsakeyprint$ openssl genrsa 768 | openssl rsa -outform der -out rsa.key
Generating RSA private key, 768 bit long modulus (2 primes)
..+++++++
........+++++++
e is 65537 (0x010001)
writing RSA key
user@comp-ubuntu1810:~/rsakeyprint$ dotnet run rsa.key
Read 461 bytes, 0 extra byte(s) in file.
0F-D0-82-34-F8-13-38-4A-7F-C7-52-4A-F6-93-F8-FB-6D-98-7A-6A-04-3B-BC-35-8C-7D-AC-A5-A3-6E-AD-C1-66-30-81-2C-2A-DE-DA-60-03-6A-2C-D9-76-15-7F-61-97-57-
79-E1-6E-45-62-C3-83-04-97-CB-32-EF-C5-17-5F-99-60-92-AE-B6-34-6F-30-06-03-AC-BF-15-24-43-84-EB-83-60-EF-4D-3B-BD-D9-5D-56-26-F0-51-CE-F1
user@comp-ubuntu1810:~/rsakeyprint$ openssl rsa -in rsa.key -inform der -text -noout | grep -A7 private
privateExponent:
    0f:d0:82:34:f8:13:38:4a:7f:c7:52:4a:f6:93:f8:
    fb:6d:98:7a:6a:04:3b:bc:35:8c:7d:ac:a5:a3:6e:
    ad:c1:66:30:81:2c:2a:de:da:60:03:6a:2c:d9:76:
    15:7f:61:97:57:79:e1:6e:45:62:c3:83:04:97:cb:
    32:ef:c5:17:5f:99:60:92:ae:b6:34:6f:30:06:03:
    ac:bf:15:24:43:84:eb:83:60:ef:4d:3b:bd:d9:5d:
    56:26:f0:51:ce:f1
```

<span data-ttu-id="0d31f-242">可以使用 `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo` 类检查 PKCS#8 文件。</span><span class="sxs-lookup"><span data-stu-id="0d31f-242">PKCS#8 files can be inspected with the `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo` class.</span></span>

<span data-ttu-id="0d31f-243">可以分别使用 `System.Security.Cryptography.Pkcs.Pkcs12Info` 和 `System.Security.Cryptography.Pkcs.Pkcs12Builder` 检查和操作 PFX/PKCS#12 文件。</span><span class="sxs-lookup"><span data-stu-id="0d31f-243">PFX/PKCS#12 files can be inspected and manipulated with `System.Security.Cryptography.Pkcs.Pkcs12Info` and `System.Security.Cryptography.Pkcs.Pkcs12Builder`, respectively.</span></span>

## <a name="serialport-for-linux"></a><span data-ttu-id="0d31f-244">适用于 Linux 的 SerialPort</span><span class="sxs-lookup"><span data-stu-id="0d31f-244">SerialPort for Linux</span></span>

<span data-ttu-id="0d31f-245">.NET Core 3.0 现在在 Linux 上支持 <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="0d31f-245">.NET Core 3.0 now supports <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> on Linux.</span></span>

<span data-ttu-id="0d31f-246">以前，.NET Core 只支持在 Windows 上使用 `SerialPort` 类型。</span><span class="sxs-lookup"><span data-stu-id="0d31f-246">Previously, .NET Core only supported using the `SerialPort` type on Windows.</span></span>

## <a name="more-bcl-improvements"></a><span data-ttu-id="0d31f-247">更多的 BCL 改进</span><span class="sxs-lookup"><span data-stu-id="0d31f-247">More BCL Improvements</span></span>

<span data-ttu-id="0d31f-248">.NET Core 2.1 中引入的 `Span<T>`、`Memory<T>` 和相关类型已在 .NET Core 3.0 中优化。</span><span class="sxs-lookup"><span data-stu-id="0d31f-248">The `Span<T>`, `Memory<T>`, and related types that were introduced in .NET Core 2.1, have been optimized in .NET Core 3.0.</span></span> <span data-ttu-id="0d31f-249">常见操作（例如跨越构造、切片、分析和格式化）现在可以更好地执行。</span><span class="sxs-lookup"><span data-stu-id="0d31f-249">Common operations such as span construction, slicing, parsing, and formatting now perform better.</span></span> 

<span data-ttu-id="0d31f-250">此外，像 `String` 这样的类型已经看到了一些潜在的改进，使它们在与 `Dictionary<TKey, TValue>` 和其他集合一起用作键时更有效。</span><span class="sxs-lookup"><span data-stu-id="0d31f-250">Additionally, types like `String` have seen under-the-cover improvements to make them more efficient when used as keys with `Dictionary<TKey, TValue>` and other collections.</span></span> <span data-ttu-id="0d31f-251">不需要更改代码就可以从这些改进中获益。</span><span class="sxs-lookup"><span data-stu-id="0d31f-251">No code changes are required to benefit from these improvements.</span></span>

<span data-ttu-id="0d31f-252">以下改进也是 .NET Core 3 预览版 1 中的新增功能：</span><span class="sxs-lookup"><span data-stu-id="0d31f-252">The following improvements are also new in .NET Core 3 Preview 1:</span></span>

* <span data-ttu-id="0d31f-253">内置于 HttpClient 的 Brotli 支持</span><span class="sxs-lookup"><span data-stu-id="0d31f-253">Brotli support built in to HttpClient</span></span>
* <span data-ttu-id="0d31f-254">ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)</span><span class="sxs-lookup"><span data-stu-id="0d31f-254">ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)</span></span>
* <span data-ttu-id="0d31f-255">Unsafe.Unbox</span><span class="sxs-lookup"><span data-stu-id="0d31f-255">Unsafe.Unbox</span></span>
* <span data-ttu-id="0d31f-256">CancellationToken.Unregister</span><span class="sxs-lookup"><span data-stu-id="0d31f-256">CancellationToken.Unregister</span></span>
* <span data-ttu-id="0d31f-257">复杂算术运算符</span><span class="sxs-lookup"><span data-stu-id="0d31f-257">Complex arithmetic operators</span></span>
* <span data-ttu-id="0d31f-258">TCP 套接字 API 保持活动状态</span><span class="sxs-lookup"><span data-stu-id="0d31f-258">Socket APIs for TCP keep alive</span></span>
* <span data-ttu-id="0d31f-259">StringBuilder.GetChunks</span><span class="sxs-lookup"><span data-stu-id="0d31f-259">StringBuilder.GetChunks</span></span>
* <span data-ttu-id="0d31f-260">IPEndPoint 分析</span><span class="sxs-lookup"><span data-stu-id="0d31f-260">IPEndPoint parsing</span></span>
* <span data-ttu-id="0d31f-261">RandomNumberGenerator.GetInt32</span><span class="sxs-lookup"><span data-stu-id="0d31f-261">RandomNumberGenerator.GetInt32</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="0d31f-262">分层编译</span><span class="sxs-lookup"><span data-stu-id="0d31f-262">Tiered compilation</span></span>

<span data-ttu-id="0d31f-263">仅在 .NET Core 3.0 中默认启用[分层编译](https://blogs.msdn.microsoft.com/dotnet/2018/08/02/tiered-compilation-preview-in-net-core-2-1/)。</span><span class="sxs-lookup"><span data-stu-id="0d31f-263">[Tiered compilation](https://blogs.msdn.microsoft.com/dotnet/2018/08/02/tiered-compilation-preview-in-net-core-2-1/) is on by default with .NET Core 3.0.</span></span> <span data-ttu-id="0d31f-264">它是一项功能，使运行时能够更适应地使用实时 (JIT) 编译器，从而在启动时获得更好的性能，并最大限度地提高吞吐量。</span><span class="sxs-lookup"><span data-stu-id="0d31f-264">It is a feature that enables the runtime to more adaptively use the Just-In-Time (JIT) compiler to get better performance, both at startup and to maximize throughput.</span></span>

<span data-ttu-id="0d31f-265">此功能已作为一项可选功能添加到 [.NET Core 2.1](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/)，然后在 [.NET Core 2.2 预览版 2](https://blogs.msdn.microsoft.com/dotnet/2018/09/12/announcing-net-core-2-2-preview-2/) 中默认启用。</span><span class="sxs-lookup"><span data-stu-id="0d31f-265">This feature was added as an opt-in feature in [.NET Core 2.1](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) and then was enabled by default in [.NET Core 2.2 Preview 2](https://blogs.msdn.microsoft.com/dotnet/2018/09/12/announcing-net-core-2-2-preview-2/).</span></span> <span data-ttu-id="0d31f-266">随后，它在 .NET Core 2.2 版本中还原回可选功能。</span><span class="sxs-lookup"><span data-stu-id="0d31f-266">Subsequently, it has been reverted back to opt in with the .NET Core 2.2 release.</span></span>

## <a name="arm64-linux-support"></a><span data-ttu-id="0d31f-267">ARM64 Linux 支持</span><span class="sxs-lookup"><span data-stu-id="0d31f-267">ARM64 Linux support</span></span>

<span data-ttu-id="0d31f-268">在此版本中，我们向 Linux 添加了对 ARM64 的支持。</span><span class="sxs-lookup"><span data-stu-id="0d31f-268">We are adding support for ARM64 for Linux this release.</span></span> <span data-ttu-id="0d31f-269">有关上下文，我们在使用 .NET Core 2.1 的 Linux 和使用 .NET Core 2.2 的 Windows 中添加了对 ARM32 的支持。</span><span class="sxs-lookup"><span data-stu-id="0d31f-269">For context, we added support for ARM32 for Linux with .NET Core 2.1 and Windows with .NET Core 2.2.</span></span> <span data-ttu-id="0d31f-270">ARM64 的主要用例是当前的 IoT 场景。</span><span class="sxs-lookup"><span data-stu-id="0d31f-270">The primary use case for ARM64 is currently with IoT scenarios.</span></span>

<span data-ttu-id="0d31f-271">Alpine、Debian 和 Ubuntu [Docker 映像均适用于 .NET Core for ARM64](https://hub.docker.com/r/microsoft/dotnet/)。</span><span class="sxs-lookup"><span data-stu-id="0d31f-271">Alpine, Debian and Ubuntu [Docker images are available for .NET Core for ARM64](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

<span data-ttu-id="0d31f-272">有关详细信息，请查看 [.NET Core ARM64 状态](https://github.com/dotnet/announcements/issues/82)。</span><span class="sxs-lookup"><span data-stu-id="0d31f-272">Please check [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82) for more information.</span></span>

>[!NOTE]
> <span data-ttu-id="0d31f-273">**ARM64** 尚未提供 Windows 支持。</span><span class="sxs-lookup"><span data-stu-id="0d31f-273">**ARM64** Windows support isn't yet available.</span></span>
