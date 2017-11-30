---
title: "如何：圆化 RectangleGeometry 的角"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- corners [WPF], rounding
- RectangleGeometry class [WPF], rounding corners
- graphics [WPF], rounding corners of RectangleGeometry objects [WPF]
- rounding corners of RectangleGeometry objects [WPF]
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4cd857f7ce886095bcbe92ae57c350ce83bb5c7d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-round-the-corners-of-a-rectanglegeometry"></a>如何：圆化 RectangleGeometry 的角
改为圆角的<xref:System.Windows.Media.RectangleGeometry>，将其<xref:System.Windows.Media.RectangleGeometry.RadiusX%2A>和<xref:System.Windows.Media.RectangleGeometry.RadiusY%2A>属性设置为大于零的值。 值越大，1 之间的矩形的角。  
  
## <a name="example"></a>示例  
 下面的示例显示了几个<xref:System.Windows.Media.RectangleGeometry>具有不同的对象<xref:System.Windows.Media.RectangleGeometry.RadiusX%2A>和<xref:System.Windows.Media.RectangleGeometry.RadiusY%2A>设置。 <xref:System.Windows.Media.RectangleGeometry>对象将显示使用<xref:System.Windows.Shapes.Path>元素。  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 ![使用不同的 RadiusX &#47; 的矩形RadiusY 设置](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rounded.png "graphicsmm_rounded")  
圆角矩形  
  
## <a name="see-also"></a>另请参阅  
 [Geometry 概述](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [创建复合形状](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [使用 PathGeometry 创建形状](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
