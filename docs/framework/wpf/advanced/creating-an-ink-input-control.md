---
title: 创建墨迹输入控件
ms.date: 03/30/2017
helpviewer_keywords:
- ink strokes [WPF], managing
- managing ink strokes [WPF]
- ink input control [WPF]
- input from mouse [WPF], accepting
- mouse input [WPF], accepting
- ink [WPF], rendering
- ink strokes [WPF], collecting
- rendering ink [WPF]
- collecting ink strokes [WPF]
- DynamicRenderer objects [WPF]
- StylusPlugIn objects [WPF]
ms.assetid: c31f3a67-cb3f-4ded-af9e-ed21f6575b26
ms.openlocfilehash: 394318488b0afb8e043389e0abc3f51dce8604c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186284"
---
# <a name="creating-an-ink-input-control"></a><span data-ttu-id="bb808-102">创建墨迹输入控件</span><span class="sxs-lookup"><span data-stu-id="bb808-102">Creating an Ink Input Control</span></span>
<span data-ttu-id="bb808-103">您可以创建动态和静态渲染墨迹的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="bb808-103">You can create a custom control that dynamically and statically renders ink.</span></span> <span data-ttu-id="bb808-104">也就是说，在用户绘制笔画时渲染墨迹，导致墨迹从 Tablet 笔中显示为"流"，并在墨迹添加到控件后显示墨迹，通过 Tablet 笔、从剪贴板粘贴或从文件加载。</span><span class="sxs-lookup"><span data-stu-id="bb808-104">That is, render ink as a user draws a stroke, causing the ink to appear to "flow" from the tablet pen, and display ink after it is added to the control, either via the tablet pen, pasted from the Clipboard, or loaded from a file.</span></span> <span data-ttu-id="bb808-105">要动态渲染墨迹，控件必须使用<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>。</span><span class="sxs-lookup"><span data-stu-id="bb808-105">To dynamically render ink, your control must use a <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.</span></span> <span data-ttu-id="bb808-106">要静态渲染墨迹，必须重写手写笔事件方法<xref:System.Windows.UIElement.OnStylusDown%2A>（和<xref:System.Windows.UIElement.OnStylusMove%2A> <xref:System.Windows.UIElement.OnStylusUp%2A>） 以收集数据<xref:System.Windows.Input.StylusPoint>、创建描边并将它们添加到 （<xref:System.Windows.Controls.InkPresenter>该方法在控件上呈现墨迹）。</span><span class="sxs-lookup"><span data-stu-id="bb808-106">To statically render ink, you must override the stylus event methods (<xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusMove%2A>, and <xref:System.Windows.UIElement.OnStylusUp%2A>) to collect <xref:System.Windows.Input.StylusPoint> data, create strokes, and add them to an <xref:System.Windows.Controls.InkPresenter> (which renders the ink on the control).</span></span>  
  
 <span data-ttu-id="bb808-107">本主题包含以下小节：</span><span class="sxs-lookup"><span data-stu-id="bb808-107">This topic contains the following subsections:</span></span>  
  
