---
title: 如何：使用关键帧对布尔属性值进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Booleans [WPF], animating with key frames
- animation [WPF], Booleans with key frames
- key frames [WPF], animating Booleans with
ms.assetid: 4b0fac96-6231-4fcf-9775-4dd673ddc785
ms.openlocfilehash: 0142748a5c8e9a4375802d1b48beec0501d37e7c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43521069"
---
# <a name="how-to-animate-a-boolean-by-using-key-frames"></a><span data-ttu-id="d2529-102">如何：使用关键帧对布尔属性值进行动画处理</span><span class="sxs-lookup"><span data-stu-id="d2529-102">How to: Animate a Boolean by Using Key Frames</span></span>
<span data-ttu-id="d2529-103">此示例演示如何进行动画处理的布尔属性值<xref:System.Windows.Controls.Button>使用关键帧的控件。</span><span class="sxs-lookup"><span data-stu-id="d2529-103">This example shows how to animate the Boolean property value of a <xref:System.Windows.Controls.Button> control by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2529-104">示例</span><span class="sxs-lookup"><span data-stu-id="d2529-104">Example</span></span>  
 <span data-ttu-id="d2529-105">下面的示例使用<xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>类进行动画处理<xref:System.Windows.UIElement.IsEnabled%2A>属性的<xref:System.Windows.Controls.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="d2529-105">The following example uses the <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> class to animate the <xref:System.Windows.UIElement.IsEnabled%2A> property of a <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="d2529-106">在此示例中的所有关键帧使用的实例<xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame>类。</span><span class="sxs-lookup"><span data-stu-id="d2529-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> class.</span></span> <span data-ttu-id="d2529-107">之类的离散关键帧<xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame>之间创建突然跳跃的值，也就是说，动画的运动是不平稳。</span><span class="sxs-lookup"><span data-stu-id="d2529-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-csharp[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/BooleanAnimationUsingKeyFramesExample.cs#booleananimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/booleananimationusingkeyframesexample.vb#booleananimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/BooleanAnimationUsingKeyFramesExample.xaml#booleananimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="d2529-108">有关完整示例，请参阅[关键帧动画示例](https://go.microsoft.com/fwlink/?LinkID=160012)。</span><span class="sxs-lookup"><span data-stu-id="d2529-108">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2529-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="d2529-109">See Also</span></span>  
 <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>  
 <xref:System.Windows.UIElement.IsEnabled%2A>  
 <xref:System.Windows.Controls.Button>  
 [<span data-ttu-id="d2529-110">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="d2529-110">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="d2529-111">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="d2529-111">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
