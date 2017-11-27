---
title: "如何：绘制椭圆或圆"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ellipses [WPF], drawing
- circles [WPF], drawing
- drawing circles [WPF]
- drawing ellipses [WPF]
- graphics [WPF], drawing circles
- graphics [WPF], drawing ellipses
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4da623c34b4c3b84dee0f02d631d032eb1c061d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a><span data-ttu-id="002a7-102">如何：绘制椭圆或圆</span><span class="sxs-lookup"><span data-stu-id="002a7-102">How to: Draw an Ellipse or a Circle</span></span>
<span data-ttu-id="002a7-103">此示例演示如何使用绘制椭圆形和圆形<xref:System.Windows.Shapes.Ellipse>元素。</span><span class="sxs-lookup"><span data-stu-id="002a7-103">This example shows how to draw ellipses and circles by using the <xref:System.Windows.Shapes.Ellipse> element.</span></span> <span data-ttu-id="002a7-104">若要绘制一个椭圆，创建<xref:System.Windows.Shapes.Ellipse>元素并指定其<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>。</span><span class="sxs-lookup"><span data-stu-id="002a7-104">To draw an ellipse, create an <xref:System.Windows.Shapes.Ellipse> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="002a7-105">使用其<xref:System.Windows.Shapes.Shape.Fill%2A>属性指定<xref:System.Windows.Media.Brush>用于绘制椭圆的内部。</span><span class="sxs-lookup"><span data-stu-id="002a7-105">Use its <xref:System.Windows.Shapes.Shape.Fill%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the interior of the ellipse.</span></span> <span data-ttu-id="002a7-106">使用其<xref:System.Windows.Shapes.Shape.Stroke%2A>属性指定<xref:System.Windows.Media.Brush>用于绘制椭圆的边框。</span><span class="sxs-lookup"><span data-stu-id="002a7-106">Use its <xref:System.Windows.Shapes.Shape.Stroke%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the outline of the ellipse.</span></span> <span data-ttu-id="002a7-107"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>属性指定的椭圆的边框粗细。</span><span class="sxs-lookup"><span data-stu-id="002a7-107">The <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> property specifies the thickness of the ellipse outline.</span></span>  
  
 <span data-ttu-id="002a7-108">若要绘制的圆形，请<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>的<xref:System.Windows.Shapes.Ellipse>彼此相等的元素。</span><span class="sxs-lookup"><span data-stu-id="002a7-108">To draw a circle, make the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> of the <xref:System.Windows.Shapes.Ellipse> element equal to each other.</span></span>  
  
 <span data-ttu-id="002a7-109">下面的示例绘制了四个<xref:System.Windows.Shapes.Ellipse>中的元素<xref:System.Windows.Controls.Canvas>。</span><span class="sxs-lookup"><span data-stu-id="002a7-109">The following example draws four <xref:System.Windows.Shapes.Ellipse> elements within a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="002a7-110">示例</span><span class="sxs-lookup"><span data-stu-id="002a7-110">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 <span data-ttu-id="002a7-111">虽然此示例使用<xref:System.Windows.Controls.Canvas>来包含省略号，但是您可以使用椭圆元素 （以及所有其他形状元素） 以及任何<xref:System.Windows.Controls.Panel>或<xref:System.Windows.Controls.Control>支持非文本内容。</span><span class="sxs-lookup"><span data-stu-id="002a7-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the ellipses, you can use ellipse elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="002a7-112">此示例摘自更大的示例;有关完整的示例，请参阅[形状元素示例](http://go.microsoft.com/fwlink/?LinkID=160037)。</span><span class="sxs-lookup"><span data-stu-id="002a7-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="002a7-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="002a7-113">See Also</span></span>  
 <xref:System.Windows.Shapes.Ellipse>  
 <xref:System.Windows.Shapes.Shape>  
 [<span data-ttu-id="002a7-114">形状元素示例</span><span class="sxs-lookup"><span data-stu-id="002a7-114">Shape Elements Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160037)
