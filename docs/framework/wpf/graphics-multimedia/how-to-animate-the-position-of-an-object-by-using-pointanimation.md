---
title: 如何：使用 PointAnimation 针对对象的位置进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], animation
- animation [WPF], PointAnimation
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
ms.openlocfilehash: 04dbcfdb64525e6231ecf33c8ac5ecf2a2d2cb7e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357920"
---
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a><span data-ttu-id="77e75-102">如何：使用 PointAnimation 针对对象的位置进行动画处理</span><span class="sxs-lookup"><span data-stu-id="77e75-102">How to: Animate the Position of an Object by Using PointAnimation</span></span>
<span data-ttu-id="77e75-103">此示例演示如何使用<xref:System.Windows.Media.Animation.PointAnimation>类进行动画处理的对象沿<xref:System.Windows.Shapes.Path>。</span><span class="sxs-lookup"><span data-stu-id="77e75-103">This example shows how to use the <xref:System.Windows.Media.Animation.PointAnimation> class to animate an object along a <xref:System.Windows.Shapes.Path>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77e75-104">示例</span><span class="sxs-lookup"><span data-stu-id="77e75-104">Example</span></span>  
 <span data-ttu-id="77e75-105">以下示例将一个椭圆<xref:System.Windows.Shapes.Path>从一个点到另一个屏幕上。</span><span class="sxs-lookup"><span data-stu-id="77e75-105">The following example moves an ellipse along a <xref:System.Windows.Shapes.Path> from one point on the screen to another.</span></span> <span data-ttu-id="77e75-106">该示例进行动画处理的位置<xref:System.Windows.Media.EllipseGeometry>通过使用<xref:System.Windows.Media.Animation.PointAnimation>进行动画处理<xref:System.Windows.Media.EllipseGeometry.Center%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="77e75-106">The example animates the position of an <xref:System.Windows.Media.EllipseGeometry> by using <xref:System.Windows.Media.Animation.PointAnimation> to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="77e75-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="77e75-107">See also</span></span>
- <xref:System.Windows.Media.Animation.PointAnimation>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.EllipseGeometry>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A>
- [<span data-ttu-id="77e75-108">动画概述</span><span class="sxs-lookup"><span data-stu-id="77e75-108">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="77e75-109">图形和多媒体</span><span class="sxs-lookup"><span data-stu-id="77e75-109">Graphics and Multimedia</span></span>](index.md)
- [<span data-ttu-id="77e75-110">图形操作指南主题</span><span class="sxs-lookup"><span data-stu-id="77e75-110">Graphics How-to Topics</span></span>](graphics-how-to-topics.md)
- [<span data-ttu-id="77e75-111">动画和计时操作指南主题</span><span class="sxs-lookup"><span data-stu-id="77e75-111">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
