---
title: 墨迹线程处理模型
ms.date: 03/30/2017
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
ms.openlocfilehash: 80e7ef202c46a23069766512cf4e67bb21a49564
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59335311"
---
# <a name="the-ink-threading-model"></a><span data-ttu-id="b9e22-102">墨迹线程处理模型</span><span class="sxs-lookup"><span data-stu-id="b9e22-102">The Ink Threading Model</span></span>
<span data-ttu-id="b9e22-103">Tablet PC 上的优势之一是墨迹的，它极为相似书写一样使用普通的笔和纸。</span><span class="sxs-lookup"><span data-stu-id="b9e22-103">One of the benefits of ink on a Tablet PC is that it feels a lot like writing with a regular pen and paper.</span></span>  <span data-ttu-id="b9e22-104">若要实现此目的，触笔收集输入的数据以高得多的速度比鼠标将手写内容呈现为用户写入。</span><span class="sxs-lookup"><span data-stu-id="b9e22-104">To accomplish this, the tablet pen collects input data at a much higher rate than a mouse does and renders the ink as the user writes.</span></span>  <span data-ttu-id="b9e22-105">应用程序的用户界面 (UI) 线程是不够的笔数据和呈现墨迹收集，因为它可能被阻止。</span><span class="sxs-lookup"><span data-stu-id="b9e22-105">The application's user interface (UI) thread is not sufficient for collecting pen data and rendering ink, because it can become blocked.</span></span>  <span data-ttu-id="b9e22-106">若要解决此问题，问题[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序使用两个其他线程，当用户将墨迹。</span><span class="sxs-lookup"><span data-stu-id="b9e22-106">To solve this, a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application uses two additional threads when a user writes ink.</span></span>  
  
 <span data-ttu-id="b9e22-107">以下列表描述了在收集和呈现数字墨迹了相应的线程：</span><span class="sxs-lookup"><span data-stu-id="b9e22-107">The following list describes the threads that take part in collecting and rendering digital ink:</span></span>  
  
-   <span data-ttu-id="b9e22-108">笔线程的触笔输入的线程。</span><span class="sxs-lookup"><span data-stu-id="b9e22-108">Pen thread - the thread that takes input from the stylus.</span></span>  <span data-ttu-id="b9e22-109">（实际上，这是一个线程池，但本主题会将其称为笔线程。）</span><span class="sxs-lookup"><span data-stu-id="b9e22-109">(In reality, this is a thread pool, but this topic refers to it as a pen thread.)</span></span>  
  
-   <span data-ttu-id="b9e22-110">应用程序用户界面线程的线程，用于控制应用程序的用户界面。</span><span class="sxs-lookup"><span data-stu-id="b9e22-110">Application user interface thread - the thread that controls the user interface of the application.</span></span>  
  
-   <span data-ttu-id="b9e22-111">动态呈现线程的线程呈现墨迹时用户绘制笔划。</span><span class="sxs-lookup"><span data-stu-id="b9e22-111">Dynamic rendering thread - the thread that renders the ink while the user draws a stroke.</span></span> <span data-ttu-id="b9e22-112">动态呈现线程是不同于呈现的应用程序，其他 UI 元素的线程窗口 Presentation Foundation 中所述[线程模型](threading-model.md)。</span><span class="sxs-lookup"><span data-stu-id="b9e22-112">The dynamic rendering thread is different than the thread that renders other UI elements for the application, as mentioned in Window Presentation Foundation [Threading Model](threading-model.md).</span></span>  
  
 <span data-ttu-id="b9e22-113">墨迹模型都是相同的应用程序使用是否<xref:System.Windows.Controls.InkCanvas>或自定义控件中的一个类似[创建墨迹输入控件](creating-an-ink-input-control.md)。</span><span class="sxs-lookup"><span data-stu-id="b9e22-113">The inking model is the same whether the application uses the <xref:System.Windows.Controls.InkCanvas> or a custom control similar to the one in [Creating an Ink Input Control](creating-an-ink-input-control.md).</span></span>  <span data-ttu-id="b9e22-114">尽管本主题讨论了线程处理的<xref:System.Windows.Controls.InkCanvas>，在创建自定义控件时应用相同的概念。</span><span class="sxs-lookup"><span data-stu-id="b9e22-114">Although this topic discusses threading in terms of the <xref:System.Windows.Controls.InkCanvas>, the same concepts apply when you create a custom control.</span></span>  
  
