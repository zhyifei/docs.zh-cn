---
title: ToolStrip 控件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- Toolstrip
helpviewer_keywords:
- ToolStrip control [Windows Forms], about ToolStrip control
- toolbars [Windows Forms], what's new in Windows Forms
- toolbars [Windows Forms]
- what's new [Windows Forms], toolbars
ms.assetid: 81d067ed-297c-4dad-90de-1bcac15336ec
ms.openlocfilehash: 3e532b040d3c7859220b7f73958b63e7208b988c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59144568"
---
# <a name="toolstrip-control-overview-windows-forms"></a><span data-ttu-id="5674f-102">ToolStrip 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="5674f-102">ToolStrip Control Overview (Windows Forms)</span></span>
<span data-ttu-id="5674f-103">Windows 窗体<xref:System.Windows.Forms.ToolStrip>控制和及其关联的类将用户界面元素组合到工具栏、 状态栏和菜单提供一个通用框架。</span><span class="sxs-lookup"><span data-stu-id="5674f-103">The Windows Forms <xref:System.Windows.Forms.ToolStrip> control and its associated classes provide a common framework for combining user interface elements into toolbars, status bars, and menus.</span></span> <span data-ttu-id="5674f-104"><xref:System.Windows.Forms.ToolStrip> 控件提供丰富的设计时体验，包括就地激活和编辑、 自定义布局和漂浮，即工具栏共享水平或垂直空间的能力。</span><span class="sxs-lookup"><span data-stu-id="5674f-104"><xref:System.Windows.Forms.ToolStrip> controls offer a rich design-time experience that includes in-place activation and editing, custom layout, and rafting, which is the ability of toolbars to share horizontal or vertical space.</span></span>  
  
 <span data-ttu-id="5674f-105">尽管<xref:System.Windows.Forms.ToolStrip>替换，并将功能添加到在上一版本中，控件<xref:System.Windows.Forms.ToolBar>如果需要保留向后兼容性和将来使用。</span><span class="sxs-lookup"><span data-stu-id="5674f-105">Although <xref:System.Windows.Forms.ToolStrip> replaces and adds functionality to the control in previous versions, <xref:System.Windows.Forms.ToolBar> is retained for both backward compatibility and future use if desired.</span></span>  
  
## <a name="features-of-the-toolstrip-controls"></a><span data-ttu-id="5674f-106">ToolStrip 控件的功能</span><span class="sxs-lookup"><span data-stu-id="5674f-106">Features of the ToolStrip Controls</span></span>  
 <span data-ttu-id="5674f-107">使用<xref:System.Windows.Forms.ToolStrip>控制转移到：</span><span class="sxs-lookup"><span data-stu-id="5674f-107">Use the <xref:System.Windows.Forms.ToolStrip> control to:</span></span>  
  
-   <span data-ttu-id="5674f-108">在容器中显示常见的用户界面。</span><span class="sxs-lookup"><span data-stu-id="5674f-108">Present a common user interface across containers.</span></span>  
  
-   <span data-ttu-id="5674f-109">创建轻松地自定义，支持的常用的工具栏高级用户界面和布局功能，例如使用文本和图像、 下拉按钮和控件停靠、 漂浮、 按钮、 溢出按钮和运行时重新排序<xref:System.Windows.Forms.ToolStrip>项。</span><span class="sxs-lookup"><span data-stu-id="5674f-109">Create easily customized, commonly employed toolbars that support advanced user interface and layout features, such as docking, rafting, buttons with text and images, drop-down buttons and controls, overflow buttons, and run-time reordering of <xref:System.Windows.Forms.ToolStrip> items.</span></span>  
  
-   <span data-ttu-id="5674f-110">支持溢出和运行时项重新排序。</span><span class="sxs-lookup"><span data-stu-id="5674f-110">Support overflow and run-time item reordering.</span></span> <span data-ttu-id="5674f-111">溢出功能将项目移动到下拉列表菜单时没有足够的空间来将它们显示在<xref:System.Windows.Forms.ToolStrip>。</span><span class="sxs-lookup"><span data-stu-id="5674f-111">The overflow feature moves items to a drop-down menu when there is not enough room to display them in a <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
-   <span data-ttu-id="5674f-112">支持的典型的外观和行为通过常见的呈现模型的操作系统。</span><span class="sxs-lookup"><span data-stu-id="5674f-112">Support the typical appearance and behavior of the operating system through a common rendering model.</span></span>  
  
-   <span data-ttu-id="5674f-113">与处理事件的其他控件相同的方式处理始终对所有容器和包含的项的事件。</span><span class="sxs-lookup"><span data-stu-id="5674f-113">Handle events consistently for all containers and contained items, in the same way you handle events for other controls.</span></span>  
  
