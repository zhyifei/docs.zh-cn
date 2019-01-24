---
title: 如何：使用 ImageDrawing 绘制图像
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], images
- graphics [WPF], drawing images
- images [WPF], drawing
ms.assetid: df28ab41-25fb-4ab3-b51d-7f695b24f55e
ms.openlocfilehash: 5c1617d1a60fde8e9f1c215a5b644f6fd330817a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629067"
---
# <a name="how-to-draw-an-image-using-imagedrawing"></a><span data-ttu-id="a6755-102">如何：使用 ImageDrawing 绘制图像</span><span class="sxs-lookup"><span data-stu-id="a6755-102">How to: Draw an Image Using ImageDrawing</span></span>
<span data-ttu-id="a6755-103">此示例演示如何使用<xref:System.Windows.Media.ImageDrawing>要绘制图像。</span><span class="sxs-lookup"><span data-stu-id="a6755-103">This example shows how to use an <xref:System.Windows.Media.ImageDrawing> to draw an image.</span></span> <span data-ttu-id="a6755-104"><xref:System.Windows.Media.ImageDrawing>允许您显示<xref:System.Windows.Media.ImageSource>与<xref:System.Windows.Media.DrawingBrush>， <xref:System.Windows.Media.DrawingImage>，或<xref:System.Windows.Media.Visual>。</span><span class="sxs-lookup"><span data-stu-id="a6755-104">An <xref:System.Windows.Media.ImageDrawing> enables you display an <xref:System.Windows.Media.ImageSource> with a <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage>, or <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="a6755-105">若要绘制图像，则创建<xref:System.Windows.Media.ImageDrawing>并设置其<xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType>和<xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="a6755-105">To draw an image, you create an <xref:System.Windows.Media.ImageDrawing> and set its <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> and <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> properties.</span></span> <span data-ttu-id="a6755-106"><xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType>属性指定要绘制，图像和<xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType>属性指定的位置和每个图像的大小。</span><span class="sxs-lookup"><span data-stu-id="a6755-106">The <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> property specifies the image to draw, and the <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> property specifies the position and size of each image.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6755-107">示例</span><span class="sxs-lookup"><span data-stu-id="a6755-107">Example</span></span>  
 <span data-ttu-id="a6755-108">下面的示例创建复合绘图使用四个<xref:System.Windows.Media.ImageDrawing>对象。</span><span class="sxs-lookup"><span data-stu-id="a6755-108">The following example creates a composite drawing using four <xref:System.Windows.Media.ImageDrawing> objects.</span></span> <span data-ttu-id="a6755-109">此示例将生成以下映像：</span><span class="sxs-lookup"><span data-stu-id="a6755-109">This example produces the following image:</span></span>  
  
 <span data-ttu-id="a6755-110">![几个 DrawingImage 对象](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")</span><span class="sxs-lookup"><span data-stu-id="a6755-110">![Several DrawingImage objects](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")</span></span>  
<span data-ttu-id="a6755-111">四个 ImageDrawing 对象</span><span class="sxs-lookup"><span data-stu-id="a6755-111">Four ImageDrawing objects</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawingExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawingexample)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawingExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawingexample)]  
  
 <span data-ttu-id="a6755-112">有关演示简单的方法来显示图像而不使用的示例<xref:System.Windows.Media.ImageDrawing>，请参阅[使用 Image 元素](../../../../docs/framework/wpf/controls/how-to-use-the-image-element.md)。</span><span class="sxs-lookup"><span data-stu-id="a6755-112">For an example showing a simple way to display an image without using <xref:System.Windows.Media.ImageDrawing>, see [Use the Image Element](../../../../docs/framework/wpf/controls/how-to-use-the-image-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6755-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6755-113">See also</span></span>
- <xref:System.Windows.Freezable.Freeze%2A>
- <xref:System.Windows.Controls.Image>
- [<span data-ttu-id="a6755-114">Drawing 对象概述</span><span class="sxs-lookup"><span data-stu-id="a6755-114">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="a6755-115">Freezable 对象概述</span><span class="sxs-lookup"><span data-stu-id="a6755-115">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)
- [<span data-ttu-id="a6755-116">PresentationOptions:Freeze 特性</span><span class="sxs-lookup"><span data-stu-id="a6755-116">PresentationOptions:Freeze Attribute</span></span>](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)
