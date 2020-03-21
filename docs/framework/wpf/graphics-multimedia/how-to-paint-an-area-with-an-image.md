---
title: 如何：使用图像绘制区域
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], painting with
- painting [WPF], with images
- brushes [WPF], painting with images
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
ms.openlocfilehash: 92969778c04c6ac634a2964c402d6c3439b96b49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186057"
---
# <a name="how-to-paint-an-area-with-an-image"></a>如何：使用图像绘制区域
此示例演示如何使用 类<xref:System.Windows.Media.ImageBrush>使用图像绘制区域。 显示<xref:System.Windows.Media.ImageBrush>由其<xref:System.Windows.Media.ImageBrush.ImageSource%2A>属性指定的单个图像。  
  
## <a name="example"></a>示例  
 下面的示例<xref:System.Windows.Controls.Control.Background%2A>使用 绘制按钮的 。 <xref:System.Windows.Media.ImageBrush>  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 默认情况下，拉伸<xref:System.Windows.Media.ImageBrush>其图像以完全填充要绘制的区域。 在以上示例中，拉伸图像以填充按钮，可能会使图像失真。 可以通过<xref:System.Windows.Media.TileBrush.Stretch%2A>设置<xref:System.Windows.Media.TileBrush>的 属性 来<xref:System.Windows.Media.Stretch.Uniform>控制此行为<xref:System.Windows.Media.Stretch.UniformToFill>，这将导致画笔保留图像的纵横比。  
  
 如果设置 的<xref:System.Windows.Media.TileBrush.Viewport%2A><xref:System.Windows.Media.TileBrush.TileMode%2A>和 属性<xref:System.Windows.Media.ImageBrush>，则可以创建重复模式。 以下示例通过使用从图像创建的图案来绘制按钮。  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 有关该类的详细信息，<xref:System.Windows.Media.ImageBrush>请参阅[使用图像、绘图和视觉对象进行绘画](painting-with-images-drawings-and-visuals.md)。  
  
 此代码示例是为类提供的较大示例的<xref:System.Windows.Media.ImageBrush>一部分。 有关完整示例，请参阅[图像画笔示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)。  
  
## <a name="see-also"></a>另请参阅

- [使用图像、绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)
