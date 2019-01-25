---
title: 如何：使用四元数对三维旋转进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- quaternions [WPF]
- animation [WPF], 3-D translations [WPF], with quaternions
- 3-D translations [WPF], animating [WPF], with quaternions
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
ms.openlocfilehash: df51db324bffc038bc585b6d977a82d54feefb3b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550924"
---
# <a name="how-to-animate-a-3-d-rotation-using-quaternions"></a>如何：使用四元数对三维旋转进行动画处理
此示例演示如何使用四元数对三维对象的旋转进行动画处理。  
  
 下面的代码显示<xref:System.Windows.Media.Media3D.QuaternionRotation3D>的值作为<xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A>属性的<xref:System.Windows.Media.Media3D.RotateTransform3D>。  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 这<xref:System.Windows.Media.Media3D.QuaternionRotation3D>进行动画处理<xref:System.Windows.Media.Animation.QuaternionAnimation>内<xref:System.Windows.Media.Animation.Storyboard>使用下面的代码。  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a>示例  
 下面的代码演示了整个示例。  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a>请参阅
- [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [创建 3D 场景](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)
- [3D 图形概述](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
- [转换概述](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
- [使用情节提要为 3D 旋转设置动画效果](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)
- [使用 Rotation3DAnimation 为 3D 旋转设置动画效果](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
