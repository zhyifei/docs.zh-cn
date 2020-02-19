---
title: 如何：沿着路径针对对象进行动画处理（点动画）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
ms.openlocfilehash: eff0c24a9369ffaa0cfca1cc46af4eff39f58a38
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452891"
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a>如何：沿着路径针对对象进行动画处理（点动画）
此示例演示如何使用 <xref:System.Windows.Media.Animation.PointAnimationUsingPath> 对象沿着曲线路径对 <xref:System.Windows.Point> 进行动画处理。  
  
## <a name="example"></a>示例  
 下面的示例沿着 <xref:System.Windows.Media.PathGeometry>定义的路径移动 <xref:System.Windows.Media.EllipseGeometry>。 省略号几何图形的 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 属性，它采用 <xref:System.Windows.Point> 值，指定其位置;若要移动椭圆几何，请对其 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 属性进行动画处理。 该示例使用 <xref:System.Windows.Media.Animation.PointAnimationUsingPath> 对 <xref:System.Windows.Media.EllipseGeometry> 对象的 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 属性进行动画处理。  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 有关完整示例，请参阅[路径动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)。  
  
 前面示例的代码版本使用 <xref:System.Windows.Media.Animation.Storyboard> 对 <xref:System.Windows.Media.EllipseGeometry>进行动画处理，即使只应用了一个动画。 <xref:System.Windows.Media.Animation.Storyboard> 通常是应用多个动画的最简单方法，因为这些动画可以通过相同的 <xref:System.Windows.Media.Animation.Storyboard>来控制。 但是，使用代码时，将单个动画应用于属性的更简单方法是使用 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 方法。 有关示例，请参阅[在不使用情节提要的情况下对属性进行动画处理](how-to-animate-a-property-without-using-a-storyboard.md)。  
  
## <a name="see-also"></a>另请参阅

- [路径动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [动画概述](animation-overview.md)
- [路径动画操作说明主题](path-animation-how-to-topics.md)
