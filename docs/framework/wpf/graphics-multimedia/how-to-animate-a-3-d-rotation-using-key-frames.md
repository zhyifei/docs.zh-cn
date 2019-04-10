---
title: 如何：使用关键帧对三维旋转进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3-D translations [WPF], with key frames (Rotation3DAnimation)
- key frames [WPF], Rotation3DAnimation
- 3-D translations [WPF], animating [WPF], with key frames (Rotation3DAnimation)
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
ms.openlocfilehash: e72ec94f830f0f5001a77e7492aa1326a47b309d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59297988"
---
# <a name="how-to-animate-a-3-d-rotation-using-key-frames"></a><span data-ttu-id="63f33-102">如何：使用关键帧对三维旋转进行动画处理</span><span class="sxs-lookup"><span data-stu-id="63f33-102">How to: Animate a 3-D Rotation Using Key Frames</span></span>
<span data-ttu-id="63f33-103">在以下示例中，<xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames>用于使三维旋转进行动画处理的旋转轴，从而导致"原因"时对象。</span><span class="sxs-lookup"><span data-stu-id="63f33-103">In the following example, <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> is used to make a 3D object rotate while its axis of rotation animates resulting in a "wobble".</span></span> <span data-ttu-id="63f33-104">此动画使用以下关键帧：</span><span class="sxs-lookup"><span data-stu-id="63f33-104">This animation uses the following key frames:</span></span>  
  
1. <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> <span data-ttu-id="63f33-105">用于创建值之间的平滑的线性插值。</span><span class="sxs-lookup"><span data-stu-id="63f33-105">is used to create a smooth, linear interpolation between values.</span></span>  
  
2. <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> <span data-ttu-id="63f33-106">用于之间创建突然"跳跃"的值 （没有内插法）。</span><span class="sxs-lookup"><span data-stu-id="63f33-106">is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> <span data-ttu-id="63f33-107">用于创建具体取决于值之间的变量转换<xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="63f33-107">is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="63f33-108">在下面的示例中，此部分动画启动较慢，但是即将结束的时间段，以指数方式加速。</span><span class="sxs-lookup"><span data-stu-id="63f33-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63f33-109">示例</span><span class="sxs-lookup"><span data-stu-id="63f33-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="63f33-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="63f33-110">See also</span></span>

- [<span data-ttu-id="63f33-111">三维图形概述</span><span class="sxs-lookup"><span data-stu-id="63f33-111">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="63f33-112">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="63f33-112">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="63f33-113">使用情节提要对三维旋转进行动画处理</span><span class="sxs-lookup"><span data-stu-id="63f33-113">Animate a 3-D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="63f33-114">使用 Rotation3DAnimation 对三维旋转进行动画处理</span><span class="sxs-lookup"><span data-stu-id="63f33-114">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="63f33-115">使用四元数对三维旋转进行动画处理</span><span class="sxs-lookup"><span data-stu-id="63f33-115">Animate a 3-D Rotation Using Quaternions</span></span>](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="63f33-116">使用关键帧对三维旋转进行动画处理 (QuaternionAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="63f33-116">Animate a 3-D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>](animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)
