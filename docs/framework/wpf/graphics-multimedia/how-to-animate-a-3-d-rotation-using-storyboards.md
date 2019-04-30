---
title: 如何：使用情节提要对三维旋转进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF]
- 3-D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3-D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
ms.openlocfilehash: 03b01205f1a31426a01b09533b350682c384df4b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024750"
---
# <a name="how-to-animate-a-3-d-rotation-using-storyboards"></a>如何：使用情节提要对三维旋转进行动画处理
下面的示例演示如何创建旋转时它"松动"通过进行动画处理的三维对象<xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A>并<xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A>的属性<xref:System.Windows.Media.Media3D.AxisAngleRotation3D>对象。 这<xref:System.Windows.Media.Media3D.AxisAngleRotation3D>对象指定的旋转变换的三维对象，并因此对其属性进行动画处理创建需的旋转效果。 在情节提要<xref:System.Windows.Media.Animation.DoubleAnimation>用于进行动画处理<xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A>属性，同时<xref:System.Windows.Media.Animation.Vector3DAnimation>用于进行动画处理<xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A>属性。  
  
## <a name="example"></a>示例  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a>请参阅

- [使用 Rotation3DAnimation 为 3D 旋转设置动画效果](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [使用关键帧为 3D 旋转设置动画效果 (Rotation3DAnimationUsingKeyFrames)](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [3D 图形概述](3-d-graphics-overview.md)
- [演示图板概述](storyboards-overview.md)
