---
title: 如何：使用设计器禁用 ToolStripMenuItem
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
ms.openlocfilehash: 692b6c11f6d58c52a0af29ed04ada45c48cae058
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046241"
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="72af8-102">如何：使用设计器禁用 ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="72af8-102">How to: Disable ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="72af8-103">你可以通过启用和禁用菜单项来限制或放宽用户在响应用户活动时所能执行的命令。</span><span class="sxs-lookup"><span data-stu-id="72af8-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="72af8-104">默认情况下, 菜单项在创建时处于启用状态, 但可以通过<xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>属性进行调整。</span><span class="sxs-lookup"><span data-stu-id="72af8-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="72af8-105">可以在设计时在 "**属性**" 窗口中或通过编程方式在代码中设置此属性。</span><span class="sxs-lookup"><span data-stu-id="72af8-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span> <span data-ttu-id="72af8-106">有关详细信息，请参阅[如何：禁用 Toolstripmenuitem](how-to-disable-toolstripmenuitems.md)。</span><span class="sxs-lookup"><span data-stu-id="72af8-106">For more information, see [How to: Disable ToolStripMenuItems](how-to-disable-toolstripmenuitems.md).</span></span>

## <a name="to-disable-a-menu-item-at-design-time"></a><span data-ttu-id="72af8-107">在设计时禁用菜单项</span><span class="sxs-lookup"><span data-stu-id="72af8-107">To disable a menu item at design time</span></span>

1. <span data-ttu-id="72af8-108">在窗体上选中菜单项时, 将<xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>属性设置为。 `false`</span><span class="sxs-lookup"><span data-stu-id="72af8-108">With the menu item selected on the form, set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>

    > [!TIP]
    > <span data-ttu-id="72af8-109">禁用菜单中的第一个或顶级菜单项, 将禁用该菜单中包含的所有菜单项。</span><span class="sxs-lookup"><span data-stu-id="72af8-109">Disabling the first or top-level menu item in a menu disables all the menu items contained within the menu.</span></span> <span data-ttu-id="72af8-110">同样, 禁用具有子菜单项的菜单项将禁用子菜单项。</span><span class="sxs-lookup"><span data-stu-id="72af8-110">Likewise, disabling a menu item that has submenu items disables the submenu items.</span></span> <span data-ttu-id="72af8-111">如果给定菜单上的所有命令均不可供用户使用, 则会被视为良好的编程做法, 隐藏和禁用整个菜单, 因为这会显示一个干净的用户界面。</span><span class="sxs-lookup"><span data-stu-id="72af8-111">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="72af8-112">你应隐藏和禁用菜单, 因为仅隐藏不会阻止通过快捷键访问菜单命令。</span><span class="sxs-lookup"><span data-stu-id="72af8-112">You should both hide and disable the menu, as hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="72af8-113">将顶级<xref:System.Windows.Forms.ToolStripItem.Visible%2A>菜单项的属性设置为`false`以隐藏整个菜单。</span><span class="sxs-lookup"><span data-stu-id="72af8-113">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>

## <a name="see-also"></a><span data-ttu-id="72af8-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="72af8-114">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="72af8-115">如何：隐藏 Toolstripmenuitem</span><span class="sxs-lookup"><span data-stu-id="72af8-115">How to: Hide ToolStripMenuItems</span></span>](how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="72af8-116">MenuStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="72af8-116">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
