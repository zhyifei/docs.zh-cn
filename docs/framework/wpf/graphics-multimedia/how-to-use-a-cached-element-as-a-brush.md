---
title: 如何：使用缓存的元素作为画笔
ms.date: 03/30/2017
helpviewer_keywords:
- BitmapCache [WPF], using
- cached element [WPF], use as a brush
- BitmapCacheBrush [WPF], using
- CacheMode [WPF], using
ms.assetid: d36e944a-866e-4baf-98c4-fd6a75f6fdd0
ms.openlocfilehash: c43c4ecbefe99d6e38766705378d85d92ecc5729
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-a-cached-element-as-a-brush"></a>如何：使用缓存的元素作为画笔
使用<xref:System.Windows.Media.BitmapCacheBrush>类，以有效地重用缓存的元素。 若要缓存的元素，创建的新实例<xref:System.Windows.Media.BitmapCache>类并将其分配给元素的<xref:System.Windows.UIElement.CacheMode%2A>属性。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何重用缓存的元素。 缓存的元素是<xref:System.Windows.Controls.Image>显示较大的图像的控件。 <xref:System.Windows.Controls.Image>控件使用的缓存以位图格式<xref:System.Windows.Media.BitmapCache>类，且缓存可以通过将其分配给重用<xref:System.Windows.Media.BitmapCacheBrush>。 画笔分配给 25 个按钮的背景以显示高效的重用。  
  
 [!code-xaml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.BitmapCache>  
 <xref:System.Windows.Media.BitmapCacheBrush>  
 <xref:System.Windows.UIElement.CacheMode%2A>  
 [如何：通过缓存元素来提升呈现性能](../../../../docs/framework/wpf/graphics-multimedia/how-to-improve-rendering-performance-by-caching-an-element.md)
