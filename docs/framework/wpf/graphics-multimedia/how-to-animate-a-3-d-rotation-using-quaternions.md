---
title: 如何：使用四元数为 3D 旋转设置动画
ms.date: 03/30/2017
helpviewer_keywords:
- quaternions [WPF]
- animation [WPF], 3D translations [WPF], with quaternions
- 3D translations [WPF], animating [WPF], with quaternions
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
ms.openlocfilehash: 0d229b0a714cc53459943fae751ab4d4f787d7d8
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112240"
---
# <a name="how-to-animate-a-3d-rotation-using-quaternions"></a>如何：使用四元数为 3D 旋转设置动画
此示例演示如何使用四元数为 3D 对象的旋转设置动画。  
  
 下面的代码显示了用作<xref:System.Windows.Media.Media3D.QuaternionRotation3D>属性的值。 <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> <xref:System.Windows.Media.Media3D.RotateTransform3D>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 使用<xref:System.Windows.Media.Media3D.QuaternionRotation3D>下面的代码在<xref:System.Windows.Media.Animation.Storyboard><xref:System.Windows.Media.Animation.QuaternionAnimation>中使用 动画。  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a>示例  
 以下代码显示整个示例。  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a>另请参阅

- [动画概述](animation-overview.md)
- [创建 3D 场景](how-to-create-a-3-d-scene.md)
- [3D 图形概述](3-d-graphics-overview.md)
- [转换概述](transforms-overview.md)
- [使用情节提要为 3D 旋转设置动画](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [使用旋转3D动画为 3D 旋转设置动画](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
