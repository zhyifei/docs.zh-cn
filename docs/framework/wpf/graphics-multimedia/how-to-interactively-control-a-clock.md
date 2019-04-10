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
ms.openlocfilehash: 05989b6a03e03fb5723a70c9c36d5e32f9117049
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186584"
---
# <a name="how-to-interactively-control-a-clock"></a><span data-ttu-id="03e72-102">如何：以交互方式控制时钟</span><span class="sxs-lookup"><span data-stu-id="03e72-102">How to: Interactively Control a Clock</span></span>
<span data-ttu-id="03e72-103">一个<xref:System.Windows.Media.Animation.Clock>对象的<xref:System.Windows.Media.Animation.ClockController>属性使您能够以交互方式启动、 暂停、 恢复、 查找，请转到其填充期，时钟和停止时钟。</span><span class="sxs-lookup"><span data-stu-id="03e72-103">A <xref:System.Windows.Media.Animation.Clock> object's <xref:System.Windows.Media.Animation.ClockController> property enables you to interactively start, pause, resume, seek, advance the clock to its fill period, and stop the clock.</span></span> <span data-ttu-id="03e72-104">可以以交互方式控制仅一个计时树的根时钟。</span><span class="sxs-lookup"><span data-stu-id="03e72-104">Only the root clock of a timing tree can be interactively controlled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="03e72-105">还有其他方法为以交互方式控制动画的不需要您要直接使用时钟： 你还可以使用情节提要。</span><span class="sxs-lookup"><span data-stu-id="03e72-105">There are other ways to interactively control animations that don't require you to work directly with clocks: you can also use Storyboards.</span></span> <span data-ttu-id="03e72-106">情节提要支持标记和代码中。</span><span class="sxs-lookup"><span data-stu-id="03e72-106">Storyboards are supported in both markup and code.</span></span> <span data-ttu-id="03e72-107">有关示例，请参阅[使用情节提要对属性进行动画处理](how-to-animate-a-property-by-using-a-storyboard.md)或[动画概述](animation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="03e72-107">For an example, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md) or the [Animation Overview](animation-overview.md).</span></span>  
  
 <span data-ttu-id="03e72-108">在以下示例中，几个按钮，用于以交互方式控制的动画时钟。</span><span class="sxs-lookup"><span data-stu-id="03e72-108">In the following example, several buttons are used to interactively control an animation clock.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03e72-109">示例</span><span class="sxs-lookup"><span data-stu-id="03e72-109">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="03e72-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="03e72-110">See also</span></span>

- [<span data-ttu-id="03e72-111">使用情节提要对属性进行动画处理</span><span class="sxs-lookup"><span data-stu-id="03e72-111">Animate a Property by Using a Storyboard</span></span>](how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="03e72-112">动画概述</span><span class="sxs-lookup"><span data-stu-id="03e72-112">Animation Overview</span></span>](animation-overview.md)
