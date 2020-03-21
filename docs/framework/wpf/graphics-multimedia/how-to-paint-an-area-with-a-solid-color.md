---
title: 如何：使用纯色绘制区域
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: be28a0af04c4e43cdf745a5429468aee99e34c40
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2020
ms.locfileid: "78849517"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a>如何：使用纯色绘制区域
要使用<xref:System.Windows.Media.Brushes.Red%2A>纯色绘制区域，可以使用预定义的系统画笔（如 或<xref:System.Windows.Media.Brushes.Blue%2A>，）或者可以使用 Alpha、红色、绿色和<xref:System.Windows.Media.SolidColorBrush>蓝色值创建新<xref:System.Windows.Media.SolidColorBrush.Color%2A>区域并描述其区域。 在 XAML 中，还可以使用十六进制表示法来利用纯色绘制区域。  
  
 以下示例使用以下每种技术来绘制<xref:System.Windows.Shapes.Rectangle>蓝色。  
  
## <a name="example"></a>示例  
 **使用预定义画笔**  
  
 在下面的示例中，使用预定义的画笔<xref:System.Windows.Media.Brushes.Blue%2A>绘制一个矩形蓝色。  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 **使用十六进制表示法**  
  
 下一个示例使用 8 位十六进制表示法绘制一个蓝色矩形。  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 **使用 ARGB 值**  
  
 下一个示例创建<xref:System.Windows.Media.SolidColorBrush>和<xref:System.Windows.Media.SolidColorBrush.Color%2A>描述其使用颜色为蓝色的 ARGB 值。  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 有关描述颜色的其他方法，<xref:System.Windows.Media.Color>请参阅结构。  
  
 **相关主题**  
  
 有关相关信息<xref:System.Windows.Media.SolidColorBrush>和其他示例，请参阅["具有纯色和渐变的绘画概述](painting-with-solid-colors-and-gradients-overview.md)"。  
  
 此代码示例是为类提供的更大示例的<xref:System.Windows.Media.SolidColorBrush>一部分。 有关完整示例，请参阅[画笔示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Brushes>
