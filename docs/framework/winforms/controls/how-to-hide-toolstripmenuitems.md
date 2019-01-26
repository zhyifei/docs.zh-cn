---
title: 如何：隐藏 Toolstripmenuitem
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding
- MenuStrip control [Windows Forms], hiding menu items
- menus [Windows Forms], hiding menu items
- menu items [Windows Forms], hiding
- hiding menu items
ms.assetid: 418a768f-808a-44cd-8cef-f4e161883621
ms.openlocfilehash: 73e49c96c20f145490a2d494177e21bc957605b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727620"
---
# <a name="how-to-hide-toolstripmenuitems"></a>如何：隐藏 Toolstripmenuitem
隐藏菜单项是一种方法来控制你的应用程序的用户界面并限制用户命令。 通常情况下，想要在其上的菜单项都不可用时隐藏整个菜单。 这提供了用户很少会分心。 此外，您可能希望能够同时隐藏和禁用的菜单或菜单项，如仅隐藏不会阻止用户使用的快捷键访问菜单命令。  
  
### <a name="to-hide-any-menu-item-programmatically"></a>若要以编程方式隐藏任何菜单项  
  
-   在其中设置菜单项的属性方法中，添加代码以设置<xref:System.Windows.Forms.ToolStripItem.Visible%2A>属性设置为`false`。  
  
    ```vb  
    MenuItem3.Visible = False  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
    ```  
  
## <a name="see-also"></a>请参阅
- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- [MenuStrip 控件概述](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
- [如何：禁用 Toolstripmenuitem](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md)
