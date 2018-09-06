---
title: 如何：使用关键帧对字符串进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: 1b55afd5938073a326789e67b66fec9cfce12015
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43868518"
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a><span data-ttu-id="0bc13-102">如何：使用关键帧对字符串进行动画处理</span><span class="sxs-lookup"><span data-stu-id="0bc13-102">How to: Animate a String by Using Key Frames</span></span>
<span data-ttu-id="0bc13-103">此示例演示如何对字符串，它在此示例中为动画处理<xref:System.Windows.Controls.ContentControl.Content%2A>属性的<xref:System.Windows.Controls.Button>控件，使用关键帧。</span><span class="sxs-lookup"><span data-stu-id="0bc13-103">This example shows how to animate a string, which in this example is the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bc13-104">示例</span><span class="sxs-lookup"><span data-stu-id="0bc13-104">Example</span></span>  
 <span data-ttu-id="0bc13-105">下面的示例使用<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>类进行动画处理<xref:System.Windows.Controls.ContentControl.Content%2A>属性的<xref:System.Windows.Controls.Button>。</span><span class="sxs-lookup"><span data-stu-id="0bc13-105">The following example uses the <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="0bc13-106">在此示例中的所有关键帧使用的实例<xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>类，因为使用关键帧创建一个字符串动画只能使用离散关键帧。</span><span class="sxs-lookup"><span data-stu-id="0bc13-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> class because a string animation that is created with key frames can only use discrete key frames.</span></span> <span data-ttu-id="0bc13-107">之类的离散关键帧<xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>之间创建突然跳跃的值，也就是说，动画变化快速发生的而不是。</span><span class="sxs-lookup"><span data-stu-id="0bc13-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> create sudden jumps between values, that is, changes to the animation occur quickly and are not subtle.</span></span>  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="0bc13-108">有关完整示例，请参阅[关键帧动画示例](https://go.microsoft.com/fwlink/?LinkID=160012)。</span><span class="sxs-lookup"><span data-stu-id="0bc13-108">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bc13-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="0bc13-109">See Also</span></span>  
 <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>  
 <xref:System.Windows.Controls.ContentControl.Content%2A>  
 <xref:System.Windows.Controls.Button>  
 <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>  
 [<span data-ttu-id="0bc13-110">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="0bc13-110">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="0bc13-111">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="0bc13-111">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
