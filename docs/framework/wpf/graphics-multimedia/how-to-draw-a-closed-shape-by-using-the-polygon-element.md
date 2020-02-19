---
title: 如何：使用多边形元素来绘制闭合形状
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
ms.openlocfilehash: 324a5623ee658789b8600a43a89ce26cab7cd6cd
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452969"
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a>如何：使用多边形元素来绘制闭合形状
此示例演示如何使用 <xref:System.Windows.Shapes.Polygon> 元素绘制闭合形状。 若要绘制闭合形状，请创建 <xref:System.Windows.Shapes.Polygon> 元素，并使用其 <xref:System.Windows.Shapes.Polygon.Points%2A> 属性指定形状的顶点。 将自动绘制一条线，用于连接第一个点和最后一个点。 最后，指定 <xref:System.Windows.Shapes.Shape.Fill%2A>和/或 <xref:System.Windows.Shapes.Shape.Stroke%2A>。  
  
## <a name="example"></a>示例  
 在 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]中，点的有效语法为以空格分隔的、以逗号分隔的 x 和 y 坐标对的列表。  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 尽管该示例使用了一个包含多边形的 <xref:System.Windows.Controls.Canvas>，但您可以使用任何支持非文本内容的 <xref:System.Windows.Controls.Panel> 或 <xref:System.Windows.Controls.Control> 的多边形元素（以及其他所有形状元素）。  
  
 此示例摘自一个更大的示例;有关完整示例，请参阅[形状元素示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)。
