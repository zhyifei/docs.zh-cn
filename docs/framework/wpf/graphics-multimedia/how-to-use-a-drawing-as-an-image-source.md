---
title: 如何：将绘图用作图像源
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], drawings [WPF], as image sources
- image sources [WPF], drawings
- drawings [WPF], as image sources
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
ms.openlocfilehash: 01c8cd65128ce4e78dcbf9e38519091767b7ba2f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499270"
---
# <a name="how-to-use-a-drawing-as-an-image-source"></a>如何：将绘图用作图像源
此示例演示如何使用<xref:System.Windows.Media.Drawing>作为<xref:System.Windows.Controls.Image.Source%2A>为<xref:System.Windows.Controls.Image>控件。 若要显示<xref:System.Windows.Media.Drawing>与<xref:System.Windows.Controls.Image>控制，请使用<xref:System.Windows.Media.DrawingImage>作为<xref:System.Windows.Controls.Image>控件的<xref:System.Windows.Controls.Image.Source%2A>并设置<xref:System.Windows.Media.DrawingImage>对象的<xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType>属性设置为你想要显示的绘图。  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Windows.Media.DrawingImage>和一个<xref:System.Windows.Controls.Image>控件来显示<xref:System.Windows.Media.GeometryDrawing>。 该示例产生下面的输出：  
  
 ![两个椭圆的 GeometryDrawing](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
一个 DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## <a name="see-also"></a>请参阅
- <xref:System.Windows.Freezable.Freeze%2A>
- [使用 ImageDrawing 绘制图像](../../../../docs/framework/wpf/graphics-multimedia/how-to-draw-an-image-using-imagedrawing.md)
- [Drawing 对象概述](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
- [Freezable 对象概述](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)
- [PresentationOptions:Freeze 特性](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)
