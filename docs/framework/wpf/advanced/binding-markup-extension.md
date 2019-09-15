---
title: 绑定标记扩展
ms.date: 03/30/2017
f1_keywords:
- Binding
helpviewer_keywords:
- Binding markup extensions [WPF]
- XAML [WPF], Binding markup extension
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
ms.openlocfilehash: 6776c89db474668b3aed0e38a3e18359bf93399d
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991482"
---
# <a name="binding-markup-extension"></a>绑定标记扩展
将属性值延迟为数据绑定值，创建中间表达式对象并在运行时解释应用于该元素及其绑定的数据上下文。  
  
## <a name="binding-expression-usage"></a>绑定表达式使用情况  
  
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
  
## <a name="syntax-notes"></a>语法说明  
 在这些语法中， `[]`和`*`不是文本。 它们是表示法的一部分，用于指示可以使用零个或多个*bindProp*`=`*值*对，其中`,`分隔符和前面的*bindProp*`=`*值*对。  
  
 可以改为使用<xref:System.Windows.Data.Binding>对象元素的属性设置 "可以使用绑定扩展设置的绑定属性" 部分中列出的任何属性。 但是，这并不是真正的标记扩展用法<xref:System.Windows.Data.Binding>，只是用于设置 CLR <xref:System.Windows.Data.Binding>类的属性的属性的常规 XAML 处理。 `<Binding`换句话说， *bindProp1* *value1 bindPropN*valueN 是对象元素用法的属性的等效语法<xref:System.Windows.Data.Binding> `"]*/>` `="``"[` `="`而不是使用表达式。`Binding` 若要了解的特定属性<xref:System.Windows.Data.Binding>的 xaml 特性用法，请参阅 .NET Framework 类库中的相关属性的<xref:System.Windows.Data.Binding> "xaml 特性用法" 部分。  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|要设置的<xref:System.Windows.Data.Binding>或<xref:System.Windows.Data.BindingBase>属性的名称。 并非所有<xref:System.Windows.Data.Binding>属性都可以`Binding`使用扩展进行设置，并且某些`Binding`属性只能通过使用更多嵌套标记扩展在表达式中设置。 请参阅 "绑定可通过绑定扩展进行设置的属性" 一节。|  
|`value1, valueN`|要将属性设置为的值。 特性值的处理最终特定于所设置的特定<xref:System.Windows.Data.Binding>属性的类型和逻辑。|  
|`path`|设置隐式<xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>属性的路径字符串。 另请参阅[PROPERTYPATH XAML 语法](propertypath-xaml-syntax.md)。|  
  
## <a name="unqualified-binding"></a>非限定 {Binding}  
 "绑定表达式使用情况" 中显示的<xref:System.Windows.Data.Binding> <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> `null`用法使用默认值创建一个对象，该对象包含的初始。 `{Binding}` 这在许多情况下仍有用，因为创建<xref:System.Windows.Data.Binding>的可能依赖于关键数据绑定属性， <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>如和<xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType>在运行时数据上下文中设置。 有关数据上下文概念的详细信息，请参阅[数据绑定](../data/data-binding-wpf.md)。  
  
## <a name="implicit-path"></a>隐式路径  
 标记`Binding` `Path=`扩展将用作概念 "默认属性"，其中无需出现在表达式中。 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 如果使用隐式`Binding`路径指定表达式，则隐式路径必须出现在表达式中的第一个位置，然后再`bindProp` = `value`将该<xref:System.Windows.Data.Binding>属性指定为名称。 例如： `{Binding PathString}`，其中`PathString`是一个字符串，其计算结果<xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>为标记扩展用法所创建的<xref:System.Windows.Data.Binding>中的值。 可以在逗号分隔符后面追加具有其他命名属性的隐式路径，例如`{Binding LastName, Mode=TwoWay}`。  
  
