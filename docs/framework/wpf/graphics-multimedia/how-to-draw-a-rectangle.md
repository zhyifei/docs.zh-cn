---
title: 如何：绘制矩形
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
ms.openlocfilehash: 100f1a8062628e892e9a71b988bb2a8754ea6bad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561041"
---
# <a name="how-to-draw-a-rectangle"></a>如何：绘制矩形
此示例演示如何使用绘制矩形<xref:System.Windows.Shapes.Rectangle>元素。  
  
 若要绘制一个矩形，创建<xref:System.Windows.Shapes.Rectangle>元素并指定其<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>。 若要绘制的矩形的内部，将设置其<xref:System.Windows.Shapes.Shape.Fill%2A>。 若要为矩形提供概述，请使用其<xref:System.Windows.Shapes.Shape.Stroke%2A>和<xref:System.Windows.Shapes.Shape.StrokeThickness%2A>属性。  
  
 若要绘制矩形圆角中，指定可选<xref:System.Windows.Shapes.Rectangle.RadiusX%2A>和<xref:System.Windows.Shapes.Rectangle.RadiusY%2A>属性。 <xref:System.Windows.Shapes.Rectangle.RadiusX%2A>和<xref:System.Windows.Shapes.Rectangle.RadiusY%2A>属性设置用于圆角化矩形角的椭圆的 x 轴和 y 轴半径。  
  
 在下面的示例中，两个<xref:System.Windows.Shapes.Rectangle>中绘制元素<xref:System.Windows.Controls.Canvas>。 第一个矩形<xref:System.Windows.Media.Brushes.Blue%2A>内部。 第二个矩形具有<xref:System.Windows.Media.Brushes.Blue%2A>内部，<xref:System.Windows.Media.Brushes.Black%2A>大纲，和圆的角。  
  
## <a name="example"></a>示例  
 [!code-xaml[drawingwithshapeelements#Rectangle1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 虽然此示例使用<xref:System.Windows.Controls.Canvas>来包含矩形，但是您可以使用矩形元素 （以及所有其他形状元素） 以及任何<xref:System.Windows.Controls.Panel>或<xref:System.Windows.Controls.Control>支持非文本内容。 事实上，矩形的用处尤其显著提供的某些部分的背景<xref:System.Windows.Controls.Grid>面板。 有关示例，请参阅[表概述](../../../../docs/framework/wpf/advanced/table-overview.md)。  
  
 此示例摘自更大的示例;有关完整的示例，请参阅[形状元素示例](http://go.microsoft.com/fwlink/?LinkID=160037)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Shapes.Rectangle>  
 [形状元素示例](http://go.microsoft.com/fwlink/?LinkID=160037)  
 [WPF 中的形状和基本绘图概述](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [表概述](../../../../docs/framework/wpf/advanced/table-overview.md)
