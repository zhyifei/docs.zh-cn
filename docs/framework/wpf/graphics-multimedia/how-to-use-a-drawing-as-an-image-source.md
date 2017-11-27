---
title: "如何：将绘图用作图像源"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [WPF], drawings [WPF], as image sources
- image sources [WPF], drawings
- drawings [WPF], as image sources
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0e100bc29afb17a37bc0c66621261347bea6d210
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-drawing-as-an-image-source"></a>如何：将绘图用作图像源
此示例演示如何使用<xref:System.Windows.Media.Drawing>作为<xref:System.Windows.Controls.Image.Source%2A>为<xref:System.Windows.Controls.Image>控件。 若要显示<xref:System.Windows.Media.Drawing>与<xref:System.Windows.Controls.Image>控制，请使用<xref:System.Windows.Media.DrawingImage>作为<xref:System.Windows.Controls.Image>控件的<xref:System.Windows.Controls.Image.Source%2A>并设置<xref:System.Windows.Media.DrawingImage>对象的<xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType>到绘图想要显示的属性。  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Windows.Media.DrawingImage>和<xref:System.Windows.Controls.Image>控件来显示<xref:System.Windows.Media.GeometryDrawing>。 该示例产生下面的输出：  
  
 ![两个椭圆的 GeometryDrawing](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
一个 DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Freezable.Freeze%2A>  
 [使用 ImageDrawing 绘制图像](../../../../docs/framework/wpf/graphics-multimedia/how-to-draw-an-image-using-imagedrawing.md)  
 [Drawing 对象概述](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Freezable 对象概述](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [PresentationOptions:Freeze 特性](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)
