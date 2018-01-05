---
title: "缓动函数"
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
- applying mathematical formulas to animations [WPF]
- applying easing functions to animations [WPF]
- mathematical formulas [WPF], applying to animations
- animations [WPF], realistic movement
- easing functions [WPF]
- customizing easing functions [WPF]
- easing functions [WPF], definition
- easing functions [WPF], customizing
- animations [WPF], applying
ms.assetid: 075b9c2b-82c4-43fa-b3cd-de0b6236eb38
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 570a065d3f28befe8db4887ff908c3bd60a639a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="easing-functions"></a><span data-ttu-id="d4b3a-102">缓动函数</span><span class="sxs-lookup"><span data-stu-id="d4b3a-102">Easing Functions</span></span>
<span data-ttu-id="d4b3a-103">缓动函数允许将自定义的数学公式应用到动画。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-103">Easing functions allow you to apply custom mathematical formulas to your animations.</span></span> <span data-ttu-id="d4b3a-104">例如，用户可能希望某个对象逼真地弹跳或表现出像在弹簧上一样。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-104">For example, you may want an object to realistically bounce or behave as though it were on a spring.</span></span> <span data-ttu-id="d4b3a-105">可使用关键帧甚至 From/To/By 动画来近似地实现这些效果，但它将需要大量工作，并且动画不如使用数学公式准确。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-105">You could use Key-Frame or even From/To/By animations to approximate these effects but it would take a significant amount of work and the animation would be less accurate than using a mathematical formula.</span></span>  
  
 <span data-ttu-id="d4b3a-106">除了通过继承创建你自己的自定义缓动函数外<xref:System.Windows.Media.Animation.EasingFunctionBase>，可以使用运行时提供的若干缓动函数之一来创建常见效果。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-106">Besides creating your own custom easing function by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>, you can use one of several easing functions provided by the runtime to create common effects.</span></span>  
  
-   <span data-ttu-id="d4b3a-107"><xref:System.Windows.Media.Animation.BackEase>： 将收回动画的运动略有开始进行动画处理中指定的路径之前。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-107"><xref:System.Windows.Media.Animation.BackEase>: Retracts the motion of an animation slightly before it begins to animate in the path indicated.</span></span>  
  
-   <span data-ttu-id="d4b3a-108"><xref:System.Windows.Media.Animation.BounceEase>： 创建弹跳效果。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-108"><xref:System.Windows.Media.Animation.BounceEase>: Creates a bouncing effect.</span></span>  
  
-   <span data-ttu-id="d4b3a-109"><xref:System.Windows.Media.Animation.CircleEase>： 创建动画加速和/或减速使用圆形函数。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-109"><xref:System.Windows.Media.Animation.CircleEase>: Creates an animation that accelerates and/or decelerates using a circular function.</span></span>  
  
-   <span data-ttu-id="d4b3a-110"><xref:System.Windows.Media.Animation.CubicEase>： 创建动画加速和/或减速使用公式*f*(*t*) = *t*<sup>3</sup>。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-110"><xref:System.Windows.Media.Animation.CubicEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>3</sup>.</span></span>  
  
-   <span data-ttu-id="d4b3a-111"><xref:System.Windows.Media.Animation.ElasticEase>： 创建类似于弹簧 rest 直到显示来回振荡的动画。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-111"><xref:System.Windows.Media.Animation.ElasticEase>: Creates an animation that resembles a spring oscillating back and forth until it comes to rest.</span></span>  
  
-   <span data-ttu-id="d4b3a-112"><xref:System.Windows.Media.Animation.ExponentialEase>： 创建动画加速和/或减速使用指数的公式。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Creates an animation that accelerates and/or decelerates using an exponential formula.</span></span>  
  
-   <span data-ttu-id="d4b3a-113"><xref:System.Windows.Media.Animation.PowerEase>： 创建动画加速和/或减速使用公式*f*(*t*) = *t*<sup>p</sup> p 等于<xref:System.Windows.Media.Animation.PowerEase.Power%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-113"><xref:System.Windows.Media.Animation.PowerEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>p</sup> where p is equal to the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span>  
  
-   <span data-ttu-id="d4b3a-114"><xref:System.Windows.Media.Animation.QuadraticEase>： 创建动画加速和/或减速使用公式*f*(*t*) = *t*<sup>2</sup>。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>2</sup>.</span></span>  
  
-   <span data-ttu-id="d4b3a-115"><xref:System.Windows.Media.Animation.QuarticEase>： 创建动画加速和/或减速使用公式*f*(*t*) = *t*<sup>4</sup>。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-115"><xref:System.Windows.Media.Animation.QuarticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>4</sup>.</span></span>  
  
