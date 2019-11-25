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
ms.openlocfilehash: 8321a09db31c9f6d2103a252a195fcdbf8da3e66
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283859"
---
# <a name="xkey-directive"></a>x:Key 指令
唯一标识在 XAML 定义的字典中创建和引用的元素。 将 `x:Key` 值添加到 XAML 对象元素是在资源字典中标识资源的最常见方法，例如在 WPF <xref:System.Windows.ResourceDictionary>中。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xaml  
<object x:Key="stringKeyValue".../>  
-or-  
<object x:Key="{markupExtensionUsage}".../>  
```  
  
## <a name="xaml-attribute-usage-wpf-specific"></a>XAML 特性用法（特定于 WPF）  
  
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
|`stringKeyValue`|要用作键的文本字符串。 文本字符串必须符合[XamlName 语法](xamlname-grammar.md)。|  
|`markupExtensionUsage`|标记扩展分隔符 {}，这是一个提供要用作键的对象的标记扩展用法。 请参阅“备注”。|  
  
## <a name="remarks"></a>备注  
 `x:Key` 支持 XAML 资源字典概念。 作为语言的 XAML 不会定义资源字典实现，该实现留给特定的 UI 框架。 若要了解有关如何在 WPF 中实现 XAML 资源字典的详细信息，请参阅[Xaml 资源](../../desktop-wpf/fundamentals/xaml-resources-define.md)。  
  
 在 XAML 2006 和 WPF 中，`x:Key` 必须作为属性提供。 你仍可以使用非字符串键，但这需要使用标记扩展用法来提供属性窗体中的非字符串值。 如果你使用的是 XAML 2009，则可以将 `x:Key` 指定为元素，以显式支持由对象类型（而不是字符串）提供支持的字典，而无需使用标记扩展。 请参阅本主题中的 "XAML 2009" 部分。 备注部分的剩余部分专门适用于 XAML 2006 实现。  
  
 `x:Key` 的属性值可以是[XamlName 语法](xamlname-grammar.md)中定义的任何字符串，也可以是通过标记扩展进行计算的对象。 有关 WPF 的示例，请参阅 "WPF 使用说明"。  
  
 作为 <xref:System.Collections.IDictionary> 实现的父元素的子元素通常必须包括一个 `x:Key` 属性，该属性指定字典中的唯一键值。 框架可能实现用别名的键属性来替换特定类型的 `x:Key`;定义此类属性的类型应与 <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>特性化。  
  
 等效于指定 `x:Key` 的代码是用于基础 <xref:System.Collections.IDictionary>的键。 例如，当您将资源添加到代码中的 WPF <xref:System.Windows.ResourceDictionary> 时，WPF 中某个资源的标记中应用的 `x:Key` 相当于 <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> 的 `key` 参数的值。  
  
## <a name="wpf-usage-notes"></a>WPF 使用说明  
 作为 <xref:System.Collections.IDictionary> 实现的父对象的子对象（如 WPF <xref:System.Windows.ResourceDictionary>）通常必须包含 `x:Key` 特性，并且键值在该字典中必须是唯一的。 有两个值得注意的异常：  
  
- 一些 WPF 类型声明了字典使用的隐式键。 例如，使用 <xref:System.Windows.Style.TargetType%2A>的 <xref:System.Windows.Style> 或带有 <xref:System.Windows.DataTemplate.DataType%2A>的 <xref:System.Windows.DataTemplate> 可以位于 <xref:System.Windows.ResourceDictionary> 中，并使用隐式键。  
  
- WPF 支持合并资源字典概念。 可以在合并字典之间共享键，并且可以使用 <xref:System.Windows.FrameworkContentElement.FindResource%2A>访问共享密钥行为。 有关详细信息，请参阅[合并资源字典](../wpf/advanced/merged-resource-dictionaries.md)。  
  
 在整个 WPF XAML 实现和应用程序模型中，XAML 标记编译器不会检查密钥的唯一性。 相反，缺少或不唯一的 `x:Key` 值会导致加载时 XAML 分析器错误。 但是，Visual Studio for WPF 字典处理通常会在设计阶段记录此类错误。  
  
 请注意，在显示的语法中，<xref:System.Windows.ResourceDictionary> 对象是隐式的，因为 WPF XAML 处理器如何生成用于填充 <xref:System.Windows.FrameworkElement.Resources%2A> 集合的集合。 通常不会在标记中将 <xref:System.Windows.ResourceDictionary> 显式提供为元素，不过，在某些情况下，如果需要清楚起见（它将是 <xref:System.Windows.FrameworkElement.Resources%2A> 属性元素与中填充字典的项之间的集合对象元素）。 有关集合对象在标记中几乎始终为隐式元素的原因的信息，请参阅[XAML 语法（详细](../wpf/advanced/xaml-syntax-in-detail.md)）。  
  
 在 WPF XAML 实现中，资源字典键的处理由 <xref:System.Windows.ResourceKey> 抽象类定义。 不过，WPF XAML 处理器基于它们的用法为密钥生成不同的基础扩展类型。 例如，<xref:System.Windows.DataTemplate> 或任何派生类的键单独处理，并生成一个不同的 <xref:System.Windows.DataTemplateKey> 对象。  
  
 键和名称在基本 XAML 定义中使用不同的指令和语言元素（`x:Key` 与 `x:Name`）。 键和名称还可用于 WPF 定义和应用这些概念的不同情况。 有关详细信息，请参阅[WPF XAML 名称范围](../wpf/advanced/wpf-xaml-namescopes.md)。  
  
 如前所述，密钥的值可以通过标记扩展提供，也可以是字符串值以外的值。 WPF 方案的一个示例是 `x:Key` 的值可能是[ComponentResourceKey](../wpf/advanced/componentresourcekey-markup-extension.md)。 某些控件为自定义样式资源公开该类型的样式键，该资源会影响该控件的外观和行为的一部分，而不会完全替换样式。 <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>此类密钥的示例。  
  
 WPF 合并字典功能引入了有关密钥唯一性和键查找行为的其他注意事项。 有关详细信息，请参阅[合并资源字典](../wpf/advanced/merged-resource-dictionaries.md)。  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009 放宽了 `x:Key` 始终以属性形式提供的限制。  
  
 在 WPF 中，可以使用 XAML 2009 功能，但仅针对未进行标记编译的 XAML。 WPF 的已编译标记的 XAML 以及 XAML 的 BAML 形式当前不支持 XAML 2009 关键字和功能。  
  
 在 XAML 2009 下，可以通过以下用法指定 `x:Key` 元素：  
  
### <a name="xaml-element-usage-xaml-2009-only"></a>XAML 元素用法（仅适用于 XAML 2009）  
  
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
|`keyObject`|对象的对象元素，该对象用作专用字典中给定 `object` 的键。|  
  
- 此类用途的容器/父项未在此处显示。 `object` 应是表示专用字典实现的对象元素的子元素。 `keyObject` 应为一个对象实例（或值类型的值），该实例适合作为该特定专用字典实现的键。  
  
- WPF 不实现需要此用法的字典。 对象键是 XAML 语言的常规功能，对于在 XAML 中创建字典的某些自定义字典方案可能很有用。 对于使用资源的非字符串密钥的隐式样式等 WPF 功能，存在用于建立或指定密钥的其他方法，因此不需要使用对象密钥。  
  
- *keyObject*也可以是对象元素窗体中的标记扩展用法，而不是直接对象实例。  
  
## <a name="silverlight-usage-notes"></a>Silverlight 使用说明  
 Silverlight `x:Key` 分别进行了说明。 有关详细信息，请参阅[XAML 命名空间（x：）语言功能（Silverlight）](https://go.microsoft.com/fwlink/?LinkId=199081)。  
  
## <a name="see-also"></a>另请参阅

- [XAML 资源](../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [资源和代码](../wpf/advanced/resources-and-code.md)
- [StaticResource 标记扩展](../wpf/advanced/staticresource-markup-extension.md)
