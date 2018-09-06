---
title: 如何：使动画加速或减速
ms.date: 03/30/2017
helpviewer_keywords:
- decelerating animation [WPF]
- accelerating animation [WPF]
- animation [WPF], accelerating
- animation [WPF], decelerating
ms.assetid: 4f383b2c-f94d-4a4e-9a06-f56f5dae95f9
ms.openlocfilehash: b1649f27fc8ff850516eef2086dbce732915406b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43724053"
---
# <a name="how-to-accelerate-or-decelerate-an-animation"></a><span data-ttu-id="14aaf-102">如何：使动画加速或减速</span><span class="sxs-lookup"><span data-stu-id="14aaf-102">How to: Accelerate or Decelerate an Animation</span></span>
<span data-ttu-id="14aaf-103">此示例演示如何使动画加速和减速随着时间的推移。</span><span class="sxs-lookup"><span data-stu-id="14aaf-103">This example demonstrates how to make an animation accelerate and decelerate over time.</span></span> <span data-ttu-id="14aaf-104">在以下示例中，多个矩形进行动画处理与不同的动画<xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A>和<xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A>设置。</span><span class="sxs-lookup"><span data-stu-id="14aaf-104">In the following example, several rectangles are animated by animations with different <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> and <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> settings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14aaf-105">示例</span><span class="sxs-lookup"><span data-stu-id="14aaf-105">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AccelDecelExample.xaml#1)]  
  
 <span data-ttu-id="14aaf-106">此示例中省略了代码。</span><span class="sxs-lookup"><span data-stu-id="14aaf-106">Code has been omitted from this example.</span></span> <span data-ttu-id="14aaf-107">有关完整的代码，请参阅[动画计时行为示例](https://go.microsoft.com/fwlink/?LinkID=159970)。</span><span class="sxs-lookup"><span data-stu-id="14aaf-107">For the complete code, see the [Animation Timing Behavior Sample](https://go.microsoft.com/fwlink/?LinkID=159970).</span></span>
