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
ms.openlocfilehash: 28471f9b42140a6c75b043d33939503528b63194
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112162"
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a>如何：使用关键帧对照相机位置和方向进行动画处理
在下面的示例中，<xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames>用于为 3D 场景中的位置<xref:System.Windows.Media.Media3D.PerspectiveCamera>设置动画。 此外，<xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames>还用于为摄像机在 3D 场景中指向的方向设置动画。 这两个动画都使用几个关键帧来创建一系列动画效果：  
  
1. <xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame><xref:System.Windows.Media.Animation.LinearVector3DKeyFrame>并用于在值之间创建平滑的线性插值。  
  
2. <xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame><xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame>并用于在值之间创建突然的"跳跃"（无插值）。  
  
3. <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame>并<xref:System.Windows.Media.Animation.SplineVector3DKeyFrame>用于根据<xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A>属性在值之间创建变量转换。 在下面的示例中，动画开始缓慢，但接近时段的末尾，速度呈指数级增长。  
  
## <a name="example"></a>示例  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>另请参阅

- [在 3D 场景中为照相机位置和方向设置动画效果](how-to-animate-camera-position-and-direction-in-a-3d-scene.md)
- [3D 图形概述](3-d-graphics-overview.md)
