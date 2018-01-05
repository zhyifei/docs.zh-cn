---
title: "如何：使用 TileBrush 创建不同的平铺模式"
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
- TileBrush [WPF], creating tile patterns
- tile patterns [WPF], creating
- creating [WPF], tile patterns with TileBrush
ms.assetid: 5aa46632-3527-4668-9d8d-0375c8af28aa
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 646ce5142875c95c0b1ca19643790f73f7eb83e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-different-tile-patterns-with-a-tilebrush"></a><span data-ttu-id="801e5-102">如何：使用 TileBrush 创建不同的平铺模式</span><span class="sxs-lookup"><span data-stu-id="801e5-102">How to: Create Different Tile Patterns with a TileBrush</span></span>
<span data-ttu-id="801e5-103">此示例演示如何使用<xref:System.Windows.Media.TileBrush.TileMode%2A>属性<xref:System.Windows.Media.TileBrush>创建一种模式。</span><span class="sxs-lookup"><span data-stu-id="801e5-103">This example shows how to use the <xref:System.Windows.Media.TileBrush.TileMode%2A> property of a <xref:System.Windows.Media.TileBrush> to create a pattern.</span></span>  
  
 <span data-ttu-id="801e5-104"><xref:System.Windows.Media.TileBrush.TileMode%2A>属性使您能够指定了内容的<xref:System.Windows.Media.TileBrush>重复，也就是说，平铺以填充输出区域。</span><span class="sxs-lookup"><span data-stu-id="801e5-104">The <xref:System.Windows.Media.TileBrush.TileMode%2A> property enables you to specify how the content of a <xref:System.Windows.Media.TileBrush> is repeated, that is, tiled to fill an output area.</span></span> <span data-ttu-id="801e5-105">若要创建一种模式，你可以设置<xref:System.Windows.Media.TileBrush.TileMode%2A>到<xref:System.Windows.Media.TileMode.Tile>， <xref:System.Windows.Media.TileMode.FlipX>， <xref:System.Windows.Media.TileMode.FlipY>，或<xref:System.Windows.Media.TileMode.FlipXY>。</span><span class="sxs-lookup"><span data-stu-id="801e5-105">To create a pattern, you set the <xref:System.Windows.Media.TileBrush.TileMode%2A> to <xref:System.Windows.Media.TileMode.Tile>, <xref:System.Windows.Media.TileMode.FlipX>, <xref:System.Windows.Media.TileMode.FlipY>, or <xref:System.Windows.Media.TileMode.FlipXY>.</span></span> <span data-ttu-id="801e5-106">你还必须设置<xref:System.Windows.Media.TileBrush.Viewport%2A>的<xref:System.Windows.Media.TileBrush>以便小于区域你正在绘画的; 否则，单个磁贴生成，无论程序其中<xref:System.Windows.Media.TileBrush.TileMode%2A>你使用的设置。</span><span class="sxs-lookup"><span data-stu-id="801e5-106">You must also set the <xref:System.Windows.Media.TileBrush.Viewport%2A> of the <xref:System.Windows.Media.TileBrush> so that it is smaller than the area that you are painting; otherwise, only a single tile is produced, regardless which <xref:System.Windows.Media.TileBrush.TileMode%2A> setting you use.</span></span>  
  
## <a name="example"></a><span data-ttu-id="801e5-107">示例</span><span class="sxs-lookup"><span data-stu-id="801e5-107">Example</span></span>  
 <span data-ttu-id="801e5-108">下面的示例创建五个<xref:System.Windows.Media.DrawingBrush>的对象，提供每个不同<xref:System.Windows.Media.TileBrush.TileMode%2A>设置，并使用它们绘制五个矩形。</span><span class="sxs-lookup"><span data-stu-id="801e5-108">The following example creates five <xref:System.Windows.Media.DrawingBrush> objects, gives them each a different <xref:System.Windows.Media.TileBrush.TileMode%2A> setting, and uses them to paint five rectangles.</span></span> <span data-ttu-id="801e5-109">虽然此示例使用<xref:System.Windows.Media.DrawingBrush>类以演示<xref:System.Windows.Media.TileBrush.TileMode%2A>行为，<xref:System.Windows.Media.TileBrush.TileMode%2A>属性的工作方式完全相同所有<xref:System.Windows.Media.TileBrush>对象，即为<xref:System.Windows.Media.ImageBrush>， <xref:System.Windows.Media.VisualBrush>，和<xref:System.Windows.Media.DrawingBrush>。</span><span class="sxs-lookup"><span data-stu-id="801e5-109">Although this example uses the <xref:System.Windows.Media.DrawingBrush> class to demonstrate <xref:System.Windows.Media.TileBrush.TileMode%2A> behavior, the <xref:System.Windows.Media.TileBrush.TileMode%2A> property works identically for all the <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush>, and <xref:System.Windows.Media.DrawingBrush>.</span></span>  
  
 <span data-ttu-id="801e5-110">下图显示了此示例生成的输出。</span><span class="sxs-lookup"><span data-stu-id="801e5-110">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="801e5-111">![TileBrush 平铺示例输出](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")</span><span class="sxs-lookup"><span data-stu-id="801e5-111">![TileBrush tiling example output](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")</span></span>  
<span data-ttu-id="801e5-112">使用 TileMode 属性创建的磁贴模式</span><span class="sxs-lookup"><span data-stu-id="801e5-112">Tile patterns created with the TileMode property</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/TileModeExample.cs#graphicsmmdrawingbrushtilemodeexample)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/tilemodeexample.vb#graphicsmmdrawingbrushtilemodeexample)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/TileModeExample.xaml#graphicsmmdrawingbrushtilemodeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="801e5-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="801e5-113">See Also</span></span>  
 [<span data-ttu-id="801e5-114">设置 TileBrush 的平铺大小</span><span class="sxs-lookup"><span data-stu-id="801e5-114">Set the Tile Size for a TileBrush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-the-tile-size-for-a-tilebrush.md)  
 [<span data-ttu-id="801e5-115">使用图像、绘图和视觉对象进行绘制</span><span class="sxs-lookup"><span data-stu-id="801e5-115">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
