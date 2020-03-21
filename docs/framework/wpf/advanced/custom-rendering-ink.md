---
title: 自定义呈现墨迹
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom-rendering ink
- ink [WPF], custom-rendering
- classes [WPF], InkCanvas
ms.assetid: 65c978a7-0ee0-454f-ac7f-b1bd2efecac5
ms.openlocfilehash: 0ceb831057a9a92aa7319d2004f04d7cf5ac820e
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111824"
---
# <a name="custom-rendering-ink"></a><span data-ttu-id="5ba47-102">自定义呈现墨迹</span><span class="sxs-lookup"><span data-stu-id="5ba47-102">Custom Rendering Ink</span></span>
<span data-ttu-id="5ba47-103">描<xref:System.Windows.Ink.Stroke.DrawingAttributes%2A>边的属性允许您指定描边的外观，例如其大小、颜色和形状，但有时可能需要自定义超出<xref:System.Windows.Ink.Stroke.DrawingAttributes%2A>允许的外观。</span><span class="sxs-lookup"><span data-stu-id="5ba47-103">The <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> property of a stroke allows you to specify the appearance of a stroke, such as its size, color, and shape, but there may be times that you want to customize the appearance beyond what <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> allow.</span></span> <span data-ttu-id="5ba47-104">建议通过使用喷笔、油画和多种其他效果呈现外观，从而自定义墨迹的外观。</span><span class="sxs-lookup"><span data-stu-id="5ba47-104">You may want to customize the appearance of ink by rendering in the appearance of an air brush, oil paint, and many other effects.</span></span> <span data-ttu-id="5ba47-105">Windows 演示文稿基础 （WPF） 允许您通过实现自定义<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>和<xref:System.Windows.Ink.Stroke>对象来自定义渲染墨迹。</span><span class="sxs-lookup"><span data-stu-id="5ba47-105">The Windows Presentation Foundation (WPF) allows you to custom render ink by implementing a custom <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> and <xref:System.Windows.Ink.Stroke> object.</span></span>  
  
 <span data-ttu-id="5ba47-106">本主题包含以下小节：</span><span class="sxs-lookup"><span data-stu-id="5ba47-106">This topic contains the following subsections:</span></span>  
  
