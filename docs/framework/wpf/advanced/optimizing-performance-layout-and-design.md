---
title: 优化性能：布局和设计
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- layout [WPF], optimizing performance
- design considerations [WPF]
- layout pass [WPF]
ms.assetid: 005f4cda-a849-448b-916b-38d14d9a96fe
ms.openlocfilehash: c5dd567fa9f5db69c52072a1cc67b5c574f8e1f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623867"
---
# <a name="optimizing-performance-layout-and-design"></a><span data-ttu-id="10a0a-102">优化性能：布局和设计</span><span class="sxs-lookup"><span data-stu-id="10a0a-102">Optimizing Performance: Layout and Design</span></span>
<span data-ttu-id="10a0a-103">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序的设计在计算布局和验证对象引用时会产生不必要的开销，从而影响性能。</span><span class="sxs-lookup"><span data-stu-id="10a0a-103">The design of your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application can impact its performance by creating unnecessary overhead in calculating layout and validating object references.</span></span> <span data-ttu-id="10a0a-104">对象的构造会影响应用程序的性能特征，在运行时更是如此。</span><span class="sxs-lookup"><span data-stu-id="10a0a-104">The construction of objects, particularly at run time, can affect the performance characteristics of your application.</span></span>  
  
 <span data-ttu-id="10a0a-105">本主题提供这些方面的性能改进建议。</span><span class="sxs-lookup"><span data-stu-id="10a0a-105">This topic provides performance recommendations in these areas.</span></span>  
  
## <a name="layout"></a><span data-ttu-id="10a0a-106">布局</span><span class="sxs-lookup"><span data-stu-id="10a0a-106">Layout</span></span>  
 <span data-ttu-id="10a0a-107">"布局处理过程"一词描述测量和排列的成员的过程<xref:System.Windows.Controls.Panel>-派生的子级，并在其中绘制它们在屏幕上的对象的集合。</span><span class="sxs-lookup"><span data-stu-id="10a0a-107">The term "layout pass" describes the process of measuring and arranging the members of a <xref:System.Windows.Controls.Panel>-derived object's collection of children, and then drawing them onscreen.</span></span> <span data-ttu-id="10a0a-108">布局处理过程是一个数学密集型过程，即：集合中的子级数目越多，所需的计算量就越大。</span><span class="sxs-lookup"><span data-stu-id="10a0a-108">The layout pass is a mathematically-intensive process—the larger the number of children in the collection, the greater the number of calculations required.</span></span> <span data-ttu-id="10a0a-109">例如，每次子<xref:System.Windows.UIElement>集合中的对象改变其位置，它可能触发一个新的布局系统传递。</span><span class="sxs-lookup"><span data-stu-id="10a0a-109">For example, each time a child <xref:System.Windows.UIElement> object in the collection changes its position, it has the potential to trigger a new pass by the layout system.</span></span> <span data-ttu-id="10a0a-110">由于对象特征与布局行为之间的关系非常紧密，因此有必要了解可以调用布局系统的事件类型。</span><span class="sxs-lookup"><span data-stu-id="10a0a-110">Because of the close relationship between object characteristics and layout behavior, it's important to understand the type of events that can invoke the layout system.</span></span> <span data-ttu-id="10a0a-111">应用程序将尽可能减少不必要的布局处理过程调用，从而改善性能。</span><span class="sxs-lookup"><span data-stu-id="10a0a-111">Your application will perform better by reducing as much as possible any unnecessary invocations of the layout pass.</span></span>  
  
 <span data-ttu-id="10a0a-112">布局系统对集合中的每个子成员都完成两个处理过程：测量处理过程和排列处理过程。</span><span class="sxs-lookup"><span data-stu-id="10a0a-112">The layout system completes two passes for each child member in a collection: a measure pass, and an arrange pass.</span></span> <span data-ttu-id="10a0a-113">每个子对象提供了自己的重写的实现<xref:System.Windows.UIElement.Measure%2A>和<xref:System.Windows.UIElement.Arrange%2A>方法中，以便提供其自己特定的布局行为。</span><span class="sxs-lookup"><span data-stu-id="10a0a-113">Each child object provides its own overridden implementation of the <xref:System.Windows.UIElement.Measure%2A> and <xref:System.Windows.UIElement.Arrange%2A> methods in order to provide its own specific layout behavior.</span></span> <span data-ttu-id="10a0a-114">简单地说，布局是一个递归系统，实现在屏幕上对元素进行大小调整、定位和绘制。</span><span class="sxs-lookup"><span data-stu-id="10a0a-114">At its simplest, layout is a recursive system that leads to an element being sized, positioned, and drawn onscreen.</span></span>  
  
