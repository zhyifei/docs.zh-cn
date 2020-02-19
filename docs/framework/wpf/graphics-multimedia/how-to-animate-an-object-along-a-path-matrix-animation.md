---
title: 如何：沿着路径针对对象进行动画处理（矩阵动画）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (matrix animation)
- matrix animation [WPF]
ms.assetid: 7000e697-1414-468c-b915-cf66062fc49e
ms.openlocfilehash: 7dfc233fe60e1cea293edc44a2bba79dc6962f7c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452904"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation"></a>如何：沿着路径针对对象进行动画处理（矩阵动画）
此示例演示如何使用 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 类沿着 <xref:System.Windows.Media.PathGeometry>定义的路径对对象进行动画处理。  
  
## <a name="example"></a>示例  
 下面的示例通过执行以下操作沿着路径针对对象进行动画处理：  
  
- 将 <xref:System.Windows.Media.MatrixTransform> 应用于对象，以便移动它。  
  
- 使用 <xref:System.Windows.Media.PathGeometry>定义路径。  
  
- 创建 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>，并使用它对 <xref:System.Windows.Media.MatrixTransform>的 <xref:System.Windows.Media.Matrix> 属性进行动画处理。 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 采用 <xref:System.Windows.Media.PathGeometry> 并使用它来生成 <xref:System.Windows.Media.Matrix> 值。  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexample.xaml#matrixanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExample.cs#matrixanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExample.vb#matrixanimationusingpathwholepage)]  
  
 有关完整示例，请参阅[路径动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)。 有关几何路径的详细信息，请参阅[几何概述](geometry-overview.md)。  
  
## <a name="see-also"></a>另请参阅

- [动画概述](animation-overview.md)
- [路径动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [路径动画操作说明主题](path-animation-how-to-topics.md)
