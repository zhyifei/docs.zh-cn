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
# <a name="how-to-improve-rendering-performance-by-caching-an-element"></a><span data-ttu-id="aedfe-102">如何：改善呈现性能，通过缓存元素</span><span class="sxs-lookup"><span data-stu-id="aedfe-102">How to: Improve Rendering Performance by Caching an Element</span></span>
<span data-ttu-id="aedfe-103">使用<xref:System.Windows.Media.BitmapCache>类来改善呈现性能的一种复杂<xref:System.Windows.UIElement>。</span><span class="sxs-lookup"><span data-stu-id="aedfe-103">Use the <xref:System.Windows.Media.BitmapCache> class to improve rendering performance of a complex <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="aedfe-104">若要缓存的元素，创建的新实例<xref:System.Windows.Media.BitmapCache>类，并将其分配给元素的<xref:System.Windows.UIElement.CacheMode%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="aedfe-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span> <span data-ttu-id="aedfe-105">可以重用<xref:System.Windows.Media.BitmapCache>有效地在<xref:System.Windows.Media.BitmapCacheBrush>。</span><span class="sxs-lookup"><span data-stu-id="aedfe-105">You can reuse a <xref:System.Windows.Media.BitmapCache> efficiently in a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aedfe-106">示例</span><span class="sxs-lookup"><span data-stu-id="aedfe-106">Example</span></span>  
 <span data-ttu-id="aedfe-107">下面的代码示例演示如何创建复杂元素并将其缓存为位图，这将提高性能时元素进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="aedfe-107">The following code example shows how to create a complex element and cache it as a bitmap, which improves performance when the element is animated.</span></span> <span data-ttu-id="aedfe-108">该元素是包含带有多个顶点几何形状的画布。</span><span class="sxs-lookup"><span data-stu-id="aedfe-108">The element is a canvas that holds shape geometries with many vertices.</span></span> <span data-ttu-id="aedfe-109">一个<xref:System.Windows.Media.BitmapCache>，默认值的值分配给<xref:System.Windows.UIElement.CacheMode%2A>的画布，并且动画将显示平滑的缓存的位图缩放。</span><span class="sxs-lookup"><span data-stu-id="aedfe-109">A <xref:System.Windows.Media.BitmapCache> with default values is assigned to the <xref:System.Windows.UIElement.CacheMode%2A> of the canvas, and an animation shows the smooth scaling of the cached bitmap.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## <a name="see-also"></a><span data-ttu-id="aedfe-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="aedfe-110">See also</span></span>
- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [<span data-ttu-id="aedfe-111">如何：缓存的元素用作画笔</span><span class="sxs-lookup"><span data-stu-id="aedfe-111">How to: Use a Cached Element as a Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-cached-element-as-a-brush.md)
