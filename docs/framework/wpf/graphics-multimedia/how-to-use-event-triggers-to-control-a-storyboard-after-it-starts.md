---
title: 如何：在情节提要启动之后使用事件触发器来控制情节提要
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: d444349f8bc9236e1d15f484f35b1326c77e2425
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170646"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="018bd-102">如何：在情节提要启动之后使用事件触发器来控制情节提要</span><span class="sxs-lookup"><span data-stu-id="018bd-102">How to: Use Event Triggers to Control a Storyboard After It Starts</span></span>
<span data-ttu-id="018bd-103">此示例演示如何控制<xref:System.Windows.Media.Animation.Storyboard>启动后对它。</span><span class="sxs-lookup"><span data-stu-id="018bd-103">This example shows how to control a <xref:System.Windows.Media.Animation.Storyboard> after it starts.</span></span> <span data-ttu-id="018bd-104">若要启动<xref:System.Windows.Media.Animation.Storyboard>通过使用[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，使用<xref:System.Windows.Media.Animation.BeginStoryboard>，这样可以将分发到的对象和属性，它们进行动画处理，然后启动情节提要的动画。</span><span class="sxs-lookup"><span data-stu-id="018bd-104">To start a <xref:System.Windows.Media.Animation.Storyboard> by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Media.Animation.BeginStoryboard>, which distributes the animations to the objects and properties they animate and then starts the storyboard.</span></span> <span data-ttu-id="018bd-105">如果您为提供<xref:System.Windows.Media.Animation.BeginStoryboard>通过指定的名称及其<xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A>属性，您使它可控制情节提要。</span><span class="sxs-lookup"><span data-stu-id="018bd-105">If you give <xref:System.Windows.Media.Animation.BeginStoryboard> a name by specifying its <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> property, you make it a controllable storyboard.</span></span> <span data-ttu-id="018bd-106">然后您可以以交互方式控制情节提要启动后。</span><span class="sxs-lookup"><span data-stu-id="018bd-106">You can then interactively control the storyboard after it starts.</span></span>  
  
 <span data-ttu-id="018bd-107">使用以下情节提要操作一起使用<xref:System.Windows.EventTrigger>对象来控制情节提要。</span><span class="sxs-lookup"><span data-stu-id="018bd-107">Use the following storyboard actions together with <xref:System.Windows.EventTrigger> objects to control a storyboard.</span></span>  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard><span data-ttu-id="018bd-108">:暂停情节提要。</span><span class="sxs-lookup"><span data-stu-id="018bd-108">: Pauses the storyboard.</span></span>  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard><span data-ttu-id="018bd-109">:恢复暂停的情节提要。</span><span class="sxs-lookup"><span data-stu-id="018bd-109">: Resumes a paused storyboard.</span></span>  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio><span data-ttu-id="018bd-110">:更改情节提要速度。</span><span class="sxs-lookup"><span data-stu-id="018bd-110">: Changes the storyboard speed.</span></span>  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill><span data-ttu-id="018bd-111">:如果有，请转到其填充期，末尾情节提要。</span><span class="sxs-lookup"><span data-stu-id="018bd-111">: Advances a storyboard to the end of its fill period, if it has one.</span></span>  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard><span data-ttu-id="018bd-112">:停止情节提要。</span><span class="sxs-lookup"><span data-stu-id="018bd-112">: Stops the storyboard.</span></span>  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard><span data-ttu-id="018bd-113">:删除情节提要，释放资源。</span><span class="sxs-lookup"><span data-stu-id="018bd-113">: Removes the storyboard, freeing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="018bd-114">示例</span><span class="sxs-lookup"><span data-stu-id="018bd-114">Example</span></span>  
 <span data-ttu-id="018bd-115">以下示例使用可控制情节提要操作来以交互方式控制情节提要。</span><span class="sxs-lookup"><span data-stu-id="018bd-115">The following example uses controllable storyboard actions to interactively control a storyboard.</span></span>  
  
 <span data-ttu-id="018bd-116">**注意：** 若要查看通过使用代码来控制情节提要的示例，请参阅[控制演示图板后它启动使用其交互式方法](how-to-control-a-storyboard-after-it-starts.md)。</span><span class="sxs-lookup"><span data-stu-id="018bd-116">**Note:** To see an example of controlling a storyboard by using code, see [Control a Storyboard After It Starts Using Its Interactive Methods](how-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
 [!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 <span data-ttu-id="018bd-117">有关其他示例，请参阅[动画示例库](https://go.microsoft.com/fwlink/?LinkID=159969)。</span><span class="sxs-lookup"><span data-stu-id="018bd-117">For additional examples, see the [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="018bd-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="018bd-118">See also</span></span>

- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [<span data-ttu-id="018bd-119">在情节提要启动后使用其交互式方法对其进行控制</span><span class="sxs-lookup"><span data-stu-id="018bd-119">Control a Storyboard After It Starts Using Its Interactive Methods</span></span>](how-to-control-a-storyboard-after-it-starts.md)
- [<span data-ttu-id="018bd-120">动画概述</span><span class="sxs-lookup"><span data-stu-id="018bd-120">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="018bd-121">演示图板概述</span><span class="sxs-lookup"><span data-stu-id="018bd-121">Storyboards Overview</span></span>](storyboards-overview.md)
