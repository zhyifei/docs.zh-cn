---
title: ToolStrip 控件概述
ms.date: 03/30/2017
f1_keywords:
- Toolstrip
helpviewer_keywords:
- ToolStrip control [Windows Forms], about ToolStrip control
- toolbars [Windows Forms], what's new in Windows Forms
- toolbars [Windows Forms]
- what's new [Windows Forms], toolbars
ms.assetid: 81d067ed-297c-4dad-90de-1bcac15336ec
ms.openlocfilehash: 931a6a0ea09f9b684b793c05cb1c3db8ee8fb7c7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741073"
---
# <a name="toolstrip-control-overview-windows-forms"></a><span data-ttu-id="77f3c-102">ToolStrip 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="77f3c-102">ToolStrip Control Overview (Windows Forms)</span></span>
<span data-ttu-id="77f3c-103">Windows 窗体 <xref:System.Windows.Forms.ToolStrip> 控件及其关联的类提供一个公共框架，用于将用户界面元素合并到工具栏、状态栏和菜单中。</span><span class="sxs-lookup"><span data-stu-id="77f3c-103">The Windows Forms <xref:System.Windows.Forms.ToolStrip> control and its associated classes provide a common framework for combining user interface elements into toolbars, status bars, and menus.</span></span> <span data-ttu-id="77f3c-104"><xref:System.Windows.Forms.ToolStrip> 控件提供丰富的设计时体验，其中包括就地激活和编辑、自定义布局和漂浮（这是工具栏共享水平或垂直空间的能力）。</span><span class="sxs-lookup"><span data-stu-id="77f3c-104"><xref:System.Windows.Forms.ToolStrip> controls offer a rich design-time experience that includes in-place activation and editing, custom layout, and rafting, which is the ability of toolbars to share horizontal or vertical space.</span></span>  
  
 <span data-ttu-id="77f3c-105">尽管 <xref:System.Windows.Forms.ToolStrip> 在早期版本中替换控件并添加功能，但如果需要，<xref:System.Windows.Forms.ToolBar> 会保留以实现向后兼容性和将来使用。</span><span class="sxs-lookup"><span data-stu-id="77f3c-105">Although <xref:System.Windows.Forms.ToolStrip> replaces and adds functionality to the control in previous versions, <xref:System.Windows.Forms.ToolBar> is retained for both backward compatibility and future use if desired.</span></span>  
  
## <a name="features-of-the-toolstrip-controls"></a><span data-ttu-id="77f3c-106">ToolStrip 控件的功能</span><span class="sxs-lookup"><span data-stu-id="77f3c-106">Features of the ToolStrip Controls</span></span>  
 <span data-ttu-id="77f3c-107">使用 <xref:System.Windows.Forms.ToolStrip> 控件可以：</span><span class="sxs-lookup"><span data-stu-id="77f3c-107">Use the <xref:System.Windows.Forms.ToolStrip> control to:</span></span>  
  
- <span data-ttu-id="77f3c-108">跨容器显示公共用户界面。</span><span class="sxs-lookup"><span data-stu-id="77f3c-108">Present a common user interface across containers.</span></span>  
  
- <span data-ttu-id="77f3c-109">创建可轻松自定义的常用工具栏，它们支持高级用户界面和布局功能，如停靠、漂浮、带有文本和图像的按钮、下拉按钮和控件、溢出按钮以及对 <xref:System.Windows.Forms.ToolStrip> 项的运行时重新排序。</span><span class="sxs-lookup"><span data-stu-id="77f3c-109">Create easily customized, commonly employed toolbars that support advanced user interface and layout features, such as docking, rafting, buttons with text and images, drop-down buttons and controls, overflow buttons, and run-time reordering of <xref:System.Windows.Forms.ToolStrip> items.</span></span>  
  
- <span data-ttu-id="77f3c-110">支持溢出和运行时项重新排序。</span><span class="sxs-lookup"><span data-stu-id="77f3c-110">Support overflow and run-time item reordering.</span></span> <span data-ttu-id="77f3c-111">当在 <xref:System.Windows.Forms.ToolStrip>中没有足够的空间来显示项时，溢出功能会将项移动到下拉菜单。</span><span class="sxs-lookup"><span data-stu-id="77f3c-111">The overflow feature moves items to a drop-down menu when there is not enough room to display them in a <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
- <span data-ttu-id="77f3c-112">通过常见的呈现模型支持操作系统的典型外观和行为。</span><span class="sxs-lookup"><span data-stu-id="77f3c-112">Support the typical appearance and behavior of the operating system through a common rendering model.</span></span>  
  
- <span data-ttu-id="77f3c-113">以一致的方式处理所有容器和包含项的事件，其方式与处理其他控件的事件的方式相同。</span><span class="sxs-lookup"><span data-stu-id="77f3c-113">Handle events consistently for all containers and contained items, in the same way you handle events for other controls.</span></span>  
  
