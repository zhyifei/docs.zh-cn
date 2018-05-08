---
title: 如何：禁用 ToolStripMenuItems
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], enabling
- ToolStripMenuItems [Windows Forms], disabling
- menu items [Windows Forms], disabling
- disabling menu items
- menu items [Windows Forms], enabling
- menus [Windows Forms], disabling menu items
ms.assetid: bcc1da84-50fd-41d2-8475-103b581d5654
ms.openlocfilehash: 20d0e13642aac3004a31ff416318cf6723207379
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-disable-toolstripmenuitems"></a>如何：禁用 ToolStripMenuItems
你可以限制或扩大用户可通过启用和禁用菜单项以响应用户活动的命令。 当创建，但这可以通过调整时，默认情况下启用菜单项<xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>属性。 在设计时使用此属性可**属性**窗口或以编程方式通过在代码中设置。  
  
### <a name="to-disable-a-menu-item-programmatically"></a>若要以编程方式禁用菜单项  
  
-   在其中设置菜单项的属性方法中，添加代码以设置<xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>属性`false`。  
  
    ```vb  
    MenuItem1.Enabled = False  
    ```  
  
    ```csharp  
    menuItem1.Enabled = false;  
    ```  
  
    ```cpp  
    menuItem1->Enabled = false;  
    ```  
  
    > [!TIP]
    >  禁用菜单中的第一个或顶级菜单项隐藏包含在该菜单中，所有菜单项，但不会禁用它们。 同样，禁用菜单项具有子菜单项隐藏这些子菜单项，但不会禁用它们。 如果给定的菜单上的所有命令都都向用户不可用，它则被视为良好编程习惯隐藏和禁用整个菜单上，这会带来全新的用户界面。 你应隐藏和禁用菜单上，禁用每个项和子菜单项在菜单中，因为仅靠隐藏不会向菜单命令的快捷键通过阻止访问。 设置<xref:System.Windows.Forms.ToolStripItem.Visible%2A>顶级菜单项的属性`false`若要隐藏整个菜单。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [如何：隐藏 ToolStripMenuItem](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)  
 [MenuStrip 控件概述](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
