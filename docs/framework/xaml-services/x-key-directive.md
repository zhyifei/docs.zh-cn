---
title: "x:Key 指令"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xKey
- Key
- x:Key
helpviewer_keywords:
- x:Key attribute [XAML Services]
- Key attribute in XAML [XAML Services]
- XAML [XAML Services], x:Key attribute
ms.assetid: 1985cd45-f197-42d5-b75e-886add64b248
caps.latest.revision: "25"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 5e2ad03fcb52db1ffdd01849381a392187082991
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="xkey-directive"></a>x:Key 指令
唯一标识元素创建和引用 XAML 定义的字典中。 添加`x:Key`到 XAML 对象元素的值是标识资源字典中，例如在 WPF 中的资源的最常见方法<xref:System.Windows.ResourceDictionary>。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```  
<object x:Key="stringKeyValue".../>  
-or-  
<object x:Key="{markupExtensionUsage}".../>  
```  
  
## <a name="xaml-attribute-usage-wpf-specific"></a>XAML 属性用法 （特定于 WPF）  
  
```  
<object.Resources>  
  <object x:Key="stringKeyValue".../>  
</object.Resources>  
-or-  
<object.Resources>  
  <object x:Key="{markupExtensionUsage}".../>  
</object.Resources>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`stringKeyValue`|要用作键的文本字符串。 文本字符串必须符合[XamlName 语法](../../../docs/framework/xaml-services/xamlname-grammar.md)。|  
|`markupExtensionUsage`|在标记扩展的分隔符 {} 中，标记扩展用法，提供要使用作为键的对象。 请参阅“备注”。|  
  
## <a name="remarks"></a>备注  
 `x:Key`支持 XAML 资源字典概念。 作为一种语言的 XAML 未定义的资源字典实现，从左到特定的 UI 框架。 若要了解有关如何在 WPF 中实现 XAML 资源字典的详细信息，请参阅[XAML 资源](../../../docs/framework/wpf/advanced/xaml-resources.md)。  
  
 在 XAML 2006 和 WPF，`x:Key`必须作为属性提供。 你仍然可以使用非字符串键，但这要求以便提供属性窗体中的非字符串值的标记扩展用法。 如果你使用 XAML 2009`x:Key`可以被指定为元素，以显式支持键控的对象类型以外的字典字符串而无需中间的标记扩展。 请参阅本主题中的"XAML 2009"一节。 备注部分的其余部分特别适用于 XAML 2006 实现。  
  
 属性值的`x:Key`可以中定义的任何字符串[XamlName 语法](../../../docs/framework/xaml-services/xamlname-grammar.md)也可以是计算通过标记扩展的对象。 有关从 WPF 示例，请参阅"WPF 用法注释"。  
  
 是一个父元素的子元素<xref:System.Collections.IDictionary>实现通常必须包括`x:Key`指定唯一的键值，该字典中的属性。 框架可能实现使用别名键属性，用于替换`x:Key`对特定类型; 定义此类属性的类型应使用进行特性化<xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>。  
  
 指定的代码等效项`x:Key`是适用于基础的关键<xref:System.Collections.IDictionary>。 例如， `x:Key` ，在应用中标记的值等效 WPF 中的资源为`key`参数<xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType>时将资源添加到 WPF<xref:System.Windows.ResourceDictionary>在代码中。  
  
## <a name="wpf-usage-notes"></a>WPF 用法说明  
 子对象的父对象，该对象<xref:System.Collections.IDictionary>实现，如 WPF <xref:System.Windows.ResourceDictionary>，通常必须包括`x:Key`属性和密钥值内必须是唯一的字典。 有两个值得注意的例外情况：  
  
-   一些 WPF 类型声明用于字典使用情况的隐式密钥。 例如，<xref:System.Windows.Style>与<xref:System.Windows.Style.TargetType%2A>，或<xref:System.Windows.DataTemplate>与<xref:System.Windows.DataTemplate.DataType%2A>，可能处于<xref:System.Windows.ResourceDictionary>并使用隐式密钥。  
  
-   WPF 支持合并的资源字典概念。 密钥可以共享之间合并的字典，并且可以使用访问的共享密钥行为<xref:System.Windows.FrameworkContentElement.FindResource%2A>。 有关详细信息，请参阅[合并资源字典](../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md)。  
  
 总体 WPF XAML 实现和应用程序模型中，由 XAML 标记编译器进行不检查唯一性。 相反，丢失或非唯一`x:Key`值会导致加载时间 XAML 分析器错误。 但是，[!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)]处理的字典中的 WPF 通常可以在设计阶段注意此类错误。  
  
 请注意，在语法中所示，<xref:System.Windows.ResourceDictionary>对象是隐式的 WPF XAML 处理器如何生成一个集合来填充<xref:System.Windows.FrameworkElement.Resources%2A>集合。 A<xref:System.Windows.ResourceDictionary>不通常用作显式的元素在标记中，但也可以是在某些情况下，如果想为清楚起见 (它将集合对象元素之间<xref:System.Windows.FrameworkElement.Resources%2A>属性元素，并在其中的项填充字典）。 有关为什么集合对象几乎始终是隐式元素标记中的信息，请参阅[在详细信息的 XAML 语法](../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)。  
  
 在 WPF XAML 实现中，资源字典键的处理由定义<xref:System.Windows.ResourceKey>抽象类。 但是，WPF XAML 处理器生成不同基础的扩展类型，密钥基于它们的用法。 例如，为项<xref:System.Windows.DataTemplate>或任何派生的类分别进行处理，并且生成一个不同<xref:System.Windows.DataTemplateKey>对象。  
  
 键和名称使用不同的指令和语言元素 (`x:Key`与`x:Name`) 中的基本的 XAML 定义。 键和名称也使用不同的情况下的 WPF 定义和应用程序的这些概念。 有关详细信息，请参阅[WPF XAML Namescopes](../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)。  
  
 如前面所述，键的值可以通过标记扩展提供，并且可以字符串值以外。 示例 WPF 方案是的值`x:Key`可能[ComponentResourceKey](../../../docs/framework/wpf/advanced/componentresourcekey-markup-extension.md)。 某些控件公开样式的键的该类型的自定义样式资源的影响而不替换样式的外观的一部分，该控件的行为。 此密钥的一个示例是<xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>。  
  
 WPF 合并的字典功能引入了键唯一性和键查找行为的其他注意事项。 有关详细信息，请参阅[合并资源字典](../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md)。  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009 解除此限制，`x:Key`始终以属性形式提供。  
  
 在 WPF 中，你可以使用 XAML 2009 功能，但只针对未标记编译的 XAML。 WPF 的已编译标记的 XAML 以及 XAML 的 BAML 形式当前不支持 XAML 2009 关键字和功能。  
  
 在 XAML 2009 中可以指定`x:Key`通过以下使用情况的元素：  
  
### <a name="xaml-element-usage-xaml-2009-only"></a>XAML 元素用法 （仅 XAML 2009 年）  
  
```  
<object>  
  <x:Key>  
