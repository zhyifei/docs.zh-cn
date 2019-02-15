---
title: 如何：对 BorderThickness 值进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF], animating changes to
- animation [WPF], changes to border thickness
ms.assetid: fd021978-f74b-4e7b-a7f7-3987dcad9e0f
ms.openlocfilehash: 96467fd013ddd2b2e215520384da2000aec68866
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2019
ms.locfileid: "56304214"
---
# <a name="how-to-animate-a-borderthickness-value"></a><span data-ttu-id="b579b-102">如何：对 BorderThickness 值进行动画处理</span><span class="sxs-lookup"><span data-stu-id="b579b-102">How to: Animate a BorderThickness Value</span></span>
<span data-ttu-id="b579b-103">此示例演示如何使用更改对边框的粗细进行动画处理<xref:System.Windows.Media.Animation.ThicknessAnimation>类。</span><span class="sxs-lookup"><span data-stu-id="b579b-103">This example shows how to animate changes to the thickness of a border by using the <xref:System.Windows.Media.Animation.ThicknessAnimation> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b579b-104">示例</span><span class="sxs-lookup"><span data-stu-id="b579b-104">Example</span></span>  
 <span data-ttu-id="b579b-105">下面的示例通过使用进行动画处理对边框的粗细<xref:System.Windows.Media.Animation.ThicknessAnimation>。</span><span class="sxs-lookup"><span data-stu-id="b579b-105">The following example animates the thickness of a border by using <xref:System.Windows.Media.Animation.ThicknessAnimation>.</span></span> <span data-ttu-id="b579b-106">该示例使用<xref:System.Windows.Controls.Border.BorderThickness%2A>属性的<xref:System.Windows.Controls.Border>。</span><span class="sxs-lookup"><span data-stu-id="b579b-106">The example uses the <xref:System.Windows.Controls.Border.BorderThickness%2A> property of <xref:System.Windows.Controls.Border>.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#ThicknessAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/ThicknessAnimationExample.cs#thicknessanimationwholepage)]
 [!code-vb[BasicAnimations_snip#ThicknessAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/ThicknessAnimationExample.vb#thicknessanimationwholepage)]  
  
 <span data-ttu-id="b579b-107">有关完整示例，请参阅[动画示例库](https://go.microsoft.com/fwlink/?LinkID=159969)。</span><span class="sxs-lookup"><span data-stu-id="b579b-107">For the complete sample, see [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b579b-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="b579b-108">See also</span></span>
- <xref:System.Windows.Media.Animation.ThicknessAnimation>
- <xref:System.Windows.Controls.Border.BorderThickness%2A>
- <xref:System.Windows.Controls.Border>
- [<span data-ttu-id="b579b-109">动画概述</span><span class="sxs-lookup"><span data-stu-id="b579b-109">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="b579b-110">动画和计时操作指南主题</span><span class="sxs-lookup"><span data-stu-id="b579b-110">Animation and Timing How-to Topics</span></span>](../graphics-multimedia/animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="b579b-111">使用关键帧为边框粗细设置动画效果</span><span class="sxs-lookup"><span data-stu-id="b579b-111">Animate the Thickness of a Border by Using Key Frames</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-the-thickness-of-a-border-by-using-key-frames.md)
