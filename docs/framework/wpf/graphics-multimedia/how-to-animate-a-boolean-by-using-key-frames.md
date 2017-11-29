---
title: "如何：使用关键帧对布尔属性值进行动画处理"
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
- Booleans [WPF], animating with key frames
- animation [WPF], Booleans with key frames
- key frames [WPF], animating Booleans with
ms.assetid: 4b0fac96-6231-4fcf-9775-4dd673ddc785
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0ac129bf133cca88a6d2f6a724d25ea2519cb72e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-boolean-by-using-key-frames"></a><span data-ttu-id="357c4-102">如何：使用关键帧对布尔属性值进行动画处理</span><span class="sxs-lookup"><span data-stu-id="357c4-102">How to: Animate a Boolean by Using Key Frames</span></span>
<span data-ttu-id="357c4-103">此示例演示如何进行动画处理的布尔属性值<xref:System.Windows.Controls.Button>使用关键帧的控件。</span><span class="sxs-lookup"><span data-stu-id="357c4-103">This example shows how to animate the Boolean property value of a <xref:System.Windows.Controls.Button> control by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="357c4-104">示例</span><span class="sxs-lookup"><span data-stu-id="357c4-104">Example</span></span>  
 <span data-ttu-id="357c4-105">下面的示例使用<xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>类进行动画处理<xref:System.Windows.UIElement.IsEnabled%2A>属性<xref:System.Windows.Controls.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="357c4-105">The following example uses the <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> class to animate the <xref:System.Windows.UIElement.IsEnabled%2A> property of a <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="357c4-106">在此示例中的所有关键帧使用的实例<xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame>类。</span><span class="sxs-lookup"><span data-stu-id="357c4-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> class.</span></span> <span data-ttu-id="357c4-107">之类的离散的关键帧<xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame>突变值，即，动画的移动是不平稳。</span><span class="sxs-lookup"><span data-stu-id="357c4-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-csharp[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/BooleanAnimationUsingKeyFramesExample.cs#booleananimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/booleananimationusingkeyframesexample.vb#booleananimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/BooleanAnimationUsingKeyFramesExample.xaml#booleananimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="357c4-108">有关完整示例，请参阅[关键帧动画示例](http://go.microsoft.com/fwlink/?LinkID=160012)。</span><span class="sxs-lookup"><span data-stu-id="357c4-108">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="357c4-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="357c4-109">See Also</span></span>  
 <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>  
 <xref:System.Windows.UIElement.IsEnabled%2A>  
 <xref:System.Windows.Controls.Button>  
 [<span data-ttu-id="357c4-110">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="357c4-110">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="357c4-111">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="357c4-111">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
