---
title: "如何：变换画笔"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], rotating contents
- brushes [WPF], Transform property
- rotating contents of brushes [WPF]
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ee517eb76877bb4e02c021061055b328597c517
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-transform-a-brush"></a><span data-ttu-id="aef91-102">如何：变换画笔</span><span class="sxs-lookup"><span data-stu-id="aef91-102">How to: Transform a Brush</span></span>
<span data-ttu-id="aef91-103">此示例演示如何将转换<xref:System.Windows.Media.Brush>通过使用其两个转换属性的对象：<xref:System.Windows.Media.Brush.RelativeTransform%2A>和<xref:System.Windows.Media.Brush.Transform%2A>。</span><span class="sxs-lookup"><span data-stu-id="aef91-103">This example shows how to transform <xref:System.Windows.Media.Brush> objects by using their two transformation properties: <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A>.</span></span>  
  
 <span data-ttu-id="aef91-104">下面的示例使用<xref:System.Windows.Media.RotateTransform>要旋转的内容<xref:System.Windows.Media.ImageBrush>旋转 45 度。</span><span class="sxs-lookup"><span data-stu-id="aef91-104">The following examples use a <xref:System.Windows.Media.RotateTransform> to rotate the content of an <xref:System.Windows.Media.ImageBrush> by 45 degrees.</span></span>  
  
 <span data-ttu-id="aef91-105">下图显示<xref:System.Windows.Media.ImageBrush>而无需<xref:System.Windows.Media.RotateTransform>，与<xref:System.Windows.Media.RotateTransform>应用于<xref:System.Windows.Media.Brush.RelativeTransform%2A>属性，且<xref:System.Windows.Media.RotateTransform>应用于<xref:System.Windows.Media.Brush.Transform%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="aef91-105">The following illustration shows the <xref:System.Windows.Media.ImageBrush> without a <xref:System.Windows.Media.RotateTransform>, with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property, and with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.Transform%2A> property.</span></span>  
  
 <span data-ttu-id="aef91-106">![画笔 RelativeTransform 和 Transform 设置](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span><span class="sxs-lookup"><span data-stu-id="aef91-106">![Brush RelativeTransform and Transform settings](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span></span>  
  
## <a name="example"></a><span data-ttu-id="aef91-107">示例</span><span class="sxs-lookup"><span data-stu-id="aef91-107">Example</span></span>  
 <span data-ttu-id="aef91-108">第一个示例适用<xref:System.Windows.Media.RotateTransform>到<xref:System.Windows.Media.Brush.RelativeTransform%2A>属性<xref:System.Windows.Media.ImageBrush>。</span><span class="sxs-lookup"><span data-stu-id="aef91-108">The first example applies a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property of an <xref:System.Windows.Media.ImageBrush>.</span></span> <span data-ttu-id="aef91-109"><xref:System.Windows.Media.RotateTransform.CenterX%2A>和<xref:System.Windows.Media.RotateTransform.CenterY%2A>属性<xref:System.Windows.Media.RotateTransform>对象都设置为 0.5，这是此内容的中心点的相对坐标。</span><span class="sxs-lookup"><span data-stu-id="aef91-109">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of a <xref:System.Windows.Media.RotateTransform> object are both set to 0.5, which is the relative coordinate of the center point of this content.</span></span> <span data-ttu-id="aef91-110">因此，<xref:System.Windows.Media.ImageBrush>内容围绕其中心。</span><span class="sxs-lookup"><span data-stu-id="aef91-110">As a result, the <xref:System.Windows.Media.ImageBrush> content rotates about its center.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 <span data-ttu-id="aef91-111">第二个示例也适用<xref:System.Windows.Media.RotateTransform>到<xref:System.Windows.Media.ImageBrush>; 但是，此示例使用<xref:System.Windows.Media.Brush.Transform%2A>属性而不是<xref:System.Windows.Media.Brush.RelativeTransform%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="aef91-111">The second example also applies a <xref:System.Windows.Media.RotateTransform> to an <xref:System.Windows.Media.ImageBrush>; however, this example uses the <xref:System.Windows.Media.Brush.Transform%2A> property instead of the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property.</span></span>  
  
 <span data-ttu-id="aef91-112">若要将围绕其中心画笔，该示例设置<xref:System.Windows.Media.RotateTransform.CenterX%2A>和<xref:System.Windows.Media.RotateTransform.CenterY%2A>属性<xref:System.Windows.Media.RotateTransform>为绝对坐标的对象。</span><span class="sxs-lookup"><span data-stu-id="aef91-112">To rotate the brush about its center, the example sets the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> object to absolute coordinates.</span></span> <span data-ttu-id="aef91-113">因为画笔绘制了一个 175x90 像素的矩形，所以该矩形的中心点为 (87.5, 45)。</span><span class="sxs-lookup"><span data-stu-id="aef91-113">Because the brush paints a rectangle that is 175 by 90 pixels, the center point of the rectangle is (87.5, 45).</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 <span data-ttu-id="aef91-114">有关如何说明<xref:System.Windows.Media.Brush.RelativeTransform%2A>和<xref:System.Windows.Media.Brush.Transform%2A>属性工作，请参见[画笔转换概述](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="aef91-114">For a description of how the <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A> properties work, see the [Brush Transformation Overview](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md).</span></span>  
  
 <span data-ttu-id="aef91-115">有关完整示例，请参阅[画笔示例](http://go.microsoft.com/fwlink/?LinkID=159973)。</span><span class="sxs-lookup"><span data-stu-id="aef91-115">For the complete sample, see [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="aef91-116">有关画笔的详细信息，请参阅[使用纯色和渐变进行绘制概述](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="aef91-116">For more information about brushes, see [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aef91-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="aef91-117">See Also</span></span>  
 [<span data-ttu-id="aef91-118">画笔转换概述</span><span class="sxs-lookup"><span data-stu-id="aef91-118">Brush Transformation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md)  
 [<span data-ttu-id="aef91-119">使用纯色和渐变进行绘制概述</span><span class="sxs-lookup"><span data-stu-id="aef91-119">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [<span data-ttu-id="aef91-120">转换概述</span><span class="sxs-lookup"><span data-stu-id="aef91-120">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
