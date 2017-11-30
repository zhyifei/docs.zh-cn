---
title: "如何：使用关键帧针对对象进行动画处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 71feb0ecef7a6356c95b843fbc2657ad2e4a7996
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a><span data-ttu-id="86fe1-102">如何：使用关键帧针对对象进行动画处理</span><span class="sxs-lookup"><span data-stu-id="86fe1-102">How to: Animate an Object by Using Key Frames</span></span>
<span data-ttu-id="86fe1-103">此示例演示如何进行动画处理的对象，它在此示例中为<xref:System.Windows.Controls.Page.Background%2A>属性<xref:System.Windows.Controls.Page>控件，通过使用关键帧。</span><span class="sxs-lookup"><span data-stu-id="86fe1-103">This example shows how to animate an object, which in this example is the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86fe1-104">示例</span><span class="sxs-lookup"><span data-stu-id="86fe1-104">Example</span></span>  
 <span data-ttu-id="86fe1-105">下面的示例使用<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>颜色进行动画处理的类更改<xref:System.Windows.Controls.Page.Background%2A>属性<xref:System.Windows.Controls.Page>控件。</span><span class="sxs-lookup"><span data-stu-id="86fe1-105">The following example uses the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class to animate color changes for the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control.</span></span> <span data-ttu-id="86fe1-106">示例动画定期将更改为不同的背景画笔。</span><span class="sxs-lookup"><span data-stu-id="86fe1-106">The example animation changes to a different background brush at regular intervals.</span></span> <span data-ttu-id="86fe1-107">此动画使用<xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>类，以创建三个不同的关键帧。</span><span class="sxs-lookup"><span data-stu-id="86fe1-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> class to create three different key frames.</span></span> <span data-ttu-id="86fe1-108">动画按以下方式使用关键帧：</span><span class="sxs-lookup"><span data-stu-id="86fe1-108">The animation uses key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="86fe1-109">在第一秒结束时，进行动画处理的实例<xref:System.Windows.Media.LinearGradientBrush>类。</span><span class="sxs-lookup"><span data-stu-id="86fe1-109">At the end of the first second, animates an instance of the <xref:System.Windows.Media.LinearGradientBrush> class.</span></span> <span data-ttu-id="86fe1-110">此部分的示例适用范围线性渐变的背景色，以便颜色从黄色转换为红色的橙色。</span><span class="sxs-lookup"><span data-stu-id="86fe1-110">This section of the example applies a linear gradient to the background color so that the color transitions from yellow to orange to red.</span></span>  
  
2.  <span data-ttu-id="86fe1-111">在下一步的第二个结束时，进行动画处理的实例<xref:System.Windows.Media.RadialGradientBrush>类。</span><span class="sxs-lookup"><span data-stu-id="86fe1-111">At the end of the next second, animates an instance of the <xref:System.Windows.Media.RadialGradientBrush> class.</span></span> <span data-ttu-id="86fe1-112">此部分的示例适用范围径向渐变的背景色，以便从空白为蓝色为黑色转换颜色。</span><span class="sxs-lookup"><span data-stu-id="86fe1-112">This section of the example applies a radial gradient to the background color so that the color transitions from white to blue to black.</span></span>  
  
3.  <span data-ttu-id="86fe1-113">在第三个第二个结束时，进行动画处理的实例<xref:System.Windows.Media.DrawingBrush>类。</span><span class="sxs-lookup"><span data-stu-id="86fe1-113">At the end of the third second, animates an instance of the <xref:System.Windows.Media.DrawingBrush> class.</span></span> <span data-ttu-id="86fe1-114">此部分的示例适用于后台呈现为棋盘样式。</span><span class="sxs-lookup"><span data-stu-id="86fe1-114">This section of the example applies a checkerboard pattern to the background.</span></span>  
  
4.  <span data-ttu-id="86fe1-115">动画将重新开始计算，无限期地重复。</span><span class="sxs-lookup"><span data-stu-id="86fe1-115">The animation begins again and repeats indefinitely.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="86fe1-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>是你可以使用的关键帧的唯一类型<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>类。</span><span class="sxs-lookup"><span data-stu-id="86fe1-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> is the only type of key frame that you can use with the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class.</span></span> <span data-ttu-id="86fe1-117">关键帧如<xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>值，即创建突然变化、 突然发生在此示例中的颜色更改。</span><span class="sxs-lookup"><span data-stu-id="86fe1-117">Key frames like <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> create sudden changes in values, that is, the color changes in this example occur suddenly.</span></span>  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="86fe1-118">有关完整示例，请参阅[关键帧动画示例](http://go.microsoft.com/fwlink/?LinkID=160012)。</span><span class="sxs-lookup"><span data-stu-id="86fe1-118">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86fe1-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86fe1-119">See Also</span></span>  
 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>  
 <xref:System.Windows.Controls.Page.Background%2A>  
 <xref:System.Windows.Controls.Page>  
 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>  
 <xref:System.Windows.Media.LinearGradientBrush>  
 <xref:System.Windows.Media.RadialGradientBrush>  
 <xref:System.Windows.Media.DrawingBrush>  
 [<span data-ttu-id="86fe1-120">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="86fe1-120">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="86fe1-121">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="86fe1-121">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