- <span data-ttu-id="77f3c-114">将项从一个 <xref:System.Windows.Forms.ToolStrip> 拖动到另一个或 <xref:System.Windows.Forms.ToolStrip>中。</span><span class="sxs-lookup"><span data-stu-id="77f3c-114">Drag items from one <xref:System.Windows.Forms.ToolStrip> to another or within a <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
- <span data-ttu-id="77f3c-115">在 <xref:System.Windows.Forms.ToolStripDropDown>中创建具有高级布局的下拉控件和用户界面类型编辑器。</span><span class="sxs-lookup"><span data-stu-id="77f3c-115">Create drop-down controls and user interface type editors with advanced layouts in a <xref:System.Windows.Forms.ToolStripDropDown>.</span></span>  
  
 <span data-ttu-id="77f3c-116">使用 <xref:System.Windows.Forms.ToolStripControlHost> 类在 <xref:System.Windows.Forms.ToolStrip> 上使用其他控件，并为其获取 <xref:System.Windows.Forms.ToolStrip> 功能。</span><span class="sxs-lookup"><span data-stu-id="77f3c-116">Use the <xref:System.Windows.Forms.ToolStripControlHost> class to use other controls on a <xref:System.Windows.Forms.ToolStrip> and gain <xref:System.Windows.Forms.ToolStrip> functionality for them.</span></span>  
  
 <span data-ttu-id="77f3c-117">您可以使用 <xref:System.Windows.Forms.ToolStripRenderer>、<xref:System.Windows.Forms.ToolStripProfessionalRenderer>和 <xref:System.Windows.Forms.ToolStripManager> 以及 <xref:System.Windows.Forms.ToolStripRenderMode> 和 <xref:System.Windows.Forms.ToolStripManagerRenderMode> 枚举来扩展功能并修改外观和行为。</span><span class="sxs-lookup"><span data-stu-id="77f3c-117">You can extend the functionality and modify the appearance and behavior by using the <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, and <xref:System.Windows.Forms.ToolStripManager> along with the <xref:System.Windows.Forms.ToolStripRenderMode> and <xref:System.Windows.Forms.ToolStripManagerRenderMode> enumerations.</span></span>  
  
 <span data-ttu-id="77f3c-118"><xref:System.Windows.Forms.ToolStrip> 控件高度可配置且可扩展，并且提供了许多属性、方法和事件来自定义外观和行为。</span><span class="sxs-lookup"><span data-stu-id="77f3c-118">The <xref:System.Windows.Forms.ToolStrip> control is highly configurable and extensible, and it provides many properties, methods, and events to customize appearance and behavior.</span></span> <span data-ttu-id="77f3c-119">下面是一些值得注意的成员：</span><span class="sxs-lookup"><span data-stu-id="77f3c-119">Below are some noteworthy members:</span></span>  
  
### <a name="important-toolstrip-members"></a><span data-ttu-id="77f3c-120">重要 ToolStrip 成员</span><span class="sxs-lookup"><span data-stu-id="77f3c-120">Important ToolStrip Members</span></span>  
  
