---
title: 自定义类型和库的 XAML 相关 CLR 特性
ms.date: 03/30/2017
helpviewer_keywords:
- CLR attributes for custom types [XAML Services]
ms.assetid: 5dfb299a-b6e2-41b8-8694-e6ac987547f1
ms.openlocfilehash: 5481d02e4d393312fa0f0dd13b45c54acc567e13
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432982"
---
# <a name="xaml-related-clr-attributes-for-custom-types-and-libraries"></a>用于自定义类型和库的与 XAML 相关的 CLR 属性

本主题介绍由 .NET XAML 服务定义的通用语言运行时 （CLR） 属性。 它还描述了在 .NET 中定义的其他 CLR 属性，这些属性具有与 XAML 相关的方案，用于应用程序到程序集或类型。 将这些 CLR 属性的程序集、类型或成员归为具有 XAML 类型系统信息，这些信息与您的类型相关。 信息提供给使用 .NET XAML 服务直接或通过专用 XAML 读取器和 XAML 编写器处理 XAML 节点流的任何 XAML 使用者。

## <a name="xaml-related-clr-attributes-for-custom-types-and-custom-members"></a>用于自定义类型和自定义成员的 XAML 相关 CLR 属性

使用 CLR 属性意味着您使用整个 CLR 来定义类型，否则此类属性不可用。 如果使用 CLR 定义类型备份，则 .NET XAML 服务 XAML 编写器使用的默认 XAML 架构上下文可以通过反射来读取 CLR 归因。

以下各节介绍可应用于自定义类型或自定义成员的与 XAML 相关的属性。 每个 CLR 属性都传达与 XAML 类型系统相关的信息。 在加载路径中，属性化信息要么帮助 XAML 读取器形成有效的 XAML 节点流，要么帮助 XAML 编写器生成有效的对象图。 在保存路径中，属性化信息要么帮助 XAML 读取器形成有效的 XAML 节点流，从而重新构成 XAML 类型系统信息;或者声明 XAML 编写器或其他 XAML 使用者的序列化提示或要求。

### <a name="ambientattribute"></a>环境属性

**参考文档：**<xref:System.Windows.Markup.AmbientAttribute>

**适用于：** 支持可附加属性的`get`类、属性或访问器成员。

**参数：** 没有

<xref:System.Windows.Markup.AmbientAttribute>指示属性或采用属性类型的所有属性应在 XAML 中的环境属性概念下解释。 环境概念涉及 XAML 处理器如何确定成员的类型所有者。 环境属性是一个属性，在创建对象图时，该值在解析器上下文中可用，但在创建的直接 XAML 节点集时暂停典型的类型成员查找的属性。

环境概念可以应用于可附加成员，这些成员在 CLR 属性定义方面不表示为属性<xref:System.AttributeTargets>。 方法归因用应仅适用于支持 XAML 可附加用法的`get`访问者。

### <a name="constructorargumentattribute"></a>构造函数参数属性

**参考文档：**  <xref:System.Windows.Markup.ConstructorArgumentAttribute>

**适用于：** 类

**参数：** 指定与单个构造函数参数匹配的属性名称的字符串。

<xref:System.Windows.Markup.ConstructorArgumentAttribute>指定可以使用非参数构造函数语法初始化对象，并且指定名称的属性提供构造信息。 此信息主要用于 XAML 序列化。 有关详细信息，请参阅 <xref:System.Windows.Markup.ConstructorArgumentAttribute>。

### <a name="contentpropertyattribute"></a>内容属性属性

**参考文档：**  <xref:System.Windows.Markup.ContentPropertyAttribute>

**适用于：** 类

**参数：** 指定属性类型成员名称的字符串。

<xref:System.Windows.Markup.ContentPropertyAttribute>指示参数命名的属性应用作该类型的 XAML 内容属性。 XAML 内容属性定义将继承到可分配给定义类型的所有派生类型。 可以通过应用于<xref:System.Windows.Markup.ContentPropertyAttribute>特定派生类型来覆盖特定派生类型上的定义。

