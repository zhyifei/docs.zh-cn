---
title: "墨迹线程处理模型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application user interface thread [WPF]
- stylus plug-in
- ink threading model [WPF]
- ink [WPF], rendering
- pen thread [WPF]
- threading model [WPF]
- rendering ink [WPF]
- dynamic rendering thread [WPF]
- ink collection plug-in
- plug-ins [WPF], for ink
ms.assetid: c85fcad1-cb50-4431-847c-ac4145a35c89
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: efbd05f88b962363e3b866fbf914f6d3a37823cc
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="the-ink-threading-model"></a><span data-ttu-id="9c90d-102">墨迹线程处理模型</span><span class="sxs-lookup"><span data-stu-id="9c90d-102">The Ink Threading Model</span></span>
<span data-ttu-id="9c90d-103">墨迹在 Tablet PC 上的优势之一是，其外观很像编写使用普通的笔和纸。</span><span class="sxs-lookup"><span data-stu-id="9c90d-103">One of the benefits of ink on a Tablet PC is that it feels a lot like writing with a regular pen and paper.</span></span>  <span data-ttu-id="9c90d-104">若要实现此目的，触笔收集以高得多的速度比鼠标将墨迹呈现为用户写入的输入的数据。</span><span class="sxs-lookup"><span data-stu-id="9c90d-104">To accomplish this, the tablet pen collects input data at a much higher rate than a mouse does and renders the ink as the user writes.</span></span>  <span data-ttu-id="9c90d-105">应用程序的用户界面 (UI) 线程不收集钢笔数据和呈现墨迹满足需求，因为它可能被阻止。</span><span class="sxs-lookup"><span data-stu-id="9c90d-105">The application's user interface (UI) thread is not sufficient for collecting pen data and rendering ink, because it can become blocked.</span></span>  <span data-ttu-id="9c90d-106">为了解决此问题，问题[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序时用户会编写墨迹使用两个其他线程。</span><span class="sxs-lookup"><span data-stu-id="9c90d-106">To solve this, a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application uses two additional threads when a user writes ink.</span></span>  
  
 <span data-ttu-id="9c90d-107">以下列表描述参与收集和呈现数字墨迹线程：</span><span class="sxs-lookup"><span data-stu-id="9c90d-107">The following list describes the threads that take part in collecting and rendering digital ink:</span></span>  
  
-   <span data-ttu-id="9c90d-108">笔线程-将触笔输入的线程。</span><span class="sxs-lookup"><span data-stu-id="9c90d-108">Pen thread - the thread that takes input from the stylus.</span></span>  <span data-ttu-id="9c90d-109">（事实上，这是一个线程池，但本主题将其称为笔线程。）</span><span class="sxs-lookup"><span data-stu-id="9c90d-109">(In reality, this is a thread pool, but this topic refers to it as a pen thread.)</span></span>  
  
-   <span data-ttu-id="9c90d-110">应用程序用户界面线程的控制应用程序的用户界面的线程。</span><span class="sxs-lookup"><span data-stu-id="9c90d-110">Application user interface thread - the thread that controls the user interface of the application.</span></span>  
  
-   <span data-ttu-id="9c90d-111">动态呈现线程-呈现时用户墨迹线程绘制笔画。</span><span class="sxs-lookup"><span data-stu-id="9c90d-111">Dynamic rendering thread - the thread that renders the ink while the user draws a stroke.</span></span> <span data-ttu-id="9c90d-112">窗口 Presentation Foundation 中所述，动态呈现线程是不同于呈现应用程序的其他 UI 元素的线程[线程处理模型](../../../../docs/framework/wpf/advanced/threading-model.md)。</span><span class="sxs-lookup"><span data-stu-id="9c90d-112">The dynamic rendering thread is different than the thread that renders other UI elements for the application, as mentioned in Window Presentation Foundation [Threading Model](../../../../docs/framework/wpf/advanced/threading-model.md).</span></span>  
  
 <span data-ttu-id="9c90d-113">墨迹模型都是相同是否应用程序使用<xref:System.Windows.Controls.InkCanvas>或自定义控件类似于中的一个[创建墨迹输入控件](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md)。</span><span class="sxs-lookup"><span data-stu-id="9c90d-113">The inking model is the same whether the application uses the <xref:System.Windows.Controls.InkCanvas> or a custom control similar to the one in [Creating an Ink Input Control](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).</span></span>  <span data-ttu-id="9c90d-114">虽然本主题讨论方面的线程处理<xref:System.Windows.Controls.InkCanvas>，创建自定义控件时，将应用相同的概念。</span><span class="sxs-lookup"><span data-stu-id="9c90d-114">Although this topic discusses threading in terms of the <xref:System.Windows.Controls.InkCanvas>, the same concepts apply when you create a custom control.</span></span>  
  
