---
title: 如何：将 Visual 编码为图像文件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image files [WPF], encoding from visuals
- encoding image formats [WPF]
- visuals [WPF], encoding to an image file
ms.assetid: 2036385b-ea47-4d54-8027-5797f52c8149
ms.openlocfilehash: e8988256d4b7181c5e1af12252ca26e0248d016f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645218"
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a><span data-ttu-id="62dce-102">如何：将 Visual 编码为图像文件</span><span class="sxs-lookup"><span data-stu-id="62dce-102">How to: Encode a Visual to an Image File</span></span>
<span data-ttu-id="62dce-103">此示例演示如何进行编码<xref:System.Windows.Media.Visual>为图像文件，并使用对象<xref:System.Windows.Media.Imaging.RenderTargetBitmap>和一个<xref:System.Windows.Media.Imaging.PngBitmapEncoder>。</span><span class="sxs-lookup"><span data-stu-id="62dce-103">This example demonstrates how to encode a <xref:System.Windows.Media.Visual> object into an image file using a <xref:System.Windows.Media.Imaging.RenderTargetBitmap> and a <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62dce-104">示例</span><span class="sxs-lookup"><span data-stu-id="62dce-104">Example</span></span>  
 <span data-ttu-id="62dce-105"><xref:System.Windows.Media.DrawingVisual>使用创建<xref:System.Windows.Media.Imaging.BitmapImage>并<xref:System.Windows.Media.FormattedText>呈现到<xref:System.Windows.Media.Imaging.RenderTargetBitmap>。</span><span class="sxs-lookup"><span data-stu-id="62dce-105">The <xref:System.Windows.Media.DrawingVisual> is created using a <xref:System.Windows.Media.Imaging.BitmapImage> and <xref:System.Windows.Media.FormattedText> which is rendered to a <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.</span></span> <span data-ttu-id="62dce-106">呈现的位图随后用于创建<xref:System.Windows.Media.Imaging.BitmapFrame>添加到<xref:System.Windows.Media.Imaging.PngBitmapEncoder>若要创建一个新[!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)]文件。</span><span class="sxs-lookup"><span data-stu-id="62dce-106">The rendered bitmap is then used to create a <xref:System.Windows.Media.Imaging.BitmapFrame> which is added to the <xref:System.Windows.Media.Imaging.PngBitmapEncoder> to create a new [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] file.</span></span>  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 <span data-ttu-id="62dce-107">一个<xref:System.Windows.Media.Imaging.PngBitmapEncoder>使用在此示例中，但任何派生<xref:System.Windows.Media.Imaging.BitmapEncoder>对象可能已用来创建图像文件。</span><span class="sxs-lookup"><span data-stu-id="62dce-107">A <xref:System.Windows.Media.Imaging.PngBitmapEncoder> was used in this example but any of the derived <xref:System.Windows.Media.Imaging.BitmapEncoder> objects could have been used to create the image file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62dce-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="62dce-108">See also</span></span>
- <xref:System.Windows.Media.DrawingContext>
- [<span data-ttu-id="62dce-109">图像处理概述</span><span class="sxs-lookup"><span data-stu-id="62dce-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
- [<span data-ttu-id="62dce-110">Drawing 对象概述</span><span class="sxs-lookup"><span data-stu-id="62dce-110">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="62dce-111">使用 DrawingVisual 对象</span><span class="sxs-lookup"><span data-stu-id="62dce-111">Using DrawingVisual Objects</span></span>](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)
