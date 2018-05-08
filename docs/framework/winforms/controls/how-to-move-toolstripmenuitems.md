---
title: 如何：移动 ToolStripMenuItem
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], moving
- menus [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], dragging and dropping
- menu items [Windows Forms], moving
- menu items [Windows Forms], cutting and pasting
- menu items [Windows Forms], dragging and dropping
- MenuStrip control [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], cutting and pasting
ms.assetid: cab9e03e-4edd-4c25-b3e3-bd1edc602bd9
ms.openlocfilehash: 5cfaf87a59d27678cfb786633ed4c9a9f66bac76
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-move-toolstripmenuitems"></a>如何：移动 ToolStripMenuItem
在设计时，你可以将整个顶级菜单及其菜单项到其他位置<xref:System.Windows.Forms.MenuStrip>。 你还可以顶级菜单之间移动的单个菜单项或更改的菜单中的菜单项的位置。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a>若要将顶级菜单及其菜单项移动到另一个顶级位置  
  
1.  单击并按住鼠标左键在显示你想要移动的菜单。  
  
2.  将插入点拖到预期新位置之前的顶级菜单并释放鼠标左键。  
  
     所选的菜单将插入点的右移。  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a>若要将顶级菜单及其菜单项移动到一个下拉位置  
  
1.  左键单击想要移动并按 CTRL + X，或右键单击该菜单选择的菜单**剪切**从快捷菜单。  
  
2.  在目标顶级菜单中，左键单击预期新位置上方的菜单项，按 CTRL + V，或右键单击预期新位置上方的菜单项并选择**粘贴**从快捷菜单。  
  
     你将剪切的菜单将插入到所选的菜单项之后。  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a>移动菜单使用项集合编辑器中的一个菜单项  
  
1.  右键单击包含您想要移动的菜单项的菜单。  
  
2.  从快捷菜单中选择**编辑下拉菜单项**。  
  
3.  在**项集合编辑器**，左键单击想要移动的菜单项。  
  
4.  单击向上和向下箭头键，来移动菜单中的菜单项。  
  
5.  单击 **“确定”**。  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a>移动菜单使用键盘中的一个菜单项  
  
1.  按住 ALT 键。  
  
2.  单击并按住鼠标左键在您想要移动的菜单项上。  
  
3.  将菜单项拖动到新位置并释放鼠标左键。  
  
### <a name="to-move-a-menu-item-to-another-menu"></a>若要移动到另一个菜单的菜单项  
  
1.  左键单击想要移动，按 CTRL + X，或右键单击菜单项，选择菜单项**剪切**从快捷菜单。  
  
2.  左键单击将包含你所剪切菜单项的菜单。  
  
3.  左键单击预期新位置之前的菜单项并按 CTRL + V，或右键单击预期新位置并选择之前的菜单项**粘贴**从快捷菜单。  
  
     所选的菜单项后插入的菜单项，你将剪切。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [MenuStrip 控件概述](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