## <a name="threading-overview"></a><span data-ttu-id="9c90d-115">线程处理概述</span><span class="sxs-lookup"><span data-stu-id="9c90d-115">Threading Overview</span></span>  
 <span data-ttu-id="9c90d-116">下图阐释了线程处理模型，当用户绘制笔画时：</span><span class="sxs-lookup"><span data-stu-id="9c90d-116">The following diagram illustrates the threading model when a user draws a stroke:</span></span>  
  
 <span data-ttu-id="9c90d-117">![绘制笔画时的线程处理模型。] (../../../../docs/framework/wpf/advanced/media/inkthreading-drawingink.png "InkThreading_DrawingInk")</span><span class="sxs-lookup"><span data-stu-id="9c90d-117">![Threading model while drawing a stroke.](../../../../docs/framework/wpf/advanced/media/inkthreading-drawingink.png "InkThreading_DrawingInk")</span></span>  
  
1.  <span data-ttu-id="9c90d-118">用户绘制笔画时发生的操作</span><span class="sxs-lookup"><span data-stu-id="9c90d-118">Actions occurring while the user draws the stroke</span></span>  
  
    1.  <span data-ttu-id="9c90d-119">当用户绘制笔画时，触笔接触点参与笔线程。</span><span class="sxs-lookup"><span data-stu-id="9c90d-119">When the user draws a stroke, the stylus points come in on the pen thread.</span></span>  <span data-ttu-id="9c90d-120">触笔插件，包括<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>，接受笔线程上的触笔点并有机会修改在之前将其<xref:System.Windows.Controls.InkCanvas>接收它们。</span><span class="sxs-lookup"><span data-stu-id="9c90d-120">Stylus plug-ins, including the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, accept the stylus points on the pen thread and have the chance to modify them before the <xref:System.Windows.Controls.InkCanvas> receives them.</span></span>  
  
    2.  <span data-ttu-id="9c90d-121"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>呈现动态呈现线程上的触笔点。</span><span class="sxs-lookup"><span data-stu-id="9c90d-121">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> renders the stylus points on the dynamic rendering thread.</span></span> <span data-ttu-id="9c90d-122">在上一步在同一时间发生此异常。</span><span class="sxs-lookup"><span data-stu-id="9c90d-122">This happens at the same time as the previous step.</span></span>  
  
    3.  <span data-ttu-id="9c90d-123"><xref:System.Windows.Controls.InkCanvas>接收 UI 线程上的触笔点。</span><span class="sxs-lookup"><span data-stu-id="9c90d-123">The <xref:System.Windows.Controls.InkCanvas> receives the stylus points on the UI thread.</span></span>  
  
