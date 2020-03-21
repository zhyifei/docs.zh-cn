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
ms.openlocfilehash: ee45441e9ad09c60d8b61ecce4ef08b0027ce29e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145405"
---
# <a name="timing-events-overview"></a>计时事件概述
本主题介绍如何使用 on 和<xref:System.Windows.Media.Animation.Timeline><xref:System.Windows.Media.Animation.Clock>对象上可用的五个计时事件。  
  
## <a name="prerequisites"></a>系统必备  
 若要了解本主题，应了解如何创建和使用动画。 要开始使用动画，请参阅[动画概述](animation-overview.md)。  
  
 有多种方法可以对 属性进行[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]动画处理：  
  
- **使用情节提要对象**（标记和代码）：您可以使用<xref:System.Windows.Media.Animation.Storyboard>对象将动画排列到一个或多个对象。 例如，请参阅[使用情节提要为属性设置动画](how-to-animate-a-property-by-using-a-storyboard.md)。  
  
- **使用局部动画**（仅限代码）：可以直接将对象应用于<xref:System.Windows.Media.Animation.AnimationTimeline>它们设置动画的属性。 有关示例，请参阅[在不使用情节提要的情况下对属性进行动画处理](how-to-animate-a-property-without-using-a-storyboard.md)。  
  
- **使用时钟**（仅代码）：可以显式管理时钟创建并自行分发动画时钟。  例如，请参阅[使用动画时钟为属性设置动画](how-to-animate-a-property-by-using-an-animationclock.md)。  
  
 由于您可以在标记和代码中使用它们，因此此概述中的示例使用<xref:System.Windows.Media.Animation.Storyboard>对象。 但是，所介绍的概念适用于其他对属性进行动画处理的方法。  
  
### <a name="what-is-a-clock"></a>是什么时钟？  
 除了描述时间段外，时间线本身并无其他任何作用。 是时间线<xref:System.Windows.Media.Animation.Clock>的对象可以执行实际工作：它维护时间线的计时相关运行时状态。 在大多数情况下，比如使用情节提要时，会自动为时间线创建时钟。 还可以通过使用<xref:System.Windows.Media.Animation.Timeline.CreateClock%2A>方法显式<xref:System.Windows.Media.Animation.Clock>创建 。 有关<xref:System.Windows.Media.Animation.Clock>对象的详细信息，请参阅[动画和计时系统概述](animation-and-timing-system-overview.md)。  
  
## <a name="why-use-events"></a>为什么使用事件？  
 除了一个例外（对齐到上一时钟周期的查找操作），所有交互式计时操作均为异步操作。 无法准确知道它们何时执行。 当存在其他代码依赖于计时操作时，可能会产生问题。 假设你希望停止对矩形进行动画处理的时间线。 在时间线停止后，更改矩形的颜色。  
  
 [!code-csharp[events_procedural#NeedForEventsFragment](~/samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#needforeventsfragment)]
 [!code-vb[events_procedural#NeedForEventsFragment](~/samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#needforeventsfragment)]  
  
 在上一示例中，第二行代码可能会在情节提要停止前执行。 这是因为停止操作是异步操作。 告知时间线或时钟停止将创建各种“停止请求”，但它仅在计时引擎的下一时钟周期才会处理。  
  
 若要在时间线完成后执行命令，请使用计时事件。 在下面的示例中，事件处理程序用于在情节提要停止播放后更改矩形的颜色。  
  
 [!code-csharp[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#registerforstoryboardcurrentstateinvalidatedevent)]
 [!code-vb[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#registerforstoryboardcurrentstateinvalidatedevent)]  
[!code-csharp[events_procedural#StoryboardCurrentStateInvalidatedEvent2](~/samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#storyboardcurrentstateinvalidatedevent2)]
[!code-vb[events_procedural#StoryboardCurrentStateInvalidatedEvent2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#storyboardcurrentstateinvalidatedevent2)]  
  
 有关更完整的示例，请参阅[时钟状态更改时接收通知](how-to-receive-notification-when-clock-state-changes.md)。  
  
## <a name="public-events"></a>公共事件  
 <xref:System.Windows.Media.Animation.Timeline>和<xref:System.Windows.Media.Animation.Clock>类都提供五个计时事件。 下表列出了这些事件及其触发条件。  
  
|事件|触发交互式操作|其他触发器|  
|-----------|--------------------------------------|--------------------|  
|**完成**|跳过以填充|时钟完成。|  
|**CurrentGlobalSpeedInvalidated**|暂停、恢复、查找、设置速度比、跳过以填充、停止|时钟反转、加速、启动或停止。|  
|**CurrentStateInvalidated**|开始、跳过以填充、停止|时钟开始、停止或填充。|  
|**CurrentTimeInvalidated**|开始、查找、跳过以填充、停止|时钟前进。|  
|**RemoveRequested**|删除||  
  
## <a name="ticking-and-event-consolidation"></a>时钟周期和事件合并  
 在 中[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]为对象设置动画时，是管理动画的计时引擎。 计时引擎跟踪时间进度，并计算每个动画的状态。 它一秒内进行多次计算。 这些计算过程称为“时钟周期”。  
  
 尽管滴答频率很高，但是在两次滴答之间还是有可能会发生许多事情。 例如，时间线可能会停止、启动、再次停止，在这种情况下其当前状态将更改三次。 从理论上讲，在一个时钟周期内，可以多次引发事件；但是，计时引擎会合并事件，因此每个事件在每个时钟周期内只能引发一次。  
  
## <a name="registering-for-events"></a>注册事件  
 可以通过两种方法注册计时事件：使用时间线或使用从时间线创建的时钟进行注册。 直接使用时钟注册事件相当简单，不过该方法只能在代码中执行。 可以在标记或代码中使用时间线注册事件。 下一节介绍如何使用时间线注册时钟事件。  
  
<a name="registeringforclockeventswithatimeline"></a>
## <a name="registering-for-clock-events-with-a-timeline"></a>使用时间线注册时钟事件  
 尽管时间线<xref:System.Windows.Media.Animation.Timeline.Completed>的 、、<xref:System.Windows.Media.Animation.Timeline.CurrentGlobalSpeedInvalidated><xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated><xref:System.Windows.Media.Animation.Timeline.CurrentTimeInvalidated>和<xref:System.Windows.Media.Animation.Timeline.RemoveRequested>事件似乎与时间线相关联，但为这些事件注册实际上将事件处理程序与为时间线<xref:System.Windows.Media.Animation.Clock>创建的处理程序相关联。  
  
 例如，当您在时间线<xref:System.Windows.Media.Animation.Timeline.Completed>上注册事件时，实际上是在告诉系统注册为时间线创建的每个时钟<xref:System.Windows.Media.Animation.Clock.Completed>的事件。 在代码中，您必须在为此时间线创建 之前<xref:System.Windows.Media.Animation.Clock>注册此事件;因此，您必须为此时间线注册 。否则，您将不会收到通知。 这将在 中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]自动发生。解析器在创建 之前自动注册该<xref:System.Windows.Media.Animation.Clock>事件。  
  
## <a name="see-also"></a>另请参阅

- [动画和计时系统概述](animation-and-timing-system-overview.md)
- [动画概述](animation-overview.md)
- [计时行为概述](timing-behaviors-overview.md)
