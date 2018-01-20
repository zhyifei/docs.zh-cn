---
title: "如何：使用设计器禁用 ToolStripMenuItem"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f704e99622900d8c37c8ddd5054a3c5ad920bc6b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="70284-102">如何：使用设计器禁用 ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="70284-102">How to: Disable ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="70284-103">你可以限制或扩大用户可通过启用和禁用菜单项以响应用户活动的命令。</span><span class="sxs-lookup"><span data-stu-id="70284-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="70284-104">当创建，但这可以通过调整时，默认情况下启用菜单项<xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="70284-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="70284-105">在设计时使用此属性可**属性**窗口或以编程方式通过在代码中设置。</span><span class="sxs-lookup"><span data-stu-id="70284-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span> <span data-ttu-id="70284-106">有关详细信息，请参阅[如何： 禁用 ToolStripMenuItems](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md)。</span><span class="sxs-lookup"><span data-stu-id="70284-106">For more information, see [How to: Disable ToolStripMenuItems](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70284-107">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="70284-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="70284-108">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="70284-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="70284-109">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="70284-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-disable-a-menu-item-at-design-time"></a><span data-ttu-id="70284-110">若要在设计时禁用菜单项</span><span class="sxs-lookup"><span data-stu-id="70284-110">To disable a menu item at design time</span></span>  
  
1.  <span data-ttu-id="70284-111">选择窗体上的菜单项，其中设置<xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>属性`false`。</span><span class="sxs-lookup"><span data-stu-id="70284-111">With the menu item selected on the form, set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="70284-112">禁用菜单中的第一个或顶级菜单项将禁用菜单中包含的所有菜单项。</span><span class="sxs-lookup"><span data-stu-id="70284-112">Disabling the first or top-level menu item in a menu disables all the menu items contained within the menu.</span></span> <span data-ttu-id="70284-113">同样，禁用菜单项具有子菜单项将禁用这些子菜单项。</span><span class="sxs-lookup"><span data-stu-id="70284-113">Likewise, disabling a menu item that has submenu items disables the submenu items.</span></span> <span data-ttu-id="70284-114">如果给定的菜单上的所有命令都都向用户不可用，它则被视为良好编程习惯隐藏和禁用整个菜单上，这会带来全新的用户界面。</span><span class="sxs-lookup"><span data-stu-id="70284-114">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="70284-115">你应同时隐藏和禁用菜单上，因为仅靠隐藏不会向菜单命令的快捷键通过阻止访问。</span><span class="sxs-lookup"><span data-stu-id="70284-115">You should both hide and disable the menu, as hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="70284-116">设置<xref:System.Windows.Forms.ToolStripItem.Visible%2A>顶级菜单项的属性`false`若要隐藏整个菜单。</span><span class="sxs-lookup"><span data-stu-id="70284-116">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70284-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="70284-117">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="70284-118">如何：隐藏 ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="70284-118">How to: Hide ToolStripMenuItems</span></span>](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)  
 [<span data-ttu-id="70284-119">MenuStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="70284-119">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
