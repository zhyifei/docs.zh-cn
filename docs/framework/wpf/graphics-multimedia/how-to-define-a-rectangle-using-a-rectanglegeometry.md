---
title: "如何：使用 RectangleGeometry 定义矩形"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rectangles
- rectangles [WPF], creating with RectangleGeometry class
ms.assetid: e40b8a8e-54b8-416b-a9f2-be6dca9fdf0b
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 678d6f36c02c63825782b9f1c860285450a6a9f3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-a-rectangle-using-a-rectanglegeometry"></a>如何：使用 RectangleGeometry 定义矩形
本示例介绍了如何使用<xref:System.Windows.Media.RectangleGeometry>类描述一个矩形。  
  
## <a name="example"></a>示例  
 下面的示例演示如何创建和呈现<xref:System.Windows.Media.RectangleGeometry>。  由定义的相对位置和矩形的尺寸<xref:System.Windows.Rect>结构。 相对位置是`50,50`和高度和宽度都`25`创建一个正方形。 与绘制矩形的内部<xref:System.Windows.Media.Brushes.LemonChiffon%2A>画笔，它的轮廓绘制与<xref:System.Windows.Media.Brushes.Black%2A>描边的粗细设为与`1`。  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 ![一个 RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "graphicsmm_rectangle")  
RectangleGeometry  
  
 尽管此示例使用<xref:System.Windows.Shapes.Path>元素来呈现<xref:System.Windows.Media.RectangleGeometry>，有多种其他的方法，以使用<xref:System.Windows.Media.RectangleGeometry>对象。 例如，<xref:System.Windows.Media.RectangleGeometry>可以用于指定<xref:System.Windows.UIElement.Clip%2A>的<xref:System.Windows.UIElement>或<xref:System.Windows.Media.GeometryDrawing.Geometry%2A>的<xref:System.Windows.Media.GeometryDrawing>。  
  
 简单的几何图形的其他类包括<xref:System.Windows.Media.LineGeometry>和<xref:System.Windows.Media.EllipseGeometry>。 这些几何图形，以及更复杂的也可以创建使用<xref:System.Windows.Media.PathGeometry>或<xref:System.Windows.Media.StreamGeometry>。  
  
## <a name="see-also"></a>另请参阅  
 [Geometry 概述](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [创建复合形状](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [使用 PathGeometry 创建形状](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
