---
title: 绑定标记扩展
ms.date: 03/30/2017
f1_keywords:
- Binding
helpviewer_keywords:
- Binding markup extensions [WPF]
- XAML [WPF], Binding markup extension
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
ms.openlocfilehash: d0a437e756da16db978d8074c4355fd83d211b67
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453610"
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
 在这些语法中，`[]` 和 `*` 不是文本。 它们是表示法的一部分，用于指示可以使用零个或多个*bindProp*`=`*值*对，并在它们和前面的*bindProp*`=`*值*对之间使用 `,` 分隔符。  
  
 "可以使用绑定扩展设置的绑定属性" 一节中列出的任何属性都可以通过使用 <xref:System.Windows.Data.Binding> 对象元素的属性来设置。 但是，这并不是真正 <xref:System.Windows.Data.Binding>的标记扩展用法，只是设置 CLR <xref:System.Windows.Data.Binding> 类的属性的属性的常规 XAML 处理。 换句话说，`<Binding` *bindProp1*`="`*value1*`"[` *bindPropN*`="`*valueN*`"]*/>` 是 <xref:System.Windows.Data.Binding> 对象元素用法的属性的等效语法，而不是 `Binding` 表达式用法。 若要了解 <xref:System.Windows.Data.Binding>的特定属性的 XAML 属性用法，请参阅 .NET Framework 类库中 <xref:System.Windows.Data.Binding> 相关属性的 "XAML 属性用法" 部分。  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|要设置的 <xref:System.Windows.Data.Binding> 或 <xref:System.Windows.Data.BindingBase> 属性的名称。 并非所有 <xref:System.Windows.Data.Binding> 属性都可以使用 `Binding` 扩展进行设置，而某些属性只能通过使用更多嵌套标记扩展在 `Binding` 表达式中设置。 请参阅 "绑定可通过绑定扩展进行设置的属性" 一节。|  
|`value1, valueN`|要将属性设置为的值。 特性值的处理最终特定于所设置的特定 <xref:System.Windows.Data.Binding> 属性的类型和逻辑。|  
|`path`|设置隐式 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 属性的路径字符串。 另请参阅[PROPERTYPATH XAML 语法](propertypath-xaml-syntax.md)。|  
  
## <a name="unqualified-binding"></a>非限定 {Binding}  
 "绑定表达式使用情况" 中显示的 `{Binding}` 用法使用默认值创建 <xref:System.Windows.Data.Binding> 对象，其中包括 `null`的初始 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>。 这在许多情况下仍有用，因为创建的 <xref:System.Windows.Data.Binding> 可能依赖于关键数据绑定属性，如在运行时数据上下文中设置 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 和 <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType>。 有关数据上下文概念的详细信息，请参阅[数据绑定](../data/data-binding-wpf.md)。  
  
## <a name="implicit-path"></a>隐式路径  
 `Binding` 标记扩展使用 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 作为概念 "默认属性"，其中 `Path=` 不需要出现在表达式中。 如果使用隐式路径指定 `Binding` 表达式，则隐式路径必须出现在表达式中的第一个位置，在任何其他 `bindProp`=`value` 对（其中，<xref:System.Windows.Data.Binding> 属性由 name 指定）之前。 例如： `{Binding PathString}`，其中，`PathString` 是一个字符串，其计算结果为标记扩展用法创建的 <xref:System.Windows.Data.Binding> 中 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 的值。 可以在逗号分隔符后面追加具有其他命名属性的隐式路径，例如 `{Binding LastName, Mode=TwoWay}`。  
  
## <a name="binding-properties-that-can-be-set-with-the-binding-extension"></a>可通过绑定扩展进行设置的绑定属性  
 本主题中所示的语法使用泛型 `bindProp`=`value` 近似值，因为可以通过 <xref:System.Windows.Data.Binding> 标记扩展/表达式语法来设置 <xref:System.Windows.Data.BindingBase> 或 `Binding` 的多个读/写属性。 它们可以按任意顺序进行设置，但隐含 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>例外。 （您可以选择显式指定 `Path=`，在这种情况下，可以按任意顺序进行设置）。 基本上，可以使用以逗号分隔的 `bindProp`=`value` 对，在下面的列表中设置零个或多个属性。  
  
 其中一些属性值需要对象类型，这些对象类型不支持 XAML 中的文本语法的本机类型转换，因此需要标记扩展才能设置为属性值。 有关详细信息，请查看每个属性的 .NET Framework 类库中的 XAML 特性用法部分;用于带有或不带进一步标记扩展用法的 XAML 属性语法的字符串基本上与您在 `Binding` 表达式中指定的值相同，但不会将每个 `bindProp`的引号括起来 =`value``Binding` 表达式。  
  
