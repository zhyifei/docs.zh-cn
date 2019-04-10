---
title: 如何：使用关键帧对三维旋转进行动画处理 (QuaternionAnimationUsingKeyFrames)
ms.date: 03/30/2017
helpviewer_keywords:
- 3-D translations [WPF], animating [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
- key frames [WPF], QuaternionAnimationUsingKeyFrames
- animation [WPF], 3-D translations [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
ms.openlocfilehash: 87176df26405a69cb2c3d63620def0575b750b52
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59338015"
---
# <a name="how-to-animate-a-3-d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a><span data-ttu-id="020a7-102">如何：使用关键帧对三维旋转进行动画处理 (QuaternionAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="020a7-102">How to: Animate a 3-D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>
<span data-ttu-id="020a7-103">在以下示例中，<xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames>用于使旋转三维对象。</span><span class="sxs-lookup"><span data-stu-id="020a7-103">In the following example, <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> is used to make a 3D object rotate.</span></span> <span data-ttu-id="020a7-104">此动画使用以下关键帧：</span><span class="sxs-lookup"><span data-stu-id="020a7-104">This animation uses the following key frames:</span></span>  
  
1. <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> <span data-ttu-id="020a7-105">用于创建值之间的平滑的线性插值。</span><span class="sxs-lookup"><span data-stu-id="020a7-105">is used to create a smooth, linear interpolation between values.</span></span>  
  
2. <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> <span data-ttu-id="020a7-106">用于之间创建突然"跳跃"的值 （没有内插法）。</span><span class="sxs-lookup"><span data-stu-id="020a7-106">is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> <span data-ttu-id="020a7-107">用于创建具体取决于值之间的变量转换<xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="020a7-107">is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="020a7-108">在下面的示例中，此部分动画启动较慢，但是即将结束的时间段，以指数方式加速。</span><span class="sxs-lookup"><span data-stu-id="020a7-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="020a7-109">示例</span><span class="sxs-lookup"><span data-stu-id="020a7-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="020a7-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="020a7-110">See also</span></span>

- [<span data-ttu-id="020a7-111">使用情节提要对三维旋转进行动画处理</span><span class="sxs-lookup"><span data-stu-id="020a7-111">Animate a 3-D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="020a7-112">使用 Rotation3DAnimation 对三维旋转进行动画处理</span><span class="sxs-lookup"><span data-stu-id="020a7-112">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="020a7-113">使用四元数对三维旋转进行动画处理</span><span class="sxs-lookup"><span data-stu-id="020a7-113">Animate a 3-D Rotation Using Quaternions</span></span>](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="020a7-114">使用关键帧对三维旋转进行动画处理 (Rotation3DAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="020a7-114">Animate a 3-D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [<span data-ttu-id="020a7-115">三维图形概述</span><span class="sxs-lookup"><span data-stu-id="020a7-115">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="020a7-116">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="020a7-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
