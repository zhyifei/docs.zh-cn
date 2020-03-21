---
title: 如何：使元素就地旋转
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: a1b515822391de08ec8ed8ff0ff1f0086874dc02
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112071"
---
# <a name="how-to-make-an-element-spin-in-place"></a>如何：使元素就地旋转
此示例演示如何使用 和<xref:System.Windows.Media.RotateTransform>使元素旋转。 <xref:System.Windows.Media.Animation.DoubleAnimation>  
  
 下面的示例将 应用于<xref:System.Windows.Media.RotateTransform><xref:System.Windows.UIElement.RenderTransform%2A>元素的属性。 该示例使用<xref:System.Windows.Media.Animation.DoubleAnimation><xref:System.Windows.Media.RotateTransform.Angle%2A><xref:System.Windows.Media.RotateTransform> 要使元素就位旋转，该示例将元素的属性设置<xref:System.Windows.UIElement.RenderTransformOrigin%2A>到点 （0.5， 0.5）。  
  
## <a name="example"></a>示例  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 有关包含更多变换示例的完整示例，请参阅[2D 变换示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)。  
  
## <a name="see-also"></a>另请参阅

- [动画概述](animation-overview.md)
- [转换概述](transforms-overview.md)