- <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>：标识可能的绑定组的字符串。 这是一个相对较高级的绑定概念;请参阅 <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>的参考页。  
  
- <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>：布尔值，可以是 `true` 或 `false`。 默认值为 `false`。  
  
- <xref:System.Windows.Data.Binding.Converter%2A>：可以设置为表达式中的 `bindProp`=`value` 字符串，但为了实现此目的，需要对值使用对象引用，如[StaticResource 标记扩展](staticresource-markup-extension.md)。 在此示例中，值是自定义转换器类的实例。  
  
- <xref:System.Windows.Data.Binding.ConverterCulture%2A>：可在表达式中设置为基于标准的标识符;有关 <xref:System.Windows.Data.Binding.ConverterCulture%2A>，请参阅参考主题。  
  
- <xref:System.Windows.Data.Binding.ConverterParameter%2A>：可以设置为表达式中的 `bindProp`=`value` 字符串，但这取决于传递的参数的类型。 如果传递值的引用类型，则此用法需要对象引用，例如嵌套的[StaticResource 标记扩展](staticresource-markup-extension.md)。  
  
- <xref:System.Windows.Data.Binding.ElementName%2A>：互相排斥与 <xref:System.Windows.Data.Binding.RelativeSource%2A> 和 <xref:System.Windows.Data.Binding.Source%2A>;其中每个绑定属性都表示一个特定的绑定方法。 请参阅[数据绑定概述](../data/data-binding-overview.md)。  
  
- <xref:System.Windows.Data.BindingBase.FallbackValue%2A>：可以设置为表达式中的 `bindProp`=`value` 字符串，但这依赖于所传递的值的类型。 如果传递引用类型，则需要对象引用，例如嵌套的[StaticResource 标记扩展](staticresource-markup-extension.md)。  
  
- <xref:System.Windows.Data.Binding.IsAsync%2A>：布尔值，可以是 `true` 或 `false`。 默认值为 `false`。  
  
- <xref:System.Windows.Data.Binding.Mode%2A>：*值*是 <xref:System.Windows.Data.BindingMode> 枚举中的常量名。 例如 `{Binding Mode=OneWay}`。  
  
- <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>：布尔值，可以是 `true` 或 `false`。 默认值为 `false`。  
  
- <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>：布尔值，可以是 `true` 或 `false`。 默认值为 `false`。  
  
- <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>：布尔值，可以是 `true` 或 `false`。 默认值为 `false`。  
  
- <xref:System.Windows.Data.Binding.Path%2A>：描述数据对象或常规对象模型的路径的字符串。 格式为遍历对象模型提供了几种不同的约定，此约定在本主题中无法充分介绍。 请参阅[PROPERTYPATH XAML 语法](propertypath-xaml-syntax.md)。  
  
- <xref:System.Windows.Data.Binding.RelativeSource%2A>：与 <xref:System.Windows.Data.Binding.ElementName%2A> 和 <xref:System.Windows.Data.Binding.Source%2A>互相排斥;其中每个绑定属性都表示一个特定的绑定方法。 请参阅[数据绑定概述](../data/data-binding-overview.md)。 要求使用嵌套的[RelativeSource MarkupExtension](relativesource-markupextension.md) ，以指定值。  
  
- <xref:System.Windows.Data.Binding.Source%2A>：互相排斥与 <xref:System.Windows.Data.Binding.RelativeSource%2A> 和 <xref:System.Windows.Data.Binding.ElementName%2A>;其中每个绑定属性都表示一个特定的绑定方法。 请参阅[数据绑定概述](../data/data-binding-overview.md)。 要求使用嵌套扩展用法，通常是一个[StaticResource 的标记扩展](staticresource-markup-extension.md)，它从键控资源字典引用对象数据源。  
  