-   <span data-ttu-id="5674f-114">将项从一个拖<xref:System.Windows.Forms.ToolStrip>到另一个中或在<xref:System.Windows.Forms.ToolStrip>。</span><span class="sxs-lookup"><span data-stu-id="5674f-114">Drag items from one <xref:System.Windows.Forms.ToolStrip> to another or within a <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
-   <span data-ttu-id="5674f-115">创建下拉列表控件和用户界面类型编辑器中的高级布局<xref:System.Windows.Forms.ToolStripDropDown>。</span><span class="sxs-lookup"><span data-stu-id="5674f-115">Create drop-down controls and user interface type editors with advanced layouts in a <xref:System.Windows.Forms.ToolStripDropDown>.</span></span>  
  
 <span data-ttu-id="5674f-116">使用<xref:System.Windows.Forms.ToolStripControlHost>类上使用其他控件<xref:System.Windows.Forms.ToolStrip>，并获得<xref:System.Windows.Forms.ToolStrip>为它们的功能。</span><span class="sxs-lookup"><span data-stu-id="5674f-116">Use the <xref:System.Windows.Forms.ToolStripControlHost> class to use other controls on a <xref:System.Windows.Forms.ToolStrip> and gain <xref:System.Windows.Forms.ToolStrip> functionality for them.</span></span>  
  
 <span data-ttu-id="5674f-117">可以扩展功能并使用修改的外观和行为<xref:System.Windows.Forms.ToolStripRenderer>， <xref:System.Windows.Forms.ToolStripProfessionalRenderer>，并<xref:System.Windows.Forms.ToolStripManager>连同<xref:System.Windows.Forms.ToolStripRenderMode>和<xref:System.Windows.Forms.ToolStripManagerRenderMode>枚举。</span><span class="sxs-lookup"><span data-stu-id="5674f-117">You can extend the functionality and modify the appearance and behavior by using the <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, and <xref:System.Windows.Forms.ToolStripManager> along with the <xref:System.Windows.Forms.ToolStripRenderMode> and <xref:System.Windows.Forms.ToolStripManagerRenderMode> enumerations.</span></span>  
  
 <span data-ttu-id="5674f-118"><xref:System.Windows.Forms.ToolStrip>控件是高度可配置且可扩展的并提供许多属性、 方法和事件，以自定义外观和行为。</span><span class="sxs-lookup"><span data-stu-id="5674f-118">The <xref:System.Windows.Forms.ToolStrip> control is highly configurable and extensible, and it provides many properties, methods, and events to customize appearance and behavior.</span></span> <span data-ttu-id="5674f-119">以下是一些值得注意的成员：</span><span class="sxs-lookup"><span data-stu-id="5674f-119">Below are some noteworthy members:</span></span>  
  
### <a name="important-toolstrip-members"></a><span data-ttu-id="5674f-120">重要 ToolStrip 成员</span><span class="sxs-lookup"><span data-stu-id="5674f-120">Important ToolStrip Members</span></span>  
  
