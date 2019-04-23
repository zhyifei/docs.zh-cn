---
title: 如何：使用关键帧对照相机位置和方向进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera direction with key frames
- key frames [WPF], animating camera direction
- animation [WPF], camera position with key frames
- camera position [WPF], animating with key frames
- key frames [WPF], animating camera position
- camera direction [WPF], animating with key frames
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
ms.openlocfilehash: 44464cc314d649516998338e36c1b523101ac4e2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59346075"
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a><span data-ttu-id="abae3-102">如何：使用关键帧对照相机位置和方向进行动画处理</span><span class="sxs-lookup"><span data-stu-id="abae3-102">How to: Animate Camera Position and Direction Using Key Frames</span></span>
<span data-ttu-id="abae3-103">在以下示例中，<xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames>使用的位置进行动画处理<xref:System.Windows.Media.Media3D.PerspectiveCamera>三维场景中。</span><span class="sxs-lookup"><span data-stu-id="abae3-103">In the following example, <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> is used to animate the position of a <xref:System.Windows.Media.Media3D.PerspectiveCamera> in a 3D scene.</span></span> <span data-ttu-id="abae3-104">此外，<xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames>用于对三维场景中指照相机的方向进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="abae3-104">In addition, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> is used to animate the direction the camera is pointing in the 3D scene.</span></span> <span data-ttu-id="abae3-105">这两个这些动画使用几个关键帧来创建一系列的动画效果：</span><span class="sxs-lookup"><span data-stu-id="abae3-105">Both of these animations use several key frames which create a series of animation effects:</span></span>  
  
1. <span data-ttu-id="abae3-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> 和<xref:System.Windows.Media.Animation.LinearVector3DKeyFrame>用于创建值之间的平滑的线性插值。</span><span class="sxs-lookup"><span data-stu-id="abae3-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> and <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> are used to create a smooth, linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="abae3-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> 和<xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame>用于之间创建突然"跳跃"的值 （没有内插法）。</span><span class="sxs-lookup"><span data-stu-id="abae3-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> are used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <span data-ttu-id="abae3-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> 并<xref:System.Windows.Media.Animation.SplineVector3DKeyFrame>用来创建具体取决于值之间的变量转换<xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="abae3-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> are used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="abae3-109">以下示例中，在动画启动较慢，但是即将结束的时间段，以指数方式加速。</span><span class="sxs-lookup"><span data-stu-id="abae3-109">In the example below, the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="abae3-110">示例</span><span class="sxs-lookup"><span data-stu-id="abae3-110">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="abae3-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="abae3-111">See also</span></span>

- [<span data-ttu-id="abae3-112">在 3D 场景中为照相机位置和方向设置动画效果</span><span class="sxs-lookup"><span data-stu-id="abae3-112">Animate Camera Position and Direction in a 3D Scene</span></span>](how-to-animate-camera-position-and-direction-in-a-3d-scene.md)
- [<span data-ttu-id="abae3-113">3D 图形概述</span><span class="sxs-lookup"><span data-stu-id="abae3-113">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