2.  <span data-ttu-id="9c90d-124">用户结束笔画后发生的操作</span><span class="sxs-lookup"><span data-stu-id="9c90d-124">Actions occurring after the user ends the stroke</span></span>  
  
    1.  <span data-ttu-id="9c90d-125">当用户完成绘制笔画，<xref:System.Windows.Controls.InkCanvas>创建<xref:System.Windows.Ink.Stroke>对象，并将其添加到<xref:System.Windows.Controls.InkPresenter>，这样可以静态呈现。</span><span class="sxs-lookup"><span data-stu-id="9c90d-125">When the user finishes drawing the stroke, the <xref:System.Windows.Controls.InkCanvas> creates a <xref:System.Windows.Ink.Stroke> object and adds it to the <xref:System.Windows.Controls.InkPresenter>, which statically renders it.</span></span>  
  
    2.  <span data-ttu-id="9c90d-126">UI 线程警报<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>静态呈现描边，因此<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>中移除的笔划的其可视表示形式。</span><span class="sxs-lookup"><span data-stu-id="9c90d-126">The UI thread alerts the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> that the stroke is statically rendered, so the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> removes its visual representation of the stroke.</span></span>  
  
## <a name="ink-collection-and-stylus-plug-ins"></a><span data-ttu-id="9c90d-127">墨迹集合和触笔插件</span><span class="sxs-lookup"><span data-stu-id="9c90d-127">Ink collection and Stylus Plug-ins</span></span>  
 <span data-ttu-id="9c90d-128">每个<xref:System.Windows.UIElement>具有<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>。</span><span class="sxs-lookup"><span data-stu-id="9c90d-128">Each <xref:System.Windows.UIElement> has a <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.</span></span>  <span data-ttu-id="9c90d-129"><xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>中的对象<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>接收并且可以修改笔线程上的触笔点。</span><span class="sxs-lookup"><span data-stu-id="9c90d-129">The <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objects in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> receive and can modify the stylus points on the pen thread.</span></span> <span data-ttu-id="9c90d-130"><xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>对象接收根据它们在中顺序的触笔点<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>。</span><span class="sxs-lookup"><span data-stu-id="9c90d-130">The <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objects receive the stylus points according to their order in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.</span></span>  
  
 <span data-ttu-id="9c90d-131">下图演示了一个假想的场景其中<xref:System.Windows.UIElement.StylusPlugIns%2A>集合<xref:System.Windows.UIElement>包含`stylusPlugin1`、 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>，和`stylusPlugin2`按顺序。</span><span class="sxs-lookup"><span data-stu-id="9c90d-131">The following diagram illustrates the hypothetical situation where the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection of a <xref:System.Windows.UIElement> contains `stylusPlugin1`, a <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, and `stylusPlugin2`, in that order.</span></span>  
  
 <span data-ttu-id="9c90d-132">![顺序触笔插件影响输出。] (../../../../docs/framework/wpf/advanced/media/inkthreading-pluginorder.png "InkThreading_PluginOrder")</span><span class="sxs-lookup"><span data-stu-id="9c90d-132">![Order of Stylus Plugins affect output.](../../../../docs/framework/wpf/advanced/media/inkthreading-pluginorder.png "InkThreading_PluginOrder")</span></span>  
  
 <span data-ttu-id="9c90d-133">在上图中，以下行为将发生：</span><span class="sxs-lookup"><span data-stu-id="9c90d-133">In the previous diagram, the following behavior takes place:</span></span>  
  
1.  <span data-ttu-id="9c90d-134">`StylusPlugin1`修改的 x 值和 y。</span><span class="sxs-lookup"><span data-stu-id="9c90d-134">`StylusPlugin1` modifies the values for x and y.</span></span>  
  
2.  <span data-ttu-id="9c90d-135"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>接收的已修改的触笔点并将它们呈现在动态呈现线程。</span><span class="sxs-lookup"><span data-stu-id="9c90d-135"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> receives the modified stylus points and renders them on the dynamic rendering thread.</span></span>  
  
3.  <span data-ttu-id="9c90d-136">`StylusPlugin2`接收的已修改的触笔点并进一步修改的 x 值和 y。</span><span class="sxs-lookup"><span data-stu-id="9c90d-136">`StylusPlugin2` receives the modified stylus points and further modifies the values for x and y.</span></span>  
  
