---
title: x:Key 指令
ms.date: 03/30/2017
f1_keywords:
- xKey
- Key
- x:Key
helpviewer_keywords:
- x:Key attribute [XAML Services]
- Key attribute in XAML [XAML Services]
- XAML [XAML Services], x:Key attribute
ms.assetid: 1985cd45-f197-42d5-b75e-886add64b248
ms.openlocfilehash: c05f98932ceceeb1530b34a09b1923f2af1378b5
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432754"
---
# <a name="xkey-directive"></a>x:Key 指令
唯一标识在 XAML 定义的字典中创建和引用的元素。 向`x:Key`XAML 对象元素添加值是标识资源字典中资源的最常见方法，例如在 WPF<xref:System.Windows.ResourceDictionary>中。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xaml  
<object x:Key="stringKeyValue".../>  
-or-  
<object x:Key="{markupExtensionUsage}".../>  
```  
  
## <a name="xaml-attribute-usage-wpf-specific"></a>XAML 属性使用情况（特定于 WPF）  
  
```xaml  
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
|`stringKeyValue`|用作键的文本字符串。 文本字符串必须符合[XamlName 语法](xamlname-grammar.md)。|  
|`markupExtensionUsage`|在标记扩展分隔符{}中，提供用作键的对象的标记扩展用法。 请参阅“备注”。|  
  
## <a name="remarks"></a>备注  
 `x:Key`支持 XAML 资源字典概念。 XAML 作为一种语言不会定义资源字典实现，而资源字典实现留给特定的 UI 框架。 要了解有关如何在 WPF 中实现 XAML 资源字典的更多信息，请参阅[XAML 资源](../fundamentals/xaml-resources-define.md)。  
  
 在 XAML 2006 和`x:Key`WPF 中，必须作为属性提供。 您仍可以使用非字符串键，但这需要标记扩展用法才能在属性窗体中提供非字符串值。 如果使用 XAML 2009，`x:Key`则可以指定为元素，以显式支持由字符串以外的对象类型键控的字典，而无需标记扩展中间。 请参阅本主题中的"XAML 2009"部分。 备注部分的其余部分特别适用于 XAML 2006 实现。  
  
 的属性`x:Key`值可以是[XamlName 语法](xamlname-grammar.md)中定义的任何字符串，也可以是通过标记扩展计算的对象。 有关 WPF 的示例，请参阅"WPF 使用说明"。  
  
 作为<xref:System.Collections.IDictionary>实现的父元素的子元素通常必须包含指定`x:Key`该字典中唯一键值的属性。 框架可能实现别名键属性，`x:Key`以替换特定类型;定义此类属性的类型应归因于<xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>。  
  
 指定`x:Key`等效的代码是用于基础<xref:System.Collections.IDictionary>的键。 例如，在`x:Key`WPF 中资源标记中应用的 与 将资源添加到代码中的 WPF`key`<xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType><xref:System.Windows.ResourceDictionary>时的参数值等效。  
  
## <a name="wpf-usage-notes"></a>WPF 用法说明  
 作为<xref:System.Collections.IDictionary>实现（如 WPF）<xref:System.Windows.ResourceDictionary>的父对象的子对象通常必须包含属性`x:Key`，并且键值必须是唯一的字典。 有两个值得注意的例外：  
  
- 某些 WPF 类型声明字典用法的隐式键。 例如，带<xref:System.Windows.Style><xref:System.Windows.Style.TargetType%2A>的 或<xref:System.Windows.DataTemplate>的<xref:System.Windows.DataTemplate.DataType%2A>和 ， 可以<xref:System.Windows.ResourceDictionary>位于 中，并使用隐式键。  
  
