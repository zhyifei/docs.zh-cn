---
title: 如何：在使用情节提要对属性进行动画处理后设置此属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], changing property values after
ms.assetid: 79466556-4dbf-40bd-9c1e-a77613b07077
ms.openlocfilehash: 593d3fcefe3bb81518d0886afde82f9a172874ba
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2019
ms.locfileid: "64912389"
---
# <a name="how-to-set-a-property-after-animating-it-with-a-storyboard"></a><span data-ttu-id="73e65-102">如何：在使用情节提要对属性进行动画处理后设置此属性</span><span class="sxs-lookup"><span data-stu-id="73e65-102">How to: Set a Property After Animating It with a Storyboard</span></span>
<span data-ttu-id="73e65-103">在某些情况下，它可能显示后进行动画处理，无法更改属性的值。</span><span class="sxs-lookup"><span data-stu-id="73e65-103">In some cases, it might appear that you can't change the value of a property after it has been animated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73e65-104">示例</span><span class="sxs-lookup"><span data-stu-id="73e65-104">Example</span></span>  
 <span data-ttu-id="73e65-105">在以下示例中，<xref:System.Windows.Media.Animation.Storyboard>使用的颜色进行动画处理<xref:System.Windows.Media.SolidColorBrush>。</span><span class="sxs-lookup"><span data-stu-id="73e65-105">In the following example, a <xref:System.Windows.Media.Animation.Storyboard> is used to animate the color of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="73e65-106">单击此按钮时，会触发情节提要。</span><span class="sxs-lookup"><span data-stu-id="73e65-106">The storyboard is triggered when the button is clicked.</span></span> <span data-ttu-id="73e65-107"><xref:System.Windows.Media.Animation.Timeline.Completed> ，以便通知程序处理事件时<xref:System.Windows.Media.Animation.ColorAnimation>完成。</span><span class="sxs-lookup"><span data-stu-id="73e65-107">The <xref:System.Windows.Media.Animation.Timeline.Completed> event is handled so that the program is notified when the <xref:System.Windows.Media.Animation.ColorAnimation> completes.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton1Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton1declaration)]  
  
## <a name="example"></a><span data-ttu-id="73e65-108">示例</span><span class="sxs-lookup"><span data-stu-id="73e65-108">Example</span></span>  
 <span data-ttu-id="73e65-109">之后<xref:System.Windows.Media.Animation.ColorAnimation>完成后，该程序尝试更改画笔的颜色为蓝色。</span><span class="sxs-lookup"><span data-stu-id="73e65-109">After the <xref:System.Windows.Media.Animation.ColorAnimation> completes, the program attempts to change the brush's color to blue.</span></span>  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton1Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton1handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton1Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton1handler)]  
  
 <span data-ttu-id="73e65-110">前面的代码似乎不执行任何操作： 画笔仍然保持为黄色，即的值提供的<xref:System.Windows.Media.Animation.ColorAnimation>，经过动画处理的画笔。</span><span class="sxs-lookup"><span data-stu-id="73e65-110">The previous code doesn't appear to do anything: the brush remains yellow, which is the value supplied by the <xref:System.Windows.Media.Animation.ColorAnimation> that animated the brush.</span></span> <span data-ttu-id="73e65-111">基础属性值 （基本值） 实际更改为蓝色。</span><span class="sxs-lookup"><span data-stu-id="73e65-111">The underlying property value (the base value) is actually changed to blue.</span></span> <span data-ttu-id="73e65-112">但是，有效，或当前的值仍保持为黄色因为<xref:System.Windows.Media.Animation.ColorAnimation>仍然在重写的基础价值。</span><span class="sxs-lookup"><span data-stu-id="73e65-112">However, the effective, or current, value remains yellow because the <xref:System.Windows.Media.Animation.ColorAnimation> is still overriding the base value.</span></span> <span data-ttu-id="73e65-113">如果你想要再次变得有效的值的基础值，必须使动画不再影响该属性。</span><span class="sxs-lookup"><span data-stu-id="73e65-113">If you want the base value to become the effective value again, you must stop the animation from influencing the property.</span></span> <span data-ttu-id="73e65-114">有三种方法使用演示图板动画执行此操作：</span><span class="sxs-lookup"><span data-stu-id="73e65-114">There are three ways to do this with storyboard animations:</span></span>  
  
