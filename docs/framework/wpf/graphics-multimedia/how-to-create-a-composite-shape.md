---
title: 如何：创建复合形状
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- shapes [WPF], composite
- composite shapes [WPF]
- graphics [WPF], composite shapes
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
ms.openlocfilehash: c56053f2b07d6055deac5097a68fd7b80ad704ba
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452092"
---
# <a name="how-to-create-a-composite-shape"></a>如何：创建复合形状
此示例演示如何使用 <xref:System.Windows.Media.Geometry> 对象创建复合形状，以及如何使用 <xref:System.Windows.Shapes.Path> 元素来显示它们。 在下面的示例中，将 <xref:System.Windows.Media.LineGeometry>、<xref:System.Windows.Media.EllipseGeometry>和 <xref:System.Windows.Media.RectangleGeometry> 与 <xref:System.Windows.Media.GeometryGroup> 一起用于创建复合形状。 然后使用 <xref:System.Windows.Shapes.Path> 元素绘制几何。  
  
## <a name="example"></a>示例  
 [!code-xaml[GeometrySample#19](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 下图显示在上一个示例中创建的形状。  
  
 ![使用 GeometryGroup 创建的复合几何图形](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")  
复合几何图形  
  
 对于更复杂的形状（例如带有曲线段的多边形和形状），可以使用 <xref:System.Windows.Media.PathGeometry>创建。 有关演示如何使用 <xref:System.Windows.Media.PathGeometry>创建形状的示例，请参阅[使用 System.windows.media.pathgeometry> 创建形状](how-to-create-a-shape-by-using-a-pathgeometry.md)。  虽然此示例使用 <xref:System.Windows.Shapes.Path> 元素将形状呈现到屏幕，但 <xref:System.Windows.Media.Geometry> 对象也可用于描述 <xref:System.Windows.Media.GeometryDrawing> 或 <xref:System.Windows.Media.DrawingContext>的内容。 它们还可用于剪辑和命中测试。  
  
 此示例是更大示例的组成部分；有关完整示例，请参阅[几何图形示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)。
