---
title: 如何：保持背景图像的长宽比
ms.date: 03/30/2017
helpviewer_keywords:
- aspect ratios of background images [WPF], preserving
- brushes [WPF], preserving aspect ratios of background images
- background images [WPF], preserving aspect ratios
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
ms.openlocfilehash: 8cf0a3804172b90af33318299d60aa6c7eaa53f0
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863081"
---
# <a name="how-to-preserve-the-aspect-ratio-of-an-image-used-as-a-background"></a>如何：保持背景图像的长宽比
此示例演示如何使用<xref:System.Windows.Media.TileBrush.Stretch%2A>属性的<xref:System.Windows.Media.ImageBrush>为了保持图像的纵横比。  
  
 默认情况下，当您使用<xref:System.Windows.Media.ImageBrush>绘制区域，其内容将进行拉伸以完全填充输出区域。 当输出区域和图像的纵横比不同时，图像就会因拉伸而失真。  
  
 若要使<xref:System.Windows.Media.ImageBrush>保持其图像的纵横比，设置<xref:System.Windows.Media.TileBrush.Stretch%2A>属性设置为<xref:System.Windows.Media.Stretch.Uniform>或<xref:System.Windows.Media.Stretch.UniformToFill>。  
  
## <a name="example"></a>示例  
 下面的示例使用两个<xref:System.Windows.Media.ImageBrush>对象来绘制两个矩形。 每个矩形都为 300x150 像素，每个矩形都包含一个像素为 300x300 的图像。 <xref:System.Windows.Media.TileBrush.Stretch%2A>的第一个画笔属性设置为<xref:System.Windows.Media.Stretch.Uniform>，并<xref:System.Windows.Media.TileBrush.Stretch%2A>第二个画笔的属性设置为<xref:System.Windows.Media.Stretch.UniformToFill>。  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 下图显示了具有第一个画笔的输出<xref:System.Windows.Media.TileBrush.Stretch%2A>设置的<xref:System.Windows.Media.Stretch.Uniform>。  
  
 ![ImageBrush with Uniform stretching](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")  
  
 下图显示具有第二个画笔的输出<xref:System.Windows.Media.TileBrush.Stretch%2A>设置的<xref:System.Windows.Media.Stretch.UniformToFill>。  
  
 ![具有 UniformToFill 拉伸的 ImageBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")  
  
 请注意，<xref:System.Windows.Media.TileBrush.Stretch%2A>属性适用于其他的行为相同<xref:System.Windows.Media.TileBrush>对象，也就是说，对于<xref:System.Windows.Media.DrawingBrush>和<xref:System.Windows.Media.VisualBrush>。 有关详细信息<xref:System.Windows.Media.ImageBrush>和其他<xref:System.Windows.Media.TileBrush>对象，请参阅[使用图像、 绘图和视觉对象进行绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)。  
  
 另请注意，尽管<xref:System.Windows.Media.TileBrush.Stretch%2A>属性将显示以指定如何<xref:System.Windows.Media.TileBrush>内容将进行拉伸以适合其输出区域，实际上指定了<xref:System.Windows.Media.TileBrush>内容拉伸以填充其基本磁贴。 有关详细信息，请参阅<xref:System.Windows.Media.TileBrush>。  
  
 此代码示例是为提供一个更大示例的一部分<xref:System.Windows.Media.ImageBrush>类。 有关完整示例，请参阅[ImageBrush 示例](https://go.microsoft.com/fwlink/?LinkID=160005)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.TileBrush>  
 [使用图像、绘图和视觉对象进行绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
