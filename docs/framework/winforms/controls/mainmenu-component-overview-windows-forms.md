---
title: MainMenu 组件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: da1b76a7019f364e7463a8345aa80d9a9bd6089e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168475"
---
# <a name="mainmenu-component-overview-windows-forms"></a><span data-ttu-id="660bc-102">MainMenu 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="660bc-102">MainMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="660bc-103">尽管<xref:System.Windows.Forms.MenuStrip>和<xref:System.Windows.Forms.ContextMenuStrip>替换并将功能添加到<xref:System.Windows.Forms.MainMenu>并<xref:System.Windows.Forms.ContextMenu>的早期版本中，控件<xref:System.Windows.Forms.MainMenu>和<xref:System.Windows.Forms.ContextMenu>也可选择将保留向后兼容性和将来使用。</span><span class="sxs-lookup"><span data-stu-id="660bc-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="660bc-104">Windows 窗体<xref:System.Windows.Forms.MainMenu>组件在运行时显示一个菜单。</span><span class="sxs-lookup"><span data-stu-id="660bc-104">The Windows Forms <xref:System.Windows.Forms.MainMenu> component displays a menu at run time.</span></span> <span data-ttu-id="660bc-105">主菜单和各个项的所有子菜单是<xref:System.Windows.Forms.MenuItem>对象。</span><span class="sxs-lookup"><span data-stu-id="660bc-105">All submenus of the main menu and individual items are <xref:System.Windows.Forms.MenuItem> objects.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="660bc-106">键属性</span><span class="sxs-lookup"><span data-stu-id="660bc-106">Key Properties</span></span>  
 <span data-ttu-id="660bc-107">菜单项可以指定为默认项的设置<xref:System.Windows.Forms.MenuItem.DefaultItem%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="660bc-107">A menu item can be designated as the default item by setting the <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> property to `true`.</span></span> <span data-ttu-id="660bc-108">单击菜单时，默认项以粗体文本显示。</span><span class="sxs-lookup"><span data-stu-id="660bc-108">The default item appears in bold text when the menu is clicked.</span></span> <span data-ttu-id="660bc-109">菜单项<xref:System.Windows.Forms.MenuItem.Checked%2A>属性是`true`或`false`，并指示是否选定菜单项。</span><span class="sxs-lookup"><span data-stu-id="660bc-109">The menu item's <xref:System.Windows.Forms.MenuItem.Checked%2A> property is either `true` or `false`, and indicates whether the menu item is selected.</span></span> <span data-ttu-id="660bc-110">菜单项<xref:System.Windows.Forms.MenuItem.RadioCheck%2A>属性自定义的选定项的外观： 如果<xref:System.Windows.Forms.MenuItem.RadioCheck%2A>设置为`true`，单选按钮旁边的项; 如果<xref:System.Windows.Forms.MenuItem.RadioCheck%2A>设置为`false`，项的旁边显示复选标记。</span><span class="sxs-lookup"><span data-stu-id="660bc-110">The menu item's <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> property customizes the appearance of the selected item: if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `true`, a radio button appears next to the item; if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `false`, a check mark appears next to the item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="660bc-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="660bc-111">See also</span></span>

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="660bc-112">MenuStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="660bc-112">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