-   <span data-ttu-id="10a0a-115">子<xref:System.Windows.UIElement>对象通过首先测量其核心属性来开始布局过程。</span><span class="sxs-lookup"><span data-stu-id="10a0a-115">A child <xref:System.Windows.UIElement> object begins the layout process by first having its core properties measured.</span></span>  
  
-   <span data-ttu-id="10a0a-116">对象的<xref:System.Windows.FrameworkElement>属性与大小，如<xref:System.Windows.FrameworkElement.Width%2A>， <xref:System.Windows.FrameworkElement.Height%2A>，和<xref:System.Windows.FrameworkElement.Margin%2A>，进行计算。</span><span class="sxs-lookup"><span data-stu-id="10a0a-116">The object's <xref:System.Windows.FrameworkElement> properties that are related to size, such as <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, and <xref:System.Windows.FrameworkElement.Margin%2A>, are evaluated.</span></span>  
  
-   <span data-ttu-id="10a0a-117"><xref:System.Windows.Controls.Panel>-应用特定的逻辑，如<xref:System.Windows.Controls.DockPanel.Dock%2A>的属性<xref:System.Windows.Controls.DockPanel>，或<xref:System.Windows.Controls.StackPanel.Orientation%2A>属性的<xref:System.Windows.Controls.StackPanel>。</span><span class="sxs-lookup"><span data-stu-id="10a0a-117"><xref:System.Windows.Controls.Panel>-specific logic is applied, such as the <xref:System.Windows.Controls.DockPanel.Dock%2A> property of the <xref:System.Windows.Controls.DockPanel>, or the <xref:System.Windows.Controls.StackPanel.Orientation%2A> property of the <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
-   <span data-ttu-id="10a0a-118">在测量所有的子对象后，将排列或定位内容。</span><span class="sxs-lookup"><span data-stu-id="10a0a-118">Content is arranged, or positioned, after all child objects have been measured.</span></span>  
  
-   <span data-ttu-id="10a0a-119">将子对象集合绘制到屏幕上。</span><span class="sxs-lookup"><span data-stu-id="10a0a-119">The collection of child objects is drawn to the screen.</span></span>  
  
 <span data-ttu-id="10a0a-120">如果发生下列任一操作，将再次调用布局处理过程：</span><span class="sxs-lookup"><span data-stu-id="10a0a-120">The layout pass process is invoked again if any of the following actions occur:</span></span>  
  
-   <span data-ttu-id="10a0a-121">向集合中添加了一个子对象。</span><span class="sxs-lookup"><span data-stu-id="10a0a-121">A child object is added to the collection.</span></span>  
  
-   <span data-ttu-id="10a0a-122">一个<xref:System.Windows.FrameworkElement.LayoutTransform%2A>应用到子对象。</span><span class="sxs-lookup"><span data-stu-id="10a0a-122">A <xref:System.Windows.FrameworkElement.LayoutTransform%2A> is applied to the child object.</span></span>  
  
-   <span data-ttu-id="10a0a-123"><xref:System.Windows.UIElement.UpdateLayout%2A>为子对象调用方法。</span><span class="sxs-lookup"><span data-stu-id="10a0a-123">The <xref:System.Windows.UIElement.UpdateLayout%2A> method is called for the child object.</span></span>  
  
-   <span data-ttu-id="10a0a-124">使用影响测量或排列过程的元数据进行标记的依赖属性的值发生更改时。</span><span class="sxs-lookup"><span data-stu-id="10a0a-124">When a change occurs to the value of a dependency property that is marked with metadata affecting the measure or arrange passes.</span></span>  
  
