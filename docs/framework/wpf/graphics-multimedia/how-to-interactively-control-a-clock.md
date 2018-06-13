---
title: 如何：以交互方式控制时钟
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controlling clocks interactively [WPF]
- clocks [WPF], controlling interactively
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
ms.openlocfilehash: 63e72c48afd9b72a6b334ccdc234d08cef7288f0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560219"
---
# <a name="how-to-interactively-control-a-clock"></a><span data-ttu-id="4dfaa-102">如何：以交互方式控制时钟</span><span class="sxs-lookup"><span data-stu-id="4dfaa-102">How to: Interactively Control a Clock</span></span>
<span data-ttu-id="4dfaa-103">A<xref:System.Windows.Media.Animation.Clock>对象的<xref:System.Windows.Media.Animation.ClockController>属性使您能够以交互方式启动、 暂停、 恢复、 查找、 时钟前进到其填充期间，和停止时钟。</span><span class="sxs-lookup"><span data-stu-id="4dfaa-103">A <xref:System.Windows.Media.Animation.Clock> object's <xref:System.Windows.Media.Animation.ClockController> property enables you to interactively start, pause, resume, seek, advance the clock to its fill period, and stop the clock.</span></span> <span data-ttu-id="4dfaa-104">可以以交互方式控制仅计时树的根时钟。</span><span class="sxs-lookup"><span data-stu-id="4dfaa-104">Only the root clock of a timing tree can be interactively controlled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4dfaa-105">以交互方式控件不需要您直接使用时钟的动画的其他方式： 你还可以使用情节提要。</span><span class="sxs-lookup"><span data-stu-id="4dfaa-105">There are other ways to interactively control animations that don't require you to work directly with clocks: you can also use Storyboards.</span></span> <span data-ttu-id="4dfaa-106">情节提要支持标记和代码。</span><span class="sxs-lookup"><span data-stu-id="4dfaa-106">Storyboards are supported in both markup and code.</span></span> <span data-ttu-id="4dfaa-107">有关示例，请参阅[使用情节提要属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)或[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="4dfaa-107">For an example, see [Animate a Property by Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) or the [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span>  
  
 <span data-ttu-id="4dfaa-108">在下面的示例中，多个按钮用于启动为交互式控制的动画时钟。</span><span class="sxs-lookup"><span data-stu-id="4dfaa-108">In the following example, several buttons are used to interactively control an animation clock.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4dfaa-109">示例</span><span class="sxs-lookup"><span data-stu-id="4dfaa-109">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="4dfaa-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="4dfaa-110">See Also</span></span>  
 [<span data-ttu-id="4dfaa-111">使用情节提要对属性进行动画处理</span><span class="sxs-lookup"><span data-stu-id="4dfaa-111">Animate a Property by Using a Storyboard</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)  
 [<span data-ttu-id="4dfaa-112">动画概述</span><span class="sxs-lookup"><span data-stu-id="4dfaa-112">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
