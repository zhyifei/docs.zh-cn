---
title: 如何：向对象应用多个变换
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- grouping Transform objects [WPF]
- Transform objects [WPF], grouping
- graphics [WPF], grouping Transform objects
- TransformGroup [WPF]
ms.assetid: 98cd1921-12bc-4bf5-8193-529228fb7402
ms.openlocfilehash: 544d0a26f24e5ad4ed7e2e3cfa25f8e15d1be446
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452826"
---
# <a name="how-to-apply-multiple-transforms-to-an-object"></a>如何：向对象应用多个变换
此示例演示如何使用 <xref:System.Windows.Media.TransformGroup> 将两个或多个 <xref:System.Windows.Media.Transform> 对象组合成单个复合 <xref:System.Windows.Media.Transform>。  
  
## <a name="example"></a>示例  
 下面的示例使用 <xref:System.Windows.Media.TransformGroup> 向 <xref:System.Windows.Controls.Button>应用 <xref:System.Windows.Media.ScaleTransform> 和 <xref:System.Windows.Media.RotateTransform>。  
  
 [!code-xaml[Transforms_snip#MultipleTransformExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MultipleTransformExample.xaml#multipletransformexamplewholepage)]  
  
 [!code-csharp[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/MultipleTransformsExample.cs#multipletransformscodeexamplewholepage)]
 [!code-vb[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/MultipleTransformsExample.vb#multipletransformscodeexamplewholepage)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.UIElement.RenderTransform%2A>
- <xref:System.Windows.Media.TransformGroup>
- [转换概述](transforms-overview.md)
- [2D 转换示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)
