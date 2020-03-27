---
title: 如何：使用关键帧对字符串进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: c954806ca901bbfc3ab6d4bbcc237cd0e404f154
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344673"
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a><span data-ttu-id="c0a1a-102">如何：使用关键帧对字符串进行动画处理</span><span class="sxs-lookup"><span data-stu-id="c0a1a-102">How to: Animate a String by Using Key Frames</span></span>
<span data-ttu-id="c0a1a-103">此示例演示如何使用关键帧为字符串设置动画，在此示例中，该字符串是<xref:System.Windows.Controls.ContentControl.Content%2A><xref:System.Windows.Controls.Button>控件的属性。</span><span class="sxs-lookup"><span data-stu-id="c0a1a-103">This example shows how to animate a string, which in this example is the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0a1a-104">示例</span><span class="sxs-lookup"><span data-stu-id="c0a1a-104">Example</span></span>  
 <span data-ttu-id="c0a1a-105">下面的示例使用 类<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>为 属性<xref:System.Windows.Controls.Button>设置<xref:System.Windows.Controls.ContentControl.Content%2A>动画。</span><span class="sxs-lookup"><span data-stu-id="c0a1a-105">The following example uses the <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="c0a1a-106">此示例中的所有关键帧都使用类的实例，<xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>因为使用关键帧创建的字符串动画只能使用离散关键帧。</span><span class="sxs-lookup"><span data-stu-id="c0a1a-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> class because a string animation that is created with key frames can only use discrete key frames.</span></span> <span data-ttu-id="c0a1a-107">离散的关键帧（<xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>如在值之间创建突然跳转），即动画更改发生得很快，并且不是微妙的。</span><span class="sxs-lookup"><span data-stu-id="c0a1a-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> create sudden jumps between values, that is, changes to the animation occur quickly and are not subtle.</span></span>  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="c0a1a-108">有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。</span><span class="sxs-lookup"><span data-stu-id="c0a1a-108">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0a1a-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0a1a-109">See also</span></span>

- <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.ContentControl.Content%2A>
- <xref:System.Windows.Controls.Button>
- <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>
- [<span data-ttu-id="c0a1a-110">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="c0a1a-110">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="c0a1a-111">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="c0a1a-111">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