对于用作 XAML 内容属性的属性，可以在 XAML 用法中省略该属性的属性元素标记。 通常，您指定 XAML 内容属性，这些属性可为您的内容和包含模型推广简化的 XAML 标记。 由于只能将一个成员指定为 XAML 内容属性，因此您有时可以选择将某种类型的多个容器属性中的哪一个指定为 XAML 内容属性。 其他容器属性必须与显式属性元素一起使用。

在 XAML 节点流中，XAML 内容`StartMember`属性`EndMember`仍使用 的属性的名称生成和节点<xref:System.Xaml.XamlMember>。 要确定成员是否为 XAML 内容属性，请从<xref:System.Xaml.XamlType>`StartObject`位置检查值并获取 的值<xref:System.Xaml.XamlType.ContentProperty%2A>。

### <a name="contentwrapperattribute"></a>内容包装属性

**参考文档：**  <xref:System.Windows.Markup.ContentWrapperAttribute>

**适用于：** 类，特别是集合类型。

**参数：** 指定<xref:System.Type>用作外国内容内容包装类型的类型的类型。

<xref:System.Windows.Markup.ContentWrapperAttribute>指定将用于包装外来内容的关联集合类型的一个或多个类型。 外国内容是指内容属性类型的类型系统约束未捕获拥有类型的 XAML 使用的所有可能内容情形的情况。 例如，对特定类型内容的 XAML 支持可能支持强类型泛型<xref:System.Collections.ObjectModel.Collection%601>中的字符串。 内容包装器可用于将预先存在的标记约定迁移到 XAML 的集合可分配值的概念中，例如迁移与文本相关的内容模型。

要指定多个内容包装类型，请多次应用该属性。

### <a name="dependsonattribute"></a>依赖属性

**参考文档：**  <xref:System.Windows.Markup.DependsOnAttribute>

**适用于：** 财产

**参数：** 指定属性类型另一个成员名称的字符串。

<xref:System.Windows.Markup.DependsOnAttribute>指示属性属性取决于另一个属性的值。 将此属性应用于属性定义可确保在 XAML 对象写入中首先处理从属属性。 的<xref:System.Windows.Markup.DependsOnAttribute>用法指定属性的特殊情况，这些类型对于有效对象创建必须遵循特定的分析顺序。

您可以将多个<xref:System.Windows.Markup.DependsOnAttribute>案例应用于属性定义。

### <a name="markupextensionreturntypeattribute"></a>标记扩展返回类型属性

**参考文档：**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>

**适用于：** 类，应为<xref:System.Windows.Markup.MarkupExtension>派生类型。

**参数：**<xref:System.Type>指定作为`ProvideValue`属性<xref:System.Windows.Markup.MarkupExtension>的结果预期的最精确类型。

有关详细信息，请参阅[XAML 概述的标记扩展](markup-extensions-overview.md)。

### <a name="namescopepropertyattribute"></a>名称范围属性

**参考文档：**  <xref:System.Windows.Markup.NameScopePropertyAttribute>

**适用于：** 类

**参数：** 支持两种归因形式：

- 指定属性类型上属性名称的字符串。

- 指定属性名称的字符串，以及定义命名属性的类型的<xref:System.Type>的 字符串。 此窗体用于将可附加成员指定为 XAML 命名范围属性。

<xref:System.Windows.Markup.NameScopePropertyAttribute>指定为属性类提供 XAML 命名范围值的属性。 XAML 命名范围属性应引用实现<xref:System.Windows.Markup.INameScope>并保存实际 XAML 名称范围、其存储及其行为的对象。

### <a name="runtimenamepropertyattribute"></a>运行时名称属性属性

**参考文档：**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>

**适用于：** 类

**参数：** 指定属性化类型上的运行时名称属性名称的字符串。

