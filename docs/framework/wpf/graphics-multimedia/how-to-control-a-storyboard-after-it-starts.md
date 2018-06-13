---
title: 如何：在演示图板启动后对其进行控制
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
ms.openlocfilehash: 2407de5029007748de691a3020078b1241b02fd4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561457"
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="750c3-102">如何：在演示图板启动后对其进行控制</span><span class="sxs-lookup"><span data-stu-id="750c3-102">How to: Control a Storyboard After It Starts</span></span>
<span data-ttu-id="750c3-103">此示例演示如何使用代码添加到控件<xref:System.Windows.Media.Animation.Storyboard>它启动后。</span><span class="sxs-lookup"><span data-stu-id="750c3-103">This example shows how to use code to control a <xref:System.Windows.Media.Animation.Storyboard> after it has started.</span></span> <span data-ttu-id="750c3-104">若要控制在情节提要[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，使用<xref:System.Windows.Trigger>和<xref:System.Windows.TriggerAction>对象; 例如，请参阅[使用事件触发器，以控制 a 情节提要后它将开始](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)。</span><span class="sxs-lookup"><span data-stu-id="750c3-104">To control a storyboard in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Trigger> and <xref:System.Windows.TriggerAction> objects; for an example, see [Use Event Triggers to Control a Storyboard After It Starts](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
 <span data-ttu-id="750c3-105">若要启动情节提要，你可以使用其<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>方法，将分发到的属性，它们进行动画处理，并启动情节提要的情节提要的动画。</span><span class="sxs-lookup"><span data-stu-id="750c3-105">To start a storyboard, you use its <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method, which distributes the storyboard's animations to the properties they animate and starts the storyboard.</span></span>  
  
 <span data-ttu-id="750c3-106">若要使情节提要可以控制，你可以使用<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>方法并指定**true**第二个参数。</span><span class="sxs-lookup"><span data-stu-id="750c3-106">To make a storyboard controllable, you use the <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method and specify **true** as the second parameter.</span></span> <span data-ttu-id="750c3-107">然后可以使用情节提要的交互式方法来暂停、 恢复、 查找、 停止、 加快，或速度变慢情节提要，或使它前进到其填充期间。</span><span class="sxs-lookup"><span data-stu-id="750c3-107">You can then use the storyboard's interactive methods to pause, resume, seek, stop, speed up, or slow down the storyboard, or advance it to its fill period.</span></span> <span data-ttu-id="750c3-108">下面是演示图板的交互式方法的列表：</span><span class="sxs-lookup"><span data-stu-id="750c3-108">The following is a list of the storyboard's interactive methods:</span></span>  
  
-   <span data-ttu-id="750c3-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>： 暂停情节提要。</span><span class="sxs-lookup"><span data-stu-id="750c3-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Pauses the storyboard.</span></span>  
  
-   <span data-ttu-id="750c3-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>： 将恢复暂停的情节提要。</span><span class="sxs-lookup"><span data-stu-id="750c3-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Resumes a paused storyboard.</span></span>  
  
-   <span data-ttu-id="750c3-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>： 设置情节提要的交互速度。</span><span class="sxs-lookup"><span data-stu-id="750c3-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Sets the storyboard's interactive speed.</span></span>  
  
-   <span data-ttu-id="750c3-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>： 查找情节提要的指定位置。</span><span class="sxs-lookup"><span data-stu-id="750c3-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Seeks the storyboard the specified location.</span></span>  
  
-   <span data-ttu-id="750c3-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>： 查找情节提要到指定的位置。</span><span class="sxs-lookup"><span data-stu-id="750c3-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Seeks the storyboard to the specified location.</span></span> <span data-ttu-id="750c3-114">与不同<xref:System.Windows.Media.Animation.Storyboard.Seek%2A>在下一个计时周期之前处理方法，此操作。</span><span class="sxs-lookup"><span data-stu-id="750c3-114">Unlike the <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> method, this operation is processed before the next tick.</span></span>  
  
-   <span data-ttu-id="750c3-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>： 如果有的话，请转到其填充期间，情节提要。</span><span class="sxs-lookup"><span data-stu-id="750c3-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Advances the storyboard to its fill period, if it has one.</span></span>  
  
-   <span data-ttu-id="750c3-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>： 停止情节提要。</span><span class="sxs-lookup"><span data-stu-id="750c3-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Stops the storyboard.</span></span>  
  
 <span data-ttu-id="750c3-117">在下面的示例中，几种情节提要方法用于以交互方式控制情节提要。</span><span class="sxs-lookup"><span data-stu-id="750c3-117">In the following example, several storyboard methods are used to interactively control a storyboard.</span></span>  
  
 <span data-ttu-id="750c3-118">**注意：** 若要查看的控制使用具有触发器情节提要示例[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，请参阅[使用事件触发器，以控制 a 情节提要后它将开始](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)。</span><span class="sxs-lookup"><span data-stu-id="750c3-118">**Note:** To see an example of controlling a storyboard using triggers with [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], see [Use Event Triggers to Control a Storyboard After It Starts](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="750c3-119">示例</span><span class="sxs-lookup"><span data-stu-id="750c3-119">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
 [!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="750c3-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="750c3-120">See Also</span></span>  
 [<span data-ttu-id="750c3-121">在情节提要启动之后使用事件触发器来控制情节提要</span><span class="sxs-lookup"><span data-stu-id="750c3-121">Use Event Triggers to Control a Storyboard After It Starts</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
