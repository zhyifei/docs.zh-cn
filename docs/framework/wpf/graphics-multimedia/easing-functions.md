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
ms.openlocfilehash: 456308e37bddc1df86b49085139a3810c4959a58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763051"
---
# <a name="easing-functions"></a><span data-ttu-id="11008-102">缓动函数</span><span class="sxs-lookup"><span data-stu-id="11008-102">Easing Functions</span></span>
<span data-ttu-id="11008-103">缓动函数允许将自定义的数学公式应用到动画。</span><span class="sxs-lookup"><span data-stu-id="11008-103">Easing functions allow you to apply custom mathematical formulas to your animations.</span></span> <span data-ttu-id="11008-104">例如，用户可能希望某个对象逼真地弹跳或表现出像在弹簧上一样。</span><span class="sxs-lookup"><span data-stu-id="11008-104">For example, you may want an object to realistically bounce or behave as though it were on a spring.</span></span> <span data-ttu-id="11008-105">可使用关键帧甚至 From/To/By 动画来近似地实现这些效果，但它将需要大量工作，并且动画不如使用数学公式准确。</span><span class="sxs-lookup"><span data-stu-id="11008-105">You could use Key-Frame or even From/To/By animations to approximate these effects but it would take a significant amount of work and the animation would be less accurate than using a mathematical formula.</span></span>  
  
 <span data-ttu-id="11008-106">除了通过继承创建自定义的缓动函数<xref:System.Windows.Media.Animation.EasingFunctionBase>，可以使用由运行时提供的多个缓动函数之一创建常见效果。</span><span class="sxs-lookup"><span data-stu-id="11008-106">Besides creating your own custom easing function by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>, you can use one of several easing functions provided by the runtime to create common effects.</span></span>  
  
- <span data-ttu-id="11008-107"><xref:System.Windows.Media.Animation.BackEase>：略微收回动画的动作，然后再开始进行动画处理指示的路径中。</span><span class="sxs-lookup"><span data-stu-id="11008-107"><xref:System.Windows.Media.Animation.BackEase>: Retracts the motion of an animation slightly before it begins to animate in the path indicated.</span></span>  
  
- <span data-ttu-id="11008-108"><xref:System.Windows.Media.Animation.BounceEase>：创建弹跳效果。</span><span class="sxs-lookup"><span data-stu-id="11008-108"><xref:System.Windows.Media.Animation.BounceEase>: Creates a bouncing effect.</span></span>  
  
- <span data-ttu-id="11008-109"><xref:System.Windows.Media.Animation.CircleEase>：创建加速和/或减速使用循环函数的动画。</span><span class="sxs-lookup"><span data-stu-id="11008-109"><xref:System.Windows.Media.Animation.CircleEase>: Creates an animation that accelerates and/or decelerates using a circular function.</span></span>  
  
- <span data-ttu-id="11008-110"><xref:System.Windows.Media.Animation.CubicEase>：创建加速和/或减速使用的公式的动画*f*(*t*) = *t*<sup>3</sup>。</span><span class="sxs-lookup"><span data-stu-id="11008-110"><xref:System.Windows.Media.Animation.CubicEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>3</sup>.</span></span>  
  
- <span data-ttu-id="11008-111"><xref:System.Windows.Media.Animation.ElasticEase>：创建类似于弹簧来回直到静止的动画。</span><span class="sxs-lookup"><span data-stu-id="11008-111"><xref:System.Windows.Media.Animation.ElasticEase>: Creates an animation that resembles a spring oscillating back and forth until it comes to rest.</span></span>  
  
- <span data-ttu-id="11008-112"><xref:System.Windows.Media.Animation.ExponentialEase>：创建加速和/或减速使用指数公式的动画。</span><span class="sxs-lookup"><span data-stu-id="11008-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Creates an animation that accelerates and/or decelerates using an exponential formula.</span></span>  
  
- <span data-ttu-id="11008-113"><xref:System.Windows.Media.Animation.PowerEase>：创建加速和/或减速使用的公式的动画*f*(*t*) = *t*<sup>p</sup>其中 p 等于<xref:System.Windows.Media.Animation.PowerEase.Power%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="11008-113"><xref:System.Windows.Media.Animation.PowerEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>p</sup> where p is equal to the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span>  
  
- <span data-ttu-id="11008-114"><xref:System.Windows.Media.Animation.QuadraticEase>：创建加速和/或减速使用的公式的动画*f*(*t*) = *t*<sup>2</sup>。</span><span class="sxs-lookup"><span data-stu-id="11008-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>2</sup>.</span></span>  
  
