---
title: 如何：将绘图用作图像源
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], drawings [WPF], as image sources
- image sources [WPF], drawings
- drawings [WPF], as image sources
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
ms.openlocfilehash: 07659463a3fec9b962f7b4bb255ed065d544d954
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351731"
---
# <a name="how-to-use-a-drawing-as-an-image-source"></a><span data-ttu-id="22d52-102">如何：将绘图用作图像源</span><span class="sxs-lookup"><span data-stu-id="22d52-102">How to: Use a Drawing as an Image Source</span></span>
<span data-ttu-id="22d52-103">此示例演示如何使用<xref:System.Windows.Media.Drawing>作为<xref:System.Windows.Controls.Image.Source%2A>为<xref:System.Windows.Controls.Image>控件。</span><span class="sxs-lookup"><span data-stu-id="22d52-103">This example shows how to use a <xref:System.Windows.Media.Drawing> as the <xref:System.Windows.Controls.Image.Source%2A> for an <xref:System.Windows.Controls.Image> control.</span></span> <span data-ttu-id="22d52-104">若要显示<xref:System.Windows.Media.Drawing>与<xref:System.Windows.Controls.Image>控制，请使用<xref:System.Windows.Media.DrawingImage>作为<xref:System.Windows.Controls.Image>控件的<xref:System.Windows.Controls.Image.Source%2A>并设置<xref:System.Windows.Media.DrawingImage>对象的<xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType>属性设置为你想要显示的绘图。</span><span class="sxs-lookup"><span data-stu-id="22d52-104">To display a <xref:System.Windows.Media.Drawing> with an <xref:System.Windows.Controls.Image> control, use a <xref:System.Windows.Media.DrawingImage> as the <xref:System.Windows.Controls.Image> control's <xref:System.Windows.Controls.Image.Source%2A> and set the <xref:System.Windows.Media.DrawingImage> object's <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> property to the drawing you want to display.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22d52-105">示例</span><span class="sxs-lookup"><span data-stu-id="22d52-105">Example</span></span>  
 <span data-ttu-id="22d52-106">下面的示例使用<xref:System.Windows.Media.DrawingImage>和一个<xref:System.Windows.Controls.Image>控件来显示<xref:System.Windows.Media.GeometryDrawing>。</span><span class="sxs-lookup"><span data-stu-id="22d52-106">The following example uses a <xref:System.Windows.Media.DrawingImage> and an <xref:System.Windows.Controls.Image> control to display a <xref:System.Windows.Media.GeometryDrawing>.</span></span> <span data-ttu-id="22d52-107">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="22d52-107">This example produces the following output:</span></span>  
  
 <span data-ttu-id="22d52-108">![两个椭圆的 GeometryDrawing](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span><span class="sxs-lookup"><span data-stu-id="22d52-108">![A GeometryDrawing of two ellipses](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span></span>  
<span data-ttu-id="22d52-109">一个 DrawingImage</span><span class="sxs-lookup"><span data-stu-id="22d52-109">A DrawingImage</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="22d52-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="22d52-110">See also</span></span>
- <xref:System.Windows.Freezable.Freeze%2A>
- [<span data-ttu-id="22d52-111">使用 ImageDrawing 绘制图像</span><span class="sxs-lookup"><span data-stu-id="22d52-111">Draw an Image Using ImageDrawing</span></span>](how-to-draw-an-image-using-imagedrawing.md)
- [<span data-ttu-id="22d52-112">Drawing 对象概述</span><span class="sxs-lookup"><span data-stu-id="22d52-112">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="22d52-113">Freezable 对象概述</span><span class="sxs-lookup"><span data-stu-id="22d52-113">Freezable Objects Overview</span></span>](../advanced/freezable-objects-overview.md)
- [<span data-ttu-id="22d52-114">PresentationOptions:Freeze 特性</span><span class="sxs-lookup"><span data-stu-id="22d52-114">PresentationOptions:Freeze Attribute</span></span>](../advanced/presentationoptions-freeze-attribute.md)
