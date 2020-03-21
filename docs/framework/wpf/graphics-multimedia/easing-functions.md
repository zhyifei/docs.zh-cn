---
title: 缓动函数
ms.date: 03/30/2017
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
ms.openlocfilehash: a25bde5098af853c3906a174a189fc35f33f0525
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186503"
---
# <a name="easing-functions"></a><span data-ttu-id="3c514-102">缓动函数</span><span class="sxs-lookup"><span data-stu-id="3c514-102">Easing Functions</span></span>
<span data-ttu-id="3c514-103">缓动函数允许将自定义的数学公式应用到动画。</span><span class="sxs-lookup"><span data-stu-id="3c514-103">Easing functions allow you to apply custom mathematical formulas to your animations.</span></span> <span data-ttu-id="3c514-104">例如，用户可能希望某个对象逼真地弹跳或表现出像在弹簧上一样。</span><span class="sxs-lookup"><span data-stu-id="3c514-104">For example, you may want an object to realistically bounce or behave as though it were on a spring.</span></span> <span data-ttu-id="3c514-105">可使用关键帧甚至 From/To/By 动画来近似地实现这些效果，但它将需要大量工作，并且动画不如使用数学公式准确。</span><span class="sxs-lookup"><span data-stu-id="3c514-105">You could use Key-Frame or even From/To/By animations to approximate these effects but it would take a significant amount of work and the animation would be less accurate than using a mathematical formula.</span></span>  
  
 <span data-ttu-id="3c514-106">除了通过继承创建自己的自定义缓动函数外<xref:System.Windows.Media.Animation.EasingFunctionBase>，您还可以使用运行时提供的几个缓动函数之一来创建常见效果。</span><span class="sxs-lookup"><span data-stu-id="3c514-106">Besides creating your own custom easing function by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>, you can use one of several easing functions provided by the runtime to create common effects.</span></span>  
  
- <span data-ttu-id="3c514-107"><xref:System.Windows.Media.Animation.BackEase>：在动画开始在指示的路径中设置动画之前稍微缩回动画的运动。</span><span class="sxs-lookup"><span data-stu-id="3c514-107"><xref:System.Windows.Media.Animation.BackEase>: Retracts the motion of an animation slightly before it begins to animate in the path indicated.</span></span>  
  
- <span data-ttu-id="3c514-108"><xref:System.Windows.Media.Animation.BounceEase>：创建弹跳效果。</span><span class="sxs-lookup"><span data-stu-id="3c514-108"><xref:System.Windows.Media.Animation.BounceEase>: Creates a bouncing effect.</span></span>  
  
- <span data-ttu-id="3c514-109"><xref:System.Windows.Media.Animation.CircleEase>：创建使用圆形函数加速和/或减速的动画。</span><span class="sxs-lookup"><span data-stu-id="3c514-109"><xref:System.Windows.Media.Animation.CircleEase>: Creates an animation that accelerates and/or decelerates using a circular function.</span></span>  
  
- <span data-ttu-id="3c514-110"><xref:System.Windows.Media.Animation.CubicEase>： 创建使用公式*f*（*t*） = *t*<sup>3</sup>加速和/或减速的动画。</span><span class="sxs-lookup"><span data-stu-id="3c514-110"><xref:System.Windows.Media.Animation.CubicEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>3</sup>.</span></span>  
  
- <span data-ttu-id="3c514-111"><xref:System.Windows.Media.Animation.ElasticEase>：创建类似于弹簧来回摆动的动画，直到它开始休息。</span><span class="sxs-lookup"><span data-stu-id="3c514-111"><xref:System.Windows.Media.Animation.ElasticEase>: Creates an animation that resembles a spring oscillating back and forth until it comes to rest.</span></span>  
  
- <span data-ttu-id="3c514-112"><xref:System.Windows.Media.Animation.ExponentialEase>：创建使用指数公式加速和/或减速的动画。</span><span class="sxs-lookup"><span data-stu-id="3c514-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Creates an animation that accelerates and/or decelerates using an exponential formula.</span></span>  
  
- <span data-ttu-id="3c514-113"><xref:System.Windows.Media.Animation.PowerEase>： 创建使用公式*f*（*t*） = *t*<sup>p</sup>的公式加速和/或减速的动画<xref:System.Windows.Media.Animation.PowerEase.Power%2A>，其中 p 等于属性。</span><span class="sxs-lookup"><span data-stu-id="3c514-113"><xref:System.Windows.Media.Animation.PowerEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>p</sup> where p is equal to the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span>  
  
- <span data-ttu-id="3c514-114"><xref:System.Windows.Media.Animation.QuadraticEase>： 创建使用公式*f*（*t*） = *t*<sup>2</sup>加速和/或减速的动画。</span><span class="sxs-lookup"><span data-stu-id="3c514-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>2</sup>.</span></span>  
  
