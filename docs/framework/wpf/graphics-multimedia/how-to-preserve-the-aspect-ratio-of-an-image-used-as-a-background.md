---
title: 如何：保持背景图像的长宽比
ms.date: 03/30/2017
helpviewer_keywords:
- aspect ratios of background images [WPF], preserving
- brushes [WPF], preserving aspect ratios of background images
- background images [WPF], preserving aspect ratios
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
ms.openlocfilehash: df5632aa3d3c7dbc2442cabe1f4db7a850a1bd54
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353941"
---
# <a name="how-to-preserve-the-aspect-ratio-of-an-image-used-as-a-background"></a><span data-ttu-id="2fede-102">如何：保持背景图像的长宽比</span><span class="sxs-lookup"><span data-stu-id="2fede-102">How to: Preserve the Aspect Ratio of an Image Used as a Background</span></span>
<span data-ttu-id="2fede-103">此示例演示如何使用<xref:System.Windows.Media.TileBrush.Stretch%2A>属性的<xref:System.Windows.Media.ImageBrush>为了保持图像的纵横比。</span><span class="sxs-lookup"><span data-stu-id="2fede-103">This example shows how to use the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of an <xref:System.Windows.Media.ImageBrush> in order to preserve the aspect ratio of the image.</span></span>  
  
 <span data-ttu-id="2fede-104">默认情况下，当您使用<xref:System.Windows.Media.ImageBrush>绘制区域，其内容将进行拉伸以完全填充输出区域。</span><span class="sxs-lookup"><span data-stu-id="2fede-104">By default, when you use an <xref:System.Windows.Media.ImageBrush> to paint an area, its content stretches to completely fill the output area.</span></span> <span data-ttu-id="2fede-105">当输出区域和图像的纵横比不同时，图像就会因拉伸而失真。</span><span class="sxs-lookup"><span data-stu-id="2fede-105">When the output area and the image have different aspect ratios, the image is distorted by this stretching.</span></span>  
  
 <span data-ttu-id="2fede-106">若要使<xref:System.Windows.Media.ImageBrush>保持其图像的纵横比，设置<xref:System.Windows.Media.TileBrush.Stretch%2A>属性设置为<xref:System.Windows.Media.Stretch.Uniform>或<xref:System.Windows.Media.Stretch.UniformToFill>。</span><span class="sxs-lookup"><span data-stu-id="2fede-106">To make an <xref:System.Windows.Media.ImageBrush> preserve the aspect ratio of its image, set the <xref:System.Windows.Media.TileBrush.Stretch%2A> property to <xref:System.Windows.Media.Stretch.Uniform> or <xref:System.Windows.Media.Stretch.UniformToFill>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2fede-107">示例</span><span class="sxs-lookup"><span data-stu-id="2fede-107">Example</span></span>  
 <span data-ttu-id="2fede-108">下面的示例使用两个<xref:System.Windows.Media.ImageBrush>对象来绘制两个矩形。</span><span class="sxs-lookup"><span data-stu-id="2fede-108">The following example uses two <xref:System.Windows.Media.ImageBrush> objects to paint two rectangles.</span></span> <span data-ttu-id="2fede-109">每个矩形都为 300x150 像素，每个矩形都包含一个像素为 300x300 的图像。</span><span class="sxs-lookup"><span data-stu-id="2fede-109">Each rectangle is 300 by 150 pixels and each contains a 300 by 300 pixel image.</span></span> <span data-ttu-id="2fede-110"><xref:System.Windows.Media.TileBrush.Stretch%2A>的第一个画笔属性设置为<xref:System.Windows.Media.Stretch.Uniform>，并<xref:System.Windows.Media.TileBrush.Stretch%2A>第二个画笔的属性设置为<xref:System.Windows.Media.Stretch.UniformToFill>。</span><span class="sxs-lookup"><span data-stu-id="2fede-110">The <xref:System.Windows.Media.TileBrush.Stretch%2A> property of the first brush is set to <xref:System.Windows.Media.Stretch.Uniform>, and the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of the second brush is set to <xref:System.Windows.Media.Stretch.UniformToFill>.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 <span data-ttu-id="2fede-111">下图显示了具有第一个画笔的输出<xref:System.Windows.Media.TileBrush.Stretch%2A>设置的<xref:System.Windows.Media.Stretch.Uniform>。</span><span class="sxs-lookup"><span data-stu-id="2fede-111">The following illustration shows the output of the first brush, which has a <xref:System.Windows.Media.TileBrush.Stretch%2A> setting of <xref:System.Windows.Media.Stretch.Uniform>.</span></span>  
  
 <span data-ttu-id="2fede-112">![ImageBrush with Uniform stretching](./media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")</span><span class="sxs-lookup"><span data-stu-id="2fede-112">![ImageBrush with Uniform stretching](./media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")</span></span>  
  
 <span data-ttu-id="2fede-113">下图显示具有第二个画笔的输出<xref:System.Windows.Media.TileBrush.Stretch%2A>设置的<xref:System.Windows.Media.Stretch.UniformToFill>。</span><span class="sxs-lookup"><span data-stu-id="2fede-113">The next illustration shows the output of the second brush, which has a <xref:System.Windows.Media.TileBrush.Stretch%2A> setting of <xref:System.Windows.Media.Stretch.UniformToFill>.</span></span>  
  
 <span data-ttu-id="2fede-114">![具有 UniformToFill 拉伸的 ImageBrush](./media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")</span><span class="sxs-lookup"><span data-stu-id="2fede-114">![ImageBrush with UniformToFill stretching](./media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")</span></span>  
  
 <span data-ttu-id="2fede-115">请注意，<xref:System.Windows.Media.TileBrush.Stretch%2A>属性适用于其他的行为相同<xref:System.Windows.Media.TileBrush>对象，也就是说，对于<xref:System.Windows.Media.DrawingBrush>和<xref:System.Windows.Media.VisualBrush>。</span><span class="sxs-lookup"><span data-stu-id="2fede-115">Note that the <xref:System.Windows.Media.TileBrush.Stretch%2A> property behaves identically for the other <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.DrawingBrush> and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="2fede-116">有关详细信息<xref:System.Windows.Media.ImageBrush>和其他<xref:System.Windows.Media.TileBrush>对象，请参阅[使用图像、 绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)。</span><span class="sxs-lookup"><span data-stu-id="2fede-116">For more information about <xref:System.Windows.Media.ImageBrush> and the other <xref:System.Windows.Media.TileBrush> objects, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>  
  
 <span data-ttu-id="2fede-117">另请注意，尽管<xref:System.Windows.Media.TileBrush.Stretch%2A>属性将显示以指定如何<xref:System.Windows.Media.TileBrush>内容将进行拉伸以适合其输出区域，实际上指定了<xref:System.Windows.Media.TileBrush>内容拉伸以填充其基本磁贴。</span><span class="sxs-lookup"><span data-stu-id="2fede-117">Note also that, although the <xref:System.Windows.Media.TileBrush.Stretch%2A> property appears to specify how the <xref:System.Windows.Media.TileBrush> content stretches to fit its output area, it actually specifies how the <xref:System.Windows.Media.TileBrush> content stretches to fill its base tile.</span></span> <span data-ttu-id="2fede-118">有关详细信息，请参阅 <xref:System.Windows.Media.TileBrush>。</span><span class="sxs-lookup"><span data-stu-id="2fede-118">For more information, see <xref:System.Windows.Media.TileBrush>.</span></span>  
  
 <span data-ttu-id="2fede-119">此代码示例是为提供一个更大示例的一部分<xref:System.Windows.Media.ImageBrush>类。</span><span class="sxs-lookup"><span data-stu-id="2fede-119">This code example is part of a larger example that is provided for the <xref:System.Windows.Media.ImageBrush> class.</span></span> <span data-ttu-id="2fede-120">有关完整示例，请参阅[ImageBrush 示例](https://go.microsoft.com/fwlink/?LinkID=160005)。</span><span class="sxs-lookup"><span data-stu-id="2fede-120">For the complete sample, see [ImageBrush Sample](https://go.microsoft.com/fwlink/?LinkID=160005).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fede-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="2fede-121">See also</span></span>
- <xref:System.Windows.Media.TileBrush>
- [<span data-ttu-id="2fede-122">使用图像、绘图和视觉对象进行绘制</span><span class="sxs-lookup"><span data-stu-id="2fede-122">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
