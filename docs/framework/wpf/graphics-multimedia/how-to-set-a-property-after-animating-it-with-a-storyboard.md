---
title: "如何：在使用演示图板对属性进行动画处理后设置该属性"
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
helpviewer_keywords: animation [WPF], changing property values after
ms.assetid: 79466556-4dbf-40bd-9c1e-a77613b07077
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 357a9bb6c1a01b00e7f9bcfc17267797f20366b0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-a-property-after-animating-it-with-a-storyboard"></a><span data-ttu-id="0ee4a-102">如何：在使用演示图板对属性进行动画处理后设置该属性</span><span class="sxs-lookup"><span data-stu-id="0ee4a-102">How to: Set a Property After Animating It with a Storyboard</span></span>
<span data-ttu-id="0ee4a-103">在某些情况下，它可能显示，你不能更改属性的值后进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="0ee4a-103">In some cases, it might appear that you can't change the value of a property after it has been animated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ee4a-104">示例</span><span class="sxs-lookup"><span data-stu-id="0ee4a-104">Example</span></span>  
 <span data-ttu-id="0ee4a-105">在下面的示例中，<xref:System.Windows.Media.Animation.Storyboard>用于进行动画处理的颜色<xref:System.Windows.Media.SolidColorBrush>。</span><span class="sxs-lookup"><span data-stu-id="0ee4a-105">In the following example, a <xref:System.Windows.Media.Animation.Storyboard> is used to animate the color of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="0ee4a-106">单击该按钮时，将触发情节提要。</span><span class="sxs-lookup"><span data-stu-id="0ee4a-106">The storyboard is triggered when the button is clicked.</span></span> <span data-ttu-id="0ee4a-107"><xref:System.Windows.Media.Animation.Timeline.Completed>以便通知程序处理事件时<xref:System.Windows.Media.Animation.ColorAnimation>完成。</span><span class="sxs-lookup"><span data-stu-id="0ee4a-107">The <xref:System.Windows.Media.Animation.Timeline.Completed> event is handled so that the program is notified when the <xref:System.Windows.Media.Animation.ColorAnimation> completes.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton1Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton1declaration)]  
  
## <a name="example"></a><span data-ttu-id="0ee4a-108">示例</span><span class="sxs-lookup"><span data-stu-id="0ee4a-108">Example</span></span>  
 <span data-ttu-id="0ee4a-109">后<xref:System.Windows.Media.Animation.ColorAnimation>完成后，该程序尝试更改画笔的颜色为蓝色。</span><span class="sxs-lookup"><span data-stu-id="0ee4a-109">After the <xref:System.Windows.Media.Animation.ColorAnimation> completes, the program attempts to change the brush's color to blue.</span></span>  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton1handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton1handler)]  
  
 <span data-ttu-id="0ee4a-110">前面的代码不会显示为执行任何操作： 画笔仍然保持为黄色，即的值提供<xref:System.Windows.Media.Animation.ColorAnimation>基值画笔。</span><span class="sxs-lookup"><span data-stu-id="0ee4a-110">The previous code doesn't appear to do anything: the brush remains yellow, which is the value supplied by the <xref:System.Windows.Media.Animation.ColorAnimation> that animated the brush.</span></span> <span data-ttu-id="0ee4a-111">基础属性值 （基本值） 实际更改为蓝色。</span><span class="sxs-lookup"><span data-stu-id="0ee4a-111">The underlying property value (the base value) is actually changed to blue.</span></span> <span data-ttu-id="0ee4a-112">但是，有效，或者说当前值仍保持为黄色因为<xref:System.Windows.Media.Animation.ColorAnimation>仍将重写的基础价值。</span><span class="sxs-lookup"><span data-stu-id="0ee4a-112">However, the effective, or current, value remains yellow because the <xref:System.Windows.Media.Animation.ColorAnimation> is still overriding the base value.</span></span> <span data-ttu-id="0ee4a-113">如果你想要再次变得有效的值的基础值，你必须停止动画影响该属性。</span><span class="sxs-lookup"><span data-stu-id="0ee4a-113">If you want the base value to become the effective value again, you must stop the animation from influencing the property.</span></span> <span data-ttu-id="0ee4a-114">有三种方法可以使用情节提要动画执行此操作：</span><span class="sxs-lookup"><span data-stu-id="0ee4a-114">There are three ways to do this with storyboard animations:</span></span>  
  
