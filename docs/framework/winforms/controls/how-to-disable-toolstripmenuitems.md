---
title: 如何：禁用 ToolStripMenuItem
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
ms.openlocfilehash: f86a2934e799e4604693491dacbecc517d44d810
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046222"
---
# <a name="how-to-disable-toolstripmenuitems"></a><span data-ttu-id="56281-102">如何：禁用 ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="56281-102">How to: Disable ToolStripMenuItems</span></span>
<span data-ttu-id="56281-103">你可以通过启用和禁用菜单项来限制或放宽用户在响应用户活动时所能执行的命令。</span><span class="sxs-lookup"><span data-stu-id="56281-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="56281-104">默认情况下, 菜单项在创建时处于启用状态, 但可以通过<xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>属性进行调整。</span><span class="sxs-lookup"><span data-stu-id="56281-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="56281-105">可以在设计时在 "**属性**" 窗口中或通过编程方式在代码中设置此属性。</span><span class="sxs-lookup"><span data-stu-id="56281-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span>  
  
### <a name="to-disable-a-menu-item-programmatically"></a><span data-ttu-id="56281-106">以编程方式禁用菜单项</span><span class="sxs-lookup"><span data-stu-id="56281-106">To disable a menu item programmatically</span></span>  
  
- <span data-ttu-id="56281-107">在设置菜单项属性的方法中, 添加要将属性设置为<xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> `false`的代码。</span><span class="sxs-lookup"><span data-stu-id="56281-107">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
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
    > <span data-ttu-id="56281-108">禁用菜单中的第一个或顶级菜单项将隐藏菜单中包含的所有菜单项, 但不会将其禁用。</span><span class="sxs-lookup"><span data-stu-id="56281-108">Disabling the first or top-level menu item in a menu hides all the menu items contained within the menu, but does not disable them.</span></span> <span data-ttu-id="56281-109">同样, 禁用具有子菜单项的菜单项将隐藏子菜单项, 但不会禁用子菜单项。</span><span class="sxs-lookup"><span data-stu-id="56281-109">Likewise, disabling a menu item that has submenu items hides the submenu items, but does not disable them.</span></span> <span data-ttu-id="56281-110">如果给定菜单上的所有命令均不可供用户使用, 则会被视为良好的编程做法, 隐藏和禁用整个菜单, 因为这会显示一个干净的用户界面。</span><span class="sxs-lookup"><span data-stu-id="56281-110">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="56281-111">你应隐藏和禁用菜单, 并禁用菜单中的每个项和子菜单项, 因为仅限隐藏不会阻止通过快捷键访问菜单命令。</span><span class="sxs-lookup"><span data-stu-id="56281-111">You should hide and disable the menu, and disable every item and submenu item in the menu, because hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="56281-112">将顶级<xref:System.Windows.Forms.ToolStripItem.Visible%2A>菜单项的属性设置为`false`以隐藏整个菜单。</span><span class="sxs-lookup"><span data-stu-id="56281-112">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56281-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="56281-113">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="56281-114">如何：隐藏 Toolstripmenuitem</span><span class="sxs-lookup"><span data-stu-id="56281-114">How to: Hide ToolStripMenuItems</span></span>](how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="56281-115">MenuStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="56281-115">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
