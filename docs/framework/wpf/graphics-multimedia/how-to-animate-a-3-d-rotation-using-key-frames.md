---
title: 如何：使用关键帧为 3D 旋转设置动画
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3D translations [WPF], with key frames (Rotation3DAnimation)
- key frames [WPF], Rotation3DAnimation
- 3D translations [WPF], animating [WPF], with key frames (Rotation3DAnimation)
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
ms.openlocfilehash: 2b9059df079125c34c70237c0f600751020044c6
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112305"
---
# <a name="how-to-animate-a-3d-rotation-using-key-frames"></a>如何：使用关键帧为 3D 旋转设置动画
在下面的示例中，<xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames>用于使 3D 对象旋转，而其旋转轴动画会导致"摆动"。 此动画使用以下关键帧：  
  
1. <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>用于在值之间创建平滑的线性插值。  
  
2. <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>用于在值之间创建突然的"跳跃"（无插值）。  
  
3. <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>用于根据<xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A>属性在值之间创建变量转换。 在下面的示例中，动画的这一部分开始缓慢，但接近时段的末尾，速度呈指数级增长。  
  
## <a name="example"></a>示例  
 [!code-xaml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>另请参阅

- [3D 图形概述](3-d-graphics-overview.md)
- [关键帧动画概述](key-frame-animations-overview.md)
- [使用情节提要为 3D 旋转设置动画](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [使用旋转3D动画为 3D 旋转设置动画](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [使用四元数为 3D 旋转设置动画](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [使用关键帧为 3D 旋转设置动画（四元动画使用关键帧）](animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)
