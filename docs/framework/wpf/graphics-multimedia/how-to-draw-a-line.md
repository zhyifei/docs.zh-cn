---
title: 如何：绘制线条
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: 54152b6b68dd453c565afa2ffb23edfe8132a441
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629015"
---
# <a name="how-to-draw-a-line"></a><span data-ttu-id="3d877-102">如何：绘制线条</span><span class="sxs-lookup"><span data-stu-id="3d877-102">How to: Draw a Line</span></span>
<span data-ttu-id="3d877-103">此示例演示如何通过使用绘制线条<xref:System.Windows.Shapes.Line>元素。</span><span class="sxs-lookup"><span data-stu-id="3d877-103">This example shows you how to draw lines by using the <xref:System.Windows.Shapes.Line> element.</span></span>  
  
 <span data-ttu-id="3d877-104">若要绘制一条线，请创建<xref:System.Windows.Shapes.Line>元素。</span><span class="sxs-lookup"><span data-stu-id="3d877-104">To draw a line, create a <xref:System.Windows.Shapes.Line> element.</span></span> <span data-ttu-id="3d877-105">使用其<xref:System.Windows.Shapes.Line.X1%2A>并<xref:System.Windows.Shapes.Line.Y1%2A>属性来设置其开始点; 并使用其<xref:System.Windows.Shapes.Line.X2%2A>和<xref:System.Windows.Shapes.Line.Y2%2A>要设置其终结点的属性。</span><span class="sxs-lookup"><span data-stu-id="3d877-105">Use its <xref:System.Windows.Shapes.Line.X1%2A> and <xref:System.Windows.Shapes.Line.Y1%2A> properties to set its start point; and use its <xref:System.Windows.Shapes.Line.X2%2A> and <xref:System.Windows.Shapes.Line.Y2%2A> properties to set its end point.</span></span> <span data-ttu-id="3d877-106">最后，设置其<xref:System.Windows.Shapes.Shape.Stroke%2A>和<xref:System.Windows.Shapes.Shape.StrokeThickness%2A>因为没有笔画行是不可见。</span><span class="sxs-lookup"><span data-stu-id="3d877-106">Finally, set its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> because a line without a stroke is invisible.</span></span>  
  
 <span data-ttu-id="3d877-107">设置<xref:System.Windows.Shapes.Shape.Fill%2A>行的元素具有不起作用，由于直线没有内部区域。</span><span class="sxs-lookup"><span data-stu-id="3d877-107">Setting the <xref:System.Windows.Shapes.Shape.Fill%2A> element for a line has no effect, because a line has no interior.</span></span>  
  
 <span data-ttu-id="3d877-108">下面的示例绘制内的三个行<xref:System.Windows.Controls.Canvas>元素。</span><span class="sxs-lookup"><span data-stu-id="3d877-108">The following example draws three lines inside a <xref:System.Windows.Controls.Canvas> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d877-109">示例</span><span class="sxs-lookup"><span data-stu-id="3d877-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 <span data-ttu-id="3d877-110">此示例摘自一个更大的示例;有关完整示例，请参阅[形状元素示例](https://go.microsoft.com/fwlink/?LinkID=160037)。</span><span class="sxs-lookup"><span data-stu-id="3d877-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d877-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d877-111">See also</span></span>
- <xref:System.Windows.Shapes.Line>
- [<span data-ttu-id="3d877-112">形状元素示例</span><span class="sxs-lookup"><span data-stu-id="3d877-112">Shape Elements Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160037)
