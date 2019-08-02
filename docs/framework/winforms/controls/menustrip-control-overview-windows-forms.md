---
title: MenuStrip 控件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
ms.openlocfilehash: 46a3a25415db77ee261f5fb1c3bf114b2275a2d4
ms.sourcegitcommit: 8c6426a3d2adff5fbcbe1fed0f28eda718c15351
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/02/2019
ms.locfileid: "68733461"
---
# <a name="menustrip-control-overview-windows-forms"></a><span data-ttu-id="670cc-102">MenuStrip 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="670cc-102">MenuStrip Control Overview (Windows Forms)</span></span>
<span data-ttu-id="670cc-103">菜单通过保存按公共主题分组的命令向用户公开功能。</span><span class="sxs-lookup"><span data-stu-id="670cc-103">Menus expose functionality to your users by holding commands that are grouped by a common theme.</span></span>  
  
 <span data-ttu-id="670cc-104"><xref:System.Windows.Forms.MenuStrip>控件是在 .NET Framework 2.0 版中引入的。</span><span class="sxs-lookup"><span data-stu-id="670cc-104">The <xref:System.Windows.Forms.MenuStrip> control was introduced in version 2.0 of the .NET Framework.</span></span> <span data-ttu-id="670cc-105"><xref:System.Windows.Forms.MenuStrip>借助控件, 可以轻松创建菜单, 如 Microsoft Office 中找到的菜单。</span><span class="sxs-lookup"><span data-stu-id="670cc-105">With the <xref:System.Windows.Forms.MenuStrip> control, you can easily create menus like those found in Microsoft Office.</span></span>  
  
 <span data-ttu-id="670cc-106"><xref:System.Windows.Forms.MenuStrip>控件支持多文档界面 (MDI) 和菜单合并、工具提示和溢出。</span><span class="sxs-lookup"><span data-stu-id="670cc-106">The <xref:System.Windows.Forms.MenuStrip> control supports the multiple-document interface (MDI) and menu merging, tool tips, and overflow.</span></span> <span data-ttu-id="670cc-107">您可以通过添加访问键、快捷键、复选标记、图像和分隔栏来增强菜单的可用性和可读性。</span><span class="sxs-lookup"><span data-stu-id="670cc-107">You can enhance the usability and readability of your menus by adding access keys, shortcut keys, check marks, images, and separator bars.</span></span>  
  
 <span data-ttu-id="670cc-108">控件将替换并添加<xref:System.Windows.Forms.MainMenu>到<xref:System.Windows.Forms.MainMenu>控件中的功能; 但是, 会保留控件以实现向后兼容性和将来使用 (如果你选择)。 <xref:System.Windows.Forms.MenuStrip></span><span class="sxs-lookup"><span data-stu-id="670cc-108">The <xref:System.Windows.Forms.MenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.MainMenu> control; however, the <xref:System.Windows.Forms.MainMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
## <a name="ways-to-use-the-menustrip-control"></a><span data-ttu-id="670cc-109">使用 MenuStrip 控件的方式</span><span class="sxs-lookup"><span data-stu-id="670cc-109">Ways to Use the MenuStrip Control</span></span>  
 <span data-ttu-id="670cc-110"><xref:System.Windows.Forms.MenuStrip>使用控件可以:</span><span class="sxs-lookup"><span data-stu-id="670cc-110">Use the <xref:System.Windows.Forms.MenuStrip> control to:</span></span>  
  
- <span data-ttu-id="670cc-111">创建可轻松自定义的常用菜单, 这些菜单支持高级用户界面和布局功能, 如文本和图像顺序和对齐方式、拖放操作、MDI、溢出以及访问菜单命令的其他模式。</span><span class="sxs-lookup"><span data-stu-id="670cc-111">Create easily customized, commonly employed menus that support advanced user interface and layout features, such as text and image ordering and alignment, drag-and-drop operations, MDI, overflow, and alternate modes of accessing menu commands.</span></span>  
  
- <span data-ttu-id="670cc-112">支持操作系统的典型外观和行为。</span><span class="sxs-lookup"><span data-stu-id="670cc-112">Support the typical appearance and behavior of the operating system.</span></span>  
  
