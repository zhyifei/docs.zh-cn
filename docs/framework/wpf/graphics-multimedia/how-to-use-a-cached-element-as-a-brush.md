---
title: 如何：缓存的元素用作画笔
ms.date: 03/30/2017
helpviewer_keywords:
- BitmapCache [WPF], using
- cached element [WPF], use as a brush
- BitmapCacheBrush [WPF], using
- CacheMode [WPF], using
ms.assetid: d36e944a-866e-4baf-98c4-fd6a75f6fdd0
ms.openlocfilehash: 008bec87390a807ae2b4797af8b86aaf59c92ef5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372485"
---
# <a name="how-to-use-a-cached-element-as-a-brush"></a><span data-ttu-id="9725c-102">如何：缓存的元素用作画笔</span><span class="sxs-lookup"><span data-stu-id="9725c-102">How to: Use a Cached Element as a Brush</span></span>
<span data-ttu-id="9725c-103">使用<xref:System.Windows.Media.BitmapCacheBrush>类，以有效地重复使用缓存的元素。</span><span class="sxs-lookup"><span data-stu-id="9725c-103">Use the <xref:System.Windows.Media.BitmapCacheBrush> class to reuse a cached element efficiently.</span></span> <span data-ttu-id="9725c-104">若要缓存的元素，创建的新实例<xref:System.Windows.Media.BitmapCache>类，并将其分配给元素的<xref:System.Windows.UIElement.CacheMode%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="9725c-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9725c-105">示例</span><span class="sxs-lookup"><span data-stu-id="9725c-105">Example</span></span>  
 <span data-ttu-id="9725c-106">下面的代码示例显示如何重复使用缓存的元素。</span><span class="sxs-lookup"><span data-stu-id="9725c-106">The following code example shows how to reuse a cached element.</span></span> <span data-ttu-id="9725c-107">缓存的元素是<xref:System.Windows.Controls.Image>控件，用于显示大图像。</span><span class="sxs-lookup"><span data-stu-id="9725c-107">The cached element is an <xref:System.Windows.Controls.Image> control that displays a large image.</span></span> <span data-ttu-id="9725c-108"><xref:System.Windows.Controls.Image>控件通过使用缓存作为位图<xref:System.Windows.Media.BitmapCache>类，并在缓存重新分配到使用<xref:System.Windows.Media.BitmapCacheBrush>。</span><span class="sxs-lookup"><span data-stu-id="9725c-108">The <xref:System.Windows.Controls.Image> control is cached as a bitmap by using the <xref:System.Windows.Media.BitmapCache> class, and the cache is reused by assigning it to a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span> <span data-ttu-id="9725c-109">画笔分配到 25 个按钮的背景以显示有效重用。</span><span class="sxs-lookup"><span data-stu-id="9725c-109">The brush is assigned to the background of twenty-five buttons to show efficient reuse.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="9725c-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="9725c-110">See also</span></span>
- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [<span data-ttu-id="9725c-111">如何：改善呈现性能，通过缓存元素</span><span class="sxs-lookup"><span data-stu-id="9725c-111">How to: Improve Rendering Performance by Caching an Element</span></span>](how-to-improve-rendering-performance-by-caching-an-element.md)
