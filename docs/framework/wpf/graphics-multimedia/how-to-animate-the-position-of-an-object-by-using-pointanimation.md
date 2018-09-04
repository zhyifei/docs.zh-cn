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
ms.openlocfilehash: 91447685988d91dfe86707c2cf265deabeb717b9
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43561038"
---
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a><span data-ttu-id="7aecb-102">如何：使用 PointAnimation 针对对象的位置进行动画处理</span><span class="sxs-lookup"><span data-stu-id="7aecb-102">How to: Animate the Position of an Object by Using PointAnimation</span></span>
<span data-ttu-id="7aecb-103">此示例演示如何使用<xref:System.Windows.Media.Animation.PointAnimation>类进行动画处理的对象沿<xref:System.Windows.Shapes.Path>。</span><span class="sxs-lookup"><span data-stu-id="7aecb-103">This example shows how to use the <xref:System.Windows.Media.Animation.PointAnimation> class to animate an object along a <xref:System.Windows.Shapes.Path>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7aecb-104">示例</span><span class="sxs-lookup"><span data-stu-id="7aecb-104">Example</span></span>  
 <span data-ttu-id="7aecb-105">以下示例将一个椭圆<xref:System.Windows.Shapes.Path>从一个点到另一个屏幕上。</span><span class="sxs-lookup"><span data-stu-id="7aecb-105">The following example moves an ellipse along a <xref:System.Windows.Shapes.Path> from one point on the screen to another.</span></span> <span data-ttu-id="7aecb-106">该示例进行动画处理的位置<xref:System.Windows.Media.EllipseGeometry>通过使用<xref:System.Windows.Media.Animation.PointAnimation>进行动画处理<xref:System.Windows.Media.EllipseGeometry.Center%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="7aecb-106">The example animates the position of an <xref:System.Windows.Media.EllipseGeometry> by using <xref:System.Windows.Media.Animation.PointAnimation> to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="7aecb-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="7aecb-107">See Also</span></span>  
 <xref:System.Windows.Media.Animation.PointAnimation>  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.EllipseGeometry>  
 <xref:System.Windows.Media.EllipseGeometry.Center%2A>  
 [<span data-ttu-id="7aecb-108">动画概述</span><span class="sxs-lookup"><span data-stu-id="7aecb-108">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="7aecb-109">图形和多媒体</span><span class="sxs-lookup"><span data-stu-id="7aecb-109">Graphics and Multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)  
 [<span data-ttu-id="7aecb-110">帮助主题</span><span class="sxs-lookup"><span data-stu-id="7aecb-110">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/graphics-how-to-topics.md)  
 [<span data-ttu-id="7aecb-111">动画和计时</span><span class="sxs-lookup"><span data-stu-id="7aecb-111">Animation and Timing</span></span>](https://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="7aecb-112">帮助主题</span><span class="sxs-lookup"><span data-stu-id="7aecb-112">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
