---
title: 内联样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
ms.openlocfilehash: b88ef444283f4e1e85009c59b39f3cc41965d300
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460005"
---
# <a name="inline-styles-and-templates"></a>内联样式和模板
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供 <xref:System.Windows.Style> 对象和模板对象（<xref:System.Windows.FrameworkTemplate> 子类）作为一种方法，用于在资源中定义元素的可视外观，以便可以多次使用它们。 出于此原因，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中采用类型 <xref:System.Windows.Style> 和 <xref:System.Windows.FrameworkTemplate> 的属性几乎始终对现有样式和模板进行资源引用，而不是以内联方式定义新的样式和模板。  
  
## <a name="limitations-of-inline-styles-and-templates"></a>内联样式和模板的限制  
 在 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]中，从技术上讲，可以通过以下两种方式之一设置样式和模板属性。 您可以使用特性语法来引用资源中定义的样式，例如 `<`*对象*`Style="{StaticResource`*myResourceKey*`}" .../>`。 或者，可以使用属性元素语法来定义内联样式，例如：  
  
 `<`*对象*`>`  
  
 `<`*对象*`.Style>`  
  
 `<` `Style``.../>`  
  
 `</`*对象*`.Style>`  
  
 `</`*对象*`>`  
  
 特性用法更常见。 在资源中以内联方式定义且未在资源中定义的样式必须仅限于包含元素，因为它没有资源键，所以不能轻易地重新使用。 通常，资源定义的样式更通用，更有用，更多的是将程序逻辑与代码中的程序逻辑分离的通用 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 编程模型原则。  
  
 通常，即使只是要在该位置使用该样式或模板，也没有理由设置样式或模板。 大多数可以采用样式或模板的元素也支持 content 属性和内容模型。 如果只使用通过样式设置或模板化一次创建的任何逻辑树，只需在直接标记中使用等效的子元素填充该内容属性即可。 这会完全跳过样式和模板机制。  
  
 对于样式和模板，也可以通过返回对象的标记扩展启用其他语法。 有两种可能的方案包括[TemplateBinding](templatebinding-markup-extension.md)和 <xref:System.Windows.Data.Binding>。  
  
## <a name="see-also"></a>请参阅

- [样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
