---
title: 如何：使用 Polyline 元素绘制折线
ms.date: 03/30/2017
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
ms.openlocfilehash: fb5220082989a9d0a22c4998bb79c0a196067e7e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934962"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a>如何：使用 Polyline 元素绘制折线
此示例演示如何使用<xref:System.Windows.Shapes.Polyline>元素绘制折线, 这是一系列连接的直线。  
  
 若要绘制折线, 请创建<xref:System.Windows.Shapes.Polyline>一个元素, 并<xref:System.Windows.Shapes.Polyline.Points%2A>使用其属性指定形状顶点。 最后, 使用<xref:System.Windows.Shapes.Shape.Stroke%2A>和<xref:System.Windows.Shapes.Shape.StrokeThickness%2A>属性来描述折线轮廓, 因为没有描边的线条是不可见的。  
  
> [!NOTE]
> 由于该<xref:System.Windows.Shapes.Polyline>元素不是闭合的形状, 因此<xref:System.Windows.Shapes.Shape.Fill%2A>即使您特意关闭了形状轮廓, 此属性也不起作用。 若要使用创建闭合形状<xref:System.Windows.Shapes.Shape.Fill%2A>, 请<xref:System.Windows.Shapes.Polygon>使用元素。  
  
 下面的示例在<xref:System.Windows.Shapes.Polyline> <xref:System.Windows.Controls.Canvas>内绘制两个元素。  
  
## <a name="example"></a>示例  
 在[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]中, 点的有效语法是以空格分隔的、以逗号分隔的 x 和 y 坐标对的列表。  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 虽然此示例使用<xref:System.Windows.Controls.Canvas>来包含折线, 但你可以将折线元素 (及所有其他形状元素) 与支持非文本内容的任何<xref:System.Windows.Controls.Panel>或<xref:System.Windows.Controls.Control>一起使用。  
  
 此示例摘自一个更大的示例;有关完整示例, 请参阅[形状元素示例](https://go.microsoft.com/fwlink/?LinkID=160037)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [形状元素示例](https://go.microsoft.com/fwlink/?LinkID=160037)
- [WPF 中的形状和基本绘图概述](shapes-and-basic-drawing-in-wpf-overview.md)
