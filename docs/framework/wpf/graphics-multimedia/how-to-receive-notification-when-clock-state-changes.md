---
title: "如何： 接收通知时时钟 &#39; s 状态更改"
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
helpviewer_keywords:
- clocks [WPF], notification of state changes
- notifications [WPF], clocks' state changes
ms.assetid: ecb10fc9-d0c2-45c3-b0a1-7b11baa733da
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 396e2c51894ad5ed11f8953bceb1bd36899cfc62
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-receive-notification-when-a-clock39s-state-changes"></a><span data-ttu-id="33cfe-102">如何： 接收通知时时钟 &#39; s 状态更改</span><span class="sxs-lookup"><span data-stu-id="33cfe-102">How to: Receive Notification When a Clock&#39;s State Changes</span></span>
<span data-ttu-id="33cfe-103">时钟的<xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated>事件发生时其<xref:System.Windows.Media.Animation.Clock.CurrentState%2A>将变为无效，如时钟时启动或停止。</span><span class="sxs-lookup"><span data-stu-id="33cfe-103">A clock's <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> event occurs when its <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> becomes invalid, such as when the clock starts or stops.</span></span> <span data-ttu-id="33cfe-104">你可以直接使用此事件注册<xref:System.Windows.Media.Animation.Clock>，或者也可以注册使用<xref:System.Windows.Media.Animation.Timeline>。</span><span class="sxs-lookup"><span data-stu-id="33cfe-104">You can register for this event with directly using a <xref:System.Windows.Media.Animation.Clock>, or you can register using a <xref:System.Windows.Media.Animation.Timeline>.</span></span>  
  
 <span data-ttu-id="33cfe-105">在下面的示例中，<xref:System.Windows.Media.Animation.Storyboard>和两个<xref:System.Windows.Media.Animation.DoubleAnimation>使用对象进行动画处理的两个矩形的宽度。</span><span class="sxs-lookup"><span data-stu-id="33cfe-105">In the following example, a <xref:System.Windows.Media.Animation.Storyboard> and two <xref:System.Windows.Media.Animation.DoubleAnimation> objects are used to animate the width of two rectangles.</span></span> <span data-ttu-id="33cfe-106"><xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>事件用于侦听的时钟状态更改。</span><span class="sxs-lookup"><span data-stu-id="33cfe-106">The <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event is used to listen for clock state changes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33cfe-107">示例</span><span class="sxs-lookup"><span data-stu-id="33cfe-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#_graphicsmm_StateExampleMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml#_graphicsmm_stateexamplemarkupwholepage)]  
  
 [!code-csharp[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml.cs#_graphicsmm_stateeventhandlers)]
 [!code-vb[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/stateexample.xaml.vb#_graphicsmm_stateeventhandlers)]  
  
 <span data-ttu-id="33cfe-108">下图显示的不同状态动画输入作为父时间线 (*情节提要*) 进行。</span><span class="sxs-lookup"><span data-stu-id="33cfe-108">The following illustration shows the different states the animations enter as the parent timeline (*Storyboard*) progresses.</span></span>  
  
 <span data-ttu-id="33cfe-109">![具有两个动画的演示图板的时钟状态](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-3timelines.png "graphicsmm_3timelines")</span><span class="sxs-lookup"><span data-stu-id="33cfe-109">![Clock states for a Storyboard with two animations](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-3timelines.png "graphicsmm_3timelines")</span></span>  
  
 <span data-ttu-id="33cfe-110">下表显示时间从该处*Animation1*的<xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>事件将触发：</span><span class="sxs-lookup"><span data-stu-id="33cfe-110">The following table shows the times at which *Animation1*'s <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires:</span></span>  
  
||||||||  
|-|-|-|-|-|-|-|  
|<span data-ttu-id="33cfe-111">时间 （秒）</span><span class="sxs-lookup"><span data-stu-id="33cfe-111">Time (Seconds)</span></span>|<span data-ttu-id="33cfe-112">1</span><span class="sxs-lookup"><span data-stu-id="33cfe-112">1</span></span>|<span data-ttu-id="33cfe-113">10</span><span class="sxs-lookup"><span data-stu-id="33cfe-113">10</span></span>|<span data-ttu-id="33cfe-114">19</span><span class="sxs-lookup"><span data-stu-id="33cfe-114">19</span></span>|<span data-ttu-id="33cfe-115">21</span><span class="sxs-lookup"><span data-stu-id="33cfe-115">21</span></span>|<span data-ttu-id="33cfe-116">30</span><span class="sxs-lookup"><span data-stu-id="33cfe-116">30</span></span>|<span data-ttu-id="33cfe-117">39</span><span class="sxs-lookup"><span data-stu-id="33cfe-117">39</span></span>|  
|<span data-ttu-id="33cfe-118">状态</span><span class="sxs-lookup"><span data-stu-id="33cfe-118">State</span></span>|<span data-ttu-id="33cfe-119">活动的</span><span class="sxs-lookup"><span data-stu-id="33cfe-119">Active</span></span>|<span data-ttu-id="33cfe-120">活动的</span><span class="sxs-lookup"><span data-stu-id="33cfe-120">Active</span></span>|<span data-ttu-id="33cfe-121">已停止</span><span class="sxs-lookup"><span data-stu-id="33cfe-121">Stopped</span></span>|<span data-ttu-id="33cfe-122">活动的</span><span class="sxs-lookup"><span data-stu-id="33cfe-122">Active</span></span>|<span data-ttu-id="33cfe-123">活动的</span><span class="sxs-lookup"><span data-stu-id="33cfe-123">Active</span></span>|<span data-ttu-id="33cfe-124">已停止</span><span class="sxs-lookup"><span data-stu-id="33cfe-124">Stopped</span></span>|  
  
 <span data-ttu-id="33cfe-125">下表显示时间从该处*Animation2*的<xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>事件将触发：</span><span class="sxs-lookup"><span data-stu-id="33cfe-125">The following table shows the times at which *Animation2*'s <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires:</span></span>  
  
||||||||||  
|-|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="33cfe-126">时间 （秒）</span><span class="sxs-lookup"><span data-stu-id="33cfe-126">Time (Seconds)</span></span>|<span data-ttu-id="33cfe-127">1</span><span class="sxs-lookup"><span data-stu-id="33cfe-127">1</span></span>|<span data-ttu-id="33cfe-128">9</span><span class="sxs-lookup"><span data-stu-id="33cfe-128">9</span></span>|<span data-ttu-id="33cfe-129">11</span><span class="sxs-lookup"><span data-stu-id="33cfe-129">11</span></span>|<span data-ttu-id="33cfe-130">19</span><span class="sxs-lookup"><span data-stu-id="33cfe-130">19</span></span>|<span data-ttu-id="33cfe-131">21</span><span class="sxs-lookup"><span data-stu-id="33cfe-131">21</span></span>|<span data-ttu-id="33cfe-132">29</span><span class="sxs-lookup"><span data-stu-id="33cfe-132">29</span></span>|<span data-ttu-id="33cfe-133">31</span><span class="sxs-lookup"><span data-stu-id="33cfe-133">31</span></span>|<span data-ttu-id="33cfe-134">39</span><span class="sxs-lookup"><span data-stu-id="33cfe-134">39</span></span>|  
|<span data-ttu-id="33cfe-135">状态</span><span class="sxs-lookup"><span data-stu-id="33cfe-135">State</span></span>|<span data-ttu-id="33cfe-136">活动的</span><span class="sxs-lookup"><span data-stu-id="33cfe-136">Active</span></span>|<span data-ttu-id="33cfe-137">填充</span><span class="sxs-lookup"><span data-stu-id="33cfe-137">Filling</span></span>|<span data-ttu-id="33cfe-138">活动的</span><span class="sxs-lookup"><span data-stu-id="33cfe-138">Active</span></span>|<span data-ttu-id="33cfe-139">已停止</span><span class="sxs-lookup"><span data-stu-id="33cfe-139">Stopped</span></span>|<span data-ttu-id="33cfe-140">活动的</span><span class="sxs-lookup"><span data-stu-id="33cfe-140">Active</span></span>|<span data-ttu-id="33cfe-141">填充</span><span class="sxs-lookup"><span data-stu-id="33cfe-141">Filling</span></span>|<span data-ttu-id="33cfe-142">活动的</span><span class="sxs-lookup"><span data-stu-id="33cfe-142">Active</span></span>|<span data-ttu-id="33cfe-143">已停止</span><span class="sxs-lookup"><span data-stu-id="33cfe-143">Stopped</span></span>|  
  
 <span data-ttu-id="33cfe-144">请注意， *Animation1*的<xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>在 10 秒，将激发的事件，即使其状态保持<xref:System.Windows.Media.Animation.ClockState.Active>。</span><span class="sxs-lookup"><span data-stu-id="33cfe-144">Notice that *Animation1*'s  <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires at 10 seconds, even though its state remains <xref:System.Windows.Media.Animation.ClockState.Active>.</span></span> <span data-ttu-id="33cfe-145">这是因为在 10 秒，更改其状态，但它从更改<xref:System.Windows.Media.Animation.ClockState.Active>到<xref:System.Windows.Media.Animation.ClockState.Filling>和再转回<xref:System.Windows.Media.Animation.ClockState.Active>中相同的刻度。</span><span class="sxs-lookup"><span data-stu-id="33cfe-145">That's because its state changed at 10 seconds, but it changed from <xref:System.Windows.Media.Animation.ClockState.Active> to <xref:System.Windows.Media.Animation.ClockState.Filling> and then back to <xref:System.Windows.Media.Animation.ClockState.Active> in the same tick.</span></span>