## <a name="threading-overview"></a><span data-ttu-id="b9e22-115">线程处理概述</span><span class="sxs-lookup"><span data-stu-id="b9e22-115">Threading Overview</span></span>  
 <span data-ttu-id="b9e22-116">下图说明了线程模型，当用户绘制笔划时：</span><span class="sxs-lookup"><span data-stu-id="b9e22-116">The following diagram illustrates the threading model when a user draws a stroke:</span></span>  
  
 <span data-ttu-id="b9e22-117">![绘制笔画时的线程处理模型。](./media/inkthreading-drawingink.png "InkThreading_DrawingInk")</span><span class="sxs-lookup"><span data-stu-id="b9e22-117">![Threading model while drawing a stroke.](./media/inkthreading-drawingink.png "InkThreading_DrawingInk")</span></span>  
  
1. <span data-ttu-id="b9e22-118">用户绘制笔划时发生的操作</span><span class="sxs-lookup"><span data-stu-id="b9e22-118">Actions occurring while the user draws the stroke</span></span>  
  
    1.  <span data-ttu-id="b9e22-119">当用户绘制笔划时，触笔接触点在笔线程上。</span><span class="sxs-lookup"><span data-stu-id="b9e22-119">When the user draws a stroke, the stylus points come in on the pen thread.</span></span>  <span data-ttu-id="b9e22-120">在触笔插件，包括<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>，接受在笔线程上的触笔接触点，并有机会修改之前已对其<xref:System.Windows.Controls.InkCanvas>接收它们。</span><span class="sxs-lookup"><span data-stu-id="b9e22-120">Stylus plug-ins, including the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, accept the stylus points on the pen thread and have the chance to modify them before the <xref:System.Windows.Controls.InkCanvas> receives them.</span></span>  
  
    2.  <span data-ttu-id="b9e22-121"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>呈现动态呈现线程上的触笔接触点。</span><span class="sxs-lookup"><span data-stu-id="b9e22-121">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> renders the stylus points on the dynamic rendering thread.</span></span> <span data-ttu-id="b9e22-122">发生这种情况在同时作为在上一步。</span><span class="sxs-lookup"><span data-stu-id="b9e22-122">This happens at the same time as the previous step.</span></span>  
  
    3.  <span data-ttu-id="b9e22-123"><xref:System.Windows.Controls.InkCanvas>接收在 UI 线程上的触笔接触点。</span><span class="sxs-lookup"><span data-stu-id="b9e22-123">The <xref:System.Windows.Controls.InkCanvas> receives the stylus points on the UI thread.</span></span>  
  
2. <span data-ttu-id="b9e22-124">用户结束笔画后发生的操作</span><span class="sxs-lookup"><span data-stu-id="b9e22-124">Actions occurring after the user ends the stroke</span></span>  
  
    1.  <span data-ttu-id="b9e22-125">在用户完成绘制笔画<xref:System.Windows.Controls.InkCanvas>创建<xref:System.Windows.Ink.Stroke>对象，并将其添加到<xref:System.Windows.Controls.InkPresenter>，它将以静态方式呈现它。</span><span class="sxs-lookup"><span data-stu-id="b9e22-125">When the user finishes drawing the stroke, the <xref:System.Windows.Controls.InkCanvas> creates a <xref:System.Windows.Ink.Stroke> object and adds it to the <xref:System.Windows.Controls.InkPresenter>, which statically renders it.</span></span>  
  
    2.  <span data-ttu-id="b9e22-126">UI 线程通知<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>静态呈现笔划，因此<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>删除笔画其可视表示形式。</span><span class="sxs-lookup"><span data-stu-id="b9e22-126">The UI thread alerts the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> that the stroke is statically rendered, so the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> removes its visual representation of the stroke.</span></span>  
  
## <a name="ink-collection-and-stylus-plug-ins"></a><span data-ttu-id="b9e22-127">墨迹收集和触笔插件</span><span class="sxs-lookup"><span data-stu-id="b9e22-127">Ink collection and Stylus Plug-ins</span></span>  
 <span data-ttu-id="b9e22-128">每个<xref:System.Windows.UIElement>具有<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>。</span><span class="sxs-lookup"><span data-stu-id="b9e22-128">Each <xref:System.Windows.UIElement> has a <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.</span></span>  <span data-ttu-id="b9e22-129"><xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>中的对象<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>接收，并可以修改在笔线程上的触笔接触点。</span><span class="sxs-lookup"><span data-stu-id="b9e22-129">The <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objects in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> receive and can modify the stylus points on the pen thread.</span></span> <span data-ttu-id="b9e22-130"><xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>对象接收根据其在顺序触笔接触点<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>。</span><span class="sxs-lookup"><span data-stu-id="b9e22-130">The <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objects receive the stylus points according to their order in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.</span></span>  
  
 <span data-ttu-id="b9e22-131">下图演示了一个假想的场景其中<xref:System.Windows.UIElement.StylusPlugIns%2A>的集合<xref:System.Windows.UIElement>包含`stylusPlugin1`即<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>，和`stylusPlugin2`按顺序。</span><span class="sxs-lookup"><span data-stu-id="b9e22-131">The following diagram illustrates the hypothetical situation where the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection of a <xref:System.Windows.UIElement> contains `stylusPlugin1`, a <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, and `stylusPlugin2`, in that order.</span></span>  
  
 <span data-ttu-id="b9e22-132">![在触笔插件的顺序会影响输出。](./media/inkthreading-pluginorder.png "InkThreading_PluginOrder")</span><span class="sxs-lookup"><span data-stu-id="b9e22-132">![Order of Stylus Plugins affect output.](./media/inkthreading-pluginorder.png "InkThreading_PluginOrder")</span></span>  
  
 <span data-ttu-id="b9e22-133">在上图中，以下行为会发生：</span><span class="sxs-lookup"><span data-stu-id="b9e22-133">In the previous diagram, the following behavior takes place:</span></span>  
  
