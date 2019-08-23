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
ms.openlocfilehash: fe46683faee13bad951d5a7185aad8a687c290ef
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952137"
---
# <a name="mainmenu-component-overview-windows-forms"></a>MainMenu 组件概述（Windows 窗体）
> [!IMPORTANT]
> 尽管<xref:System.Windows.Forms.MenuStrip>和<xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu>将功能替换为以前版本的和控件, 并将其保留以实现后向兼容性和将来使用 (如果你选择)。 <xref:System.Windows.Forms.ContextMenuStrip>  
  
 Windows 窗体<xref:System.Windows.Forms.MainMenu>组件在运行时显示菜单。 主菜单和各个项的所有子菜单都<xref:System.Windows.Forms.MenuItem>是对象。  
  
## <a name="key-properties"></a>键属性  
 可以通过将<xref:System.Windows.Forms.MenuItem.DefaultItem%2A>属性设置为来`true`将菜单项指定为默认项。 单击菜单时, 默认项将以粗体文本显示。 菜单项的<xref:System.Windows.Forms.MenuItem.Checked%2A>属性`true`为或`false`, 指示菜单项是否已选中。 <xref:System.Windows.Forms.MenuItem.RadioCheck%2A>菜单项的属性自定义选定项的外观: 如果`true` <xref:System.Windows.Forms.MenuItem.RadioCheck%2A>将设置为, 则该项旁边会出现一个单选按钮; 如果<xref:System.Windows.Forms.MenuItem.RadioCheck%2A>设置为`false`, 则该项旁边会出现一个复选标记。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [MenuStrip 控件概述](menustrip-control-overview-windows-forms.md)