- WPF 支持合并的资源字典概念。 密钥可以在合并字典之间共享，并且可以使用<xref:System.Windows.FrameworkContentElement.FindResource%2A>访问共享密钥行为。 有关详细信息，请参阅[合并资源字典](../../framework/wpf/advanced/merged-resource-dictionaries.md)。  
  
 在整体 WPF XAML 实现和应用模型中，XAML 标记编译器不检查密钥唯一性。 相反，缺少或非唯`x:Key`一值会导致加载时间 XAML 解析器错误。 但是，Visual Studio 处理 WPF 字典时通常可以在设计阶段注意到此类错误。  
  
 请注意，在所示的语法中，<xref:System.Windows.ResourceDictionary>对象隐化于 WPF XAML 处理器如何生成集合以填充<xref:System.Windows.FrameworkElement.Resources%2A>集合。 在<xref:System.Windows.ResourceDictionary>标记中，通常不作为元素显式提供 a，尽管在某些情况下，如果需要，它可以是集合对象元素（它将是<xref:System.Windows.FrameworkElement.Resources%2A>属性元素和填充字典中的项之间的集合对象元素）。 有关集合对象在标记中几乎总是隐式元素的原因的信息，请参阅[XAML 语法详细信息](../../framework/wpf/advanced/xaml-syntax-in-detail.md)。  
  
 在 WPF XAML 实现中，资源字典密钥的处理由<xref:System.Windows.ResourceKey>抽象类定义。 但是，WPF XAML 处理器会根据密钥的用法为密钥生成不同的基础扩展类型。 例如，或<xref:System.Windows.DataTemplate>任何派生类的键单独处理，并生成不同的<xref:System.Windows.DataTemplateKey>对象。  
  
 键和名称在基本的 XAML`x:Key`定义`x:Name`中使用不同的指令和语言元素 （ 对 ） 。 WPF 的定义和这些概念的应用也在不同的情况下使用密钥和名称。 有关详细信息，请参阅[WPF XAML 名称范围](../../framework/wpf/advanced/wpf-xaml-namescopes.md)。  
  
 如前所述，键的值可以通过标记扩展提供，并且可以不提供字符串值。 WPF 方案的示例是 ， 的值`x:Key`可能是[组件资源密钥](../../framework/wpf/advanced/componentresourcekey-markup-extension.md)。 某些控件公开自定义样式资源的该类型的样式键，该样式资源在不完全替换样式的情况下会影响该控件的部分外观和行为。 这种键的一个例子是<xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>。  
  
 WPF 合并字典功能引入了关键唯一性和密钥查找行为的其他注意事项。 有关详细信息，请参阅[合并资源字典](../../framework/wpf/advanced/merged-resource-dictionaries.md)。  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009 放宽`x:Key`了始终以属性形式提供的限制。  
  
 在 WPF 中，可以使用 XAML 2009 功能，但仅适用于未标记编译的 XAML。 WPF 的已编译标记的 XAML 以及 XAML 的 BAML 形式当前不支持 XAML 2009 关键字和功能。  
  
 在 XAML 2009 下`x:Key`，您可以通过以下用法指定元素：  
  
### <a name="xaml-element-usage-xaml-2009-only"></a>XAML 元素使用（仅限 XAML 2009）  
  
```xaml  
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
|`keyObject`|对象的对象元素，该对象用作专用字典中给定`object`项的键。|  
  
- 此种使用的容器/父级不在此处显示。 `object`应作为表示专用字典实现的对象元素的子元素。 `keyObject`应作为该特定专用字典实现的关键的对象实例（或值类型的值）。  
  
- WPF 不实现需要此用法的字典。 对象键是 XAML 语言的一个常规功能，对于某些自定义字典方案可能很有用，在其中需要在 XAML 中创建字典。 对于 WPF 功能（如使用非字符串键进行资源化的隐式样式），存在其他用于建立或指定键的技术，因此无需使用对象键。  
  
- `keyObject`也可以是对象元素形式的标记扩展用法，而不是直接的对象实例。  
  
## <a name="silverlight-usage-notes"></a>银光使用说明  
 `x:Key`银光单独记录。 有关详细信息，请参阅[XAML 命名空间 （x：）语言功能（银光）](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).  
  
## <a name="see-also"></a>请参阅

- [XAML 资源](../fundamentals/xaml-resources-define.md)
- [资源和代码](../../framework/wpf/advanced/resources-and-code.md)
- [StaticResource 标记扩展](../../framework/wpf/advanced/staticresource-markup-extension.md)
