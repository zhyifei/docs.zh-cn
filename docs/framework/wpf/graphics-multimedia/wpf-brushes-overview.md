---
title: WPF 画笔概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], about brushes
ms.assetid: ecea1955-420b-45c6-bf43-c1404c072c41
ms.openlocfilehash: 8a1d05ad48ce75ce67d21d5a4d508015fea879b2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458622"
---
# <a name="wpf-brushes-overview"></a><span data-ttu-id="89d76-102">WPF 画笔概述</span><span class="sxs-lookup"><span data-stu-id="89d76-102">WPF Brushes Overview</span></span>
<span data-ttu-id="89d76-103">屏幕上可见的所有内容都可见，因为它是由画笔绘制的。</span><span class="sxs-lookup"><span data-stu-id="89d76-103">Everything visible on your screen is visible because it was painted by a brush.</span></span> <span data-ttu-id="89d76-104">例如，画笔用于描述按钮的背景、文本的前景和形状的填充效果。</span><span class="sxs-lookup"><span data-stu-id="89d76-104">For example, a brush is used to describe the background of a button, the foreground of text, and the fill of a shape.</span></span> <span data-ttu-id="89d76-105">本主题介绍与 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 画笔进行绘制的概念，并提供示例。</span><span class="sxs-lookup"><span data-stu-id="89d76-105">This topic introduces the concepts of painting with [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] brushes and provides examples.</span></span> <span data-ttu-id="89d76-106">借助画笔，可以利用任意内容（从简单的纯色到复杂的图案和图像集）绘制 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 对象。</span><span class="sxs-lookup"><span data-stu-id="89d76-106">Brushes enable you to paint [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] objects with anything from simple, solid colors to complex sets of patterns and images.</span></span>  
  
<a name="paintingwithbrush"></a>   
## <a name="painting-with-a-brush"></a><span data-ttu-id="89d76-107">使用画笔进行绘制</span><span class="sxs-lookup"><span data-stu-id="89d76-107">Painting with a Brush</span></span>  
 <span data-ttu-id="89d76-108"><xref:System.Windows.Media.Brush> "绘制" 带有其输出的区域。</span><span class="sxs-lookup"><span data-stu-id="89d76-108">A <xref:System.Windows.Media.Brush> "paints" an area with its output.</span></span> <span data-ttu-id="89d76-109">不同的画笔具有不同类型的输出。</span><span class="sxs-lookup"><span data-stu-id="89d76-109">Different brushes have different types of output.</span></span> <span data-ttu-id="89d76-110">某些画笔使用纯色绘制区域，其他画笔使用渐变、图案、图像或绘图。</span><span class="sxs-lookup"><span data-stu-id="89d76-110">Some brushes paint an area with a solid color, others with a gradient, pattern, image, or drawing.</span></span> <span data-ttu-id="89d76-111">下图显示了每种不同 <xref:System.Windows.Media.Brush> 类型的示例。</span><span class="sxs-lookup"><span data-stu-id="89d76-111">The following illustration shows examples of each of the different <xref:System.Windows.Media.Brush> types.</span></span>  
  
 <span data-ttu-id="89d76-112">![画笔类型](./media/graphicsmm-brushtypes.jpg "graphicsmm_brushtypes")</span><span class="sxs-lookup"><span data-stu-id="89d76-112">![Brush types](./media/graphicsmm-brushtypes.jpg "graphicsmm_brushtypes")</span></span>  
<span data-ttu-id="89d76-113">画笔示例</span><span class="sxs-lookup"><span data-stu-id="89d76-113">Brush examples</span></span>  
  
 <span data-ttu-id="89d76-114">大多数视觉对象使您能够指定如何绘制它们。</span><span class="sxs-lookup"><span data-stu-id="89d76-114">Most visual objects enable you to specify how they are painted.</span></span> <span data-ttu-id="89d76-115">下表列出了一些可以使用 <xref:System.Windows.Media.Brush>的常见对象和属性。</span><span class="sxs-lookup"><span data-stu-id="89d76-115">The following table lists some common objects and properties with which you can use a <xref:System.Windows.Media.Brush>.</span></span>  
  