keyObject  
  </x:Key>  
...  
</object>  
```  
  
### <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`keyObject`|用作键的对象的对象元素给定`object`专用字典中。|  
  
-   使用这种容器/父级不在此处显示。 `object`应为表示一种专用的字典实现对象元素的子元素。 `keyObject`应为对象实例 （或值类型的值），适合作为该特定的专用的字典实现的密钥。  
  
-   WPF 未实现需要这种用法的字典。 对象键是更可能有用的某些自定义词典方案在 XAML 中创建字典所需的 XAML 语言的常规功能。 WPF 功能，如对资源使用非字符串键的隐式样式，用于建立或指定键的其他方法存在，因此不需要使用对象键。  
  
-   *keyObject*也可能是在对象元素窗体，而不是直接对象实例的标记扩展用法。  
  
## <a name="silverlight-usage-notes"></a>Silverlight 用法说明  
 `x:Key`适用于 Silverlight 是分开记录。 有关详细信息，请参阅[XAML Namespace （x:）语言功能 (Silverlight)](http://go.microsoft.com/fwlink/?LinkId=199081)。  
  
## <a name="see-also"></a>另请参阅  
 [XAML 资源](../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [资源和代码](../../../docs/framework/wpf/advanced/resources-and-code.md)  
 [StaticResource 标记扩展](../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)
