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
ms.openlocfilehash: 836f61e062b921c7e51166a35d8169f903fcbab9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738295"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation"></a>如何：沿着路径针对对象进行动画处理（矩阵动画）
此示例演示如何使用<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>类沿着由定义路径针对对象进行动画处理<xref:System.Windows.Media.PathGeometry>。  
  
## <a name="example"></a>示例  
 下面的示例通过执行以下操作沿着路径针对对象进行动画处理：  
  
-   适用<xref:System.Windows.Media.MatrixTransform>对象以将其移到。  
  
-   通过使用定义的路径<xref:System.Windows.Media.PathGeometry>。  
  
-   创建<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>并使用它来进行动画处理<xref:System.Windows.Media.Matrix>属性的<xref:System.Windows.Media.MatrixTransform>。 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>采用<xref:System.Windows.Media.PathGeometry>并使用它来生成<xref:System.Windows.Media.Matrix>值。  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexample.xaml#matrixanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExample.cs#matrixanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExample.vb#matrixanimationusingpathwholepage)]  
  
 有关完整示例，请参阅[路径动画示例](https://go.microsoft.com/fwlink/?LinkID=160028)。 有关几何路径的详细信息，请参阅[几何概述](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)。  
  
## <a name="see-also"></a>请参阅
- [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [路径动画示例](https://go.microsoft.com/fwlink/?LinkID=160028)
- [路径动画操作说明主题](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
