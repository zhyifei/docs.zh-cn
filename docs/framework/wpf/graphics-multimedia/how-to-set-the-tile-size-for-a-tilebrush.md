---
title: 如何：为 TileBrush 设置平铺大小
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tile properties
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: af7bab59a292549b29dad9b6a7417f22b1b84e48
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186840"
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a><span data-ttu-id="0bef2-102">如何：为 TileBrush 设置平铺大小</span><span class="sxs-lookup"><span data-stu-id="0bef2-102">How to: Set the Tile Size for a TileBrush</span></span>

<span data-ttu-id="0bef2-103">此示例演示如何设置 的<xref:System.Windows.Media.TileBrush>磁贴大小。</span><span class="sxs-lookup"><span data-stu-id="0bef2-103">This example shows how to set the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="0bef2-104">默认情况下，生成<xref:System.Windows.Media.TileBrush>一个完全填充要绘制的区域的磁贴。</span><span class="sxs-lookup"><span data-stu-id="0bef2-104">By default, a <xref:System.Windows.Media.TileBrush> produces a single tile that completely fills the area that you are painting.</span></span> <span data-ttu-id="0bef2-105">可以通过设置 和<xref:System.Windows.Media.TileBrush.Viewport%2A><xref:System.Windows.Media.TileBrush.ViewportUnits%2A>属性来重写此行为。</span><span class="sxs-lookup"><span data-stu-id="0bef2-105">You can override this behavior by setting the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties.</span></span>

<span data-ttu-id="0bef2-106">属性<xref:System.Windows.Media.TileBrush.Viewport%2A>指定 的<xref:System.Windows.Media.TileBrush>磁贴大小。</span><span class="sxs-lookup"><span data-stu-id="0bef2-106">The <xref:System.Windows.Media.TileBrush.Viewport%2A> property specifies the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="0bef2-107">默认情况下，<xref:System.Windows.Media.TileBrush.Viewport%2A>属性的值与要绘制的区域的大小相关。</span><span class="sxs-lookup"><span data-stu-id="0bef2-107">By default, the value of the <xref:System.Windows.Media.TileBrush.Viewport%2A> property is relative to the size of the area being painted.</span></span> <span data-ttu-id="0bef2-108">要使<xref:System.Windows.Media.TileBrush.Viewport%2A>属性指定绝对磁贴大小，请将<xref:System.Windows.Media.TileBrush.ViewportUnits%2A>属性设置为<xref:System.Windows.Media.BrushMappingMode.Absolute>。</span><span class="sxs-lookup"><span data-stu-id="0bef2-108">To make the <xref:System.Windows.Media.TileBrush.Viewport%2A> property specify an absolute tile size, set the <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> property to <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span>

## <a name="example"></a><span data-ttu-id="0bef2-109">示例</span><span class="sxs-lookup"><span data-stu-id="0bef2-109">Example</span></span>

<span data-ttu-id="0bef2-110">下面的示例使用<xref:System.Windows.Media.ImageBrush>、 的类型<xref:System.Windows.Media.TileBrush>，使用切片绘制矩形。</span><span class="sxs-lookup"><span data-stu-id="0bef2-110">The following example uses an <xref:System.Windows.Media.ImageBrush>, a type of <xref:System.Windows.Media.TileBrush>, to paint a rectangle with tiles.</span></span> <span data-ttu-id="0bef2-111">该示例将每个磁贴按输出区域（矩形）的 50% 设置为 50%。</span><span class="sxs-lookup"><span data-stu-id="0bef2-111">The example sets each tile to 50 percent by 50 percent of the output area (the rectangle).</span></span> <span data-ttu-id="0bef2-112">因此，将用四个投影图像绘制该矩形。</span><span class="sxs-lookup"><span data-stu-id="0bef2-112">As a result, the rectangle is painted with four projections of the image.</span></span>

