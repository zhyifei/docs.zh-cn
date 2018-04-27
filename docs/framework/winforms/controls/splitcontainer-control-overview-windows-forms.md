---
title: SplitContainer 控件概述（Windows 窗体）
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SplitContainer
helpviewer_keywords:
- SplitContainer control [Windows Forms], about SplitContainer control
ms.assetid: 6de5a5f7-97a5-402d-be6d-7e2785483db5
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a553ea1b6dae24b4a0c3bd169edccbd9b52c5203
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
# <a name="splitcontainer-control-overview-windows-forms"></a><span data-ttu-id="71007-102">SplitContainer 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="71007-102">SplitContainer Control Overview (Windows Forms)</span></span>
<span data-ttu-id="71007-103">Windows 窗体 <xref:System.Windows.Forms.SplitContainer> 控件可视为一个复合控件；它是由可移动条隔开的两个面板。</span><span class="sxs-lookup"><span data-stu-id="71007-103">The Windows Forms <xref:System.Windows.Forms.SplitContainer> control can be thought of as a composite; it is two panels separated by a movable bar.</span></span> <span data-ttu-id="71007-104">当鼠标指针位于条上方时，指针将改变形状以表示条可移动。</span><span class="sxs-lookup"><span data-stu-id="71007-104">When the mouse pointer is over the bar, the pointer changes shape to show that the bar is movable.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="71007-105">在**工具箱**，<xref:System.Windows.Forms.SplitContainer>控件替代<xref:System.Windows.Forms.Splitter>以前版本的 Visual Studio 中的控件。</span><span class="sxs-lookup"><span data-stu-id="71007-105">In the **Toolbox**, <xref:System.Windows.Forms.SplitContainer> control replaces the <xref:System.Windows.Forms.Splitter> control that was there in the previous version of Visual Studio.</span></span> <span data-ttu-id="71007-106">相较于 <xref:System.Windows.Forms.Splitter> 控件，优先选择 <xref:System.Windows.Forms.SplitContainer> 控件。</span><span class="sxs-lookup"><span data-stu-id="71007-106">The <xref:System.Windows.Forms.SplitContainer> control is much preferred over the <xref:System.Windows.Forms.Splitter> control.</span></span> <span data-ttu-id="71007-107"><xref:System.Windows.Forms.Splitter>类仍包含在[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]为了兼容现有应用程序，但我们强烈建议你使用<xref:System.Windows.Forms.SplitContainer>为新项目的控件。</span><span class="sxs-lookup"><span data-stu-id="71007-107">The <xref:System.Windows.Forms.Splitter> class is still included in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] for compatibility with existing applications, but we strongly encourage you to use the <xref:System.Windows.Forms.SplitContainer> control for new projects.</span></span>  
  
 <span data-ttu-id="71007-108">与<xref:System.Windows.Forms.SplitContainer>控件，你可以创建复杂的用户界面; 通常，在一个面板中的选项决定了另一个面板中显示哪些对象。</span><span class="sxs-lookup"><span data-stu-id="71007-108">With the <xref:System.Windows.Forms.SplitContainer> control, you can create complex user interfaces; often, a selection in one panel determines what objects are shown in the other panel.</span></span> <span data-ttu-id="71007-109">这种安排对于显示和浏览信息非常有效。</span><span class="sxs-lookup"><span data-stu-id="71007-109">This arrangement is very effective for displaying and browsing information.</span></span> <span data-ttu-id="71007-110">具有两个面板使你聚合等方面的信息并栏中或"splitter，"使用户可以方便地调整面板大小。</span><span class="sxs-lookup"><span data-stu-id="71007-110">Having two panels lets you aggregate information in areas, and the bar, or "splitter," makes it easy for users to resize the panels.</span></span>  
  
 <span data-ttu-id="71007-111">多个<xref:System.Windows.Forms.SplitContainer>控件也可以嵌套，与第二个<xref:System.Windows.Forms.SplitContainer>控件水平，放置创建顶部和底部面板。</span><span class="sxs-lookup"><span data-stu-id="71007-111">More than one <xref:System.Windows.Forms.SplitContainer> control can also be nested, with the second <xref:System.Windows.Forms.SplitContainer> control oriented horizontally, to create top and bottom panels.</span></span>  
  
 <span data-ttu-id="71007-112">请注意，<xref:System.Windows.Forms.SplitContainer>控件键盘访问默认情况下; 用户可以按箭头键在需要时移动拆分器<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>属性设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="71007-112">Be aware that the <xref:System.Windows.Forms.SplitContainer> control is keyboard-accessible by default; users can press the ARROW keys to move the splitter if the <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> property is set to `false`.</span></span>  
  
 <span data-ttu-id="71007-113"><xref:System.Windows.Forms.SplitContainer.Orientation%2A>属性<xref:System.Windows.Forms.SplitContainer>控件确定拆分器，而不是该控件本身的方向。</span><span class="sxs-lookup"><span data-stu-id="71007-113">The <xref:System.Windows.Forms.SplitContainer.Orientation%2A> property of the <xref:System.Windows.Forms.SplitContainer> control determines the direction of the splitter, not of the control itself.</span></span> <span data-ttu-id="71007-114">因此，此属性设置为<xref:System.Windows.Forms.Orientation.Vertical>，从顶部运行到下，创建左侧和右侧面板的拆分器。</span><span class="sxs-lookup"><span data-stu-id="71007-114">Hence, when this property is set to <xref:System.Windows.Forms.Orientation.Vertical>, the splitter runs from top to bottom, creating left and right panels.</span></span>  
  
 <span data-ttu-id="71007-115">此外，请注意，值<xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A>属性而异的值<xref:System.Windows.Forms.SplitContainer.Orientation%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="71007-115">Additionally, be aware that the value of the <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> property varies depending on the value of the <xref:System.Windows.Forms.SplitContainer.Orientation%2A> property.</span></span> <span data-ttu-id="71007-116">有关详细信息，请参阅<xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="71007-116">For more information, see <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> property.</span></span>  
  
 <span data-ttu-id="71007-117">你也可以限制的大小和移动<xref:System.Windows.Forms.SplitContainer>控件。</span><span class="sxs-lookup"><span data-stu-id="71007-117">You can also restrict the size and movement of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="71007-118"><xref:System.Windows.Forms.SplitContainer.FixedPanel%2A>属性确定哪个面板将保持相同的大小后<xref:System.Windows.Forms.SplitContainer>调整控件的与<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>属性确定是否可由键盘或鼠标移动拆分器。</span><span class="sxs-lookup"><span data-stu-id="71007-118">The <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> property determines which panel will remain the same size after the <xref:System.Windows.Forms.SplitContainer> control is resized, and the <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> property determines if the splitter is movable by the keyboard or mouse.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71007-119">即使<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>属性设置为`true`，拆分器可能仍以编程方式; 例如，通过移动<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="71007-119">Even if the <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> property is set to `true`, the splitter may still be moved programmatically; for example, by using the <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> property.</span></span>  
  
 <span data-ttu-id="71007-120">最后，每个面板<xref:System.Windows.Forms.SplitContainer>控件具有属性，以确定其各自的大小。</span><span class="sxs-lookup"><span data-stu-id="71007-120">Finally, each panel of the <xref:System.Windows.Forms.SplitContainer> control has properties to determine its individual size.</span></span>  
  
