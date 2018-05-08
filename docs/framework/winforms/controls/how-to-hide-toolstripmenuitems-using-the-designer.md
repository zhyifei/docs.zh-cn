---
title: 如何：使用设计器隐藏 ToolStripMenuItem
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
ms.openlocfilehash: b0018516b9ac337cea3716c4b2eddc6eb859dbb0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a>如何：使用设计器隐藏 ToolStripMenuItem
隐藏菜单项是一种方法来控制你的应用程序的用户界面 (UI)，并限制用户命令。 通常情况下，你将想要隐藏整个菜单的菜单项在其上的所有时不可用。 这会带来较少的用户的干扰。 此外，你可能想要同时隐藏和禁用的菜单或菜单项，如隐藏单独不会阻止用户使用的快捷键访问菜单命令。 禁用菜单项的详细信息，请参阅[如何： 禁用 ToolStripMenuItems 使用设计器](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a>若要隐藏顶级菜单及其子菜单项  
  
1.  选择的顶级菜单项并设置其<xref:System.Windows.Forms.ToolStripItem.Visible%2A>或<xref:System.Windows.Forms.ToolStripItem.Available%2A>属性`false`。  
  
     如果你隐藏顶级菜单项，都将隐藏该菜单中的所有菜单项。 如果你单击以外的某处上<xref:System.Windows.Forms.MenuStrip>后设置<xref:System.Windows.Forms.ToolStripItem.Visible%2A>到`false`，整个顶级菜单项和及其子菜单项从窗体中，因此显示你的操作的运行时效果消失。 若要在设计时显示隐藏的顶级菜单项，请单击<xref:System.Windows.Forms.MenuStrip>中**组件栏**中**文档大纲**，或在属性网格的顶部。  
  
> [!NOTE]
>  极少数情况下将隐藏整个菜单合并方案中的多个文档界面 (MDI) 子菜单除外。  
  
### <a name="to-hide-a-submenu-item"></a>若要隐藏子菜单项  
  
1.  选择的子菜单项并设置其<xref:System.Windows.Forms.ToolStripItem.Visible%2A>属性`false`。  
  
     当隐藏子菜单项时，它将一直显示在设计时窗体上，以便可以轻松地选择它进行进一步的工作。 它将实际被隐藏在运行时。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>  
 <xref:System.Windows.Forms.ToolStripItem.Available%2A>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>  
 [MenuStrip 控件概述](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)  
 [如何：使用设计器禁用 ToolStripMenuItem](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)
