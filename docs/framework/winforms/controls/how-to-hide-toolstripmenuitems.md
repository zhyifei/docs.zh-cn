---
title: 如何：隐藏 ToolStripMenuItem
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
ms.openlocfilehash: dc9daa945f2a546548f2cc6ea033378bd9ceff93
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127421"
---
# <a name="how-to-hide-toolstripmenuitems"></a><span data-ttu-id="d4f35-102">如何：隐藏 ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="d4f35-102">How to: Hide ToolStripMenuItems</span></span>
<span data-ttu-id="d4f35-103">隐藏菜单项是一种方法来控制你的应用程序的用户界面并限制用户命令。</span><span class="sxs-lookup"><span data-stu-id="d4f35-103">Hiding menu items is a way to control the user interface of your application and restrict user commands.</span></span> <span data-ttu-id="d4f35-104">通常情况下，想要在其上的菜单项都不可用时隐藏整个菜单。</span><span class="sxs-lookup"><span data-stu-id="d4f35-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="d4f35-105">这提供了用户很少会分心。</span><span class="sxs-lookup"><span data-stu-id="d4f35-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="d4f35-106">此外，您可能希望能够同时隐藏和禁用的菜单或菜单项，如仅隐藏不会阻止用户使用的快捷键访问菜单命令。</span><span class="sxs-lookup"><span data-stu-id="d4f35-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span>  
  
### <a name="to-hide-any-menu-item-programmatically"></a><span data-ttu-id="d4f35-107">若要以编程方式隐藏任何菜单项</span><span class="sxs-lookup"><span data-stu-id="d4f35-107">To hide any menu item programmatically</span></span>  
  
-   <span data-ttu-id="d4f35-108">在其中设置菜单项的属性方法中，添加代码以设置<xref:System.Windows.Forms.ToolStripItem.Visible%2A>属性设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="d4f35-108">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>  
  
    ```vb  
    MenuItem3.Visible = False  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d4f35-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4f35-109">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- [<span data-ttu-id="d4f35-110">MenuStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="d4f35-110">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
- [<span data-ttu-id="d4f35-111">如何：禁用 Toolstripmenuitem</span><span class="sxs-lookup"><span data-stu-id="d4f35-111">How to: Disable ToolStripMenuItems</span></span>](how-to-disable-toolstripmenuitems.md)