## <a name="binding-properties-that-can-be-set-with-the-binding-extension"></a>可通过绑定扩展进行设置的绑定属性  
 本主题中所示的语法使用通用`bindProp` <xref:System.Windows.Data.Binding> = `value`近似值，因为<xref:System.Windows.Data.BindingBase>有多个或可通过`Binding`标记扩展/表达式语法。 它们可以按任意顺序进行设置，但隐式<xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>除外。 （您可以选择显式指定`Path=`，在这种情况下，可以按任意顺序进行设置）。 基本上，可以使用`bindProp` = `value`以逗号分隔的对，在下面的列表中设置零个或多个属性。  
  
 其中一些属性值需要对象类型，这些对象类型不支持 XAML 中的文本语法的本机类型转换，因此需要标记扩展才能设置为属性值。 有关详细信息，请查看每个属性的 .NET Framework 类库中的 XAML 特性用法部分;用于带有或不带进一步标记扩展用法的 XAML 属性语法的字符串基本上与你在`Binding`表达式中指定的值相同，但不会在每个`bindProp` =中放置引号在表达式中 。`Binding` `value`  
  
- <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>：一个字符串，用于标识可能的绑定组。 这是一个相对较高级的绑定概念;请参阅的<xref:System.Windows.Data.BindingBase.BindingGroupName%2A>参考页。  
  
- <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>：布尔值，可以是`true`或`false`。 默认值为 `false`。  
  
- <xref:System.Windows.Data.Binding.Converter%2A>：可在表达式中设置`bindProp`为= `value`字符串，但要执行此操作，需要对值使用对象引用，如[StaticResource 标记扩展](staticresource-markup-extension.md)。 在此示例中，值是自定义转换器类的实例。  
  
- <xref:System.Windows.Data.Binding.ConverterCulture%2A>：可在表达式中设置为基于标准的标识符;请参阅的参考主题<xref:System.Windows.Data.Binding.ConverterCulture%2A>。  
  
- <xref:System.Windows.Data.Binding.ConverterParameter%2A>：可以设置为`bindProp` =表达式中的字符串，但这取决于传递的参数的类型。 `value` 如果传递值的引用类型，则此用法需要对象引用，例如嵌套的[StaticResource 标记扩展](staticresource-markup-extension.md)。  
  
- <xref:System.Windows.Data.Binding.ElementName%2A>：互相排斥与<xref:System.Windows.Data.Binding.RelativeSource%2A>和<xref:System.Windows.Data.Binding.Source%2A>; 每个绑定属性都表示一个特定的绑定方法。 请参阅[数据绑定概述](../data/data-binding-overview.md)。  
  
- <xref:System.Windows.Data.BindingBase.FallbackValue%2A>：可以设置为`bindProp` =表达式中的字符串，但这取决于所传递的值的类型。 `value` 如果传递引用类型，则需要对象引用，例如嵌套的[StaticResource 标记扩展](staticresource-markup-extension.md)。  
  
- <xref:System.Windows.Data.Binding.IsAsync%2A>：布尔值，可以是`true`或`false`。 默认值为 `false`。  
  
- <xref:System.Windows.Data.Binding.Mode%2A>：*值*是来自<xref:System.Windows.Data.BindingMode>枚举的常量名称。 例如， `{Binding Mode=OneWay}` 。  
  
- <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>：布尔值，可以是`true`或`false`。 默认值为 `false`。  
  
- <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>：布尔值，可以是`true`或`false`。 默认值为 `false`。  
  
- <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>：布尔值，可以是`true`或`false`。 默认值为 `false`。  
  
- <xref:System.Windows.Data.Binding.Path%2A>：描述数据对象或常规对象模型的路径的字符串。 格式为遍历对象模型提供了几种不同的约定，此约定在本主题中无法充分介绍。 请参阅[PROPERTYPATH XAML 语法](propertypath-xaml-syntax.md)。  
  
- <xref:System.Windows.Data.Binding.RelativeSource%2A>：与<xref:System.Windows.Data.Binding.ElementName%2A>和和<xref:System.Windows.Data.Binding.Source%2A>互相排斥; 每个绑定属性都表示一个特定的绑定方法。 请参阅[数据绑定概述](../data/data-binding-overview.md)。 要求使用嵌套的[RelativeSource MarkupExtension](relativesource-markupextension.md) ，以指定值。  
  
- <xref:System.Windows.Data.Binding.Source%2A>：互相排斥与<xref:System.Windows.Data.Binding.RelativeSource%2A>和<xref:System.Windows.Data.Binding.ElementName%2A>; 每个绑定属性都表示一个特定的绑定方法。 请参阅[数据绑定概述](../data/data-binding-overview.md)。 要求使用嵌套扩展用法，通常是一个[StaticResource 的标记扩展](staticresource-markup-extension.md)，它从键控资源字典引用对象数据源。  
  
