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
ms.openlocfilehash: 13cf583277b4e105da01c5ab56111123cf03038c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351612"
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a><span data-ttu-id="f06c4-102">如何：沿着路径针对对象进行动画处理（点动画）</span><span class="sxs-lookup"><span data-stu-id="f06c4-102">How to: Animate an Object Along a Path (Point Animation)</span></span>
<span data-ttu-id="f06c4-103">此示例演示如何使用<xref:System.Windows.Media.Animation.PointAnimationUsingPath>对象进行动画处理<xref:System.Windows.Point>沿着曲线路径。</span><span class="sxs-lookup"><span data-stu-id="f06c4-103">This example shows how to use a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> object to animate a <xref:System.Windows.Point> along a curved path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f06c4-104">示例</span><span class="sxs-lookup"><span data-stu-id="f06c4-104">Example</span></span>  
 <span data-ttu-id="f06c4-105">以下示例将移动<xref:System.Windows.Media.EllipseGeometry>沿着由定义路径<xref:System.Windows.Media.PathGeometry>。</span><span class="sxs-lookup"><span data-stu-id="f06c4-105">The following example moves an <xref:System.Windows.Media.EllipseGeometry> along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="f06c4-106">椭圆几何图形<xref:System.Windows.Media.EllipseGeometry.Center%2A>属性，采用<xref:System.Windows.Point>值，指定其位置; 若要移动椭圆几何图形，您进行动画处理其<xref:System.Windows.Media.EllipseGeometry.Center%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="f06c4-106">The ellipse geometry's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property, which takes a <xref:System.Windows.Point> value, specifies its position; to move the ellipse geometry, you animate its <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span> <span data-ttu-id="f06c4-107">该示例使用<xref:System.Windows.Media.Animation.PointAnimationUsingPath>进行动画处理<xref:System.Windows.Media.EllipseGeometry>对象的<xref:System.Windows.Media.EllipseGeometry.Center%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="f06c4-107">The example uses a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> to animate the <xref:System.Windows.Media.EllipseGeometry> object's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 <span data-ttu-id="f06c4-108">有关完整示例，请参阅[路径动画示例](https://go.microsoft.com/fwlink/?LinkID=160028)。</span><span class="sxs-lookup"><span data-stu-id="f06c4-108">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
 <span data-ttu-id="f06c4-109">使用前面示例的代码版本<xref:System.Windows.Media.Animation.Storyboard>进行动画处理<xref:System.Windows.Media.EllipseGeometry>，即使只有一个动画已应用。</span><span class="sxs-lookup"><span data-stu-id="f06c4-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="f06c4-110">一个<xref:System.Windows.Media.Animation.Storyboard>通常是因为这些动画可以控制由同一个应用多个动画的最简单方式<xref:System.Windows.Media.Animation.Storyboard>。</span><span class="sxs-lookup"><span data-stu-id="f06c4-110">A <xref:System.Windows.Media.Animation.Storyboard> is often the easiest way to apply multiple animations because these animations can be controlled by the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="f06c4-111">但是，使用代码时，将一个动画应用到属性的更简单方法是使用<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="f06c4-111">However, an easier way to apply a single animation to a property when using code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="f06c4-112">有关示例，请参阅[在不使用情节提要的情况下对属性进行动画处理](how-to-animate-a-property-without-using-a-storyboard.md)。</span><span class="sxs-lookup"><span data-stu-id="f06c4-112">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f06c4-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="f06c4-113">See also</span></span>
- [<span data-ttu-id="f06c4-114">路径动画示例</span><span class="sxs-lookup"><span data-stu-id="f06c4-114">Path Animation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160028)
- [<span data-ttu-id="f06c4-115">动画概述</span><span class="sxs-lookup"><span data-stu-id="f06c4-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="f06c4-116">路径动画操作说明主题</span><span class="sxs-lookup"><span data-stu-id="f06c4-116">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
