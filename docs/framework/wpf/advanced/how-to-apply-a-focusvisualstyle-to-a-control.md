---
title: 如何：对控件应用 FocusVisualStyle
ms.date: 03/30/2017
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
ms.openlocfilehash: b44330ee7554f953389556bd62ff49db120b5db9
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459816"
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a>如何：对控件应用 FocusVisualStyle
此示例演示如何使用 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> 属性在资源中创建焦点视觉样式，并将样式应用于控件。  
  
## <a name="example"></a>示例  
 下面的示例定义了一个样式，该样式创建的附加控件组合仅适用于控件在 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]中的焦点。 这是通过以下方式实现的：使用 <xref:System.Windows.Controls.ControlTemplate>定义样式，然后在设置 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> 属性时将该样式作为资源引用。  
  
 在矩形区域外放置一个类似于边框的外部矩形。 除非进行了其他修改，否则样式的大小将使用应用了焦点视觉样式的矩形控件的 <xref:System.Windows.FrameworkElement.ActualHeight%2A> 和 <xref:System.Windows.FrameworkElement.ActualWidth%2A>。 此示例为 <xref:System.Windows.FrameworkElement.Margin%2A> 设置负值，使边框在聚焦控件之外稍微显示。  
  
 [!code-xaml[FEFocusVisualStyle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> 会附加到任何控件模板样式，无论是显式样式还是主题样式，都是如此。仍可使用 <xref:System.Windows.Controls.ControlTemplate> 创建控件的主样式，并将该样式设置为 <xref:System.Windows.FrameworkElement.Style%2A> 属性。  
  
 应在主题或 UI 中一致地使用焦点视觉样式，而不是为每个可获得焦点的元素使用不同的样式。 有关详细信息，请参阅为[控件中的焦点设置样式和 FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [为控件中的焦点设置样式以及 FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md)
