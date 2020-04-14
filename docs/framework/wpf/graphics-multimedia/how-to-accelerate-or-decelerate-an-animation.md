---
title: 如何：使动画加速或减速
ms.date: 03/30/2017
helpviewer_keywords:
- decelerating animation [WPF]
- accelerating animation [WPF]
- animation [WPF], accelerating
- animation [WPF], decelerating
ms.assetid: 4f383b2c-f94d-4a4e-9a06-f56f5dae95f9
ms.openlocfilehash: 7ab55ba44b866a992b9021284f170858f0108d15
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243006"
---
# <a name="how-to-accelerate-or-decelerate-an-animation"></a><span data-ttu-id="14991-102">如何：加速或减速动画</span><span class="sxs-lookup"><span data-stu-id="14991-102">How to: Accelerate or decelerate an animation</span></span>

<span data-ttu-id="14991-103">此示例演示如何使动画随着时间的推移加速和减速。</span><span class="sxs-lookup"><span data-stu-id="14991-103">This example demonstrates how to make an animation accelerate and decelerate over time.</span></span> <span data-ttu-id="14991-104">在下面的示例中，几个矩形由具有不同<xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A>和<xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A>设置的动画进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="14991-104">In the following example, several rectangles are animated by animations with different <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> and <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> settings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14991-105">示例</span><span class="sxs-lookup"><span data-stu-id="14991-105">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AccelDecelExample.xaml#1)]  
  
 <span data-ttu-id="14991-106">此示例中省略了代码。</span><span class="sxs-lookup"><span data-stu-id="14991-106">Code has been omitted from this example.</span></span> <span data-ttu-id="14991-107">有关完整代码，请参阅[动画计时行为 （C#）](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp)或[动画计时行为 （视觉基本）](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic)。</span><span class="sxs-lookup"><span data-stu-id="14991-107">For the complete code, see the [Animation Timing Behavior (C#)](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp) or [Animation Timing Behavior (Visual Basic)](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic).</span></span>
