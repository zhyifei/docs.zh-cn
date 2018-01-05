---
title: "如何：将绘图用作图像源"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [WPF], drawings [WPF], as image sources
- image sources [WPF], drawings
- drawings [WPF], as image sources
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5e0fe8f7d3633143348693c95d92dd2715bd0442
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-drawing-as-an-image-source"></a><span data-ttu-id="09089-102">如何：将绘图用作图像源</span><span class="sxs-lookup"><span data-stu-id="09089-102">How to: Use a Drawing as an Image Source</span></span>
<span data-ttu-id="09089-103">此示例演示如何使用<xref:System.Windows.Media.Drawing>作为<xref:System.Windows.Controls.Image.Source%2A>为<xref:System.Windows.Controls.Image>控件。</span><span class="sxs-lookup"><span data-stu-id="09089-103">This example shows how to use a <xref:System.Windows.Media.Drawing> as the <xref:System.Windows.Controls.Image.Source%2A> for an <xref:System.Windows.Controls.Image> control.</span></span> <span data-ttu-id="09089-104">若要显示<xref:System.Windows.Media.Drawing>与<xref:System.Windows.Controls.Image>控制，请使用<xref:System.Windows.Media.DrawingImage>作为<xref:System.Windows.Controls.Image>控件的<xref:System.Windows.Controls.Image.Source%2A>并设置<xref:System.Windows.Media.DrawingImage>对象的<xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType>到绘图想要显示的属性。</span><span class="sxs-lookup"><span data-stu-id="09089-104">To display a <xref:System.Windows.Media.Drawing> with an <xref:System.Windows.Controls.Image> control, use a <xref:System.Windows.Media.DrawingImage> as the <xref:System.Windows.Controls.Image> control's <xref:System.Windows.Controls.Image.Source%2A> and set the <xref:System.Windows.Media.DrawingImage> object's <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> property to the drawing you want to display.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09089-105">示例</span><span class="sxs-lookup"><span data-stu-id="09089-105">Example</span></span>  
 <span data-ttu-id="09089-106">下面的示例使用<xref:System.Windows.Media.DrawingImage>和<xref:System.Windows.Controls.Image>控件来显示<xref:System.Windows.Media.GeometryDrawing>。</span><span class="sxs-lookup"><span data-stu-id="09089-106">The following example uses a <xref:System.Windows.Media.DrawingImage> and an <xref:System.Windows.Controls.Image> control to display a <xref:System.Windows.Media.GeometryDrawing>.</span></span> <span data-ttu-id="09089-107">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="09089-107">This example produces the following output:</span></span>  
  
 <span data-ttu-id="09089-108">![两个椭圆的 GeometryDrawing](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span><span class="sxs-lookup"><span data-stu-id="09089-108">![A GeometryDrawing of two ellipses](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span></span>  
<span data-ttu-id="09089-109">一个 DrawingImage</span><span class="sxs-lookup"><span data-stu-id="09089-109">A DrawingImage</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="09089-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="09089-110">See Also</span></span>  
 <xref:System.Windows.Freezable.Freeze%2A>  
 [<span data-ttu-id="09089-111">使用 ImageDrawing 绘制图像</span><span class="sxs-lookup"><span data-stu-id="09089-111">Draw an Image Using ImageDrawing</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-draw-an-image-using-imagedrawing.md)  
 [<span data-ttu-id="09089-112">Drawing 对象概述</span><span class="sxs-lookup"><span data-stu-id="09089-112">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="09089-113">Freezable 对象概述</span><span class="sxs-lookup"><span data-stu-id="09089-113">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="09089-114">PresentationOptions:Freeze 特性</span><span class="sxs-lookup"><span data-stu-id="09089-114">PresentationOptions:Freeze Attribute</span></span>](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)
