---
title: 如何：使用设计器隐藏 ToolStripMenuItem
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
ms.openlocfilehash: 0e1cd7d1868adabd4d3eec9510f6ee567ba3867d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966618"
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a>如何：使用设计器隐藏 ToolStripMenuItem
通过隐藏菜单项, 可以控制应用程序的用户界面 (UI) 和限制用户命令。 通常, 当菜单上的所有菜单项均不可用时, 您需要隐藏整个菜单。 这为用户提供的干扰更少。 此外, 您可能还希望隐藏和禁用菜单项或菜单项, 因为仅隐藏不会阻止用户使用快捷键访问菜单命令。 有关禁用菜单项的详细信息, 请[参阅如何:使用设计器](how-to-disable-toolstripmenuitems-using-the-designer.md)禁用 toolstripmenuitem。

## <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a>隐藏顶级菜单及其子菜单项

1. 选择顶级菜单项, 并将其<xref:System.Windows.Forms.ToolStripItem.Visible%2A>或<xref:System.Windows.Forms.ToolStripItem.Available%2A>属性设置为`false`。

     隐藏顶级菜单项时, 该菜单内的所有菜单项也将隐藏。 如果在 "设置<xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ToolStripItem.Visible%2A>为`false`" 后单击 "除" 之外的任何位置, 则整个顶级菜单项及其子菜单项将从窗体中消失, 从而显示操作的运行时效果。 若要在设计时显示隐藏的顶级菜单项, 请在<xref:System.Windows.Forms.MenuStrip> **组件栏**、"**文档大纲**" 中或在属性网格顶部单击。

> [!NOTE]
> 除了合并方案中的多文档界面 (MDI) 子菜单以外, 您几乎不会隐藏整个菜单。

## <a name="to-hide-a-submenu-item"></a>隐藏子菜单项

1. 选择子菜单项, 并将<xref:System.Windows.Forms.ToolStripItem.Visible%2A>其属性`false`设置为。

     隐藏子菜单项时, 它会在设计时在窗体上保持可见, 以便您可以轻松地选择它来进行进一步的工作。 它实际上会在运行时隐藏。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>
- <xref:System.Windows.Forms.ToolStripItem.Available%2A>
- <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>
- [MenuStrip 控件概述](menustrip-control-overview-windows-forms.md)
- [如何：使用设计器禁用 Toolstripmenuitem](how-to-disable-toolstripmenuitems-using-the-designer.md)
