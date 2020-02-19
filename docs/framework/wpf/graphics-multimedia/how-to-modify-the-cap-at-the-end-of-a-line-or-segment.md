---
title: 如何：修改线条或线段末端的线帽
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: 5f755d7b4d1682755ea461121f91c0666d450ad1
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452774"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a>如何：修改线条或线段末端的线帽
此示例演示如何在打开的 <xref:System.Windows.Shapes.Shape> 元素的开头或结尾处修改形状。 若要更改打开 <xref:System.Windows.Shapes.Shape>开头的 cap，请使用其 <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> 属性。 若要更改开放 <xref:System.Windows.Shapes.Shape>末尾的端点，请使用其 <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> 属性。 若要查看可用的行帽，请参阅 <xref:System.Windows.Media.PenLineCap> 枚举。  
  
> [!NOTE]
> 此属性仅影响开放形状，例如 <xref:System.Windows.Shapes.Line>、<xref:System.Windows.Shapes.Polyline>或打开的 <xref:System.Windows.Shapes.Path> 元素。  
  
 下面的示例绘制四个 <xref:System.Windows.Shapes.Polyline> 元素，并在每个元素的两端使用一组不同的形状。  
  
## <a name="example"></a>示例  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 此示例摘自一个更大的示例;有关完整示例，请参阅[形状元素示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
