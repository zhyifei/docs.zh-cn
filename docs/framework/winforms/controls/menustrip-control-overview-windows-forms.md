---
title: "MenuStrip 控件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eb27503fffc798b644f95fd213f8f23bdb3e228a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="menustrip-control-overview-windows-forms"></a><span data-ttu-id="407d3-102">MenuStrip 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="407d3-102">MenuStrip Control Overview (Windows Forms)</span></span>
<span data-ttu-id="407d3-103">菜单公开按常见的主题分组的命令到你的用户的功能。</span><span class="sxs-lookup"><span data-stu-id="407d3-103">Menus expose functionality to your users by holding commands that are grouped by a common theme.</span></span>  
  
 <span data-ttu-id="407d3-104"><xref:System.Windows.Forms.MenuStrip>控件不熟悉此版本的 Visual Studio 和.NET Framework。</span><span class="sxs-lookup"><span data-stu-id="407d3-104">The <xref:System.Windows.Forms.MenuStrip> control is new to this version of Visual Studio and the .NET Framework.</span></span> <span data-ttu-id="407d3-105">与该控件可以轻松创建如在 Microsoft Office 中找到的菜单。</span><span class="sxs-lookup"><span data-stu-id="407d3-105">With the control, you can easily create menus like those found in Microsoft Office.</span></span>  
  
 <span data-ttu-id="407d3-106"><xref:System.Windows.Forms.MenuStrip>控件支持多文档界面 (MDI) 和菜单合并功能、 工具提示和溢出。</span><span class="sxs-lookup"><span data-stu-id="407d3-106">The <xref:System.Windows.Forms.MenuStrip> control supports the multiple-document interface (MDI) and menu merging, tool tips, and overflow.</span></span> <span data-ttu-id="407d3-107">你可以通过添加访问密钥、 快捷键、 复选标记、 映像和分隔条增强的可用性和你菜单的可读性。</span><span class="sxs-lookup"><span data-stu-id="407d3-107">You can enhance the usability and readability of your menus by adding access keys, shortcut keys, check marks, images, and separator bars.</span></span>  
  
 <span data-ttu-id="407d3-108"><xref:System.Windows.Forms.MenuStrip>控件替换，并将功能添加到<xref:System.Windows.Forms.MainMenu>控制; 但是，<xref:System.Windows.Forms.MainMenu>可以选择保留向后兼容并供将来使用的控件。</span><span class="sxs-lookup"><span data-stu-id="407d3-108">The <xref:System.Windows.Forms.MenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.MainMenu> control; however, the <xref:System.Windows.Forms.MainMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
## <a name="ways-to-use-the-menustrip-control"></a><span data-ttu-id="407d3-109">如何使用 MenuStrip 控件</span><span class="sxs-lookup"><span data-stu-id="407d3-109">Ways to Use the MenuStrip Control</span></span>  
 <span data-ttu-id="407d3-110">使用<xref:System.Windows.Forms.MenuStrip>控制转移到：</span><span class="sxs-lookup"><span data-stu-id="407d3-110">Use the <xref:System.Windows.Forms.MenuStrip> control to:</span></span>  
  
-   <span data-ttu-id="407d3-111">创建轻松地自定义，支持的常用的菜单高级用户界面和布局功能，例如文本和图像排序和对齐方式、 拖放操作、 MDI、 溢出及访问菜单命令的备用模式。</span><span class="sxs-lookup"><span data-stu-id="407d3-111">Create easily customized, commonly employed menus that support advanced user interface and layout features, such as text and image ordering and alignment, drag-and-drop operations, MDI, overflow, and alternate modes of accessing menu commands.</span></span>  
  
-   <span data-ttu-id="407d3-112">支持的典型的外观和行为的操作系统。</span><span class="sxs-lookup"><span data-stu-id="407d3-112">Support the typical appearance and behavior of the operating system.</span></span>  
  
-   <span data-ttu-id="407d3-113">处理一致地为所有容器和包含的项的事件，将相同的方式处理其他控件的事件。</span><span class="sxs-lookup"><span data-stu-id="407d3-113">Handle events consistently for all containers and contained items, in the same way you handle events for other controls.</span></span>  
  
 <span data-ttu-id="407d3-114">下表显示的某些特别重要属性<xref:System.Windows.Forms.MenuStrip>和关联的类。</span><span class="sxs-lookup"><span data-stu-id="407d3-114">The following table shows some particularly important properties of <xref:System.Windows.Forms.MenuStrip> and associated classes.</span></span>  
  