- <xref:System.Windows.Data.BindingBase.StringFormat%2A>：一个字符串，描述绑定数据的字符串格式约定。 这是一个相对较高级的绑定概念;请参阅的<xref:System.Windows.Data.BindingBase.StringFormat%2A>参考页。  
  
- <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>：可以设置为`bindProp` =表达式中的字符串，但这取决于传递的参数的类型。 `value` 如果传递值的引用类型，则需要对象引用，例如嵌套的[StaticResource 标记扩展](staticresource-markup-extension.md)。  
  
- <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>：*值*是来自<xref:System.Windows.Data.UpdateSourceTrigger>枚举的常量名称。 例如， `{Binding UpdateSourceTrigger=LostFocus}` 。 对于此绑定属性，特定控件可能具有不同的默认值。 请参阅 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>。  
  
- <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>：布尔值，可以是`true`或`false`。 默认值为 `false`。 请参阅“备注”。  
  
- <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>：布尔值，可以是`true`或`false`。 默认值为 `false`。 请参阅“备注”。  
  
- <xref:System.Windows.Data.Binding.XPath%2A>：描述 XML 数据源的 XMLDOM 路径的字符串。 请参阅[使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)。  
  
 以下是无法`Binding`使用标记<xref:System.Windows.Data.Binding>扩展/`{Binding}`表达式窗体设置的属性。  
  
- <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>：此属性需要对回调实现的引用。 不能在 XAML 语法中引用事件处理程序以外的回调/方法。  
  
- <xref:System.Windows.Data.Binding.ValidationRules%2A>：属性采用<xref:System.Windows.Controls.ValidationRule>对象的泛型集合。 这可以表示为<xref:System.Windows.Data.Binding>对象元素中的属性元素，但没有任何可用于`Binding`表达式中的用法的属性分析技术。 请参阅参考主题<xref:System.Windows.Data.Binding.ValidationRules%2A>。  
  
- <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## <a name="remarks"></a>备注  
  
> [!IMPORTANT]
> 就依赖属性优先级而言， `Binding`表达式等效于本地设置的值。 如果为先前具有`Binding`表达式的属性设置本地值`Binding` ，则将完全删除。 有关详细信息，请参阅[依赖属性值优先级](dependency-property-value-precedence.md)。  
  
 本主题不涉及在基本级别描述数据绑定。 请参阅[数据绑定概述](../data/data-binding-overview.md)。  
  
> [!NOTE]
> <xref:System.Windows.Data.MultiBinding>和<xref:System.Windows.Data.PriorityBinding> 不[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]支持扩展语法。 您将改用属性元素。 请参阅和<xref:System.Windows.Data.PriorityBinding>的<xref:System.Windows.Data.MultiBinding>参考主题。  
  
 XAML 的布尔值不区分大小写。 例如，可以指定`{Binding NotifyOnValidationError=true}`或。 `{Binding NotifyOnValidationError=True}`  
  
 涉及数据验证的绑定通常由`Binding`显式元素（而不`{Binding ...}`是表达式）指定，而表达式中的<xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>设置<xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>或不常见。 这是因为不能在<xref:System.Windows.Data.Binding.ValidationRules%2A>表达式窗体中轻松设置伴生属性。 有关详细信息，请参阅[实现绑定验证](../data/how-to-implement-binding-validation.md)。  
  
 `Binding` 是标记扩展。 通常在要求转义特性值时，通常会实现标记扩展，而不是文本值或处理程序名称，并且该要求比在某些类型或属性上指定的类型转换器更全局性。 Xaml 中的`{`所有标记扩展在其`}`特性语法中使用和字符，这是 xaml 处理器识别标记扩展必须处理字符串内容的约定。 有关详细信息，请参阅[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。  
  
 `Binding`是一个非典型的标记扩展， <xref:System.Windows.Data.Binding>因为实现 WPF XAML 实现扩展功能的类还实现了一些与 XAML 无关的其他方法和属性。 其他成员旨在创建<xref:System.Windows.Data.Binding>更通用和独立的类，这些类可用于处理除作为 XAML 标记扩展以外的许多数据绑定方案。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Data.Binding>
- [数据绑定概述](../data/data-binding-overview.md)
- [XAML 概述 (WPF)](xaml-overview-wpf.md)
- [标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)
