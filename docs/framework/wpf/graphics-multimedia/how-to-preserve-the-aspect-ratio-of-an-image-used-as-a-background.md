---
title: "如何：保持背景图像的长宽比"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- aspect ratios of background images [WPF], preserving
- brushes [WPF], preserving aspect ratios of background images
- background images [WPF], preserving aspect ratios
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a34377403a55ba42d9d3f2946ef26ea48982f5d9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-preserve-the-aspect-ratio-of-an-image-used-as-a-background"></a>如何：保持背景图像的长宽比
此示例演示如何使用<xref:System.Windows.Media.TileBrush.Stretch%2A>属性<xref:System.Windows.Media.ImageBrush>以保持图像的纵横比。  
  
 默认情况下，当你使用<xref:System.Windows.Media.ImageBrush>来绘制的区域，其内容将进行拉伸以完全填充输出区域。 当输出区域和图像的纵横比不同时，图像就会因拉伸而失真。  
  
 若要使<xref:System.Windows.Media.ImageBrush>保留其图像的纵横比，设置<xref:System.Windows.Media.TileBrush.Stretch%2A>属性<xref:System.Windows.Media.Stretch.Uniform>或<xref:System.Windows.Media.Stretch.UniformToFill>。  
  
## <a name="example"></a>示例  
 下面的示例使用两个<xref:System.Windows.Media.ImageBrush>对象来绘制两个矩形。 每个矩形都为 300x150 像素，每个矩形都包含一个像素为 300x300 的图像。 <xref:System.Windows.Media.TileBrush.Stretch%2A>的第一个画笔属性设置为<xref:System.Windows.Media.Stretch.Uniform>，和<xref:System.Windows.Media.TileBrush.Stretch%2A>的第二个画笔属性设置为<xref:System.Windows.Media.Stretch.UniformToFill>。  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 下图显示的第一个画笔，它具有输出<xref:System.Windows.Media.TileBrush.Stretch%2A>设置<xref:System.Windows.Media.Stretch.Uniform>。  
  
 ![ImageBrush with Uniform stretching](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")  
  
 下图显示的第二个画笔，它具有输出<xref:System.Windows.Media.TileBrush.Stretch%2A>设置<xref:System.Windows.Media.Stretch.UniformToFill>。  
  
 ![具有 UniformToFill 拉伸的 ImageBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")  
  
 请注意，<xref:System.Windows.Media.TileBrush.Stretch%2A>属性行为相同，其他<xref:System.Windows.Media.TileBrush>对象，即为<xref:System.Windows.Media.DrawingBrush>和<xref:System.Windows.Media.VisualBrush>。 有关详细信息<xref:System.Windows.Media.ImageBrush>和其他<xref:System.Windows.Media.TileBrush>对象，请参阅[使用图像、 图形和视觉对象进行绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)。  
  
 另请注意，尽管<xref:System.Windows.Media.TileBrush.Stretch%2A>属性看起来指定如何<xref:System.Windows.Media.TileBrush>内容将进行拉伸以适应其输出区域，实际上指定如何<xref:System.Windows.Media.TileBrush>内容拉伸以填充其基本磁贴。 有关更多信息，请参见<xref:System.Windows.Media.TileBrush>。  
  
 此代码示例是一个更大的示例为提供的一部分<xref:System.Windows.Media.ImageBrush>类。 有关完整的示例，请参阅[ImageBrush 示例](http://go.microsoft.com/fwlink/?LinkID=160005)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Media.TileBrush>  
 [使用图像、绘图和视觉对象进行绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