<xref:System.Windows.Markup.RuntimeNamePropertyAttribute>报告映射到 XAML [x：Name 指令](xname-directive.md)的属性类型。 属性必须为类型<xref:System.String>，并且必须读取/写入。

定义将继承到可分配给定义类型的所有派生类型。 可以通过应用于<xref:System.Windows.Markup.RuntimeNamePropertyAttribute>特定派生类型来覆盖特定派生类型上的定义。

### <a name="trimsurroundingwhitespaceattribute"></a>修剪包围空白属性

**参考文档：**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>

**适用于：** 类型

**参数：** 没有。

<xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>应用于可能显示为空白重要内容中的子元素的特定类型（由 具有<xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>的集合持有的内容）。 <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>主要与保存路径相关，但通过检查<xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=nameWithType>在负载路径中的 XAML 类型系统中可用。 有关详细信息，请参阅[XAML 中的空白处理](white-space-processing.md)。

### <a name="typeconverterattribute"></a>TypeConverterAttribute

**参考文档：**  <xref:System.ComponentModel.TypeConverterAttribute>

**适用于：** 类、属性、方法（唯一`get`的 XAML 有效方法大小写是支持可连接成员的访问器）。

**参数：** 的<xref:System.Type> <xref:System.ComponentModel.TypeConverter>。

<xref:System.ComponentModel.TypeConverterAttribute>在 XAML 上下文中引用自定义<xref:System.ComponentModel.TypeConverter>。 这为<xref:System.ComponentModel.TypeConverter>自定义类型或该类型的成员提供类型转换行为。

将<xref:System.ComponentModel.TypeConverterAttribute>该属性应用于类型，引用类型转换器实现。 您可以在类、结构或接口上为 XAML 定义类型转换器。 您无需为枚举提供类型转换，该转换是本机启用的。

类型转换器应该能够从用于标记中的属性或初始化文本的字符串转换为预期的目标类型。 有关详细信息，请参阅[类型转换器和 XAML](../../framework/wpf/advanced/typeconverters-and-xaml.md)。

也可以在特定属性上建立 XAML 的类型转换器行为，而不是应用于类型的所有值。 在这种情况下，您将应用于<xref:System.ComponentModel.TypeConverterAttribute>属性定义（外部定义，而不是特定`get`定义和`set`定义）。

可以通过应用于<xref:System.ComponentModel.TypeConverterAttribute>支持 XAML 用法`get`的方法访问器来分配自定义可连接成员的 XAML 使用的类型转换器行为。

与<xref:System.ComponentModel.TypeConverter>类似<xref:System.ComponentModel.TypeConverterAttribute>，在 XAML 存在之前存在于 .NET 中，类型转换器模型具有其他用途。 为了引用和使用<xref:System.ComponentModel.TypeConverterAttribute>，您必须完全限定它或提供`using`语句。 <xref:System.ComponentModel> 还在项目中包括系统程序集。

### <a name="uidpropertyattribute"></a>乌德属性

**参考文档：**  <xref:System.Windows.Markup.UidPropertyAttribute>

**适用于：** 类

**参数：** 按名称引用相关属性的字符串。

指示别名[x：Uid 指令](xuid-directive.md)的类的 CLR 属性。

### <a name="usableduringinitializationattribute"></a>初始化期间可用属性

**参考文档：**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute>

**适用于：** 类

**参数：** 一个布尔。 如果用于属性的预期用途，则该值应设置为`true`。

指示类型在 XAML 对象图形创建期间是否自上而下生成。 这是一个高级概念，可能与编程模型的定义密切相关。 有关详细信息，请参阅 <xref:System.Windows.Markup.UsableDuringInitializationAttribute>。

### <a name="valueserializerattribute"></a>值序列器属性

**参考文档：**  <xref:System.Windows.Markup.ValueSerializerAttribute>

**适用于：** 类、属性、方法（唯一`get`的 XAML 有效方法大小写是支持可连接成员的访问器）。

