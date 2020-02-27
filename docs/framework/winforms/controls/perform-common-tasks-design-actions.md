---
title: 在控件上使用设计器操作执行常见任务
ms.date: 02/13/2019
helpviewer_keywords:
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 342741b9ce032b1b8ec50a6c689d9109d12f5b3b
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2020
ms.locfileid: "77634893"
---
# <a name="walkthrough-perform-common-tasks-using-designer-actions"></a>演练：使用设计器操作执行常见任务

当你为 Windows 窗体应用程序构造窗体和控件时，将重复执行许多任务。 以下列表显示了你将会遇到的一些常见任务：

- 添加或删除 <xref:System.Windows.Forms.TabControl>上的选项卡。
- 将控件停靠到其父控件。
- 更改 <xref:System.Windows.Forms.SplitContainer> 控件的方向。

为了加快开发速度，许多控件都提供设计器操作，这些操作是上下文相关的菜单，可用于在设计时在单个手势中执行类似的任务。 这些任务称为*设计器操作谓词*。

设计器操作在设计器中保持附加到控件实例的生存期，并且始终可用。

## <a name="create-the-project"></a>创建项目

第一步是创建项目并设置窗体。

1. 在 Visual Studio 中，创建一个名为**DesignerActionsExample**的基于 Windows 的应用程序项目。

2. 在**Windows 窗体设计器**中选择窗体。

## <a name="use-designer-actions"></a>使用设计器操作

设计器操作在提供这些操作的控件上始终可用。

1. 将 <xref:System.Windows.Forms.TabControl> 从 "**工具箱**" 拖到窗体上。 请注意，<xref:System.Windows.Forms.TabControl>一侧显示的设计器操作标志符号（![小黑色箭头](./media/designer-actions-glyph.gif)）。

2. 单击设计器操作标志符号。 在标志符号旁边显示的快捷菜单中，选择 "**添加" 选项卡**项。 请注意，新的选项卡页已添加到 <xref:System.Windows.Forms.TabControl>。

3. 从 <xref:System.Windows.Forms.TableLayoutPanel> “工具箱” **将** 控件拖到你的窗体上。

4. 单击设计器操作标志符号。 在出现标志符号旁边的快捷菜单中，选择 "**添加列**" 项。 请注意，新列已添加到 <xref:System.Windows.Forms.TableLayoutPanel> 控件。

5. 从 <xref:System.Windows.Forms.SplitContainer> “工具箱” **将** 控件拖到你的窗体上。

6. 单击设计器操作标志符号。 在标志符号旁边显示的快捷菜单中，选择 "**水平拆分器方向**" 项。 请注意，<xref:System.Windows.Forms.SplitContainer> 控件的拆分条现在为水平方向。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
