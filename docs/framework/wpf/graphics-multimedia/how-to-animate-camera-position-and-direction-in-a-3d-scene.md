---
title: "如何：在三维场景中对照相机位置和方向进行动画处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], camera position in 3-D scenes
- camera direction [WPF], animating in 3-D scenes
- 3-D scenes [WPF], animating camera position
- 3-D scenes [WPF], animating camera direction
- camera position [WPF], animating in 3-D scenes
- animation [WPF], camera direction in 3-D scenes
ms.assetid: 480224b7-a5e5-4165-ba7f-ef760ddff94a
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a8e80f1032e886d59240b74281c2ed87ad5743a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-camera-position-and-direction-in-a-3d-scene"></a>如何：在三维场景中对照相机位置和方向进行动画处理
下面的示例演示如何进行动画处理的照相机的位置和它所指在三维场景中的方向进行动画处理。 这可通过使用<xref:System.Windows.Media.Animation.Point3DAnimation>和<xref:System.Windows.Media.Animation.Vector3DAnimation>要进行动画处理<xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A>和<xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A>属性分别<xref:System.Windows.Media.Media3D.PerspectiveCamera>。 你可能使用如下动画更改以响应事件的场景观察的视图。  
  
## <a name="example"></a>示例  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationExample.xaml#pointvector3danimationexamplewholepage)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.Animation.Vector3DAnimation>  
 <xref:System.Windows.Media.Animation.Point3DAnimation>  
 [使用关键帧为照相机位置和方向设置动画效果](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-camera-position-and-direction-using-key-frames.md)  
 [3D 图形概述](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