**参数：** 指定<xref:System.Type>在序列化属性类型或特定属性属性的所有属性时要使用的值序列化器支持类。

<xref:System.Windows.Markup.ValueSerializer>指定一个值序列化类，该类需要比 更多的<xref:System.ComponentModel.TypeConverter>状态和上下文。 <xref:System.Windows.Markup.ValueSerializer>通过将属性应用于可附加成员的静态<xref:System.Windows.Markup.ValueSerializerAttribute>`get`访问器方法，可以与可连接成员关联。 值序列化也适用于枚举、接口和结构，但不适用于委托。

### <a name="whitespacesignificantcollectionattribute"></a>空白显著集合属性

**参考文档：**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>

**适用于：** 类，特别是预期承载混合内容的集合类型，其中对象元素周围的空白对于 UI 表示可能很重要。

**参数：** 没有。

<xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>指示集合类型应被 XAML 处理器处理为具有显著意义的空格，这会影响集合中 XAML 节点流的值节点的构造。 有关详细信息，请参阅[XAML 中的空白处理](white-space-processing.md)。

### <a name="xamldeferloadattribute"></a>XamlDeferLoad 属性

**参考文档：**  <xref:System.Windows.Markup.XamlDeferLoadAttribute>

**适用于：** 类，属性。

**参数：** 支持两个归因窗体类型作为字符串，或<xref:System.Type>类型为 。 请参阅 <xref:System.Windows.Markup.XamlDeferLoadAttribute>。

指示类或属性具有 XAML 的延迟加载用途（如模板行为），并报告启用延迟行为及其目标/内容类型的类。

### <a name="xamlsetmarkupextensionattribute"></a>XamlSetMarkup 扩展属性

**参考文档：**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute>

**适用于：** 类

**参数：** 命名回调。

指示类可以使用标记扩展为一个或多个属性提供值，并引用 XAML 编写器在对类的任何属性执行标记扩展集操作之前应调用的处理程序。

### <a name="xamlsettypeconverterattribute"></a>XamlSet 类型转换器属性

**参考文档：**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute>

**适用于：** 类

**参数：** 命名回调。

指示类可以使用类型转换器为其一个或多个属性提供值，并引用 XAML 编写器在对类的任何属性执行类型转换器集操作之前应调用的处理程序。

### <a name="xmllangpropertyattribute"></a>XmlLang属性

**参考文档：**  <xref:System.Windows.Markup.XmlLangPropertyAttribute>

**适用于：** 类

**参数：** 一个字符串，用于在属性类型上指定属性的名称`xml:lang`到别名。

<xref:System.Windows.Markup.XmlLangPropertyAttribute>报告映射到 XML`lang`指令的属性类型的属性。 属性不一定是类型<xref:System.String>，但必须从字符串中分配（可以通过将类型转换器与属性的类型或特定属性相关联来实现）。 属性必须读/写。

映射`xml:lang`方案是，运行时对象模型可以访问 XML 指定的语言信息，而无需专门使用 XMLDOM 进行处理。

定义将继承到可分配给定义类型的所有派生类型。 可以通过应用于<xref:System.Windows.Markup.XmlLangPropertyAttribute>特定派生类型来覆盖特定派生类型上的定义，尽管这种情况并不常见。

## <a name="xaml-related-clr-attributes-at-the-assembly-level"></a>装配层级的 XAML 相关 CLR 属性

以下各节介绍不应用于类型或成员定义但应用于程序集的与 XAML 相关的属性。 这些属性与定义包含要在 XAML 中使用的自定义类型的库的总体目标相关。 某些属性不一定直接影响 XAML 节点流，而是在节点流中传递，供其他使用者使用。 信息的使用者包括需要 XAML 命名空间信息和关联的前缀信息的设计环境或序列化过程。 XAML 架构上下文（包括 .NET XAML 服务默认值）也使用此信息。

