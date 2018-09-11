---
title: 如何：沿着路径针对对象进行动画处理（点动画）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
ms.openlocfilehash: d6dc79cd7a15aef2a4168fffb293c5e1f33cde08
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44259777"
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a><span data-ttu-id="72f27-102">如何：沿着路径针对对象进行动画处理（点动画）</span><span class="sxs-lookup"><span data-stu-id="72f27-102">How to: Animate an Object Along a Path (Point Animation)</span></span>
<span data-ttu-id="72f27-103">此示例演示如何使用<xref:System.Windows.Media.Animation.PointAnimationUsingPath>对象进行动画处理<xref:System.Windows.Point>沿着曲线路径。</span><span class="sxs-lookup"><span data-stu-id="72f27-103">This example shows how to use a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> object to animate a <xref:System.Windows.Point> along a curved path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72f27-104">示例</span><span class="sxs-lookup"><span data-stu-id="72f27-104">Example</span></span>  
 <span data-ttu-id="72f27-105">以下示例将移动<xref:System.Windows.Media.EllipseGeometry>沿着由定义路径<xref:System.Windows.Media.PathGeometry>。</span><span class="sxs-lookup"><span data-stu-id="72f27-105">The following example moves an <xref:System.Windows.Media.EllipseGeometry> along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="72f27-106">椭圆几何图形<xref:System.Windows.Media.EllipseGeometry.Center%2A>属性，采用<xref:System.Windows.Point>值，指定其位置; 若要移动椭圆几何图形，您进行动画处理其<xref:System.Windows.Media.EllipseGeometry.Center%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="72f27-106">The ellipse geometry's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property, which takes a <xref:System.Windows.Point> value, specifies its position; to move the ellipse geometry, you animate its <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span> <span data-ttu-id="72f27-107">该示例使用<xref:System.Windows.Media.Animation.PointAnimationUsingPath>进行动画处理<xref:System.Windows.Media.EllipseGeometry>对象的<xref:System.Windows.Media.EllipseGeometry.Center%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="72f27-107">The example uses a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> to animate the <xref:System.Windows.Media.EllipseGeometry> object's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 <span data-ttu-id="72f27-108">有关完整示例，请参阅[路径动画示例](https://go.microsoft.com/fwlink/?LinkID=160028)。</span><span class="sxs-lookup"><span data-stu-id="72f27-108">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
 <span data-ttu-id="72f27-109">使用前面示例的代码版本<xref:System.Windows.Media.Animation.Storyboard>进行动画处理<xref:System.Windows.Media.EllipseGeometry>，即使只有一个动画已应用。</span><span class="sxs-lookup"><span data-stu-id="72f27-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="72f27-110">一个<xref:System.Windows.Media.Animation.Storyboard>通常是因为这些动画可以控制由同一个应用多个动画的最简单方式<xref:System.Windows.Media.Animation.Storyboard>。</span><span class="sxs-lookup"><span data-stu-id="72f27-110">A <xref:System.Windows.Media.Animation.Storyboard> is often the easiest way to apply multiple animations because these animations can be controlled by the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="72f27-111">但是，使用代码时，将一个动画应用到属性的更简单方法是使用<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="72f27-111">However, an easier way to apply a single animation to a property when using code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="72f27-112">有关示例，请参阅[在不使用情节提要的情况下对属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)。</span><span class="sxs-lookup"><span data-stu-id="72f27-112">For an example, see [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72f27-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="72f27-113">See Also</span></span>  
 [<span data-ttu-id="72f27-114">路径动画示例</span><span class="sxs-lookup"><span data-stu-id="72f27-114">Path Animation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160028)  
 [<span data-ttu-id="72f27-115">动画概述</span><span class="sxs-lookup"><span data-stu-id="72f27-115">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="72f27-116">路径动画操作说明主题</span><span class="sxs-lookup"><span data-stu-id="72f27-116">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
