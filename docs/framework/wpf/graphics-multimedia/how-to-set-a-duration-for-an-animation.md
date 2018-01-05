---
title: "如何：设置动画的持续时间"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], duration
- Timelines [WPF], description
- duration of animations [WPF]
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e8d15a1b8432b3dae5bee73396bdec9fc9d50f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-a-duration-for-an-animation"></a><span data-ttu-id="47835-102">如何：设置动画的持续时间</span><span class="sxs-lookup"><span data-stu-id="47835-102">How to: Set a Duration for an Animation</span></span>
<span data-ttu-id="47835-103">A<xref:System.Windows.Media.Animation.Timeline>表示的时间段和段的长度由时间线的<xref:System.Windows.Duration>。</span><span class="sxs-lookup"><span data-stu-id="47835-103">A <xref:System.Windows.Media.Animation.Timeline> represents a segment of time and the length of that segment is determined by the timeline's <xref:System.Windows.Duration>.</span></span> <span data-ttu-id="47835-104">当<xref:System.Windows.Media.Animation.Timeline>到达结尾的其持续时间，就会停止播放。</span><span class="sxs-lookup"><span data-stu-id="47835-104">When a <xref:System.Windows.Media.Animation.Timeline> reaches the end of its duration, it stops playing.</span></span> <span data-ttu-id="47835-105">如果<xref:System.Windows.Media.Animation.Timeline>具有子时间线，它们也会停止播放。</span><span class="sxs-lookup"><span data-stu-id="47835-105">If the <xref:System.Windows.Media.Animation.Timeline> has child timelines, they stop playing as well.</span></span> <span data-ttu-id="47835-106">对于动画，<xref:System.Windows.Duration>指定动画的时间转换从其起始值为其结束的值。</span><span class="sxs-lookup"><span data-stu-id="47835-106">In the case of an animation, the <xref:System.Windows.Duration> specifies how long the animation takes to transition from its starting value to its ending value.</span></span>  
  
 <span data-ttu-id="47835-107">你可以指定<xref:System.Windows.Duration>与特定的有限时间或特殊值<xref:System.Windows.Duration.Automatic%2A>或<xref:System.Windows.Duration.Forever%2A>。</span><span class="sxs-lookup"><span data-stu-id="47835-107">You can specify a <xref:System.Windows.Duration> with a specific, finite time or the special values <xref:System.Windows.Duration.Automatic%2A> or <xref:System.Windows.Duration.Forever%2A>.</span></span> <span data-ttu-id="47835-108">动画的持续时间必须始终为时间值，因为动画必须始终具有已定义的有限的长度-否则，动画将不知道如何其目标值之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="47835-108">An animation's duration must always be a time value, because an animation must always have a defined, finite length—otherwise, the animation would not know how to transition between its target values.</span></span> <span data-ttu-id="47835-109">容器时间线 (<xref:System.Windows.Media.Animation.TimelineGroup>对象)，如<xref:System.Windows.Media.Animation.Storyboard>和<xref:System.Windows.Media.Animation.ParallelTimeline>，默认持续时间为<xref:System.Windows.Duration.Automatic%2A>，这意味着它们将自动结束时其最后一个子级停止播放。</span><span class="sxs-lookup"><span data-stu-id="47835-109">Container timelines (<xref:System.Windows.Media.Animation.TimelineGroup> objects), such as <xref:System.Windows.Media.Animation.Storyboard> and <xref:System.Windows.Media.Animation.ParallelTimeline>, have a default duration of <xref:System.Windows.Duration.Automatic%2A>, which means they automatically end when their last child stops playing.</span></span>  
  
 <span data-ttu-id="47835-110">中的以下示例、 宽度、 高度和填充颜色<xref:System.Windows.Shapes.Rectangle>进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="47835-110">In the following example, the width, height and fill color of a <xref:System.Windows.Shapes.Rectangle> is animated.</span></span> <span data-ttu-id="47835-111">导致包括控制动画的感觉的速度和重写的子时间线容器时间线的持续时间的持续时间的动画效果的动画和容器时间线上设置的持续时间。</span><span class="sxs-lookup"><span data-stu-id="47835-111">Durations are set on animation and container timelines resulting in animation effects including controlling the perceived speed of an animation and overriding the duration of child timelines with the duration of a container timeline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47835-112">示例</span><span class="sxs-lookup"><span data-stu-id="47835-112">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#DurationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="47835-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="47835-113">See Also</span></span>  
 <xref:System.Windows.Duration>  
 [<span data-ttu-id="47835-114">动画概述</span><span class="sxs-lookup"><span data-stu-id="47835-114">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
