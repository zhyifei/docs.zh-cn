---
title: 如何：使用 PathGeometry 创建形状
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
ms.openlocfilehash: 6c77844b054dd89a0c3f3cbecd0725968df9ae71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a>如何：使用 PathGeometry 创建形状
此示例演示如何创建形状使用<xref:System.Windows.Media.PathGeometry>类。 <xref:System.Windows.Media.PathGeometry> 对象包括一个或多个<xref:System.Windows.Media.PathFigure>对象; 每个<xref:System.Windows.Media.PathFigure>表示不同的"图"或形状。 每个<xref:System.Windows.Media.PathFigure>本身由一个或多个<xref:System.Windows.Media.PathSegment>对象，每个表示连接的部分图或形状。 段类型包括<xref:System.Windows.Media.LineSegment>， <xref:System.Windows.Media.ArcSegment>，和<xref:System.Windows.Media.BezierSegment>。  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Windows.Media.PathGeometry>从而形成一个三角形。 <xref:System.Windows.Media.PathGeometry>使用显示<xref:System.Windows.Shapes.Path>元素。  
  
 [!code-xaml[GeometrySample#49](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 下图显示在上一个示例中创建的形状。  
  
 ![一个 PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")  
使用一个 PathGeometry 创建一个三角形  
  
 前面的示例演示如何创建一个相对简单形状上，一个三角形。 A<xref:System.Windows.Media.PathGeometry>还用于创建更复杂的图形，包括弧线和曲线。 有关示例，请参阅[创建一条椭圆弧](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md)，[创建三次方贝塞尔曲线](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)，和[创建二次贝塞尔曲线](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)。  
  
 此示例是更大示例的组成部分；有关完整示例，请参阅[几何图形示例](http://go.microsoft.com/fwlink/?LinkID=159989)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.GeometryDrawing>  
 [Geometry 概述](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [几何图形示例](http://go.microsoft.com/fwlink/?LinkID=159989)
