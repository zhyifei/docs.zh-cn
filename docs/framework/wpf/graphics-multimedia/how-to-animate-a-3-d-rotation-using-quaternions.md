---
title: "如何：使用四元数对三维旋转进行动画处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- quaternions [WPF]
- animation [WPF], 3-D translations [WPF], with quaternions
- 3-D translations [WPF], animating [WPF], with quaternions
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4301f4ffc935c6c72509638561ffa40b7744b94a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-3-d-rotation-using-quaternions"></a>如何：使用四元数对三维旋转进行动画处理
此示例演示如何进行动画处理的三维对象使用四元数旋转。  
  
 下面的代码显示<xref:System.Windows.Media.Media3D.QuaternionRotation3D>用作的值<xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A>属性<xref:System.Windows.Media.Media3D.RotateTransform3D>。  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 这<xref:System.Windows.Media.Media3D.QuaternionRotation3D>进行动画处理<xref:System.Windows.Media.Animation.QuaternionAnimation>内<xref:System.Windows.Media.Animation.Storyboard>使用下面的代码。  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a>示例  
 下面的代码演示了整个示例。  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a>请参阅  
 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [创建 3D 场景](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [3D 图形概述](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [转换概述](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [使用情节提要为 3D 旋转设置动画效果](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)  
 [使用 Rotation3DAnimation 为 3D 旋转设置动画效果](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
