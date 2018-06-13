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
ms.openlocfilehash: 73f67bbe6b2d51a59b6f72ab5faf21db9d6db12d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531948"
---
# <a name="how-to-hide-toolstripmenuitems"></a><span data-ttu-id="546c5-102">如何：隐藏 ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="546c5-102">How to: Hide ToolStripMenuItems</span></span>
<span data-ttu-id="546c5-103">隐藏菜单项是一种方法来控制你的应用程序的用户界面并限制用户命令。</span><span class="sxs-lookup"><span data-stu-id="546c5-103">Hiding menu items is a way to control the user interface of your application and restrict user commands.</span></span> <span data-ttu-id="546c5-104">通常情况下，你将想要隐藏整个菜单的菜单项在其上的所有时不可用。</span><span class="sxs-lookup"><span data-stu-id="546c5-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="546c5-105">这会带来较少的用户的干扰。</span><span class="sxs-lookup"><span data-stu-id="546c5-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="546c5-106">此外，你可能想要同时隐藏和禁用的菜单或菜单项，如隐藏单独不会阻止用户使用的快捷键访问菜单命令。</span><span class="sxs-lookup"><span data-stu-id="546c5-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span>  
  
### <a name="to-hide-any-menu-item-programmatically"></a><span data-ttu-id="546c5-107">若要以编程方式隐藏任何菜单项</span><span class="sxs-lookup"><span data-stu-id="546c5-107">To hide any menu item programmatically</span></span>  
  
-   <span data-ttu-id="546c5-108">在其中设置菜单项的属性方法中，添加代码以设置<xref:System.Windows.Forms.ToolStripItem.Visible%2A>属性`false`。</span><span class="sxs-lookup"><span data-stu-id="546c5-108">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>  
  
    ```vb  
    MenuItem3.Visible = False  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="546c5-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="546c5-109">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
 <xref:System.Windows.Forms.MenuStrip>  
 [<span data-ttu-id="546c5-110">MenuStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="546c5-110">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="546c5-111">如何：禁用 ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="546c5-111">How to: Disable ToolStripMenuItems</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md)
