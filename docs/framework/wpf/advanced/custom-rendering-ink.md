---
title: "自定义呈现墨迹"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom-rendering ink
- ink [WPF], custom-rendering
- classes [WPF], InkCanvas
ms.assetid: 65c978a7-0ee0-454f-ac7f-b1bd2efecac5
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 481990acdf2f5b8f798144d36434569b9e2cd481
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="custom-rendering-ink"></a><span data-ttu-id="ee433-102">自定义呈现墨迹</span><span class="sxs-lookup"><span data-stu-id="ee433-102">Custom Rendering Ink</span></span>
<span data-ttu-id="ee433-103"><xref:System.Windows.Ink.Stroke.DrawingAttributes%2A>笔画属性允许你指定的外观描边，如其大小、 颜色和形状，但可能有些时候你想要自定义超出什么外观<xref:System.Windows.Ink.Stroke.DrawingAttributes%2A>允许。</span><span class="sxs-lookup"><span data-stu-id="ee433-103">The <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> property of a stroke allows you to specify the appearance of a stroke, such as its size, color, and shape, but there may be times that you want to customize the appearance beyond what <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> allow.</span></span> <span data-ttu-id="ee433-104">建议通过使用喷笔、油画和多种其他效果呈现外观，从而自定义墨迹的外观。</span><span class="sxs-lookup"><span data-stu-id="ee433-104">You may want to customize the appearance of ink by rendering in the appearance of an air brush, oil paint, and many other effects.</span></span> <span data-ttu-id="ee433-105">[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]允许你自定义实现自定义呈现墨迹<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>和<xref:System.Windows.Ink.Stroke>对象。</span><span class="sxs-lookup"><span data-stu-id="ee433-105">The [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] allows you to custom render ink by implementing a custom <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> and <xref:System.Windows.Ink.Stroke> object.</span></span>  
  
 <span data-ttu-id="ee433-106">本主题包含以下小节：</span><span class="sxs-lookup"><span data-stu-id="ee433-106">This topic contains the following subsections:</span></span>  
  
