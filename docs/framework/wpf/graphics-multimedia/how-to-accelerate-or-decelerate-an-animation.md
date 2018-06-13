---
title: 如何：使动画加速或减速
ms.date: 03/30/2017
helpviewer_keywords:
- decelerating animation [WPF]
- accelerating animation [WPF]
- animation [WPF], accelerating
- animation [WPF], decelerating
ms.assetid: 4f383b2c-f94d-4a4e-9a06-f56f5dae95f9
ms.openlocfilehash: b4bea64dbc88ce32c908289b9465b058c558a932
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555668"
---
# <a name="how-to-accelerate-or-decelerate-an-animation"></a><span data-ttu-id="56e3c-102">如何：使动画加速或减速</span><span class="sxs-lookup"><span data-stu-id="56e3c-102">How to: Accelerate or Decelerate an Animation</span></span>
<span data-ttu-id="56e3c-103">此示例演示如何进行加速和随着时间的推移减速的动画。</span><span class="sxs-lookup"><span data-stu-id="56e3c-103">This example demonstrates how to make an animation accelerate and decelerate over time.</span></span> <span data-ttu-id="56e3c-104">在下面的示例中，多个矩形进行动画处理具有不同的动画<xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A>和<xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A>设置。</span><span class="sxs-lookup"><span data-stu-id="56e3c-104">In the following example, several rectangles are animated by animations with different <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> and <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> settings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56e3c-105">示例</span><span class="sxs-lookup"><span data-stu-id="56e3c-105">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AccelDecelExample.xaml#1)]  
  
 <span data-ttu-id="56e3c-106">此示例中，代码已被省略。</span><span class="sxs-lookup"><span data-stu-id="56e3c-106">Code has been omitted from this example.</span></span> <span data-ttu-id="56e3c-107">有关完整的代码，请参阅[动画计时行为示例](http://go.microsoft.com/fwlink/?LinkID=159970)。</span><span class="sxs-lookup"><span data-stu-id="56e3c-107">For the complete code, see the [Animation Timing Behavior Sample](http://go.microsoft.com/fwlink/?LinkID=159970).</span></span>
