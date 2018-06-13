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
ms.openlocfilehash: 581dc89d21091ad0ce856d7a7ced84fd7bcea9d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559277"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a><span data-ttu-id="c5e85-102">如何：使用关键帧对矩形几何形状进行动画处理</span><span class="sxs-lookup"><span data-stu-id="c5e85-102">How to: Animate a Rectangle Geometry by Using Key Frames</span></span>
<span data-ttu-id="c5e85-103">此示例演示如何进行动画处理<xref:System.Windows.Media.RectangleGeometry.Rect%2A>属性<xref:System.Windows.Media.RectangleGeometry>使用关键帧。</span><span class="sxs-lookup"><span data-stu-id="c5e85-103">This example shows how to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5e85-104">示例</span><span class="sxs-lookup"><span data-stu-id="c5e85-104">Example</span></span>  
 <span data-ttu-id="c5e85-105">下面的示例使用<xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>类进行动画处理<xref:System.Windows.Media.RectangleGeometry.Rect%2A>属性<xref:System.Windows.Media.RectangleGeometry>。</span><span class="sxs-lookup"><span data-stu-id="c5e85-105">The following example uses the <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry>.</span></span> <span data-ttu-id="c5e85-106">此动画按以下方式使用三个关键帧：</span><span class="sxs-lookup"><span data-stu-id="c5e85-106">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="c5e85-107">在第一个的两秒内，使用的是实例<xref:System.Windows.Media.Animation.LinearRectKeyFrame>类进行动画处理逐步更改位置、 宽度和高度的矩形。</span><span class="sxs-lookup"><span data-stu-id="c5e85-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearRectKeyFrame> class to animate a gradual change in the position, width, and height of a rectangle.</span></span> <span data-ttu-id="c5e85-108">之类的线性的关键帧<xref:System.Windows.Media.Animation.LinearRectKeyFrame>创建平滑的值之间的线性转换。</span><span class="sxs-lookup"><span data-stu-id="c5e85-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearRectKeyFrame> create a smooth linear transition between values.</span></span>  
  
2.  <span data-ttu-id="c5e85-109">在下一步的末尾半秒，将使用的实例<xref:System.Windows.Media.Animation.DiscreteRectKeyFrame>类突然减小的矩形的高度。</span><span class="sxs-lookup"><span data-stu-id="c5e85-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> class to suddenly decrease the height of the rectangle.</span></span> <span data-ttu-id="c5e85-110">之类的离散的关键帧<xref:System.Windows.Media.Animation.DiscreteRectKeyFrame>突变值，即，高度减小快速发生的不是细微。</span><span class="sxs-lookup"><span data-stu-id="c5e85-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> create sudden changes between values, that is, the decrease in height occurs quickly and is not subtle.</span></span>  
  
3.  <span data-ttu-id="c5e85-111">在最终的两秒内，使用的是实例<xref:System.Windows.Media.Animation.SplineRectKeyFrame>类要更改回为其原始大小和位置的矩形。</span><span class="sxs-lookup"><span data-stu-id="c5e85-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame> class to change the rectangle back to its original size and position.</span></span> <span data-ttu-id="c5e85-112">之类的样条关键帧<xref:System.Windows.Media.Animation.SplineRectKeyFrame>创建变量的值根据值之间转换<xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="c5e85-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineRectKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="c5e85-113">在此示例中，变化开始时缓慢，然后以指数级加速，直到时间段结束。</span><span class="sxs-lookup"><span data-stu-id="c5e85-113">In this example, the change begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="c5e85-114">有关完整示例，请参阅[关键帧动画示例](http://go.microsoft.com/fwlink/?LinkID=160012)。</span><span class="sxs-lookup"><span data-stu-id="c5e85-114">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5e85-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5e85-115">See Also</span></span>  
 <xref:System.Windows.Media.RectangleGeometry>  
 <xref:System.Windows.Media.RectangleGeometry.Rect%2A>  
 <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>  
 [<span data-ttu-id="c5e85-116">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="c5e85-116">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="c5e85-117">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="c5e85-117">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
