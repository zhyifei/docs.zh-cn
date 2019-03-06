---
title: 如何：指定时间线是否自动反转
ms.date: 03/30/2017
helpviewer_keywords:
- AutoReverse property of timelines [WPF]
- Timelines [WPF], AutoReverse property
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
ms.openlocfilehash: 0fe2d337d8afa5197475e5b9ee40950226596e8b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354201"
---
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a><span data-ttu-id="1d528-102">如何：指定时间线是否自动反转</span><span class="sxs-lookup"><span data-stu-id="1d528-102">How to: Specify Whether a Timeline Automatically Reverses</span></span>
<span data-ttu-id="1d528-103">时间线的<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>属性确定是否反向播放完成向前迭代后。</span><span class="sxs-lookup"><span data-stu-id="1d528-103">A timeline's <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property determines whether it plays in reverse after it completes a forward iteration.</span></span> <span data-ttu-id="1d528-104">下面的示例演示使用相同的持续时间和目标值，但使用不同的多个动画<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>设置。</span><span class="sxs-lookup"><span data-stu-id="1d528-104">The following example shows several animations with identical duration and target values, but with different <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> settings.</span></span> <span data-ttu-id="1d528-105">若要演示如何<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>属性具有不同的行为与<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>设置，某些动画设置为重复。</span><span class="sxs-lookup"><span data-stu-id="1d528-105">To demonstrate how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property behaves with different <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> settings, some animations are set to repeat.</span></span> <span data-ttu-id="1d528-106">最后一个动画演示如何将<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>属性嵌套时间线上的工作原理。</span><span class="sxs-lookup"><span data-stu-id="1d528-106">The last animation shows how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property works on nested timelines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d528-107">示例</span><span class="sxs-lookup"><span data-stu-id="1d528-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