### <a name="use-the-most-efficient-panel-where-possible"></a><span data-ttu-id="10a0a-125">尽可能使用最高效的面板</span><span class="sxs-lookup"><span data-stu-id="10a0a-125">Use the Most Efficient Panel where Possible</span></span>  
 <span data-ttu-id="10a0a-126">布局过程的复杂性直接取决于的布局行为<xref:System.Windows.Controls.Panel>-派生您使用的元素。</span><span class="sxs-lookup"><span data-stu-id="10a0a-126">The complexity of the layout process is directly based on the layout behavior of the <xref:System.Windows.Controls.Panel>-derived elements you use.</span></span> <span data-ttu-id="10a0a-127">例如，<xref:System.Windows.Controls.Grid>或<xref:System.Windows.Controls.StackPanel>控件提供了更多的功能比<xref:System.Windows.Controls.Canvas>控件。</span><span class="sxs-lookup"><span data-stu-id="10a0a-127">For example, a <xref:System.Windows.Controls.Grid> or <xref:System.Windows.Controls.StackPanel> control provides much more functionality than a <xref:System.Windows.Controls.Canvas> control.</span></span> <span data-ttu-id="10a0a-128">功能大幅度改进的代价是性能成本的大幅度提高。</span><span class="sxs-lookup"><span data-stu-id="10a0a-128">The price for this greater increase in functionality is a greater increase in performance costs.</span></span> <span data-ttu-id="10a0a-129">但是，如果您不需要的功能，<xref:System.Windows.Controls.Grid>控件提供了应使用成本较低的替代方法，如<xref:System.Windows.Controls.Canvas>或自定义面板。</span><span class="sxs-lookup"><span data-stu-id="10a0a-129">However, if you do not require the functionality that a <xref:System.Windows.Controls.Grid> control provides, you should use the less costly alternatives, such as a <xref:System.Windows.Controls.Canvas> or a custom panel.</span></span>  
  
 <span data-ttu-id="10a0a-130">有关详细信息，请参阅[面板概述](../../../../docs/framework/wpf/controls/panels-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="10a0a-130">For more information, see [Panels Overview](../../../../docs/framework/wpf/controls/panels-overview.md).</span></span>  
  
### <a name="update-rather-than-replace-a-rendertransform"></a><span data-ttu-id="10a0a-131">更新而不替换 RenderTransform</span><span class="sxs-lookup"><span data-stu-id="10a0a-131">Update Rather than Replace a RenderTransform</span></span>  
 <span data-ttu-id="10a0a-132">您可能无法在更新<xref:System.Windows.Media.Transform>而不是替换的值作为<xref:System.Windows.UIElement.RenderTransform%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="10a0a-132">You may be able to update a <xref:System.Windows.Media.Transform> rather than replacing it as the value of a <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span> <span data-ttu-id="10a0a-133">在涉及动画的方案中，尤其是这样。</span><span class="sxs-lookup"><span data-stu-id="10a0a-133">This is particularly true in scenarios that involve animation.</span></span> <span data-ttu-id="10a0a-134">通过更新现有<xref:System.Windows.Media.Transform>，可以避免启动不需要的布局计算。</span><span class="sxs-lookup"><span data-stu-id="10a0a-134">By updating an existing <xref:System.Windows.Media.Transform>, you avoid initiating an unnecessary layout calculation.</span></span>  
  
### <a name="build-your-tree-top-down"></a><span data-ttu-id="10a0a-135">从上到下生成树</span><span class="sxs-lookup"><span data-stu-id="10a0a-135">Build Your Tree Top-Down</span></span>  
 <span data-ttu-id="10a0a-136">在逻辑树中添加或删除节点时，会在该节点的父级及其所有子级上引起属性失效。</span><span class="sxs-lookup"><span data-stu-id="10a0a-136">When a node is added or removed from the logical tree, property invalidations are raised on the node's parent and all its children.</span></span> <span data-ttu-id="10a0a-137">因此，应始终遵循从上到下的构造模式，以避免由于在经过验证的节点中出现不必要的失效而付出代价。</span><span class="sxs-lookup"><span data-stu-id="10a0a-137">As a result, a top-down construction pattern should always be followed to avoid the cost of unnecessary invalidations on nodes that have already been validated.</span></span> <span data-ttu-id="10a0a-138">下表显示了执行速度之间构建树自上而下与自下而上，其中树有 150 级深与单个差异<xref:System.Windows.Controls.TextBlock>和<xref:System.Windows.Controls.DockPanel>每个级别。</span><span class="sxs-lookup"><span data-stu-id="10a0a-138">The following table shows the difference in execution speed between building a tree top-down versus bottom-up, where the tree is 150 levels deep with a single <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Controls.DockPanel> at each level.</span></span>  
  
|<span data-ttu-id="10a0a-139">**操作**</span><span class="sxs-lookup"><span data-stu-id="10a0a-139">**Action**</span></span>|<span data-ttu-id="10a0a-140">**构建树（以毫秒为单位）**</span><span class="sxs-lookup"><span data-stu-id="10a0a-140">**Tree building (in ms)**</span></span>|<span data-ttu-id="10a0a-141">**呈现 - 包括生成树（以毫秒为单位）**</span><span class="sxs-lookup"><span data-stu-id="10a0a-141">**Render—includes tree building (in ms)**</span></span>|  
|----------------|---------------------------------|-------------------------------------------------|  
|<span data-ttu-id="10a0a-142">从下到上</span><span class="sxs-lookup"><span data-stu-id="10a0a-142">Bottom-up</span></span>|<span data-ttu-id="10a0a-143">366</span><span class="sxs-lookup"><span data-stu-id="10a0a-143">366</span></span>|<span data-ttu-id="10a0a-144">454</span><span class="sxs-lookup"><span data-stu-id="10a0a-144">454</span></span>|  
|<span data-ttu-id="10a0a-145">从上到下</span><span class="sxs-lookup"><span data-stu-id="10a0a-145">Top-down</span></span>|<span data-ttu-id="10a0a-146">11</span><span class="sxs-lookup"><span data-stu-id="10a0a-146">11</span></span>|<span data-ttu-id="10a0a-147">96</span><span class="sxs-lookup"><span data-stu-id="10a0a-147">96</span></span>|  
  
 <span data-ttu-id="10a0a-148">以下代码示例演示如何从上到下创建树。</span><span class="sxs-lookup"><span data-stu-id="10a0a-148">The following code example demonstrates how to create a tree top down.</span></span>  
  
 [!code-csharp[Performance#PerformanceSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet1)]
 [!code-vb[Performance#PerformanceSnippet1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet1)]  
  
 <span data-ttu-id="10a0a-149">有关逻辑树的详细信息，请参阅 [WPF 中的树](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="10a0a-149">For more information on the logical tree, see [Trees in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10a0a-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="10a0a-150">See also</span></span>
- [<span data-ttu-id="10a0a-151">优化 WPF 应用程序性能</span><span class="sxs-lookup"><span data-stu-id="10a0a-151">Optimizing WPF Application Performance</span></span>](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)
- [<span data-ttu-id="10a0a-152">规划应用程序性能</span><span class="sxs-lookup"><span data-stu-id="10a0a-152">Planning for Application Performance</span></span>](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)
- [<span data-ttu-id="10a0a-153">利用硬件</span><span class="sxs-lookup"><span data-stu-id="10a0a-153">Taking Advantage of Hardware</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)
- [<span data-ttu-id="10a0a-154">2D 图形和图像处理</span><span class="sxs-lookup"><span data-stu-id="10a0a-154">2D Graphics and Imaging</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="10a0a-155">对象行为</span><span class="sxs-lookup"><span data-stu-id="10a0a-155">Object Behavior</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)
- [<span data-ttu-id="10a0a-156">应用程序资源</span><span class="sxs-lookup"><span data-stu-id="10a0a-156">Application Resources</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)
- [<span data-ttu-id="10a0a-157">文本</span><span class="sxs-lookup"><span data-stu-id="10a0a-157">Text</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)
- [<span data-ttu-id="10a0a-158">数据绑定</span><span class="sxs-lookup"><span data-stu-id="10a0a-158">Data Binding</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)
- [<span data-ttu-id="10a0a-159">其他性能建议</span><span class="sxs-lookup"><span data-stu-id="10a0a-159">Other Performance Recommendations</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
- [<span data-ttu-id="10a0a-160">布局</span><span class="sxs-lookup"><span data-stu-id="10a0a-160">Layout</span></span>](../../../../docs/framework/wpf/advanced/layout.md)
