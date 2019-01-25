---
title: 如何：改善呈现性能，通过缓存元素
ms.date: 03/30/2017
helpviewer_keywords:
- rendering performance [WPF], caching an element
- BitmapCache [WPF], improving rendering performance
- CacheMode [WPF], improving rendering performance
- performance [WPF], caching an element
- UIElement [WPF], caching
ms.assetid: 4739c1fc-60ba-4c46-aba6-f6c1a2688f19
ms.openlocfilehash: 79f427198be370d9cb48cab429906202a62bb72d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54647566"
---
# <a name="how-to-improve-rendering-performance-by-caching-an-element"></a>如何：改善呈现性能，通过缓存元素
使用<xref:System.Windows.Media.BitmapCache>类来改善呈现性能的一种复杂<xref:System.Windows.UIElement>。 若要缓存的元素，创建的新实例<xref:System.Windows.Media.BitmapCache>类，并将其分配给元素的<xref:System.Windows.UIElement.CacheMode%2A>属性。 可以重用<xref:System.Windows.Media.BitmapCache>有效地在<xref:System.Windows.Media.BitmapCacheBrush>。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何创建复杂元素并将其缓存为位图，这将提高性能时元素进行动画处理。 该元素是包含带有多个顶点几何形状的画布。 一个<xref:System.Windows.Media.BitmapCache>，默认值的值分配给<xref:System.Windows.UIElement.CacheMode%2A>的画布，并且动画将显示平滑的缓存的位图缩放。  
  
 [!code-xaml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## <a name="see-also"></a>请参阅
- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [如何：缓存的元素用作画笔](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-cached-element-as-a-brush.md)