|<span data-ttu-id="89d76-116">实例</span><span class="sxs-lookup"><span data-stu-id="89d76-116">Class</span></span>|<span data-ttu-id="89d76-117">画笔属性</span><span class="sxs-lookup"><span data-stu-id="89d76-117">Brush properties</span></span>|  
|-----------|----------------------|  
|<xref:System.Windows.Controls.Border>|<span data-ttu-id="89d76-118"><xref:System.Windows.Controls.Border.BorderBrush%2A>，<xref:System.Windows.Controls.Border.Background%2A></span><span class="sxs-lookup"><span data-stu-id="89d76-118"><xref:System.Windows.Controls.Border.BorderBrush%2A>, <xref:System.Windows.Controls.Border.Background%2A></span></span>|  
|<xref:System.Windows.Controls.Control>|<span data-ttu-id="89d76-119"><xref:System.Windows.Controls.Control.Background%2A>，<xref:System.Windows.Controls.Control.Foreground%2A></span><span class="sxs-lookup"><span data-stu-id="89d76-119"><xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A></span></span>|  
|<xref:System.Windows.Controls.Panel>|<xref:System.Windows.Controls.Panel.Background%2A>|  
|<xref:System.Windows.Media.Pen>|<xref:System.Windows.Media.Pen.Brush%2A>|  
|<xref:System.Windows.Shapes.Shape>|<span data-ttu-id="89d76-120"><xref:System.Windows.Shapes.Shape.Fill%2A>，<xref:System.Windows.Shapes.Shape.Stroke%2A></span><span class="sxs-lookup"><span data-stu-id="89d76-120"><xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A></span></span>|  
|<xref:System.Windows.Controls.TextBlock>|<xref:System.Windows.Controls.TextBlock.Background%2A>|  
  
 <span data-ttu-id="89d76-121">以下各节介绍了不同的 <xref:System.Windows.Media.Brush> 类型，并提供了每种类型的示例。</span><span class="sxs-lookup"><span data-stu-id="89d76-121">The following sections describe the different <xref:System.Windows.Media.Brush> types and provide an example of each.</span></span>  
  
<a name="paintwithsolidcolorbrush"></a>   
## <a name="paint-with-a-solid-color"></a><span data-ttu-id="89d76-122">使用纯色绘制</span><span class="sxs-lookup"><span data-stu-id="89d76-122">Paint with a Solid Color</span></span>  
 <span data-ttu-id="89d76-123"><xref:System.Windows.Media.SolidColorBrush> 使用纯色 <xref:System.Windows.Media.Color>绘制区域。</span><span class="sxs-lookup"><span data-stu-id="89d76-123">A <xref:System.Windows.Media.SolidColorBrush> paints an area with a solid <xref:System.Windows.Media.Color>.</span></span> <span data-ttu-id="89d76-124">有多种方法可以指定 <xref:System.Windows.Media.SolidColorBrush>的 <xref:System.Windows.Media.SolidColorBrush.Color%2A>：例如，可以指定其 alpha、红色、蓝色和绿色通道，或使用 <xref:System.Windows.Media.Colors> 类提供的预定义颜色之一。</span><span class="sxs-lookup"><span data-stu-id="89d76-124">There are a variety of ways to specify the <xref:System.Windows.Media.SolidColorBrush.Color%2A> of a <xref:System.Windows.Media.SolidColorBrush>: for example, you can specify its alpha, red, blue, and green channels or use one of the predefined color provided by the <xref:System.Windows.Media.Colors> class.</span></span>  
  
 <span data-ttu-id="89d76-125">下面的示例使用 <xref:System.Windows.Media.SolidColorBrush> 绘制 <xref:System.Windows.Shapes.Rectangle>的 <xref:System.Windows.Shapes.Shape.Fill%2A>。</span><span class="sxs-lookup"><span data-stu-id="89d76-125">The following example uses a <xref:System.Windows.Media.SolidColorBrush> to paint the <xref:System.Windows.Shapes.Shape.Fill%2A> of a <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="89d76-126">下图显示了绘制的矩形。</span><span class="sxs-lookup"><span data-stu-id="89d76-126">The following illustration shows the painted rectangle.</span></span>  
  
 <span data-ttu-id="89d76-127">![使用 System.windows.media.solidcolorbrush> 绘制的矩形](./media/graphicsmm-brush-ovw-solidcolorbrush.png "graphicsmm_brush_ovw_solidcolorbrush")</span><span class="sxs-lookup"><span data-stu-id="89d76-127">![A rectangle painted using a SolidColorBrush](./media/graphicsmm-brush-ovw-solidcolorbrush.png "graphicsmm_brush_ovw_solidcolorbrush")</span></span>  
