---
title: "如何：使用 ImageDrawing 绘制图像"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawing [WPF], images
- graphics [WPF], drawing images
- images [WPF], drawing
ms.assetid: df28ab41-25fb-4ab3-b51d-7f695b24f55e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d292617ef18bea32396327fd1b0a1d08d35ee16f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-an-image-using-imagedrawing"></a>如何：使用 ImageDrawing 绘制图像
此示例演示如何使用<xref:System.Windows.Media.ImageDrawing>要绘制图像。 <xref:System.Windows.Media.ImageDrawing>允许您显示<xref:System.Windows.Media.ImageSource>与<xref:System.Windows.Media.DrawingBrush>， <xref:System.Windows.Media.DrawingImage>，或<xref:System.Windows.Media.Visual>。 若要绘制图像，则创建<xref:System.Windows.Media.ImageDrawing>并设置其<xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType>和<xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType>属性。 <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType>属性指定要绘制图像，和<xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType>属性指定的位置和每个图像的大小。  
  
## <a name="example"></a>示例  
 下面的示例创建使用四个复合绘图<xref:System.Windows.Media.ImageDrawing>对象。 该示例产生下面的图像：  
  
 ![几个 DrawingImage 对象](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")  
四个 ImageDrawing 对象  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawingExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawingexample)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawingExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawingexample)]  
  
 有关演示一种简单的方法，可显示图像，而无需使用的示例<xref:System.Windows.Media.ImageDrawing>，请参阅[使用图像元素](../../../../docs/framework/wpf/controls/how-to-use-the-image-element.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Freezable.Freeze%2A>  
 <xref:System.Windows.Controls.Image>  
 [Drawing 对象概述](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Freezable 对象概述](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [PresentationOptions:Freeze 特性](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)
