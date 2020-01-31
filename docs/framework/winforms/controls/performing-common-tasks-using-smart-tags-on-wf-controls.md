---
title: 使用控件上的智能标记 Performi 常见任务
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 826313d0a89410f62c034a5fba4dee32e90a1750
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744256"
---
# <a name="walkthrough-perform-common-tasks-using-smart-tags"></a>演练：使用智能标记执行常规任务

当你为 Windows 窗体应用程序构造窗体和控件时，将重复执行许多任务。 以下是你将会遇到的一些常见任务：

- 添加或删除 <xref:System.Windows.Forms.TabControl>上的选项卡。

- 将控件停靠到其父控件。

- 更改 <xref:System.Windows.Forms.SplitContainer> 控件的方向。

为了加快开发速度，许多控件都提供智能标记，这是一个上下文相关菜单，可用于在设计时在单个手势中执行类似这些任务的常见任务。 这些任务称为*智能标记谓词*。

智能标记在设计器的生存期内保持附加到控件实例，并且始终可用。

## <a name="create-the-project"></a>프로젝트를 만듭니다.

첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.

1. 在 Visual Studio 中，创建一个名为**SmartTagsExample**的基于 Windows 的应用程序项目。

2. 在**Windows 窗体设计器**中选择窗体。

## <a name="use-smart-tags"></a>使用智能标记

智能标记在设计时在提供这些标记的控件上始终可用。

1. 将 <xref:System.Windows.Forms.TabControl> 从 "**工具箱**" 拖到窗体上。 请注意，在 <xref:System.Windows.Forms.TabControl>的一侧会出现智能标记标志符号（![智能标记标志符号](./media/vs-winformsmttagglyph.gif)）。

2. 单击智能标记标志符号。 在标志符号旁边显示的快捷菜单中，选择 "**添加" 选项卡**项。 请注意，新的选项卡页已添加到 <xref:System.Windows.Forms.TabControl>。

3. <xref:System.Windows.Forms.TableLayoutPanel> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.

4. 单击智能标记标志符号。 在出现标志符号旁边的快捷菜单中，选择 "**添加列**" 项。 请注意，新列已添加到 <xref:System.Windows.Forms.TableLayoutPanel> 控件。

5. <xref:System.Windows.Forms.SplitContainer> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.

6. 单击智能标记标志符号。 在标志符号旁边显示的快捷菜单中，选择 "**水平拆分器方向**" 项。 请注意，<xref:System.Windows.Forms.SplitContainer> 控件的拆分条现在为水平方向。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
