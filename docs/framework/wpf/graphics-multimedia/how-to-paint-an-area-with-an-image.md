---
title: 如何：使用图像绘制区域
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], painting with
- painting [WPF], with images
- brushes [WPF], painting with images
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
ms.openlocfilehash: 92969778c04c6ac634a2964c402d6c3439b96b49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186057"
---
# <a name="how-to-paint-an-area-with-an-image"></a><span data-ttu-id="83e60-102">如何：使用图像绘制区域</span><span class="sxs-lookup"><span data-stu-id="83e60-102">How to: Paint an Area with an Image</span></span>
<span data-ttu-id="83e60-103">此示例演示如何使用 类<xref:System.Windows.Media.ImageBrush>使用图像绘制区域。</span><span class="sxs-lookup"><span data-stu-id="83e60-103">This example shows how to use the <xref:System.Windows.Media.ImageBrush> class to paint an area with an image.</span></span> <span data-ttu-id="83e60-104">显示<xref:System.Windows.Media.ImageBrush>由其<xref:System.Windows.Media.ImageBrush.ImageSource%2A>属性指定的单个图像。</span><span class="sxs-lookup"><span data-stu-id="83e60-104">An <xref:System.Windows.Media.ImageBrush> displays a single image, which is specified by its <xref:System.Windows.Media.ImageBrush.ImageSource%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83e60-105">示例</span><span class="sxs-lookup"><span data-stu-id="83e60-105">Example</span></span>  
 <span data-ttu-id="83e60-106">下面的示例<xref:System.Windows.Controls.Control.Background%2A>使用 绘制按钮的 。 <xref:System.Windows.Media.ImageBrush></span><span class="sxs-lookup"><span data-stu-id="83e60-106">The following example paints the <xref:System.Windows.Controls.Control.Background%2A> of a button by using an <xref:System.Windows.Media.ImageBrush>.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 <span data-ttu-id="83e60-107">默认情况下，拉伸<xref:System.Windows.Media.ImageBrush>其图像以完全填充要绘制的区域。</span><span class="sxs-lookup"><span data-stu-id="83e60-107">By default, an <xref:System.Windows.Media.ImageBrush> stretches its image to completely fill the area that you are painting.</span></span> <span data-ttu-id="83e60-108">在以上示例中，拉伸图像以填充按钮，可能会使图像失真。</span><span class="sxs-lookup"><span data-stu-id="83e60-108">In the preceding example, the image is stretched to fill the button, possibly distorting the image.</span></span> <span data-ttu-id="83e60-109">可以通过<xref:System.Windows.Media.TileBrush.Stretch%2A>设置<xref:System.Windows.Media.TileBrush>的 属性 来<xref:System.Windows.Media.Stretch.Uniform>控制此行为<xref:System.Windows.Media.Stretch.UniformToFill>，这将导致画笔保留图像的纵横比。</span><span class="sxs-lookup"><span data-stu-id="83e60-109">You can control this behavior by setting the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of <xref:System.Windows.Media.TileBrush> to <xref:System.Windows.Media.Stretch.Uniform> or <xref:System.Windows.Media.Stretch.UniformToFill>, which causes the brush to preserve the aspect ratio of the image.</span></span>  
  
 <span data-ttu-id="83e60-110">如果设置 的<xref:System.Windows.Media.TileBrush.Viewport%2A><xref:System.Windows.Media.TileBrush.TileMode%2A>和 属性<xref:System.Windows.Media.ImageBrush>，则可以创建重复模式。</span><span class="sxs-lookup"><span data-stu-id="83e60-110">If you set the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> properties of an <xref:System.Windows.Media.ImageBrush>, you can create a repeating pattern.</span></span> <span data-ttu-id="83e60-111">以下示例通过使用从图像创建的图案来绘制按钮。</span><span class="sxs-lookup"><span data-stu-id="83e60-111">The following example paints a button by using a pattern that is created from an image.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 <span data-ttu-id="83e60-112">有关该类的详细信息，<xref:System.Windows.Media.ImageBrush>请参阅[使用图像、绘图和视觉对象进行绘画](painting-with-images-drawings-and-visuals.md)。</span><span class="sxs-lookup"><span data-stu-id="83e60-112">For more information about the <xref:System.Windows.Media.ImageBrush> class, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>  
  
 <span data-ttu-id="83e60-113">此代码示例是为类提供的较大示例的<xref:System.Windows.Media.ImageBrush>一部分。</span><span class="sxs-lookup"><span data-stu-id="83e60-113">This code example is part of a larger example that is provided for the <xref:System.Windows.Media.ImageBrush> class.</span></span> <span data-ttu-id="83e60-114">有关完整示例，请参阅[图像画笔示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)。</span><span class="sxs-lookup"><span data-stu-id="83e60-114">For the complete sample, see [ImageBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83e60-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83e60-115">See also</span></span>

- [<span data-ttu-id="83e60-116">使用图像、绘图和视觉对象进行绘制</span><span class="sxs-lookup"><span data-stu-id="83e60-116">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
