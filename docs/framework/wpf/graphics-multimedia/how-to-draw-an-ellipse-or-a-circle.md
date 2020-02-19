---
title: 如何：绘制椭圆或圆
ms.date: 03/30/2017
helpviewer_keywords:
- ellipses [WPF], drawing
- circles [WPF], drawing
- drawing circles [WPF]
- drawing ellipses [WPF]
- graphics [WPF], drawing circles
- graphics [WPF], drawing ellipses
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
ms.openlocfilehash: 5f17615da4907cba6e25b68f2f934602c2f8a390
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452917"
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a>如何：绘制椭圆或圆
此示例演示如何使用 <xref:System.Windows.Shapes.Ellipse> 元素来绘制椭圆和圆圈。 若要绘制一个椭圆，请创建一个 <xref:System.Windows.Shapes.Ellipse> 元素，并指定其 <xref:System.Windows.FrameworkElement.Width%2A> 和 <xref:System.Windows.FrameworkElement.Height%2A>。 使用其 <xref:System.Windows.Shapes.Shape.Fill%2A> 属性指定用来绘制椭圆内部的 <xref:System.Windows.Media.Brush>。 使用其 <xref:System.Windows.Shapes.Shape.Stroke%2A> 属性指定用来绘制椭圆轮廓的 <xref:System.Windows.Media.Brush>。 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 属性指定椭圆轮廓的粗细。  
  
 若要绘制一个圆，请使 <xref:System.Windows.Shapes.Ellipse> 元素的 <xref:System.Windows.FrameworkElement.Width%2A> 和 <xref:System.Windows.FrameworkElement.Height%2A> 彼此相等。  
  
 下面的示例在一个 <xref:System.Windows.Controls.Canvas>中绘制四个 <xref:System.Windows.Shapes.Ellipse> 元素。  
  
## <a name="example"></a>示例  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 虽然此示例使用 <xref:System.Windows.Controls.Canvas> 来包含省略号，但你可以将椭圆形元素（和所有其他形状元素）与支持非文本内容的任何 <xref:System.Windows.Controls.Panel> 或 <xref:System.Windows.Controls.Control> 一起使用。  
  
 此示例摘自一个更大的示例;有关完整示例，请参阅[形状元素示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Shapes.Ellipse>
- <xref:System.Windows.Shapes.Shape>
- [形状元素示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
