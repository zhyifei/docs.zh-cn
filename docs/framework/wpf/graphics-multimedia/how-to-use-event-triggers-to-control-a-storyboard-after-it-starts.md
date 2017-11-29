---
title: "如何：在演示图板启动之后使用事件触发器来控制演示图板"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7d9e096969713cc4b9c42261b238691d51cb49d9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="8b1c9-102">如何：在演示图板启动之后使用事件触发器来控制演示图板</span><span class="sxs-lookup"><span data-stu-id="8b1c9-102">How to: Use Event Triggers to Control a Storyboard After It Starts</span></span>
<span data-ttu-id="8b1c9-103">此示例演示如何控制<xref:System.Windows.Media.Animation.Storyboard>启动后对它。</span><span class="sxs-lookup"><span data-stu-id="8b1c9-103">This example shows how to control a <xref:System.Windows.Media.Animation.Storyboard> after it starts.</span></span> <span data-ttu-id="8b1c9-104">若要启动<xref:System.Windows.Media.Animation.Storyboard>使用[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，使用<xref:System.Windows.Media.Animation.BeginStoryboard>，这样可以将对象和属性，它们进行动画处理，然后启动情节提要的动画。</span><span class="sxs-lookup"><span data-stu-id="8b1c9-104">To start a <xref:System.Windows.Media.Animation.Storyboard> by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Media.Animation.BeginStoryboard>, which distributes the animations to the objects and properties they animate and then starts the storyboard.</span></span> <span data-ttu-id="8b1c9-105">如果你向提供<xref:System.Windows.Media.Animation.BeginStoryboard>通过指定的名称及其<xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A>属性，你可以让它从此情节提要。</span><span class="sxs-lookup"><span data-stu-id="8b1c9-105">If you give <xref:System.Windows.Media.Animation.BeginStoryboard> a name by specifying its <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> property, you make it a controllable storyboard.</span></span> <span data-ttu-id="8b1c9-106">然后，你可以以交互方式控制情节提要在其开始后。</span><span class="sxs-lookup"><span data-stu-id="8b1c9-106">You can then interactively control the storyboard after it starts.</span></span>  
  
 <span data-ttu-id="8b1c9-107">使用下列情节提要操作连同<xref:System.Windows.EventTrigger>对象以控制情节提要。</span><span class="sxs-lookup"><span data-stu-id="8b1c9-107">Use the following storyboard actions together with <xref:System.Windows.EventTrigger> objects to control a storyboard.</span></span>  
  
-   <span data-ttu-id="8b1c9-108"><xref:System.Windows.Media.Animation.PauseStoryboard>： 暂停情节提要。</span><span class="sxs-lookup"><span data-stu-id="8b1c9-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Pauses the storyboard.</span></span>  
  
-   <span data-ttu-id="8b1c9-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>： 将恢复暂停的情节提要。</span><span class="sxs-lookup"><span data-stu-id="8b1c9-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Resumes a paused storyboard.</span></span>  
  
-   <span data-ttu-id="8b1c9-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>： 更改的情节提要速度。</span><span class="sxs-lookup"><span data-stu-id="8b1c9-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Changes the storyboard speed.</span></span>  
  
-   <span data-ttu-id="8b1c9-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>： 如果有的话，请转到其填充期间，末尾情节提要。</span><span class="sxs-lookup"><span data-stu-id="8b1c9-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Advances a storyboard to the end of its fill period, if it has one.</span></span>  
  
-   <span data-ttu-id="8b1c9-112"><xref:System.Windows.Media.Animation.StopStoryboard>： 停止情节提要。</span><span class="sxs-lookup"><span data-stu-id="8b1c9-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Stops the storyboard.</span></span>  
  
-   <span data-ttu-id="8b1c9-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>： 删除的情节提要释放资源。</span><span class="sxs-lookup"><span data-stu-id="8b1c9-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Removes the storyboard, freeing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b1c9-114">示例</span><span class="sxs-lookup"><span data-stu-id="8b1c9-114">Example</span></span>  
 <span data-ttu-id="8b1c9-115">下面的示例使用可控演示图板操作以交互方式控制情节提要。</span><span class="sxs-lookup"><span data-stu-id="8b1c9-115">The following example uses controllable storyboard actions to interactively control a storyboard.</span></span>  
  
 <span data-ttu-id="8b1c9-116">**注意：**若要查看的情节提要控制通过使用代码示例，请参阅[控制情节提要后它启动使用其交互式方法](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md)。</span><span class="sxs-lookup"><span data-stu-id="8b1c9-116">**Note:** To see an example of controlling a storyboard by using code, see [Control a Storyboard After It Starts Using Its Interactive Methods](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
 [!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 <span data-ttu-id="8b1c9-117">有关其他示例，请参阅[动画示例库](http://go.microsoft.com/fwlink/?LinkID=159969)。</span><span class="sxs-lookup"><span data-stu-id="8b1c9-117">For additional examples, see the [Animation Example Gallery](http://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b1c9-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b1c9-118">See Also</span></span>  
 <xref:System.Windows.Media.Animation.ResumeStoryboard>  
 <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>  
 <xref:System.Windows.Media.Animation.SkipStoryboardToFill>  
 <xref:System.Windows.Media.Animation.PauseStoryboard>  
 <xref:System.Windows.Media.Animation.StopStoryboard>  
 <xref:System.Windows.Media.Animation.SeekStoryboard>  
 [<span data-ttu-id="8b1c9-119">在情节提要启动后使用其交互式方法对其进行控制</span><span class="sxs-lookup"><span data-stu-id="8b1c9-119">Control a Storyboard After It Starts Using Its Interactive Methods</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md)  
 [<span data-ttu-id="8b1c9-120">动画概述</span><span class="sxs-lookup"><span data-stu-id="8b1c9-120">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="8b1c9-121">演示图板概述</span><span class="sxs-lookup"><span data-stu-id="8b1c9-121">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
