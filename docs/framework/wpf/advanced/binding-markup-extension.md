---
title: 绑定标记扩展
ms.date: 03/30/2017
f1_keywords:
- Binding
helpviewer_keywords:
- Binding markup extensions [WPF]
- XAML [WPF], Binding markup extension
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
ms.openlocfilehash: c6a424e085c7499db08d0a7e6b652f45fb2cdd70
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81644087"
---
# <a name="binding-markup-extension"></a>绑定标记扩展
将属性值延迟为数据绑定值，创建中间表达式对象并解释在运行时应用于元素及其绑定的数据上下文。  
  
## <a name="binding-expression-usage"></a>绑定表达式用法  
  
```xaml  
<object property="{Binding}" .../>  
-or-  
<object property="{Binding  bindProp1=value1[, bindPropN=valueN]*}" ...  
/>  
-or-  
<object property="{Binding path}" .../>  
-or  
<object property="{Binding path[, bindPropN=valueN]*}" .../>  
```  
  
## <a name="syntax-notes"></a>语法注释  
 在这些语法中，`[]`和`*`不是文本。 它们是表示法的一部分，用于指示可以使用零个或多个*绑定Prop*`=`*值*对，并在它们之间和前面的`,`*绑定Prop*`=`*值*对之间具有分隔符。  
  
 可以使用<xref:System.Windows.Data.Binding>对象元素的属性设置"可以使用绑定扩展设置的绑定属性"部分中列出的任何属性。 但是，这不是真正的标记扩展用法<xref:System.Windows.Data.Binding>，它只是设置 CLR<xref:System.Windows.Data.Binding>类属性的属性的一般 XAML 处理。 换句话说`<Binding`*，bindProp1*`="``"]*/>` <xref:System.Windows.Data.Binding> `Binding` `"[` *valuepropNvalueN*`="`*valueN*值N是对象元素使用属性的等效语法，而不是表达式用法。*value1* 要了解 的 XAML 属性使用情况<xref:System.Windows.Data.Binding>，请参阅 .NET 框架类库中的相关<xref:System.Windows.Data.Binding>属性的"XAML 属性用法"部分。  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|要设置的<xref:System.Windows.Data.Binding>或<xref:System.Windows.Data.BindingBase>属性的名称。 并非所有<xref:System.Windows.Data.Binding>属性都可以使用`Binding`扩展设置，并且某些属性仅在表达式中仅通过使用进一`Binding`步的嵌套标记扩展进行设置。 请参阅"可以使用绑定扩展设置的绑定属性"部分。|  
|`value1, valueN`|要将属性设置为的值。 属性值的处理最终特定于要设置的特定<xref:System.Windows.Data.Binding>属性的类型和逻辑。|  
|`path`|设置隐式<xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>属性的路径字符串。 另请参阅[属性路径 XAML 语法](propertypath-xaml-syntax.md)。|  
  
## <a name="unqualified-binding"></a>不合格 [绑定]  
 "`{Binding}`绑定表达式用法"中显示的用法创建具有<xref:System.Windows.Data.Binding>默认值的对象，其中包括<xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>的初始`null`值。 这在许多方案中仍然很有用，因为创建的<xref:System.Windows.Data.Binding>可能依赖于关键数据绑定属性，例如<xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>并在<xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType>运行时数据上下文中设置。 有关数据上下文概念的详细信息，请参阅[数据绑定](../../../desktop-wpf/data/data-binding-overview.md)。  
  
## <a name="implicit-path"></a>隐式路径  
 标记`Binding`扩展用作<xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>概念性的"默认属性"，其中`Path=`不需要出现在表达式中。 如果`Binding`指定具有隐式路径的表达式，则隐式路径必须首先出现在表达式中，在任何其他`bindProp`=`value`由名称指定<xref:System.Windows.Data.Binding>该属性的对之前。 例如： `{Binding PathString}`，`PathString`其中的字符串被计算为 标记扩展用法<xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType><xref:System.Windows.Data.Binding>创建的 中的值。 例如，可以在逗号分隔符之后附加隐式路径和其他命名属性。 `{Binding LastName, Mode=TwoWay}`  
  
