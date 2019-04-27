---
title: 如何：沿着路径针对对象进行动画处理（累积偏移量的矩阵动画）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- offset accumulation [WPF]
- animation [WPF], objects along paths (matrix animation with offset accumulation)
- matrix animation with offset accumulation [WPF]
ms.assetid: 1bca90ef-9832-4128-8ed6-62908e7ec146
ms.openlocfilehash: 3e7b892e2a2215d26512850477844d71bce7fe09
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922689"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation-with-offset-accumulation"></a>如何：沿着路径针对对象进行动画处理（累积偏移量的矩阵动画）
此示例演示如何使用<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>类沿着路径针对对象进行动画处理，并让该动画会累积其偏移量值重复。  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>对象进行动画处理<xref:System.Windows.Media.MatrixTransform.Matrix%2A>属性的<xref:System.Windows.Media.MatrixTransform>应用于按钮。 因此，按钮会沿着曲线路径移动。  
  
 此外，该示例设置<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A>属性设置为`true`，这将导致动画矩阵动画重复时累计的偏移量。 由于偏移量累积，因此按钮会在动画重复时更快速地在屏幕上移动，而不是重置为起始位置。  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 请注意，尽管<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A>属性导致偏移量的值随着重复累计，但不会导致旋转值累积。 若要使旋转值累积，设置该动画<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A>并<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A>属性设置为`true`。  
  
 有关完整示例，请参阅[路径动画示例](https://go.microsoft.com/fwlink/?LinkID=160028)。 有关演示如何进行动画处理的示例<xref:System.Windows.Media.Matrix>没有偏移量进行累积路径上的值，请参阅[沿着路径针对对象 （矩阵动画） 进行动画处理](how-to-animate-an-object-along-a-path-matrix-animation.md)。  
  
## <a name="see-also"></a>请参阅

- [动画概述](animation-overview.md)
- [路径动画操作说明主题](path-animation-how-to-topics.md)
