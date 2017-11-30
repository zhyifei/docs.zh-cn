---
title: "如何：对 BorderThickness 值进行动画处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF], animating changes to
- animation [WPF], changes to border thickness
ms.assetid: fd021978-f74b-4e7b-a7f7-3987dcad9e0f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b9b0d91d4044f8c91c5e69ab146dee820b6b8519
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-borderthickness-value"></a><span data-ttu-id="233f2-102">如何：对 BorderThickness 值进行动画处理</span><span class="sxs-lookup"><span data-stu-id="233f2-102">How to: Animate a BorderThickness Value</span></span>
<span data-ttu-id="233f2-103">此示例演示如何使用边框的粗细对更改进行动画处理<xref:System.Windows.Media.Animation.ThicknessAnimation>类。</span><span class="sxs-lookup"><span data-stu-id="233f2-103">This example shows how to animate changes to the thickness of a border by using the <xref:System.Windows.Media.Animation.ThicknessAnimation> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="233f2-104">示例</span><span class="sxs-lookup"><span data-stu-id="233f2-104">Example</span></span>  
 <span data-ttu-id="233f2-105">下面的示例进行动画处理的边框的粗细，可通过使用<xref:System.Windows.Media.Animation.ThicknessAnimation>。</span><span class="sxs-lookup"><span data-stu-id="233f2-105">The following example animates the thickness of a border by using <xref:System.Windows.Media.Animation.ThicknessAnimation>.</span></span> <span data-ttu-id="233f2-106">该示例使用<xref:System.Windows.Controls.Border.BorderThickness%2A>属性<xref:System.Windows.Controls.Border>。</span><span class="sxs-lookup"><span data-stu-id="233f2-106">The example uses the <xref:System.Windows.Controls.Border.BorderThickness%2A> property of <xref:System.Windows.Controls.Border>.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#ThicknessAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/ThicknessAnimationExample.cs#thicknessanimationwholepage)]
 [!code-vb[BasicAnimations_snip#ThicknessAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/ThicknessAnimationExample.vb#thicknessanimationwholepage)]  
  
 <span data-ttu-id="233f2-107">有关完整的示例，请参阅[动画示例库](http://go.microsoft.com/fwlink/?LinkID=159969)。</span><span class="sxs-lookup"><span data-stu-id="233f2-107">For the complete sample, see [Animation Example Gallery](http://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="233f2-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="233f2-108">See Also</span></span>  
 <xref:System.Windows.Media.Animation.ThicknessAnimation>  
 <xref:System.Windows.Controls.Border.BorderThickness%2A>  
 <xref:System.Windows.Controls.Border>  
 [<span data-ttu-id="233f2-109">动画概述</span><span class="sxs-lookup"><span data-stu-id="233f2-109">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="233f2-110">动画和计时</span><span class="sxs-lookup"><span data-stu-id="233f2-110">Animation and Timing</span></span>](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="233f2-111">操作说明主题</span><span class="sxs-lookup"><span data-stu-id="233f2-111">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)  
 [<span data-ttu-id="233f2-112">使用关键帧为边框粗细设置动画效果</span><span class="sxs-lookup"><span data-stu-id="233f2-112">Animate the Thickness of a Border by Using Key Frames</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-the-thickness-of-a-border-by-using-key-frames.md)