- <span data-ttu-id="3c514-115"><xref:System.Windows.Media.Animation.QuarticEase>： 创建使用公式*f*（*t*） = *t*<sup>4</sup>加速和/或减速的动画。</span><span class="sxs-lookup"><span data-stu-id="3c514-115"><xref:System.Windows.Media.Animation.QuarticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>4</sup>.</span></span>  
  
- <span data-ttu-id="3c514-116"><xref:System.Windows.Media.Animation.QuinticEase>： 创建使用公式*f*（*t*） = *t*<sup>5</sup>加速和/或减速的动画。</span><span class="sxs-lookup"><span data-stu-id="3c514-116"><xref:System.Windows.Media.Animation.QuinticEase>: Create an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>5</sup>.</span></span>  
  
- <span data-ttu-id="3c514-117"><xref:System.Windows.Media.Animation.SineEase>：创建使用子项公式加速和/或减速的动画。</span><span class="sxs-lookup"><span data-stu-id="3c514-117"><xref:System.Windows.Media.Animation.SineEase>: Creates an animation that accelerates and/or decelerates using a sine formula.</span></span>  
  
 <span data-ttu-id="3c514-118">要将缓动函数应用于动画，请使用动画`EasingFunction`的属性指定要应用于动画的缓动函数。</span><span class="sxs-lookup"><span data-stu-id="3c514-118">To apply an easing function to an animation, use the `EasingFunction` property of the animation specify the easing function to apply to the animation.</span></span> <span data-ttu-id="3c514-119">下面的示例将<xref:System.Windows.Media.Animation.BounceEase>缓动函数应用于<xref:System.Windows.Media.Animation.DoubleAnimation>创建弹跳效果。</span><span class="sxs-lookup"><span data-stu-id="3c514-119">The following example applies a <xref:System.Windows.Media.Animation.BounceEase> easing function to a <xref:System.Windows.Media.Animation.DoubleAnimation> to create a bouncing effect.</span></span>  
  
 [!code-xaml[BounceEase_snippet#BounceEase](~/samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 <span data-ttu-id="3c514-120">在上一示例中，缓动函数应用于 From/To/By 动画。</span><span class="sxs-lookup"><span data-stu-id="3c514-120">In the previous example, the easing function was applied to a From/To/By animation.</span></span> <span data-ttu-id="3c514-121">还可以将这些缓动函数应用到关键帧动画。</span><span class="sxs-lookup"><span data-stu-id="3c514-121">You can also apply these easing functions to Key-Frame animations.</span></span> <span data-ttu-id="3c514-122">以下示例显示如何将关键帧与其相关联的缓动函数结合使用，以创建一个协定上升、减速、向下展开（如同下落），然后弹跳至停止的矩形的动画。</span><span class="sxs-lookup"><span data-stu-id="3c514-122">The following example shows how to use key frames with easing functions associated with them to create an animation of a rectangle that contracts upward, slows down, then expands downward (as though falling) and then bounces to a stop.</span></span>  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](~/samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 <span data-ttu-id="3c514-123">可以使用 属性<xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>更改缓动函数的特性，即更改动画插值的方式。</span><span class="sxs-lookup"><span data-stu-id="3c514-123">You can use the <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> property to alter how the easing function behaves, that is, change how the animation interpolates.</span></span> <span data-ttu-id="3c514-124">您可以为<xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>：</span><span class="sxs-lookup"><span data-stu-id="3c514-124">There are three possible values you can give for <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span></span>  
  
- <span data-ttu-id="3c514-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>：插值遵循与缓动函数关联的数学公式。</span><span class="sxs-lookup"><span data-stu-id="3c514-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Interpolation follows the mathematical formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="3c514-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>：插值遵循 100% 插值减去与缓动函数关联的公式的输出。</span><span class="sxs-lookup"><span data-stu-id="3c514-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Interpolation follows 100% interpolation minus the output of the formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="3c514-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>：插值用于<xref:System.Windows.Media.Animation.EasingMode.EaseIn>动画的上半部分和<xref:System.Windows.Media.Animation.EasingMode.EaseOut>下半场。</span><span class="sxs-lookup"><span data-stu-id="3c514-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Interpolation uses <xref:System.Windows.Media.Animation.EasingMode.EaseIn> for the first half of the animation and <xref:System.Windows.Media.Animation.EasingMode.EaseOut> for the second half.</span></span>  
  
 <span data-ttu-id="3c514-128">下图显示了*f*（*x* <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> ） 表示动画进度和*t*表示时间的不同值。</span><span class="sxs-lookup"><span data-stu-id="3c514-128">The graphs below demonstrate the different values of <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> where *f*(*x*) represents the animation progress and *t* represents time.</span></span>  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 <span data-ttu-id="3c514-129">![BackEase EasingMode 图。](./media/backease-graph.png "BackEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="3c514-129">![BackEase EasingMode graphs.](./media/backease-graph.png "BackEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 <span data-ttu-id="3c514-130">![BounceEase EasingMode 图。](./media/bounceease-graph.png "BounceEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="3c514-130">![BounceEase EasingMode graphs.](./media/bounceease-graph.png "BounceEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 <span data-ttu-id="3c514-131">![CircleEase EasingMode 图。](./media/circleease-graph.png "CircleEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="3c514-131">![CircleEase EasingMode graphs.](./media/circleease-graph.png "CircleEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 <span data-ttu-id="3c514-132">![CubicEase EasingMode 图。](./media/cubicease-graph.png "CubicEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="3c514-132">![CubicEase EasingMode graphs.](./media/cubicease-graph.png "CubicEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 <span data-ttu-id="3c514-133">![带不同缓动模式图的 ElasticEase。](./media/elasticease-graph.png "ElasticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="3c514-133">![ElasticEase with graphs of different easingmodes.](./media/elasticease-graph.png "ElasticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 <span data-ttu-id="3c514-134">![具有不同缓动模式的 ExponentialEase 图。](./media/exponentialease-graph.png "ExponentialEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="3c514-134">![ExponentialEase graphs of different easingmodes.](./media/exponentialease-graph.png "ExponentialEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 <span data-ttu-id="3c514-135">![带不同缓动模式图的 QuarticEase。](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="3c514-135">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 <span data-ttu-id="3c514-136">![具有不同缓动模式的图形的二次缓动](./media/quadraticease-graph.png "QuadraticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="3c514-136">![QuadraticEase with graphs of different easingmodes](./media/quadraticease-graph.png "QuadraticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 <span data-ttu-id="3c514-137">![带不同缓动模式图的 QuarticEase。](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="3c514-137">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 <span data-ttu-id="3c514-138">![带不同缓动模式图的 QuinticEase。](./media/quinticease-graph.png "QuinticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="3c514-138">![QuinticEase with graphs of different easingmodes.](./media/quinticease-graph.png "QuinticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 <span data-ttu-id="3c514-139">![不同 EasingMode 值的 SineEase](./media/sineease-graph.png "SineEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="3c514-139">![SineEase for different EasingMode values](./media/sineease-graph.png "SineEase_Graph")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3c514-140">可以使用 创建<xref:System.Windows.Media.Animation.PowerEase>与<xref:System.Windows.Media.Animation.CubicEase><xref:System.Windows.Media.Animation.QuadraticEase><xref:System.Windows.Media.Animation.QuarticEase>、 和<xref:System.Windows.Media.Animation.QuinticEase>以及 使用 属性<xref:System.Windows.Media.Animation.PowerEase.Power%2A>相同的行为。</span><span class="sxs-lookup"><span data-stu-id="3c514-140">You can use <xref:System.Windows.Media.Animation.PowerEase> to create the same behavior as <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, and <xref:System.Windows.Media.Animation.QuinticEase> by using the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span> <span data-ttu-id="3c514-141">例如，如果要使用<xref:System.Windows.Media.Animation.PowerEase>替换<xref:System.Windows.Media.Animation.CubicEase>，请指定<xref:System.Windows.Media.Animation.PowerEase.Power%2A>值 3。</span><span class="sxs-lookup"><span data-stu-id="3c514-141">For example, if you want to use <xref:System.Windows.Media.Animation.PowerEase> to substitute for <xref:System.Windows.Media.Animation.CubicEase>, specify a <xref:System.Windows.Media.Animation.PowerEase.Power%2A> value of 3.</span></span>  
  
 <span data-ttu-id="3c514-142">除了使用运行时中包含的缓动函数外，还可以通过继承 来<xref:System.Windows.Media.Animation.EasingFunctionBase>创建自己的自定义缓动函数。</span><span class="sxs-lookup"><span data-stu-id="3c514-142">In addition to using the easing functions included in the run-time, you can create your own custom easing functions by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span></span> <span data-ttu-id="3c514-143">以下示例演示如何创建简单的自定义缓动函数。</span><span class="sxs-lookup"><span data-stu-id="3c514-143">The following example demonstrates how to create a simple custom easing function.</span></span> <span data-ttu-id="3c514-144">您可以添加您自己的数学逻辑，用于缓动函数如何通过重写<xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A>方法来运行。</span><span class="sxs-lookup"><span data-stu-id="3c514-144">You can add your own mathematical logic for how the easing function behaves by overriding the <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> method.</span></span>
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
