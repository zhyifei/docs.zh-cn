---
title: ContextMenu 组件概述
ms.date: 03/30/2017
f1_keywords:
- ContextMenu
helpviewer_keywords:
- ContextMenu component [Windows Forms], about ContextMenu component
- context menus [Windows Forms], ContextMenu component
- shortcut menus [Windows Forms], ContextMenu component
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
ms.openlocfilehash: 83740221894941d09d1014585513043851a518e5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746195"
---
# <a name="contextmenu-component-overview-windows-forms"></a><span data-ttu-id="c59fb-102">ContextMenu 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="c59fb-102">ContextMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="c59fb-103">尽管 <xref:System.Windows.Forms.MenuStrip> 和 <xref:System.Windows.Forms.ContextMenuStrip> 将功能替换并添加到以前版本的 <xref:System.Windows.Forms.MainMenu> 和 <xref:System.Windows.Forms.ContextMenu> 控件中，但 <xref:System.Windows.Forms.MainMenu> 和 <xref:System.Windows.Forms.ContextMenu> 会保留，以实现向后兼容性和将来使用（如果你选择）。</span><span class="sxs-lookup"><span data-stu-id="c59fb-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="c59fb-104">使用 Windows 窗体 <xref:System.Windows.Forms.ContextMenu> 组件时，你可以为用户提供易于访问的快捷菜单，其中包含与所选对象关联的常用命令。</span><span class="sxs-lookup"><span data-stu-id="c59fb-104">With the Windows Forms <xref:System.Windows.Forms.ContextMenu> component, you can provide users with an easily accessible shortcut menu of frequently used commands that are associated with the selected object.</span></span> <span data-ttu-id="c59fb-105">快捷菜单中的项通常是显示在应用程序中其他位置的主菜单中的项的子集。</span><span class="sxs-lookup"><span data-stu-id="c59fb-105">The items in a shortcut menu are frequently a subset of the items from main menus that appear elsewhere in the application.</span></span> <span data-ttu-id="c59fb-106">用户通常可以通过右键单击鼠标来访问快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="c59fb-106">A user can typically access a shortcut menu by right-clicking the mouse.</span></span> <span data-ttu-id="c59fb-107">在 Windows 窗体上，快捷菜单与控件相关联。</span><span class="sxs-lookup"><span data-stu-id="c59fb-107">On Windows Forms, shortcut menus are associated with controls.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="c59fb-108">键属性</span><span class="sxs-lookup"><span data-stu-id="c59fb-108">Key Properties</span></span>  
 <span data-ttu-id="c59fb-109">可以通过将控件的 <xref:System.Windows.Forms.Control.ContextMenu%2A> 属性设置为 <xref:System.Windows.Forms.ContextMenu> 组件来将快捷菜单与控件相关联。</span><span class="sxs-lookup"><span data-stu-id="c59fb-109">You can associate a shortcut menu with a control by setting the control's <xref:System.Windows.Forms.Control.ContextMenu%2A> property to the <xref:System.Windows.Forms.ContextMenu> component.</span></span> <span data-ttu-id="c59fb-110">单个快捷菜单可以与多个控件关联，但每个控件只能有一个快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="c59fb-110">A single shortcut menu can be associated with multiple controls, but each control can have only one shortcut menu.</span></span>  
  
 <span data-ttu-id="c59fb-111"><xref:System.Windows.Forms.ContextMenu> 组件的 key 属性是 <xref:System.Windows.Forms.Menu.MenuItems%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="c59fb-111">The key property of the <xref:System.Windows.Forms.ContextMenu> component is the <xref:System.Windows.Forms.Menu.MenuItems%2A> property.</span></span> <span data-ttu-id="c59fb-112">您可以通过编程方式 <xref:System.Windows.Forms.MenuItem> 创建菜单项，并将它们添加到快捷菜单的 <xref:System.Windows.Forms.Menu.MenuItemCollection> 中。</span><span class="sxs-lookup"><span data-stu-id="c59fb-112">You can add menu items by programmatically creating <xref:System.Windows.Forms.MenuItem> objects and adding them to the <xref:System.Windows.Forms.Menu.MenuItemCollection> of the shortcut menu.</span></span> <span data-ttu-id="c59fb-113">由于快捷菜单中的项通常从其他菜单绘制，因此您最常通过复制快捷菜单来向其添加项。</span><span class="sxs-lookup"><span data-stu-id="c59fb-113">Because the items in a shortcut menu are usually drawn from other menus, you will most frequently add items to a shortcut menu by copying them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c59fb-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c59fb-114">See also</span></span>

- <xref:System.Windows.Forms.ContextMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