- [<span data-ttu-id="bb808-108">如何：收集手写笔点数据并创建墨迹描边</span><span class="sxs-lookup"><span data-stu-id="bb808-108">How to: Collect Stylus Point Data and Create Ink Strokes</span></span>](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
- [<span data-ttu-id="bb808-109">如何：使控件接受来自鼠标的输入</span><span class="sxs-lookup"><span data-stu-id="bb808-109">How to: Enable Your Control to Accept Input from the Mouse</span></span>](#EnablingYourControlToAcceptInputTromTheMouse)  
  
- [<span data-ttu-id="bb808-110">综合运用</span><span class="sxs-lookup"><span data-stu-id="bb808-110">Putting it together</span></span>](#PuttingItTogether)  
  
- [<span data-ttu-id="bb808-111">使用其他插件和动态渲染器</span><span class="sxs-lookup"><span data-stu-id="bb808-111">Using Additional Plug-ins and DynamicRenderers</span></span>](#UsingAdditionalPluginsAndDynamicRenderers)  
  
- [<span data-ttu-id="bb808-112">结论</span><span class="sxs-lookup"><span data-stu-id="bb808-112">Conclusion</span></span>](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>
## <a name="how-to-collect-stylus-point-data-and-create-ink-strokes"></a><span data-ttu-id="bb808-113">如何：收集手写笔点数据并创建墨迹描边</span><span class="sxs-lookup"><span data-stu-id="bb808-113">How to: Collect Stylus Point Data and Create Ink Strokes</span></span>  
 <span data-ttu-id="bb808-114">要创建收集和管理墨迹描边的控件，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bb808-114">To create a control that collects and manages ink strokes do the following:</span></span>  
  
1. <span data-ttu-id="bb808-115">派生来自<xref:System.Windows.Controls.Control>或 派生自<xref:System.Windows.Controls.Control>的类之一，<xref:System.Windows.Controls.Label>例如 。</span><span class="sxs-lookup"><span data-stu-id="bb808-115">Derive a class from <xref:System.Windows.Controls.Control> or one of the classes derived from <xref:System.Windows.Controls.Control>, such as <xref:System.Windows.Controls.Label>.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2. <span data-ttu-id="bb808-116">将<xref:System.Windows.Controls.InkPresenter>add 添加到 类<xref:System.Windows.Controls.ContentControl.Content%2A>并将 属性设置为<xref:System.Windows.Controls.InkPresenter>新 。</span><span class="sxs-lookup"><span data-stu-id="bb808-116">Add an <xref:System.Windows.Controls.InkPresenter> to the class and set the <xref:System.Windows.Controls.ContentControl.Content%2A> property to the new <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3. <span data-ttu-id="bb808-117"><xref:System.Windows.Controls.InkPresenter>通过调用<xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A>方法将<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer><xref:System.Windows.UIElement.StylusPlugIns%2A><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A>的 将 的<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>附加到 ，并将 添加到集合中。</span><span class="sxs-lookup"><span data-stu-id="bb808-117">Attach the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> of the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the <xref:System.Windows.Controls.InkPresenter> by calling the <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> method, and add the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection.</span></span> <span data-ttu-id="bb808-118">这允许 在<xref:System.Windows.Controls.InkPresenter>控件收集手写笔点数据时显示墨迹。</span><span class="sxs-lookup"><span data-stu-id="bb808-118">This allows the <xref:System.Windows.Controls.InkPresenter> to display the ink as the stylus point data is collected by your control.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4. <span data-ttu-id="bb808-119">重写 <xref:System.Windows.UIElement.OnStylusDown%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="bb808-119">Override the <xref:System.Windows.UIElement.OnStylusDown%2A> method.</span></span>  <span data-ttu-id="bb808-120">在此方法中，使用 调用<xref:System.Windows.Input.Stylus.Capture%2A>捕获手写笔。</span><span class="sxs-lookup"><span data-stu-id="bb808-120">In this method, capture the stylus with a call to <xref:System.Windows.Input.Stylus.Capture%2A>.</span></span> <span data-ttu-id="bb808-121">通过捕获手写笔，即使手写笔离开控件的边界，您的控件仍<xref:System.Windows.UIElement.StylusMove>将继续<xref:System.Windows.UIElement.StylusUp>接收和事件。</span><span class="sxs-lookup"><span data-stu-id="bb808-121">By capturing the stylus, your control will to continue to receive <xref:System.Windows.UIElement.StylusMove> and <xref:System.Windows.UIElement.StylusUp> events even if the stylus leaves the control's boundaries.</span></span> <span data-ttu-id="bb808-122">这不是严格的强制性，但几乎总是需要良好的用户体验。</span><span class="sxs-lookup"><span data-stu-id="bb808-122">This is not strictly mandatory, but almost always desired for a good user experience.</span></span> <span data-ttu-id="bb808-123">创建新数据<xref:System.Windows.Input.StylusPointCollection>以收集数据<xref:System.Windows.Input.StylusPoint>。</span><span class="sxs-lookup"><span data-stu-id="bb808-123">Create a new <xref:System.Windows.Input.StylusPointCollection> to gather <xref:System.Windows.Input.StylusPoint> data.</span></span> <span data-ttu-id="bb808-124">最后，将初始数据集<xref:System.Windows.Input.StylusPoint>添加到 。 <xref:System.Windows.Input.StylusPointCollection></span><span class="sxs-lookup"><span data-stu-id="bb808-124">Finally, add the initial set of <xref:System.Windows.Input.StylusPoint> data to the <xref:System.Windows.Input.StylusPointCollection>.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5. <span data-ttu-id="bb808-125">重写<xref:System.Windows.UIElement.OnStylusMove%2A>方法并将<xref:System.Windows.Input.StylusPoint>数据添加到之前创建<xref:System.Windows.Input.StylusPointCollection>的对象。</span><span class="sxs-lookup"><span data-stu-id="bb808-125">Override the <xref:System.Windows.UIElement.OnStylusMove%2A> method and add the <xref:System.Windows.Input.StylusPoint> data to the <xref:System.Windows.Input.StylusPointCollection> object that you created earlier.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6. <span data-ttu-id="bb808-126">重写方法<xref:System.Windows.UIElement.OnStylusUp%2A>，使用<xref:System.Windows.Ink.Stroke><xref:System.Windows.Input.StylusPointCollection>数据创建新数据。</span><span class="sxs-lookup"><span data-stu-id="bb808-126">Override the <xref:System.Windows.UIElement.OnStylusUp%2A> method and create a new <xref:System.Windows.Ink.Stroke> with the <xref:System.Windows.Input.StylusPointCollection> data.</span></span> <span data-ttu-id="bb808-127">将您创建<xref:System.Windows.Ink.Stroke>的新样式添加到<xref:System.Windows.Controls.InkPresenter.Strokes%2A><xref:System.Windows.Controls.InkPresenter>和 释放手写笔捕获的集合中。</span><span class="sxs-lookup"><span data-stu-id="bb808-127">Add the new <xref:System.Windows.Ink.Stroke> you created to the <xref:System.Windows.Controls.InkPresenter.Strokes%2A> collection of the <xref:System.Windows.Controls.InkPresenter> and release stylus capture.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>
## <a name="how-to-enable-your-control-to-accept-input-from-the-mouse"></a><span data-ttu-id="bb808-128">如何：使控件接受来自鼠标的输入</span><span class="sxs-lookup"><span data-stu-id="bb808-128">How to: Enable Your Control to Accept Input from the Mouse</span></span>  
 <span data-ttu-id="bb808-129">如果将前面的控件添加到应用程序，运行它，并将鼠标用作输入设备，您会注意到笔画不会持久化。</span><span class="sxs-lookup"><span data-stu-id="bb808-129">If you add the preceding control to your application, run it, and use the mouse as an input device, you will notice that the strokes are not persisted.</span></span> <span data-ttu-id="bb808-130">要在将鼠标用作输入设备时保留笔画，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bb808-130">To persist the strokes when the mouse is used as the input device do the following:</span></span>  
  
1. <span data-ttu-id="bb808-131">重写<xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A>并创建新<xref:System.Windows.Input.StylusPointCollection>的"在事件发生时获取鼠标的位置"，并使用点数据创建<xref:System.Windows.Input.StylusPoint>一个 ，并将 添加到<xref:System.Windows.Input.StylusPoint>。 <xref:System.Windows.Input.StylusPointCollection></span><span class="sxs-lookup"><span data-stu-id="bb808-131">Override the <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> and create a new <xref:System.Windows.Input.StylusPointCollection> Get the position of the mouse when the event occurred and create a <xref:System.Windows.Input.StylusPoint> using the point data and add the <xref:System.Windows.Input.StylusPoint> to the <xref:System.Windows.Input.StylusPointCollection>.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2. <span data-ttu-id="bb808-132">重写 <xref:System.Windows.UIElement.OnMouseMove%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="bb808-132">Override the <xref:System.Windows.UIElement.OnMouseMove%2A> method.</span></span> <span data-ttu-id="bb808-133">在事件发生时获取鼠标的位置，并使用点数据创建一个<xref:System.Windows.Input.StylusPoint>。</span><span class="sxs-lookup"><span data-stu-id="bb808-133">Get the position of the mouse when the event occurred and create a <xref:System.Windows.Input.StylusPoint> using the point data.</span></span>  <span data-ttu-id="bb808-134">将<xref:System.Windows.Input.StylusPoint>添加到之前<xref:System.Windows.Input.StylusPointCollection>创建的对象。</span><span class="sxs-lookup"><span data-stu-id="bb808-134">Add the <xref:System.Windows.Input.StylusPoint> to the <xref:System.Windows.Input.StylusPointCollection> object that you created earlier.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3. <span data-ttu-id="bb808-135">重写 <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="bb808-135">Override the <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> method.</span></span>  <span data-ttu-id="bb808-136"><xref:System.Windows.Ink.Stroke>使用<xref:System.Windows.Input.StylusPointCollection>数据创建新数据，并将创建<xref:System.Windows.Ink.Stroke><xref:System.Windows.Controls.InkPresenter.Strokes%2A>的新添加到 集合中。 <xref:System.Windows.Controls.InkPresenter></span><span class="sxs-lookup"><span data-stu-id="bb808-136">Create a new <xref:System.Windows.Ink.Stroke> with the <xref:System.Windows.Input.StylusPointCollection> data, and add the new <xref:System.Windows.Ink.Stroke> you created to the <xref:System.Windows.Controls.InkPresenter.Strokes%2A> collection of the <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>
## <a name="putting-it-together"></a><span data-ttu-id="bb808-137">综合运用</span><span class="sxs-lookup"><span data-stu-id="bb808-137">Putting it together</span></span>  
 <span data-ttu-id="bb808-138">下面的示例是一个自定义控件，当用户使用鼠标或笔时收集墨迹。</span><span class="sxs-lookup"><span data-stu-id="bb808-138">The following example is a custom control that collects ink when the user uses either the mouse or the pen.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>
## <a name="using-additional-plug-ins-and-dynamicrenderers"></a><span data-ttu-id="bb808-139">使用其他插件和动态渲染器</span><span class="sxs-lookup"><span data-stu-id="bb808-139">Using Additional Plug-ins and DynamicRenderers</span></span>  
 <span data-ttu-id="bb808-140">与 InkCanvas 一样，自定义控件可以<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>具有自定义<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>对象和其他对象。</span><span class="sxs-lookup"><span data-stu-id="bb808-140">Like the InkCanvas, your custom control can have custom <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> and additional <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> objects.</span></span> <span data-ttu-id="bb808-141">将这些添加到集合中<xref:System.Windows.UIElement.StylusPlugIns%2A>。</span><span class="sxs-lookup"><span data-stu-id="bb808-141">Add these to the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection.</span></span> <span data-ttu-id="bb808-142">中<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>的对象的顺序<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>会影响墨迹在渲染时的外观。</span><span class="sxs-lookup"><span data-stu-id="bb808-142">The order of the <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objects in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> affects the appearance of the ink when it is rendered.</span></span> <span data-ttu-id="bb808-143">假设您有一个<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>已`dynamicRenderer`调用的自定义<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>项`translatePlugin`，该调用的自定义项会偏移 Tablet 笔中的墨迹。</span><span class="sxs-lookup"><span data-stu-id="bb808-143">Suppose you have a <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> called `dynamicRenderer` and a custom <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> called `translatePlugin` that offsets the ink from the tablet pen.</span></span> <span data-ttu-id="bb808-144">如果`translatePlugin`是第一<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>个，<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>是第`dynamicRenderer`二个，则当用户移动笔时，"流动"的墨迹将被偏移。</span><span class="sxs-lookup"><span data-stu-id="bb808-144">If `translatePlugin` is the first <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, and `dynamicRenderer` is the second, the ink that "flows" will be offset as the user moves the pen.</span></span> <span data-ttu-id="bb808-145">如果`dynamicRenderer`是第一，是第`translatePlugin`二，则在用户抬起笔之前，墨迹不会偏移。</span><span class="sxs-lookup"><span data-stu-id="bb808-145">If `dynamicRenderer` is first, and `translatePlugin` is second, the ink will not be offset until the user lifts the pen.</span></span>  
  
<a name="AdvancedInkHandling_Conclusion"></a>
## <a name="conclusion"></a><span data-ttu-id="bb808-146">结束语</span><span class="sxs-lookup"><span data-stu-id="bb808-146">Conclusion</span></span>  
 <span data-ttu-id="bb808-147">您可以创建通过重写手写笔事件方法收集和呈现墨迹的控件。</span><span class="sxs-lookup"><span data-stu-id="bb808-147">You can create a control that collects and renders ink by overriding the stylus event methods.</span></span> <span data-ttu-id="bb808-148">通过创建自己的控件、派生自己的<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>类并将它们插入 到 中<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>，您可以实现几乎任何使用数字墨迹可以想象到的行为。</span><span class="sxs-lookup"><span data-stu-id="bb808-148">By creating your own control, deriving your own <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> classes, and inserting them the into <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, you can implement virtually any behavior imaginable with digital ink.</span></span> <span data-ttu-id="bb808-149">您可以在生成<xref:System.Windows.Input.StylusPoint>数据时访问数据，从而有机会自定义<xref:System.Windows.Input.Stylus>输入并在屏幕上根据需要呈现它，以适合您的应用程序。</span><span class="sxs-lookup"><span data-stu-id="bb808-149">You have access to the <xref:System.Windows.Input.StylusPoint> data as it is generated, giving you the opportunity to  customize <xref:System.Windows.Input.Stylus> input and render it on the screen as appropriate for your application.</span></span> <span data-ttu-id="bb808-150">由于您对<xref:System.Windows.Input.StylusPoint>数据具有如此低级别的访问，因此可以实现墨迹收集，并针对应用程序以最佳性能呈现它。</span><span class="sxs-lookup"><span data-stu-id="bb808-150">Because you have such low-level access to the <xref:System.Windows.Input.StylusPoint> data, you can implement ink collection and render it with optimal performance for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb808-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb808-151">See also</span></span>

- [<span data-ttu-id="bb808-152">高级墨迹处理</span><span class="sxs-lookup"><span data-stu-id="bb808-152">Advanced Ink Handling</span></span>](advanced-ink-handling.md)
- <span data-ttu-id="bb808-153">[访问和操作笔输入](https://docs.microsoft.com/previous-versions/ms818317(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="bb808-153">[Accessing and Manipulating Pen Input](https://docs.microsoft.com/previous-versions/ms818317(v=msdn.10))</span></span>
