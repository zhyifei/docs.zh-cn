---
title: "如何：使用关键帧对三维旋转进行动画处理 (QuaternionAnimationUsingKeyFrames)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 3-D translations [WPF], animating [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
- key frames [WPF], QuaternionAnimationUsingKeyFrames
- animation [WPF], 3-D translations [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 89719cbcb72c5c24654962e9eb17a540224fd588
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-3-d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a>如何：使用关键帧对三维旋转进行动画处理 (QuaternionAnimationUsingKeyFrames)
在下面的示例中，<xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames>用于使三维旋转对象。 此动画使用以下关键帧：  
  
1.  <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>用于创建值之间的平滑、 线性内插。  
  
2.  <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>用于创建突然"跳转"值 （无内插） 之间。  
  
3.  <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>用于创建具体取决于值之间的变量过渡<xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A>属性。 在下面的示例中，这一部分动画启动较慢，但是时间段结束时，呈指数方式加速。  
  
## <a name="example"></a>示例  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>请参阅  
 [使用情节提要为 3D 旋转设置动画效果](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)  
 [使用 Rotation3DAnimation 为 3D 旋转设置动画效果](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)  
 [使用四元数为 3D 旋转设置动画效果](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-quaternions.md)  
 [使用关键帧为 3D 旋转设置动画效果 (Rotation3DAnimationUsingKeyFrames)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-key-frames.md)  
 [3D 图形概述](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [关键帧动画概述](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)
