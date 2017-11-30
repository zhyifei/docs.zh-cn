---
title: "如何：创建 GeometryDrawing"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7f0fa86a9786e5440db9fec0cee76c5ed28363b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-geometrydrawing"></a>如何：创建 GeometryDrawing
此示例演示如何创建和显示<xref:System.Windows.Media.GeometryDrawing>。 A<xref:System.Windows.Media.GeometryDrawing>使您能够创建具有填充和边框的形状，通过将相关联<xref:System.Windows.Media.Pen>和<xref:System.Windows.Media.Brush>与<xref:System.Windows.Media.Geometry>。 <xref:System.Windows.Media.GeometryDrawing.Geometry%2A>描述形状的结构<xref:System.Windows.Media.GeometryDrawing.Brush%2A>描述形状的填充和<xref:System.Windows.Media.GeometryDrawing.Pen%2A>描述形状的轮廓。  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Windows.Media.GeometryDrawing>来呈现形状。 描述形状<xref:System.Windows.Media.GeometryGroup>和两个<xref:System.Windows.Media.EllipseGeometry>对象。 形状内部上色与<xref:System.Windows.Media.LinearGradientBrush>和以绘制其轮廓<xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>。 <xref:System.Windows.Media.GeometryDrawing>使用显示<xref:System.Windows.Media.ImageDrawing>和<xref:System.Windows.Controls.Image>元素。  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 下图显示得到的<xref:System.Windows.Media.GeometryDrawing>。  
  
 ![两个椭圆的 GeometryDrawing](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
  
 若要创建更复杂的绘图，你可以将多个图形对象组合到单个复合绘制使用<xref:System.Windows.Media.DrawingGroup>。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Media.DrawingGroup>  
 [Drawing 对象概述](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Geometry 概述](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [创建复合绘图](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-drawing.md)
