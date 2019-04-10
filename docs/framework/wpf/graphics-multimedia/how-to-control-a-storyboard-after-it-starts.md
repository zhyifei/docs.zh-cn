---
title: 如何：演示图板启动后对其进行控制
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
ms.openlocfilehash: 107391386dfbb718f9436d9a039b08439fbc3279
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59161481"
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="a0405-102">如何：演示图板启动后对其进行控制</span><span class="sxs-lookup"><span data-stu-id="a0405-102">How to: Control a Storyboard After It Starts</span></span>
<span data-ttu-id="a0405-103">此示例演示如何使用代码添加到控件<xref:System.Windows.Media.Animation.Storyboard>已开始后。</span><span class="sxs-lookup"><span data-stu-id="a0405-103">This example shows how to use code to control a <xref:System.Windows.Media.Animation.Storyboard> after it has started.</span></span> <span data-ttu-id="a0405-104">若要控制在情节提要[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，使用<xref:System.Windows.Trigger>并<xref:System.Windows.TriggerAction>对象; 有关示例，请参阅[使用事件触发器来控制情节提要启动之后](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)。</span><span class="sxs-lookup"><span data-stu-id="a0405-104">To control a storyboard in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Trigger> and <xref:System.Windows.TriggerAction> objects; for an example, see [Use Event Triggers to Control a Storyboard After It Starts](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
 <span data-ttu-id="a0405-105">若要启动情节提要，你可以使用其<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>方法，将分发到的属性，它们进行动画处理，然后启动情节提要的情节提要的动画。</span><span class="sxs-lookup"><span data-stu-id="a0405-105">To start a storyboard, you use its <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method, which distributes the storyboard's animations to the properties they animate and starts the storyboard.</span></span>  
  
 <span data-ttu-id="a0405-106">若要使可控制演示图板，应使用<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>方法并指定**true**第二个参数。</span><span class="sxs-lookup"><span data-stu-id="a0405-106">To make a storyboard controllable, you use the <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method and specify **true** as the second parameter.</span></span> <span data-ttu-id="a0405-107">然后可以使用情节提要的交互式方法来暂停、 恢复、 查找、 停止、 加快，或降低情节提要，或转到其填充期。</span><span class="sxs-lookup"><span data-stu-id="a0405-107">You can then use the storyboard's interactive methods to pause, resume, seek, stop, speed up, or slow down the storyboard, or advance it to its fill period.</span></span> <span data-ttu-id="a0405-108">下面是演示图板的交互式方法的列表：</span><span class="sxs-lookup"><span data-stu-id="a0405-108">The following is a list of the storyboard's interactive methods:</span></span>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Pause%2A><span data-ttu-id="a0405-109">:暂停情节提要。</span><span class="sxs-lookup"><span data-stu-id="a0405-109">: Pauses the storyboard.</span></span>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Resume%2A><span data-ttu-id="a0405-110">:恢复暂停的情节提要。</span><span class="sxs-lookup"><span data-stu-id="a0405-110">: Resumes a paused storyboard.</span></span>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A><span data-ttu-id="a0405-111">:设置情节提要的交互速度。</span><span class="sxs-lookup"><span data-stu-id="a0405-111">: Sets the storyboard's interactive speed.</span></span>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Seek%2A><span data-ttu-id="a0405-112">:查找情节提要的指定位置。</span><span class="sxs-lookup"><span data-stu-id="a0405-112">: Seeks the storyboard the specified location.</span></span>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A><span data-ttu-id="a0405-113">:查找到指定位置的情节提要。</span><span class="sxs-lookup"><span data-stu-id="a0405-113">: Seeks the storyboard to the specified location.</span></span> <span data-ttu-id="a0405-114">与不同<xref:System.Windows.Media.Animation.Storyboard.Seek%2A>在下一时钟周期之前处理方法，此操作。</span><span class="sxs-lookup"><span data-stu-id="a0405-114">Unlike the <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> method, this operation is processed before the next tick.</span></span>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A><span data-ttu-id="a0405-115">:如果有，请转到其填充期，情节提要。</span><span class="sxs-lookup"><span data-stu-id="a0405-115">: Advances the storyboard to its fill period, if it has one.</span></span>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Stop%2A><span data-ttu-id="a0405-116">:停止情节提要。</span><span class="sxs-lookup"><span data-stu-id="a0405-116">: Stops the storyboard.</span></span>  
  
 <span data-ttu-id="a0405-117">在以下示例中，多个情节提要方法用于以交互方式控制情节提要。</span><span class="sxs-lookup"><span data-stu-id="a0405-117">In the following example, several storyboard methods are used to interactively control a storyboard.</span></span>  
  
 <span data-ttu-id="a0405-118">**注意：** 若要控制使用触发器和情节提要的示例，请参阅[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，请参阅[使用事件触发器来控制情节提要启动之后](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)。</span><span class="sxs-lookup"><span data-stu-id="a0405-118">**Note:** To see an example of controlling a storyboard using triggers with [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], see [Use Event Triggers to Control a Storyboard After It Starts](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0405-119">示例</span><span class="sxs-lookup"><span data-stu-id="a0405-119">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
 [!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="a0405-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0405-120">See also</span></span>

- [<span data-ttu-id="a0405-121">在情节提要启动之后使用事件触发器来控制情节提要</span><span class="sxs-lookup"><span data-stu-id="a0405-121">Use Event Triggers to Control a Storyboard After It Starts</span></span>](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
