---
title: "ContextMenuStrip 控件概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ContextMenuStrip
helpviewer_keywords:
- context menus [Windows Forms], ContextMenuStrip control [Windows Forms]
- shortcut menus [Windows Forms], ContextMenuStrip control [Windows Forms]
- ContextMenuStrip control [Windows Forms], about ContextMenuStrip control
ms.assetid: 9787cdb3-88f1-4198-972f-eefd9524ce39
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 11d5de760b8a03d7bc35adabb631048a70e20264
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="contextmenustrip-control-overview"></a><span data-ttu-id="47bf9-102">ContextMenuStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="47bf9-102">ContextMenuStrip Control Overview</span></span>
> [!NOTE]
>  <span data-ttu-id="47bf9-103"><xref:System.Windows.Forms.ContextMenuStrip>控件替换，并将功能添加到<xref:System.Windows.Forms.ContextMenu>控制; 但是，<xref:System.Windows.Forms.ContextMenu>可以选择保留向后兼容并供将来使用的控件。</span><span class="sxs-lookup"><span data-stu-id="47bf9-103">The <xref:System.Windows.Forms.ContextMenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ContextMenu> control; however, the <xref:System.Windows.Forms.ContextMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="47bf9-104">用户单击鼠标右键按钮时，快捷菜单，也称为上下文菜单，将出现在鼠标位置。</span><span class="sxs-lookup"><span data-stu-id="47bf9-104">Shortcut menus, also called context menus, appear at the mouse position when the user clicks the right mouse button.</span></span> <span data-ttu-id="47bf9-105">快捷*菜单*工作区或鼠标指针位置的控件提供的选项。</span><span class="sxs-lookup"><span data-stu-id="47bf9-105">Shortcut *menus* provide options for the client area or the control at the mouse pointer location.</span></span>  
  
 <span data-ttu-id="47bf9-106"><xref:System.Windows.Forms.ContextMenuStrip>控件设计可以无缝地使用新<xref:System.Windows.Forms.ToolStrip>和相关的控件，但你可以将相关联<xref:System.Windows.Forms.ContextMenuStrip>与其他控件一样轻松。</span><span class="sxs-lookup"><span data-stu-id="47bf9-106">The <xref:System.Windows.Forms.ContextMenuStrip> control is designed to work seamlessly with the new <xref:System.Windows.Forms.ToolStrip> and related controls, but you can associate a <xref:System.Windows.Forms.ContextMenuStrip> with other controls just as easily.</span></span>  
  
 <span data-ttu-id="47bf9-107">下表显示了重要<xref:System.Windows.Forms.ContextMenuStrip>伴生类。</span><span class="sxs-lookup"><span data-stu-id="47bf9-107">The following table shows the important <xref:System.Windows.Forms.ContextMenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="47bf9-108">类</span><span class="sxs-lookup"><span data-stu-id="47bf9-108">Class</span></span>|<span data-ttu-id="47bf9-109">描述</span><span class="sxs-lookup"><span data-stu-id="47bf9-109">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="47bf9-110">表示上显示的可选选项<xref:System.Windows.Forms.MenuStrip>或<xref:System.Windows.Forms.ContextMenuStrip>。</span><span class="sxs-lookup"><span data-stu-id="47bf9-110">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="47bf9-111">表示使用户能够从在用户单击时显示的列表中选择单个项的控件<xref:System.Windows.Forms.ToolStripDropDownButton>或更高级别的菜单项。</span><span class="sxs-lookup"><span data-stu-id="47bf9-111">Represents a control that enables the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="47bf9-112">提供基本功能，为控件派生自<xref:System.Windows.Forms.ToolStripItem>显示单击时的下拉列表项。</span><span class="sxs-lookup"><span data-stu-id="47bf9-112">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="47bf9-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="47bf9-113">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 <xref:System.Windows.Forms.ToolStripDropDown>
