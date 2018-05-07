---
title: 计时事件概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- timelines [WPF]
- timing events [WPF]
ms.assetid: 597e3280-0867-4359-a97b-5b2f4149e350
ms.openlocfilehash: a48d1621e5568d556a1177578cc662813d70a283
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="timing-events-overview"></a>计时事件概述
本主题介绍如何使用可在上找到的五个计时事件<xref:System.Windows.Media.Animation.Timeline>和<xref:System.Windows.Media.Animation.Clock>对象。  
  
## <a name="prerequisites"></a>系统必备  
 若要了解本主题，应了解如何创建和使用动画。 若要开始使用动画，请参阅[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)。  
  
 有多种方法中的属性进行动画处理[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
-   **使用情节提要对象**（标记和代码）： 你可以使用<xref:System.Windows.Media.Animation.Storyboard>对象以排列，并将分发到一个或多个对象的动画。 有关示例，请参阅[使用情节提要属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)。  
  
-   **使用本地动画**（仅代码）： 你可以将应用<xref:System.Windows.Media.Animation.AnimationTimeline>对象直接与它们进行动画处理的属性。 有关示例，请参阅[在不使用情节提要的情况下对属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)。  
  
-   **使用时钟**（仅代码）：可以显式管理时钟创建并自行分发动画时钟。  有关示例，请参阅[使用 AnimationClock 属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-an-animationclock.md)。  
  
 因为你可以将其用于标记和代码，此概述中的示例使用<xref:System.Windows.Media.Animation.Storyboard>对象。 但是，所介绍的概念适用于其他对属性进行动画处理的方法。  
  
### <a name="what-is-a-clock"></a>是什么时钟？  
 除了描述时间段外，时间线本身并无其他任何作用。 它是时间线的<xref:System.Windows.Media.Animation.Clock>对象，不能实际工作： 它维护与计时相关时间线的运行时状态。 在大多数情况下，比如使用情节提要时，会自动为时间线创建时钟。 你还可以创建<xref:System.Windows.Media.Animation.Clock>通过使用显式<xref:System.Windows.Media.Animation.Timeline.CreateClock%2A>方法。 有关详细信息<xref:System.Windows.Media.Animation.Clock>对象，请参阅[动画和计时系统概述](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)。  
  
## <a name="why-use-events"></a>为什么使用事件？  
 除了一个例外（对齐到上一时钟周期的查找操作），所有交互式计时操作均为异步操作。 无法准确知道它们何时执行。 当存在其他代码依赖于计时操作时，可能会产生问题。 假设你希望停止对矩形进行动画处理的时间线。 在时间线停止后，更改矩形的颜色。  
  
 [!code-csharp[events_procedural#NeedForEventsFragment](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#needforeventsfragment)]
 [!code-vb[events_procedural#NeedForEventsFragment](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#needforeventsfragment)]  
  
 在上一示例中，第二行代码可能会在情节提要停止前执行。 这是因为停止操作是异步操作。 告知时间线或时钟停止将创建各种“停止请求”，但它仅在计时引擎的下一时钟周期才会处理。  
  
 若要在时间线完成后执行命令，请使用计时事件。 在下面的示例中，事件处理程序用于在情节提要停止播放后更改矩形的颜色。  
  
 [!code-csharp[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#registerforstoryboardcurrentstateinvalidatedevent)]
 [!code-vb[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#registerforstoryboardcurrentstateinvalidatedevent)]  
[!code-csharp[events_procedural#StoryboardCurrentStateInvalidatedEvent2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#storyboardcurrentstateinvalidatedevent2)]
[!code-vb[events_procedural#StoryboardCurrentStateInvalidatedEvent2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#storyboardcurrentstateinvalidatedevent2)]  
  
 有关更完整示例，请参阅[收到通知时时钟的状态更改](../../../../docs/framework/wpf/graphics-multimedia/how-to-receive-notification-when-clock-state-changes.md)。  
  
## <a name="public-events"></a>公共事件  
 <xref:System.Windows.Media.Animation.Timeline>和<xref:System.Windows.Media.Animation.Clock>类都提供五个计时事件。 下表列出了这些事件及其触发条件。  
  
|事件|触发交互式操作|其他触发器|  
|-----------|--------------------------------------|--------------------|  
|**Completed**|跳过以填充|时钟完成。|  
|**CurrentGlobalSpeedInvalidated**|暂停、恢复、查找、设置速度比、跳过以填充、停止|时钟反转、加速、启动或停止。|  
|**CurrentStateInvalidated**|开始、跳过以填充、停止|时钟开始、停止或填充。|  
|**CurrentTimeInvalidated**|开始、查找、跳过以填充、停止|时钟前进。|  
|**RemoveRequested**|删除||  
  
## <a name="ticking-and-event-consolidation"></a>时钟周期和事件合并  
 当您创建动画中的对象[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，它是管理您的动画的计时引擎。 计时引擎跟踪时间进度，并计算每个动画的状态。 它一秒内进行多次计算。 这些计算过程称为“时钟周期”。  
  
 尽管时钟周期频繁发生，但是不同时钟周期之间可能会很多操作。 例如，时间线可能会停止、启动、再次停止，在这种情况下其当前状态将更改三次。 从理论上讲，在一个时钟周期内，可以多次引发事件；但是，计时引擎会合并事件，因此每个事件在每个时钟周期内只能引发一次。  
  
## <a name="registering-for-events"></a>注册事件  
 可以通过两种方法注册计时事件：使用时间线或使用从时间线创建的时钟进行注册。 直接使用时钟注册事件相当简单，不过该方法只能在代码中执行。 可以在标记或代码中使用时间线注册事件。 下一节介绍如何使用时间线注册时钟事件。  
  
<a name="registeringforclockeventswithatimeline"></a>   
## <a name="registering-for-clock-events-with-a-timeline"></a>使用时间线注册时钟事件  
 虽然时间线的<xref:System.Windows.Media.Animation.Timeline.Completed>， <xref:System.Windows.Media.Animation.Timeline.CurrentGlobalSpeedInvalidated>， <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>， <xref:System.Windows.Media.Animation.Timeline.CurrentTimeInvalidated>，和<xref:System.Windows.Media.Animation.Timeline.RemoveRequested>事件显示为与时间线，注册这些事件实际上将关联的事件处理程序替换为关联<xref:System.Windows.Media.Animation.Clock>为时间线创建。  
  
 当你注册<xref:System.Windows.Media.Animation.Timeline.Completed>时间线上的事件，例如，你正在实际相当于告诉系统注册<xref:System.Windows.Media.Animation.Clock.Completed>事件的时间线创建每个时钟。 在代码中，你必须注册此事件之前<xref:System.Windows.Media.Animation.Clock>创建为此时间线; 否则，你不会收到通知。 发生这种情况会自动在[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; 分析器自动注册为事件之前<xref:System.Windows.Media.Animation.Clock>创建。  
  
## <a name="see-also"></a>请参阅  
 [动画和计时系统概述](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)  
 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [计时行为概述](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)