<span data-ttu-id="89d76-128">使用 System.windows.media.solidcolorbrush> 绘制的矩形</span><span class="sxs-lookup"><span data-stu-id="89d76-128">A Rectangle painted using a SolidColorBrush</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmsolidcolorbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmsolidcolorbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmsolidcolorbrushexampleinline)]  
  
 <span data-ttu-id="89d76-129">有关 <xref:System.Windows.Media.SolidColorBrush> 类的详细信息，请参阅[采用纯色和渐变进行绘制概述](painting-with-solid-colors-and-gradients-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="89d76-129">For more information about the <xref:System.Windows.Media.SolidColorBrush> class, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
<a name="paintwithlineargradientbrush"></a>   
## <a name="paint-with-a-linear-gradient"></a><span data-ttu-id="89d76-130">使用线性渐变绘制</span><span class="sxs-lookup"><span data-stu-id="89d76-130">Paint with a Linear Gradient</span></span>  
 <span data-ttu-id="89d76-131"><xref:System.Windows.Media.LinearGradientBrush> 使用线性渐变绘制区域。</span><span class="sxs-lookup"><span data-stu-id="89d76-131">A <xref:System.Windows.Media.LinearGradientBrush> paints an area with a linear gradient.</span></span> <span data-ttu-id="89d76-132">线性渐变跨线条（渐变轴）混合两种或多种颜色。</span><span class="sxs-lookup"><span data-stu-id="89d76-132">A linear gradient blends two or more colors across a line, the gradient axis.</span></span> <span data-ttu-id="89d76-133">使用 <xref:System.Windows.Media.GradientStop> 对象来指定渐变中的颜色及其位置。</span><span class="sxs-lookup"><span data-stu-id="89d76-133">You use <xref:System.Windows.Media.GradientStop> objects to specify the colors in the gradient and their positions.</span></span>  
  
 <span data-ttu-id="89d76-134">下面的示例使用 <xref:System.Windows.Media.LinearGradientBrush> 绘制 <xref:System.Windows.Shapes.Rectangle>的 <xref:System.Windows.Shapes.Shape.Fill%2A>。</span><span class="sxs-lookup"><span data-stu-id="89d76-134">The following example uses a <xref:System.Windows.Media.LinearGradientBrush> to paint the <xref:System.Windows.Shapes.Shape.Fill%2A> of a <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="89d76-135">下图显示了绘制的矩形。</span><span class="sxs-lookup"><span data-stu-id="89d76-135">The following illustration shows the painted rectangle.</span></span>  
  
 <span data-ttu-id="89d76-136">![使用 LinearGradientBrush 绘制的矩形](./media/graphicsmm-brush-ovw-lineargradientbrush.jpg "graphicsmm_brush_ovw_lineargradientbrush")</span><span class="sxs-lookup"><span data-stu-id="89d76-136">![A rectangle painted using a LinearGradientBrush](./media/graphicsmm-brush-ovw-lineargradientbrush.jpg "graphicsmm_brush_ovw_lineargradientbrush")</span></span>  
<span data-ttu-id="89d76-137">使用 LinearGradientBrush 绘制的矩形</span><span class="sxs-lookup"><span data-stu-id="89d76-137">A Rectangle painted using a LinearGradientBrush</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmlineargradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmlineargradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmlineargradientbrushexampleinline)]  
  
 <span data-ttu-id="89d76-138">有关 <xref:System.Windows.Media.LinearGradientBrush> 类的详细信息，请参阅[采用纯色和渐变进行绘制概述](painting-with-solid-colors-and-gradients-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="89d76-138">For more information about the <xref:System.Windows.Media.LinearGradientBrush> class, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
<a name="paintwithradialgradientbrush"></a>   
## <a name="paint-with-a-radial-gradient"></a><span data-ttu-id="89d76-139">使用径向渐变绘制</span><span class="sxs-lookup"><span data-stu-id="89d76-139">Paint with a Radial Gradient</span></span>  
 <span data-ttu-id="89d76-140">使用径向渐变绘制区域 <xref:System.Windows.Media.RadialGradientBrush>。</span><span class="sxs-lookup"><span data-stu-id="89d76-140">A <xref:System.Windows.Media.RadialGradientBrush> paints an area with a radial gradient.</span></span> <span data-ttu-id="89d76-141">径向渐变跨一个圆混合两种或多种颜色。</span><span class="sxs-lookup"><span data-stu-id="89d76-141">A radial gradient blends two or more colors across a circle.</span></span> <span data-ttu-id="89d76-142">与 <xref:System.Windows.Media.LinearGradientBrush> 类一样，您可以使用 <xref:System.Windows.Media.GradientStop> 对象来指定渐变中的颜色及其位置。</span><span class="sxs-lookup"><span data-stu-id="89d76-142">As with the <xref:System.Windows.Media.LinearGradientBrush> class, you use <xref:System.Windows.Media.GradientStop> objects to specify the colors in the gradient and their positions.</span></span>  
  
 <span data-ttu-id="89d76-143">下面的示例使用 <xref:System.Windows.Media.RadialGradientBrush> 绘制 <xref:System.Windows.Shapes.Rectangle>的 <xref:System.Windows.Shapes.Shape.Fill%2A>。</span><span class="sxs-lookup"><span data-stu-id="89d76-143">The following example uses a <xref:System.Windows.Media.RadialGradientBrush> to paint the <xref:System.Windows.Shapes.Shape.Fill%2A> of a <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="89d76-144">下图显示了绘制的矩形。</span><span class="sxs-lookup"><span data-stu-id="89d76-144">The following illustration shows the painted rectangle.</span></span>  
  
 <span data-ttu-id="89d76-145">![使用 RadialGradientBrush 绘制的矩形](./media/graphicsmm-brush-ovw-radialgradientbrush.jpg "graphicsmm_brush_ovw_radialgradientbrush")</span><span class="sxs-lookup"><span data-stu-id="89d76-145">![A rectangle painted using a RadialGradientBrush](./media/graphicsmm-brush-ovw-radialgradientbrush.jpg "graphicsmm_brush_ovw_radialgradientbrush")</span></span>  
<span data-ttu-id="89d76-146">使用 RadialGradientBrush 绘制的矩形</span><span class="sxs-lookup"><span data-stu-id="89d76-146">A Rectangle painted using a RadialGradientBrush</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmradialgradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmradialgradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmradialgradientbrushexampleinline)]  
  
 <span data-ttu-id="89d76-147">有关 <xref:System.Windows.Media.RadialGradientBrush> 类的详细信息，请参阅[采用纯色和渐变进行绘制概述](painting-with-solid-colors-and-gradients-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="89d76-147">For more information about the <xref:System.Windows.Media.RadialGradientBrush> class, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
<a name="paintwithimage"></a>   
## <a name="paint-with-an-image"></a><span data-ttu-id="89d76-148">使用图像进行绘制</span><span class="sxs-lookup"><span data-stu-id="89d76-148">Paint with an Image</span></span>  
 <span data-ttu-id="89d76-149"><xref:System.Windows.Media.ImageBrush> 使用 <xref:System.Windows.Media.ImageSource>绘制区域。</span><span class="sxs-lookup"><span data-stu-id="89d76-149">An <xref:System.Windows.Media.ImageBrush> paints an area with a <xref:System.Windows.Media.ImageSource>.</span></span>  
  
 <span data-ttu-id="89d76-150">下面的示例使用 <xref:System.Windows.Media.ImageBrush> 绘制 <xref:System.Windows.Shapes.Rectangle>的 <xref:System.Windows.Shapes.Shape.Fill%2A>。</span><span class="sxs-lookup"><span data-stu-id="89d76-150">The following example uses an <xref:System.Windows.Media.ImageBrush> to paint the <xref:System.Windows.Shapes.Shape.Fill%2A> of a <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="89d76-151">下图显示了绘制的矩形。</span><span class="sxs-lookup"><span data-stu-id="89d76-151">The following illustration shows the painted rectangle.</span></span>  
  
 <span data-ttu-id="89d76-152">![System.windows.media.imagebrush> 绘制的矩形](./media/graphicsmm-brush-ovw-imagebrush.jpg "graphicsmm_brush_ovw_imagebrush")</span><span class="sxs-lookup"><span data-stu-id="89d76-152">![A Rectangle painted by an ImageBrush](./media/graphicsmm-brush-ovw-imagebrush.jpg "graphicsmm_brush_ovw_imagebrush")</span></span>  
<span data-ttu-id="89d76-153">使用图像绘制的矩形</span><span class="sxs-lookup"><span data-stu-id="89d76-153">A Rectangle painted using a Image</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmimagebrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmimagebrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmimagebrushexampleinline)]  
  
 <span data-ttu-id="89d76-154">有关 <xref:System.Windows.Media.ImageBrush> 类的详细信息，请参阅[利用图像、绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)。</span><span class="sxs-lookup"><span data-stu-id="89d76-154">For more information about the <xref:System.Windows.Media.ImageBrush> class, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>  
  
