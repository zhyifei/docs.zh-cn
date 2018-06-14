---
title: mc:Ignorable 特性
ms.date: 03/30/2017
helpviewer_keywords:
- mc XML namespace prefix [WPF]
- mc:Ignorable attribute
- XML [WPF], mc namespace prefix
- XAML [WPF], mc:Ignorable attribute
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: acd9a6ef-b7ca-4146-abb6-60f3b366e9ec
ms.openlocfilehash: 7b8a2ef6e27bc6b25776157e59bef04b883fcb1a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546193"
---
# <a name="mcignorable-attribute"></a>mc:Ignorable 特性
指定哪些[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]可能忽略在标记文件中遇到的命名空间前缀[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器。 `mc:Ignorable`属性支持标记兼容性，为自定义命名空间映射和[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]版本控制。  
  
## <a name="xaml-attribute-usage-single-prefix"></a>XAML 属性用法 （单个前缀）  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a>XAML 属性用法 （两个前缀）  
  
```  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|*ignorablePrefix、 ignorablePrefix1，等等。*|根据 XML 1.0 规范任何有效的前缀字符串。|  
|*ignorableUri*|任何有效的 URI，指定命名空间中的，根据 XML 1.0 规范。|  
|*ThisElementCanBeIgnored*|可通过忽略的元素[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]处理器实现，如果基础类型不能解析。|  
  
## <a name="remarks"></a>备注  
 `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]命名空间前缀是要使用映射时的推荐的前缀约定[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]兼容性命名空间[!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)]。  
  
 元素或属性的元素名称的前缀部分被视为`mc:Ignorable`不会引发错误时由处理[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器。 如果该属性不能解析为基础类型或编程构造，则忽略该元素。 但是请注意，被忽略的元素仍可能会生成其他分析错误，因为将会不处理该元素的负面影响的其他元素要求。 例如，特定元素的内容模型可能需要一个子元素，但如果指定的子元素已在`mc:Ignorable`前缀和指定的子元素不能被解析为的类型，则[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器可能引发错误。  
  
 `mc:Ignorable` 仅适用于命名空间映射为标识符字符串。 `mc:Ignorable` 不适用于命名空间映射到指定的程序集[!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]命名空间和程序集 （或与程序集的当前可执行文件的默认值）。  
  
 如果你要实现[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器，处理器实现必须不会引发分析或处理的任何元素或由标识为前缀限定的属性的类型解析错误`mc:Ignorable`。 但仍然可以引发作为无法加载或处理，如前面的一个子元素示例某元素的间接后果的异常。  
  
 默认情况下，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器将忽略中被忽略的元素的内容。 但是，你可以指定另一个属性， [mc:ProcessContent 属性](../../../../docs/framework/wpf/advanced/mc-processcontent-attribute.md)，需要忽略元素的下一个可用的父元素内的内容的继续的处理。  
  
 可以在使用一个或多个空白字符作为分隔符，例如属性指定多个前缀： `mc:Ignorable="ignore1 ignore2"`。  
  
 [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)]命名空间定义其他元素和属性未记录的此区域内[!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]。 有关详细信息，请参阅[XML 标记兼容性规范](http://go.microsoft.com/fwlink/?LinkId=73824)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Markup.XamlReader>  
 [PresentationOptions:Freeze 特性](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)  
 [XAML 概述 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [WPF 中的文档](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