- <span data-ttu-id="73e65-115">设置动画的<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>属性 <xref:System.Windows.Media.Animation.FillBehavior.Stop></span><span class="sxs-lookup"><span data-stu-id="73e65-115">Set the animation's <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property to <xref:System.Windows.Media.Animation.FillBehavior.Stop></span></span>  
  
- <span data-ttu-id="73e65-116">删除整个情节提要。</span><span class="sxs-lookup"><span data-stu-id="73e65-116">Remove the entire Storyboard.</span></span>  
  
- <span data-ttu-id="73e65-117">删除中的各个属性的动画。</span><span class="sxs-lookup"><span data-stu-id="73e65-117">Remove the animation from the individual property.</span></span>  
  
## <a name="set-the-animations-fillbehavior-property-to-stop"></a><span data-ttu-id="73e65-118">将动画的 FillBehavior 属性设置为 Stop</span><span class="sxs-lookup"><span data-stu-id="73e65-118">Set the animation's FillBehavior property to Stop</span></span>  
 <span data-ttu-id="73e65-119">通过设置<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>到<xref:System.Windows.Media.Animation.FillBehavior.Stop>，告诉动画停止到达其有效期末尾后影响其目标属性。</span><span class="sxs-lookup"><span data-stu-id="73e65-119">By setting <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, you tell the animation to stop affecting its target property after it reaches the end of its active period.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton2Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton2declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton2Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton2handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton2Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton2handler)]  
  
## <a name="remove-the-entire-storyboard"></a><span data-ttu-id="73e65-120">删除整个情节提要</span><span class="sxs-lookup"><span data-stu-id="73e65-120">Remove the entire storyboard</span></span>  
 <span data-ttu-id="73e65-121">通过使用<xref:System.Windows.Media.Animation.RemoveStoryboard>触发器或<xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType>方法，您告诉情节提要动画停止影响其目标属性。</span><span class="sxs-lookup"><span data-stu-id="73e65-121">By using a <xref:System.Windows.Media.Animation.RemoveStoryboard> trigger or the <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> method, you tell the storyboard animations to stop affecting their target properties.</span></span> <span data-ttu-id="73e65-122">此方法和设置之间的区别<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>属性是可以删除情节提要在任何时间，而<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>属性动画到达其活动周期的结尾时才有意义。</span><span class="sxs-lookup"><span data-stu-id="73e65-122">The difference between this approach and setting the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property is that you can remove the storyboard at anytime, while the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property only has an effect when the animation reaches the end of its active period.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton3Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton3declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton3Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton3handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton3Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton3handler)]  
  
## <a name="remove-an-animation-from-an-individual-property"></a><span data-ttu-id="73e65-123">从的单个属性中删除动画</span><span class="sxs-lookup"><span data-stu-id="73e65-123">Remove an animation from an individual property</span></span>  
 <span data-ttu-id="73e65-124">若要停止的动画影响属性的另一种方法是使用<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29>对象进行动画处理的方法。</span><span class="sxs-lookup"><span data-stu-id="73e65-124">Another technique to stop an animation from affecting a property is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> method of the object being animated.</span></span> <span data-ttu-id="73e65-125">指定要进行动画处理的第一个参数的属性和`null`为第二个。</span><span class="sxs-lookup"><span data-stu-id="73e65-125">Specify the property being animated as the first parameter and `null` as the second.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton4Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton4declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton4Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton4handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton4Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton4handler)]  
  
 <span data-ttu-id="73e65-126">此方法也适用于非演示图板动画。</span><span class="sxs-lookup"><span data-stu-id="73e65-126">This technique also works for non-storyboard animations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73e65-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="73e65-127">See also</span></span>

- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.Animation.RemoveStoryboard>
- [<span data-ttu-id="73e65-128">动画概述</span><span class="sxs-lookup"><span data-stu-id="73e65-128">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="73e65-129">属性动画技术概述</span><span class="sxs-lookup"><span data-stu-id="73e65-129">Property Animation Techniques Overview</span></span>](property-animation-techniques-overview.md)
