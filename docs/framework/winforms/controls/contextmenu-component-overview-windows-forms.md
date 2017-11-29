---
title: "ContextMenu 组件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ContextMenu
helpviewer_keywords:
- ContextMenu component [Windows Forms], about ContextMenu component
- context menus [Windows Forms], ContextMenu component
- shortcut menus [Windows Forms], ContextMenu component
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f6c2542ca7ee27bec96bb5010bcdb2fcd7416f72
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="contextmenu-component-overview-windows-forms"></a>ContextMenu 组件概述（Windows 窗体）
> [!IMPORTANT]
>  尽管<xref:System.Windows.Forms.MenuStrip>和<xref:System.Windows.Forms.ContextMenuStrip>替换，并将功能添加到<xref:System.Windows.Forms.MainMenu>和<xref:System.Windows.Forms.ContextMenu>的早期版本中，控件<xref:System.Windows.Forms.MainMenu>和<xref:System.Windows.Forms.ContextMenu>如果你选择将保留用于向后兼容性和将来使用。  
  
 在 Windows 窗体<xref:System.Windows.Forms.ContextMenu>组件，你可以为用户提供了与所选对象的常用命令可以轻松进行访问的快捷菜单。 快捷菜单中的项通常是从应用程序中的其他位置出现的主菜单项的子集。 用户通常可通过快捷菜单上单击鼠标右键。 Windows 窗体上快捷菜单都与控件关联。  
  
## <a name="key-properties"></a>键属性  
 你可以与控件关联的快捷菜单，通过设置控件的<xref:System.Windows.Forms.Control.ContextMenu%2A>属性<xref:System.Windows.Forms.ContextMenu>组件。 单个的快捷菜单可能与多个控件，但每个控件可以有一个快捷菜单。  
  
 键属性的<xref:System.Windows.Forms.ContextMenu>组件是<xref:System.Windows.Forms.Menu.MenuItems%2A>属性。 您可以通过以编程方式创建添加菜单项<xref:System.Windows.Forms.MenuItem>对象并将它们添加到<xref:System.Windows.Forms.Menu.MenuItemCollection>的快捷菜单。 因为快捷菜单中的项通常取自其他菜单，你将最常将项添加到快捷菜单将其复制。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.ContextMenu>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>
