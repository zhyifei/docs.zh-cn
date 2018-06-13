---
title: 如何：指定时间线是否自动反转
ms.date: 03/30/2017
helpviewer_keywords:
- AutoReverse property of timelines [WPF]
- Timelines [WPF], AutoReverse property
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
ms.openlocfilehash: 498aefa16b8a76262c01965b8992ef9a94b7ce28
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560060"
---
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a><span data-ttu-id="9f68c-102">如何：指定时间线是否自动反转</span><span class="sxs-lookup"><span data-stu-id="9f68c-102">How to: Specify Whether a Timeline Automatically Reverses</span></span>
<span data-ttu-id="9f68c-103">时间线的<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>属性确定是否它播放按相反的顺序完成向前迭代后。</span><span class="sxs-lookup"><span data-stu-id="9f68c-103">A timeline's <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property determines whether it plays in reverse after it completes a forward iteration.</span></span> <span data-ttu-id="9f68c-104">下面的示例演示使用相同的持续时间和目标值，但使用不同的几个动画<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>设置。</span><span class="sxs-lookup"><span data-stu-id="9f68c-104">The following example shows several animations with identical duration and target values, but with different <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> settings.</span></span> <span data-ttu-id="9f68c-105">为了演示如何<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>属性具有不同的行为<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>设置，某些动画都设置为重复。</span><span class="sxs-lookup"><span data-stu-id="9f68c-105">To demonstrate how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property behaves with different <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> settings, some animations are set to repeat.</span></span> <span data-ttu-id="9f68c-106">最后一个的动画演示如何<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>属性适用于嵌套的时间线。</span><span class="sxs-lookup"><span data-stu-id="9f68c-106">The last animation shows how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property works on nested timelines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f68c-107">示例</span><span class="sxs-lookup"><span data-stu-id="9f68c-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
