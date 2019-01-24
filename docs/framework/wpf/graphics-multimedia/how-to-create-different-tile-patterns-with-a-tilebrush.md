---
title: 如何：使用 TileBrush 创建不同的平铺模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF], creating tile patterns
- tile patterns [WPF], creating
- creating [WPF], tile patterns with TileBrush
ms.assetid: 5aa46632-3527-4668-9d8d-0375c8af28aa
ms.openlocfilehash: d6b6d4a20d43478131d3adb7c7d091214b3c5871
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54721909"
---
# <a name="how-to-create-different-tile-patterns-with-a-tilebrush"></a><span data-ttu-id="6346c-102">如何：使用 TileBrush 创建不同的平铺模式</span><span class="sxs-lookup"><span data-stu-id="6346c-102">How to: Create Different Tile Patterns with a TileBrush</span></span>
<span data-ttu-id="6346c-103">此示例演示如何使用<xref:System.Windows.Media.TileBrush.TileMode%2A>属性的<xref:System.Windows.Media.TileBrush>创建模式。</span><span class="sxs-lookup"><span data-stu-id="6346c-103">This example shows how to use the <xref:System.Windows.Media.TileBrush.TileMode%2A> property of a <xref:System.Windows.Media.TileBrush> to create a pattern.</span></span>  
  
 <span data-ttu-id="6346c-104"><xref:System.Windows.Media.TileBrush.TileMode%2A>属性可用于指定如何将内容的<xref:System.Windows.Media.TileBrush>重复，也就是说，平铺来填充输出区域。</span><span class="sxs-lookup"><span data-stu-id="6346c-104">The <xref:System.Windows.Media.TileBrush.TileMode%2A> property enables you to specify how the content of a <xref:System.Windows.Media.TileBrush> is repeated, that is, tiled to fill an output area.</span></span> <span data-ttu-id="6346c-105">若要创建一种模式，您可以设置<xref:System.Windows.Media.TileBrush.TileMode%2A>到<xref:System.Windows.Media.TileMode.Tile>， <xref:System.Windows.Media.TileMode.FlipX>， <xref:System.Windows.Media.TileMode.FlipY>，或<xref:System.Windows.Media.TileMode.FlipXY>。</span><span class="sxs-lookup"><span data-stu-id="6346c-105">To create a pattern, you set the <xref:System.Windows.Media.TileBrush.TileMode%2A> to <xref:System.Windows.Media.TileMode.Tile>, <xref:System.Windows.Media.TileMode.FlipX>, <xref:System.Windows.Media.TileMode.FlipY>, or <xref:System.Windows.Media.TileMode.FlipXY>.</span></span> <span data-ttu-id="6346c-106">您还必须设置<xref:System.Windows.Media.TileBrush.Viewport%2A>的<xref:System.Windows.Media.TileBrush>以便小于区域要绘制; 否则，单个磁贴是生成，而不考虑其<xref:System.Windows.Media.TileBrush.TileMode%2A>您使用的设置。</span><span class="sxs-lookup"><span data-stu-id="6346c-106">You must also set the <xref:System.Windows.Media.TileBrush.Viewport%2A> of the <xref:System.Windows.Media.TileBrush> so that it is smaller than the area that you are painting; otherwise, only a single tile is produced, regardless which <xref:System.Windows.Media.TileBrush.TileMode%2A> setting you use.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6346c-107">示例</span><span class="sxs-lookup"><span data-stu-id="6346c-107">Example</span></span>  
 <span data-ttu-id="6346c-108">下面的示例创建五个<xref:System.Windows.Media.DrawingBrush>对象，每个不同<xref:System.Windows.Media.TileBrush.TileMode%2A>设置，并使用它们来绘制五个矩形。</span><span class="sxs-lookup"><span data-stu-id="6346c-108">The following example creates five <xref:System.Windows.Media.DrawingBrush> objects, gives them each a different <xref:System.Windows.Media.TileBrush.TileMode%2A> setting, and uses them to paint five rectangles.</span></span> <span data-ttu-id="6346c-109">虽然此示例使用<xref:System.Windows.Media.DrawingBrush>类，以演示<xref:System.Windows.Media.TileBrush.TileMode%2A>行为，<xref:System.Windows.Media.TileBrush.TileMode%2A>属性的工作方式完全相同的所有<xref:System.Windows.Media.TileBrush>对象，也就是说，对于<xref:System.Windows.Media.ImageBrush>， <xref:System.Windows.Media.VisualBrush>，和<xref:System.Windows.Media.DrawingBrush>。</span><span class="sxs-lookup"><span data-stu-id="6346c-109">Although this example uses the <xref:System.Windows.Media.DrawingBrush> class to demonstrate <xref:System.Windows.Media.TileBrush.TileMode%2A> behavior, the <xref:System.Windows.Media.TileBrush.TileMode%2A> property works identically for all the <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush>, and <xref:System.Windows.Media.DrawingBrush>.</span></span>  
  
 <span data-ttu-id="6346c-110">下图显示了此示例生成的输出。</span><span class="sxs-lookup"><span data-stu-id="6346c-110">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="6346c-111">![TileBrush 平铺示例输出](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")</span><span class="sxs-lookup"><span data-stu-id="6346c-111">![TileBrush tiling example output](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")</span></span>  
<span data-ttu-id="6346c-112">使用 TileMode 属性创建平铺模式</span><span class="sxs-lookup"><span data-stu-id="6346c-112">Tile patterns created with the TileMode property</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/TileModeExample.cs#graphicsmmdrawingbrushtilemodeexample)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/tilemodeexample.vb#graphicsmmdrawingbrushtilemodeexample)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/TileModeExample.xaml#graphicsmmdrawingbrushtilemodeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="6346c-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="6346c-113">See also</span></span>
- [<span data-ttu-id="6346c-114">设置 TileBrush 的平铺大小</span><span class="sxs-lookup"><span data-stu-id="6346c-114">Set the Tile Size for a TileBrush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-the-tile-size-for-a-tilebrush.md)
- [<span data-ttu-id="6346c-115">使用图像、绘图和视觉对象进行绘制</span><span class="sxs-lookup"><span data-stu-id="6346c-115">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
