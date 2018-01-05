---
title: "如何：使用 From、To 和 By 控制动画"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], From/to/by
- basic animation [WPF]
- animation [WPF], basic animation
- From/to/by animation
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 17f87c8bcf09022aa389df779e29f5e5affabc20
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-control-an-animation-using-from-to-and-by"></a><span data-ttu-id="84cf7-102">如何：使用 From、To 和 By 控制动画</span><span class="sxs-lookup"><span data-stu-id="84cf7-102">How to: Control an Animation using From, To, and By</span></span>
<span data-ttu-id="84cf7-103">"从/到/者"或"基本动画"创建两个目标值之间的转换 (请参阅[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)有关不同类型的动画的简介)。</span><span class="sxs-lookup"><span data-stu-id="84cf7-103">A "From/To/By" or "basic animation" creates a transition between two target values (see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) for an introduction to different types of animations).</span></span> <span data-ttu-id="84cf7-104">若要设置的基本动画的目标值，使用其<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>， <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>，和<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="84cf7-104">To set the target values of a basic animation, use its <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> properties.</span></span>  <span data-ttu-id="84cf7-105">下表总结了如何<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>， <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>，和<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>属性可能一起使用或单独来确定动画的目标值。</span><span class="sxs-lookup"><span data-stu-id="84cf7-105">The following table summarizes how the <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> properties may be used together or separately to determine an animation's target values.</span></span>  
  
|<span data-ttu-id="84cf7-106">指定的属性</span><span class="sxs-lookup"><span data-stu-id="84cf7-106">Properties specified</span></span>|<span data-ttu-id="84cf7-107">产生的行为</span><span class="sxs-lookup"><span data-stu-id="84cf7-107">Resulting behavior</span></span>|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|<span data-ttu-id="84cf7-108">从指定的值的动画<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>属性设为正在进行动画处理的属性的基值或前一动画的输出值，具体取决于如何配置前一动画。</span><span class="sxs-lookup"><span data-stu-id="84cf7-108">The animation progresses from the value specified by the <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> property to the base value of the property being animated or to a previous animation's output value, depending on how the previous animation is configured.</span></span>|  
|<span data-ttu-id="84cf7-109"><xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 和 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A></span><span class="sxs-lookup"><span data-stu-id="84cf7-109"><xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A></span></span>|<span data-ttu-id="84cf7-110">从指定的值的动画<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>属性设置为指定的值<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="84cf7-110">The animation progresses from the value specified by the <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> property to the value specified by the <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> property.</span></span>|  
|<span data-ttu-id="84cf7-111"><xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 和 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A></span><span class="sxs-lookup"><span data-stu-id="84cf7-111"><xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A></span></span>|<span data-ttu-id="84cf7-112">从指定的值的动画<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>的总和来指定的值的属性<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>和<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="84cf7-112">The animation progresses from the value specified by the <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> property to the value specified by the sum of the <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> properties.</span></span>|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|<span data-ttu-id="84cf7-113">动画转换从动画的属性的基值或前一动画的输出值与指定的值<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="84cf7-113">The animation progresses from the animated property's base value or a previous animation's output value to the value specified by the <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> property.</span></span>|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|<span data-ttu-id="84cf7-114">动画从正在进行动画处理的属性的基值或前一动画的输出值，该值与指定的值的要求和<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="84cf7-114">The animation progresses from the base value of the property being animated or a previous animation's output value to the sum of that value and the value specified by the <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> property.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="84cf7-115">请勿同时设置<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>属性和<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>上相同的动画的属性。</span><span class="sxs-lookup"><span data-stu-id="84cf7-115">Do not set both the <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> property and the <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> property on the same animation.</span></span>  
  
 <span data-ttu-id="84cf7-116">若要在两个以上的目标值之间使用内插方法或进行动画处理，请使用关键帧动画。</span><span class="sxs-lookup"><span data-stu-id="84cf7-116">To use other interpolation methods or animate between more than two target values, use a key frame animation.</span></span> <span data-ttu-id="84cf7-117">请参阅[关键帧动画概述](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="84cf7-117">See [Key-Frame Animations Overview](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md) for more information.</span></span>  
  
 <span data-ttu-id="84cf7-118">有关将多个动画应用到单个属性的信息，请参阅[关键帧动画概述](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="84cf7-118">For information about applying multiple animations to a single property, see [Key-Frame Animations Overview](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="84cf7-119">下面的示例演示的设置不同的效果<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>， <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>，和<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>动画的属性。</span><span class="sxs-lookup"><span data-stu-id="84cf7-119">The example below shows the different effects of setting <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>, and <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> properties on animations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84cf7-120">示例</span><span class="sxs-lookup"><span data-stu-id="84cf7-120">Example</span></span>  
 [!code-xaml[BasicAnimations_snippet#AnimationTargetValuesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="84cf7-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="84cf7-121">See Also</span></span>  
 [<span data-ttu-id="84cf7-122">动画概述</span><span class="sxs-lookup"><span data-stu-id="84cf7-122">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="84cf7-123">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="84cf7-123">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="84cf7-124">From、To 和 By 动画目标值示例</span><span class="sxs-lookup"><span data-stu-id="84cf7-124">From, To, and By Animation Target Values Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159988)
