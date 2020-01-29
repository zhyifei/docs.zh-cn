---
title: MenuStrip 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
ms.openlocfilehash: a536d13cb7be3f4e4e4a085e1a4da1b0899b3a0c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734464"
---
# <a name="menustrip-control-overview-windows-forms"></a>MenuStrip 컨트롤 개요(Windows Forms)
菜单通过保存按公共主题分组的命令向用户公开功能。  
  
 <xref:System.Windows.Forms.MenuStrip> 控件是在 .NET Framework 版本2.0 中引入的。 利用 <xref:System.Windows.Forms.MenuStrip> 控件，你可以轻松地创建菜单，如 Microsoft Office 中找到的菜单。  
  
 <xref:System.Windows.Forms.MenuStrip> 控件支持多文档界面（MDI）和菜单合并、工具提示和溢出。 您可以通过添加访问键、快捷键、复选标记、图像和分隔栏来增强菜单的可用性和可读性。  
  
 <xref:System.Windows.Forms.MenuStrip> 控件将替换功能并将其添加到 <xref:System.Windows.Forms.MainMenu> 控件;但是，会保留 <xref:System.Windows.Forms.MainMenu> 控件以实现向后兼容性和将来使用（如果你选择）。  
  
## <a name="ways-to-use-the-menustrip-control"></a>使用 MenuStrip 控件的方式  
 使用 <xref:System.Windows.Forms.MenuStrip> 控件可以：  
  
- 创建可轻松自定义的常用菜单，这些菜单支持高级用户界面和布局功能，如文本和图像顺序和对齐方式、拖放操作、MDI、溢出以及访问菜单命令的其他模式。  
  
- 支持操作系统的典型外观和行为。  
  
- 以一致的方式处理所有容器和包含项的事件，其方式与处理其他控件的事件的方式相同。  
  
 下表显示 <xref:System.Windows.Forms.MenuStrip> 和关联类的一些特别重要的属性。  
  
|속성|설명|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|获取或设置用于显示 MDI 子窗体列表的 <xref:System.Windows.Forms.ToolStripMenuItem>。|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|获取或设置如何在 MDI 应用程序中将子菜单与父菜单合并。|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|获取或设置在 MDI 应用程序中的菜单内的合并项的位置。|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|获取或设置一个值，该值指示窗体是否为 MDI 子窗体的容器。|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|获取或设置一个值，该值指示是否为 <xref:System.Windows.Forms.MenuStrip>显示工具提示。|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|获取或设置一个值，该值指示 <xref:System.Windows.Forms.MenuStrip> 是否支持溢出功能。|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|获取或设置与 <xref:System.Windows.Forms.ToolStripMenuItem>关联的快捷键。|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|获取或设置一个值，该值指示与 <xref:System.Windows.Forms.ToolStripMenuItem> 关联的快捷键是否显示在 <xref:System.Windows.Forms.ToolStripMenuItem>旁边。|  
  
 下表显示了重要的 <xref:System.Windows.Forms.MenuStrip> 伴生类。  
  
|클래스|설명|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|表示在 <xref:System.Windows.Forms.MenuStrip> 或 <xref:System.Windows.Forms.ContextMenuStrip>上显示的可选择选项。|  
|<xref:System.Windows.Forms.ContextMenuStrip>|바로 가기 메뉴를 나타냅니다.|  
|<xref:System.Windows.Forms.ToolStripDropDown>|表示一个控件，该控件允许用户从列表中选择单个项（当用户单击 <xref:System.Windows.Forms.ToolStripDropDownButton> 或更高级别菜单项时显示）。|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|提供从 <xref:System.Windows.Forms.ToolStripItem> 派生的控件的基本功能，这些控件在被单击时显示下拉项。|  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
