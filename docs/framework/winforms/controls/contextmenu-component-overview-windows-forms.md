---
title: ContextMenu 구성 요소 개요
ms.date: 03/30/2017
f1_keywords:
- ContextMenu
helpviewer_keywords:
- ContextMenu component [Windows Forms], about ContextMenu component
- context menus [Windows Forms], ContextMenu component
- shortcut menus [Windows Forms], ContextMenu component
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
ms.openlocfilehash: 83740221894941d09d1014585513043851a518e5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746195"
---
# <a name="contextmenu-component-overview-windows-forms"></a>ContextMenu 구성 요소 개요(Windows Forms)
> [!IMPORTANT]
> 尽管 <xref:System.Windows.Forms.MenuStrip> 和 <xref:System.Windows.Forms.ContextMenuStrip> 将功能替换并添加到以前版本的 <xref:System.Windows.Forms.MainMenu> 和 <xref:System.Windows.Forms.ContextMenu> 控件中，但 <xref:System.Windows.Forms.MainMenu> 和 <xref:System.Windows.Forms.ContextMenu> 会保留，以实现向后兼容性和将来使用（如果你选择）。  
  
 使用 Windows 窗体 <xref:System.Windows.Forms.ContextMenu> 组件时，你可以为用户提供易于访问的快捷菜单，其中包含与所选对象关联的常用命令。 快捷菜单中的项通常是显示在应用程序中其他位置的主菜单中的项的子集。 用户通常可以通过右键单击鼠标来访问快捷菜单。 在 Windows 窗体上，快捷菜单与控件相关联。  
  
## <a name="key-properties"></a>키 속성  
 可以通过将控件的 <xref:System.Windows.Forms.Control.ContextMenu%2A> 属性设置为 <xref:System.Windows.Forms.ContextMenu> 组件来将快捷菜单与控件相关联。 单个快捷菜单可以与多个控件关联，但每个控件只能有一个快捷菜单。  
  
 <xref:System.Windows.Forms.ContextMenu> 组件的 key 属性是 <xref:System.Windows.Forms.Menu.MenuItems%2A> 属性。 您可以通过编程方式 <xref:System.Windows.Forms.MenuItem> 创建菜单项，并将它们添加到快捷菜单的 <xref:System.Windows.Forms.Menu.MenuItemCollection> 中。 由于快捷菜单中的项通常从其他菜单绘制，因此您最常通过复制快捷菜单来向其添加项。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ContextMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
