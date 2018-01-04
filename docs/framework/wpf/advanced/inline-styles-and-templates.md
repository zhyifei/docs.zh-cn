---
title: "内联样式和模板"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5dccf0b274121ff4fe88c9270119a2f631ffcf29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="inline-styles-and-templates"></a>内联样式和模板
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]提供<xref:System.Windows.Style>对象和模板对象 (<xref:System.Windows.FrameworkTemplate>子类) 作为在资源中定义的元素的可视外观的方法，以便它们可以使用多次。 为此中的属性[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]它们采用类型<xref:System.Windows.Style>和<xref:System.Windows.FrameworkTemplate>几乎总是建立了对现有样式和模板的资源引用而不是内联定义新的。  
  
## <a name="limitations-of-inline-styles-and-templates"></a>内联样式和模板的限制  
 在[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]，从技术上讲可以在两种方式之一设置样式和模板的属性。 你可以使用的特性语法来引用样式已在其中定义资源，例如`<`*对象*`Style="{StaticResource`*myResourceKey*`}" .../>`。 或者，可以使用属性元素语法来定义内联样式，例如：  
  
 `<`*对象*`>`  
  
 `<`*对象*`.Style>`  
  
 `<` `Style`  `.../>`  
  
 `</`*对象*`.Style>`  
  
 `</`*对象*`>`  
  
 特性用法是得更加常见。 样式会以内联方式定义和未定义中资源一定范围限定为仅包含的元素，不能重新使用一样轻松因为它具有没有资源键。 为资源定义的样式通常是更通用和有用，因此更符合常规[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]编程模型将在代码中的程序逻辑中分离从标记中的设计原则。  
  
 通常没有无需设置内联样式或模板，即使你只想要在该位置中使用该样式或模板。 可以采用样式或模板的大多数元素还支持内容的属性和内容模型。 如果你只使用任何逻辑树一次创建通过样式或模板，将能够更轻松地仅将该内容的属性填充直接标记中的等效子元素。 这将完全跳过的样式和模板的机制。  
  
 通过返回的对象的标记扩展其他语法也可使用的样式和模板。 具有可能的方案的两个此类扩展包括[TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md)和<xref:System.Windows.Data.Binding>。  
  
## <a name="see-also"></a>请参阅  
 [样式设置和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)
