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
ms.openlocfilehash: 2b88982e7a8d196c31869dc74aac636d78f68386
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207807"
---
# <a name="how-to-paint-an-area-with-an-image"></a><span data-ttu-id="bd820-102">如何：使用图像绘制区域</span><span class="sxs-lookup"><span data-stu-id="bd820-102">How to: Paint an Area with an Image</span></span>
<span data-ttu-id="bd820-103">此示例演示如何使用<xref:System.Windows.Media.ImageBrush>类，以使用图像绘制区域。</span><span class="sxs-lookup"><span data-stu-id="bd820-103">This example shows how to use the <xref:System.Windows.Media.ImageBrush> class to paint an area with an image.</span></span> <span data-ttu-id="bd820-104"><xref:System.Windows.Media.ImageBrush>显示由指定的单个映像及其<xref:System.Windows.Media.ImageBrush.ImageSource%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="bd820-104">An <xref:System.Windows.Media.ImageBrush> displays a single image, which is specified by its <xref:System.Windows.Media.ImageBrush.ImageSource%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd820-105">示例</span><span class="sxs-lookup"><span data-stu-id="bd820-105">Example</span></span>  
 <span data-ttu-id="bd820-106">以下示例绘制<xref:System.Windows.Controls.Control.Background%2A>通过使用一个按钮<xref:System.Windows.Media.ImageBrush>。</span><span class="sxs-lookup"><span data-stu-id="bd820-106">The following example paints the <xref:System.Windows.Controls.Control.Background%2A> of a button by using an <xref:System.Windows.Media.ImageBrush>.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 <span data-ttu-id="bd820-107">默认情况下，<xref:System.Windows.Media.ImageBrush>拉伸其图像以完全填充要绘制的区域。</span><span class="sxs-lookup"><span data-stu-id="bd820-107">By default, an <xref:System.Windows.Media.ImageBrush> stretches its image to completely fill the area that you are painting.</span></span> <span data-ttu-id="bd820-108">在以上示例中，拉伸图像以填充按钮，可能会使图像失真。</span><span class="sxs-lookup"><span data-stu-id="bd820-108">In the preceding example, the image is stretched to fill the button, possibly distorting the image.</span></span> <span data-ttu-id="bd820-109">可以通过设置控制此行为<xref:System.Windows.Media.TileBrush.Stretch%2A>的属性<xref:System.Windows.Media.TileBrush>到<xref:System.Windows.Media.Stretch.Uniform>或<xref:System.Windows.Media.Stretch.UniformToFill>，这将导致要保持图像的纵横比的画笔。</span><span class="sxs-lookup"><span data-stu-id="bd820-109">You can control this behavior by setting the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of <xref:System.Windows.Media.TileBrush> to <xref:System.Windows.Media.Stretch.Uniform> or <xref:System.Windows.Media.Stretch.UniformToFill>, which causes the brush to preserve the aspect ratio of the image.</span></span>  
  
 <span data-ttu-id="bd820-110">如果您设置<xref:System.Windows.Media.TileBrush.Viewport%2A>并<xref:System.Windows.Media.TileBrush.TileMode%2A>的属性<xref:System.Windows.Media.ImageBrush>，可以创建一个重复图案。</span><span class="sxs-lookup"><span data-stu-id="bd820-110">If you set the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> properties of an <xref:System.Windows.Media.ImageBrush>, you can create a repeating pattern.</span></span> <span data-ttu-id="bd820-111">以下示例通过使用从图像创建的图案来绘制按钮。</span><span class="sxs-lookup"><span data-stu-id="bd820-111">The following example paints a button by using a pattern that is created from an image.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 <span data-ttu-id="bd820-112">有关详细信息<xref:System.Windows.Media.ImageBrush>类，请参阅[使用图像、 绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)。</span><span class="sxs-lookup"><span data-stu-id="bd820-112">For more information about the <xref:System.Windows.Media.ImageBrush> class, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>  
  
 <span data-ttu-id="bd820-113">此代码示例是为提供一个更大示例的一部分<xref:System.Windows.Media.ImageBrush>类。</span><span class="sxs-lookup"><span data-stu-id="bd820-113">This code example is part of a larger example that is provided for the <xref:System.Windows.Media.ImageBrush> class.</span></span> <span data-ttu-id="bd820-114">有关完整示例，请参阅[ImageBrush 示例](https://go.microsoft.com/fwlink/?LinkID=160005)。</span><span class="sxs-lookup"><span data-stu-id="bd820-114">For the complete sample, see [ImageBrush Sample](https://go.microsoft.com/fwlink/?LinkID=160005).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd820-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd820-115">See also</span></span>

- [<span data-ttu-id="bd820-116">使用图像、图形和视觉对象进行绘制</span><span class="sxs-lookup"><span data-stu-id="bd820-116">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
