---
title: ContextMenu 组件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- ContextMenu
helpviewer_keywords:
- ContextMenu component [Windows Forms], about ContextMenu component
- context menus [Windows Forms], ContextMenu component
- shortcut menus [Windows Forms], ContextMenu component
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
ms.openlocfilehash: 7da0522dae00608ead356484a31d219a67ec4ba9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54545668"
---
# <a name="contextmenu-component-overview-windows-forms"></a><span data-ttu-id="2f9a1-102">ContextMenu 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="2f9a1-102">ContextMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="2f9a1-103">尽管<xref:System.Windows.Forms.MenuStrip>和<xref:System.Windows.Forms.ContextMenuStrip>替换并将功能添加到<xref:System.Windows.Forms.MainMenu>并<xref:System.Windows.Forms.ContextMenu>的早期版本中，控件<xref:System.Windows.Forms.MainMenu>和<xref:System.Windows.Forms.ContextMenu>也可选择将保留向后兼容性和将来使用。</span><span class="sxs-lookup"><span data-stu-id="2f9a1-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="2f9a1-104">使用 Windows 窗体<xref:System.Windows.Forms.ContextMenu>组件，您可以向用户提供与所选对象相关联的常用命令的轻松访问的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="2f9a1-104">With the Windows Forms <xref:System.Windows.Forms.ContextMenu> component, you can provide users with an easily accessible shortcut menu of frequently used commands that are associated with the selected object.</span></span> <span data-ttu-id="2f9a1-105">快捷菜单中的项通常是从主应用程序中的其他位置出现的菜单项的子集。</span><span class="sxs-lookup"><span data-stu-id="2f9a1-105">The items in a shortcut menu are frequently a subset of the items from main menus that appear elsewhere in the application.</span></span> <span data-ttu-id="2f9a1-106">用户通常可以通过右键单击鼠标访问快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="2f9a1-106">A user can typically access a shortcut menu by right-clicking the mouse.</span></span> <span data-ttu-id="2f9a1-107">在 Windows 窗体上快捷菜单是与控件相关联。</span><span class="sxs-lookup"><span data-stu-id="2f9a1-107">On Windows Forms, shortcut menus are associated with controls.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="2f9a1-108">键属性</span><span class="sxs-lookup"><span data-stu-id="2f9a1-108">Key Properties</span></span>  
 <span data-ttu-id="2f9a1-109">可以与控件关联的快捷菜单，通过设置控件的<xref:System.Windows.Forms.Control.ContextMenu%2A>属性设置为<xref:System.Windows.Forms.ContextMenu>组件。</span><span class="sxs-lookup"><span data-stu-id="2f9a1-109">You can associate a shortcut menu with a control by setting the control's <xref:System.Windows.Forms.Control.ContextMenu%2A> property to the <xref:System.Windows.Forms.ContextMenu> component.</span></span> <span data-ttu-id="2f9a1-110">一个快捷方式菜单可以与多个控件相关联，但每个控件可以有一个快捷方式菜单。</span><span class="sxs-lookup"><span data-stu-id="2f9a1-110">A single shortcut menu can be associated with multiple controls, but each control can have only one shortcut menu.</span></span>  
  
 <span data-ttu-id="2f9a1-111">键属性<xref:System.Windows.Forms.ContextMenu>组件是<xref:System.Windows.Forms.Menu.MenuItems%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="2f9a1-111">The key property of the <xref:System.Windows.Forms.ContextMenu> component is the <xref:System.Windows.Forms.Menu.MenuItems%2A> property.</span></span> <span data-ttu-id="2f9a1-112">可以通过以编程方式创建添加菜单项<xref:System.Windows.Forms.MenuItem>对象并将它们添加到<xref:System.Windows.Forms.Menu.MenuItemCollection>的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="2f9a1-112">You can add menu items by programmatically creating <xref:System.Windows.Forms.MenuItem> objects and adding them to the <xref:System.Windows.Forms.Menu.MenuItemCollection> of the shortcut menu.</span></span> <span data-ttu-id="2f9a1-113">因为快捷菜单中的项通常取自其他菜单，您将最常添加项到快捷菜单通过将其复制。</span><span class="sxs-lookup"><span data-stu-id="2f9a1-113">Because the items in a shortcut menu are usually drawn from other menus, you will most frequently add items to a shortcut menu by copying them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f9a1-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="2f9a1-114">See also</span></span>
- <xref:System.Windows.Forms.ContextMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
