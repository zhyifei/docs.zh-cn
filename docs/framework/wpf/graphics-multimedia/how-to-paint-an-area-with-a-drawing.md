---
title: 如何：使用图形绘制区域
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with drawings
- painting [WPF], with drawings
- drawings [WPF], painting with
ms.assetid: c10dc4b1-09b1-41e8-ad14-456b5fb377df
ms.openlocfilehash: 6b204ae631912181333e2559ebadcdc37e7693b7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010058"
---
# <a name="how-to-paint-an-area-with-a-drawing"></a><span data-ttu-id="5299c-102">如何：使用图形绘制区域</span><span class="sxs-lookup"><span data-stu-id="5299c-102">How to: Paint an Area with a Drawing</span></span>
<span data-ttu-id="5299c-103">本示例演示如何使用 Drawing 绘制一个区域。</span><span class="sxs-lookup"><span data-stu-id="5299c-103">This example shows how to paint an area with a drawing.</span></span> <span data-ttu-id="5299c-104">若要绘制使用图形绘制区域，请使用<xref:System.Windows.Media.DrawingBrush>和一个或多个<xref:System.Windows.Media.Drawing>对象。</span><span class="sxs-lookup"><span data-stu-id="5299c-104">To paint an area with a drawing, you use a <xref:System.Windows.Media.DrawingBrush> and one or more <xref:System.Windows.Media.Drawing> objects.</span></span>   <span data-ttu-id="5299c-105">下面的示例使用<xref:System.Windows.Media.DrawingBrush>若要使用两个椭圆组成的 drawing 对象绘制对象。</span><span class="sxs-lookup"><span data-stu-id="5299c-105">The following example uses a <xref:System.Windows.Media.DrawingBrush> to paint an object with a drawing of two ellipses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5299c-106">示例</span><span class="sxs-lookup"><span data-stu-id="5299c-106">Example</span></span>  
 [!code-xaml[drawingbrush_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/DrawingBrushExample.vb#drawingbrushexamplewholepage)]  
  
 <span data-ttu-id="5299c-107">下图显示该示例的输出。</span><span class="sxs-lookup"><span data-stu-id="5299c-107">The following illustration shows the example's output.</span></span>  
  
 <span data-ttu-id="5299c-108">![DrawingBrush 的输出](./media/graphicsmm-drawingbrush-simple.png "graphicsmm_drawingbrush_simple")</span><span class="sxs-lookup"><span data-stu-id="5299c-108">![Output from a DrawingBrush](./media/graphicsmm-drawingbrush-simple.png "graphicsmm_drawingbrush_simple")</span></span>  
  
 <span data-ttu-id="5299c-109">(原因中所述的形状的中心为白色[控制复合形状的填充](how-to-control-the-fill-of-a-composite-shape.md)。)</span><span class="sxs-lookup"><span data-stu-id="5299c-109">(The center of the shape is white for reasons described in     [Control the Fill of a Composite Shape](how-to-control-the-fill-of-a-composite-shape.md).)</span></span>  
  
 <span data-ttu-id="5299c-110">通过设置<xref:System.Windows.Media.DrawingBrush>对象的<xref:System.Windows.Media.TileBrush.Viewport%2A>和<xref:System.Windows.Media.TileBrush.TileMode%2A>属性，可以创建一个重复图案。</span><span class="sxs-lookup"><span data-stu-id="5299c-110">By setting a <xref:System.Windows.Media.DrawingBrush> object's <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> properties, you can create a repeating pattern.</span></span> <span data-ttu-id="5299c-111">以下示例使用基于由两个椭圆组成的 Drawing 创建的图案绘制一个对象。</span><span class="sxs-lookup"><span data-stu-id="5299c-111">The following example paints an object with a pattern created from a drawing of two ellipses.</span></span>  
  
 [!code-xaml[drawingbrush_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/TiledDrawingBrushExample.xaml#tileddrawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/TiledDrawingBrushExample.cs#tileddrawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/TiledDrawingBrushExample.vb#tileddrawingbrushexamplewholepage)]  
  
 <span data-ttu-id="5299c-112">下图显示了平铺<xref:System.Windows.Media.DrawingBrush>输出。</span><span class="sxs-lookup"><span data-stu-id="5299c-112">The following illustration shows the tiled <xref:System.Windows.Media.DrawingBrush> output.</span></span>  
  
 <span data-ttu-id="5299c-113">![DrawingBrush 的平铺输出](./media/graphicsmm-drawingbrush-tiled.png "graphicsmm_drawingbrush_tiled")</span><span class="sxs-lookup"><span data-stu-id="5299c-113">![Tiled output from a DrawingBrush](./media/graphicsmm-drawingbrush-tiled.png "graphicsmm_drawingbrush_tiled")</span></span>  
  
 <span data-ttu-id="5299c-114">有关图形画笔的详细信息，请参阅[使用图像、 绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)。</span><span class="sxs-lookup"><span data-stu-id="5299c-114">For more information about drawing brushes, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span> <span data-ttu-id="5299c-115">有关详细信息<xref:System.Windows.Media.Drawing>对象，请参阅[Drawing 对象概述](drawing-objects-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5299c-115">For more information about <xref:System.Windows.Media.Drawing> objects, see the [Drawing Objects Overview](drawing-objects-overview.md).</span></span>