- <span data-ttu-id="670cc-113">以一致的方式处理所有容器和包含项的事件, 其方式与处理其他控件的事件的方式相同。</span><span class="sxs-lookup"><span data-stu-id="670cc-113">Handle events consistently for all containers and contained items, in the same way you handle events for other controls.</span></span>  
  
 <span data-ttu-id="670cc-114">下表显示了和关联类的一些<xref:System.Windows.Forms.MenuStrip>特别重要的属性。</span><span class="sxs-lookup"><span data-stu-id="670cc-114">The following table shows some particularly important properties of <xref:System.Windows.Forms.MenuStrip> and associated classes.</span></span>  
  
|<span data-ttu-id="670cc-115">Property</span><span class="sxs-lookup"><span data-stu-id="670cc-115">Property</span></span>|<span data-ttu-id="670cc-116">描述</span><span class="sxs-lookup"><span data-stu-id="670cc-116">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|<span data-ttu-id="670cc-117">获取或设置<xref:System.Windows.Forms.ToolStripMenuItem>用于显示 MDI 子窗体列表的。</span><span class="sxs-lookup"><span data-stu-id="670cc-117">Gets or sets the <xref:System.Windows.Forms.ToolStripMenuItem> that is used to display a list of MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|<span data-ttu-id="670cc-118">获取或设置如何在 MDI 应用程序中将子菜单与父菜单合并。</span><span class="sxs-lookup"><span data-stu-id="670cc-118">Gets or sets how child menus are merged with parent menus in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|<span data-ttu-id="670cc-119">获取或设置在 MDI 应用程序中的菜单内的合并项的位置。</span><span class="sxs-lookup"><span data-stu-id="670cc-119">Gets or sets the position of a merged item within a menu in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|<span data-ttu-id="670cc-120">获取或设置一个值, 该值指示窗体是否为 MDI 子窗体的容器。</span><span class="sxs-lookup"><span data-stu-id="670cc-120">Gets or sets a value indicating whether the form is a container for MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|<span data-ttu-id="670cc-121">获取或设置一个值, 该值指示是否显示<xref:System.Windows.Forms.MenuStrip>的工具提示。</span><span class="sxs-lookup"><span data-stu-id="670cc-121">Gets or sets a value indicating whether tool tips are shown for the <xref:System.Windows.Forms.MenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|<span data-ttu-id="670cc-122">获取或设置一个值，该值指示 <xref:System.Windows.Forms.MenuStrip> 是否支持溢出功能。</span><span class="sxs-lookup"><span data-stu-id="670cc-122">Gets or sets a value indicating whether the <xref:System.Windows.Forms.MenuStrip> supports overflow functionality.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|<span data-ttu-id="670cc-123">获取或设置与<xref:System.Windows.Forms.ToolStripMenuItem>关联的快捷键。</span><span class="sxs-lookup"><span data-stu-id="670cc-123">Gets or sets the shortcut keys associated with the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|<span data-ttu-id="670cc-124">获取或设置一个值, 该值指示与关联的<xref:System.Windows.Forms.ToolStripMenuItem>快捷键是否显示在旁边。 <xref:System.Windows.Forms.ToolStripMenuItem></span><span class="sxs-lookup"><span data-stu-id="670cc-124">Gets or sets a value indicating whether the shortcut keys that are associated with the <xref:System.Windows.Forms.ToolStripMenuItem> are displayed next to the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
  
 <span data-ttu-id="670cc-125">下表显示了重要<xref:System.Windows.Forms.MenuStrip>的伴生类。</span><span class="sxs-lookup"><span data-stu-id="670cc-125">The following table shows the important <xref:System.Windows.Forms.MenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="670cc-126">类</span><span class="sxs-lookup"><span data-stu-id="670cc-126">Class</span></span>|<span data-ttu-id="670cc-127">描述</span><span class="sxs-lookup"><span data-stu-id="670cc-127">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="670cc-128">表示在<xref:System.Windows.Forms.MenuStrip>或<xref:System.Windows.Forms.ContextMenuStrip>上显示的可选择选项。</span><span class="sxs-lookup"><span data-stu-id="670cc-128">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<span data-ttu-id="670cc-129">表示快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="670cc-129">Represents a shortcut menu.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="670cc-130">表示一个控件, 该控件允许用户从列表中选择单个项 (当用户单击<xref:System.Windows.Forms.ToolStripDropDownButton>或更高级别菜单项时显示)。</span><span class="sxs-lookup"><span data-stu-id="670cc-130">Represents a control that allows the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="670cc-131">为在单击时显示<xref:System.Windows.Forms.ToolStripItem>的下拉项的控件提供基本功能。</span><span class="sxs-lookup"><span data-stu-id="670cc-131">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="670cc-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="670cc-132">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