-   [<span data-ttu-id="ee433-107">体系结构</span><span class="sxs-lookup"><span data-stu-id="ee433-107">Architecture</span></span>](#Architecture)  
  
-   [<span data-ttu-id="ee433-108">实现动态呈现器</span><span class="sxs-lookup"><span data-stu-id="ee433-108">Implementing a Dynamic Renderer</span></span>](#ImplementingADynamicRenderer)  
  
-   [<span data-ttu-id="ee433-109">实现自定义笔划</span><span class="sxs-lookup"><span data-stu-id="ee433-109">Implementing Custom Strokes</span></span>](#ImplementingCustomStrokes)  
  
-   [<span data-ttu-id="ee433-110">实现自定义 InkCanvas</span><span class="sxs-lookup"><span data-stu-id="ee433-110">Implementing a Custom InkCanvas</span></span>](#ImplementingACustomInkCanvas)  
  
-   [<span data-ttu-id="ee433-111">结束语</span><span class="sxs-lookup"><span data-stu-id="ee433-111">Conclusion</span></span>](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a><span data-ttu-id="ee433-112">体系结构</span><span class="sxs-lookup"><span data-stu-id="ee433-112">Architecture</span></span>  
 <span data-ttu-id="ee433-113">墨迹呈现会出现两次：用户将墨迹写入墨迹书写表面时，以及将笔划添加到启用了墨迹的表面之后。</span><span class="sxs-lookup"><span data-stu-id="ee433-113">Ink rendering occurs two times; when a user writes ink to an inking surface, and again after the stroke is added to the ink-enabled surface.</span></span> <span data-ttu-id="ee433-114"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>当用户将触笔数字化仪上, 呈现墨迹和<xref:System.Windows.Ink.Stroke>添加到元素后呈现自身。</span><span class="sxs-lookup"><span data-stu-id="ee433-114">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> renders the ink when the user moves the tablet pen on the digitizer, and the <xref:System.Windows.Ink.Stroke> renders itself once it is added to an element.</span></span>  
  
 <span data-ttu-id="ee433-115">动态呈现墨迹时需要实现三个类。</span><span class="sxs-lookup"><span data-stu-id="ee433-115">There are three classes to implement when dynamically rendering ink.</span></span>  
  
1.  <span data-ttu-id="ee433-116">**DynamicRenderer**： 实现派生自类<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>。</span><span class="sxs-lookup"><span data-stu-id="ee433-116">**DynamicRenderer**: Implement a class that derives from <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.</span></span> <span data-ttu-id="ee433-117">此类是一个专用<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>时进行绘制，呈现笔画。</span><span class="sxs-lookup"><span data-stu-id="ee433-117">This class is a specialized <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> that renders the stroke as it is drawn.</span></span> <span data-ttu-id="ee433-118"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>上进行呈现一个单独的线程，因此墨迹图面显示为收集墨迹，即使应用程序用户界面 (UI) 线程被阻止。</span><span class="sxs-lookup"><span data-stu-id="ee433-118">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> does the rendering on a separate thread, so the inking surface appears to collect ink even when the application user interface (UI) thread is blocked.</span></span> <span data-ttu-id="ee433-119">有关线程模型的详细信息，请参阅[墨迹线程模型](../../../../docs/framework/wpf/advanced/the-ink-threading-model.md)。</span><span class="sxs-lookup"><span data-stu-id="ee433-119">For more information about the threading model, see [The Ink Threading Model](../../../../docs/framework/wpf/advanced/the-ink-threading-model.md).</span></span> <span data-ttu-id="ee433-120">若要自定义动态呈现描边，重写<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="ee433-120">To customize dynamically rendering a stroke, override the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> method.</span></span>  
  
2.  <span data-ttu-id="ee433-121">**笔画**： 实现派生自类<xref:System.Windows.Ink.Stroke>。</span><span class="sxs-lookup"><span data-stu-id="ee433-121">**Stroke**: Implement a class that derives from <xref:System.Windows.Ink.Stroke>.</span></span> <span data-ttu-id="ee433-122">此类负责静态呈现<xref:System.Windows.Input.StylusPoint>数据后已转换为<xref:System.Windows.Ink.Stroke>对象。</span><span class="sxs-lookup"><span data-stu-id="ee433-122">This class is responsible for static rendering of the <xref:System.Windows.Input.StylusPoint> data after it has been converted into a <xref:System.Windows.Ink.Stroke> object.</span></span> <span data-ttu-id="ee433-123">重写<xref:System.Windows.Ink.Stroke.DrawCore%2A>方法，以确保该静态呈现的笔划的是与动态呈现一致。</span><span class="sxs-lookup"><span data-stu-id="ee433-123">Override the <xref:System.Windows.Ink.Stroke.DrawCore%2A> method to ensure that static rendering of the stroke is consistent with dynamic rendering.</span></span>  
  
3.  <span data-ttu-id="ee433-124">**InkCanvas:**实现派生自类<xref:System.Windows.Controls.InkCanvas>。</span><span class="sxs-lookup"><span data-stu-id="ee433-124">**InkCanvas:** Implement a class that derives from <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="ee433-125">分配的自定义<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>到<xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="ee433-125">Assign the customized <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> property.</span></span> <span data-ttu-id="ee433-126">重写<xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A>方法并添加到自定义笔画<xref:System.Windows.Controls.InkCanvas.Strokes%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="ee433-126">Override the <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> method and add a custom stroke to the <xref:System.Windows.Controls.InkCanvas.Strokes%2A> property.</span></span> <span data-ttu-id="ee433-127">这样可以确保墨迹外观一致。</span><span class="sxs-lookup"><span data-stu-id="ee433-127">This ensures that the appearance of the ink is consistent.</span></span>  
  
<a name="ImplementingADynamicRenderer"></a>   
## <a name="implementing-a-dynamic-renderer"></a><span data-ttu-id="ee433-128">实现动态呈现器</span><span class="sxs-lookup"><span data-stu-id="ee433-128">Implementing a Dynamic Renderer</span></span>  
 <span data-ttu-id="ee433-129">尽管<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>类是标准的一部分[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，若要进行更专业的呈现，则必须创建自定义动态呈现器，派生自<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>，并重写<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="ee433-129">Although the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> class is a standard part of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], to perform more specialized rendering, you must create a customized dynamic renderer that derives from the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> and override the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> method.</span></span>  
  
 <span data-ttu-id="ee433-130">下面的示例演示自定义<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>绘制带有线性渐变画笔效果墨迹。</span><span class="sxs-lookup"><span data-stu-id="ee433-130">The following example demonstrates a customized <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> that draws ink with a linear gradient brush effect.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#1)]
[!code-vb[AdvancedInkTopicsSamples#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#1)]  
  
<a name="ImplementingCustomStrokes"></a>   
## <a name="implementing-custom-strokes"></a><span data-ttu-id="ee433-131">实现自定义笔划</span><span class="sxs-lookup"><span data-stu-id="ee433-131">Implementing Custom Strokes</span></span>  
 <span data-ttu-id="ee433-132">实现从 <xref:System.Windows.Ink.Stroke> 派生的类。</span><span class="sxs-lookup"><span data-stu-id="ee433-132">Implement a class that derives from <xref:System.Windows.Ink.Stroke>.</span></span> <span data-ttu-id="ee433-133">此类负责呈现<xref:System.Windows.Input.StylusPoint>数据后已转换为<xref:System.Windows.Ink.Stroke>对象。</span><span class="sxs-lookup"><span data-stu-id="ee433-133">This class is responsible for rendering <xref:System.Windows.Input.StylusPoint> data after it has been converted into a <xref:System.Windows.Ink.Stroke> object.</span></span> <span data-ttu-id="ee433-134">重写<xref:System.Windows.Ink.Stroke.DrawCore%2A>类来执行实际的绘图。</span><span class="sxs-lookup"><span data-stu-id="ee433-134">Override the <xref:System.Windows.Ink.Stroke.DrawCore%2A> class to do the actual drawing.</span></span>  
  
 <span data-ttu-id="ee433-135">您的 Stroke 类还可以通过使用存储自定义数据<xref:System.Windows.Ink.Stroke.AddPropertyData%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="ee433-135">Your Stroke class can also store custom data by using the <xref:System.Windows.Ink.Stroke.AddPropertyData%2A> method.</span></span> <span data-ttu-id="ee433-136">此数据持续存在时会与笔划数据一起存储。</span><span class="sxs-lookup"><span data-stu-id="ee433-136">This data is stored with the stroke data when persisted.</span></span>  
  
 <span data-ttu-id="ee433-137"><xref:System.Windows.Ink.Stroke>类还可以执行的命中测试。</span><span class="sxs-lookup"><span data-stu-id="ee433-137">The <xref:System.Windows.Ink.Stroke> class can also perform hit testing.</span></span> <span data-ttu-id="ee433-138">你也可以实现你自己的命中测试算法通过重写<xref:System.Windows.Ink.Stroke.HitTest%2A>当前类中的方法。</span><span class="sxs-lookup"><span data-stu-id="ee433-138">You can also implement your own hit testing algorithm by overriding the <xref:System.Windows.Ink.Stroke.HitTest%2A> method in the current class.</span></span>  
  
 <span data-ttu-id="ee433-139">下面的 C# 代码演示自定义<xref:System.Windows.Ink.Stroke>呈现类的<xref:System.Windows.Input.StylusPoint>为三维描边的数据。</span><span class="sxs-lookup"><span data-stu-id="ee433-139">The following C# code demonstrates a custom <xref:System.Windows.Ink.Stroke> class that renders <xref:System.Windows.Input.StylusPoint> data as a 3-D stroke.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#2)]
[!code-vb[AdvancedInkTopicsSamples#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#2)]  
  
<a name="ImplementingACustomInkCanvas"></a>   
## <a name="implementing-a-custom-inkcanvas"></a><span data-ttu-id="ee433-140">实现自定义 InkCanvas</span><span class="sxs-lookup"><span data-stu-id="ee433-140">Implementing a Custom InkCanvas</span></span>  
 <span data-ttu-id="ee433-141">使用你自定义的最简单办法<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>和描边是实现派生自的类<xref:System.Windows.Controls.InkCanvas>并使用这些类。</span><span class="sxs-lookup"><span data-stu-id="ee433-141">The easiest way to use your customized <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> and stroke is to implement a class that derives from <xref:System.Windows.Controls.InkCanvas> and uses these classes.</span></span> <span data-ttu-id="ee433-142"><xref:System.Windows.Controls.InkCanvas>具有<xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A>属性，用于指定当用户在绘制时描边的呈现方式。</span><span class="sxs-lookup"><span data-stu-id="ee433-142">The <xref:System.Windows.Controls.InkCanvas> has a <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> property that specifies how the stroke is rendered when the user is drawing it.</span></span>  
  
 <span data-ttu-id="ee433-143">自定义上呈现笔画<xref:System.Windows.Controls.InkCanvas>执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ee433-143">To custom render strokes on an <xref:System.Windows.Controls.InkCanvas> do the following:</span></span>  
  
-   <span data-ttu-id="ee433-144">创建一个类，派生自<xref:System.Windows.Controls.InkCanvas>。</span><span class="sxs-lookup"><span data-stu-id="ee433-144">Create a class that derives from the <xref:System.Windows.Controls.InkCanvas>.</span></span>  
  
-   <span data-ttu-id="ee433-145">分配你自定义<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>到<xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="ee433-145">Assign your customized <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A?displayProperty=nameWithType> property.</span></span>  
  
-   <span data-ttu-id="ee433-146">重写 <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="ee433-146">Override the <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> method.</span></span> <span data-ttu-id="ee433-147">使用此方法时，请删除之前添加到 InkCanvas 的原始笔划。</span><span class="sxs-lookup"><span data-stu-id="ee433-147">In this method, remove the original stroke that was added to the InkCanvas.</span></span> <span data-ttu-id="ee433-148">然后创建自定义的描边，将其添加到<xref:System.Windows.Controls.InkCanvas.Strokes%2A>属性并调用包含一个新的基类<xref:System.Windows.Controls.InkCanvasStrokeCollectedEventArgs>，其中包含自定义描边。</span><span class="sxs-lookup"><span data-stu-id="ee433-148">Then create a custom stroke, add it to the <xref:System.Windows.Controls.InkCanvas.Strokes%2A> property, and call the base class with a new <xref:System.Windows.Controls.InkCanvasStrokeCollectedEventArgs> that contains the custom stroke.</span></span>  
  
 <span data-ttu-id="ee433-149">下面的 C# 代码演示自定义<xref:System.Windows.Controls.InkCanvas>使用自定义的类<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>和收集自定义描边。</span><span class="sxs-lookup"><span data-stu-id="ee433-149">The following C# code demonstrates a custom <xref:System.Windows.Controls.InkCanvas> class that uses a customized <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> and collects custom strokes.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#9)]  
  
 <span data-ttu-id="ee433-150"><xref:System.Windows.Controls.InkCanvas>可以有多个<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>。</span><span class="sxs-lookup"><span data-stu-id="ee433-150">An <xref:System.Windows.Controls.InkCanvas> can have more than one <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.</span></span> <span data-ttu-id="ee433-151">你可以添加多个<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>对象添加到<xref:System.Windows.Controls.InkCanvas>通过将它们添加到<xref:System.Windows.UIElement.StylusPlugIns%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="ee433-151">You can add multiple <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> objects to the <xref:System.Windows.Controls.InkCanvas> by adding them to the <xref:System.Windows.UIElement.StylusPlugIns%2A> property.</span></span>  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a><span data-ttu-id="ee433-152">结束语</span><span class="sxs-lookup"><span data-stu-id="ee433-152">Conclusion</span></span>  
 <span data-ttu-id="ee433-153">你可以通过派生您自己自定义墨迹的外观<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>， <xref:System.Windows.Ink.Stroke>，和<xref:System.Windows.Controls.InkCanvas>类。</span><span class="sxs-lookup"><span data-stu-id="ee433-153">You can customize the appearance of ink by deriving your own <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, <xref:System.Windows.Ink.Stroke>, and <xref:System.Windows.Controls.InkCanvas> classes.</span></span> <span data-ttu-id="ee433-154">将这些类结合使用可以确保用户绘制笔划时和笔划被收集后的笔划外观保持一致。</span><span class="sxs-lookup"><span data-stu-id="ee433-154">Together, these classes ensure that the appearance of the stroke is consistent when the user draws the stroke and after it is collected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee433-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="ee433-155">See Also</span></span>  
 [<span data-ttu-id="ee433-156">高级墨迹处理</span><span class="sxs-lookup"><span data-stu-id="ee433-156">Advanced Ink Handling</span></span>](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)
