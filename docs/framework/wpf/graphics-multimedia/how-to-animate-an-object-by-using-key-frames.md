---
title: 如何：使用关键帧对对象进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: b0a0f7c00125a43228a2658415b72f4d541f37be
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59315837"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a><span data-ttu-id="30d19-102">如何：使用关键帧对对象进行动画处理</span><span class="sxs-lookup"><span data-stu-id="30d19-102">How to: Animate an Object by Using Key Frames</span></span>
<span data-ttu-id="30d19-103">此示例演示如何对一个对象，其在此示例中为进行动画处理<xref:System.Windows.Controls.Page.Background%2A>属性的<xref:System.Windows.Controls.Page>控件，使用关键帧。</span><span class="sxs-lookup"><span data-stu-id="30d19-103">This example shows how to animate an object, which in this example is the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30d19-104">示例</span><span class="sxs-lookup"><span data-stu-id="30d19-104">Example</span></span>  
 <span data-ttu-id="30d19-105">下面的示例使用<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>类进行动画处理颜色更改为<xref:System.Windows.Controls.Page.Background%2A>属性的<xref:System.Windows.Controls.Page>控件。</span><span class="sxs-lookup"><span data-stu-id="30d19-105">The following example uses the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class to animate color changes for the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control.</span></span> <span data-ttu-id="30d19-106">示例动画按固定间隔更改为不同的背景画笔。</span><span class="sxs-lookup"><span data-stu-id="30d19-106">The example animation changes to a different background brush at regular intervals.</span></span> <span data-ttu-id="30d19-107">此动画使用<xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>类，以创建三个不同的关键帧。</span><span class="sxs-lookup"><span data-stu-id="30d19-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> class to create three different key frames.</span></span> <span data-ttu-id="30d19-108">动画使用关键帧按以下方式：</span><span class="sxs-lookup"><span data-stu-id="30d19-108">The animation uses key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="30d19-109">在第一秒结束时，进行动画处理的实例<xref:System.Windows.Media.LinearGradientBrush>类。</span><span class="sxs-lookup"><span data-stu-id="30d19-109">At the end of the first second, animates an instance of the <xref:System.Windows.Media.LinearGradientBrush> class.</span></span> <span data-ttu-id="30d19-110">以便颜色黄色从过渡为红色的橙色到，该示例的此部分适用于的背景色线性渐变。</span><span class="sxs-lookup"><span data-stu-id="30d19-110">This section of the example applies a linear gradient to the background color so that the color transitions from yellow to orange to red.</span></span>  
  
2. <span data-ttu-id="30d19-111">在下一步秒结束时，进行动画处理的实例<xref:System.Windows.Media.RadialGradientBrush>类。</span><span class="sxs-lookup"><span data-stu-id="30d19-111">At the end of the next second, animates an instance of the <xref:System.Windows.Media.RadialGradientBrush> class.</span></span> <span data-ttu-id="30d19-112">此部分示例适用范围径向渐变的背景色，以便从白色到黑色蓝色颜色转换。</span><span class="sxs-lookup"><span data-stu-id="30d19-112">This section of the example applies a radial gradient to the background color so that the color transitions from white to blue to black.</span></span>  
  
3. <span data-ttu-id="30d19-113">在第三个秒结束时，进行动画处理的实例<xref:System.Windows.Media.DrawingBrush>类。</span><span class="sxs-lookup"><span data-stu-id="30d19-113">At the end of the third second, animates an instance of the <xref:System.Windows.Media.DrawingBrush> class.</span></span> <span data-ttu-id="30d19-114">该示例的此部分适用于在后台棋盘图案。</span><span class="sxs-lookup"><span data-stu-id="30d19-114">This section of the example applies a checkerboard pattern to the background.</span></span>  
  
4. <span data-ttu-id="30d19-115">动画将重新开始并无限期地重复。</span><span class="sxs-lookup"><span data-stu-id="30d19-115">The animation begins again and repeats indefinitely.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30d19-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 是唯一的您可以使用关键帧类型<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>类。</span><span class="sxs-lookup"><span data-stu-id="30d19-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> is the only type of key frame that you can use with the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class.</span></span> <span data-ttu-id="30d19-117">关键帧等<xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>，它是在值中，创建突然变化，突然发生在此示例中的颜色更改。</span><span class="sxs-lookup"><span data-stu-id="30d19-117">Key frames like <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> create sudden changes in values, that is, the color changes in this example occur suddenly.</span></span>  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="30d19-118">有关完整示例，请参阅[关键帧动画示例](https://go.microsoft.com/fwlink/?LinkID=160012)。</span><span class="sxs-lookup"><span data-stu-id="30d19-118">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30d19-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="30d19-119">See also</span></span>

- <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.Page.Background%2A>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- <xref:System.Windows.Media.DrawingBrush>
- [<span data-ttu-id="30d19-120">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="30d19-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="30d19-121">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="30d19-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