<a name="paintwithdrawing"></a>   
## <a name="paint-with-a-drawing"></a><span data-ttu-id="89d76-155">使用绘图绘制</span><span class="sxs-lookup"><span data-stu-id="89d76-155">Paint with a Drawing</span></span>  
 <span data-ttu-id="89d76-156"><xref:System.Windows.Media.DrawingBrush> 使用 <xref:System.Windows.Media.Drawing>绘制区域。</span><span class="sxs-lookup"><span data-stu-id="89d76-156">A <xref:System.Windows.Media.DrawingBrush> paints an area with a <xref:System.Windows.Media.Drawing>.</span></span> <span data-ttu-id="89d76-157"><xref:System.Windows.Media.Drawing> 可以包含形状、图像、文本和媒体。</span><span class="sxs-lookup"><span data-stu-id="89d76-157">A <xref:System.Windows.Media.Drawing> can contain shapes, images, text, and media.</span></span>  
  
 <span data-ttu-id="89d76-158">下面的示例使用 <xref:System.Windows.Media.DrawingBrush> 绘制 <xref:System.Windows.Shapes.Rectangle>的 <xref:System.Windows.Shapes.Shape.Fill%2A>。</span><span class="sxs-lookup"><span data-stu-id="89d76-158">The following example uses a <xref:System.Windows.Media.DrawingBrush> to paint the <xref:System.Windows.Shapes.Shape.Fill%2A> of a <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="89d76-159">下图显示了绘制的矩形。</span><span class="sxs-lookup"><span data-stu-id="89d76-159">The following illustration shows the painted rectangle.</span></span>  
  
 <span data-ttu-id="89d76-160">![使用 System.windows.media.drawingbrush> 绘制的矩形](./media/graphicsmm-brush-ovw-drawingbrush.jpg "graphicsmm_brush_ovw_drawingbrush")</span><span class="sxs-lookup"><span data-stu-id="89d76-160">![A rectangle painted using a DrawingBrush](./media/graphicsmm-brush-ovw-drawingbrush.jpg "graphicsmm_brush_ovw_drawingbrush")</span></span>  
