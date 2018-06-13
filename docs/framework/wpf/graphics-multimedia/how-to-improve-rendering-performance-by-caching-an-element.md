---
title: 如何：通过缓存元素来改善呈现性能
ms.date: 03/30/2017
helpviewer_keywords:
- rendering performance [WPF], caching an element
- BitmapCache [WPF], improving rendering performance
- CacheMode [WPF], improving rendering performance
- performance [WPF], caching an element
- UIElement [WPF], caching
ms.assetid: 4739c1fc-60ba-4c46-aba6-f6c1a2688f19
ms.openlocfilehash: a92909c623db0c10e3434677b4275fa82b787fa7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559293"
---
# <a name="how-to-improve-rendering-performance-by-caching-an-element"></a><span data-ttu-id="4716e-102">如何：通过缓存元素来改善呈现性能</span><span class="sxs-lookup"><span data-stu-id="4716e-102">How to: Improve Rendering Performance by Caching an Element</span></span>
<span data-ttu-id="4716e-103">使用<xref:System.Windows.Media.BitmapCache>类改进的一种复杂的呈现性能<xref:System.Windows.UIElement>。</span><span class="sxs-lookup"><span data-stu-id="4716e-103">Use the <xref:System.Windows.Media.BitmapCache> class to improve rendering performance of a complex <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="4716e-104">若要缓存的元素，创建的新实例<xref:System.Windows.Media.BitmapCache>类并将其分配给元素的<xref:System.Windows.UIElement.CacheMode%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="4716e-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span> <span data-ttu-id="4716e-105">你可以重复使用<xref:System.Windows.Media.BitmapCache>中高效地<xref:System.Windows.Media.BitmapCacheBrush>。</span><span class="sxs-lookup"><span data-stu-id="4716e-105">You can reuse a <xref:System.Windows.Media.BitmapCache> efficiently in a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4716e-106">示例</span><span class="sxs-lookup"><span data-stu-id="4716e-106">Example</span></span>  
 <span data-ttu-id="4716e-107">下面的代码示例演示如何创建复杂元素并将其缓存为位图，这将提高性能，当元素进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="4716e-107">The following code example shows how to create a complex element and cache it as a bitmap, which improves performance when the element is animated.</span></span> <span data-ttu-id="4716e-108">该元素是一个包含带有多个顶点的形状几何图形的画布。</span><span class="sxs-lookup"><span data-stu-id="4716e-108">The element is a canvas that holds shape geometries with many vertices.</span></span> <span data-ttu-id="4716e-109">A<xref:System.Windows.Media.BitmapCache>使用默认值分配给<xref:System.Windows.UIElement.CacheMode%2A>的画布上，并且动画将显示缓存的位图的平滑缩放。</span><span class="sxs-lookup"><span data-stu-id="4716e-109">A <xref:System.Windows.Media.BitmapCache> with default values is assigned to the <xref:System.Windows.UIElement.CacheMode%2A> of the canvas, and an animation shows the smooth scaling of the cached bitmap.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## <a name="see-also"></a><span data-ttu-id="4716e-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="4716e-110">See Also</span></span>  
 <xref:System.Windows.Media.BitmapCache>  
 <xref:System.Windows.Media.BitmapCacheBrush>  
 <xref:System.Windows.UIElement.CacheMode%2A>  
 [<span data-ttu-id="4716e-111">如何：将缓存的元素用作画笔</span><span class="sxs-lookup"><span data-stu-id="4716e-111">How to: Use a Cached Element as a Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-cached-element-as-a-brush.md)