-   <span data-ttu-id="d4b3a-116"><xref:System.Windows.Media.Animation.QuinticEase>： 创建动画加速和/或减速使用公式*f*(*t*) = *t*<sup>5</sup>。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-116"><xref:System.Windows.Media.Animation.QuinticEase>: Create an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>5</sup>.</span></span>  
  
-   <span data-ttu-id="d4b3a-117"><xref:System.Windows.Media.Animation.SineEase>： 创建动画加速和/或减速使用正弦值的公式。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-117"><xref:System.Windows.Media.Animation.SineEase>: Creates an animation that accelerates and/or decelerates using a sine formula.</span></span>  
  
 <span data-ttu-id="d4b3a-118">可以通过以下示例探索这些缓动函数的行为。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-118">You can explore the behavior of these easing functions with the following sample.</span></span>  
  
 [<span data-ttu-id="d4b3a-119">运行此示例</span><span class="sxs-lookup"><span data-stu-id="d4b3a-119">Run this sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=139798&sref=easing_functions_gallery)  
  
 <span data-ttu-id="d4b3a-120">若要应用到动画的缓动函数，使用`EasingFunction`动画的属性指定要应用到动画的缓动函数。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-120">To apply an easing function to an animation, use the `EasingFunction` property of the animation specify the easing function to apply to the animation.</span></span> <span data-ttu-id="d4b3a-121">下面的示例应用<xref:System.Windows.Media.Animation.BounceEase>缓动函数<xref:System.Windows.Media.Animation.DoubleAnimation>创建弹跳效果。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-121">The following example applies a <xref:System.Windows.Media.Animation.BounceEase> easing function to a <xref:System.Windows.Media.Animation.DoubleAnimation> to create a bouncing effect.</span></span>  
  
 [<span data-ttu-id="d4b3a-122">运行此示例</span><span class="sxs-lookup"><span data-stu-id="d4b3a-122">Run this sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=139798&sref=BounceEase)  
  
 [!code-xaml[BounceEase_snippet#BounceEase](../../../../samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 <span data-ttu-id="d4b3a-123">在上一示例中，缓动函数应用于 From/To/By 动画。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-123">In the previous example, the easing function was applied to a From/To/By animation.</span></span> <span data-ttu-id="d4b3a-124">还可以将这些缓动函数应用到关键帧动画。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-124">You can also apply these easing functions to Key-Frame animations.</span></span> <span data-ttu-id="d4b3a-125">以下示例显示如何将关键帧与其相关联的缓动函数结合使用，以创建一个协定上升、减速、向下展开（如同下落），然后弹跳至停止的矩形的动画。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-125">The following example shows how to use key frames with easing functions associated with them to create an animation of a rectangle that contracts upward, slows down, then expands downward (as though falling) and then bounces to a stop.</span></span>  
  
 [<span data-ttu-id="d4b3a-126">运行此示例</span><span class="sxs-lookup"><span data-stu-id="d4b3a-126">Run this sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=139798&sref=EasingFunctionDoubleKeyFrame)  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](../../../../samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 <span data-ttu-id="d4b3a-127">你可以使用<xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>属性更改的缓动函数的行为方式，即，更改动画的内插。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-127">You can use the <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> property to alter how the easing function behaves, that is, change how the animation interpolates.</span></span> <span data-ttu-id="d4b3a-128">有三个可能的值会使<xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span><span class="sxs-lookup"><span data-stu-id="d4b3a-128">There are three possible values you can give for <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span></span>  
  
-   <span data-ttu-id="d4b3a-129"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>： 内插遵循的缓动函数与关联的数学公式。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-129"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Interpolation follows the mathematical formula associated with the easing function.</span></span>  
  
-   <span data-ttu-id="d4b3a-130"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>： 内插遵循的缓动函数与关联的公式的 100%减去输出的内插。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-130"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Interpolation follows 100% interpolation minus the output of the formula associated with the easing function.</span></span>  
  
-   <span data-ttu-id="d4b3a-131"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>： 内插使用<xref:System.Windows.Media.Animation.EasingMode.EaseIn>动画上半年和<xref:System.Windows.Media.Animation.EasingMode.EaseOut>为第二部分。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-131"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Interpolation uses <xref:System.Windows.Media.Animation.EasingMode.EaseIn> for the first half of the animation and <xref:System.Windows.Media.Animation.EasingMode.EaseOut> for the second half.</span></span>  
  
 <span data-ttu-id="d4b3a-132">下图演示的不同值<xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>其中*f*(*x*) 表示的动画进度和*t*表示时间。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-132">The graphs below demonstrate the different values of <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> where *f*(*x*) represents the animation progress and *t* represents time.</span></span>  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 <span data-ttu-id="d4b3a-133">![BackEase EasingMode 图。](../../../../docs/framework/wpf/graphics-multimedia/media/backease-graph.png "BackEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="d4b3a-133">![BackEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/backease-graph.png "BackEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 <span data-ttu-id="d4b3a-134">![BounceEase EasingMode 图。](../../../../docs/framework/wpf/graphics-multimedia/media/bounceease-graph.png "BounceEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="d4b3a-134">![BounceEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/bounceease-graph.png "BounceEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 <span data-ttu-id="d4b3a-135">![CircleEase EasingMode图。](../../../../docs/framework/wpf/graphics-multimedia/media/circleease-graph.png "CircleEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="d4b3a-135">![CircleEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/circleease-graph.png "CircleEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 <span data-ttu-id="d4b3a-136">![CubicEase EasingMode 图。](../../../../docs/framework/wpf/graphics-multimedia/media/cubicease-graph.png "CubicEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="d4b3a-136">![CubicEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/cubicease-graph.png "CubicEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 <span data-ttu-id="d4b3a-137">![带不同缓动模式图的 ElasticEase。](../../../../docs/framework/wpf/graphics-multimedia/media/elasticease-graph.png "ElasticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="d4b3a-137">![ElasticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/elasticease-graph.png "ElasticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 <span data-ttu-id="d4b3a-138">![不同缓动模式的 ExponentialEase 图。](../../../../docs/framework/wpf/graphics-multimedia/media/exponentialease-graph.png "ExponentialEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="d4b3a-138">![ExponentialEase graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/exponentialease-graph.png "ExponentialEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 <span data-ttu-id="d4b3a-139">![带不同缓动模式图的 QuarticEase。](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="d4b3a-139">![QuarticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 <span data-ttu-id="d4b3a-140">![带不同缓动模式图的 QuadraticEase](../../../../docs/framework/wpf/graphics-multimedia/media/quadraticease-graph.png "QuadraticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="d4b3a-140">![QuadraticEase with graphs of different easingmodes](../../../../docs/framework/wpf/graphics-multimedia/media/quadraticease-graph.png "QuadraticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 <span data-ttu-id="d4b3a-141">![带不同缓动模式图的 QuarticEase。](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="d4b3a-141">![QuarticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 <span data-ttu-id="d4b3a-142">![带不同缓动模式图的 QuinticEase。](../../../../docs/framework/wpf/graphics-multimedia/media/quinticease-graph.png "QuinticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="d4b3a-142">![QuinticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/quinticease-graph.png "QuinticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 <span data-ttu-id="d4b3a-143">![不同 EasingMode 值的 SineEase](../../../../docs/framework/wpf/graphics-multimedia/media/sineease-graph.png "SineEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="d4b3a-143">![SineEase for different EasingMode values](../../../../docs/framework/wpf/graphics-multimedia/media/sineease-graph.png "SineEase_Graph")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4b3a-144">你可以使用<xref:System.Windows.Media.Animation.PowerEase>创建相同的行为<xref:System.Windows.Media.Animation.CubicEase>， <xref:System.Windows.Media.Animation.QuadraticEase>， <xref:System.Windows.Media.Animation.QuarticEase>，和<xref:System.Windows.Media.Animation.QuinticEase>使用<xref:System.Windows.Media.Animation.PowerEase.Power%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-144">You can use <xref:System.Windows.Media.Animation.PowerEase> to create the same behavior as <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, and <xref:System.Windows.Media.Animation.QuinticEase> by using the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span> <span data-ttu-id="d4b3a-145">例如，如果你想要使用<xref:System.Windows.Media.Animation.PowerEase>用于替换<xref:System.Windows.Media.Animation.CubicEase>，指定<xref:System.Windows.Media.Animation.PowerEase.Power%2A>值为 3。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-145">For example, if you want to use <xref:System.Windows.Media.Animation.PowerEase> to substitute for <xref:System.Windows.Media.Animation.CubicEase>, specify a <xref:System.Windows.Media.Animation.PowerEase.Power%2A> value of 3.</span></span>  
  
 <span data-ttu-id="d4b3a-146">除了使用运行时中附带的缓动函数，您可以通过继承创建您自己的自定义缓动函数<xref:System.Windows.Media.Animation.EasingFunctionBase>。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-146">In addition to using the easing functions included in the run-time, you can create your own custom easing functions by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span></span> <span data-ttu-id="d4b3a-147">以下示例演示如何创建简单的自定义缓动函数。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-147">The following example demonstrates how to create a simple custom easing function.</span></span> <span data-ttu-id="d4b3a-148">可以添加您自己的通过重写的缓动函数的行为方式的数学逻辑<xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="d4b3a-148">You can add your own mathematical logic for how the easing function behaves by overriding the <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> method.</span></span>  
  
 [<span data-ttu-id="d4b3a-149">运行此示例</span><span class="sxs-lookup"><span data-stu-id="d4b3a-149">Run this sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=139798&sref=CustomEasingFunction)  
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
