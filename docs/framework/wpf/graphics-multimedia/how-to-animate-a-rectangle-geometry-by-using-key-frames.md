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
ms.openlocfilehash: 03953b79127ffceeb49e4ece2070d09f382448a5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59311339"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a><span data-ttu-id="1eabf-102">如何：使用关键帧对矩形几何形状进行动画处理</span><span class="sxs-lookup"><span data-stu-id="1eabf-102">How to: Animate a Rectangle Geometry by Using Key Frames</span></span>
<span data-ttu-id="1eabf-103">此示例演示如何进行动画处理<xref:System.Windows.Media.RectangleGeometry.Rect%2A>属性的<xref:System.Windows.Media.RectangleGeometry>使用关键帧。</span><span class="sxs-lookup"><span data-stu-id="1eabf-103">This example shows how to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1eabf-104">示例</span><span class="sxs-lookup"><span data-stu-id="1eabf-104">Example</span></span>  
 <span data-ttu-id="1eabf-105">下面的示例使用<xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>类进行动画处理<xref:System.Windows.Media.RectangleGeometry.Rect%2A>属性的<xref:System.Windows.Media.RectangleGeometry>。</span><span class="sxs-lookup"><span data-stu-id="1eabf-105">The following example uses the <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry>.</span></span> <span data-ttu-id="1eabf-106">此动画按以下方式使用三个关键帧：</span><span class="sxs-lookup"><span data-stu-id="1eabf-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="1eabf-107">在前两秒中，使用的实例<xref:System.Windows.Media.Animation.LinearRectKeyFrame>类进行动画处理中的位置、 宽度和的矩形的高度变化。</span><span class="sxs-lookup"><span data-stu-id="1eabf-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearRectKeyFrame> class to animate a gradual change in the position, width, and height of a rectangle.</span></span> <span data-ttu-id="1eabf-108">之类的线性关键帧<xref:System.Windows.Media.Animation.LinearRectKeyFrame>创建值之间平滑的线性转换。</span><span class="sxs-lookup"><span data-stu-id="1eabf-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearRectKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="1eabf-109">在结束时的下一个前半秒中，使用的实例<xref:System.Windows.Media.Animation.DiscreteRectKeyFrame>类突然降低矩形的高度。</span><span class="sxs-lookup"><span data-stu-id="1eabf-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> class to suddenly decrease the height of the rectangle.</span></span> <span data-ttu-id="1eabf-110">之类的离散关键帧<xref:System.Windows.Media.Animation.DiscreteRectKeyFrame>之间创建突然变化的值，也就是说，快速发生高度减小，而不是。</span><span class="sxs-lookup"><span data-stu-id="1eabf-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> create sudden changes between values, that is, the decrease in height occurs quickly and is not subtle.</span></span>  
  
3. <span data-ttu-id="1eabf-111">在最后两秒内，使用的实例<xref:System.Windows.Media.Animation.SplineRectKeyFrame>类将矩形更改回其原始大小和位置。</span><span class="sxs-lookup"><span data-stu-id="1eabf-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame> class to change the rectangle back to its original size and position.</span></span> <span data-ttu-id="1eabf-112">之类的自由绘制曲线关键帧<xref:System.Windows.Media.Animation.SplineRectKeyFrame>创建根据的值在值之间的变量转换<xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="1eabf-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineRectKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="1eabf-113">在此示例中，变化开始时缓慢，然后以指数级加速，直到时间段结束。</span><span class="sxs-lookup"><span data-stu-id="1eabf-113">In this example, the change begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="1eabf-114">有关完整示例，请参阅[关键帧动画示例](https://go.microsoft.com/fwlink/?LinkID=160012)。</span><span class="sxs-lookup"><span data-stu-id="1eabf-114">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eabf-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="1eabf-115">See also</span></span>

- <xref:System.Windows.Media.RectangleGeometry>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>
- [<span data-ttu-id="1eabf-116">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="1eabf-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="1eabf-117">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="1eabf-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