|<span data-ttu-id="77f3c-121">名称</span><span class="sxs-lookup"><span data-stu-id="77f3c-121">Name</span></span>|<span data-ttu-id="77f3c-122">说明</span><span class="sxs-lookup"><span data-stu-id="77f3c-122">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStrip.Dock%2A>|<span data-ttu-id="77f3c-123">获取或设置 <xref:System.Windows.Forms.ToolStrip> 停靠到的父容器的边缘。</span><span class="sxs-lookup"><span data-stu-id="77f3c-123">Gets or sets which edge of the parent container a <xref:System.Windows.Forms.ToolStrip> is docked to.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>|<span data-ttu-id="77f3c-124">获取或设置一个用于指示是否专门由 <xref:System.Windows.Forms.ToolStrip> 类处理拖放和项重新排序操作的值。</span><span class="sxs-lookup"><span data-stu-id="77f3c-124">Gets or sets a value indicating whether drag-and-drop and item reordering are handled privately by the <xref:System.Windows.Forms.ToolStrip> class.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>|<span data-ttu-id="77f3c-125">获取或设置一个值，该值指示 <xref:System.Windows.Forms.ToolStrip> 布局其项的方式。</span><span class="sxs-lookup"><span data-stu-id="77f3c-125">Gets or sets a value indicating how the <xref:System.Windows.Forms.ToolStrip> lays out its items.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>|<span data-ttu-id="77f3c-126">获取或设置 <xref:System.Windows.Forms.ToolStripItem> 是附加到 <xref:System.Windows.Forms.ToolStrip> 还是 <xref:System.Windows.Forms.ToolStripOverflowButton>，或者是否可以在这两个之间浮动。</span><span class="sxs-lookup"><span data-stu-id="77f3c-126">Gets or sets whether a <xref:System.Windows.Forms.ToolStripItem> is attached to the <xref:System.Windows.Forms.ToolStrip> or <xref:System.Windows.Forms.ToolStripOverflowButton> or can float between the two.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.IsDropDown%2A>|<span data-ttu-id="77f3c-127">获取一个值，该值指示在单击 <xref:System.Windows.Forms.ToolStripItem> 时，<xref:System.Windows.Forms.ToolStripItem> 是否显示下拉列表中的其他项。</span><span class="sxs-lookup"><span data-stu-id="77f3c-127">Gets a value indicating whether a <xref:System.Windows.Forms.ToolStripItem> displays other items in a drop-down list when the <xref:System.Windows.Forms.ToolStripItem> is clicked.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.OverflowButton%2A>|<span data-ttu-id="77f3c-128">获取 <xref:System.Windows.Forms.ToolStripItem>，它是启用了溢出的 <xref:System.Windows.Forms.ToolStrip> 的“溢出”按钮。</span><span class="sxs-lookup"><span data-stu-id="77f3c-128">Gets the <xref:System.Windows.Forms.ToolStripItem> that is the overflow button for a <xref:System.Windows.Forms.ToolStrip> with overflow enabled.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.Renderer%2A>|<span data-ttu-id="77f3c-129">获取或设置用于自定义 <xref:System.Windows.Forms.ToolStrip>的外观和行为（外观）的 <xref:System.Windows.Forms.ToolStripRenderer>。</span><span class="sxs-lookup"><span data-stu-id="77f3c-129">Gets or sets a <xref:System.Windows.Forms.ToolStripRenderer> used to customize the appearance and behavior (look and feel) of a <xref:System.Windows.Forms.ToolStrip>.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>|<span data-ttu-id="77f3c-130">获取或设置要应用于 <xref:System.Windows.Forms.ToolStrip> 的绘制样式。</span><span class="sxs-lookup"><span data-stu-id="77f3c-130">Gets or sets the painting styles to be applied to the <xref:System.Windows.Forms.ToolStrip>.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.RendererChanged>|<span data-ttu-id="77f3c-131">在 <xref:System.Windows.Forms.ToolStrip.Renderer%2A> 属性更改时引发。</span><span class="sxs-lookup"><span data-stu-id="77f3c-131">Raised when the <xref:System.Windows.Forms.ToolStrip.Renderer%2A> property changes.</span></span>|  
  
 <span data-ttu-id="77f3c-132">通过使用多个伴生类来实现 <xref:System.Windows.Forms.ToolStrip> 控件的灵活性。</span><span class="sxs-lookup"><span data-stu-id="77f3c-132">The <xref:System.Windows.Forms.ToolStrip> control's flexibility is achieved through the use of a number of companion classes.</span></span> <span data-ttu-id="77f3c-133">下面是一些最值得注意的事项：</span><span class="sxs-lookup"><span data-stu-id="77f3c-133">Below are some of the most noteworthy:</span></span>  
  
### <a name="important-toolstrip-companion-classes"></a><span data-ttu-id="77f3c-134">重要的 ToolStrip 伴生类</span><span class="sxs-lookup"><span data-stu-id="77f3c-134">Important ToolStrip Companion Classes</span></span>  
  
