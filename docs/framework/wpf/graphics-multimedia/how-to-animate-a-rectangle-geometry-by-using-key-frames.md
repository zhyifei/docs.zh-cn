---
title: 如何：使用关键帧对矩形几何形状进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
ms.openlocfilehash: bcc9e7f198b8a20ffe13daf6508fb8a735937652
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344682"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a><span data-ttu-id="07eaf-102">如何：使用关键帧对矩形几何形状进行动画处理</span><span class="sxs-lookup"><span data-stu-id="07eaf-102">How to: Animate a Rectangle Geometry by Using Key Frames</span></span>
<span data-ttu-id="07eaf-103">此示例演示如何使用关键帧对<xref:System.Windows.Media.RectangleGeometry.Rect%2A>属性<xref:System.Windows.Media.RectangleGeometry>进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="07eaf-103">This example shows how to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07eaf-104">示例</span><span class="sxs-lookup"><span data-stu-id="07eaf-104">Example</span></span>  
 <span data-ttu-id="07eaf-105">下面的示例使用 类<xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>为 属性<xref:System.Windows.Media.RectangleGeometry>设置<xref:System.Windows.Media.RectangleGeometry.Rect%2A>动画。</span><span class="sxs-lookup"><span data-stu-id="07eaf-105">The following example uses the <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry>.</span></span> <span data-ttu-id="07eaf-106">此动画按以下方式使用三个关键帧：</span><span class="sxs-lookup"><span data-stu-id="07eaf-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="07eaf-107">在前两秒钟内<xref:System.Windows.Media.Animation.LinearRectKeyFrame>，使用类的实例对矩形的位置、宽度和高度进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="07eaf-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearRectKeyFrame> class to animate a gradual change in the position, width, and height of a rectangle.</span></span> <span data-ttu-id="07eaf-108">线性关键帧（<xref:System.Windows.Media.Animation.LinearRectKeyFrame>如在值之间创建平滑线性过渡）</span><span class="sxs-lookup"><span data-stu-id="07eaf-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearRectKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="07eaf-109">在下半秒结束时，使用<xref:System.Windows.Media.Animation.DiscreteRectKeyFrame>类的实例突然降低矩形的高度。</span><span class="sxs-lookup"><span data-stu-id="07eaf-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> class to suddenly decrease the height of the rectangle.</span></span> <span data-ttu-id="07eaf-110">离散的关键帧（<xref:System.Windows.Media.Animation.DiscreteRectKeyFrame>如在值之间创建突然变化）表示，高度的降低会迅速发生，并且不微妙。</span><span class="sxs-lookup"><span data-stu-id="07eaf-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> create sudden changes between values, that is, the decrease in height occurs quickly and is not subtle.</span></span>  
  
3. <span data-ttu-id="07eaf-111">在最后两秒钟内<xref:System.Windows.Media.Animation.SplineRectKeyFrame>，使用类的实例将矩形更改回其原始大小和位置。</span><span class="sxs-lookup"><span data-stu-id="07eaf-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame> class to change the rectangle back to its original size and position.</span></span> <span data-ttu-id="07eaf-112">样条线键帧，<xref:System.Windows.Media.Animation.SplineRectKeyFrame>如根据<xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A>属性的值在值之间创建可变转换。</span><span class="sxs-lookup"><span data-stu-id="07eaf-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineRectKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="07eaf-113">在此示例中，变化开始时缓慢，然后以指数级加速，直到时间段结束。</span><span class="sxs-lookup"><span data-stu-id="07eaf-113">In this example, the change begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="07eaf-114">有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。</span><span class="sxs-lookup"><span data-stu-id="07eaf-114">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07eaf-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="07eaf-115">See also</span></span>

- <xref:System.Windows.Media.RectangleGeometry>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>
- [<span data-ttu-id="07eaf-116">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="07eaf-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="07eaf-117">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="07eaf-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
