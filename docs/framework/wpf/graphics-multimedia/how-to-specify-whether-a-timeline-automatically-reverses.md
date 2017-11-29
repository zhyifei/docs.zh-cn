---
title: "如何：指定时间线是否自动反转"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- AutoReverse property of timelines [WPF]
- Timelines [WPF], AutoReverse property
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2abce54905f0bb06bf983c065e064ce2dfeba932
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a><span data-ttu-id="a2d84-102">如何：指定时间线是否自动反转</span><span class="sxs-lookup"><span data-stu-id="a2d84-102">How to: Specify Whether a Timeline Automatically Reverses</span></span>
<span data-ttu-id="a2d84-103">时间线的<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>属性确定是否它播放按相反的顺序完成向前迭代后。</span><span class="sxs-lookup"><span data-stu-id="a2d84-103">A timeline's <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property determines whether it plays in reverse after it completes a forward iteration.</span></span> <span data-ttu-id="a2d84-104">下面的示例演示使用相同的持续时间和目标值，但使用不同的几个动画<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>设置。</span><span class="sxs-lookup"><span data-stu-id="a2d84-104">The following example shows several animations with identical duration and target values, but with different <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> settings.</span></span> <span data-ttu-id="a2d84-105">为了演示如何<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>属性具有不同的行为<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>设置，某些动画都设置为重复。</span><span class="sxs-lookup"><span data-stu-id="a2d84-105">To demonstrate how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property behaves with different <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> settings, some animations are set to repeat.</span></span> <span data-ttu-id="a2d84-106">最后一个的动画演示如何<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>属性适用于嵌套的时间线。</span><span class="sxs-lookup"><span data-stu-id="a2d84-106">The last animation shows how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property works on nested timelines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2d84-107">示例</span><span class="sxs-lookup"><span data-stu-id="a2d84-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
