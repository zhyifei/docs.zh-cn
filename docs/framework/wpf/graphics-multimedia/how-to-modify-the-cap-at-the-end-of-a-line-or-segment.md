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
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a>如何：修改线条或线段末端的线帽
此示例演示如何修改的开头或末尾打开形状<xref:System.Windows.Shapes.Shape>元素。 若要更改已打开开头的 cap <xref:System.Windows.Shapes.Shape>，使用其<xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A>属性。 若要更改已打开末尾 cap <xref:System.Windows.Shapes.Shape>，使用其<xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A>属性。 若要查看可用的线帽，请参阅<xref:System.Windows.Media.PenLineCap>枚举。  
  
> [!NOTE]
>  此属性仅会影响开放式形状，如<xref:System.Windows.Shapes.Line>、 <xref:System.Windows.Shapes.Polyline>，或打开<xref:System.Windows.Shapes.Path>元素。  
  
 下面的示例绘制了四个<xref:System.Windows.Shapes.Polyline>元素并使用上的每个端点的一组不同的形状。  
  
## <a name="example"></a>示例  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 此示例摘自更大的示例;有关完整的示例，请参阅[形状元素示例](http://go.microsoft.com/fwlink/?LinkID=160037)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Media.PenLineCap>