## <a name="binding-properties-that-can-be-set-with-the-binding-extension"></a>可以使用绑定扩展设置的绑定属性  
 本主题中显示的语法使用泛型`bindProp`=`value`近似值，因为有许多读/写属性，<xref:System.Windows.Data.BindingBase>或者<xref:System.Windows.Data.Binding>可以通过`Binding`标记扩展/表达式语法进行设置。 它们可以按任何顺序设置，但隐式<xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>。 （您确实可以选择显式指定`Path=`，在这种情况下，可以按任意顺序设置它）。 基本上，您可以使用用逗号分隔的`bindProp`=`value`对设置下面列表中的零个或多个属性。  
  
 其中一些属性值要求对象类型不支持从 XAML 中的文本语法转换本机类型，因此需要标记扩展才能设置为属性值。 有关详细信息，请查看 .NET 框架类库中的 XAML 属性使用部分，了解每个属性;用于 XAML 属性语法（无论是否具有进一步标记扩展用法）的字符串与表达式`Binding`中指定的值基本相同，但表达式中`bindProp`=`value``Binding`每个值不放置引号除外。  
  
- <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>：标识可能的绑定组的字符串。 这是一个相对先进的绑定概念;请参阅 参考<xref:System.Windows.Data.BindingBase.BindingGroupName%2A>页。  
  
- <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>： 布尔，可以是 或`true``false`。 默认为 `false`。  
  
- <xref:System.Windows.Data.Binding.Converter%2A>：`bindProp`=`value`可以设置为表达式中的字符串，但这样做需要值的对象引用，如[静态资源标记扩展](staticresource-markup-extension.md)。 在这种情况下，值是自定义转换器类的实例。  
  
- <xref:System.Windows.Data.Binding.ConverterCulture%2A>：在表达式中设置为基于标准的标识符;请参阅 的 参考<xref:System.Windows.Data.Binding.ConverterCulture%2A>主题。  
  
- <xref:System.Windows.Data.Binding.ConverterParameter%2A>： 可以设置为`bindProp`=`value`表达式中的字符串，但这取决于传递的参数的类型。 如果传递值的引用类型，则此用法需要对象引用，如嵌套[的静态资源标记扩展](staticresource-markup-extension.md)。  
  
- <xref:System.Windows.Data.Binding.ElementName%2A>： 相互排斥<xref:System.Windows.Data.Binding.RelativeSource%2A>与<xref:System.Windows.Data.Binding.Source%2A>和 ;每个绑定属性都表示特定的绑定方法。 请参阅[数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)。  
  
- <xref:System.Windows.Data.BindingBase.FallbackValue%2A>： 可以设置为`bindProp`=`value`表达式中的字符串，但这取决于要传递的值的类型。 如果传递引用类型，则需要对象引用，如嵌套[的静态资源标记扩展](staticresource-markup-extension.md)。  
  
- <xref:System.Windows.Data.Binding.IsAsync%2A>： 布尔，可以是 或`true``false`。 默认为 `false`。  
  
- <xref:System.Windows.Data.Binding.Mode%2A>：*值*是枚举中的<xref:System.Windows.Data.BindingMode>常量名称。 例如，`{Binding Mode=OneWay}` 。  
  
- <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>： 布尔，可以是 或`true``false`。 默认为 `false`。  
  
- <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>： 布尔，可以是 或`true``false`。 默认为 `false`。  
  
- <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>： 布尔，可以是 或`true``false`。 默认为 `false`。  
  
- <xref:System.Windows.Data.Binding.Path%2A>描述数据对象或常规对象模型的路径的字符串。 该格式提供了几个不同的约定来遍历本主题中无法充分描述的对象模型。 请参阅[属性路径 XAML 语法](propertypath-xaml-syntax.md)。  
  
- <xref:System.Windows.Data.Binding.RelativeSource%2A>： 与 和<xref:System.Windows.Data.Binding.ElementName%2A><xref:System.Windows.Data.Binding.Source%2A>的相互排斥;每个绑定属性都表示特定的绑定方法。 请参阅[数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)。 需要嵌套[相对源标记扩展](relativesource-markupextension.md)用法来指定值。  
  
- <xref:System.Windows.Data.Binding.Source%2A>： 相互排斥<xref:System.Windows.Data.Binding.RelativeSource%2A>与<xref:System.Windows.Data.Binding.ElementName%2A>和 ;每个绑定属性都表示特定的绑定方法。 请参阅[数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)。 需要嵌套扩展用法，通常是引用键控资源字典中的对象数据源的[静态资源标记扩展](staticresource-markup-extension.md)。  
  
