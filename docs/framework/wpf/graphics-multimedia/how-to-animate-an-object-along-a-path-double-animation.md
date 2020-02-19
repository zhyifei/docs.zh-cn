---
title: 如何：沿着路径针对对象进行动画处理（双重动画）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (double animation)
- double animation [WPF]
ms.assetid: 5a3c4a99-f303-42ad-a52a-e4794bb1798e
ms.openlocfilehash: 084caac26fd68b6914ec3858652ec44557a0dbd7
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452852"
---
# <a name="how-to-animate-an-object-along-a-path-double-animation"></a>如何：沿着路径针对对象进行动画处理（双重动画）
此示例演示如何使用 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 类沿 <xref:System.Windows.Media.PathGeometry>定义的路径移动对象。  
  
## <a name="example"></a>示例  
 下面的示例使用两个 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 对象沿几何路径移动一个矩形：  
  
- 第一个 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 对应用于矩形的 <xref:System.Windows.Media.TranslateTransform> 的 <xref:System.Windows.Media.TranslateTransform.X%2A> 进行动画处理。 这使矩形沿路径水平移动。  
  
- 第二个 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 对应用于矩形的 <xref:System.Windows.Media.TranslateTransform> 的 <xref:System.Windows.Media.TranslateTransform.Y%2A> 进行动画处理。 这使矩形沿路径垂直移动。  
  
 [!code-xaml[PathAnimationGallery_snippet#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/doubleanimationusingpathexample.xaml#doubleanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/DoubleAnimationUsingPathExample.cs#doubleanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/DoubleAnimationUsingPathExample.vb#doubleanimationusingpathwholepage)]  
  
 有关完整示例，请参阅[路径动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)。  
  
 使用几何路径移动对象的另一种方法是使用 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 对象。 有关示例，请参阅[沿着路径对对象进行动画处理（矩阵动画）](how-to-animate-an-object-along-a-path-matrix-animation.md)。  
  
## <a name="see-also"></a>另请参阅

- [动画概述](animation-overview.md)
- [路径动画操作说明主题](path-animation-how-to-topics.md)
