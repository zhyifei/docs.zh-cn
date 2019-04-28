---
title: 如何：使用几何路径旋转对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
ms.openlocfilehash: 3e35169da7297ec62e0114ab21f4ba81c0a656ea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651241"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a>如何：使用几何路径旋转对象
此示例演示如何旋转 （转动） 的对象沿几何路径定义的<xref:System.Windows.Media.PathGeometry>对象。  
  
## <a name="example"></a>示例  
 下面的示例使用三个<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>对象沿几何路径移动一个矩形。  
  
- 第一个<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>之间进行动画处理<xref:System.Windows.Media.RotateTransform>应用于矩形。 该动画会生成角度值。 它使矩形沿着路径的轮廓旋转（转动）。  
  
- 其他两个对象进行动画处理<xref:System.Windows.Media.TranslateTransform.X%2A>并<xref:System.Windows.Media.TranslateTransform.Y%2A>的值<xref:System.Windows.Media.TranslateTransform>应用于矩形。 它们使矩形沿路径水平和垂直移动。  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 另一种方法来使用几何路径旋转对象是使用<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>对象，并将其<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A>属性设置为`true`。 有关详细信息和示例，请参阅[使用几何路径 （矩阵动画） 来旋转对象](how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md)。  
  
 有关完整示例，请参阅[路径动画示例](https://go.microsoft.com/fwlink/?LinkID=160028)。  
  
## <a name="see-also"></a>请参阅

- [动画概述](animation-overview.md)
- [路径动画示例](https://go.microsoft.com/fwlink/?LinkID=160028)
- [路径动画操作说明主题](path-animation-how-to-topics.md)
