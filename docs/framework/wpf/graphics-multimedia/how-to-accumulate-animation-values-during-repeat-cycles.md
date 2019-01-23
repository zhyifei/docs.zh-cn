---
title: 如何：在重复循环过程中累积动画值
ms.date: 03/30/2017
helpviewer_keywords:
- accumulating animation values across repeating cycles [WPF]
- animation [WPF], accumulating values across repeating cycles
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
ms.openlocfilehash: 6e98b7eefd0c30e728b60926096c0f082bc079ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587276"
---
# <a name="how-to-accumulate-animation-values-during-repeat-cycles"></a><span data-ttu-id="a57a0-102">如何：在重复循环过程中累积动画值</span><span class="sxs-lookup"><span data-stu-id="a57a0-102">How to: Accumulate Animation Values During Repeat Cycles</span></span>
<span data-ttu-id="a57a0-103">此示例演示如何使用<xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A>属性以通过重复循环累积动画值。</span><span class="sxs-lookup"><span data-stu-id="a57a0-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to accumulate animation values across repeating cycles.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a57a0-104">示例</span><span class="sxs-lookup"><span data-stu-id="a57a0-104">Example</span></span>  
 <span data-ttu-id="a57a0-105">使用<xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A>属性通过重复循环累积动画的基值。</span><span class="sxs-lookup"><span data-stu-id="a57a0-105">Use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to accumulate base values of an animation across repeating cycles.</span></span> <span data-ttu-id="a57a0-106">例如，如果你设置重复 9 次的动画 (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> ="9 x") 和设置的属性进行动画处理介于 10 到 15 之间 (从 = 10 到 = 15)，该属性进行动画处理从 10 到 15 在第一个周期中，从 15 到 20 在第二个周期内从 20%到 25 期间的第三个周期，依此类推。</span><span class="sxs-lookup"><span data-stu-id="a57a0-106">For example, if you set an animation to repeat 9 times (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9x") and you set the property to animate between 10 and 15 (From = 10 To = 15), the property animates from 10 to 15 during the first cycle, from 15 to 20 during the second cycle, from 20 to 25 during the third cycle, and so on.</span></span> <span data-ttu-id="a57a0-107">因此，每个动画循环使用从以前的动画循环的动画结束值作为其基础值。</span><span class="sxs-lookup"><span data-stu-id="a57a0-107">Hence, each animation cycle uses the ending animation value from the previous animation cycle as its base value.</span></span>  
  
 <span data-ttu-id="a57a0-108">可以使用`IsCumulative`具有最基本的动画和大多数关键帧动画的属性。</span><span class="sxs-lookup"><span data-stu-id="a57a0-108">You can use the `IsCumulative` property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="a57a0-109">有关详细信息，请参阅[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)并[关键帧动画概述](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="a57a0-109">For more information, see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) and [Key-Frame Animations Overview](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="a57a0-110">下面的示例演示此行为由四个矩形的宽度进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="a57a0-110">The following example shows this behavior by animating the width of four rectangles.</span></span> <span data-ttu-id="a57a0-111">下面的示例：</span><span class="sxs-lookup"><span data-stu-id="a57a0-111">The example:</span></span>  
  
-   <span data-ttu-id="a57a0-112">与第一个矩形进行动画处理<xref:System.Windows.Media.Animation.DoubleAnimation>，并设置<xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="a57a0-112">Animates the first rectangle with <xref:System.Windows.Media.Animation.DoubleAnimation> and sets the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to `true`.</span></span>  
  
-   <span data-ttu-id="a57a0-113">与第二个矩形进行动画处理<xref:System.Windows.Media.Animation.DoubleAnimation>，并设置<xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A>属性设置的默认值为`false`。</span><span class="sxs-lookup"><span data-stu-id="a57a0-113">Animates the second rectangle with <xref:System.Windows.Media.Animation.DoubleAnimation> and sets the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to the default value of `false`.</span></span>  
  
-   <span data-ttu-id="a57a0-114">使用第三个矩形进行动画处理<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>，并设置<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="a57a0-114">Animates the third rectangle with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> and sets the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> property to `true`.</span></span>  
  
-   <span data-ttu-id="a57a0-115">包含的最后一个矩形进行动画处理<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>，并设置<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A>属性设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="a57a0-115">Animates the last rectangle with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> and sets the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> property to `false`.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="a57a0-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="a57a0-116">See also</span></span>
- [<span data-ttu-id="a57a0-117">向动画起始值添加动画输出值</span><span class="sxs-lookup"><span data-stu-id="a57a0-117">Add an Animation Output Value to an Animation Starting Value</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-add-an-animation-output-value-to-an-animation-starting-value.md)
- [<span data-ttu-id="a57a0-118">重复动画</span><span class="sxs-lookup"><span data-stu-id="a57a0-118">Repeat an Animation</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md)
- [<span data-ttu-id="a57a0-119">动画概述</span><span class="sxs-lookup"><span data-stu-id="a57a0-119">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="a57a0-120">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="a57a0-120">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)
- [<span data-ttu-id="a57a0-121">帮助主题</span><span class="sxs-lookup"><span data-stu-id="a57a0-121">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
