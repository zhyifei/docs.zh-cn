---
title: 如何：使用演示图板对三维旋转进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF]
- 3-D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3-D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
ms.openlocfilehash: a6cc8774c14d4b393b0d04822216c894e486ba66
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556700"
---
# <a name="how-to-animate-a-3-d-rotation-using-storyboards"></a>如何：使用演示图板对三维旋转进行动画处理
下面的示例演示如何使旋转时它"松动"通过进行动画处理的三维对象<xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A>和<xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A>属性<xref:System.Windows.Media.Media3D.AxisAngleRotation3D>对象。 这<xref:System.Windows.Media.Media3D.AxisAngleRotation3D>对象指定旋转转换三维对象，并因此对其属性进行动画处理创建所需旋转效果。 在情节提要，<xref:System.Windows.Media.Animation.DoubleAnimation>用于进行动画处理<xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A>属性中的，而<xref:System.Windows.Media.Animation.Vector3DAnimation>用于进行动画处理<xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A>属性。  
  
## <a name="example"></a>示例  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a>请参阅  
 [使用 Rotation3DAnimation 为 3D 旋转设置动画效果](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)  
 [使用关键帧为 3D 旋转设置动画效果 (Rotation3DAnimationUsingKeyFrames)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-key-frames.md)  
 [3D 图形概述](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [演示图板概述](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
