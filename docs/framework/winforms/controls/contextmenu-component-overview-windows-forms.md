---
title: ContextMenu 组件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- ContextMenu
helpviewer_keywords:
- ContextMenu component [Windows Forms], about ContextMenu component
- context menus [Windows Forms], ContextMenu component
- shortcut menus [Windows Forms], ContextMenu component
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
ms.openlocfilehash: 6ae7817bc158f30fbf55b5f6228ecdf134d6657d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962184"
---
# <a name="contextmenu-component-overview-windows-forms"></a>ContextMenu 组件概述（Windows 窗体）
> [!IMPORTANT]
> 尽管<xref:System.Windows.Forms.MenuStrip>和<xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu>将功能替换为以前版本的和控件, 并将其保留以实现后向兼容性和将来使用 (如果你选择)。 <xref:System.Windows.Forms.ContextMenuStrip>  
  
 使用 Windows 窗体<xref:System.Windows.Forms.ContextMenu>组件, 您可以为用户提供易于访问的快捷菜单, 其中包含与所选对象关联的常用命令。 快捷菜单中的项通常是显示在应用程序中其他位置的主菜单中的项的子集。 用户通常可以通过右键单击鼠标来访问快捷菜单。 在 Windows 窗体上, 快捷菜单与控件相关联。  
  
## <a name="key-properties"></a>键属性  
 可以通过将控件的<xref:System.Windows.Forms.Control.ContextMenu%2A>属性设置<xref:System.Windows.Forms.ContextMenu>为组件, 将快捷菜单与控件相关联。 单个快捷菜单可以与多个控件关联, 但每个控件只能有一个快捷菜单。  
  
 <xref:System.Windows.Forms.ContextMenu>组件的键属性<xref:System.Windows.Forms.Menu.MenuItems%2A>是属性。 您可以通过以编程方式创建<xref:System.Windows.Forms.MenuItem>对象并将其添加<xref:System.Windows.Forms.Menu.MenuItemCollection>到快捷菜单的中来添加菜单项。 由于快捷菜单中的项通常从其他菜单绘制, 因此您最常通过复制快捷菜单来向其添加项。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.ContextMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
