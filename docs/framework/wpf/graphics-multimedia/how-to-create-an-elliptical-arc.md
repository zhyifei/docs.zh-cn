---
title: "如何：创建椭圆弧"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eeb93cefd2e55e80f27922feab788698653f405e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-an-elliptical-arc"></a>如何：创建椭圆弧
此示例演示如何绘制一条椭圆弧。若要创建一条椭圆弧，使用<xref:System.Windows.Media.PathGeometry>， <xref:System.Windows.Media.PathFigure>，和<xref:System.Windows.Media.ArcSegment>类。  
  
## <a name="example"></a>示例  
 在以下示例中，从 (10100) 到 (200100) 绘制一条椭圆弧。 该弧<xref:System.Windows.Media.ArcSegment.Size%2A>100 通过 50 独立于设备的像素为单位的<xref:System.Windows.Media.ArcSegment.RotationAngle%2A>45 度的<xref:System.Windows.Media.ArcSegment.IsLargeArc%2A>设置`true`，和一个<xref:System.Windows.Media.ArcSegment.SweepDirection%2A>的<xref:System.Windows.Media.SweepDirection.Counterclockwise>。  
  
 [xaml]  
  
 在[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]，你可以使用的特性语法来描述的路径。  
  
 [!code-xaml[GeometrySample#56](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 [xaml]  
  
 (请注意，此特性语法实际创建<xref:System.Windows.Media.StreamGeometry>的轻量版本<xref:System.Windows.Media.PathGeometry>。 有关详细信息，请参阅[路径标记语法](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)页。）  
  
 在[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，您还可以通过显式使用对象标记绘制一条椭圆弧。 下面是等效于上述[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]标记。  
  
 [!code-xaml[GeometrySample#36](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 此示例摘自一个更大的示例。 有关完整的示例，请参阅[几何图形示例](http://go.microsoft.com/fwlink/?LinkID=159989)。  
  
## <a name="see-also"></a>另请参阅  
 [创建二次贝塞尔曲线](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)  
 [创建三次方贝塞尔曲线](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)
