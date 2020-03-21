---
title: 如何：在演示图板启动之后使用事件触发器来控制演示图板
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: 518f5d7ea0b5dc00677489f1383814563c565145
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186706"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="41e0c-102">如何：在演示图板启动之后使用事件触发器来控制演示图板</span><span class="sxs-lookup"><span data-stu-id="41e0c-102">How to: Use Event Triggers to Control a Storyboard After It Starts</span></span>

<span data-ttu-id="41e0c-103">此示例演示如何在 启动后控制<xref:System.Windows.Media.Animation.Storyboard>。</span><span class="sxs-lookup"><span data-stu-id="41e0c-103">This example shows how to control a <xref:System.Windows.Media.Animation.Storyboard> after it starts.</span></span> <span data-ttu-id="41e0c-104">要使用<xref:System.Windows.Media.Animation.Storyboard>[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]开始 ，<xref:System.Windows.Media.Animation.BeginStoryboard>使用 ， 将动画分发到它们为对象和属性设置动画，然后启动情节提要。</span><span class="sxs-lookup"><span data-stu-id="41e0c-104">To start a <xref:System.Windows.Media.Animation.Storyboard> by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Media.Animation.BeginStoryboard>, which distributes the animations to the objects and properties they animate and then starts the storyboard.</span></span> <span data-ttu-id="41e0c-105">如果通过指定<xref:System.Windows.Media.Animation.BeginStoryboard>名称<xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A>的属性来命名，则可以将其制作为可控制的情节提要。</span><span class="sxs-lookup"><span data-stu-id="41e0c-105">If you give <xref:System.Windows.Media.Animation.BeginStoryboard> a name by specifying its <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> property, you make it a controllable storyboard.</span></span> <span data-ttu-id="41e0c-106">然后，您可以在情节提要启动后以交互方式控制它。</span><span class="sxs-lookup"><span data-stu-id="41e0c-106">You can then interactively control the storyboard after it starts.</span></span>

<span data-ttu-id="41e0c-107">将以下情节提要操作与<xref:System.Windows.EventTrigger>对象一起使用来控制情节提要。</span><span class="sxs-lookup"><span data-stu-id="41e0c-107">Use the following storyboard actions together with <xref:System.Windows.EventTrigger> objects to control a storyboard.</span></span>

- <span data-ttu-id="41e0c-108"><xref:System.Windows.Media.Animation.PauseStoryboard>：暂停情节提要。</span><span class="sxs-lookup"><span data-stu-id="41e0c-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Pauses the storyboard.</span></span>

- <span data-ttu-id="41e0c-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>：恢复暂停的情节提要。</span><span class="sxs-lookup"><span data-stu-id="41e0c-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Resumes a paused storyboard.</span></span>

- <span data-ttu-id="41e0c-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>：更改情节提要速度。</span><span class="sxs-lookup"><span data-stu-id="41e0c-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Changes the storyboard speed.</span></span>

- <span data-ttu-id="41e0c-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>：将情节提要提前到填充期结束时（如果有）。</span><span class="sxs-lookup"><span data-stu-id="41e0c-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Advances a storyboard to the end of its fill period, if it has one.</span></span>

- <span data-ttu-id="41e0c-112"><xref:System.Windows.Media.Animation.StopStoryboard>：停止情节提要。</span><span class="sxs-lookup"><span data-stu-id="41e0c-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Stops the storyboard.</span></span>

- <span data-ttu-id="41e0c-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>：删除情节提要，释放资源。</span><span class="sxs-lookup"><span data-stu-id="41e0c-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Removes the storyboard, freeing resources.</span></span>

## <a name="example"></a><span data-ttu-id="41e0c-114">示例</span><span class="sxs-lookup"><span data-stu-id="41e0c-114">Example</span></span>

<span data-ttu-id="41e0c-115">下面的示例使用可控的情节提要操作来交互控制情节提要。</span><span class="sxs-lookup"><span data-stu-id="41e0c-115">The following example uses controllable storyboard actions to interactively control a storyboard.</span></span>

> [!NOTE]
> <span data-ttu-id="41e0c-116">要查看使用代码控制情节提要的示例，请参阅[在情节提要开始使用其交互方法后对其进行控制](how-to-control-a-storyboard-after-it-starts.md)。</span><span class="sxs-lookup"><span data-stu-id="41e0c-116">To see an example of controlling a storyboard by using code, see [Control a Storyboard After It Starts Using Its Interactive Methods](how-to-control-a-storyboard-after-it-starts.md).</span></span>

[!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]

<span data-ttu-id="41e0c-117">有关其他示例，请参阅[动画示例库](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples)。</span><span class="sxs-lookup"><span data-stu-id="41e0c-117">For additional examples, see the [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>

## <a name="see-also"></a><span data-ttu-id="41e0c-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41e0c-118">See also</span></span>

- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [<span data-ttu-id="41e0c-119">在情节提要启动后使用其交互式方法对其进行控制</span><span class="sxs-lookup"><span data-stu-id="41e0c-119">Control a Storyboard After It Starts Using Its Interactive Methods</span></span>](how-to-control-a-storyboard-after-it-starts.md)
- [<span data-ttu-id="41e0c-120">动画概述</span><span class="sxs-lookup"><span data-stu-id="41e0c-120">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="41e0c-121">演示图板概述</span><span class="sxs-lookup"><span data-stu-id="41e0c-121">Storyboards Overview</span></span>](storyboards-overview.md)