|<span data-ttu-id="5674f-121">名称</span><span class="sxs-lookup"><span data-stu-id="5674f-121">Name</span></span>|<span data-ttu-id="5674f-122">描述</span><span class="sxs-lookup"><span data-stu-id="5674f-122">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStrip.Dock%2A>|<span data-ttu-id="5674f-123">获取或设置父容器的边缘<xref:System.Windows.Forms.ToolStrip>停靠。</span><span class="sxs-lookup"><span data-stu-id="5674f-123">Gets or sets which edge of the parent container a <xref:System.Windows.Forms.ToolStrip> is docked to.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>|<span data-ttu-id="5674f-124">获取或设置一个用于指示是否专门由 <xref:System.Windows.Forms.ToolStrip> 类处理拖放和项重新排序操作的值。</span><span class="sxs-lookup"><span data-stu-id="5674f-124">Gets or sets a value indicating whether drag-and-drop and item reordering are handled privately by the <xref:System.Windows.Forms.ToolStrip> class.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>|<span data-ttu-id="5674f-125">获取或设置一个值，该值指示如何<xref:System.Windows.Forms.ToolStrip>其项的布局。</span><span class="sxs-lookup"><span data-stu-id="5674f-125">Gets or sets a value indicating how the <xref:System.Windows.Forms.ToolStrip> lays out its items.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>|<span data-ttu-id="5674f-126">获取或设置是否<xref:System.Windows.Forms.ToolStripItem>附加到<xref:System.Windows.Forms.ToolStrip>或<xref:System.Windows.Forms.ToolStripOverflowButton>还是漂浮在两者之间。</span><span class="sxs-lookup"><span data-stu-id="5674f-126">Gets or sets whether a <xref:System.Windows.Forms.ToolStripItem> is attached to the <xref:System.Windows.Forms.ToolStrip> or <xref:System.Windows.Forms.ToolStripOverflowButton> or can float between the two.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.IsDropDown%2A>|<span data-ttu-id="5674f-127">获取一个值，该值指示是否<xref:System.Windows.Forms.ToolStripItem>下拉列表中显示的其他项列表时<xref:System.Windows.Forms.ToolStripItem>单击。</span><span class="sxs-lookup"><span data-stu-id="5674f-127">Gets a value indicating whether a <xref:System.Windows.Forms.ToolStripItem> displays other items in a drop-down list when the <xref:System.Windows.Forms.ToolStripItem> is clicked.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.OverflowButton%2A>|<span data-ttu-id="5674f-128">获取 <xref:System.Windows.Forms.ToolStripItem>，它是启用了溢出的 <xref:System.Windows.Forms.ToolStrip> 的“溢出”按钮。</span><span class="sxs-lookup"><span data-stu-id="5674f-128">Gets the <xref:System.Windows.Forms.ToolStripItem> that is the overflow button for a <xref:System.Windows.Forms.ToolStrip> with overflow enabled.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.Renderer%2A>|<span data-ttu-id="5674f-129">获取或设置<xref:System.Windows.Forms.ToolStripRenderer>用于自定义外观和行为 （外观和感受） <xref:System.Windows.Forms.ToolStrip>。</span><span class="sxs-lookup"><span data-stu-id="5674f-129">Gets or sets a <xref:System.Windows.Forms.ToolStripRenderer> used to customize the appearance and behavior (look and feel) of a <xref:System.Windows.Forms.ToolStrip>.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>|<span data-ttu-id="5674f-130">获取或设置要应用于的绘制样式<xref:System.Windows.Forms.ToolStrip>。</span><span class="sxs-lookup"><span data-stu-id="5674f-130">Gets or sets the painting styles to be applied to the <xref:System.Windows.Forms.ToolStrip>.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.RendererChanged>|<span data-ttu-id="5674f-131">在 <xref:System.Windows.Forms.ToolStrip.Renderer%2A> 属性更改时引发。</span><span class="sxs-lookup"><span data-stu-id="5674f-131">Raised when the <xref:System.Windows.Forms.ToolStrip.Renderer%2A> property changes.</span></span>|  
  
 <span data-ttu-id="5674f-132"><xref:System.Windows.Forms.ToolStrip>通过大量的伴生类使用实现控件的灵活性。</span><span class="sxs-lookup"><span data-stu-id="5674f-132">The <xref:System.Windows.Forms.ToolStrip> control's flexibility is achieved through the use of a number of companion classes.</span></span> <span data-ttu-id="5674f-133">下面是最值得注意的一些：</span><span class="sxs-lookup"><span data-stu-id="5674f-133">Below are some of the most noteworthy:</span></span>  
  
### <a name="important-toolstrip-companion-classes"></a><span data-ttu-id="5674f-134">重要 ToolStrip 伴生类</span><span class="sxs-lookup"><span data-stu-id="5674f-134">Important ToolStrip Companion Classes</span></span>  
  