<span data-ttu-id="89d76-161">使用 System.windows.media.drawingbrush> 绘制的矩形</span><span class="sxs-lookup"><span data-stu-id="89d76-161">A Rectangle painted using a DrawingBrush</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmdrawingbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmdrawingbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmdrawingbrushexampleinline)]  
  
 <span data-ttu-id="89d76-162">有关 <xref:System.Windows.Media.DrawingBrush> 类的详细信息，请参阅[利用图像、绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)。</span><span class="sxs-lookup"><span data-stu-id="89d76-162">For more information about the <xref:System.Windows.Media.DrawingBrush> class, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>  
  
<a name="paintwithvisual"></a>   
## <a name="paint-with-a-visual"></a><span data-ttu-id="89d76-163">使用视觉对象进行绘制</span><span class="sxs-lookup"><span data-stu-id="89d76-163">Paint with a Visual</span></span>  
 <span data-ttu-id="89d76-164"><xref:System.Windows.Media.VisualBrush> 使用 <xref:System.Windows.Media.Visual> 对象绘制区域。</span><span class="sxs-lookup"><span data-stu-id="89d76-164">A <xref:System.Windows.Media.VisualBrush> paints an area with a <xref:System.Windows.Media.Visual> object.</span></span> <span data-ttu-id="89d76-165">视觉对象的示例包括 <xref:System.Windows.Controls.Button>、<xref:System.Windows.Controls.Page>和 <xref:System.Windows.Controls.MediaElement>。</span><span class="sxs-lookup"><span data-stu-id="89d76-165">Examples of Visual objects include <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Page>, and <xref:System.Windows.Controls.MediaElement>.</span></span> <span data-ttu-id="89d76-166">使用 <xref:System.Windows.Media.VisualBrush> 还可以将应用程序的一个部分的内容投影到另一个区域;这对于创建反射效果和屏幕的放大部分非常有用。</span><span class="sxs-lookup"><span data-stu-id="89d76-166">A <xref:System.Windows.Media.VisualBrush> also enables you to project content from one portion of your application into another area; it's very useful for creating reflection effects and magnifying portions of the screen.</span></span>  
  
 <span data-ttu-id="89d76-167">下面的示例使用 <xref:System.Windows.Media.VisualBrush> 绘制 <xref:System.Windows.Shapes.Rectangle>的 <xref:System.Windows.Shapes.Shape.Fill%2A>。</span><span class="sxs-lookup"><span data-stu-id="89d76-167">The following example uses a <xref:System.Windows.Media.VisualBrush> to paint the <xref:System.Windows.Shapes.Shape.Fill%2A> of a <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="89d76-168">下图显示了绘制的矩形。</span><span class="sxs-lookup"><span data-stu-id="89d76-168">The following illustration shows the painted rectangle.</span></span>  
  
 <span data-ttu-id="89d76-169">![使用 System.windows.media.visualbrush> 绘制的矩形](./media/graphicsmm-brush-ovw-visualbrush.jpg "graphicsmm_brush_ovw_visualbrush")</span><span class="sxs-lookup"><span data-stu-id="89d76-169">![A rectangle painted using a VisualBrush](./media/graphicsmm-brush-ovw-visualbrush.jpg "graphicsmm_brush_ovw_visualbrush")</span></span>  
