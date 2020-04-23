---
title: .NET Core 3.1 的新增功能
description: 了解 .NET Core 3.1 的新增功能。
dev_langs:
- csharp
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: b52615a3fb288a6ca0622deb83f4db3c8e3587fb
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607901"
---
# <a name="whats-new-in-net-core-31"></a><span data-ttu-id="bb37c-103">.NET Core 3.1 的新增功能</span><span class="sxs-lookup"><span data-stu-id="bb37c-103">What's new in .NET Core 3.1</span></span>

<span data-ttu-id="bb37c-104">本文介绍了 .NET Core 3.1 中的新增功能。</span><span class="sxs-lookup"><span data-stu-id="bb37c-104">This article describes what is new in .NET Core 3.1.</span></span> <span data-ttu-id="bb37c-105">此版本包含对 .NET Core 3.0 的细微改进，重点介绍小型但重要的修复。</span><span class="sxs-lookup"><span data-stu-id="bb37c-105">This release contains minor improvements to .NET Core 3.0, focusing on small, but important, fixes.</span></span> <span data-ttu-id="bb37c-106">.NET Core 3.1 中最重要的特性为，它是[长期支持 (LTS)](#long-term-support) 版本。</span><span class="sxs-lookup"><span data-stu-id="bb37c-106">The most important feature about .NET Core 3.1 is that it's a [long-term support (LTS)](#long-term-support) release.</span></span>

<span data-ttu-id="bb37c-107">如果使用的是 Visual Studio 2019，则必须更新到 [Visual Studio 2019 版本 16.4 或更高版本](https://visualstudio.microsoft.com/downloads/)才能使用 .NET Core 3.1 项目。</span><span class="sxs-lookup"><span data-stu-id="bb37c-107">If you're using Visual Studio 2019, you must update to [Visual Studio 2019 version 16.4 or later](https://visualstudio.microsoft.com/downloads/) to work with .NET Core 3.1 projects.</span></span> <span data-ttu-id="bb37c-108">有关 Visual Studio 版本 16.4 中新增功能的详细信息，请参阅 [Visual Studio 2019 版本 16.4 中的新增功能](/visualstudio/releases/2019/release-notes-v16.4#whats-new-in-visual-studio-2019-version-164)。</span><span class="sxs-lookup"><span data-stu-id="bb37c-108">For information on what's new in Visual Studio version 16.4, see [What's New in Visual Studio 2019 version 16.4](/visualstudio/releases/2019/release-notes-v16.4#whats-new-in-visual-studio-2019-version-164).</span></span>

<span data-ttu-id="bb37c-109">Visual Studio for Mac 也支持 .NET Core 3.1，并且 Visual Studio for Mac 8.4 中就包括 .NET Core 3.1。</span><span class="sxs-lookup"><span data-stu-id="bb37c-109">Visual Studio for Mac also supports and includes .NET Core 3.1 in Visual Studio for Mac 8.4.</span></span>

<span data-ttu-id="bb37c-110">有关版本的详细信息，请参阅 [.NET Core 3.1 公告](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/)。</span><span class="sxs-lookup"><span data-stu-id="bb37c-110">For more information about the release, see the [.NET Core 3.1 announcement](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span></span>

- <span data-ttu-id="bb37c-111">在 Windows、macOS 或 Linux 上[下载并开始使用 .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)。</span><span class="sxs-lookup"><span data-stu-id="bb37c-111">[Download and get started with .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1) on Windows, macOS, or Linux.</span></span>

## <a name="long-term-support"></a><span data-ttu-id="bb37c-112">长期支持</span><span class="sxs-lookup"><span data-stu-id="bb37c-112">Long-term support</span></span>

<span data-ttu-id="bb37c-113">.NET Core 3.1 是未来三年包含来自 Microsoft 的支持的 LTS 版本。</span><span class="sxs-lookup"><span data-stu-id="bb37c-113">.NET Core 3.1 is an LTS release with support from Microsoft for the next three years.</span></span> <span data-ttu-id="bb37c-114">强烈建议将应用移到 .NET Core 3.1。</span><span class="sxs-lookup"><span data-stu-id="bb37c-114">It's highly recommended that you move your apps to .NET Core 3.1.</span></span> <span data-ttu-id="bb37c-115">其他主要版本的当前生命周期如下所示：</span><span class="sxs-lookup"><span data-stu-id="bb37c-115">The current lifecycle of other major releases is as follows:</span></span>

| <span data-ttu-id="bb37c-116">Release</span><span class="sxs-lookup"><span data-stu-id="bb37c-116">Release</span></span> | <span data-ttu-id="bb37c-117">说明</span><span class="sxs-lookup"><span data-stu-id="bb37c-117">Note</span></span> |
| ------- | ---- |
| <span data-ttu-id="bb37c-118">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bb37c-118">.NET Core 3.0</span></span> | <span data-ttu-id="bb37c-119">生命周期终结于 2020 年 3 月 3 日。</span><span class="sxs-lookup"><span data-stu-id="bb37c-119">End of life on March 3, 2020.</span></span>     |
| <span data-ttu-id="bb37c-120">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="bb37c-120">.NET Core 2.2</span></span> | <span data-ttu-id="bb37c-121">生命周期终结于 2019 年 12 月 23 日。</span><span class="sxs-lookup"><span data-stu-id="bb37c-121">End of life on December 23, 2019.</span></span> |
| <span data-ttu-id="bb37c-122">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="bb37c-122">.NET Core 2.1</span></span> | <span data-ttu-id="bb37c-123">生命周期终结于 2021 年 8 月 21 日。</span><span class="sxs-lookup"><span data-stu-id="bb37c-123">End of life on August 21, 2021.</span></span>    |

<span data-ttu-id="bb37c-124">有关详细信息，请参阅 [.NET Core 支持策略](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)。</span><span class="sxs-lookup"><span data-stu-id="bb37c-124">For more information, see the [.NET Core support policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

## <a name="macos-apphost-and-notarization"></a><span data-ttu-id="bb37c-125">macOS appHost 和公证</span><span class="sxs-lookup"><span data-stu-id="bb37c-125">macOS appHost and notarization</span></span>

<span data-ttu-id="bb37c-126">仅 macOS </span><span class="sxs-lookup"><span data-stu-id="bb37c-126">*macOS only*</span></span>

<span data-ttu-id="bb37c-127">从已公证的适用于 macOS 的 .NET Core SDK 3.1 开始，默认已禁用 appHost 设置。</span><span class="sxs-lookup"><span data-stu-id="bb37c-127">Starting with the notarized .NET Core SDK 3.1 for macOS, the appHost setting is disabled by default.</span></span> <span data-ttu-id="bb37c-128">有关详细信息，请参阅 [macOS Catalina 公证以及对 .NET Core 下载和项目的影响](../install/macos-notarization-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="bb37c-128">For more information, see [macOS Catalina Notarization and the impact on .NET Core downloads and projects](../install/macos-notarization-issues.md).</span></span>

<span data-ttu-id="bb37c-129">启用 appHost 设置后，.NET Core 在生成或发布时将生成本机 Mach-O 可执行文件。</span><span class="sxs-lookup"><span data-stu-id="bb37c-129">When the appHost setting is enabled, .NET Core generates a native Mach-O executable when you build or publish.</span></span> <span data-ttu-id="bb37c-130">如果使用 `dotnet run` 命令从源代码中运行应用，或通过启动 Mach-O 可执行文件直接运行应用，则应用会在 appHost 的上下文中运行。</span><span class="sxs-lookup"><span data-stu-id="bb37c-130">Your app runs in the context of the appHost when it is run from source code with the `dotnet run` command, or by starting the Mach-O executable directly.</span></span>

<span data-ttu-id="bb37c-131">如果没有 appHost，用户就只能使用 `dotnet <filename.dll>` 命令启动[依赖于运行时](../deploying/index.md#publish-runtime-dependent)的应用。</span><span class="sxs-lookup"><span data-stu-id="bb37c-131">Without the appHost, the only way a user can start a [runtime-dependent](../deploying/index.md#publish-runtime-dependent) app is with the `dotnet <filename.dll>` command.</span></span> <span data-ttu-id="bb37c-132">发布[独立](../deploying/index.md#publish-self-contained)应用时，始终会创建 appHost。</span><span class="sxs-lookup"><span data-stu-id="bb37c-132">An appHost is always created when you publish your app [self-contained](../deploying/index.md#publish-self-contained).</span></span>

<span data-ttu-id="bb37c-133">可以在项目级别配置 appHost，或通过 `-p:UseAppHost` 参数切换特定 `dotnet` 命令的 appHost：</span><span class="sxs-lookup"><span data-stu-id="bb37c-133">You can either configure the appHost at the project level, or toggle the appHost for a specific `dotnet` command with the `-p:UseAppHost` parameter:</span></span>

- <span data-ttu-id="bb37c-134">项目文件</span><span class="sxs-lookup"><span data-stu-id="bb37c-134">Project file</span></span>

  ```xml
  <PropertyGroup>
    <UseAppHost>true</UseAppHost>
  </PropertyGroup>
  ```

- <span data-ttu-id="bb37c-135">命令行参数</span><span class="sxs-lookup"><span data-stu-id="bb37c-135">Command-line parameter</span></span>

  ```dotnetcli
  dotnet run -p:UseAppHost=true
  ```

<span data-ttu-id="bb37c-136">有关 `UseAppHost` 设置的详细信息，请参阅 [Microsoft.NET.Sdk 的 MSBuild 属性](../project-sdk/msbuild-props.md#useapphost)。</span><span class="sxs-lookup"><span data-stu-id="bb37c-136">For more information about the `UseAppHost` setting, see [MSBuild properties for Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost).</span></span>

## <a name="windows-forms"></a><span data-ttu-id="bb37c-137">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="bb37c-137">Windows Forms</span></span>

<span data-ttu-id="bb37c-138">*仅限 Windows*</span><span class="sxs-lookup"><span data-stu-id="bb37c-138">*Windows only*</span></span>

> [!WARNING]
> <span data-ttu-id="bb37c-139">Windows 窗体中发生重大变更。</span><span class="sxs-lookup"><span data-stu-id="bb37c-139">There are breaking changes in Windows Forms.</span></span>

<span data-ttu-id="bb37c-140">旧版控件包含在 Windows 窗体中，这些窗体在一段时间内无法在 Visual Studio 设计器工具箱中使用。</span><span class="sxs-lookup"><span data-stu-id="bb37c-140">Legacy controls were included in Windows Forms that have been unavailable in the Visual Studio Designer Toolbox for some time.</span></span> <span data-ttu-id="bb37c-141">它们已替换为 .NET Framework 2.0 中的新控件。</span><span class="sxs-lookup"><span data-stu-id="bb37c-141">These were replaced with new controls back in .NET Framework 2.0.</span></span> <span data-ttu-id="bb37c-142">它们已从适用于 .NET Core 3.1 的桌面 SDK 中删除。</span><span class="sxs-lookup"><span data-stu-id="bb37c-142">These have been removed from the Desktop SDK for .NET Core 3.1.</span></span>

| <span data-ttu-id="bb37c-143">已删除的控件</span><span class="sxs-lookup"><span data-stu-id="bb37c-143">Removed control</span></span> | <span data-ttu-id="bb37c-144">推荐的替换控件</span><span class="sxs-lookup"><span data-stu-id="bb37c-144">Recommended replacement</span></span> | <span data-ttu-id="bb37c-145">已删除关联的 API</span><span class="sxs-lookup"><span data-stu-id="bb37c-145">Associated APIs removed</span></span> |
| --------------- | ----------------------- | ----------------------- |
| <span data-ttu-id="bb37c-146">DataGrid</span><span class="sxs-lookup"><span data-stu-id="bb37c-146">DataGrid</span></span>        | <xref:System.Windows.Forms.DataGridView>      | <span data-ttu-id="bb37c-147">DataGridCell</span><span class="sxs-lookup"><span data-stu-id="bb37c-147">DataGridCell</span></span><br/><span data-ttu-id="bb37c-148">DataGridRow</span><span class="sxs-lookup"><span data-stu-id="bb37c-148">DataGridRow</span></span><br/><span data-ttu-id="bb37c-149">DataGridTableCollection</span><span class="sxs-lookup"><span data-stu-id="bb37c-149">DataGridTableCollection</span></span><br/><span data-ttu-id="bb37c-150">DataGridColumnCollection</span><span class="sxs-lookup"><span data-stu-id="bb37c-150">DataGridColumnCollection</span></span><br/><span data-ttu-id="bb37c-151">DataGridTableStyle</span><span class="sxs-lookup"><span data-stu-id="bb37c-151">DataGridTableStyle</span></span><br/><span data-ttu-id="bb37c-152">DataGridColumnStyle</span><span class="sxs-lookup"><span data-stu-id="bb37c-152">DataGridColumnStyle</span></span><br/><span data-ttu-id="bb37c-153">DataGridLineStyle</span><span class="sxs-lookup"><span data-stu-id="bb37c-153">DataGridLineStyle</span></span><br/><span data-ttu-id="bb37c-154">DataGridParentRowsLabel</span><span class="sxs-lookup"><span data-stu-id="bb37c-154">DataGridParentRowsLabel</span></span><br/><span data-ttu-id="bb37c-155">DataGridParentRowsLabelStyle</span><span class="sxs-lookup"><span data-stu-id="bb37c-155">DataGridParentRowsLabelStyle</span></span><br/><span data-ttu-id="bb37c-156">DataGridBoolColumn</span><span class="sxs-lookup"><span data-stu-id="bb37c-156">DataGridBoolColumn</span></span><br/><span data-ttu-id="bb37c-157">DataGridTextBox</span><span class="sxs-lookup"><span data-stu-id="bb37c-157">DataGridTextBox</span></span><br/><span data-ttu-id="bb37c-158">GridColumnStylesCollection</span><span class="sxs-lookup"><span data-stu-id="bb37c-158">GridColumnStylesCollection</span></span><br/><span data-ttu-id="bb37c-159">GridTableStylesCollection</span><span class="sxs-lookup"><span data-stu-id="bb37c-159">GridTableStylesCollection</span></span><br/><span data-ttu-id="bb37c-160">HitTestType</span><span class="sxs-lookup"><span data-stu-id="bb37c-160">HitTestType</span></span> |
| <span data-ttu-id="bb37c-161">ToolBar</span><span class="sxs-lookup"><span data-stu-id="bb37c-161">ToolBar</span></span>         | <xref:System.Windows.Forms.ToolStrip>         | <span data-ttu-id="bb37c-162">ToolBarAppearance</span><span class="sxs-lookup"><span data-stu-id="bb37c-162">ToolBarAppearance</span></span> |
| <span data-ttu-id="bb37c-163">ToolBarButton</span><span class="sxs-lookup"><span data-stu-id="bb37c-163">ToolBarButton</span></span>   | <xref:System.Windows.Forms.ToolStripButton>   | <span data-ttu-id="bb37c-164">ToolBarButtonClickEventArgs</span><span class="sxs-lookup"><span data-stu-id="bb37c-164">ToolBarButtonClickEventArgs</span></span><br/><span data-ttu-id="bb37c-165">ToolBarButtonClickEventHandler</span><span class="sxs-lookup"><span data-stu-id="bb37c-165">ToolBarButtonClickEventHandler</span></span><br/><span data-ttu-id="bb37c-166">ToolBarButtonStyle</span><span class="sxs-lookup"><span data-stu-id="bb37c-166">ToolBarButtonStyle</span></span><br/><span data-ttu-id="bb37c-167">ToolBarTextAlign</span><span class="sxs-lookup"><span data-stu-id="bb37c-167">ToolBarTextAlign</span></span> |
| <span data-ttu-id="bb37c-168">ContextMenu</span><span class="sxs-lookup"><span data-stu-id="bb37c-168">ContextMenu</span></span>     | <xref:System.Windows.Forms.ContextMenuStrip>  |  |
| :::no-loc text="Menu"::: | <xref:System.Windows.Forms.ToolStripDropDown><br/><xref:System.Windows.Forms.ToolStripDropDownMenu> | <span data-ttu-id="bb37c-169">MenuItemCollection</span><span class="sxs-lookup"><span data-stu-id="bb37c-169">MenuItemCollection</span></span> |
| <span data-ttu-id="bb37c-170">MainMenu</span><span class="sxs-lookup"><span data-stu-id="bb37c-170">MainMenu</span></span>        | <xref:System.Windows.Forms.MenuStrip>         |  |
| <span data-ttu-id="bb37c-171">MenuItem</span><span class="sxs-lookup"><span data-stu-id="bb37c-171">MenuItem</span></span>        | <xref:System.Windows.Forms.ToolStripMenuItem> |  |

<span data-ttu-id="bb37c-172">我们建议你将应用程序更新到 .NET Core 3.1 并移动到替换控件。</span><span class="sxs-lookup"><span data-stu-id="bb37c-172">We recommend you update your applications to .NET Core 3.1 and move to the replacement controls.</span></span> <span data-ttu-id="bb37c-173">替换控件是一个简单的过程，本质上属于“查找和替换”类型。</span><span class="sxs-lookup"><span data-stu-id="bb37c-173">Replacing the controls is a straightforward process, essentially "find and replace" on the type.</span></span>

## <a name="ccli"></a><span data-ttu-id="bb37c-174">C++/CLI</span><span class="sxs-lookup"><span data-stu-id="bb37c-174">C++/CLI</span></span>

<span data-ttu-id="bb37c-175">*仅限 Windows*</span><span class="sxs-lookup"><span data-stu-id="bb37c-175">*Windows only*</span></span>

<span data-ttu-id="bb37c-176">已添加对创建 C++/CLI（也称为“托管 C++”）项目的支持。</span><span class="sxs-lookup"><span data-stu-id="bb37c-176">Support has been added for creating C++/CLI (also known as "managed C++") projects.</span></span> <span data-ttu-id="bb37c-177">从这些项目生成的二进制文件与 .NET Core 3.0 及更高版本兼容。</span><span class="sxs-lookup"><span data-stu-id="bb37c-177">Binaries produced from these projects are compatible with .NET Core 3.0 and later versions.</span></span>

<span data-ttu-id="bb37c-178">若要添加对 Visual Studio 2019 版本 16.4 中的 C++/CLI 的支持，请安装[“使用 C++ 的桌面开发”工作负荷](/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads)。</span><span class="sxs-lookup"><span data-stu-id="bb37c-178">To add support for C++/CLI in Visual Studio 2019 version 16.4, install the [Desktop development with C++ workload](/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads).</span></span> <span data-ttu-id="bb37c-179">此工作负载将两个模板添加到 Visual Studio：</span><span class="sxs-lookup"><span data-stu-id="bb37c-179">This workload adds two templates to Visual Studio:</span></span>

- <span data-ttu-id="bb37c-180">CLR 类库(.NET Core)</span><span class="sxs-lookup"><span data-stu-id="bb37c-180">CLR Class Library (.NET Core)</span></span>
- <span data-ttu-id="bb37c-181">CLR 空项目(.NET Core)</span><span class="sxs-lookup"><span data-stu-id="bb37c-181">CLR Empty Project (.NET Core)</span></span>

## <a name="next-steps"></a><span data-ttu-id="bb37c-182">后续步骤</span><span class="sxs-lookup"><span data-stu-id="bb37c-182">Next steps</span></span>

- [<span data-ttu-id="bb37c-183">查看 .NET Core 3.0 和 3.1 之间的重大变更。</span><span class="sxs-lookup"><span data-stu-id="bb37c-183">Review the breaking changes between .NET Core 3.0 and 3.1.</span></span>](../compatibility/3.0-3.1.md)
- [<span data-ttu-id="bb37c-184">查看用于 Windows 窗体应用的 .NET Core 3.1 中的中断性变更。</span><span class="sxs-lookup"><span data-stu-id="bb37c-184">Review the breaking changes in .NET Core 3.1 for Windows Forms apps.</span></span>](../compatibility/winforms.md#net-core-31)