<span data-ttu-id="0bef2-113">下图显示了示例生成的输出：</span><span class="sxs-lookup"><span data-stu-id="0bef2-113">The following illustration shows the output that the example produces:</span></span>

![一个矩形，有四个樱桃，用图像画笔演示平铺。](./media/how-to-set-the-tile-size-for-a-tilebrush/rectangle-tile-image-brush.png)

[!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]

<span data-ttu-id="0bef2-115">下一个示例创建<xref:System.Windows.Media.ImageBrush>一个<xref:System.Windows.Media.TileBrush.Viewport%2A> `0,0,25,25` ，设置<xref:System.Windows.Media.TileBrush.ViewportUnits%2A>其<xref:System.Windows.Media.BrushMappingMode.Absolute>和 其 到 ，并使用它来绘制另一个矩形。</span><span class="sxs-lookup"><span data-stu-id="0bef2-115">The next example creates an <xref:System.Windows.Media.ImageBrush>, sets its <xref:System.Windows.Media.TileBrush.Viewport%2A> to `0,0,25,25` and its <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> to <xref:System.Windows.Media.BrushMappingMode.Absolute>, and uses it to paint another rectangle.</span></span> <span data-ttu-id="0bef2-116">因此，画笔会生成一个宽度为 25 像素、高度为 25 像素的平铺。</span><span class="sxs-lookup"><span data-stu-id="0bef2-116">As a result, the brush produces tiles that have a width of 25  pixels and a height of 25 pixels .</span></span>

<span data-ttu-id="0bef2-117">下图显示了示例生成的输出：</span><span class="sxs-lookup"><span data-stu-id="0bef2-117">The following illustration shows the output that the example produces:</span></span>

![一个长方形，有四十八个樱桃，展示一个瓷砖刷与视口。](./media/how-to-set-the-tile-size-for-a-tilebrush/25-x-25-viewport-tilebrush.png)

[!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]

<span data-ttu-id="0bef2-119">以上几个示例摘自一个更大的示例。</span><span class="sxs-lookup"><span data-stu-id="0bef2-119">The preceding examples are part of a larger sample.</span></span> <span data-ttu-id="0bef2-120">有关完整示例，请参阅[图像画笔示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)。</span><span class="sxs-lookup"><span data-stu-id="0bef2-120">For the complete sample, see [ImageBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).</span></span>

<span data-ttu-id="0bef2-121">尽管此示例使用 类<xref:System.Windows.Media.ImageBrush>，<xref:System.Windows.Media.TileBrush.Viewport%2A>但 和<xref:System.Windows.Media.TileBrush.ViewportUnits%2A>属性对于其他<xref:System.Windows.Media.TileBrush>对象（即 和<xref:System.Windows.Media.DrawingBrush>） 的行为相同。 <xref:System.Windows.Media.VisualBrush></span><span class="sxs-lookup"><span data-stu-id="0bef2-121">Although this example uses the <xref:System.Windows.Media.ImageBrush> class, the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties behave identically for the other <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.DrawingBrush> and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="0bef2-122">有关<xref:System.Windows.Media.ImageBrush>和其他<xref:System.Windows.Media.TileBrush>对象的详细信息，请参阅[使用图像、绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)。</span><span class="sxs-lookup"><span data-stu-id="0bef2-122">For more information about <xref:System.Windows.Media.ImageBrush> and the other <xref:System.Windows.Media.TileBrush> objects, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0bef2-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0bef2-123">See also</span></span>

- <xref:System.Windows.Media.TileBrush>
- [<span data-ttu-id="0bef2-124">使用图像、绘图和视觉对象进行绘制</span><span class="sxs-lookup"><span data-stu-id="0bef2-124">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="0bef2-125">使用 TileBrush 创建不同的平铺图案</span><span class="sxs-lookup"><span data-stu-id="0bef2-125">Create Different Tile Patterns with a TileBrush</span></span>](how-to-create-different-tile-patterns-with-a-tilebrush.md)
