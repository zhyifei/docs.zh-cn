---
title: 如何：使用 PointAnimation 针对对象的位置进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], animation
- animation [WPF], PointAnimation
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
ms.openlocfilehash: 91447685988d91dfe86707c2cf265deabeb717b9
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43561038"
---
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a>如何：使用 PointAnimation 针对对象的位置进行动画处理
此示例演示如何使用<xref:System.Windows.Media.Animation.PointAnimation>类进行动画处理的对象沿<xref:System.Windows.Shapes.Path>。  
  
## <a name="example"></a>示例  
 以下示例将一个椭圆<xref:System.Windows.Shapes.Path>从一个点到另一个屏幕上。 该示例进行动画处理的位置<xref:System.Windows.Media.EllipseGeometry>通过使用<xref:System.Windows.Media.Animation.PointAnimation>进行动画处理<xref:System.Windows.Media.EllipseGeometry.Center%2A>属性。  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.Animation.PointAnimation>  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.EllipseGeometry>  
 <xref:System.Windows.Media.EllipseGeometry.Center%2A>  
 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [图形和多媒体](../../../../docs/framework/wpf/graphics-multimedia/index.md)  
 [帮助主题](../../../../docs/framework/wpf/graphics-multimedia/graphics-how-to-topics.md)  
 [动画和计时](https://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [帮助主题](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
