---
title: "如何：使用关键帧对字符串进行动画处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1692777a97754fb7f6481b2d9cb8942dcb62df77
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a><span data-ttu-id="f3454-102">如何：使用关键帧对字符串进行动画处理</span><span class="sxs-lookup"><span data-stu-id="f3454-102">How to: Animate a String by Using Key Frames</span></span>
<span data-ttu-id="f3454-103">此示例演示如何进行动画处理的字符串，它在此示例中为<xref:System.Windows.Controls.ContentControl.Content%2A>属性<xref:System.Windows.Controls.Button>控件，通过使用关键帧。</span><span class="sxs-lookup"><span data-stu-id="f3454-103">This example shows how to animate a string, which in this example is the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3454-104">示例</span><span class="sxs-lookup"><span data-stu-id="f3454-104">Example</span></span>  
 <span data-ttu-id="f3454-105">下面的示例使用<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>类进行动画处理<xref:System.Windows.Controls.ContentControl.Content%2A>属性<xref:System.Windows.Controls.Button>。</span><span class="sxs-lookup"><span data-stu-id="f3454-105">The following example uses the <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="f3454-106">在此示例中的所有关键帧使用的实例<xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>类，因为创建关键帧的字符串动画只能使用离散关键帧。</span><span class="sxs-lookup"><span data-stu-id="f3454-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> class because a string animation that is created with key frames can only use discrete key frames.</span></span> <span data-ttu-id="f3454-107">之类的离散的关键帧<xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>突变值，即，更改到动画快速发生的并且不是细微变化。</span><span class="sxs-lookup"><span data-stu-id="f3454-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> create sudden jumps between values, that is, changes to the animation occur quickly and are not subtle.</span></span>  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="f3454-108">有关完整示例，请参阅[关键帧动画示例](http://go.microsoft.com/fwlink/?LinkID=160012)。</span><span class="sxs-lookup"><span data-stu-id="f3454-108">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3454-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="f3454-109">See Also</span></span>  
 <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>  
 <xref:System.Windows.Controls.ContentControl.Content%2A>  
 <xref:System.Windows.Controls.Button>  
 <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>  
 [<span data-ttu-id="f3454-110">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="f3454-110">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="f3454-111">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="f3454-111">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