- <xref:System.Windows.Data.BindingBase.StringFormat%2A>：描述绑定数据的字符串格式约定的字符串。 这是一个相对先进的绑定概念;请参阅 参考<xref:System.Windows.Data.BindingBase.StringFormat%2A>页。  
  
- <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>： 可以设置为`bindProp`=`value`表达式中的字符串，但这取决于传递的参数的类型。 如果传递值的引用类型，则需要对象引用（如嵌套[静态资源标记扩展](staticresource-markup-extension.md)）。  
  
- <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>：*值*是枚举中的<xref:System.Windows.Data.UpdateSourceTrigger>常量名称。 例如，`{Binding UpdateSourceTrigger=LostFocus}` 。 特定控件可能对此绑定属性具有不同的默认值。 请参阅 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>。  
  
- <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>： 布尔，可以是 或`true``false`。 默认为 `false`。 请参阅“备注”。  
  
- <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>： 布尔，可以是 或`true``false`。 默认为 `false`。 请参阅“备注”。  
  
- <xref:System.Windows.Data.Binding.XPath%2A>：描述进入 XML 数据源 XMLDOM 的路径的字符串。 请参阅[使用 XMLData 提供程序和 XPath 查询绑定到 XML 数据](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)。  
  
 以下是无法使用<xref:System.Windows.Data.Binding>`Binding`标记扩展/`{Binding}`表达式窗体设置的属性。  
  
- <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>：此属性需要对回调实现的引用。 无法在 XAML 语法中引用事件处理程序以外的回调/方法。  
  
- <xref:System.Windows.Data.Binding.ValidationRules%2A>：属性采用<xref:System.Windows.Controls.ValidationRule>对象的泛型集合。 这可以表示为<xref:System.Windows.Data.Binding>对象元素中的属性元素，但没有现成的属性解析技术可用于`Binding`表达式中的使用。 请参阅 参考主题<xref:System.Windows.Data.Binding.ValidationRules%2A>。  
  
- <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## <a name="remarks"></a>备注  
  
> [!IMPORTANT]
> 在依赖项属性优先级方面，`Binding`表达式等效于本地设置的值。 如果为以前具有`Binding`表达式的属性设置本地值，则 将完全删除`Binding`。 有关详细信息，请参阅[依赖属性值优先级](dependency-property-value-precedence.md)。  
  
 本主题未介绍在基本级别描述数据绑定。 请参阅[数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)。  
  
> [!NOTE]
> <xref:System.Windows.Data.MultiBinding>不支持<xref:System.Windows.Data.PriorityBinding>扩展语法[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。 您将使用属性元素。 请参阅 和<xref:System.Windows.Data.PriorityBinding><xref:System.Windows.Data.MultiBinding>的参考主题。  
  
 XAML 的布尔值不区分大小写。 例如，您可以指定 或`{Binding NotifyOnValidationError=true}``{Binding NotifyOnValidationError=True}`。  
  
 涉及数据`Binding`验证的绑定通常由显式元素而不是`{Binding ...}`表达式指定，并且设置<xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>或<xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>表达式中并不常见。 这是因为无法轻松在表达式窗体<xref:System.Windows.Data.Binding.ValidationRules%2A>中设置配套属性。 有关详细信息，请参阅[实现绑定验证](../data/how-to-implement-binding-validation.md)。  
  
 `Binding` 是标记扩展。 标记扩展通常在需要转义属性值为文本值或处理程序名称以外的时实现，并且该要求比某些类型或属性上属性化的类型转换器更全局。 XAML 中的所有标记扩展在其属性语法中使用`{``}`和 字符，这是 XAML 处理器识别标记扩展必须处理字符串内容的约定。 有关详细信息，请参阅[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。  
  
 `Binding`是一个非典型的标记扩展，因为实现<xref:System.Windows.Data.Binding>WPF XAML 实现扩展功能的类还实现了与 XAML 无关的其他几种方法和属性。 其他成员旨在创建<xref:System.Windows.Data.Binding>一个功能更通用、自包含的类，除了充当 XAML 标记扩展之外，还可以解决许多数据绑定方案。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Data.Binding>
- [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)
- [XAML 概述 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)
