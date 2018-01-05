---
title: "如何：使用 Drawing 绘制区域"
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
- brushes [WPF], painting with drawings
- painting [WPF], with drawings
- drawings [WPF], painting with
ms.assetid: c10dc4b1-09b1-41e8-ad14-456b5fb377df
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fbb7c4aff56fae9b4cc0346f8086bc490269ec8b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-paint-an-area-with-a-drawing"></a><span data-ttu-id="9d9d8-102">如何：使用 Drawing 绘制区域</span><span class="sxs-lookup"><span data-stu-id="9d9d8-102">How to: Paint an Area with a Drawing</span></span>
<span data-ttu-id="9d9d8-103">本示例演示如何使用 Drawing 绘制一个区域。</span><span class="sxs-lookup"><span data-stu-id="9d9d8-103">This example shows how to paint an area with a drawing.</span></span> <span data-ttu-id="9d9d8-104">若要绘制带有绘制的区域，请使用<xref:System.Windows.Media.DrawingBrush>和一个或多个<xref:System.Windows.Media.Drawing>对象。</span><span class="sxs-lookup"><span data-stu-id="9d9d8-104">To paint an area with a drawing, you use a <xref:System.Windows.Media.DrawingBrush> and one or more <xref:System.Windows.Media.Drawing> objects.</span></span>   <span data-ttu-id="9d9d8-105">下面的示例使用<xref:System.Windows.Media.DrawingBrush>来绘制具有两个椭圆的绘图的对象。</span><span class="sxs-lookup"><span data-stu-id="9d9d8-105">The following example uses a <xref:System.Windows.Media.DrawingBrush> to paint an object with a drawing of two ellipses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d9d8-106">示例</span><span class="sxs-lookup"><span data-stu-id="9d9d8-106">Example</span></span>  
 [!code-xaml[drawingbrush_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/DrawingBrushExample.vb#drawingbrushexamplewholepage)]  
  
 <span data-ttu-id="9d9d8-107">下图显示该示例的输出。</span><span class="sxs-lookup"><span data-stu-id="9d9d8-107">The following illustration shows the example's output.</span></span>  
  
 <span data-ttu-id="9d9d8-108">![DrawingBrush 的输出](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-simple.png "graphicsmm_drawingbrush_simple")</span><span class="sxs-lookup"><span data-stu-id="9d9d8-108">![Output from a DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-simple.png "graphicsmm_drawingbrush_simple")</span></span>  
  
 <span data-ttu-id="9d9d8-109">(有关中所述的原因，形状的中心为白色[控制复合形状的填充](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-the-fill-of-a-composite-shape.md)。)</span><span class="sxs-lookup"><span data-stu-id="9d9d8-109">(The center of the shape is white for reasons described in     [Control the Fill of a Composite Shape](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-the-fill-of-a-composite-shape.md).)</span></span>  
  
 <span data-ttu-id="9d9d8-110">通过设置<xref:System.Windows.Media.DrawingBrush>对象的<xref:System.Windows.Media.TileBrush.Viewport%2A>和<xref:System.Windows.Media.TileBrush.TileMode%2A>属性，你可以创建重复的模式。</span><span class="sxs-lookup"><span data-stu-id="9d9d8-110">By setting a <xref:System.Windows.Media.DrawingBrush> object's <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> properties, you can create a repeating pattern.</span></span> <span data-ttu-id="9d9d8-111">以下示例使用基于由两个椭圆组成的 Drawing 创建的图案绘制一个对象。</span><span class="sxs-lookup"><span data-stu-id="9d9d8-111">The following example paints an object with a pattern created from a drawing of two ellipses.</span></span>  
  
 [!code-xaml[drawingbrush_snip#TiledDrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/TiledDrawingBrushExample.xaml#tileddrawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/TiledDrawingBrushExample.cs#tileddrawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/TiledDrawingBrushExample.vb#tileddrawingbrushexamplewholepage)]  
  
 <span data-ttu-id="9d9d8-112">下图显示了平铺<xref:System.Windows.Media.DrawingBrush>输出。</span><span class="sxs-lookup"><span data-stu-id="9d9d8-112">The following illustration shows the tiled <xref:System.Windows.Media.DrawingBrush> output.</span></span>  
  
 <span data-ttu-id="9d9d8-113">![DrawingBrush 的平铺输出](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-tiled.png "graphicsmm_drawingbrush_tiled")</span><span class="sxs-lookup"><span data-stu-id="9d9d8-113">![Tiled output from a DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-tiled.png "graphicsmm_drawingbrush_tiled")</span></span>  
  
 <span data-ttu-id="9d9d8-114">有关图形画笔的详细信息，请参阅[使用图像、 图形和视觉对象进行绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)。</span><span class="sxs-lookup"><span data-stu-id="9d9d8-114">For more information about drawing brushes, see [Painting with Images, Drawings, and Visuals](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span></span> <span data-ttu-id="9d9d8-115">有关详细信息<xref:System.Windows.Media.Drawing>对象，请参阅[绘制对象概述](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="9d9d8-115">For more information about <xref:System.Windows.Media.Drawing> objects, see the [Drawing Objects Overview](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).</span></span>
