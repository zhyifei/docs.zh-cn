---
title: 如何：在三维场景中对照相机位置和方向进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera position in 3D scenes
- camera direction [WPF], animating in 3D scenes
- 3D scenes [WPF], animating camera position
- 3D scenes [WPF], animating camera direction
- camera position [WPF], animating in 3D scenes
- animation [WPF], camera direction in 3D scenes
ms.assetid: 480224b7-a5e5-4165-ba7f-ef760ddff94a
ms.openlocfilehash: 5ce94e154cd5aa29b59260f893ec2b63a08db0fc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112202"
---
# <a name="how-to-animate-camera-position-and-direction-in-a-3d-scene"></a>如何：在三维场景中对照相机位置和方向进行动画处理
下面的示例演示如何为摄像机的位置设置动画，并为它在 3D 场景中指向的方向设置动画。 这是通过使用<xref:System.Windows.Media.Animation.Point3DAnimation>和<xref:System.Windows.Media.Animation.Vector3DAnimation>分别为<xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A>和<xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A>属性设置动画来完成<xref:System.Windows.Media.Media3D.PerspectiveCamera>的。 您可以使用这样的动画来更改旁观者对场景的视图，以响应事件。  
  
## <a name="example"></a>示例  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationExample.xaml#pointvector3danimationexamplewholepage)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Animation.Vector3DAnimation>
- <xref:System.Windows.Media.Animation.Point3DAnimation>
- [使用关键帧为照相机位置和方向设置动画效果](how-to-animate-camera-position-and-direction-using-key-frames.md)
- [3D 图形概述](3-d-graphics-overview.md)