|<span data-ttu-id="407d3-115">属性</span><span class="sxs-lookup"><span data-stu-id="407d3-115">Property</span></span>|<span data-ttu-id="407d3-116">描述</span><span class="sxs-lookup"><span data-stu-id="407d3-116">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|<span data-ttu-id="407d3-117">获取或设置<xref:System.Windows.Forms.ToolStripMenuItem>用于显示 MDI 子窗体的列表。</span><span class="sxs-lookup"><span data-stu-id="407d3-117">Gets or sets the <xref:System.Windows.Forms.ToolStripMenuItem> that is used to display a list of MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|<span data-ttu-id="407d3-118">获取或设置子菜单如何合并与 MDI 应用程序中的父菜单。</span><span class="sxs-lookup"><span data-stu-id="407d3-118">Gets or sets how child menus are merged with parent menus in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|<span data-ttu-id="407d3-119">获取或设置 MDI 应用程序中合并菜单中项的位置。</span><span class="sxs-lookup"><span data-stu-id="407d3-119">Gets or sets the position of a merged item within a menu in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|<span data-ttu-id="407d3-120">获取或设置一个值，该值指示窗体 MDI 子窗体的容器。</span><span class="sxs-lookup"><span data-stu-id="407d3-120">Gets or sets a value indicating whether the form is a container for MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|<span data-ttu-id="407d3-121">获取或设置一个值，该值指示是否显示工具提示<xref:System.Windows.Forms.MenuStrip>。</span><span class="sxs-lookup"><span data-stu-id="407d3-121">Gets or sets a value indicating whether tool tips are shown for the <xref:System.Windows.Forms.MenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|<span data-ttu-id="407d3-122">获取或设置一个值，该值指示 <xref:System.Windows.Forms.MenuStrip> 是否支持溢出功能。</span><span class="sxs-lookup"><span data-stu-id="407d3-122">Gets or sets a value indicating whether the <xref:System.Windows.Forms.MenuStrip> supports overflow functionality.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|<span data-ttu-id="407d3-123">获取或设置与关联的快捷键<xref:System.Windows.Forms.ToolStripMenuItem>。</span><span class="sxs-lookup"><span data-stu-id="407d3-123">Gets or sets the shortcut keys associated with the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|<span data-ttu-id="407d3-124">获取或设置一个值，该值是否快捷方式密钥与之关联<xref:System.Windows.Forms.ToolStripMenuItem>旁边显示<xref:System.Windows.Forms.ToolStripMenuItem>。</span><span class="sxs-lookup"><span data-stu-id="407d3-124">Gets or sets a value indicating whether the shortcut keys that are associated with the <xref:System.Windows.Forms.ToolStripMenuItem> are displayed next to the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
  
 <span data-ttu-id="407d3-125">下表显示了重要<xref:System.Windows.Forms.MenuStrip>伴生类。</span><span class="sxs-lookup"><span data-stu-id="407d3-125">The following table shows the important <xref:System.Windows.Forms.MenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="407d3-126">类</span><span class="sxs-lookup"><span data-stu-id="407d3-126">Class</span></span>|<span data-ttu-id="407d3-127">描述</span><span class="sxs-lookup"><span data-stu-id="407d3-127">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="407d3-128">表示上显示的可选选项<xref:System.Windows.Forms.MenuStrip>或<xref:System.Windows.Forms.ContextMenuStrip>。</span><span class="sxs-lookup"><span data-stu-id="407d3-128">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<span data-ttu-id="407d3-129">表示快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="407d3-129">Represents a shortcut menu.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="407d3-130">表示允许用户从在用户单击时显示的列表中选择单个项的控件<xref:System.Windows.Forms.ToolStripDropDownButton>或更高级别的菜单项。</span><span class="sxs-lookup"><span data-stu-id="407d3-130">Represents a control that allows the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="407d3-131">提供基本功能，为控件派生自<xref:System.Windows.Forms.ToolStripItem>显示单击时的下拉列表项。</span><span class="sxs-lookup"><span data-stu-id="407d3-131">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="407d3-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="407d3-132">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripDropDown>
