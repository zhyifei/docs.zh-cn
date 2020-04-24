---
title: 如何：定义和引用资源
ms.date: 03/30/2017
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
ms.openlocfilehash: e33c86b03d8b18113f3a15b3ab251753958ff5b2
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646508"
---
# <a name="how-to-define-and-reference-a-resource"></a>如何：定义和引用资源

此示例演示如何使用 中[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]的属性定义资源并引用它。

## <a name="example"></a>示例

下面的示例定义了两种类型的资源：一种<xref:System.Windows.Media.SolidColorBrush>资源和多个<xref:System.Windows.Style>资源。 该<xref:System.Windows.Media.SolidColorBrush>资源`MyBrush`用于提供每个属性的值，每个属性都采用类型<xref:System.Windows.Media.Brush>值。 资源和<xref:System.Windows.Style>`PageBackground``TitleText`每个目标为特定的控件`Label`类型。 当资源键引用该样式资源并用于设置 中<xref:System.Windows.FrameworkElement.Style%2A>[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]定义的多个特定控件元素的属性时，样式在目标控件上设置各种不同的属性。

请注意，`Label`样式的 setter 中的一个属性也引用前面定义的`MyBrush`资源。 这是一种常见的技术，但请务必记住，资源按给定顺序解析并输入到资源字典中。 如果使用[静态资源标记扩展](staticresource-markup-extension.md)从其他资源中引用资源，则字典中找到的顺序也会请求资源。 确保引用的任何资源在资源集合中定义的任何资源都早于请求该资源的位置。 如有必要，可以使用[动态资源标记扩展](dynamicresource-markup-extension.md)在运行时引用资源，从而绕过资源引用的严格创建顺序，但您应该知道此动态资源技术具有性能后果。 有关详细信息，请参阅[XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)。

[!code-xaml[FEResource#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]

## <a name="see-also"></a>另请参阅

- [XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
