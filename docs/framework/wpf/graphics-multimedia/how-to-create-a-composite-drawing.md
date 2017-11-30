---
title: "如何：创建复合绘图"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawings [WPF], composite
- composite drawings [WPF]
- graphics [WPF], composite drawings
ms.assetid: 066eb0ab-5f0e-439d-85c6-dca60af269fc
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7789f9aa94db32d3dc61ccf01ef9ddfe1e777a37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-composite-drawing"></a>如何：创建复合绘图
此示例演示如何使用<xref:System.Windows.Media.DrawingGroup>来通过组合多个创建复杂图形<xref:System.Windows.Media.Drawing>到单个复合绘图的对象。  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Windows.Media.DrawingGroup>若要创建一个复合从图形<xref:System.Windows.Media.GeometryDrawing>和<xref:System.Windows.Media.ImageDrawing>对象。 下图显示了此示例生成的输出。  
  
 ![具有多个绘图的 DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.jpg "graphicsmm_simple")  
通过 DrawingGroup 创建复合绘图  
  
 请注意显示绘制的边界的灰色边框。  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 你可以使用<xref:System.Windows.Media.DrawingGroup>应用<xref:System.Windows.Media.DrawingGroup.Transform%2A>，<xref:System.Windows.Media.DrawingGroup.Opacity%2A>设置， <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>， <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>， <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>，或<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>到它所包含的绘图。 因为<xref:System.Windows.Media.DrawingGroup>也<xref:System.Windows.Media.Drawing>，它可以包含其他<xref:System.Windows.Media.DrawingGroup>对象。  
  
 下面的示例是类似于前面的示例中，只不过它使用其他<xref:System.Windows.Media.DrawingGroup>要应用于某些图形的位图效果并不透明蒙版的对象。 下图显示了此示例生成的输出。  
  
 ![具有多个绘图的 DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-multiple.jpg "graphicsmm_multiple")  
复合绘制都具有多个 DrawingGroup 对象  
  
 请注意显示绘制的边界的灰色边框。  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmmultipledrawinggroupsexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmmultipledrawinggroupsexample)]  
  
 有关详细信息<xref:System.Windows.Media.Drawing>对象，请参阅[绘制对象概述](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>  
 <xref:System.Windows.Media.DrawingGroup.Transform%2A>  
 <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>  
 <xref:System.Windows.Media.DrawingGroup.Opacity%2A>  
 <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>  
 <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>  
 [Drawing 对象概述](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
