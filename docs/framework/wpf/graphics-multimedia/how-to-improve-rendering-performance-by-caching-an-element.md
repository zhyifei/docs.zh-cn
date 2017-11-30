---
title: "如何：通过缓存元素来改善呈现性能"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- rendering performance [WPF], caching an element
- BitmapCache [WPF], improving rendering performance
- CacheMode [WPF], improving rendering performance
- performance [WPF], caching an element
- UIElement [WPF], caching
ms.assetid: 4739c1fc-60ba-4c46-aba6-f6c1a2688f19
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d754d0ed2f3951c39b3eaeae097589adf3510f5b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-improve-rendering-performance-by-caching-an-element"></a>如何：通过缓存元素来改善呈现性能
使用<xref:System.Windows.Media.BitmapCache>类改进的一种复杂的呈现性能<xref:System.Windows.UIElement>。 若要缓存的元素，创建的新实例<xref:System.Windows.Media.BitmapCache>类并将其分配给元素的<xref:System.Windows.UIElement.CacheMode%2A>属性。 你可以重复使用<xref:System.Windows.Media.BitmapCache>中高效地<xref:System.Windows.Media.BitmapCacheBrush>。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何创建复杂元素并将其缓存为位图，这将提高性能，当元素进行动画处理。 该元素是一个包含带有多个顶点的形状几何图形的画布。 A<xref:System.Windows.Media.BitmapCache>使用默认值分配给<xref:System.Windows.UIElement.CacheMode%2A>的画布上，并且动画将显示缓存的位图的平滑缩放。  
  
 [!code-xaml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Media.BitmapCache>  
 <xref:System.Windows.Media.BitmapCacheBrush>  
 <xref:System.Windows.UIElement.CacheMode%2A>  
 [如何：将缓存的元素用作画笔](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-cached-element-as-a-brush.md)