- <span data-ttu-id="11008-115"><xref:System.Windows.Media.Animation.QuarticEase>：创建加速和/或减速使用的公式的动画*f*(*t*) = *t*<sup>4</sup>。</span><span class="sxs-lookup"><span data-stu-id="11008-115"><xref:System.Windows.Media.Animation.QuarticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>4</sup>.</span></span>  
  
- <span data-ttu-id="11008-116"><xref:System.Windows.Media.Animation.QuinticEase>：创建加速和/或减速使用的公式的动画*f*(*t*) = *t*<sup>5</sup>。</span><span class="sxs-lookup"><span data-stu-id="11008-116"><xref:System.Windows.Media.Animation.QuinticEase>: Create an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>5</sup>.</span></span>  
  
- <span data-ttu-id="11008-117"><xref:System.Windows.Media.Animation.SineEase>：创建加速和/或减速使用正弦公式的动画。</span><span class="sxs-lookup"><span data-stu-id="11008-117"><xref:System.Windows.Media.Animation.SineEase>: Creates an animation that accelerates and/or decelerates using a sine formula.</span></span>  
  
 <span data-ttu-id="11008-118">若要应用到动画的缓动函数，使用`EasingFunction`动画属性指定要应用到动画的缓动函数。</span><span class="sxs-lookup"><span data-stu-id="11008-118">To apply an easing function to an animation, use the `EasingFunction` property of the animation specify the easing function to apply to the animation.</span></span> <span data-ttu-id="11008-119">下面的示例应用<xref:System.Windows.Media.Animation.BounceEase>缓动函数到<xref:System.Windows.Media.Animation.DoubleAnimation>创建弹跳效果。</span><span class="sxs-lookup"><span data-stu-id="11008-119">The following example applies a <xref:System.Windows.Media.Animation.BounceEase> easing function to a <xref:System.Windows.Media.Animation.DoubleAnimation> to create a bouncing effect.</span></span>  
  
 [!code-xaml[BounceEase_snippet#BounceEase](~/samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 <span data-ttu-id="11008-120">在上一示例中，缓动函数应用于 From/To/By 动画。</span><span class="sxs-lookup"><span data-stu-id="11008-120">In the previous example, the easing function was applied to a From/To/By animation.</span></span> <span data-ttu-id="11008-121">还可以将这些缓动函数应用到关键帧动画。</span><span class="sxs-lookup"><span data-stu-id="11008-121">You can also apply these easing functions to Key-Frame animations.</span></span> <span data-ttu-id="11008-122">以下示例显示如何将关键帧与其相关联的缓动函数结合使用，以创建一个协定上升、减速、向下展开（如同下落），然后弹跳至停止的矩形的动画。</span><span class="sxs-lookup"><span data-stu-id="11008-122">The following example shows how to use key frames with easing functions associated with them to create an animation of a rectangle that contracts upward, slows down, then expands downward (as though falling) and then bounces to a stop.</span></span>  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](~/samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 <span data-ttu-id="11008-123">可以使用<xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>属性更改缓动函数的行为方式，即更改动画的内插。</span><span class="sxs-lookup"><span data-stu-id="11008-123">You can use the <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> property to alter how the easing function behaves, that is, change how the animation interpolates.</span></span> <span data-ttu-id="11008-124">有三个可能的值可以为<xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span><span class="sxs-lookup"><span data-stu-id="11008-124">There are three possible values you can give for <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span></span>  
  
- <span data-ttu-id="11008-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>：内插遵循与缓动函数相关联的数学公式。</span><span class="sxs-lookup"><span data-stu-id="11008-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Interpolation follows the mathematical formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="11008-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>：内插遵循 100%内插值减去输出与缓动函数相关联的公式。</span><span class="sxs-lookup"><span data-stu-id="11008-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Interpolation follows 100% interpolation minus the output of the formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="11008-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>：使用内插<xref:System.Windows.Media.Animation.EasingMode.EaseIn>动画的第一个另一半和<xref:System.Windows.Media.Animation.EasingMode.EaseOut>虚拟机。</span><span class="sxs-lookup"><span data-stu-id="11008-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Interpolation uses <xref:System.Windows.Media.Animation.EasingMode.EaseIn> for the first half of the animation and <xref:System.Windows.Media.Animation.EasingMode.EaseOut> for the second half.</span></span>  
  
 <span data-ttu-id="11008-128">下图演示了不同的值<xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>其中*f*(*x*) 表示动画进度和*t*表示时间。</span><span class="sxs-lookup"><span data-stu-id="11008-128">The graphs below demonstrate the different values of <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> where *f*(*x*) represents the animation progress and *t* represents time.</span></span>  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 <span data-ttu-id="11008-129">![BackEase EasingMode 图。](./media/backease-graph.png "BackEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="11008-129">![BackEase EasingMode graphs.](./media/backease-graph.png "BackEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 <span data-ttu-id="11008-130">![BounceEase EasingMode 图。](./media/bounceease-graph.png "BounceEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="11008-130">![BounceEase EasingMode graphs.](./media/bounceease-graph.png "BounceEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 <span data-ttu-id="11008-131">![CircleEase EasingMode图。](./media/circleease-graph.png "CircleEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="11008-131">![CircleEase EasingMode graphs.](./media/circleease-graph.png "CircleEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 <span data-ttu-id="11008-132">![CubicEase EasingMode 图。](./media/cubicease-graph.png "CubicEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="11008-132">![CubicEase EasingMode graphs.](./media/cubicease-graph.png "CubicEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 <span data-ttu-id="11008-133">![带不同缓动模式图的 ElasticEase。](./media/elasticease-graph.png "ElasticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="11008-133">![ElasticEase with graphs of different easingmodes.](./media/elasticease-graph.png "ElasticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 <span data-ttu-id="11008-134">![不同缓动模式的 ExponentialEase 图。](./media/exponentialease-graph.png "ExponentialEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="11008-134">![ExponentialEase graphs of different easingmodes.](./media/exponentialease-graph.png "ExponentialEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 <span data-ttu-id="11008-135">![带不同缓动模式图的 QuarticEase。](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="11008-135">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 <span data-ttu-id="11008-136">![带不同缓动模式图的 QuadraticEase](./media/quadraticease-graph.png "QuadraticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="11008-136">![QuadraticEase with graphs of different easingmodes](./media/quadraticease-graph.png "QuadraticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 <span data-ttu-id="11008-137">![带不同缓动模式图的 QuarticEase。](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="11008-137">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 <span data-ttu-id="11008-138">![带不同缓动模式图的 QuinticEase。](./media/quinticease-graph.png "QuinticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="11008-138">![QuinticEase with graphs of different easingmodes.](./media/quinticease-graph.png "QuinticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 <span data-ttu-id="11008-139">![不同 EasingMode 值的 SineEase](./media/sineease-graph.png "SineEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="11008-139">![SineEase for different EasingMode values](./media/sineease-graph.png "SineEase_Graph")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11008-140">可以使用<xref:System.Windows.Media.Animation.PowerEase>来创建相同的行为<xref:System.Windows.Media.Animation.CubicEase>， <xref:System.Windows.Media.Animation.QuadraticEase>， <xref:System.Windows.Media.Animation.QuarticEase>，并<xref:System.Windows.Media.Animation.QuinticEase>使用<xref:System.Windows.Media.Animation.PowerEase.Power%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="11008-140">You can use <xref:System.Windows.Media.Animation.PowerEase> to create the same behavior as <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, and <xref:System.Windows.Media.Animation.QuinticEase> by using the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span> <span data-ttu-id="11008-141">例如，如果你想要使用<xref:System.Windows.Media.Animation.PowerEase>将替换为<xref:System.Windows.Media.Animation.CubicEase>，指定<xref:System.Windows.Media.Animation.PowerEase.Power%2A>值为 3。</span><span class="sxs-lookup"><span data-stu-id="11008-141">For example, if you want to use <xref:System.Windows.Media.Animation.PowerEase> to substitute for <xref:System.Windows.Media.Animation.CubicEase>, specify a <xref:System.Windows.Media.Animation.PowerEase.Power%2A> value of 3.</span></span>  
  
 <span data-ttu-id="11008-142">除了使用运行时中附带的缓动函数，可以创建自己的自定义缓动函数，通过继承<xref:System.Windows.Media.Animation.EasingFunctionBase>。</span><span class="sxs-lookup"><span data-stu-id="11008-142">In addition to using the easing functions included in the run-time, you can create your own custom easing functions by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span></span> <span data-ttu-id="11008-143">以下示例演示如何创建简单的自定义缓动函数。</span><span class="sxs-lookup"><span data-stu-id="11008-143">The following example demonstrates how to create a simple custom easing function.</span></span> <span data-ttu-id="11008-144">可以添加您自己的数学逻辑通过重写的缓动函数的行为方式<xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="11008-144">You can add your own mathematical logic for how the easing function behaves by overriding the <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> method.</span></span>   
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