<span data-ttu-id="89d76-170">使用 System.windows.media.visualbrush> 绘制的矩形</span><span class="sxs-lookup"><span data-stu-id="89d76-170">A Rectangle painted using a VisualBrush</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmvisualbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmvisualbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmvisualbrushexampleinline)]  
  
 <span data-ttu-id="89d76-171">有关 <xref:System.Windows.Media.VisualBrush> 类的详细信息，请参阅[利用图像、绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)。</span><span class="sxs-lookup"><span data-stu-id="89d76-171">For more information about the <xref:System.Windows.Media.VisualBrush> class, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>  
  
<a name="paintwithpredefinedbrushesandsystemcolors"></a>   
## <a name="paint-using-predefined-and-system-brushes"></a><span data-ttu-id="89d76-172">使用预定义画笔和系统画笔进行绘制</span><span class="sxs-lookup"><span data-stu-id="89d76-172">Paint using Predefined and System Brushes</span></span>  
 <span data-ttu-id="89d76-173">为方便起见，Windows Presentation Foundation （WPF）提供了一组预定义的和系统画笔，可用于绘制对象。</span><span class="sxs-lookup"><span data-stu-id="89d76-173">For convenience, Windows Presentation Foundation (WPF) provides a set of predefined and system brushes that you can use to paint objects.</span></span>  
  
- <span data-ttu-id="89d76-174">有关可用预定义画笔的列表，请参阅 <xref:System.Windows.Media.Brushes> 类。</span><span class="sxs-lookup"><span data-stu-id="89d76-174">For a list of available predefined brushes, see the <xref:System.Windows.Media.Brushes> class.</span></span> <span data-ttu-id="89d76-175">有关演示如何使用预定义画笔的示例，请参阅[使用纯色绘制区域](how-to-paint-an-area-with-a-solid-color.md)。</span><span class="sxs-lookup"><span data-stu-id="89d76-175">For an example showing how to use a predefined brush, see [Paint an Area with a Solid Color](how-to-paint-an-area-with-a-solid-color.md).</span></span>  
  
