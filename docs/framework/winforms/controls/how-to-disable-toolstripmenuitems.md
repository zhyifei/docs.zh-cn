---
title: 如何：禁用 Toolstripmenuitem
ms.date: 03/30/2017
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
ms.openlocfilehash: 3c18935239a4355d5416a0a79d0fa9f5c504cc7e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720207"
---
# <a name="how-to-disable-toolstripmenuitems"></a><span data-ttu-id="a6f30-102">如何：禁用 Toolstripmenuitem</span><span class="sxs-lookup"><span data-stu-id="a6f30-102">How to: Disable ToolStripMenuItems</span></span>
<span data-ttu-id="a6f30-103">您可以限制或扩大用户可通过启用和禁用对用户活动的响应中的菜单项的命令。</span><span class="sxs-lookup"><span data-stu-id="a6f30-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="a6f30-104">菜单项时创建，但这可以通过调整默认情况下启用<xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="a6f30-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="a6f30-105">在设计时使用此属性可**属性**窗口或以编程方式在代码中设置。</span><span class="sxs-lookup"><span data-stu-id="a6f30-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span>  
  
### <a name="to-disable-a-menu-item-programmatically"></a><span data-ttu-id="a6f30-106">若要以编程方式禁用菜单项</span><span class="sxs-lookup"><span data-stu-id="a6f30-106">To disable a menu item programmatically</span></span>  
  
-   <span data-ttu-id="a6f30-107">在其中设置菜单项的属性方法中，添加代码以设置<xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>属性设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="a6f30-107">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
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
    >  <span data-ttu-id="a6f30-108">禁用菜单中的第一个或顶级菜单项隐藏菜单中包含的所有菜单项，但不会禁用。</span><span class="sxs-lookup"><span data-stu-id="a6f30-108">Disabling the first or top-level menu item in a menu hides all the menu items contained within the menu, but does not disable them.</span></span> <span data-ttu-id="a6f30-109">同样，禁用具有子菜单项的菜单项隐藏子菜单项，但不会禁用。</span><span class="sxs-lookup"><span data-stu-id="a6f30-109">Likewise, disabling a menu item that has submenu items hides the submenu items, but does not disable them.</span></span> <span data-ttu-id="a6f30-110">如果给定的菜单上的所有命令都都对用户不可用，它视为良好编程习惯，同时隐藏和禁用整个菜单中，这提供了一个清晰的用户界面。</span><span class="sxs-lookup"><span data-stu-id="a6f30-110">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="a6f30-111">应隐藏和禁用菜单，并禁用每个项目和子菜单项在菜单中，因为仅靠隐藏不会向菜单命令的快捷键通过阻止访问。</span><span class="sxs-lookup"><span data-stu-id="a6f30-111">You should hide and disable the menu, and disable every item and submenu item in the menu, because hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="a6f30-112">设置<xref:System.Windows.Forms.ToolStripItem.Visible%2A>属性的顶级菜单项`false`若要隐藏整个菜单。</span><span class="sxs-lookup"><span data-stu-id="a6f30-112">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6f30-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6f30-113">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="a6f30-114">如何：隐藏 Toolstripmenuitem</span><span class="sxs-lookup"><span data-stu-id="a6f30-114">How to: Hide ToolStripMenuItems</span></span>](how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="a6f30-115">MenuStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="a6f30-115">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