-   <span data-ttu-id="0ee4a-115">设置动画的<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>属性<xref:System.Windows.Media.Animation.FillBehavior.Stop></span><span class="sxs-lookup"><span data-stu-id="0ee4a-115">Set the animation's <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property to <xref:System.Windows.Media.Animation.FillBehavior.Stop></span></span>  
  
-   <span data-ttu-id="0ee4a-116">删除整个情节提要。</span><span class="sxs-lookup"><span data-stu-id="0ee4a-116">Remove the entire Storyboard.</span></span>  
  
-   <span data-ttu-id="0ee4a-117">动画移除单个属性。</span><span class="sxs-lookup"><span data-stu-id="0ee4a-117">Remove the animation from the individual property.</span></span>  
  
## <a name="set-the-animations-fillbehavior-property-to-stop"></a><span data-ttu-id="0ee4a-118">将动画的 FillBehavior 属性设置为停止</span><span class="sxs-lookup"><span data-stu-id="0ee4a-118">Set the animation's FillBehavior property to Stop</span></span>  
 <span data-ttu-id="0ee4a-119">通过设置<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>到<xref:System.Windows.Media.Animation.FillBehavior.Stop>，告诉动画停止它到达其有效期末尾后影响其目标属性。</span><span class="sxs-lookup"><span data-stu-id="0ee4a-119">By setting <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, you tell the animation to stop affecting its target property after it reaches the end of its active period.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton2Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton2declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton2handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton2handler)]  
  
## <a name="remove-the-entire-storyboard"></a><span data-ttu-id="0ee4a-120">删除整个情节提要</span><span class="sxs-lookup"><span data-stu-id="0ee4a-120">Remove the entire storyboard</span></span>  
 <span data-ttu-id="0ee4a-121">通过使用<xref:System.Windows.Media.Animation.RemoveStoryboard>触发器或<xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType>方法，你可以判断停止影响其目标属性的情节提要动画。</span><span class="sxs-lookup"><span data-stu-id="0ee4a-121">By using a <xref:System.Windows.Media.Animation.RemoveStoryboard> trigger or the <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> method, you tell the storyboard animations to stop affecting their target properties.</span></span> <span data-ttu-id="0ee4a-122">此方法与设置之间的差异<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>属性是你可以删除情节提要在任何时候，而<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>时动画到达其有效期末尾后，属性将仅才有效。</span><span class="sxs-lookup"><span data-stu-id="0ee4a-122">The difference between this approach and setting the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property is that you can remove the storyboard at anytime, while the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property only has an effect when the animation reaches the end of its active period.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton3Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton3declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton3handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton3handler)]  
  
## <a name="remove-an-animation-from-an-individual-property"></a><span data-ttu-id="0ee4a-123">动画移除的单个属性</span><span class="sxs-lookup"><span data-stu-id="0ee4a-123">Remove an animation from an individual property</span></span>  
 <span data-ttu-id="0ee4a-124">若要停止动画影响属性的另一种方法是使用<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29>正进行动画处理的对象的方法。</span><span class="sxs-lookup"><span data-stu-id="0ee4a-124">Another technique to stop an animation from affecting a property is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> method of the object being animated.</span></span> <span data-ttu-id="0ee4a-125">指定正进行动画处理的第一个参数的属性和`null`为第二个。</span><span class="sxs-lookup"><span data-stu-id="0ee4a-125">Specify the property being animated as the first parameter and `null` as the second.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton4Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton4declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton4handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton4handler)]  
  
 <span data-ttu-id="0ee4a-126">此方法也适用于非情节提要的动画。</span><span class="sxs-lookup"><span data-stu-id="0ee4a-126">This technique also works for non-storyboard animations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ee4a-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ee4a-127">See Also</span></span>  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>  
 <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Media.Animation.RemoveStoryboard>  
 [<span data-ttu-id="0ee4a-128">动画概述</span><span class="sxs-lookup"><span data-stu-id="0ee4a-128">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="0ee4a-129">属性动画技术概述</span><span class="sxs-lookup"><span data-stu-id="0ee4a-129">Property Animation Techniques Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
