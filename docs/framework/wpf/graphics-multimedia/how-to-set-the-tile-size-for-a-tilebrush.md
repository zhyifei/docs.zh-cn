---
title: "如何：为 TileBrush 设置平铺大小"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TileBrush [WPF], size of tilepropertys
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1e9b746fe66635054dbd35463f727d28a8abd3d0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a>如何：为 TileBrush 设置平铺大小
此示例演示如何设置的磁贴大小<xref:System.Windows.Media.TileBrush>。 默认情况下，<xref:System.Windows.Media.TileBrush>生成单个磁贴可完全填充你正在绘画的区域。 可以通过设置重写此行为<xref:System.Windows.Media.TileBrush.Viewport%2A>和<xref:System.Windows.Media.TileBrush.ViewportUnits%2A>属性。  
  
 <xref:System.Windows.Media.TileBrush.Viewport%2A>属性指定的磁贴大小<xref:System.Windows.Media.TileBrush>。 默认情况下，值<xref:System.Windows.Media.TileBrush.Viewport%2A>属性是相对于当前所绘制的区域大小。 若要使<xref:System.Windows.Media.TileBrush.Viewport%2A>属性指定一个绝对磁贴大小，大小设置<xref:System.Windows.Media.TileBrush.ViewportUnits%2A>属性<xref:System.Windows.Media.BrushMappingMode.Absolute>。  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Windows.Media.ImageBrush>，一种<xref:System.Windows.Media.TileBrush>、 来绘制与磁贴的矩形。 此示例将每个平铺设置为在长宽方向上分别占输出区域（矩形）的 50%。 因此，将用四个投影图像绘制该矩形。  
  
 下图显示该示例生成的输出。
  
 ![使用图像画笔平铺的示例](../../../../docs/framework/wpf/graphics-multimedia/media/0.png "0")  
  
 [!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]  
  
 下一个示例创建<xref:System.Windows.Media.ImageBrush>，设置其<xref:System.Windows.Media.TileBrush.Viewport%2A>到`0,0,25,25`及其<xref:System.Windows.Media.TileBrush.ViewportUnits%2A>到<xref:System.Windows.Media.BrushMappingMode.Absolute>，并使用它来绘制另一个矩形。 因此，画笔会生成一个宽度为 25 像素、高度为 25 像素的平铺。  
  
 下图显示该示例生成的输出。  
  
 ![视区为 0,0,0.25,0.25 的平铺 TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/25x25viewport.png "25x25viewport")  
  
 [!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]  
  
 以上几个示例摘自一个更大的示例。 有关完整的示例，请参阅[ImageBrush 示例](http://go.microsoft.com/fwlink/?LinkID=160005)。  
  
 虽然此示例使用<xref:System.Windows.Media.ImageBrush>类，<xref:System.Windows.Media.TileBrush.Viewport%2A>和<xref:System.Windows.Media.TileBrush.ViewportUnits%2A>属性具有相同行为其他<xref:System.Windows.Media.TileBrush>对象，即为<xref:System.Windows.Media.DrawingBrush>和<xref:System.Windows.Media.VisualBrush>。 有关详细信息<xref:System.Windows.Media.ImageBrush>和其他<xref:System.Windows.Media.TileBrush>对象，请参阅[使用图像、 图形和视觉对象进行绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.TileBrush>  
 [使用图像、绘图和视觉对象进行绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [使用 TileBrush 创建不同的平铺图案](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-different-tile-patterns-with-a-tilebrush.md)