|<span data-ttu-id="77f3c-135">名称</span><span class="sxs-lookup"><span data-stu-id="77f3c-135">Name</span></span>|<span data-ttu-id="77f3c-136">说明</span><span class="sxs-lookup"><span data-stu-id="77f3c-136">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip>|<span data-ttu-id="77f3c-137">替换 <xref:System.Windows.Forms.MainMenu> 类并向其中添加功能。</span><span class="sxs-lookup"><span data-stu-id="77f3c-137">Replaces and adds functionality to the <xref:System.Windows.Forms.MainMenu> class.</span></span>|  
|<xref:System.Windows.Forms.StatusStrip>|<span data-ttu-id="77f3c-138">替换 <xref:System.Windows.Forms.StatusBar> 类并向其中添加功能。</span><span class="sxs-lookup"><span data-stu-id="77f3c-138">Replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> class.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<span data-ttu-id="77f3c-139">替换 <xref:System.Windows.Forms.ContextMenu> 类并向其中添加功能。</span><span class="sxs-lookup"><span data-stu-id="77f3c-139">Replaces and adds functionality to the <xref:System.Windows.Forms.ContextMenu> class.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem>|<span data-ttu-id="77f3c-140">用于管理 <xref:System.Windows.Forms.ToolStrip>、<xref:System.Windows.Forms.ToolStripControlHost>或 <xref:System.Windows.Forms.ToolStripDropDown> 可以包含的所有元素的事件和布局的抽象基类。</span><span class="sxs-lookup"><span data-stu-id="77f3c-140">Abstract base class that manages events and layout for all the elements that a <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripControlHost>, or <xref:System.Windows.Forms.ToolStripDropDown> can contain.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer>|<span data-ttu-id="77f3c-141">提供一个容器，该容器在窗体的每一侧有一个面板，可通过多种方式排列控件。</span><span class="sxs-lookup"><span data-stu-id="77f3c-141">Provides a container with a panel on each side of the form in which controls can be arranged in various ways.</span></span>|  
|<xref:System.Windows.Forms.ToolStripRenderer>|<span data-ttu-id="77f3c-142">处理 <xref:System.Windows.Forms.ToolStrip> 对象的绘制功能。</span><span class="sxs-lookup"><span data-stu-id="77f3c-142">Handles the painting functionality for <xref:System.Windows.Forms.ToolStrip> objects.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProfessionalRenderer>|<span data-ttu-id="77f3c-143">提供 Microsoft Office 样式的外观。</span><span class="sxs-lookup"><span data-stu-id="77f3c-143">Provides Microsoft Office-style appearance.</span></span>|  
|<xref:System.Windows.Forms.ToolStripManager>|<span data-ttu-id="77f3c-144">控制 <xref:System.Windows.Forms.ToolStrip> 的呈现和漂浮，以及 <xref:System.Windows.Forms.MenuStrip>、<xref:System.Windows.Forms.ToolStripDropDownMenu> 和 <xref:System.Windows.Forms.ToolStripMenuItem> 对象的合并。</span><span class="sxs-lookup"><span data-stu-id="77f3c-144">Controls <xref:System.Windows.Forms.ToolStrip> rendering and rafting, and the merging of <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu>, and <xref:System.Windows.Forms.ToolStripMenuItem> objects.</span></span>|  
|<xref:System.Windows.Forms.ToolStripManagerRenderMode>|<span data-ttu-id="77f3c-145">指定应用于窗体中包含的多个 <xref:System.Windows.Forms.ToolStrip> 对象的绘制样式（自定义、Windows XP 或 Microsoft Office 专业版）。</span><span class="sxs-lookup"><span data-stu-id="77f3c-145">Specifies the painting style (custom, Windows XP, or Microsoft Office Professional) applied to multiple <xref:System.Windows.Forms.ToolStrip> objects contained in a form.</span></span>|  
|<xref:System.Windows.Forms.ToolStripRenderMode>|<span data-ttu-id="77f3c-146">指定应用于窗体中包含的一个 <xref:System.Windows.Forms.ToolStrip> 对象的绘制样式（自定义、Windows XP 或 Microsoft Office 专业版）。</span><span class="sxs-lookup"><span data-stu-id="77f3c-146">Specifies the painting style (custom, Windows XP, or Microsoft Office Professional) applied to one <xref:System.Windows.Forms.ToolStrip> object contained in a form.</span></span>|  
|<xref:System.Windows.Forms.ToolStripControlHost>|<span data-ttu-id="77f3c-147">承载并非专门 <xref:System.Windows.Forms.ToolStrip> 控件但要 <xref:System.Windows.Forms.ToolStrip> 功能的其他控件。</span><span class="sxs-lookup"><span data-stu-id="77f3c-147">Hosts other controls that are not specifically <xref:System.Windows.Forms.ToolStrip> controls but for which you want <xref:System.Windows.Forms.ToolStrip> functionality.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItemPlacement>|<span data-ttu-id="77f3c-148">指定是在主 <xref:System.Windows.Forms.ToolStrip>上、在溢出 <xref:System.Windows.Forms.ToolStrip>上布局 <xref:System.Windows.Forms.ToolStripItem>，还是两者都是。</span><span class="sxs-lookup"><span data-stu-id="77f3c-148">Specifies whether a <xref:System.Windows.Forms.ToolStripItem> is to be laid out on the main <xref:System.Windows.Forms.ToolStrip>, on the overflow <xref:System.Windows.Forms.ToolStrip>, or neither.</span></span>|  
  
 <span data-ttu-id="77f3c-149">有关详细信息，请参阅[Toolstrip 技术摘要](toolstrip-technology-summary.md)和[Toolstrip 控件体系结构](toolstrip-control-architecture.md)。</span><span class="sxs-lookup"><span data-stu-id="77f3c-149">For more information, see [ToolStrip Technology Summary](toolstrip-technology-summary.md) and [ToolStrip Control Architecture](toolstrip-control-architecture.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77f3c-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77f3c-150">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
