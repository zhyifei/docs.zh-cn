---
title: 如何：使元素就地旋转
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: 2e72389a11e48629c2763fcbd9f7b1945ffff5dd
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452787"
---
# <a name="how-to-make-an-element-spin-in-place"></a>如何：使元素就地旋转
此示例演示如何使用 <xref:System.Windows.Media.RotateTransform> 和 <xref:System.Windows.Media.Animation.DoubleAnimation>使元素旋转。  
  
 下面的示例将 <xref:System.Windows.Media.RotateTransform> 应用到元素的 <xref:System.Windows.UIElement.RenderTransform%2A> 属性。 该示例使用 <xref:System.Windows.Media.Animation.DoubleAnimation> 对 <xref:System.Windows.Media.RotateTransform>的 <xref:System.Windows.Media.RotateTransform.Angle%2A> 进行动画处理。 为了使元素就地旋转，此示例将元素的 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 属性设置为点（0.5，0.5）。  
  
## <a name="example"></a>示例  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 有关包含更多转换示例的完整示例，请参阅二维[转换示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)。  
  
## <a name="see-also"></a>另请参阅

- [动画概述](animation-overview.md)
- [转换概述](transforms-overview.md)