## <a name="commonly-used-properties-methods-and-events"></a><span data-ttu-id="71007-121">常用的属性、方法和事件</span><span class="sxs-lookup"><span data-stu-id="71007-121">Commonly Used Properties, Methods, and Events</span></span>  
  
|<span data-ttu-id="71007-122">名称</span><span class="sxs-lookup"><span data-stu-id="71007-122">Name</span></span>|<span data-ttu-id="71007-123">描述</span><span class="sxs-lookup"><span data-stu-id="71007-123">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="71007-124"><xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> 属性</span><span class="sxs-lookup"><span data-stu-id="71007-124"><xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> property</span></span>|<span data-ttu-id="71007-125">确定哪个面板将保持相同大小后<xref:System.Windows.Forms.SplitContainer>调整控件的。</span><span class="sxs-lookup"><span data-stu-id="71007-125">Determines which panel will remain the same size after the <xref:System.Windows.Forms.SplitContainer> control is resized.</span></span>|  
|<span data-ttu-id="71007-126"><xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 属性</span><span class="sxs-lookup"><span data-stu-id="71007-126"><xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> property</span></span>|<span data-ttu-id="71007-127">确定是否可以使用键盘或鼠标移动拆分器。</span><span class="sxs-lookup"><span data-stu-id="71007-127">Determines if the splitter can be moved with the keyboard or mouse.</span></span>|  
|<span data-ttu-id="71007-128"><xref:System.Windows.Forms.SplitContainer.Orientation%2A> 属性</span><span class="sxs-lookup"><span data-stu-id="71007-128"><xref:System.Windows.Forms.SplitContainer.Orientation%2A> property</span></span>|<span data-ttu-id="71007-129">确定是否垂直或水平排列拆分器。</span><span class="sxs-lookup"><span data-stu-id="71007-129">Determines if the splitter is arranged vertically or horizontally.</span></span>|  
|<span data-ttu-id="71007-130"><xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> 属性</span><span class="sxs-lookup"><span data-stu-id="71007-130"><xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> property</span></span>|<span data-ttu-id="71007-131">确定以到可移动拆分条从左侧或右上边缘像素为单位的距离。</span><span class="sxs-lookup"><span data-stu-id="71007-131">Determines the distance in pixels from the left or upper edge to the movable splitter bar.</span></span>|  
|<span data-ttu-id="71007-132"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> 属性</span><span class="sxs-lookup"><span data-stu-id="71007-132"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property</span></span>|<span data-ttu-id="71007-133">确定的最小距离，以像素为单位，用户可以移动拆分器。</span><span class="sxs-lookup"><span data-stu-id="71007-133">Determines the minimum distance, in pixels, that the splitter can be moved by the user.</span></span>|  
|<span data-ttu-id="71007-134"><xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A> 属性</span><span class="sxs-lookup"><span data-stu-id="71007-134"><xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A> property</span></span>|<span data-ttu-id="71007-135">确定的粗细，以像素为单位，拆分器。</span><span class="sxs-lookup"><span data-stu-id="71007-135">Determines the thickness, in pixels, of the splitter.</span></span>|  
|<span data-ttu-id="71007-136"><xref:System.Windows.Forms.SplitContainer.SplitterMoving>事件</span><span class="sxs-lookup"><span data-stu-id="71007-136"><xref:System.Windows.Forms.SplitContainer.SplitterMoving> event</span></span>|<span data-ttu-id="71007-137">当拆分器移动时发生。</span><span class="sxs-lookup"><span data-stu-id="71007-137">Occurs when the splitter is moving.</span></span>|  
|<span data-ttu-id="71007-138"><xref:System.Windows.Forms.SplitContainer.SplitterMoved>事件</span><span class="sxs-lookup"><span data-stu-id="71007-138"><xref:System.Windows.Forms.SplitContainer.SplitterMoved> event</span></span>|<span data-ttu-id="71007-139">当拆分器移动时发生。</span><span class="sxs-lookup"><span data-stu-id="71007-139">Occurs when the splitter has moved.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="71007-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="71007-140">See Also</span></span>  
 <xref:System.Windows.Forms.SplitContainer>  
 [<span data-ttu-id="71007-141">SplitContainer 控件</span><span class="sxs-lookup"><span data-stu-id="71007-141">SplitContainer Control</span></span>](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)  
 [<span data-ttu-id="71007-142">SplitContainer 控件示例</span><span class="sxs-lookup"><span data-stu-id="71007-142">SplitContainer Control Sample</span></span>](http://msdn.microsoft.com/library/9015fad0-7108-4d85-a83a-a72d038c4f65)
