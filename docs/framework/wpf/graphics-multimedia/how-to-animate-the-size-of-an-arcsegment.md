---
title: 如何：对 ArcSegment 的大小进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], animation
- animation [WPF], ArcSegment size
- ArcSegment [WPF], animating size
ms.assetid: f93a1065-b00a-4d7e-9d4b-37023f98186a
ms.openlocfilehash: d1b9db72c9d1ea47f3c1bc6476a3b579bc03eae2
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452865"
---
# <a name="how-to-animate-the-size-of-an-arcsegment"></a><span data-ttu-id="f9342-102">如何：对 ArcSegment 的大小进行动画处理</span><span class="sxs-lookup"><span data-stu-id="f9342-102">How to: Animate the Size of an ArcSegment</span></span>
<span data-ttu-id="f9342-103">此示例演示如何对 <xref:System.Windows.Media.ArcSegment>的 <xref:System.Windows.Media.ArcSegment.Size%2A> 属性进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="f9342-103">This example shows how to animate the <xref:System.Windows.Media.ArcSegment.Size%2A> property of an <xref:System.Windows.Media.ArcSegment>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9342-104">示例</span><span class="sxs-lookup"><span data-stu-id="f9342-104">Example</span></span>  
 <span data-ttu-id="f9342-105">下面的示例创建一个在屏幕上加载时对其 <xref:System.Windows.Media.ArcSegment.Size%2A> 进行动画处理的 <xref:System.Windows.Media.ArcSegment>。</span><span class="sxs-lookup"><span data-stu-id="f9342-105">The following example creates an <xref:System.Windows.Media.ArcSegment> that animates its <xref:System.Windows.Media.ArcSegment.Size%2A> when it loads on the screen.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#SizeAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/SizeAnimationExample.cs#sizeanimationwholepage)]
 [!code-vb[BasicAnimations_snip#SizeAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/SizeAnimationExample.vb#sizeanimationwholepage)]  
  
 <span data-ttu-id="f9342-106">有关其他几何和动画示例，请参阅[几何图形示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)。</span><span class="sxs-lookup"><span data-stu-id="f9342-106">For additional geometry and animation samples, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9342-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9342-107">See also</span></span>

- <xref:System.Windows.Media.ArcSegment.Size%2A>
- <xref:System.Windows.Media.ArcSegment>
- [<span data-ttu-id="f9342-108">动画概述</span><span class="sxs-lookup"><span data-stu-id="f9342-108">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="f9342-109">几何图形概述</span><span class="sxs-lookup"><span data-stu-id="f9342-109">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="f9342-110">几何图形操作指南主题</span><span class="sxs-lookup"><span data-stu-id="f9342-110">Geometries How-to Topics</span></span>](geometries-how-to-topics.md)
- [<span data-ttu-id="f9342-111">动画和计时操作指南主题</span><span class="sxs-lookup"><span data-stu-id="f9342-111">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
