---
title: 演练：使用 Windows 窗体控件上的智能标记执行常规任务
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 07fb43a711ae8b1e2e375b17b136c07f35b1cf39
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459574"
---
# <a name="walkthrough-perform-common-tasks-using-smart-tags"></a>演练：使用智能标记执行常规任务

当你为 Windows 窗体应用程序构造窗体和控件时，将重复执行许多任务。 以下是你将会遇到的一些常见任务：

- 添加或删除 <xref:System.Windows.Forms.TabControl>上的选项卡。

- 将控件停靠到其父控件。

- 更改 <xref:System.Windows.Forms.SplitContainer> 控件的方向。

为了加快开发速度，许多控件都提供智能标记，这是一个上下文相关菜单，可用于在设计时在单个手势中执行类似这些任务的常见任务。 这些任务称为*智能标记谓词*。

智能标记在设计器的生存期内保持附加到控件实例，并且始终可用。

## <a name="create-the-project"></a>创建项目

第一步是创建项目并设置窗体。

1. 在 Visual Studio 中，创建一个名为**SmartTagsExample**的基于 Windows 的应用程序项目。

2. 在**Windows 窗体设计器**中选择窗体。

## <a name="use-smart-tags"></a>使用智能标记

智能标记在设计时在提供这些标记的控件上始终可用。

1. 将 <xref:System.Windows.Forms.TabControl> 从 "**工具箱**" 拖到窗体上。 请注意，在 <xref:System.Windows.Forms.TabControl>的一侧会出现智能标记标志符号（![智能标记标志符号](./media/vs-winformsmttagglyph.gif)）。

2. 单击智能标记标志符号。 在标志符号旁边显示的快捷菜单中，选择 "**添加" 选项卡**项。 请注意，新的选项卡页已添加到 <xref:System.Windows.Forms.TabControl>。

3. 从 <xref:System.Windows.Forms.TableLayoutPanel> “工具箱” **将** 控件拖到你的窗体上。

4. 单击智能标记标志符号。 在出现标志符号旁边的快捷菜单中，选择 "**添加列**" 项。 请注意，新列已添加到 <xref:System.Windows.Forms.TableLayoutPanel> 控件。

5. 从 <xref:System.Windows.Forms.SplitContainer> “工具箱” **将** 控件拖到你的窗体上。

6. 单击智能标记标志符号。 在标志符号旁边显示的快捷菜单中，选择 "**水平拆分器方向**" 项。 请注意，<xref:System.Windows.Forms.SplitContainer> 控件的拆分条现在为水平方向。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
