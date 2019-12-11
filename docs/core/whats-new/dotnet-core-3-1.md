---
title: .NET Core 3.1 的新增功能
description: 了解 .NET Core 3.1 的新增功能。
dev_langs:
- csharp
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 08ae824b79ba6a1ff5a92a0b4306eabe5ccadfd2
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "74838307"
---
# <a name="whats-new-in-net-core-31"></a>.NET Core 3.1 的新增功能

本文介绍了 .NET Core 3.1 中的新增功能。 此版本包含对 .NET Core 3.0 的细微改进，重点介绍小型但重要的修复。 .NET Core 3.1 中最重要的特性为，它是[长期支持 (LTS)](#long-term-support) 版本。

如果使用的是 Visual Studio 2019，则必须更新到 [Visual Studio 2019 16.4](https://visualstudio.microsoft.com/downloads/) 才能使用 .NET Core 3.1 项目。 有关 Visual Studio 中新增功能的详细信息，请参阅 [Visual Studio 博客](https://devblogs.microsoft.com/visualstudio/tis-the-season-visual-studio-2019/)。

Visual Studio for Mac 还支持并包括 Visual Studio for Mac 8.4 预览通道中的 .NET Core 3.1。 需要选择加入该预览通道才能使用 .NET Core 3.1。

有关版本的详细信息，请参阅 [.NET Core 3.1 公告](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/)。

- 在 Windows、macOS 或 Linux 上[下载并开始使用 .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)。

## <a name="long-term-support"></a>长期支持

.NET Core 3.1 是未来三年包含来自 Microsoft 的支持的 LTS 版本。 强烈建议将应用移到 .NET Core 3.1。 其他主要版本的当前生命周期如下所示：

| Release | 说明 |
| ------- | ---- |
| .NET Core 3.0 | 生命周期终结于 2020 年 3 月 3 日。     |
| .NET Core 2.2 | 生命周期终结于 2019 年 12 月 23 日。 |
| .NET Core 2.1 | 生命周期终结于 2021 年 8 月 21 日。    |

有关详细信息，请参阅 [.NET Core 支持策略](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)。

## <a name="windows-forms"></a>Windows 窗体

*仅限 Windows*

> [!WARNING]
> Windows 窗体中发生重大变更。

旧版控件包含在 Windows 窗体中，这些窗体在一段时间内无法在 Visual Studio 设计器工具箱中使用。 它们已替换为 .NET Framework 2.0 中的新控件。 它们已从适用于 .NET Core 3.1 的桌面 SDK 中删除。

| 已删除的控件 | 推荐的替换控件 | 已删除关联的 API |
| --------------- | ----------------------- | ----------------------- |
| DataGrid        | <xref:System.Windows.Forms.DataGridView>      | DataGridCell<br/>DataGridRow<br/>DataGridTableCollection<br/>DataGridColumnCollection<br/>DataGridTableStyle<br/>DataGridColumnStyle<br/>DataGridLineStyle<br/>DataGridParentRowsLabel<br/>DataGridParentRowsLabelStyle<br/>DataGridBoolColumn<br/>DataGridTextBox<br/>GridColumnStylesCollection<br/>GridTableStylesCollection<br/>HitTestType |
| ToolBar         | <xref:System.Windows.Forms.ToolStrip>         | ToolBarAppearance |
| ToolBarButton   | <xref:System.Windows.Forms.ToolStripButton>   | ToolBarButtonClickEventArgs<br/>ToolBarButtonClickEventHandler<br/>ToolBarButtonStyle<br/>ToolBarTextAlign |
| ContextMenu     | <xref:System.Windows.Forms.ContextMenuStrip>  |  |
| :::no-loc text="Menu"::: | <xref:System.Windows.Forms.ToolStripDropDown><br/><xref:System.Windows.Forms.ToolStripDropDownMenu> | MenuItemCollection |
| MainMenu        | <xref:System.Windows.Forms.MenuStrip>         |  |
| MenuItem        | <xref:System.Windows.Forms.ToolStripMenuItem> |  |

我们建议你将应用程序更新到 .NET Core 3.1 并移动到替换控件。 替换控件是一个简单的过程，本质上属于“查找和替换”类型。

## <a name="ccli"></a>C++/CLI

*仅限 Windows*

已添加对创建 C++/CLI（也称为“托管 C++”）项目的支持。 从这些项目生成的二进制文件与 .NET Core 3.0 及更高版本兼容。

若要添加对 Visual Studio 2019 16.4 中的 C++/CLI 的支持，请安装[“使用 C++ 的桌面开发”工作负载](https://docs.microsoft.com/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads)。 此工作负载将两个模板添加到 Visual Studio：

- CLR 类库(.NET Core)
- CLR 空项目(.NET Core)

## <a name="next-steps"></a>后续步骤

- [查看 .NET Core 3.0 和 3.1 之间的重大变更。](../compatibility/3.0-3.1.md)
- [查看 Windows 窗体应用的 .NET Framework 和 .NET Core 3.0 之间的中断性变更。](../porting/winforms-breaking-changes.md)