### <a name="xmlnscompatiblewithattribute"></a>与属性兼容的 Xmlns

**参考文档：**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>

**参数：**

- 指定要归纳的 XAML 命名空间的标识符的字符串。

- 指定 XAML 命名空间的标识符的字符串，该名称空间可以从上一个参数中归入 XAML 命名空间。

  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>指定 XAML 命名空间可以由另一个 XAML 命名空间进行归用。 通常，先前定义的 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 中指示了包含 XAML 命令空间。 此技术可用于在库中对 XAML 词汇进行版本控制，并使之与以前定义的标记（针对早期版本化的词汇表）兼容。

### <a name="xmlnsdefinitionattribute"></a>Xmlns 定义属性

**参考文档：**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>

**参数：**

- 指定要定义的 XAML 命名空间的标识符的字符串。

- 命名 CLR 命名空间的字符串。 CLR 命名空间应在程序集中定义公共类型，并且至少应使用一种 CLR 命名空间类型来使用 XAML。

  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>指定 XAML 命名空间和 CLR 命名空间之间的每个程序集映射，然后 XAML 对象编写器或 XAML 架构上下文用于类型解析。

  可以有多个<xref:System.Windows.Markup.XmlnsDefinitionAttribute>组件。 这可能是出于以下任何原因的组合：

- 库设计包含多个 CLR 命名空间，用于运行时 API 访问的逻辑组织;但是，您希望这些命名空间中的所有类型都可用于 XAML，通过引用相同的 XAML 命名空间。 在这种情况下，使用相同的<xref:System.Windows.Markup.XmlnsDefinitionAttribute><xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A>值但不同的<xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A>值应用多个属性。 如果要定义框架或应用程序打算成为常用的默认 XAML 命名空间的 XAML 命名空间的映射，则此功能尤其有用。

- 库设计包含多个 CLR 命名空间，您希望在这些 CLR 命名空间中类型的用法之间进行深思熟虑的 XAML 命名空间分离。

- 在程序集中定义 CLR 命名空间，并希望它可以通过多个 XAML 命名空间进行访问。 当您支持具有相同代码库的多个词汇库时，将发生此情况。

- 在一个或多个 CLR 命名空间中定义 XAML 语言支持。 在这种情况下，<xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A>值应为`http://schemas.microsoft.com/winfx/2006/xaml`。

### <a name="xmlnsprefixattribute"></a>Xmlns前缀属性

**参考文档：**  <xref:System.Windows.Markup.XmlnsPrefixAttribute>

**参数：**

- 指定 XAML 命名空间标识符的字符串。

- 指定建议前缀的字符串。

  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>指定用于 XAML 命名空间的建议前缀。 在由 .NET XAML 服务<xref:System.Xaml.XamlXmlWriter>序列化的 XAML 文件中编写元素和属性时，或者当 XAML 实现库与具有 XAML 编辑功能的设计环境交互时，前缀非常有用。

  可以有多个<xref:System.Windows.Markup.XmlnsPrefixAttribute>组件。 这可能是出于以下任何原因的组合：

- 程序集定义多个 XAML 命名空间的类型。 在这种情况下，为每个 XAML 命名空间定义不同的前缀值。

- 您支持多个词汇，并且对每个词汇表和 XAML 命名空间使用不同的前缀。

- 在程序集中定义 XAML 语言支持，并为<xref:System.Windows.Markup.XmlnsDefinitionAttribute>`http://schemas.microsoft.com/winfx/2006/xaml` 在这种情况下，通常应升级前缀`x`。

> [!NOTE]
> .NET XAML 服务还定义了与 XAML<xref:System.Windows.Markup.RootNamespaceAttribute>相关的属性 。 此属性是项目系统支持的程序集级属性，与 XAML 自定义类型无关。

## <a name="see-also"></a>请参阅

- <xref:System.Attribute>
- [定义与 .NET XAML 服务一起使用的自定义类型](define-custom-types.md)