- <span data-ttu-id="89d76-176">有关可用系统画笔的列表，请参阅 <xref:System.Windows.SystemColors> 类。</span><span class="sxs-lookup"><span data-stu-id="89d76-176">For a list of available system brushes, see the <xref:System.Windows.SystemColors> class.</span></span> <span data-ttu-id="89d76-177">有关示例，请参阅[使用系统画笔绘制区域](how-to-paint-an-area-with-a-system-brush.md)。</span><span class="sxs-lookup"><span data-stu-id="89d76-177">For an example, see [Paint an Area with a System Brush](how-to-paint-an-area-with-a-system-brush.md).</span></span>  
  
<a name="commonbrushfeatures"></a>   
## <a name="common-brush-features"></a><span data-ttu-id="89d76-178">常用画笔功能</span><span class="sxs-lookup"><span data-stu-id="89d76-178">Common Brush Features</span></span>  
 <span data-ttu-id="89d76-179"><xref:System.Windows.Media.Brush> 对象提供了一个 <xref:System.Windows.Media.Brush.Opacity%2A> 属性，该属性可用于使画笔透明或部分透明。</span><span class="sxs-lookup"><span data-stu-id="89d76-179"><xref:System.Windows.Media.Brush> objects provide an <xref:System.Windows.Media.Brush.Opacity%2A> property that can be used to make a brush transparent or partially transparent.</span></span> <span data-ttu-id="89d76-180"><xref:System.Windows.Media.Brush.Opacity%2A> 值0会使画笔完全透明，而 <xref:System.Windows.Media.Brush.Opacity%2A> 值1会使画笔完全不透明。</span><span class="sxs-lookup"><span data-stu-id="89d76-180">An <xref:System.Windows.Media.Brush.Opacity%2A> value of 0 makes a brush completely transparent, while an <xref:System.Windows.Media.Brush.Opacity%2A> value of 1 makes a brush completely opaque.</span></span> <span data-ttu-id="89d76-181">下面的示例使用 <xref:System.Windows.Media.Brush.Opacity%2A> 属性，使 <xref:System.Windows.Media.SolidColorBrush> 25% 不透明。</span><span class="sxs-lookup"><span data-stu-id="89d76-181">The following example uses the <xref:System.Windows.Media.Brush.Opacity%2A> property to make a <xref:System.Windows.Media.SolidColorBrush> 25 percent opaque.</span></span>  
  
 [!code-xaml[BrushOverviewExamples_snip#OpacityExample1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/OpacityExample.xaml#opacityexample1xaml)]  
  
 [!code-csharp[BrushOverviewExamples_snip#OpacityExample1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/OpacityExample.cs#opacityexample1csharp)]  
  
 <span data-ttu-id="89d76-182">如果画笔包含部分透明的颜色，则使用画笔的不透明度值组合颜色的不透明度值。</span><span class="sxs-lookup"><span data-stu-id="89d76-182">If the brush contains colors that are partially transparent, the opacity value of the color is combined through multiplication with the opacity value of the brush.</span></span> <span data-ttu-id="89d76-183">例如，如果画笔的不透明度值为0.5，并且画笔中使用的颜色的不透明度值为0.5，则输出颜色的不透明度值为0.25。</span><span class="sxs-lookup"><span data-stu-id="89d76-183">For example, if a brush has an opacity value of 0.5 and a color used in the brush also has an opacity value of 0.5, the output color has an opacity value of 0.25.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="89d76-184">更改画笔的不透明度值比使用其 <xref:System.Windows.UIElement.Opacity%2A?displayProperty=nameWithType> 属性更改整个元素的不透明度更为有效。</span><span class="sxs-lookup"><span data-stu-id="89d76-184">It's more efficient to change the opacity value of a brush than it is to change the opacity of an entire element using its <xref:System.Windows.UIElement.Opacity%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="89d76-185">您可以使用画笔的 <xref:System.Windows.Media.Brush.Transform%2A> 或 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 属性来旋转、缩放、倾斜和平移画笔的内容。</span><span class="sxs-lookup"><span data-stu-id="89d76-185">You can rotate, scale, skew, and translate a brush's content by using its <xref:System.Windows.Media.Brush.Transform%2A> or <xref:System.Windows.Media.Brush.RelativeTransform%2A> properties.</span></span> <span data-ttu-id="89d76-186">有关详细信息，请参阅[刷子转换概述](brush-transformation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="89d76-186">For more information, see [Brush Transformation Overview](brush-transformation-overview.md).</span></span>  
  
 <span data-ttu-id="89d76-187">因为它们是 <xref:System.Windows.Media.Animation.Animatable> 对象，所以可以对 <xref:System.Windows.Media.Brush> 对象进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="89d76-187">Because they are <xref:System.Windows.Media.Animation.Animatable> objects, <xref:System.Windows.Media.Brush> objects can be animated.</span></span> <span data-ttu-id="89d76-188">有关详细信息，请参阅 [动画概述](animation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="89d76-188">For more information, see [Animation Overview](animation-overview.md).</span></span>  
  
<a name="freezable_features"></a>   
### <a name="freezable-features"></a><span data-ttu-id="89d76-189">Freezable 功能</span><span class="sxs-lookup"><span data-stu-id="89d76-189">Freezable Features</span></span>  
 <span data-ttu-id="89d76-190">因为它继承自 <xref:System.Windows.Freezable> 类，所以 <xref:System.Windows.Media.Brush> 类提供若干特殊功能： <xref:System.Windows.Media.Brush> 对象可以声明为[资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)、在多个对象之间共享以及进行克隆。</span><span class="sxs-lookup"><span data-stu-id="89d76-190">Because it inherits from the <xref:System.Windows.Freezable> class, the <xref:System.Windows.Media.Brush> class provides several special features: <xref:System.Windows.Media.Brush> objects can be declared as [resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md), shared among multiple objects, and cloned.</span></span> <span data-ttu-id="89d76-191">此外，除 <xref:System.Windows.Media.VisualBrush> 之外的所有 <xref:System.Windows.Media.Brush> 类型都可以变为只读，以提高性能并使其成为线程安全的。</span><span class="sxs-lookup"><span data-stu-id="89d76-191">In addition, all the <xref:System.Windows.Media.Brush> types except <xref:System.Windows.Media.VisualBrush> can be made read-only to improve performance and made thread-safe.</span></span>  
  
 <span data-ttu-id="89d76-192">有关 <xref:System.Windows.Freezable> 对象提供的不同功能的详细信息，请参阅可[冻结对象概述](../advanced/freezable-objects-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="89d76-192">For more information about the different features provided by <xref:System.Windows.Freezable> objects, see [Freezable Objects Overview](../advanced/freezable-objects-overview.md).</span></span>  
  
 <span data-ttu-id="89d76-193">有关无法冻结 <xref:System.Windows.Media.VisualBrush> 对象的原因的详细信息，请参阅 <xref:System.Windows.Media.VisualBrush> 类型 "页。</span><span class="sxs-lookup"><span data-stu-id="89d76-193">For more information on why <xref:System.Windows.Media.VisualBrush> objects cannot be frozen, see the <xref:System.Windows.Media.VisualBrush> type page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89d76-194">请参阅</span><span class="sxs-lookup"><span data-stu-id="89d76-194">See also</span></span>

- <xref:System.Windows.Media.Brush>
- <xref:System.Windows.Media.Brushes>
- [<span data-ttu-id="89d76-195">使用纯色和渐变进行绘制概述</span><span class="sxs-lookup"><span data-stu-id="89d76-195">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="89d76-196">使用图像、绘图和视觉对象进行绘制</span><span class="sxs-lookup"><span data-stu-id="89d76-196">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="89d76-197">Freezable 对象概述</span><span class="sxs-lookup"><span data-stu-id="89d76-197">Freezable Objects Overview</span></span>](../advanced/freezable-objects-overview.md)
- [<span data-ttu-id="89d76-198">画笔示例</span><span class="sxs-lookup"><span data-stu-id="89d76-198">Brushes Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159973)
- [<span data-ttu-id="89d76-199">System.windows.media.imagebrush> 示例</span><span class="sxs-lookup"><span data-stu-id="89d76-199">ImageBrush Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160005)
- [<span data-ttu-id="89d76-200">VisualBrush 示例</span><span class="sxs-lookup"><span data-stu-id="89d76-200">VisualBrush Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160049)
- [<span data-ttu-id="89d76-201">帮助主题</span><span class="sxs-lookup"><span data-stu-id="89d76-201">How-to Topics</span></span>](brushes-how-to-topics.md)
- [<span data-ttu-id="89d76-202">其他性能建议</span><span class="sxs-lookup"><span data-stu-id="89d76-202">Other Performance Recommendations</span></span>](../advanced/optimizing-performance-other-recommendations.md)
