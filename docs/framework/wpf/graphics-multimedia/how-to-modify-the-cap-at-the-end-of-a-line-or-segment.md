---
title: 如何：修改线条或线段末端的线帽
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: e69f461d426fc6a587263cea7a18478da53b5b09
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559832"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a><span data-ttu-id="7d188-102">如何：修改线条或线段末端的线帽</span><span class="sxs-lookup"><span data-stu-id="7d188-102">How to: Modify the Cap at the End of a Line or Segment</span></span>
<span data-ttu-id="7d188-103">此示例演示如何修改的开头或末尾打开形状<xref:System.Windows.Shapes.Shape>元素。</span><span class="sxs-lookup"><span data-stu-id="7d188-103">This example shows how to modify the shape at the start or end of an open <xref:System.Windows.Shapes.Shape> element.</span></span> <span data-ttu-id="7d188-104">若要更改已打开开头的 cap <xref:System.Windows.Shapes.Shape>，使用其<xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="7d188-104">To change the cap at the beginning of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> property.</span></span> <span data-ttu-id="7d188-105">若要更改已打开末尾 cap <xref:System.Windows.Shapes.Shape>，使用其<xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="7d188-105">To change the cap at the end of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> property.</span></span> <span data-ttu-id="7d188-106">若要查看可用的线帽，请参阅<xref:System.Windows.Media.PenLineCap>枚举。</span><span class="sxs-lookup"><span data-stu-id="7d188-106">To view the available line caps, see the <xref:System.Windows.Media.PenLineCap> enumeration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d188-107">此属性仅会影响开放式形状，如<xref:System.Windows.Shapes.Line>、 <xref:System.Windows.Shapes.Polyline>，或打开<xref:System.Windows.Shapes.Path>元素。</span><span class="sxs-lookup"><span data-stu-id="7d188-107">This property only affects an open shape, such as a <xref:System.Windows.Shapes.Line>, a <xref:System.Windows.Shapes.Polyline>, or an open <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 <span data-ttu-id="7d188-108">下面的示例绘制了四个<xref:System.Windows.Shapes.Polyline>元素并使用上的每个端点的一组不同的形状。</span><span class="sxs-lookup"><span data-stu-id="7d188-108">The following example draws four <xref:System.Windows.Shapes.Polyline> elements and uses a different set of shapes on the ends of each.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d188-109">示例</span><span class="sxs-lookup"><span data-stu-id="7d188-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 <span data-ttu-id="7d188-110">此示例摘自更大的示例;有关完整的示例，请参阅[形状元素示例](http://go.microsoft.com/fwlink/?LinkID=160037)。</span><span class="sxs-lookup"><span data-stu-id="7d188-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d188-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="7d188-111">See Also</span></span>  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Media.PenLineCap>
