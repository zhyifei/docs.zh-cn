---
title: .NET Core 3.1 的新增功能
description: 了解 .NET Core 3.1 的新增功能。
dev_langs:
- csharp
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: eba3d21cfc787c5d388de31f988b835522118151
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2020
ms.locfileid: "75936929"
---
# <a name="whats-new-in-net-core-31"></a><span data-ttu-id="a9a50-103">.NET Core 3.1 的新增功能</span><span class="sxs-lookup"><span data-stu-id="a9a50-103">What's new in .NET Core 3.1</span></span>

<span data-ttu-id="a9a50-104">本文介绍了 .NET Core 3.1 中的新增功能。</span><span class="sxs-lookup"><span data-stu-id="a9a50-104">This article describes what is new in .NET Core 3.1.</span></span> <span data-ttu-id="a9a50-105">此版本包含对 .NET Core 3.0 的细微改进，重点介绍小型但重要的修复。</span><span class="sxs-lookup"><span data-stu-id="a9a50-105">This release contains minor improvements to .NET Core 3.0, focusing on small, but important, fixes.</span></span> <span data-ttu-id="a9a50-106">.NET Core 3.1 中最重要的特性为，它是[长期支持 (LTS)](#long-term-support) 版本。</span><span class="sxs-lookup"><span data-stu-id="a9a50-106">The most important feature about .NET Core 3.1 is that it's a [long-term support (LTS)](#long-term-support) release.</span></span>

<span data-ttu-id="a9a50-107">如果使用的是 Visual Studio 2019，则必须更新到 [Visual Studio 2019 版本 16.4](https://visualstudio.microsoft.com/downloads/) 才能使用 .NET Core 3.1 项目。</span><span class="sxs-lookup"><span data-stu-id="a9a50-107">If you're using Visual Studio 2019, you must update to [Visual Studio 2019 version 16.4](https://visualstudio.microsoft.com/downloads/) to work with .NET Core 3.1 projects.</span></span> <span data-ttu-id="a9a50-108">有关 Visual Studio 中新增功能的详细信息，请参阅 [Visual Studio 博客](https://devblogs.microsoft.com/visualstudio/tis-the-season-visual-studio-2019/)。</span><span class="sxs-lookup"><span data-stu-id="a9a50-108">For more information on what is new in Visual Studio, see the [Visual Studio Blog](https://devblogs.microsoft.com/visualstudio/tis-the-season-visual-studio-2019/).</span></span>

<span data-ttu-id="a9a50-109">Visual Studio for Mac 还支持并包括 Visual Studio for Mac 8.4 预览通道中的 .NET Core 3.1。</span><span class="sxs-lookup"><span data-stu-id="a9a50-109">Visual Studio for Mac also supports and includes .NET Core 3.1, in the Visual Studio for Mac 8.4 Preview channel.</span></span> <span data-ttu-id="a9a50-110">需要选择加入该预览通道才能使用 .NET Core 3.1。</span><span class="sxs-lookup"><span data-stu-id="a9a50-110">You'll need to opt into the Preview channel to use .NET Core 3.1.</span></span>

<span data-ttu-id="a9a50-111">有关版本的详细信息，请参阅 [.NET Core 3.1 公告](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/)。</span><span class="sxs-lookup"><span data-stu-id="a9a50-111">For more information about the release, see the [.NET Core 3.1 announcement](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span></span>

- <span data-ttu-id="a9a50-112">在 Windows、macOS 或 Linux 上[下载并开始使用 .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)。</span><span class="sxs-lookup"><span data-stu-id="a9a50-112">[Download and get started with .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1) on Windows, macOS, or Linux.</span></span>

## <a name="long-term-support"></a><span data-ttu-id="a9a50-113">长期支持</span><span class="sxs-lookup"><span data-stu-id="a9a50-113">Long-term support</span></span>

<span data-ttu-id="a9a50-114">.NET Core 3.1 是未来三年包含来自 Microsoft 的支持的 LTS 版本。</span><span class="sxs-lookup"><span data-stu-id="a9a50-114">.NET Core 3.1 is an LTS release with support from Microsoft for the next three years.</span></span> <span data-ttu-id="a9a50-115">强烈建议将应用移到 .NET Core 3.1。</span><span class="sxs-lookup"><span data-stu-id="a9a50-115">It's highly recommended that you move your apps to .NET Core 3.1.</span></span> <span data-ttu-id="a9a50-116">其他主要版本的当前生命周期如下所示：</span><span class="sxs-lookup"><span data-stu-id="a9a50-116">The current lifecycle of other major releases is as follows:</span></span>

| <span data-ttu-id="a9a50-117">Release</span><span class="sxs-lookup"><span data-stu-id="a9a50-117">Release</span></span> | <span data-ttu-id="a9a50-118">说明</span><span class="sxs-lookup"><span data-stu-id="a9a50-118">Note</span></span> |
| ------- | ---- |
| <span data-ttu-id="a9a50-119">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="a9a50-119">.NET Core 3.0</span></span> | <span data-ttu-id="a9a50-120">生命周期终结于 2020 年 3 月 3 日。</span><span class="sxs-lookup"><span data-stu-id="a9a50-120">End of life on March 3, 2020.</span></span>     |
| <span data-ttu-id="a9a50-121">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="a9a50-121">.NET Core 2.2</span></span> | <span data-ttu-id="a9a50-122">生命周期终结于 2019 年 12 月 23 日。</span><span class="sxs-lookup"><span data-stu-id="a9a50-122">End of life on December 23, 2019.</span></span> |
| <span data-ttu-id="a9a50-123">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a9a50-123">.NET Core 2.1</span></span> | <span data-ttu-id="a9a50-124">生命周期终结于 2021 年 8 月 21 日。</span><span class="sxs-lookup"><span data-stu-id="a9a50-124">End of life on August 21, 2021.</span></span>    |

<span data-ttu-id="a9a50-125">有关详细信息，请参阅 [.NET Core 支持策略](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)。</span><span class="sxs-lookup"><span data-stu-id="a9a50-125">For more information, see the [.NET Core support policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

## <a name="windows-forms"></a><span data-ttu-id="a9a50-126">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="a9a50-126">Windows Forms</span></span>

<span data-ttu-id="a9a50-127">*仅限 Windows*</span><span class="sxs-lookup"><span data-stu-id="a9a50-127">*Windows only*</span></span>

> [!WARNING]
> <span data-ttu-id="a9a50-128">Windows 窗体中发生重大变更。</span><span class="sxs-lookup"><span data-stu-id="a9a50-128">There are breaking changes in Windows Forms.</span></span>

<span data-ttu-id="a9a50-129">旧版控件包含在 Windows 窗体中，这些窗体在一段时间内无法在 Visual Studio 设计器工具箱中使用。</span><span class="sxs-lookup"><span data-stu-id="a9a50-129">Legacy controls were included in Windows Forms that have been unavailable in the Visual Studio Designer Toolbox for some time.</span></span> <span data-ttu-id="a9a50-130">它们已替换为 .NET Framework 2.0 中的新控件。</span><span class="sxs-lookup"><span data-stu-id="a9a50-130">These were replaced with new controls back in .NET Framework 2.0.</span></span> <span data-ttu-id="a9a50-131">它们已从适用于 .NET Core 3.1 的桌面 SDK 中删除。</span><span class="sxs-lookup"><span data-stu-id="a9a50-131">These have been removed from the Desktop SDK for .NET Core 3.1.</span></span>

| <span data-ttu-id="a9a50-132">已删除的控件</span><span class="sxs-lookup"><span data-stu-id="a9a50-132">Removed control</span></span> | <span data-ttu-id="a9a50-133">推荐的替换控件</span><span class="sxs-lookup"><span data-stu-id="a9a50-133">Recommended replacement</span></span> | <span data-ttu-id="a9a50-134">已删除关联的 API</span><span class="sxs-lookup"><span data-stu-id="a9a50-134">Associated APIs removed</span></span> |
| --------------- | ----------------------- | ----------------------- |
| <span data-ttu-id="a9a50-135">DataGrid</span><span class="sxs-lookup"><span data-stu-id="a9a50-135">DataGrid</span></span>        | <xref:System.Windows.Forms.DataGridView>      | <span data-ttu-id="a9a50-136">DataGridCell</span><span class="sxs-lookup"><span data-stu-id="a9a50-136">DataGridCell</span></span><br/><span data-ttu-id="a9a50-137">DataGridRow</span><span class="sxs-lookup"><span data-stu-id="a9a50-137">DataGridRow</span></span><br/><span data-ttu-id="a9a50-138">DataGridTableCollection</span><span class="sxs-lookup"><span data-stu-id="a9a50-138">DataGridTableCollection</span></span><br/><span data-ttu-id="a9a50-139">DataGridColumnCollection</span><span class="sxs-lookup"><span data-stu-id="a9a50-139">DataGridColumnCollection</span></span><br/><span data-ttu-id="a9a50-140">DataGridTableStyle</span><span class="sxs-lookup"><span data-stu-id="a9a50-140">DataGridTableStyle</span></span><br/><span data-ttu-id="a9a50-141">DataGridColumnStyle</span><span class="sxs-lookup"><span data-stu-id="a9a50-141">DataGridColumnStyle</span></span><br/><span data-ttu-id="a9a50-142">DataGridLineStyle</span><span class="sxs-lookup"><span data-stu-id="a9a50-142">DataGridLineStyle</span></span><br/><span data-ttu-id="a9a50-143">DataGridParentRowsLabel</span><span class="sxs-lookup"><span data-stu-id="a9a50-143">DataGridParentRowsLabel</span></span><br/><span data-ttu-id="a9a50-144">DataGridParentRowsLabelStyle</span><span class="sxs-lookup"><span data-stu-id="a9a50-144">DataGridParentRowsLabelStyle</span></span><br/><span data-ttu-id="a9a50-145">DataGridBoolColumn</span><span class="sxs-lookup"><span data-stu-id="a9a50-145">DataGridBoolColumn</span></span><br/><span data-ttu-id="a9a50-146">DataGridTextBox</span><span class="sxs-lookup"><span data-stu-id="a9a50-146">DataGridTextBox</span></span><br/><span data-ttu-id="a9a50-147">GridColumnStylesCollection</span><span class="sxs-lookup"><span data-stu-id="a9a50-147">GridColumnStylesCollection</span></span><br/><span data-ttu-id="a9a50-148">GridTableStylesCollection</span><span class="sxs-lookup"><span data-stu-id="a9a50-148">GridTableStylesCollection</span></span><br/><span data-ttu-id="a9a50-149">HitTestType</span><span class="sxs-lookup"><span data-stu-id="a9a50-149">HitTestType</span></span> |
| <span data-ttu-id="a9a50-150">ToolBar</span><span class="sxs-lookup"><span data-stu-id="a9a50-150">ToolBar</span></span>         | <xref:System.Windows.Forms.ToolStrip>         | <span data-ttu-id="a9a50-151">ToolBarAppearance</span><span class="sxs-lookup"><span data-stu-id="a9a50-151">ToolBarAppearance</span></span> |
| <span data-ttu-id="a9a50-152">ToolBarButton</span><span class="sxs-lookup"><span data-stu-id="a9a50-152">ToolBarButton</span></span>   | <xref:System.Windows.Forms.ToolStripButton>   | <span data-ttu-id="a9a50-153">ToolBarButtonClickEventArgs</span><span class="sxs-lookup"><span data-stu-id="a9a50-153">ToolBarButtonClickEventArgs</span></span><br/><span data-ttu-id="a9a50-154">ToolBarButtonClickEventHandler</span><span class="sxs-lookup"><span data-stu-id="a9a50-154">ToolBarButtonClickEventHandler</span></span><br/><span data-ttu-id="a9a50-155">ToolBarButtonStyle</span><span class="sxs-lookup"><span data-stu-id="a9a50-155">ToolBarButtonStyle</span></span><br/><span data-ttu-id="a9a50-156">ToolBarTextAlign</span><span class="sxs-lookup"><span data-stu-id="a9a50-156">ToolBarTextAlign</span></span> |
| <span data-ttu-id="a9a50-157">ContextMenu</span><span class="sxs-lookup"><span data-stu-id="a9a50-157">ContextMenu</span></span>     | <xref:System.Windows.Forms.ContextMenuStrip>  |  |
| :::no-loc text="Menu"::: | <xref:System.Windows.Forms.ToolStripDropDown><br/><xref:System.Windows.Forms.ToolStripDropDownMenu> | <span data-ttu-id="a9a50-158">MenuItemCollection</span><span class="sxs-lookup"><span data-stu-id="a9a50-158">MenuItemCollection</span></span> |
| <span data-ttu-id="a9a50-159">MainMenu</span><span class="sxs-lookup"><span data-stu-id="a9a50-159">MainMenu</span></span>        | <xref:System.Windows.Forms.MenuStrip>         |  |
| <span data-ttu-id="a9a50-160">MenuItem</span><span class="sxs-lookup"><span data-stu-id="a9a50-160">MenuItem</span></span>        | <xref:System.Windows.Forms.ToolStripMenuItem> |  |

<span data-ttu-id="a9a50-161">我们建议你将应用程序更新到 .NET Core 3.1 并移动到替换控件。</span><span class="sxs-lookup"><span data-stu-id="a9a50-161">We recommend you update your applications to .NET Core 3.1 and move to the replacement controls.</span></span> <span data-ttu-id="a9a50-162">替换控件是一个简单的过程，本质上属于“查找和替换”类型。</span><span class="sxs-lookup"><span data-stu-id="a9a50-162">Replacing the controls is a straightforward process, essentially "find and replace" on the type.</span></span>

## <a name="ccli"></a><span data-ttu-id="a9a50-163">C++/CLI</span><span class="sxs-lookup"><span data-stu-id="a9a50-163">C++/CLI</span></span>

<span data-ttu-id="a9a50-164">*仅限 Windows*</span><span class="sxs-lookup"><span data-stu-id="a9a50-164">*Windows only*</span></span>

<span data-ttu-id="a9a50-165">已添加对创建 C++/CLI（也称为“托管 C++”）项目的支持。</span><span class="sxs-lookup"><span data-stu-id="a9a50-165">Support has been added for creating C++/CLI (also known as "managed C++") projects.</span></span> <span data-ttu-id="a9a50-166">从这些项目生成的二进制文件与 .NET Core 3.0 及更高版本兼容。</span><span class="sxs-lookup"><span data-stu-id="a9a50-166">Binaries produced from these projects are compatible with .NET Core 3.0 and later versions.</span></span>

<span data-ttu-id="a9a50-167">若要添加对 Visual Studio 2019 16.4 中的 C++/CLI 的支持，请安装[“使用 C++ 的桌面开发”工作负载](https://docs.microsoft.com/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads)。</span><span class="sxs-lookup"><span data-stu-id="a9a50-167">To add support for C++/CLI in Visual Studio 2019 16.4, install the [Desktop development with C++ workload](https://docs.microsoft.com/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads).</span></span> <span data-ttu-id="a9a50-168">此工作负载将两个模板添加到 Visual Studio：</span><span class="sxs-lookup"><span data-stu-id="a9a50-168">This workload adds two templates to Visual Studio:</span></span>

- <span data-ttu-id="a9a50-169">CLR 类库(.NET Core)</span><span class="sxs-lookup"><span data-stu-id="a9a50-169">CLR Class Library (.NET Core)</span></span>
- <span data-ttu-id="a9a50-170">CLR 空项目(.NET Core)</span><span class="sxs-lookup"><span data-stu-id="a9a50-170">CLR Empty Project (.NET Core)</span></span>

## <a name="next-steps"></a><span data-ttu-id="a9a50-171">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a9a50-171">Next steps</span></span>

- [<span data-ttu-id="a9a50-172">查看 .NET Core 3.0 和 3.1 之间的重大变更。</span><span class="sxs-lookup"><span data-stu-id="a9a50-172">Review the breaking changes between .NET Core 3.0 and 3.1.</span></span>](../compatibility/3.0-3.1.md)
- [<span data-ttu-id="a9a50-173">查看用于 Windows 窗体应用的 .NET Core 3.1 中的中断性变更。</span><span class="sxs-lookup"><span data-stu-id="a9a50-173">Review the breaking changes between in .NET Core 3.1 for Windows Forms apps.</span></span>](../compatibility/winforms.md#net-core-31)
