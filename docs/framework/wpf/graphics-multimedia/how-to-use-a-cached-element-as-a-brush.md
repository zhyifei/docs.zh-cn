---
title: "如何：使用缓存的元素作为画笔"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BitmapCache [WPF], using
- cached element [WPF], use as a brush
- BitmapCacheBrush [WPF], using
- CacheMode [WPF], using
ms.assetid: d36e944a-866e-4baf-98c4-fd6a75f6fdd0
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f463c15855e267a4c246625a8d06e627852f48a9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-cached-element-as-a-brush"></a><span data-ttu-id="c8d01-102">如何：使用缓存的元素作为画笔</span><span class="sxs-lookup"><span data-stu-id="c8d01-102">How to: Use a Cached Element as a Brush</span></span>
<span data-ttu-id="c8d01-103">使用<xref:System.Windows.Media.BitmapCacheBrush>类，以有效地重用缓存的元素。</span><span class="sxs-lookup"><span data-stu-id="c8d01-103">Use the <xref:System.Windows.Media.BitmapCacheBrush> class to reuse a cached element efficiently.</span></span> <span data-ttu-id="c8d01-104">若要缓存的元素，创建的新实例<xref:System.Windows.Media.BitmapCache>类并将其分配给元素的<xref:System.Windows.UIElement.CacheMode%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="c8d01-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8d01-105">示例</span><span class="sxs-lookup"><span data-stu-id="c8d01-105">Example</span></span>  
 <span data-ttu-id="c8d01-106">下面的代码示例演示如何重用缓存的元素。</span><span class="sxs-lookup"><span data-stu-id="c8d01-106">The following code example shows how to reuse a cached element.</span></span> <span data-ttu-id="c8d01-107">缓存的元素是<xref:System.Windows.Controls.Image>显示较大的图像的控件。</span><span class="sxs-lookup"><span data-stu-id="c8d01-107">The cached element is an <xref:System.Windows.Controls.Image> control that displays a large image.</span></span> <span data-ttu-id="c8d01-108"><xref:System.Windows.Controls.Image>控件使用的缓存以位图格式<xref:System.Windows.Media.BitmapCache>类，且缓存可以通过将其分配给重用<xref:System.Windows.Media.BitmapCacheBrush>。</span><span class="sxs-lookup"><span data-stu-id="c8d01-108">The <xref:System.Windows.Controls.Image> control is cached as a bitmap by using the <xref:System.Windows.Media.BitmapCache> class, and the cache is reused by assigning it to a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span> <span data-ttu-id="c8d01-109">画笔分配给 25 个按钮的背景以显示高效的重用。</span><span class="sxs-lookup"><span data-stu-id="c8d01-109">The brush is assigned to the background of twenty-five buttons to show efficient reuse.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="c8d01-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8d01-110">See Also</span></span>  
 <xref:System.Windows.Media.BitmapCache>  
 <xref:System.Windows.Media.BitmapCacheBrush>  
 <xref:System.Windows.UIElement.CacheMode%2A>  
 [<span data-ttu-id="c8d01-111">如何：通过缓存元素来提升呈现性能</span><span class="sxs-lookup"><span data-stu-id="c8d01-111">How to: Improve Rendering Performance by Caching an Element</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-improve-rendering-performance-by-caching-an-element.md)
