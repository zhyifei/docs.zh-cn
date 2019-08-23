---
title: 如何：修改直线或线段末端的线帽
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: 53487417636dae8d855fe70b7b9255351a2dfb1e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916139"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a>如何：修改直线或线段末端的线帽
此示例演示如何修改 open <xref:System.Windows.Shapes.Shape>元素开头或结尾处的形状。 若要更改打开<xref:System.Windows.Shapes.Shape>的开头的端点, 请使用其<xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A>属性。 若要更改打开<xref:System.Windows.Shapes.Shape>的末尾的端点, 请使用其<xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A>属性。 若要查看可用的行帽, 请<xref:System.Windows.Media.PenLineCap>参阅枚举。  
  
> [!NOTE]
> 此属性仅影响开放形状, 如<xref:System.Windows.Shapes.Line> <xref:System.Windows.Shapes.Polyline>、或打开<xref:System.Windows.Shapes.Path>的元素。  
  
 下面的示例绘制四<xref:System.Windows.Shapes.Polyline>个元素, 并在每个元素的两端使用一组不同的形状。  
  
## <a name="example"></a>示例  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 此示例摘自一个更大的示例;有关完整示例, 请参阅[形状元素示例](https://go.microsoft.com/fwlink/?LinkID=160037)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
