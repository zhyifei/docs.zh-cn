---
title: 如何：设置动画的持续时间
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], duration
- Timelines [WPF], description
- duration of animations [WPF]
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
ms.openlocfilehash: bdae1689ffeb8c54d756b9debbd26d57a052892d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198785"
---
# <a name="how-to-set-a-duration-for-an-animation"></a><span data-ttu-id="22f93-102">如何：设置动画的持续时间</span><span class="sxs-lookup"><span data-stu-id="22f93-102">How to: Set a Duration for an Animation</span></span>
<span data-ttu-id="22f93-103">一个<xref:System.Windows.Media.Animation.Timeline>表示一个时间段和段的长度由时间线的<xref:System.Windows.Duration>。</span><span class="sxs-lookup"><span data-stu-id="22f93-103">A <xref:System.Windows.Media.Animation.Timeline> represents a segment of time and the length of that segment is determined by the timeline's <xref:System.Windows.Duration>.</span></span> <span data-ttu-id="22f93-104">当<xref:System.Windows.Media.Animation.Timeline>到达其持续时间，就会停止播放。</span><span class="sxs-lookup"><span data-stu-id="22f93-104">When a <xref:System.Windows.Media.Animation.Timeline> reaches the end of its duration, it stops playing.</span></span> <span data-ttu-id="22f93-105">如果<xref:System.Windows.Media.Animation.Timeline>具有子时间线，它们也会停止播放。</span><span class="sxs-lookup"><span data-stu-id="22f93-105">If the <xref:System.Windows.Media.Animation.Timeline> has child timelines, they stop playing as well.</span></span> <span data-ttu-id="22f93-106">播放动画时，<xref:System.Windows.Duration>指定动画需要花多长转换从其起始值为终止值。</span><span class="sxs-lookup"><span data-stu-id="22f93-106">In the case of an animation, the <xref:System.Windows.Duration> specifies how long the animation takes to transition from its starting value to its ending value.</span></span>  
  
 <span data-ttu-id="22f93-107">您可以指定<xref:System.Windows.Duration>与特定的有限时间或特殊值<xref:System.Windows.Duration.Automatic%2A>或<xref:System.Windows.Duration.Forever%2A>。</span><span class="sxs-lookup"><span data-stu-id="22f93-107">You can specify a <xref:System.Windows.Duration> with a specific, finite time or the special values <xref:System.Windows.Duration.Automatic%2A> or <xref:System.Windows.Duration.Forever%2A>.</span></span> <span data-ttu-id="22f93-108">动画的持续时间必须始终为时间值，因为动画必须始终具有已定义的有限长度 — 否则，动画将不知道如何在其目标值之间转换。</span><span class="sxs-lookup"><span data-stu-id="22f93-108">An animation's duration must always be a time value, because an animation must always have a defined, finite length—otherwise, the animation would not know how to transition between its target values.</span></span> <span data-ttu-id="22f93-109">容器时间线 (<xref:System.Windows.Media.Animation.TimelineGroup>对象)，如<xref:System.Windows.Media.Animation.Storyboard>并<xref:System.Windows.Media.Animation.ParallelTimeline>，默认持续时间为<xref:System.Windows.Duration.Automatic%2A>，这意味着它们将自动结束其最后一个子级停止播放时。</span><span class="sxs-lookup"><span data-stu-id="22f93-109">Container timelines (<xref:System.Windows.Media.Animation.TimelineGroup> objects), such as <xref:System.Windows.Media.Animation.Storyboard> and <xref:System.Windows.Media.Animation.ParallelTimeline>, have a default duration of <xref:System.Windows.Duration.Automatic%2A>, which means they automatically end when their last child stops playing.</span></span>  
  
 <span data-ttu-id="22f93-110">在下面的示例、 宽度、 高度和填充颜色的<xref:System.Windows.Shapes.Rectangle>进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="22f93-110">In the following example, the width, height and fill color of a <xref:System.Windows.Shapes.Rectangle> is animated.</span></span> <span data-ttu-id="22f93-111">从而导致动画效果，包括控制动画的感知的速度和重写的子时间线与容器时间线的持续时间的持续时间的动画和容器时间线上设置持续时间。</span><span class="sxs-lookup"><span data-stu-id="22f93-111">Durations are set on animation and container timelines resulting in animation effects including controlling the perceived speed of an animation and overriding the duration of child timelines with the duration of a container timeline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22f93-112">示例</span><span class="sxs-lookup"><span data-stu-id="22f93-112">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#DurationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="22f93-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="22f93-113">See also</span></span>

- <xref:System.Windows.Duration>
- [<span data-ttu-id="22f93-114">动画概述</span><span class="sxs-lookup"><span data-stu-id="22f93-114">Animation Overview</span></span>](animation-overview.md)
