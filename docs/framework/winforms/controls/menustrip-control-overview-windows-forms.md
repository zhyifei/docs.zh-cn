---
title: MenuStrip 控件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
ms.openlocfilehash: b09d653210c72a38bbc4dc0858ae2553ad9cbeef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="menustrip-control-overview-windows-forms"></a>MenuStrip 控件概述（Windows 窗体）
菜单公开按常见的主题分组的命令到你的用户的功能。  
  
 <xref:System.Windows.Forms.MenuStrip>控件不熟悉此版本的 Visual Studio 和.NET Framework。 与该控件可以轻松创建如在 Microsoft Office 中找到的菜单。  
  
 <xref:System.Windows.Forms.MenuStrip>控件支持多文档界面 (MDI) 和菜单合并功能、 工具提示和溢出。 你可以通过添加访问密钥、 快捷键、 复选标记、 映像和分隔条增强的可用性和你菜单的可读性。  
  
 <xref:System.Windows.Forms.MenuStrip>控件替换，并将功能添加到<xref:System.Windows.Forms.MainMenu>控制; 但是，<xref:System.Windows.Forms.MainMenu>可以选择保留向后兼容并供将来使用的控件。  
  
## <a name="ways-to-use-the-menustrip-control"></a>如何使用 MenuStrip 控件  
 使用<xref:System.Windows.Forms.MenuStrip>控制转移到：  
  
-   创建轻松地自定义，支持的常用的菜单高级用户界面和布局功能，例如文本和图像排序和对齐方式、 拖放操作、 MDI、 溢出及访问菜单命令的备用模式。  
  
-   支持的典型的外观和行为的操作系统。  
  
-   处理一致地为所有容器和包含的项的事件，将相同的方式处理其他控件的事件。  
  
 下表显示的某些特别重要属性<xref:System.Windows.Forms.MenuStrip>和关联的类。  
  
|属性|描述|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|获取或设置<xref:System.Windows.Forms.ToolStripMenuItem>用于显示 MDI 子窗体的列表。|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|获取或设置子菜单如何合并与 MDI 应用程序中的父菜单。|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|获取或设置 MDI 应用程序中合并菜单中项的位置。|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|获取或设置一个值，该值指示窗体 MDI 子窗体的容器。|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|获取或设置一个值，该值指示是否显示工具提示<xref:System.Windows.Forms.MenuStrip>。|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|获取或设置一个值，该值指示 <xref:System.Windows.Forms.MenuStrip> 是否支持溢出功能。|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|获取或设置与关联的快捷键<xref:System.Windows.Forms.ToolStripMenuItem>。|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|获取或设置一个值，该值是否快捷方式密钥与之关联<xref:System.Windows.Forms.ToolStripMenuItem>旁边显示<xref:System.Windows.Forms.ToolStripMenuItem>。|  
  
 下表显示了重要<xref:System.Windows.Forms.MenuStrip>伴生类。  
  
|类|描述|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|表示上显示的可选选项<xref:System.Windows.Forms.MenuStrip>或<xref:System.Windows.Forms.ContextMenuStrip>。|  
|<xref:System.Windows.Forms.ContextMenuStrip>|表示快捷菜单。|  
|<xref:System.Windows.Forms.ToolStripDropDown>|表示允许用户从在用户单击时显示的列表中选择单个项的控件<xref:System.Windows.Forms.ToolStripDropDownButton>或更高级别的菜单项。|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|提供基本功能，为控件派生自<xref:System.Windows.Forms.ToolStripItem>显示单击时的下拉列表项。|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripDropDown>