4.  <span data-ttu-id="9c90d-137">应用程序收集触笔接触点，以及当用户完成描边，静态呈现笔画。</span><span class="sxs-lookup"><span data-stu-id="9c90d-137">The application collects the stylus points, and, when the user finishes the stroke, statically renders the stroke.</span></span>  
  
 <span data-ttu-id="9c90d-138">假设`stylusPlugin1`将触笔接触点限制为矩形和`stylusPlugin2`将转换到右的触笔点。</span><span class="sxs-lookup"><span data-stu-id="9c90d-138">Suppose that `stylusPlugin1` restricts the stylus points to a rectangle and `stylusPlugin2` translates the stylus points to the right.</span></span>  <span data-ttu-id="9c90d-139">在前面的方案中，<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>接收的受限制的触笔点，而非已翻译的触笔点。</span><span class="sxs-lookup"><span data-stu-id="9c90d-139">In the previous scenario, the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> receives the restricted stylus points, but not the translated stylus points.</span></span>  <span data-ttu-id="9c90d-140">当用户书写笔画时，描边呈现的矩形的边界内，但是不会对笔画用户提起笔之前要转换。</span><span class="sxs-lookup"><span data-stu-id="9c90d-140">When the user draws the stroke, the stroke is rendered within the bounds of the rectangle, but the stroke doesn't appear to be translated until the user lifts the pen.</span></span>  
  
