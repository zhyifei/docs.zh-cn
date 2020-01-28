---
title: MainMenu 组件概述
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: 8bc35de239429214d6b493b343d1dd6c898f4d37
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745113"
---
# <a name="mainmenu-component-overview-windows-forms"></a>MainMenu 组件概述（Windows 窗体）
> [!IMPORTANT]
> 尽管 <xref:System.Windows.Forms.MenuStrip> 和 <xref:System.Windows.Forms.ContextMenuStrip> 将功能替换并添加到以前版本的 <xref:System.Windows.Forms.MainMenu> 和 <xref:System.Windows.Forms.ContextMenu> 控件中，但 <xref:System.Windows.Forms.MainMenu> 和 <xref:System.Windows.Forms.ContextMenu> 会保留，以实现向后兼容性和将来使用（如果你选择）。  
  
 Windows 窗体 <xref:System.Windows.Forms.MainMenu> 组件在运行时显示菜单。 主菜单和各项的所有子菜单都是 <xref:System.Windows.Forms.MenuItem> 对象。  
  
## <a name="key-properties"></a>键属性  
 可以通过将 <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> 属性设置为 `true`，将菜单项指定为默认项。 单击菜单时，默认项将以粗体文本显示。 菜单项的 <xref:System.Windows.Forms.MenuItem.Checked%2A> 属性是 `true` 或 `false`，指示菜单项是否已选中。 菜单项的 <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> 属性自定义选定项的外观：如果 <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> 设置为 `true`，则该项旁边会出现一个单选按钮;如果 <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> 设置为 `false`，则该项旁边会出现一个复选标记。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [MenuStrip 控件概述](menustrip-control-overview-windows-forms.md)