- [<span data-ttu-id="5ba47-107">建筑</span><span class="sxs-lookup"><span data-stu-id="5ba47-107">Architecture</span></span>](#Architecture)  
  
- [<span data-ttu-id="5ba47-108">实现动态呈现器</span><span class="sxs-lookup"><span data-stu-id="5ba47-108">Implementing a Dynamic Renderer</span></span>](#ImplementingADynamicRenderer)  
  
- [<span data-ttu-id="5ba47-109">实现自定义笔划</span><span class="sxs-lookup"><span data-stu-id="5ba47-109">Implementing Custom Strokes</span></span>](#ImplementingCustomStrokes)  
  
- [<span data-ttu-id="5ba47-110">实现自定义 InkCanvas</span><span class="sxs-lookup"><span data-stu-id="5ba47-110">Implementing a Custom InkCanvas</span></span>](#ImplementingACustomInkCanvas)  
  
- [<span data-ttu-id="5ba47-111">结论</span><span class="sxs-lookup"><span data-stu-id="5ba47-111">Conclusion</span></span>](#Conclusion)  
  
<a name="Architecture"></a>
## <a name="architecture"></a><span data-ttu-id="5ba47-112">体系结构</span><span class="sxs-lookup"><span data-stu-id="5ba47-112">Architecture</span></span>  
 <span data-ttu-id="5ba47-113">墨迹呈现会出现两次：用户将墨迹写入墨迹书写表面时，以及将笔划添加到启用了墨迹的表面之后。</span><span class="sxs-lookup"><span data-stu-id="5ba47-113">Ink rendering occurs two times; when a user writes ink to an inking surface, and again after the stroke is added to the ink-enabled surface.</span></span> <span data-ttu-id="5ba47-114">当用户<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>在数字化器上移动 Tablet 笔时，渲<xref:System.Windows.Ink.Stroke>染墨迹，并在将 Tablet 笔添加到元素后渲染。</span><span class="sxs-lookup"><span data-stu-id="5ba47-114">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> renders the ink when the user moves the tablet pen on the digitizer, and the <xref:System.Windows.Ink.Stroke> renders itself once it is added to an element.</span></span>  
  
 <span data-ttu-id="5ba47-115">动态呈现墨迹时需要实现三个类。</span><span class="sxs-lookup"><span data-stu-id="5ba47-115">There are three classes to implement when dynamically rendering ink.</span></span>  
  
1. <span data-ttu-id="5ba47-116">**动态呈现器**：实现派生自<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>的类。</span><span class="sxs-lookup"><span data-stu-id="5ba47-116">**DynamicRenderer**: Implement a class that derives from <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.</span></span> <span data-ttu-id="5ba47-117">此类是专门<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>化的，用于在绘制描边时呈现笔画。</span><span class="sxs-lookup"><span data-stu-id="5ba47-117">This class is a specialized <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> that renders the stroke as it is drawn.</span></span> <span data-ttu-id="5ba47-118">在<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>单独的线程上执行渲染，因此，即使应用程序用户界面 （UI） 线程被阻止，墨迹表面也会显示收集墨迹。</span><span class="sxs-lookup"><span data-stu-id="5ba47-118">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> does the rendering on a separate thread, so the inking surface appears to collect ink even when the application user interface (UI) thread is blocked.</span></span> <span data-ttu-id="5ba47-119">有关线程模型的详细信息，请参阅[墨迹线程模型](the-ink-threading-model.md)。</span><span class="sxs-lookup"><span data-stu-id="5ba47-119">For more information about the threading model, see [The Ink Threading Model](the-ink-threading-model.md).</span></span> <span data-ttu-id="5ba47-120">要自定义动态渲染描边，请重写<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="5ba47-120">To customize dynamically rendering a stroke, override the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> method.</span></span>  
  
2. <span data-ttu-id="5ba47-121">**描边**：实现派生自<xref:System.Windows.Ink.Stroke>的类。</span><span class="sxs-lookup"><span data-stu-id="5ba47-121">**Stroke**: Implement a class that derives from <xref:System.Windows.Ink.Stroke>.</span></span> <span data-ttu-id="5ba47-122">此类负责<xref:System.Windows.Input.StylusPoint>将数据转换为<xref:System.Windows.Ink.Stroke>对象后静态呈现数据。</span><span class="sxs-lookup"><span data-stu-id="5ba47-122">This class is responsible for static rendering of the <xref:System.Windows.Input.StylusPoint> data after it has been converted into a <xref:System.Windows.Ink.Stroke> object.</span></span> <span data-ttu-id="5ba47-123">重写<xref:System.Windows.Ink.Stroke.DrawCore%2A>方法以确保描边的静态呈现与动态渲染一致。</span><span class="sxs-lookup"><span data-stu-id="5ba47-123">Override the <xref:System.Windows.Ink.Stroke.DrawCore%2A> method to ensure that static rendering of the stroke is consistent with dynamic rendering.</span></span>  
  
3. <span data-ttu-id="5ba47-124">**墨水画布：** 实现派生自<xref:System.Windows.Controls.InkCanvas>的类。</span><span class="sxs-lookup"><span data-stu-id="5ba47-124">**InkCanvas:** Implement a class that derives from <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="5ba47-125">将自定义<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>属性分配给<xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="5ba47-125">Assign the customized <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> property.</span></span> <span data-ttu-id="5ba47-126">重写<xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A>方法并将自定义描边添加到<xref:System.Windows.Controls.InkCanvas.Strokes%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="5ba47-126">Override the <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> method and add a custom stroke to the <xref:System.Windows.Controls.InkCanvas.Strokes%2A> property.</span></span> <span data-ttu-id="5ba47-127">这样可以确保墨迹外观一致。</span><span class="sxs-lookup"><span data-stu-id="5ba47-127">This ensures that the appearance of the ink is consistent.</span></span>  
  
<a name="ImplementingADynamicRenderer"></a>
## <a name="implementing-a-dynamic-renderer"></a><span data-ttu-id="5ba47-128">实现动态呈现器</span><span class="sxs-lookup"><span data-stu-id="5ba47-128">Implementing a Dynamic Renderer</span></span>  
 <span data-ttu-id="5ba47-129">尽管<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>类是 的标准部分[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，但要执行更专用的渲染，则必须创建从 派生<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>并重写<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A>方法的自定义动态渲染器。</span><span class="sxs-lookup"><span data-stu-id="5ba47-129">Although the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> class is a standard part of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], to perform more specialized rendering, you must create a customized dynamic renderer that derives from the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> and override the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> method.</span></span>  
  
 <span data-ttu-id="5ba47-130">下面的示例演示了使用线性<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>渐变画笔效果绘制墨迹的自定义。</span><span class="sxs-lookup"><span data-stu-id="5ba47-130">The following example demonstrates a customized <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> that draws ink with a linear gradient brush effect.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#1](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#1)]
[!code-vb[AdvancedInkTopicsSamples#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#1)]  
  
<a name="ImplementingCustomStrokes"></a>
## <a name="implementing-custom-strokes"></a><span data-ttu-id="5ba47-131">实现自定义笔划</span><span class="sxs-lookup"><span data-stu-id="5ba47-131">Implementing Custom Strokes</span></span>  
 <span data-ttu-id="5ba47-132">实现从 <xref:System.Windows.Ink.Stroke> 派生的类。</span><span class="sxs-lookup"><span data-stu-id="5ba47-132">Implement a class that derives from <xref:System.Windows.Ink.Stroke>.</span></span> <span data-ttu-id="5ba47-133">此类负责将数据转换为<xref:System.Windows.Input.StylusPoint><xref:System.Windows.Ink.Stroke>对象后呈现数据。</span><span class="sxs-lookup"><span data-stu-id="5ba47-133">This class is responsible for rendering <xref:System.Windows.Input.StylusPoint> data after it has been converted into a <xref:System.Windows.Ink.Stroke> object.</span></span> <span data-ttu-id="5ba47-134">重写类<xref:System.Windows.Ink.Stroke.DrawCore%2A>以执行实际绘图。</span><span class="sxs-lookup"><span data-stu-id="5ba47-134">Override the <xref:System.Windows.Ink.Stroke.DrawCore%2A> class to do the actual drawing.</span></span>  
  
 <span data-ttu-id="5ba47-135">笔画类还可以使用 方法<xref:System.Windows.Ink.Stroke.AddPropertyData%2A>存储自定义数据。</span><span class="sxs-lookup"><span data-stu-id="5ba47-135">Your Stroke class can also store custom data by using the <xref:System.Windows.Ink.Stroke.AddPropertyData%2A> method.</span></span> <span data-ttu-id="5ba47-136">此数据持续存在时会与笔划数据一起存储。</span><span class="sxs-lookup"><span data-stu-id="5ba47-136">This data is stored with the stroke data when persisted.</span></span>  
  
 <span data-ttu-id="5ba47-137">该<xref:System.Windows.Ink.Stroke>类还可以执行命中测试。</span><span class="sxs-lookup"><span data-stu-id="5ba47-137">The <xref:System.Windows.Ink.Stroke> class can also perform hit testing.</span></span> <span data-ttu-id="5ba47-138">您还可以通过重写当前类中<xref:System.Windows.Ink.Stroke.HitTest%2A>的方法来实现您自己的命中测试算法。</span><span class="sxs-lookup"><span data-stu-id="5ba47-138">You can also implement your own hit testing algorithm by overriding the <xref:System.Windows.Ink.Stroke.HitTest%2A> method in the current class.</span></span>  
  
 <span data-ttu-id="5ba47-139">以下 C# 代码演示了<xref:System.Windows.Ink.Stroke>将<xref:System.Windows.Input.StylusPoint>数据呈现为 3D 描边的自定义类。</span><span class="sxs-lookup"><span data-stu-id="5ba47-139">The following C# code demonstrates a custom <xref:System.Windows.Ink.Stroke> class that renders <xref:System.Windows.Input.StylusPoint> data as a 3D stroke.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#2](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#2)]
[!code-vb[AdvancedInkTopicsSamples#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#2)]  
  
<a name="ImplementingACustomInkCanvas"></a>
## <a name="implementing-a-custom-inkcanvas"></a><span data-ttu-id="5ba47-140">实现自定义 InkCanvas</span><span class="sxs-lookup"><span data-stu-id="5ba47-140">Implementing a Custom InkCanvas</span></span>  
 <span data-ttu-id="5ba47-141">使用自定义<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>和描边的最简单方法是实现派生并<xref:System.Windows.Controls.InkCanvas>使用这些类的类。</span><span class="sxs-lookup"><span data-stu-id="5ba47-141">The easiest way to use your customized <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> and stroke is to implement a class that derives from <xref:System.Windows.Controls.InkCanvas> and uses these classes.</span></span> <span data-ttu-id="5ba47-142">具有<xref:System.Windows.Controls.InkCanvas>一个<xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A>属性，用于指定在用户绘制描边时如何呈现笔画。</span><span class="sxs-lookup"><span data-stu-id="5ba47-142">The <xref:System.Windows.Controls.InkCanvas> has a <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> property that specifies how the stroke is rendered when the user is drawing it.</span></span>  
  
 <span data-ttu-id="5ba47-143">要在 操作<xref:System.Windows.Controls.InkCanvas>上自定义渲染描边，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5ba47-143">To custom render strokes on an <xref:System.Windows.Controls.InkCanvas> do the following:</span></span>  
  
- <span data-ttu-id="5ba47-144">创建派生自 的<xref:System.Windows.Controls.InkCanvas>类。</span><span class="sxs-lookup"><span data-stu-id="5ba47-144">Create a class that derives from the <xref:System.Windows.Controls.InkCanvas>.</span></span>  
  
- <span data-ttu-id="5ba47-145">将自定义属性<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>分配给属性<xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="5ba47-145">Assign your customized <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A?displayProperty=nameWithType> property.</span></span>  
  
- <span data-ttu-id="5ba47-146">重写 <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="5ba47-146">Override the <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> method.</span></span> <span data-ttu-id="5ba47-147">使用此方法时，请删除之前添加到 InkCanvas 的原始笔划。</span><span class="sxs-lookup"><span data-stu-id="5ba47-147">In this method, remove the original stroke that was added to the InkCanvas.</span></span> <span data-ttu-id="5ba47-148">然后创建自定义描边，将其添加到属性，<xref:System.Windows.Controls.InkCanvas.Strokes%2A>然后用包含自定义描边的新项<xref:System.Windows.Controls.InkCanvasStrokeCollectedEventArgs>调用基类。</span><span class="sxs-lookup"><span data-stu-id="5ba47-148">Then create a custom stroke, add it to the <xref:System.Windows.Controls.InkCanvas.Strokes%2A> property, and call the base class with a new <xref:System.Windows.Controls.InkCanvasStrokeCollectedEventArgs> that contains the custom stroke.</span></span>  
  
 <span data-ttu-id="5ba47-149">以下 C# 代码演示了<xref:System.Windows.Controls.InkCanvas>使用自定义<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>和收集自定义描边的自定义类。</span><span class="sxs-lookup"><span data-stu-id="5ba47-149">The following C# code demonstrates a custom <xref:System.Windows.Controls.InkCanvas> class that uses a customized <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> and collects custom strokes.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#9)]  
  
 <span data-ttu-id="5ba47-150">可以<xref:System.Windows.Controls.InkCanvas>有多个<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>。</span><span class="sxs-lookup"><span data-stu-id="5ba47-150">An <xref:System.Windows.Controls.InkCanvas> can have more than one <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.</span></span> <span data-ttu-id="5ba47-151">通过将多个对象添加到<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer><xref:System.Windows.UIElement.StylusPlugIns%2A>属性，<xref:System.Windows.Controls.InkCanvas>可以向 添加多个对象。</span><span class="sxs-lookup"><span data-stu-id="5ba47-151">You can add multiple <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> objects to the <xref:System.Windows.Controls.InkCanvas> by adding them to the <xref:System.Windows.UIElement.StylusPlugIns%2A> property.</span></span>  
  
<a name="Conclusion"></a>
## <a name="conclusion"></a><span data-ttu-id="5ba47-152">结束语</span><span class="sxs-lookup"><span data-stu-id="5ba47-152">Conclusion</span></span>  
 <span data-ttu-id="5ba47-153">您可以通过派生自己的<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>和<xref:System.Windows.Ink.Stroke><xref:System.Windows.Controls.InkCanvas>类来自定义墨迹的外观。</span><span class="sxs-lookup"><span data-stu-id="5ba47-153">You can customize the appearance of ink by deriving your own <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, <xref:System.Windows.Ink.Stroke>, and <xref:System.Windows.Controls.InkCanvas> classes.</span></span> <span data-ttu-id="5ba47-154">将这些类结合使用可以确保用户绘制笔划时和笔划被收集后的笔划外观保持一致。</span><span class="sxs-lookup"><span data-stu-id="5ba47-154">Together, these classes ensure that the appearance of the stroke is consistent when the user draws the stroke and after it is collected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ba47-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ba47-155">See also</span></span>

- [<span data-ttu-id="5ba47-156">高级墨迹处理</span><span class="sxs-lookup"><span data-stu-id="5ba47-156">Advanced Ink Handling</span></span>](advanced-ink-handling.md)
