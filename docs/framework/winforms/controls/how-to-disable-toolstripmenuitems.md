---
title: "如何：禁用 ToolStripMenuItems"
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
- ToolStripMenuItems [Windows Forms], enabling
- ToolStripMenuItems [Windows Forms], disabling
- menu items [Windows Forms], disabling
- disabling menu items
- menu items [Windows Forms], enabling
- menus [Windows Forms], disabling menu items
ms.assetid: bcc1da84-50fd-41d2-8475-103b581d5654
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e3307da3e0810ea775c799a4b065e1f7484b5779
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-disable-toolstripmenuitems"></a><span data-ttu-id="bf64e-102">如何：禁用 ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="bf64e-102">How to: Disable ToolStripMenuItems</span></span>
<span data-ttu-id="bf64e-103">你可以限制或扩大用户可通过启用和禁用菜单项以响应用户活动的命令。</span><span class="sxs-lookup"><span data-stu-id="bf64e-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="bf64e-104">当创建，但这可以通过调整时，默认情况下启用菜单项<xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="bf64e-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="bf64e-105">在设计时使用此属性可**属性**窗口或以编程方式通过在代码中设置。</span><span class="sxs-lookup"><span data-stu-id="bf64e-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span>  
  
### <a name="to-disable-a-menu-item-programmatically"></a><span data-ttu-id="bf64e-106">若要以编程方式禁用菜单项</span><span class="sxs-lookup"><span data-stu-id="bf64e-106">To disable a menu item programmatically</span></span>  
  
-   <span data-ttu-id="bf64e-107">在其中设置菜单项的属性方法中，添加代码以设置<xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>属性`false`。</span><span class="sxs-lookup"><span data-stu-id="bf64e-107">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
    ```vb  
    MenuItem1.Enabled = False  
    ```  
  
    ```csharp  
    menuItem1.Enabled = false;  
    ```  
  
    ```cpp  
    menuItem1->Enabled = false;  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="bf64e-108">禁用菜单中的第一个或顶级菜单项隐藏包含在该菜单中，所有菜单项，但不会禁用它们。</span><span class="sxs-lookup"><span data-stu-id="bf64e-108">Disabling the first or top-level menu item in a menu hides all the menu items contained within the menu, but does not disable them.</span></span> <span data-ttu-id="bf64e-109">同样，禁用菜单项具有子菜单项隐藏这些子菜单项，但不会禁用它们。</span><span class="sxs-lookup"><span data-stu-id="bf64e-109">Likewise, disabling a menu item that has submenu items hides the submenu items, but does not disable them.</span></span> <span data-ttu-id="bf64e-110">如果给定的菜单上的所有命令都都向用户不可用，它则被视为良好编程习惯隐藏和禁用整个菜单上，这会带来全新的用户界面。</span><span class="sxs-lookup"><span data-stu-id="bf64e-110">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="bf64e-111">你应隐藏和禁用菜单上，禁用每个项和子菜单项在菜单中，因为仅靠隐藏不会向菜单命令的快捷键通过阻止访问。</span><span class="sxs-lookup"><span data-stu-id="bf64e-111">You should hide and disable the menu, and disable every item and submenu item in the menu, because hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="bf64e-112">设置<xref:System.Windows.Forms.ToolStripItem.Visible%2A>顶级菜单项的属性`false`若要隐藏整个菜单。</span><span class="sxs-lookup"><span data-stu-id="bf64e-112">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf64e-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf64e-113">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="bf64e-114">如何：隐藏 ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="bf64e-114">How to: Hide ToolStripMenuItems</span></span>](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)  
 [<span data-ttu-id="bf64e-115">MenuStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="bf64e-115">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
