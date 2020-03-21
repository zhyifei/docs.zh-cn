---
title: 如何：平移元素
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
ms.openlocfilehash: addff0e22fb3f27ea924887809c0635aeb3ad67d
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111967"
---
# <a name="how-to-translate-an-element"></a>如何：平移元素
此示例演示如何使用 转换（移动）元素<xref:System.Windows.Media.TranslateTransform>。  
  
 该<xref:System.Windows.Media.TranslateTransform>类对于在不支持绝对定位的面板内移动元素特别有用。 例如，<xref:System.Windows.Media.TranslateTransform>通过将 应用于元素的属性<xref:System.Windows.UIElement.RenderTransform%2A>，可以在<xref:System.Windows.Controls.StackPanel>或<xref:System.Windows.Controls.DockPanel>中移动元素。  
  
 使用<xref:System.Windows.Media.TranslateTransform.X%2A>属性<xref:System.Windows.Media.TranslateTransform>指定以像素为单位的数量沿 x 轴移动元素。 使用<xref:System.Windows.Media.TranslateTransform.Y%2A>属性指定沿 y 轴移动元素的数量（以像素为单位）。 最后，将<xref:System.Windows.Media.TranslateTransform>应用<xref:System.Windows.UIElement.RenderTransform%2A>到 元素的属性。  
  
 下面的示例使用<xref:System.Windows.Media.TranslateTransform>将元素向右移动 50 像素，向下移动 50 像素。  
  
## <a name="example"></a>示例  
 [!code-xaml[transformsSample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 有关完整示例，请参阅[2D 变换示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)。  
  
## <a name="see-also"></a>另请参阅

- [转换概述](transforms-overview.md)