### <a name="performing-operations-with-a-stylus-plug-in-on-the-ui-thread"></a><span data-ttu-id="9c90d-141">使用触笔插件在 UI 线程上执行操作</span><span class="sxs-lookup"><span data-stu-id="9c90d-141">Performing operations with a Stylus Plug-in on the UI thread</span></span>  
 <span data-ttu-id="9c90d-142">由于无法对笔线程执行准确的命中测试，某些元素偶尔可能会收到适用于其他元素的触笔输入。</span><span class="sxs-lookup"><span data-stu-id="9c90d-142">Because accurate hit-testing cannot be performed on the pen thread, some elements might occasionally receive stylus input intended for other elements.</span></span> <span data-ttu-id="9c90d-143">如果你需要确保在执行操作之前已正确路由输入，订阅并执行中的操作<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusDownProcessed%2A>， <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusMoveProcessed%2A>，或<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusUpProcessed%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="9c90d-143">If you need to make sure the input was routed correctly before performing an operation, subscribe to and perform the operation in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusDownProcessed%2A>, <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusMoveProcessed%2A>, or <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusUpProcessed%2A> method.</span></span> <span data-ttu-id="9c90d-144">在执行准确的命中测试后，将通过应用程序线程中调用这些方法。</span><span class="sxs-lookup"><span data-stu-id="9c90d-144">These methods are invoked by the application thread after accurate hit-testing has been performed.</span></span> <span data-ttu-id="9c90d-145">若要订阅对这些方法，调用<xref:System.Windows.Input.StylusPlugIns.RawStylusInput.NotifyWhenProcessed%2A>的方法中，在钢笔线程上发生的方法。</span><span class="sxs-lookup"><span data-stu-id="9c90d-145">To subscribe to these methods, call the <xref:System.Windows.Input.StylusPlugIns.RawStylusInput.NotifyWhenProcessed%2A> method in the method that occurs on the pen thread.</span></span>  
  
 <span data-ttu-id="9c90d-146">下图说明了笔线程和 UI 线程方面的触笔事件之间的关系<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>。</span><span class="sxs-lookup"><span data-stu-id="9c90d-146">The following diagram illustrates the relationship between the pen thread and UI thread with respect to the stylus events of a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>.</span></span>  
  
 <span data-ttu-id="9c90d-147">![墨迹线程处理模型 &#40;UI 和 Pen &#41;] (../../../../docs/framework/wpf/advanced/media/inkthreading-plugincallbacks.png "InkThreading_PluginCallbacks")</span><span class="sxs-lookup"><span data-stu-id="9c90d-147">![Ink Threading Models &#40;UI and Pen&#41;](../../../../docs/framework/wpf/advanced/media/inkthreading-plugincallbacks.png "InkThreading_PluginCallbacks")</span></span>  
  
## <a name="rendering-ink"></a><span data-ttu-id="9c90d-148">呈现墨迹</span><span class="sxs-lookup"><span data-stu-id="9c90d-148">Rendering Ink</span></span>  
 <span data-ttu-id="9c90d-149">用户绘制笔画，如<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>因此墨迹显示为"流"从笔即使 UI 线程忙碌呈现在单独线程上的墨迹。</span><span class="sxs-lookup"><span data-stu-id="9c90d-149">As the user draws a stroke, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> renders the ink on a separate thread so the ink appears to "flow" from the pen even when the UI thread is busy.</span></span>  <span data-ttu-id="9c90d-150"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>动态呈现线程上生成可视化树，因为它收集触笔接触点。</span><span class="sxs-lookup"><span data-stu-id="9c90d-150">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> builds a visual tree on the dynamic rendering thread as it collects stylus points.</span></span>  <span data-ttu-id="9c90d-151">当用户完成描边，<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>要求应用程序执行下一次呈现时收到通知。</span><span class="sxs-lookup"><span data-stu-id="9c90d-151">When the user finishes the stroke, the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> asks to be notified when the application does the next rendering pass.</span></span>  <span data-ttu-id="9c90d-152">应用程序完成下一步的呈现处理过程后,<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>清理其可视化树。</span><span class="sxs-lookup"><span data-stu-id="9c90d-152">After the application completes the next rendering pass, the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> cleans up its visual tree.</span></span>  <span data-ttu-id="9c90d-153">下图说明了此过程。</span><span class="sxs-lookup"><span data-stu-id="9c90d-153">The following diagram illustrates this process.</span></span>  
  
 <span data-ttu-id="9c90d-154">![墨迹线程处理关系图](../../../../docs/framework/wpf/advanced/media/inkthreading-visualtree.png "InkThreading_VisualTree")</span><span class="sxs-lookup"><span data-stu-id="9c90d-154">![Ink threading diagram](../../../../docs/framework/wpf/advanced/media/inkthreading-visualtree.png "InkThreading_VisualTree")</span></span>  
  
1.  <span data-ttu-id="9c90d-155">用户开始描边。</span><span class="sxs-lookup"><span data-stu-id="9c90d-155">The user begins the stroke.</span></span>  
  
    1.  <span data-ttu-id="9c90d-156"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>创建的可视化树。</span><span class="sxs-lookup"><span data-stu-id="9c90d-156">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> creates the visual tree.</span></span>  
  
2.  <span data-ttu-id="9c90d-157">用户绘制笔画。</span><span class="sxs-lookup"><span data-stu-id="9c90d-157">The user is drawing the stroke.</span></span>  
  
    1.  <span data-ttu-id="9c90d-158"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>生成的可视化树。</span><span class="sxs-lookup"><span data-stu-id="9c90d-158">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> builds the visual tree.</span></span>  
  
3.  <span data-ttu-id="9c90d-159">用户结束描边。</span><span class="sxs-lookup"><span data-stu-id="9c90d-159">The user ends the stroke.</span></span>  
  
    1.  <span data-ttu-id="9c90d-160"><xref:System.Windows.Controls.InkPresenter>笔画添加到其可视化树。</span><span class="sxs-lookup"><span data-stu-id="9c90d-160">The <xref:System.Windows.Controls.InkPresenter> adds the stroke to its visual tree.</span></span>  
  
    2.  <span data-ttu-id="9c90d-161">媒体集成层 (MIL) 静态呈现笔画。</span><span class="sxs-lookup"><span data-stu-id="9c90d-161">The Media Integration Layer (MIL) statically renders the strokes.</span></span>  
  
    3.  <span data-ttu-id="9c90d-162"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>清理视觉对象。</span><span class="sxs-lookup"><span data-stu-id="9c90d-162">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> cleans up the visuals.</span></span>
