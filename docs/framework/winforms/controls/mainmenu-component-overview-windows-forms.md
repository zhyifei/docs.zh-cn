---
title: MainMenu 组件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: a7ea9fcf25942f21d2d549ea998161398fbc608f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="mainmenu-component-overview-windows-forms"></a>MainMenu 组件概述（Windows 窗体）
> [!IMPORTANT]
>  尽管<xref:System.Windows.Forms.MenuStrip>和<xref:System.Windows.Forms.ContextMenuStrip>替换，并将功能添加到<xref:System.Windows.Forms.MainMenu>和<xref:System.Windows.Forms.ContextMenu>的早期版本中，控件<xref:System.Windows.Forms.MainMenu>和<xref:System.Windows.Forms.ContextMenu>如果你选择将保留用于向后兼容性和将来使用。  
  
 Windows 窗体<xref:System.Windows.Forms.MainMenu>组件在运行时显示一个菜单。 所有子菜单的主菜单和各个项是<xref:System.Windows.Forms.MenuItem>对象。  
  
## <a name="key-properties"></a>键属性  
 菜单项可以通过设置指定为默认项<xref:System.Windows.Forms.MenuItem.DefaultItem%2A>属性`true`。 单击菜单时，默认项以粗体显示。 菜单项的<xref:System.Windows.Forms.MenuItem.Checked%2A>属性`true`或`false`，并指示是否选定菜单项。 菜单项的<xref:System.Windows.Forms.MenuItem.RadioCheck%2A>属性自定义的选定项的外观： 如果<xref:System.Windows.Forms.MenuItem.RadioCheck%2A>设置为`true`，如果，则一个单选按钮项; 旁边会出现<xref:System.Windows.Forms.MenuItem.RadioCheck%2A>设置为`false`，项旁边显示一个复选标记。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.MainMenu>  
 <xref:System.Windows.Forms.Menu>  
 <xref:System.Windows.Forms.MenuItem>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 [MenuStrip 控件概述](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
