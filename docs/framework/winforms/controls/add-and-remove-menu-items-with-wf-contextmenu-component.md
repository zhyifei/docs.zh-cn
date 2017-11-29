---
title: "如何：使用 Windows 窗体 ContextMenu 组件添加和移除菜单项"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], removing items
- ContextMenu component [Windows Forms], adding items
- shortcut menus [Windows Forms], removing items
- shortcut menus [Windows Forms], examples
- context menus [Windows Forms], adding items
- shortcut menus [Windows Forms], adding items
- ContextMenu component [Windows Forms], removing items
- context menus [Windows Forms], examples
- examples [Windows Forms], context menus
ms.assetid: 426d1eaf-7fb8-4b0b-8a33-5e8721786ea4
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cf0e579d5cf377169eeb4d394c4127d53fd54540
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a>如何：使用 Windows 窗体 ContextMenu 组件添加和移除菜单项
说明如何添加和删除 Windows 窗体中的快捷菜单项。  
  
 Windows 窗体<xref:System.Windows.Forms.ContextMenu>组件提供了与所选对象相关的常用命令的菜单。 你可以将项添加到快捷菜单添加<xref:System.Windows.Forms.MenuItem>对象添加到<xref:System.Windows.Forms.Menu.MenuItems%2A>集合。  
  
 你可以永久移除项的快捷菜单;但是，在运行时它可能更合适，若要隐藏或改为禁用项。  
  
> [!IMPORTANT]
>  尽管<xref:System.Windows.Forms.MenuStrip>和<xref:System.Windows.Forms.ContextMenuStrip>替换，并将功能添加到<xref:System.Windows.Forms.MainMenu>和<xref:System.Windows.Forms.ContextMenu>的早期版本中，控件<xref:System.Windows.Forms.MainMenu>和<xref:System.Windows.Forms.ContextMenu>如果你选择将保留用于向后兼容性和将来使用。  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a>若要从快捷菜单中删除项目  
  
1.  使用<xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A>或<xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A>方法<xref:System.Windows.Forms.Menu.MenuItems%2A>集合<xref:System.Windows.Forms.ContextMenu>组件以删除特定的菜单项。  
  
    ```vb  
    ' Removes the first item in the shortcut menu.  
    ContextMenu1.MenuItems.RemoveAt(0)  
    ' Removes a particular object from the shortcut menu.  
    ContextMenu1.MenuItems.Remove(mnuItemNew)  
    ```  
  
    ```csharp  
    // Removes the first item in the shortcut menu.  
    contextMenu1.MenuItems.RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1.MenuItems.Remove(mnuItemNew);  
    ```  
  
    ```cpp  
    // Removes the first item in the shortcut menu.  
    contextMenu1->MenuItems->RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1->MenuItems->Remove(mnuItemNew);  
    ```  
  
     - 或 -  
  
2.  使用`Clear`方法`MenuItems`集合<xref:System.Windows.Forms.ContextMenu>组件从菜单中移除所有项。  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.ContextMenu>  
 [ContextMenu 组件](../../../../docs/framework/winforms/controls/contextmenu-component-windows-forms.md)  
 [ContextMenu 组件概述](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)
