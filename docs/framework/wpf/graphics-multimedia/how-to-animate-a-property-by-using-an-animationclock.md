---
title: "如何：使用 AnimationClock 对属性进行动画处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], properties [WPF], with AnimationClocks
- AnimationClocks [WPF]
ms.assetid: e6542021-714c-4675-9567-04f1c7380834
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 47df7aaad45000bc8c761a9bb9022d37e0f0828c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-property-by-using-an-animationclock"></a><span data-ttu-id="0b5ec-102">如何：使用 AnimationClock 对属性进行动画处理</span><span class="sxs-lookup"><span data-stu-id="0b5ec-102">How to: Animate a Property by Using an AnimationClock</span></span>
<span data-ttu-id="0b5ec-103">此示例演示如何使用<xref:System.Windows.Media.Animation.Clock>对象属性进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="0b5ec-103">This example shows how to use <xref:System.Windows.Media.Animation.Clock> objects to animate a property.</span></span>  
  
 <span data-ttu-id="0b5ec-104">对依赖属性进行动画处理有三种方法：</span><span class="sxs-lookup"><span data-stu-id="0b5ec-104">There are three ways to animate a dependency property:</span></span>  
  
-   <span data-ttu-id="0b5ec-105">创建<xref:System.Windows.Media.Animation.AnimationTimeline>并将其与该属性使用<xref:System.Windows.Media.Animation.Storyboard>。</span><span class="sxs-lookup"><span data-stu-id="0b5ec-105">Create an <xref:System.Windows.Media.Animation.AnimationTimeline> and associate it with that property by using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
-   <span data-ttu-id="0b5ec-106">使用对象的<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>方法以应用单个<xref:System.Windows.Media.Animation.AnimationTimeline>到目标属性。</span><span class="sxs-lookup"><span data-stu-id="0b5ec-106">Use the object's <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method to apply a single <xref:System.Windows.Media.Animation.AnimationTimeline> to a target property.</span></span>  
  
-   <span data-ttu-id="0b5ec-107">创建<xref:System.Windows.Media.Animation.AnimationClock>从<xref:System.Windows.Media.Animation.AnimationTimeline>并将其应用到属性。</span><span class="sxs-lookup"><span data-stu-id="0b5ec-107">Create an <xref:System.Windows.Media.Animation.AnimationClock> from an <xref:System.Windows.Media.Animation.AnimationTimeline> and apply it to a property.</span></span>  
  
 <span data-ttu-id="0b5ec-108"><xref:System.Windows.Media.Animation.Storyboard>对象和<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>方法使您能够对属性进行动画处理不直接创建和分发时钟 (有关示例，请参阅[使用情节提要属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)和[属性不进行动画处理使用情节提要](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md));创建和自动为你分发时钟。</span><span class="sxs-lookup"><span data-stu-id="0b5ec-108"><xref:System.Windows.Media.Animation.Storyboard> objects and the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method enable you to animate properties without directly creating and distributing clocks (for examples, see [Animate a Property by Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) and [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)); clocks are created and distributed for you automatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b5ec-109">示例</span><span class="sxs-lookup"><span data-stu-id="0b5ec-109">Example</span></span>  
 <span data-ttu-id="0b5ec-110">下面的示例演示如何创建<xref:System.Windows.Media.Animation.AnimationClock>并将其应用到两个类似的属性。</span><span class="sxs-lookup"><span data-stu-id="0b5ec-110">The following example shows how to create an <xref:System.Windows.Media.Animation.AnimationClock> and apply it to two similar properties.</span></span>  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 <span data-ttu-id="0b5ec-111">有关演示如何以交互方式控制的示例<xref:System.Windows.Media.Animation.Clock>启动后，请参阅[以交互方式控制时钟](../../../../docs/framework/wpf/graphics-multimedia/how-to-interactively-control-a-clock.md)。</span><span class="sxs-lookup"><span data-stu-id="0b5ec-111">For an example showing how to interactively control a <xref:System.Windows.Media.Animation.Clock> after it starts, see [Interactively Control a Clock](../../../../docs/framework/wpf/graphics-multimedia/how-to-interactively-control-a-clock.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b5ec-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b5ec-112">See Also</span></span>  
 [<span data-ttu-id="0b5ec-113">使用情节提要对属性进行动画处理</span><span class="sxs-lookup"><span data-stu-id="0b5ec-113">Animate a Property by Using a Storyboard</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)  
 [<span data-ttu-id="0b5ec-114">在不使用情节提要的情况下为属性设置动画效果</span><span class="sxs-lookup"><span data-stu-id="0b5ec-114">Animate a Property Without Using a Storyboard</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)  
 [<span data-ttu-id="0b5ec-115">属性动画技术概述</span><span class="sxs-lookup"><span data-stu-id="0b5ec-115">Property Animation Techniques Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
