---
title: 如何：为 TileBrush 设置平铺大小
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tilepropertys
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: e1ba1a25281ffdd1cc00e0bed0efe4f8508780be
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43467830"
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a><span data-ttu-id="001b6-102">如何：为 TileBrush 设置平铺大小</span><span class="sxs-lookup"><span data-stu-id="001b6-102">How to: Set the Tile Size for a TileBrush</span></span>
<span data-ttu-id="001b6-103">此示例演示如何设置平铺大小<xref:System.Windows.Media.TileBrush>。</span><span class="sxs-lookup"><span data-stu-id="001b6-103">This example shows how to set the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="001b6-104">默认情况下，<xref:System.Windows.Media.TileBrush>生成完全填充要绘制区域的单个磁贴。</span><span class="sxs-lookup"><span data-stu-id="001b6-104">By default, a <xref:System.Windows.Media.TileBrush> produces a single tile that completely fills the area that you are painting.</span></span> <span data-ttu-id="001b6-105">可以通过设置替代此行为<xref:System.Windows.Media.TileBrush.Viewport%2A>和<xref:System.Windows.Media.TileBrush.ViewportUnits%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="001b6-105">You can override this behavior by setting the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties.</span></span>  
  
 <span data-ttu-id="001b6-106"><xref:System.Windows.Media.TileBrush.Viewport%2A>属性指定的磁贴大小<xref:System.Windows.Media.TileBrush>。</span><span class="sxs-lookup"><span data-stu-id="001b6-106">The <xref:System.Windows.Media.TileBrush.Viewport%2A> property specifies the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="001b6-107">默认情况下的值<xref:System.Windows.Media.TileBrush.Viewport%2A>属性是相对于所绘制的区域的大小。</span><span class="sxs-lookup"><span data-stu-id="001b6-107">By default, the value of the <xref:System.Windows.Media.TileBrush.Viewport%2A> property is relative to the size of the area being painted.</span></span> <span data-ttu-id="001b6-108">若要使<xref:System.Windows.Media.TileBrush.Viewport%2A>属性指定绝对平铺大小，设置<xref:System.Windows.Media.TileBrush.ViewportUnits%2A>属性设置为<xref:System.Windows.Media.BrushMappingMode.Absolute>。</span><span class="sxs-lookup"><span data-stu-id="001b6-108">To make the <xref:System.Windows.Media.TileBrush.Viewport%2A> property specify an absolute tile size, set the <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> property to <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="001b6-109">示例</span><span class="sxs-lookup"><span data-stu-id="001b6-109">Example</span></span>  
 <span data-ttu-id="001b6-110">下面的示例使用<xref:System.Windows.Media.ImageBrush>，一种类型的<xref:System.Windows.Media.TileBrush>、 绘制一个矩形与磁贴。</span><span class="sxs-lookup"><span data-stu-id="001b6-110">The following example uses an <xref:System.Windows.Media.ImageBrush>, a type of <xref:System.Windows.Media.TileBrush>, to paint a rectangle with tiles.</span></span> <span data-ttu-id="001b6-111">此示例将每个平铺设置为在长宽方向上分别占输出区域（矩形）的 50%。</span><span class="sxs-lookup"><span data-stu-id="001b6-111">The example sets each tile to  50 percent by 50 percent of the output area (the rectangle).</span></span> <span data-ttu-id="001b6-112">因此，将用四个投影图像绘制该矩形。</span><span class="sxs-lookup"><span data-stu-id="001b6-112">As a result, the rectangle is painted with four projections of the image.</span></span>  
  
 <span data-ttu-id="001b6-113">下图显示该示例生成的输出。</span><span class="sxs-lookup"><span data-stu-id="001b6-113">The following illustration shows the output that the example produces.</span></span>
  
 <span data-ttu-id="001b6-114">![使用图像画笔平铺的示例](../../../../docs/framework/wpf/graphics-multimedia/media/0.png "0")</span><span class="sxs-lookup"><span data-stu-id="001b6-114">![Example of tiling with an image brush](../../../../docs/framework/wpf/graphics-multimedia/media/0.png "0")</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]  
  
 <span data-ttu-id="001b6-115">下一个示例创建<xref:System.Windows.Media.ImageBrush>，设置其<xref:System.Windows.Media.TileBrush.Viewport%2A>到`0,0,25,25`并将其<xref:System.Windows.Media.TileBrush.ViewportUnits%2A>到<xref:System.Windows.Media.BrushMappingMode.Absolute>，并使用它来绘制另一个矩形。</span><span class="sxs-lookup"><span data-stu-id="001b6-115">The next example creates an <xref:System.Windows.Media.ImageBrush>, sets its <xref:System.Windows.Media.TileBrush.Viewport%2A> to `0,0,25,25` and its <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> to <xref:System.Windows.Media.BrushMappingMode.Absolute>, and uses it to paint another rectangle.</span></span> <span data-ttu-id="001b6-116">因此，画笔会生成一个宽度为 25 像素、高度为 25 像素的平铺。</span><span class="sxs-lookup"><span data-stu-id="001b6-116">As a result, the brush produces tiles that have a width of 25  pixels and a height of 25 pixels .</span></span>  
  
 <span data-ttu-id="001b6-117">下图显示该示例生成的输出。</span><span class="sxs-lookup"><span data-stu-id="001b6-117">The following illustration shows the output that the example produces.</span></span>  
  
 <span data-ttu-id="001b6-118">![视区为 0,0,0.25,0.25 的平铺 TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/25x25viewport.png "25x25viewport")</span><span class="sxs-lookup"><span data-stu-id="001b6-118">![A tiled TileBrush with a Viewport of 0,0,0.25,0.25](../../../../docs/framework/wpf/graphics-multimedia/media/25x25viewport.png "25x25viewport")</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]  
  
 <span data-ttu-id="001b6-119">以上几个示例摘自一个更大的示例。</span><span class="sxs-lookup"><span data-stu-id="001b6-119">The preceding examples are part of a larger sample.</span></span> <span data-ttu-id="001b6-120">有关完整示例，请参阅[ImageBrush 示例](https://go.microsoft.com/fwlink/?LinkID=160005)。</span><span class="sxs-lookup"><span data-stu-id="001b6-120">For the complete sample, see [ImageBrush Sample](https://go.microsoft.com/fwlink/?LinkID=160005).</span></span>  
  
 <span data-ttu-id="001b6-121">虽然此示例使用<xref:System.Windows.Media.ImageBrush>类，<xref:System.Windows.Media.TileBrush.Viewport%2A>和<xref:System.Windows.Media.TileBrush.ViewportUnits%2A>属性的行为方式相同其他<xref:System.Windows.Media.TileBrush>对象，即，对于<xref:System.Windows.Media.DrawingBrush>和<xref:System.Windows.Media.VisualBrush>。</span><span class="sxs-lookup"><span data-stu-id="001b6-121">Although this example uses the <xref:System.Windows.Media.ImageBrush> class, the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties behave identically for the other <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.DrawingBrush> and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="001b6-122">有关详细信息<xref:System.Windows.Media.ImageBrush>和其他<xref:System.Windows.Media.TileBrush>对象，请参阅[使用图像、 绘图和视觉对象进行绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)。</span><span class="sxs-lookup"><span data-stu-id="001b6-122">For more information about <xref:System.Windows.Media.ImageBrush> and the other <xref:System.Windows.Media.TileBrush> objects, see [Painting with Images, Drawings, and Visuals](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="001b6-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="001b6-123">See Also</span></span>  
 <xref:System.Windows.Media.TileBrush>  
 [<span data-ttu-id="001b6-124">使用图像、绘图和视觉对象进行绘制</span><span class="sxs-lookup"><span data-stu-id="001b6-124">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [<span data-ttu-id="001b6-125">使用 TileBrush 创建不同的平铺图案</span><span class="sxs-lookup"><span data-stu-id="001b6-125">Create Different Tile Patterns with a TileBrush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-different-tile-patterns-with-a-tilebrush.md)
