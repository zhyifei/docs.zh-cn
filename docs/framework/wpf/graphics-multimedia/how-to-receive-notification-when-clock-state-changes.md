---
title: 如何：在时钟状态发生变化时接收通知
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clocks [WPF], notification of state changes
- notifications [WPF], clocks' state changes
ms.assetid: ecb10fc9-d0c2-45c3-b0a1-7b11baa733da
ms.openlocfilehash: 116647b6b7df9c012ee7d5f08abd760b7f310f71
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277103"
---
# <a name="how-to-receive-notification-when-a-clocks-state-changes"></a><span data-ttu-id="3f905-102">如何：在时钟状态发生变化时接收通知</span><span class="sxs-lookup"><span data-stu-id="3f905-102">How to: Receive Notification When a Clock's State Changes</span></span>
<span data-ttu-id="3f905-103">在时钟<xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated>事件发生时其<xref:System.Windows.Media.Animation.Clock.CurrentState%2A>变为无效，如当时钟启动或停止。</span><span class="sxs-lookup"><span data-stu-id="3f905-103">A clock's <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> event occurs when its <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> becomes invalid, such as when the clock starts or stops.</span></span> <span data-ttu-id="3f905-104">可以直接使用此事件注册<xref:System.Windows.Media.Animation.Clock>，也可以注册使用<xref:System.Windows.Media.Animation.Timeline>。</span><span class="sxs-lookup"><span data-stu-id="3f905-104">You can register for this event with directly using a <xref:System.Windows.Media.Animation.Clock>, or you can register using a <xref:System.Windows.Media.Animation.Timeline>.</span></span>  
  
 <span data-ttu-id="3f905-105">在以下示例中，<xref:System.Windows.Media.Animation.Storyboard>和两个<xref:System.Windows.Media.Animation.DoubleAnimation>对象用于对两个矩形的宽度进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="3f905-105">In the following example, a <xref:System.Windows.Media.Animation.Storyboard> and two <xref:System.Windows.Media.Animation.DoubleAnimation> objects are used to animate the width of two rectangles.</span></span> <span data-ttu-id="3f905-106"><xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>事件用于侦听的时钟状态更改。</span><span class="sxs-lookup"><span data-stu-id="3f905-106">The <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event is used to listen for clock state changes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f905-107">示例</span><span class="sxs-lookup"><span data-stu-id="3f905-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#_graphicsmm_StateExampleMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml#_graphicsmm_stateexamplemarkupwholepage)]  
  
 [!code-csharp[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml.cs#_graphicsmm_stateeventhandlers)]
 [!code-vb[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/stateexample.xaml.vb#_graphicsmm_stateeventhandlers)]  
  
 <span data-ttu-id="3f905-108">下图显示了输入作为父时间线的动画的不同状态 (*情节提要*) 的进展。</span><span class="sxs-lookup"><span data-stu-id="3f905-108">The following illustration shows the different states the animations enter as the parent timeline (*Storyboard*) progresses.</span></span>  
  
 <span data-ttu-id="3f905-109">![具有两个动画的演示图板的时钟状态](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-3timelines.png "graphicsmm_3timelines")</span><span class="sxs-lookup"><span data-stu-id="3f905-109">![Clock states for a Storyboard with two animations](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-3timelines.png "graphicsmm_3timelines")</span></span>  
  
 <span data-ttu-id="3f905-110">下表显示的时间*Animation1*的<xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>触发事件：</span><span class="sxs-lookup"><span data-stu-id="3f905-110">The following table shows the times at which *Animation1*'s <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires:</span></span>  
  
||||||||  
|-|-|-|-|-|-|-|  
|<span data-ttu-id="3f905-111">时间 （秒）</span><span class="sxs-lookup"><span data-stu-id="3f905-111">Time (Seconds)</span></span>|<span data-ttu-id="3f905-112">1</span><span class="sxs-lookup"><span data-stu-id="3f905-112">1</span></span>|<span data-ttu-id="3f905-113">10</span><span class="sxs-lookup"><span data-stu-id="3f905-113">10</span></span>|<span data-ttu-id="3f905-114">19</span><span class="sxs-lookup"><span data-stu-id="3f905-114">19</span></span>|<span data-ttu-id="3f905-115">21</span><span class="sxs-lookup"><span data-stu-id="3f905-115">21</span></span>|<span data-ttu-id="3f905-116">30</span><span class="sxs-lookup"><span data-stu-id="3f905-116">30</span></span>|<span data-ttu-id="3f905-117">39</span><span class="sxs-lookup"><span data-stu-id="3f905-117">39</span></span>|  
|<span data-ttu-id="3f905-118">状态</span><span class="sxs-lookup"><span data-stu-id="3f905-118">State</span></span>|<span data-ttu-id="3f905-119">活动的</span><span class="sxs-lookup"><span data-stu-id="3f905-119">Active</span></span>|<span data-ttu-id="3f905-120">活动的</span><span class="sxs-lookup"><span data-stu-id="3f905-120">Active</span></span>|<span data-ttu-id="3f905-121">已停止</span><span class="sxs-lookup"><span data-stu-id="3f905-121">Stopped</span></span>|<span data-ttu-id="3f905-122">活动的</span><span class="sxs-lookup"><span data-stu-id="3f905-122">Active</span></span>|<span data-ttu-id="3f905-123">活动的</span><span class="sxs-lookup"><span data-stu-id="3f905-123">Active</span></span>|<span data-ttu-id="3f905-124">已停止</span><span class="sxs-lookup"><span data-stu-id="3f905-124">Stopped</span></span>|  
  
 <span data-ttu-id="3f905-125">下表显示的时间*Animation2*的<xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>触发事件：</span><span class="sxs-lookup"><span data-stu-id="3f905-125">The following table shows the times at which *Animation2*'s <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires:</span></span>  
  
||||||||||  
|-|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="3f905-126">时间 （秒）</span><span class="sxs-lookup"><span data-stu-id="3f905-126">Time (Seconds)</span></span>|<span data-ttu-id="3f905-127">1</span><span class="sxs-lookup"><span data-stu-id="3f905-127">1</span></span>|<span data-ttu-id="3f905-128">9</span><span class="sxs-lookup"><span data-stu-id="3f905-128">9</span></span>|<span data-ttu-id="3f905-129">11</span><span class="sxs-lookup"><span data-stu-id="3f905-129">11</span></span>|<span data-ttu-id="3f905-130">19</span><span class="sxs-lookup"><span data-stu-id="3f905-130">19</span></span>|<span data-ttu-id="3f905-131">21</span><span class="sxs-lookup"><span data-stu-id="3f905-131">21</span></span>|<span data-ttu-id="3f905-132">29</span><span class="sxs-lookup"><span data-stu-id="3f905-132">29</span></span>|<span data-ttu-id="3f905-133">31</span><span class="sxs-lookup"><span data-stu-id="3f905-133">31</span></span>|<span data-ttu-id="3f905-134">39</span><span class="sxs-lookup"><span data-stu-id="3f905-134">39</span></span>|  
|<span data-ttu-id="3f905-135">状态</span><span class="sxs-lookup"><span data-stu-id="3f905-135">State</span></span>|<span data-ttu-id="3f905-136">活动的</span><span class="sxs-lookup"><span data-stu-id="3f905-136">Active</span></span>|<span data-ttu-id="3f905-137">填充</span><span class="sxs-lookup"><span data-stu-id="3f905-137">Filling</span></span>|<span data-ttu-id="3f905-138">活动的</span><span class="sxs-lookup"><span data-stu-id="3f905-138">Active</span></span>|<span data-ttu-id="3f905-139">已停止</span><span class="sxs-lookup"><span data-stu-id="3f905-139">Stopped</span></span>|<span data-ttu-id="3f905-140">活动的</span><span class="sxs-lookup"><span data-stu-id="3f905-140">Active</span></span>|<span data-ttu-id="3f905-141">填充</span><span class="sxs-lookup"><span data-stu-id="3f905-141">Filling</span></span>|<span data-ttu-id="3f905-142">活动的</span><span class="sxs-lookup"><span data-stu-id="3f905-142">Active</span></span>|<span data-ttu-id="3f905-143">已停止</span><span class="sxs-lookup"><span data-stu-id="3f905-143">Stopped</span></span>|  
  
 <span data-ttu-id="3f905-144">请注意， *Animation1*的<xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>在 10 秒，激发的事件，即使其状态保持<xref:System.Windows.Media.Animation.ClockState.Active>。</span><span class="sxs-lookup"><span data-stu-id="3f905-144">Notice that *Animation1*'s  <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires at 10 seconds, even though its state remains <xref:System.Windows.Media.Animation.ClockState.Active>.</span></span> <span data-ttu-id="3f905-145">这是因为其状态更改为 10 秒钟，但它从更改<xref:System.Windows.Media.Animation.ClockState.Active>到<xref:System.Windows.Media.Animation.ClockState.Filling>，然后返回<xref:System.Windows.Media.Animation.ClockState.Active>中相同的刻度线。</span><span class="sxs-lookup"><span data-stu-id="3f905-145">That's because its state changed at 10 seconds, but it changed from <xref:System.Windows.Media.Animation.ClockState.Active> to <xref:System.Windows.Media.Animation.ClockState.Filling> and then back to <xref:System.Windows.Media.Animation.ClockState.Active> in the same tick.</span></span>
