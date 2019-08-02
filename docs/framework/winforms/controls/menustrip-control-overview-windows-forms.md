---
title: MenuStrip 控件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
ms.openlocfilehash: 46a3a25415db77ee261f5fb1c3bf114b2275a2d4
ms.sourcegitcommit: 8c6426a3d2adff5fbcbe1fed0f28eda718c15351
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/02/2019
ms.locfileid: "68733461"
---
# <a name="menustrip-control-overview-windows-forms"></a>MenuStrip 控件概述（Windows 窗体）
菜单通过保存按公共主题分组的命令向用户公开功能。  
  
 <xref:System.Windows.Forms.MenuStrip>控件是在 .NET Framework 2.0 版中引入的。 <xref:System.Windows.Forms.MenuStrip>借助控件, 可以轻松创建菜单, 如 Microsoft Office 中找到的菜单。  
  
 <xref:System.Windows.Forms.MenuStrip>控件支持多文档界面 (MDI) 和菜单合并、工具提示和溢出。 您可以通过添加访问键、快捷键、复选标记、图像和分隔栏来增强菜单的可用性和可读性。  
  
 控件将替换并添加<xref:System.Windows.Forms.MainMenu>到<xref:System.Windows.Forms.MainMenu>控件中的功能; 但是, 会保留控件以实现向后兼容性和将来使用 (如果你选择)。 <xref:System.Windows.Forms.MenuStrip>  
  
## <a name="ways-to-use-the-menustrip-control"></a>使用 MenuStrip 控件的方式  
 <xref:System.Windows.Forms.MenuStrip>使用控件可以:  
  
- 创建可轻松自定义的常用菜单, 这些菜单支持高级用户界面和布局功能, 如文本和图像顺序和对齐方式、拖放操作、MDI、溢出以及访问菜单命令的其他模式。  
  
- 支持操作系统的典型外观和行为。  
  
- 以一致的方式处理所有容器和包含项的事件, 其方式与处理其他控件的事件的方式相同。  
  
 下表显示了和关联类的一些<xref:System.Windows.Forms.MenuStrip>特别重要的属性。  
  
|Property|描述|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|获取或设置<xref:System.Windows.Forms.ToolStripMenuItem>用于显示 MDI 子窗体列表的。|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|获取或设置如何在 MDI 应用程序中将子菜单与父菜单合并。|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|获取或设置在 MDI 应用程序中的菜单内的合并项的位置。|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|获取或设置一个值, 该值指示窗体是否为 MDI 子窗体的容器。|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|获取或设置一个值, 该值指示是否显示<xref:System.Windows.Forms.MenuStrip>的工具提示。|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|获取或设置一个值，该值指示 <xref:System.Windows.Forms.MenuStrip> 是否支持溢出功能。|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|获取或设置与<xref:System.Windows.Forms.ToolStripMenuItem>关联的快捷键。|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|获取或设置一个值, 该值指示与关联的<xref:System.Windows.Forms.ToolStripMenuItem>快捷键是否显示在旁边。 <xref:System.Windows.Forms.ToolStripMenuItem>|  
  
 下表显示了重要<xref:System.Windows.Forms.MenuStrip>的伴生类。  
  
|类|描述|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|表示在<xref:System.Windows.Forms.MenuStrip>或<xref:System.Windows.Forms.ContextMenuStrip>上显示的可选择选项。|  
|<xref:System.Windows.Forms.ContextMenuStrip>|表示快捷菜单。|  
|<xref:System.Windows.Forms.ToolStripDropDown>|表示一个控件, 该控件允许用户从列表中选择单个项 (当用户单击<xref:System.Windows.Forms.ToolStripDropDownButton>或更高级别菜单项时显示)。|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|为在单击时显示<xref:System.Windows.Forms.ToolStripItem>的下拉项的控件提供基本功能。|  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
