---
title: 如何：使用关键帧对对象进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: ffbe1845b634c8f94eb6a10dfa44fcf9903e0cd5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933912"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a><span data-ttu-id="77aaf-102">如何：使用关键帧对对象进行动画处理</span><span class="sxs-lookup"><span data-stu-id="77aaf-102">How to: Animate an Object by Using Key Frames</span></span>
<span data-ttu-id="77aaf-103">此示例演示如何使用关键帧对对象 (在此示例中为<xref:System.Windows.Controls.Page.Background%2A> <xref:System.Windows.Controls.Page>控件的属性) 进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="77aaf-103">This example shows how to animate an object, which in this example is the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77aaf-104">示例</span><span class="sxs-lookup"><span data-stu-id="77aaf-104">Example</span></span>  
 <span data-ttu-id="77aaf-105">下面的示例使用<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>类对<xref:System.Windows.Controls.Page>控件的<xref:System.Windows.Controls.Page.Background%2A>属性的颜色更改进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="77aaf-105">The following example uses the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class to animate color changes for the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control.</span></span> <span data-ttu-id="77aaf-106">该示例动画会按固定的时间间隔更改为不同的背景画笔。</span><span class="sxs-lookup"><span data-stu-id="77aaf-106">The example animation changes to a different background brush at regular intervals.</span></span> <span data-ttu-id="77aaf-107">此动画使用<xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>类创建三个不同的关键帧。</span><span class="sxs-lookup"><span data-stu-id="77aaf-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> class to create three different key frames.</span></span> <span data-ttu-id="77aaf-108">动画按以下方式使用关键帧:</span><span class="sxs-lookup"><span data-stu-id="77aaf-108">The animation uses key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="77aaf-109">在第一秒结束时, 对<xref:System.Windows.Media.LinearGradientBrush>类的实例进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="77aaf-109">At the end of the first second, animates an instance of the <xref:System.Windows.Media.LinearGradientBrush> class.</span></span> <span data-ttu-id="77aaf-110">此部分示例对背景色应用线性渐变, 使颜色从黄色转换为橙色。</span><span class="sxs-lookup"><span data-stu-id="77aaf-110">This section of the example applies a linear gradient to the background color so that the color transitions from yellow to orange to red.</span></span>  
  
2. <span data-ttu-id="77aaf-111">在下一秒结束时, 对<xref:System.Windows.Media.RadialGradientBrush>类的实例进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="77aaf-111">At the end of the next second, animates an instance of the <xref:System.Windows.Media.RadialGradientBrush> class.</span></span> <span data-ttu-id="77aaf-112">此部分示例对背景色应用径向渐变, 使颜色从白色过渡到蓝色。</span><span class="sxs-lookup"><span data-stu-id="77aaf-112">This section of the example applies a radial gradient to the background color so that the color transitions from white to blue to black.</span></span>  
  
3. <span data-ttu-id="77aaf-113">在第三秒结束时, 对<xref:System.Windows.Media.DrawingBrush>类的实例进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="77aaf-113">At the end of the third second, animates an instance of the <xref:System.Windows.Media.DrawingBrush> class.</span></span> <span data-ttu-id="77aaf-114">此部分示例将棋盘模式应用于背景。</span><span class="sxs-lookup"><span data-stu-id="77aaf-114">This section of the example applies a checkerboard pattern to the background.</span></span>  
  
4. <span data-ttu-id="77aaf-115">动画将再次开始, 并无限期地重复。</span><span class="sxs-lookup"><span data-stu-id="77aaf-115">The animation begins again and repeats indefinitely.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="77aaf-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>是唯一可与<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>类一起使用的关键帧类型。</span><span class="sxs-lookup"><span data-stu-id="77aaf-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> is the only type of key frame that you can use with the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class.</span></span> <span data-ttu-id="77aaf-117">关键帧 ( <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>如创建值的突然变化) 即, 此示例中的颜色更改突然发生。</span><span class="sxs-lookup"><span data-stu-id="77aaf-117">Key frames like <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> create sudden changes in values, that is, the color changes in this example occur suddenly.</span></span>  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="77aaf-118">有关完整示例，请参阅[关键帧动画示例](https://go.microsoft.com/fwlink/?LinkID=160012)。</span><span class="sxs-lookup"><span data-stu-id="77aaf-118">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77aaf-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="77aaf-119">See also</span></span>

- <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.Page.Background%2A>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- <xref:System.Windows.Media.DrawingBrush>
- [<span data-ttu-id="77aaf-120">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="77aaf-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="77aaf-121">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="77aaf-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
