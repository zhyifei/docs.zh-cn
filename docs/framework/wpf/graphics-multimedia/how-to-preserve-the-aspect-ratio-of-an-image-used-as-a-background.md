---
title: 如何：保持背景图像的长宽比
ms.date: 03/30/2017
helpviewer_keywords:
- aspect ratios of background images [WPF], preserving
- brushes [WPF], preserving aspect ratios of background images
- background images [WPF], preserving aspect ratios
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
ms.openlocfilehash: b467fcd353994faef19b5a997e03d6582789eac1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186033"
---
# <a name="how-to-preserve-the-aspect-ratio-of-an-image-used-as-a-background"></a>如何：保持背景图像的长宽比
此示例演示如何使用<xref:System.Windows.Media.TileBrush.Stretch%2A>属性<xref:System.Windows.Media.ImageBrush>来保留图像的纵横比。  
  
 默认情况下，当您使用<xref:System.Windows.Media.ImageBrush>绘制区域时，其内容会拉伸以完全填充输出区域。 当输出区域和图像的纵横比不同时，图像就会因拉伸而失真。  
  
 要<xref:System.Windows.Media.ImageBrush>保留其图像的纵横比，将<xref:System.Windows.Media.TileBrush.Stretch%2A>属性设置为<xref:System.Windows.Media.Stretch.Uniform>或<xref:System.Windows.Media.Stretch.UniformToFill>。  
  
## <a name="example"></a>示例  
 下面的示例使用两<xref:System.Windows.Media.ImageBrush>个对象绘制两个矩形。 每个矩形都为 300x150 像素，每个矩形都包含一个像素为 300x300 的图像。 第<xref:System.Windows.Media.TileBrush.Stretch%2A>一个画笔的属性设置为<xref:System.Windows.Media.Stretch.Uniform>，第二个画笔<xref:System.Windows.Media.TileBrush.Stretch%2A>的属性设置为<xref:System.Windows.Media.Stretch.UniformToFill>。  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 下图显示了第一<xref:System.Windows.Media.TileBrush.Stretch%2A>个画笔的输出，该画笔的设置为<xref:System.Windows.Media.Stretch.Uniform>。  
  
 ![具有 Uniform 拉伸的 ImageBrush](./media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")  
  
 下图显示了第二个<xref:System.Windows.Media.TileBrush.Stretch%2A>画笔的输出，其设置为<xref:System.Windows.Media.Stretch.UniformToFill>。  
  
 ![具有 UniformToFill 拉伸的 ImageBrush](./media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")  
  
 请注意，<xref:System.Windows.Media.TileBrush.Stretch%2A>属性对于其他<xref:System.Windows.Media.TileBrush>对象（即 和 ）<xref:System.Windows.Media.DrawingBrush>的事务相同。 <xref:System.Windows.Media.VisualBrush> 有关<xref:System.Windows.Media.ImageBrush>和其他<xref:System.Windows.Media.TileBrush>对象的详细信息，请参阅[使用图像、绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)。  
  
 另请注意，尽管<xref:System.Windows.Media.TileBrush.Stretch%2A>属性似乎指定<xref:System.Windows.Media.TileBrush>内容如何拉伸以适合其输出区域，但它实际上指定<xref:System.Windows.Media.TileBrush>内容如何拉伸以填充其基本磁贴。 有关详细信息，请参阅 <xref:System.Windows.Media.TileBrush>。  
  
 此代码示例是为类提供的较大示例的<xref:System.Windows.Media.ImageBrush>一部分。 有关完整示例，请参阅[图像画笔示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.TileBrush>
- [使用图像、绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)
