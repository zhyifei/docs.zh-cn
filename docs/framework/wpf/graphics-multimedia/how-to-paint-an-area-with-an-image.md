---
title: "如何：使用图像绘制区域"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], painting with
- painting [WPF], with images
- brushes [WPF], painting with images
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 90e346990696301d27ea329ea4255258562b353c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-paint-an-area-with-an-image"></a>如何：使用图像绘制区域
此示例演示如何使用<xref:System.Windows.Media.ImageBrush>类来绘制图像的区域。 <xref:System.Windows.Media.ImageBrush>显示一幅图像，通过指定其<xref:System.Windows.Media.ImageBrush.ImageSource%2A>属性。  
  
## <a name="example"></a>示例  
 以下示例绘制<xref:System.Windows.Controls.Control.Background%2A>使用按钮的<xref:System.Windows.Media.ImageBrush>。  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 默认情况下，<xref:System.Windows.Media.ImageBrush>拉伸其图像以完全填充你正在绘画的区域。 在以上示例中，拉伸图像以填充按钮，可能会使图像失真。 你可以通过设置来控制此行为<xref:System.Windows.Media.TileBrush.Stretch%2A>属性<xref:System.Windows.Media.TileBrush>到<xref:System.Windows.Media.Stretch.Uniform>或<xref:System.Windows.Media.Stretch.UniformToFill>，这将导致保留图像的纵横比的画笔。  
  
 如果你设置<xref:System.Windows.Media.TileBrush.Viewport%2A>和<xref:System.Windows.Media.TileBrush.TileMode%2A>属性<xref:System.Windows.Media.ImageBrush>，你可以创建重复的模式。 以下示例通过使用从图像创建的图案来绘制按钮。  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 有关详细信息<xref:System.Windows.Media.ImageBrush>类，请参阅[使用图像、 图形和视觉对象进行绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)。  
  
 此代码示例是一个更大的示例为提供的一部分<xref:System.Windows.Media.ImageBrush>类。 有关完整的示例，请参阅[ImageBrush 示例](http://go.microsoft.com/fwlink/?LinkID=160005)。  
  
## <a name="see-also"></a>请参阅  
 [使用图像、绘图和视觉对象进行绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