- <xref:System.Windows.Data.BindingBase.StringFormat%2A>：一个字符串，描述绑定数据的字符串格式约定。 这是一个相对较高级的绑定概念;请参阅 <xref:System.Windows.Data.BindingBase.StringFormat%2A>的参考页。  
  
- <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>：可以设置为表达式中的 `bindProp`=`value` 字符串，但这取决于传递的参数的类型。 如果传递值的引用类型，则需要对象引用，例如嵌套的[StaticResource 标记扩展](staticresource-markup-extension.md)。  
  
- <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>：*值*是 <xref:System.Windows.Data.UpdateSourceTrigger> 枚举中的常量名。 例如 `{Binding UpdateSourceTrigger=LostFocus}`。 对于此绑定属性，特定控件可能具有不同的默认值。 请参阅<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
- <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>：布尔值，可以是 `true` 或 `false`。 默认值为 `false`。 请参阅“备注”。  
  
- <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>：布尔值，可以是 `true` 或 `false`。 默认值为 `false`。 请参阅“备注”。  
  
- <xref:System.Windows.Data.Binding.XPath%2A>：描述 XML 数据源的 XMLDOM 路径的字符串。 请参阅[使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)。  
  
 下面是不能使用 `Binding` 标记扩展/`{Binding}` 表达式格式设置的 <xref:System.Windows.Data.Binding> 属性。  
  
- <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>：此属性需要对回调实现的引用。 不能在 XAML 语法中引用事件处理程序以外的回调/方法。  
  
- <xref:System.Windows.Data.Binding.ValidationRules%2A>：属性采用 <xref:System.Windows.Controls.ValidationRule> 对象的泛型集合。 这可以表示为 <xref:System.Windows.Data.Binding> 对象元素中的属性元素，但没有任何可用于 `Binding` 表达式中的用法的属性分析技术。 有关 <xref:System.Windows.Data.Binding.ValidationRules%2A>，请参阅参考主题。  
  
- <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## <a name="remarks"></a>备注  
  
> [!IMPORTANT]
> 就依赖属性优先级而言，`Binding` 表达式等效于本地设置的值。 如果为先前具有 `Binding` 表达式的属性设置本地值，则 `Binding` 将被完全删除。 有关详细信息，请参阅[依赖属性值优先级](dependency-property-value-precedence.md)。  
  
 本主题不涉及在基本级别描述数据绑定。 请参阅[数据绑定概述](../data/data-binding-overview.md)。  
  
> [!NOTE]
> <xref:System.Windows.Data.MultiBinding> 和 <xref:System.Windows.Data.PriorityBinding> 不支持 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 扩展语法。 您将改用属性元素。 有关 <xref:System.Windows.Data.MultiBinding> 和 <xref:System.Windows.Data.PriorityBinding>，请参阅参考主题。  
  
 XAML 的布尔值不区分大小写。 例如，可以指定 `{Binding NotifyOnValidationError=true}` 或 `{Binding NotifyOnValidationError=True}`。  
  
 涉及数据验证的绑定通常由显式 `Binding` 元素指定，而不是作为 `{Binding ...}` 表达式指定，在表达式中设置 <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> 或 <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> 的情况并不常见。 这是因为无法在表达式窗体中轻松设置伴生属性 <xref:System.Windows.Data.Binding.ValidationRules%2A>。 有关详细信息，请参阅[实现绑定验证](../data/how-to-implement-binding-validation.md)。  
  
 `Binding` 是标记扩展。 通常在要求转义特性值时，通常会实现标记扩展，而不是文本值或处理程序名称，并且该要求比在某些类型或属性上指定的类型转换器更全局性。 XAML 中的所有标记扩展在其特性语法中使用 `{` 和 `}` 字符，这是 XAML 处理器识别标记扩展必须处理字符串内容的约定。 有关详细信息，请参阅[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。  
  
 `Binding` 是一种典型的标记扩展，因为实现 WPF XAML 实现扩展功能的 <xref:System.Windows.Data.Binding> 类还实现了与 XAML 无关的多个其他方法和属性。 其他成员旨在使 <xref:System.Windows.Data.Binding> 一个更通用的自包含类，除了作为 XAML 标记扩展外，还可以处理许多数据绑定方案。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Data.Binding>
- [数据绑定概述](../data/data-binding-overview.md)
- [XAML 概述 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)