1. `StylusPlugin1` <span data-ttu-id="b9e22-134">修改的 x 值和 y。</span><span class="sxs-lookup"><span data-stu-id="b9e22-134">modifies the values for x and y.</span></span>  
  
2. <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> <span data-ttu-id="b9e22-135">接收已修改的触笔接触点，并将它们呈现在动态呈现线程。</span><span class="sxs-lookup"><span data-stu-id="b9e22-135">receives the modified stylus points and renders them on the dynamic rendering thread.</span></span>  
  
3. `StylusPlugin2` <span data-ttu-id="b9e22-136">接收已修改的触笔接触点，并进一步修改的 x 值和 y。</span><span class="sxs-lookup"><span data-stu-id="b9e22-136">receives the modified stylus points and further modifies the values for x and y.</span></span>  
  
4. <span data-ttu-id="b9e22-137">应用程序收集触笔接触点，并在用户完成笔画，以静态方式呈现笔划。</span><span class="sxs-lookup"><span data-stu-id="b9e22-137">The application collects the stylus points, and, when the user finishes the stroke, statically renders the stroke.</span></span>  
  
 <span data-ttu-id="b9e22-138">假设`stylusPlugin1`限制对矩形的触笔接触点和`stylusPlugin2`转换到右侧触笔接触点。</span><span class="sxs-lookup"><span data-stu-id="b9e22-138">Suppose that `stylusPlugin1` restricts the stylus points to a rectangle and `stylusPlugin2` translates the stylus points to the right.</span></span>  <span data-ttu-id="b9e22-139">在前面的方案，<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>收到受限制的触笔点，但是不翻译后的触笔接触点。</span><span class="sxs-lookup"><span data-stu-id="b9e22-139">In the previous scenario, the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> receives the restricted stylus points, but not the translated stylus points.</span></span>  <span data-ttu-id="b9e22-140">时用户绘制笔划，笔划的呈现的矩形的边界内，但不会对笔画用户提起笔之前转换。</span><span class="sxs-lookup"><span data-stu-id="b9e22-140">When the user draws the stroke, the stroke is rendered within the bounds of the rectangle, but the stroke doesn't appear to be translated until the user lifts the pen.</span></span>  
  
