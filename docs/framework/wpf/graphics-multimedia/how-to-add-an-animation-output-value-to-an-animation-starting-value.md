---
title: 如何：向动画起始值添加动画输出值
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF]
ms.assetid: b89a82be-b03d-481e-a8d3-cc513d09ca00
ms.openlocfilehash: 820e03064d331e852a224e1f989685d7a77983db
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603022"
---
# <a name="how-to-add-an-animation-output-value-to-an-animation-starting-value"></a><span data-ttu-id="0b017-102">如何：向动画起始值添加动画输出值</span><span class="sxs-lookup"><span data-stu-id="0b017-102">How to: Add an Animation Output Value to an Animation Starting Value</span></span>
<span data-ttu-id="0b017-103">此示例演示如何向动画起始值添加动画输出值。</span><span class="sxs-lookup"><span data-stu-id="0b017-103">This example shows how to add an animation output value to an animation starting value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b017-104">示例</span><span class="sxs-lookup"><span data-stu-id="0b017-104">Example</span></span>  
 <span data-ttu-id="0b017-105"><xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A>属性指定是否希望添加到动画的属性的起始值 （基本值） 的动画的输出值。</span><span class="sxs-lookup"><span data-stu-id="0b017-105">The <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property specifies whether you want the output value of an animation added to the starting value (base value) of an animated property.</span></span> <span data-ttu-id="0b017-106">可以使用<xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A>具有最基本的动画和大多数关键帧动画的属性。</span><span class="sxs-lookup"><span data-stu-id="0b017-106">You can use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="0b017-107">有关详细信息，请参阅[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)并[关键帧动画概述](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="0b017-107">For more information, see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) and [Key-Frame Animations Overview](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="0b017-108">下面的示例演示使用的效果<xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType>具有属性<xref:System.Windows.Media.Animation.DoubleAnimation>并使用<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType>具有属性<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>。</span><span class="sxs-lookup"><span data-stu-id="0b017-108">The following example shows the effect of using the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimation> and using the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsAdditiveWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsAdditiveExample.xaml#isadditivewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="0b017-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b017-109">See also</span></span>
- [<span data-ttu-id="0b017-110">在重复循环过程中累积动画值</span><span class="sxs-lookup"><span data-stu-id="0b017-110">Accumulate Animation Values During Repeat Cycles</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)
- [<span data-ttu-id="0b017-111">动画概述</span><span class="sxs-lookup"><span data-stu-id="0b017-111">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="0b017-112">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="0b017-112">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)
- [<span data-ttu-id="0b017-113">动画和计时</span><span class="sxs-lookup"><span data-stu-id="0b017-113">Animation and Timing</span></span>](https://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)
- [<span data-ttu-id="0b017-114">帮助主题</span><span class="sxs-lookup"><span data-stu-id="0b017-114">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