|<span data-ttu-id="5674f-135">名称</span><span class="sxs-lookup"><span data-stu-id="5674f-135">Name</span></span>|<span data-ttu-id="5674f-136">描述</span><span class="sxs-lookup"><span data-stu-id="5674f-136">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip>|<span data-ttu-id="5674f-137">替换并添加了功能<xref:System.Windows.Forms.MainMenu>类。</span><span class="sxs-lookup"><span data-stu-id="5674f-137">Replaces and adds functionality to the <xref:System.Windows.Forms.MainMenu> class.</span></span>|  
|<xref:System.Windows.Forms.StatusStrip>|<span data-ttu-id="5674f-138">替换并添加了功能<xref:System.Windows.Forms.StatusBar>类。</span><span class="sxs-lookup"><span data-stu-id="5674f-138">Replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> class.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<span data-ttu-id="5674f-139">替换并添加了功能<xref:System.Windows.Forms.ContextMenu>类。</span><span class="sxs-lookup"><span data-stu-id="5674f-139">Replaces and adds functionality to the <xref:System.Windows.Forms.ContextMenu> class.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem>|<span data-ttu-id="5674f-140">抽象基类，用于管理事件和布局的所有元素的<xref:System.Windows.Forms.ToolStrip>， <xref:System.Windows.Forms.ToolStripControlHost>，或<xref:System.Windows.Forms.ToolStripDropDown>可以包含。</span><span class="sxs-lookup"><span data-stu-id="5674f-140">Abstract base class that manages events and layout for all the elements that a <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripControlHost>, or <xref:System.Windows.Forms.ToolStripDropDown> can contain.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer>|<span data-ttu-id="5674f-141">使用窗体以各种方式排列控件的每一侧面板提供容器。</span><span class="sxs-lookup"><span data-stu-id="5674f-141">Provides a container with a panel on each side of the form in which controls can be arranged in various ways.</span></span>|  
|<xref:System.Windows.Forms.ToolStripRenderer>|<span data-ttu-id="5674f-142">处理的绘制功能<xref:System.Windows.Forms.ToolStrip>对象。</span><span class="sxs-lookup"><span data-stu-id="5674f-142">Handles the painting functionality for <xref:System.Windows.Forms.ToolStrip> objects.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProfessionalRenderer>|<span data-ttu-id="5674f-143">提供 Microsoft Office 样式外观。</span><span class="sxs-lookup"><span data-stu-id="5674f-143">Provides Microsoft Office-style appearance.</span></span>|  
|<xref:System.Windows.Forms.ToolStripManager>|<span data-ttu-id="5674f-144">控件<xref:System.Windows.Forms.ToolStrip>呈现和漂浮，以及将合并<xref:System.Windows.Forms.MenuStrip>， <xref:System.Windows.Forms.ToolStripDropDownMenu>，和<xref:System.Windows.Forms.ToolStripMenuItem>对象。</span><span class="sxs-lookup"><span data-stu-id="5674f-144">Controls <xref:System.Windows.Forms.ToolStrip> rendering and rafting, and the merging of <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu>, and <xref:System.Windows.Forms.ToolStripMenuItem> objects.</span></span>|  
|<xref:System.Windows.Forms.ToolStripManagerRenderMode>|<span data-ttu-id="5674f-145">指定应用到多个的绘制样式 （自定义，Windows XP 或 Microsoft Office Professional）<xref:System.Windows.Forms.ToolStrip>窗体中包含的对象。</span><span class="sxs-lookup"><span data-stu-id="5674f-145">Specifies the painting style (custom, Windows XP, or Microsoft Office Professional) applied to multiple <xref:System.Windows.Forms.ToolStrip> objects contained in a form.</span></span>|  
|<xref:System.Windows.Forms.ToolStripRenderMode>|<span data-ttu-id="5674f-146">指定应用于一个的绘制样式 （自定义，Windows XP 或 Microsoft Office Professional）<xref:System.Windows.Forms.ToolStrip>窗体中包含的对象。</span><span class="sxs-lookup"><span data-stu-id="5674f-146">Specifies the painting style (custom, Windows XP, or Microsoft Office Professional) applied to one <xref:System.Windows.Forms.ToolStrip> object contained in a form.</span></span>|  
|<xref:System.Windows.Forms.ToolStripControlHost>|<span data-ttu-id="5674f-147">承载其他控件没有专门<xref:System.Windows.Forms.ToolStrip>控件，但要为其<xref:System.Windows.Forms.ToolStrip>功能。</span><span class="sxs-lookup"><span data-stu-id="5674f-147">Hosts other controls that are not specifically <xref:System.Windows.Forms.ToolStrip> controls but for which you want <xref:System.Windows.Forms.ToolStrip> functionality.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItemPlacement>|<span data-ttu-id="5674f-148">指定是否<xref:System.Windows.Forms.ToolStripItem>是在主要的分布方式<xref:System.Windows.Forms.ToolStrip>，在溢出<xref:System.Windows.Forms.ToolStrip>，或都不。</span><span class="sxs-lookup"><span data-stu-id="5674f-148">Specifies whether a <xref:System.Windows.Forms.ToolStripItem> is to be laid out on the main <xref:System.Windows.Forms.ToolStrip>, on the overflow <xref:System.Windows.Forms.ToolStrip>, or neither.</span></span>|  
  
 <span data-ttu-id="5674f-149">有关详细信息，请参阅[ToolStrip 技术摘要](toolstrip-technology-summary.md)并[ToolStrip 控件体系结构](toolstrip-control-architecture.md)。</span><span class="sxs-lookup"><span data-stu-id="5674f-149">For more information, see [ToolStrip Technology Summary](toolstrip-technology-summary.md) and [ToolStrip Control Architecture](toolstrip-control-architecture.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5674f-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="5674f-150">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
