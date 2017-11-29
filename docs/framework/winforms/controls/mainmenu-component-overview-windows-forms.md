---
title: "MainMenu 组件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6f5cfe3a97bbbd4d5ba2d3ba089736599b6a2190
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="mainmenu-component-overview-windows-forms"></a><span data-ttu-id="80ddc-102">MainMenu 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="80ddc-102">MainMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="80ddc-103">尽管<xref:System.Windows.Forms.MenuStrip>和<xref:System.Windows.Forms.ContextMenuStrip>替换，并将功能添加到<xref:System.Windows.Forms.MainMenu>和<xref:System.Windows.Forms.ContextMenu>的早期版本中，控件<xref:System.Windows.Forms.MainMenu>和<xref:System.Windows.Forms.ContextMenu>如果你选择将保留用于向后兼容性和将来使用。</span><span class="sxs-lookup"><span data-stu-id="80ddc-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="80ddc-104">Windows 窗体<xref:System.Windows.Forms.MainMenu>组件在运行时显示一个菜单。</span><span class="sxs-lookup"><span data-stu-id="80ddc-104">The Windows Forms <xref:System.Windows.Forms.MainMenu> component displays a menu at run time.</span></span> <span data-ttu-id="80ddc-105">所有子菜单的主菜单和各个项是<xref:System.Windows.Forms.MenuItem>对象。</span><span class="sxs-lookup"><span data-stu-id="80ddc-105">All submenus of the main menu and individual items are <xref:System.Windows.Forms.MenuItem> objects.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="80ddc-106">键属性</span><span class="sxs-lookup"><span data-stu-id="80ddc-106">Key Properties</span></span>  
 <span data-ttu-id="80ddc-107">菜单项可以通过设置指定为默认项<xref:System.Windows.Forms.MenuItem.DefaultItem%2A>属性`true`。</span><span class="sxs-lookup"><span data-stu-id="80ddc-107">A menu item can be designated as the default item by setting the <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> property to `true`.</span></span> <span data-ttu-id="80ddc-108">单击菜单时，默认项以粗体显示。</span><span class="sxs-lookup"><span data-stu-id="80ddc-108">The default item appears in bold text when the menu is clicked.</span></span> <span data-ttu-id="80ddc-109">菜单项的<xref:System.Windows.Forms.MenuItem.Checked%2A>属性`true`或`false`，并指示是否选定菜单项。</span><span class="sxs-lookup"><span data-stu-id="80ddc-109">The menu item's <xref:System.Windows.Forms.MenuItem.Checked%2A> property is either `true` or `false`, and indicates whether the menu item is selected.</span></span> <span data-ttu-id="80ddc-110">菜单项的<xref:System.Windows.Forms.MenuItem.RadioCheck%2A>属性自定义的选定项的外观： 如果<xref:System.Windows.Forms.MenuItem.RadioCheck%2A>设置为`true`，如果，则一个单选按钮项; 旁边会出现<xref:System.Windows.Forms.MenuItem.RadioCheck%2A>设置为`false`，项旁边显示一个复选标记。</span><span class="sxs-lookup"><span data-stu-id="80ddc-110">The menu item's <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> property customizes the appearance of the selected item: if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `true`, a radio button appears next to the item; if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `false`, a check mark appears next to the item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80ddc-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80ddc-111">See Also</span></span>  
 <xref:System.Windows.Forms.MainMenu>  
 <xref:System.Windows.Forms.Menu>  
 <xref:System.Windows.Forms.MenuItem>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 [<span data-ttu-id="80ddc-112">MenuStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="80ddc-112">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
