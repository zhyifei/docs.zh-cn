---
title: 如何：创建 GeometryDrawing
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
ms.openlocfilehash: 713cecd10bfa62494c50c96cb8cbece69f7e5660
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560655"
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
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.DrawingGroup>  
 [Drawing 对象概述](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Geometry 概述](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [创建复合绘图](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-drawing.md)