### <a name="performing-operations-with-a-stylus-plug-in-on-the-ui-thread"></a><span data-ttu-id="b9e22-141">使用触笔插件在 UI 线程上执行操作</span><span class="sxs-lookup"><span data-stu-id="b9e22-141">Performing operations with a Stylus Plug-in on the UI thread</span></span>  
 <span data-ttu-id="b9e22-142">由于不能在笔线程上执行准确的命中测试，因此某些元素可能会偶尔收到适用于其他元素的触笔输入。</span><span class="sxs-lookup"><span data-stu-id="b9e22-142">Because accurate hit-testing cannot be performed on the pen thread, some elements might occasionally receive stylus input intended for other elements.</span></span> <span data-ttu-id="b9e22-143">如果你需要确保输入已正确路由正在执行的操作之前，订阅并执行中的操作<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusDownProcessed%2A>， <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusMoveProcessed%2A>，或<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusUpProcessed%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="b9e22-143">If you need to make sure the input was routed correctly before performing an operation, subscribe to and perform the operation in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusDownProcessed%2A>, <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusMoveProcessed%2A>, or <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusUpProcessed%2A> method.</span></span> <span data-ttu-id="b9e22-144">在执行准确的命中测试后，应用程序线程将调用这些方法。</span><span class="sxs-lookup"><span data-stu-id="b9e22-144">These methods are invoked by the application thread after accurate hit-testing has been performed.</span></span> <span data-ttu-id="b9e22-145">若要订阅对这些方法，调用<xref:System.Windows.Input.StylusPlugIns.RawStylusInput.NotifyWhenProcessed%2A>在笔线程发生的方法中的方法。</span><span class="sxs-lookup"><span data-stu-id="b9e22-145">To subscribe to these methods, call the <xref:System.Windows.Input.StylusPlugIns.RawStylusInput.NotifyWhenProcessed%2A> method in the method that occurs on the pen thread.</span></span>  
  
 <span data-ttu-id="b9e22-146">下图说明了在笔线程和 UI 线程方面的触笔事件之间的关系<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>。</span><span class="sxs-lookup"><span data-stu-id="b9e22-146">The following diagram illustrates the relationship between the pen thread and UI thread with respect to the stylus events of a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>.</span></span>  
  
 <span data-ttu-id="b9e22-147">![墨迹线程模型&#40;UI 和 Pen&#41;](./media/inkthreading-plugincallbacks.png "InkThreading_PluginCallbacks")</span><span class="sxs-lookup"><span data-stu-id="b9e22-147">![Ink Threading Models &#40;UI and Pen&#41;](./media/inkthreading-plugincallbacks.png "InkThreading_PluginCallbacks")</span></span>  
  
## <a name="rendering-ink"></a><span data-ttu-id="b9e22-148">呈现墨迹</span><span class="sxs-lookup"><span data-stu-id="b9e22-148">Rendering Ink</span></span>  
 <span data-ttu-id="b9e22-149">用户绘制笔划，如<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>呈现单独的线程上的墨迹，因此墨迹看上去"流"从笔即使 UI 线程正忙。</span><span class="sxs-lookup"><span data-stu-id="b9e22-149">As the user draws a stroke, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> renders the ink on a separate thread so the ink appears to "flow" from the pen even when the UI thread is busy.</span></span>  <span data-ttu-id="b9e22-150"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>动态呈现线程上生成可视化树，因为它收集触笔接触点。</span><span class="sxs-lookup"><span data-stu-id="b9e22-150">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> builds a visual tree on the dynamic rendering thread as it collects stylus points.</span></span>  <span data-ttu-id="b9e22-151">在用户完成描边，<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>要求应用程序执行下一次呈现时收到通知。</span><span class="sxs-lookup"><span data-stu-id="b9e22-151">When the user finishes the stroke, the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> asks to be notified when the application does the next rendering pass.</span></span>  <span data-ttu-id="b9e22-152">应用程序完成下一次呈现的之后,<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>清理其可视化树。</span><span class="sxs-lookup"><span data-stu-id="b9e22-152">After the application completes the next rendering pass, the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> cleans up its visual tree.</span></span>  <span data-ttu-id="b9e22-153">下图说明了此过程。</span><span class="sxs-lookup"><span data-stu-id="b9e22-153">The following diagram illustrates this process.</span></span>  
  
 <span data-ttu-id="b9e22-154">![墨迹线程处理示意图](./media/inkthreading-visualtree.png "InkThreading_VisualTree")</span><span class="sxs-lookup"><span data-stu-id="b9e22-154">![Ink threading diagram](./media/inkthreading-visualtree.png "InkThreading_VisualTree")</span></span>  
  
1. <span data-ttu-id="b9e22-155">用户开始笔画。</span><span class="sxs-lookup"><span data-stu-id="b9e22-155">The user begins the stroke.</span></span>  
  
    1.  <span data-ttu-id="b9e22-156"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>创建可视化树。</span><span class="sxs-lookup"><span data-stu-id="b9e22-156">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> creates the visual tree.</span></span>  
  
2. <span data-ttu-id="b9e22-157">用户绘制笔划。</span><span class="sxs-lookup"><span data-stu-id="b9e22-157">The user is drawing the stroke.</span></span>  
  
    1.  <span data-ttu-id="b9e22-158"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>构建可视化树。</span><span class="sxs-lookup"><span data-stu-id="b9e22-158">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> builds the visual tree.</span></span>  
  
3. <span data-ttu-id="b9e22-159">用户结束笔画。</span><span class="sxs-lookup"><span data-stu-id="b9e22-159">The user ends the stroke.</span></span>  
  
    1.  <span data-ttu-id="b9e22-160"><xref:System.Windows.Controls.InkPresenter>笔画添加到其可视化树。</span><span class="sxs-lookup"><span data-stu-id="b9e22-160">The <xref:System.Windows.Controls.InkPresenter> adds the stroke to its visual tree.</span></span>  
  
    2.  <span data-ttu-id="b9e22-161">媒体集成层 (MIL) 以静态方式呈现笔划。</span><span class="sxs-lookup"><span data-stu-id="b9e22-161">The Media Integration Layer (MIL) statically renders the strokes.</span></span>  
  
    3.  <span data-ttu-id="b9e22-162"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>清理视觉对象。</span><span class="sxs-lookup"><span data-stu-id="b9e22-162">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> cleans up the visuals.</span></span>
