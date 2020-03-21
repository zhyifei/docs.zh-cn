---
title: 如何：使用关键帧为 3D 旋转设置动画（四元动画使用关键帧）
ms.date: 03/30/2017
helpviewer_keywords:
- 3D translations [WPF], animating [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
- key frames [WPF], QuaternionAnimationUsingKeyFrames
- animation [WPF], 3D translations [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
ms.openlocfilehash: 5273183aaa49a743cc401dec0b4b16bae09e3129
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112292"
---
# <a name="how-to-animate-a-3d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a><span data-ttu-id="2a569-102">如何：使用关键帧为 3D 旋转设置动画（四元动画使用关键帧）</span><span class="sxs-lookup"><span data-stu-id="2a569-102">How to: Animate a 3D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>
<span data-ttu-id="2a569-103">在下面的示例中，<xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames>用于使 3D 对象旋转。</span><span class="sxs-lookup"><span data-stu-id="2a569-103">In the following example, <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> is used to make a 3D object rotate.</span></span> <span data-ttu-id="2a569-104">此动画使用以下关键帧：</span><span class="sxs-lookup"><span data-stu-id="2a569-104">This animation uses the following key frames:</span></span>  
  
1. <span data-ttu-id="2a569-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>用于在值之间创建平滑的线性插值。</span><span class="sxs-lookup"><span data-stu-id="2a569-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> is used to create a smooth, linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="2a569-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>用于在值之间创建突然的"跳跃"（无插值）。</span><span class="sxs-lookup"><span data-stu-id="2a569-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <span data-ttu-id="2a569-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>用于根据<xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A>属性在值之间创建变量转换。</span><span class="sxs-lookup"><span data-stu-id="2a569-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="2a569-108">在下面的示例中，动画的这一部分开始缓慢，但接近时段的末尾，速度呈指数级增长。</span><span class="sxs-lookup"><span data-stu-id="2a569-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a569-109">示例</span><span class="sxs-lookup"><span data-stu-id="2a569-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="2a569-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a569-110">See also</span></span>

- [<span data-ttu-id="2a569-111">使用情节提要为 3D 旋转设置动画</span><span class="sxs-lookup"><span data-stu-id="2a569-111">Animate a 3D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="2a569-112">使用旋转3D动画为 3D 旋转设置动画</span><span class="sxs-lookup"><span data-stu-id="2a569-112">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="2a569-113">使用四元数为 3D 旋转设置动画</span><span class="sxs-lookup"><span data-stu-id="2a569-113">Animate a 3D Rotation Using Quaternions</span></span>](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="2a569-114">使用关键帧为 3D 旋转设置动画（旋转3D动画使用关键帧）</span><span class="sxs-lookup"><span data-stu-id="2a569-114">Animate a 3D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [<span data-ttu-id="2a569-115">3D 图形概述</span><span class="sxs-lookup"><span data-stu-id="2a569-115">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="2a569-116">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="2a569-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
