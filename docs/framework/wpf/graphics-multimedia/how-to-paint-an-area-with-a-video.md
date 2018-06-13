---
title: 如何：使用视频绘制区域
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- painting with a video [WPF]
- video [WPF], painting with
- brushes [WPF], painting with a video
ms.assetid: 04dd6600-4a6e-4b43-a93e-21cce7dfbcb8
ms.openlocfilehash: d2ca0f8b70abf6e895ea275d2a47eb4a6dd4bfe4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560772"
---
# <a name="how-to-paint-an-area-with-a-video"></a>如何：使用视频绘制区域
此示例演示如何使用媒体绘制区域。 绘制带有媒体的区域的一种方法是使用<xref:System.Windows.Controls.MediaElement>连同<xref:System.Windows.Media.VisualBrush>。 使用<xref:System.Windows.Controls.MediaElement>加载和播放媒体，并使用它来设置<xref:System.Windows.Media.VisualBrush.Visual%2A>属性<xref:System.Windows.Media.VisualBrush>。 然后，可以使用<xref:System.Windows.Media.VisualBrush>来绘制带有加载媒体的区域。  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Windows.Controls.MediaElement>和<xref:System.Windows.Media.VisualBrush>来绘制<xref:System.Windows.Controls.TextBlock.Foreground%2A>的<xref:System.Windows.Controls.TextBlock>视频的控件。 此示例将设置<xref:System.Windows.Controls.MediaElement.IsMuted%2A>属性<xref:System.Windows.Controls.MediaElement>到`true`，以便它不发出声音。  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundinline)]  
  
## <a name="example"></a>示例  
 因为<xref:System.Windows.Media.VisualBrush>继承自<xref:System.Windows.Media.TileBrush>类，它提供了几个平铺模式。 通过设置<xref:System.Windows.Media.TileBrush.TileMode%2A>属性<xref:System.Windows.Media.VisualBrush>到<xref:System.Windows.Media.TileMode.Tile>并设置其<xref:System.Windows.Media.TileBrush.Viewport%2A>属性的值小于你正在绘画的区域，你可以创建平铺的模式。  
  
 下面的示例与前面的示例，只不过等同<xref:System.Windows.Media.VisualBrush>从该视频生成模式。  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundtiledinline)]  
  
 有关如何将内容文件，如媒体文件添加到你的应用程序，请参阅[WPF 应用程序资源、 内容和数据文件](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)。 当你添加的媒体文件时，你必须将其添加为内容文件，而不是资源文件。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.VisualBrush>  
 [使用图像、绘图和视觉对象进行绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [TileBrush 概述](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md)  
 [多媒体概述](../../../../docs/framework/wpf/graphics-multimedia/multimedia-overview.md)
