---
title: 如何：使用视频绘制区域
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- painting with a video [WPF]
- video [WPF], painting with
- brushes [WPF], painting with a video
ms.assetid: 04dd6600-4a6e-4b43-a93e-21cce7dfbcb8
ms.openlocfilehash: 0756a9e87840648b55ecad4b3f1ce6e0e5452eb7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363288"
---
# <a name="how-to-paint-an-area-with-a-video"></a><span data-ttu-id="9e7dd-102">如何：使用视频绘制区域</span><span class="sxs-lookup"><span data-stu-id="9e7dd-102">How to: Paint an Area with a Video</span></span>
<span data-ttu-id="9e7dd-103">此示例演示如何使用媒体绘制区域。</span><span class="sxs-lookup"><span data-stu-id="9e7dd-103">This example shows how to paint an area with media.</span></span> <span data-ttu-id="9e7dd-104">使用媒体绘制区域的一种方法是使用<xref:System.Windows.Controls.MediaElement>一起使用<xref:System.Windows.Media.VisualBrush>。</span><span class="sxs-lookup"><span data-stu-id="9e7dd-104">One way to paint an area with media is to use a <xref:System.Windows.Controls.MediaElement> together with a <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="9e7dd-105">使用<xref:System.Windows.Controls.MediaElement>若要加载和播放媒体，并使用它来设置<xref:System.Windows.Media.VisualBrush.Visual%2A>属性的<xref:System.Windows.Media.VisualBrush>。</span><span class="sxs-lookup"><span data-stu-id="9e7dd-105">Use the <xref:System.Windows.Controls.MediaElement> to load and play the media, and then use it to set the <xref:System.Windows.Media.VisualBrush.Visual%2A> property of the <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="9e7dd-106">然后，可以使用<xref:System.Windows.Media.VisualBrush>要加载的介质使用绘制区域。</span><span class="sxs-lookup"><span data-stu-id="9e7dd-106">You can then use the <xref:System.Windows.Media.VisualBrush> to paint an area with the loaded media.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e7dd-107">示例</span><span class="sxs-lookup"><span data-stu-id="9e7dd-107">Example</span></span>  
 <span data-ttu-id="9e7dd-108">下面的示例使用<xref:System.Windows.Controls.MediaElement>和一个<xref:System.Windows.Media.VisualBrush>绘制<xref:System.Windows.Controls.TextBlock.Foreground%2A>的<xref:System.Windows.Controls.TextBlock>控件使用的视频。</span><span class="sxs-lookup"><span data-stu-id="9e7dd-108">The following example uses a <xref:System.Windows.Controls.MediaElement> and a <xref:System.Windows.Media.VisualBrush> to paint the <xref:System.Windows.Controls.TextBlock.Foreground%2A> of a <xref:System.Windows.Controls.TextBlock> control with video.</span></span> <span data-ttu-id="9e7dd-109">此示例设置<xref:System.Windows.Controls.MediaElement.IsMuted%2A>的属性<xref:System.Windows.Controls.MediaElement>到`true`，以便它不发出声音。</span><span class="sxs-lookup"><span data-stu-id="9e7dd-109">This example sets the <xref:System.Windows.Controls.MediaElement.IsMuted%2A> property of the <xref:System.Windows.Controls.MediaElement> to `true` so that it produces no sound.</span></span>  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundinline)]  
  
## <a name="example"></a><span data-ttu-id="9e7dd-110">示例</span><span class="sxs-lookup"><span data-stu-id="9e7dd-110">Example</span></span>  
 <span data-ttu-id="9e7dd-111">因为<xref:System.Windows.Media.VisualBrush>继承<xref:System.Windows.Media.TileBrush>类，它提供了几个平铺模式。</span><span class="sxs-lookup"><span data-stu-id="9e7dd-111">Because <xref:System.Windows.Media.VisualBrush> inherits from the <xref:System.Windows.Media.TileBrush> class, it provides several tiling modes.</span></span> <span data-ttu-id="9e7dd-112">通过设置<xref:System.Windows.Media.TileBrush.TileMode%2A>的属性<xref:System.Windows.Media.VisualBrush>到<xref:System.Windows.Media.TileMode.Tile>并设置其<xref:System.Windows.Media.TileBrush.Viewport%2A>属性的值小于要绘制的区域，可以创建一个平铺的图案。</span><span class="sxs-lookup"><span data-stu-id="9e7dd-112">By setting the <xref:System.Windows.Media.TileBrush.TileMode%2A> property of a <xref:System.Windows.Media.VisualBrush> to <xref:System.Windows.Media.TileMode.Tile> and by setting its <xref:System.Windows.Media.TileBrush.Viewport%2A> property to a value smaller than the area that you are painting, you can create a tiled pattern.</span></span>  
  
 <span data-ttu-id="9e7dd-113">下面的示例等同于上一示例中，不同之处在于<xref:System.Windows.Media.VisualBrush>来自视频将生成一种模式。</span><span class="sxs-lookup"><span data-stu-id="9e7dd-113">The following example is identical to the previous example, except that the <xref:System.Windows.Media.VisualBrush> generates a pattern from the video.</span></span>  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundtiledinline)]  
  
 <span data-ttu-id="9e7dd-114">了解如何将内容文件，例如媒体文件添加到您的应用程序，请参阅[WPF 应用程序资源、 内容和数据文件](../app-development/wpf-application-resource-content-and-data-files.md)。</span><span class="sxs-lookup"><span data-stu-id="9e7dd-114">For information about how to add a content file, such as a media file, to your application, see [WPF Application Resource, Content, and Data Files](../app-development/wpf-application-resource-content-and-data-files.md).</span></span> <span data-ttu-id="9e7dd-115">当添加媒体文件时，必须将其添加，作为内容文件，而不是资源文件。</span><span class="sxs-lookup"><span data-stu-id="9e7dd-115">When you add a media file, you must add it as a content file, not as a resource file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e7dd-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e7dd-116">See also</span></span>
- <xref:System.Windows.Media.VisualBrush>
- [<span data-ttu-id="9e7dd-117">使用图像、绘图和视觉对象进行绘制</span><span class="sxs-lookup"><span data-stu-id="9e7dd-117">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="9e7dd-118">TileBrush 概述</span><span class="sxs-lookup"><span data-stu-id="9e7dd-118">TileBrush Overview</span></span>](tilebrush-overview.md)
- [<span data-ttu-id="9e7dd-119">多媒体概述</span><span class="sxs-lookup"><span data-stu-id="9e7dd-119">Multimedia Overview</span></span>](multimedia-overview.md)
