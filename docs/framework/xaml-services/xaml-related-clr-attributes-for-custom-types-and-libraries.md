---
title: "自定义类型和库的 XAML 相关 CLR 特性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: CLR attributes for custom types [XAML Services]
ms.assetid: 5dfb299a-b6e2-41b8-8694-e6ac987547f1
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 25aac1d4478279561cbcdda6c1cf912c3c3b2cde
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="xaml-related-clr-attributes-for-custom-types-and-libraries"></a>自定义类型和库的 XAML 相关 CLR 特性
本主题介绍由.NET Framework XAML 服务定义的公共语言运行时 (CLR) 属性。 它还介绍在.NET Framework 中定义具有对程序集或类型的应用程序的与 XAML 相关方案的其他 CLR 特性。 使用这些 CLR 特性的归程序集、 类型或成员提供与你的类型的 XAML 类型系统信息。 使用.NET Framework XAML 服务，用于处理 XAML 节点流直接或通过专用的 XAML 读取器和 XAML 编写器任何 XAML 使用者提供信息。  
  
## <a name="xaml-related-clr-attributes-for-custom-types-and-custom-members"></a>自定义类型和自定义成员与 XAML 相关 CLR 特性  
 使用 CLR 特性要求，你正在使用的总体 CLR 来定义类型，否则此类特性将不可用。 如果你使用 CLR 定义的类型支持，.NET Framework XAML 服务 XAML 编写器使用的默认 XAML 架构上下文可以读取通过反射对支持程序集的 CLR 特性。  
  
 以下各节描述了可应用于自定义的类型或自定义成员与 XAML 相关的属性。 每个 CLR 特性进行通信的 XAML 类型系统与相关的信息。 在加载路径中，特性化的信息可帮助形成有效的 XAML 节点流，XAML 读取器或帮助生成有效的对象图形的 XAML 编写器。 在保存路径，或者可帮助窗体将重组 XAML 类型系统信息; 有效的 XAML 节点流的 XAML 读取器的特性化的信息或它声明序列化提示或 XAML 编写器或其他 XAML 使用者的要求。  
  
### <a name="ambientattribute"></a>AmbientAttribute  
 **参考文档：**  <xref:System.Windows.Markup.AmbientAttribute>  
  
 **适用于：**类、 属性和或`get`支持可附加属性的访问器成员。  
  
 **自变量：**无  
  
 <xref:System.Windows.Markup.AmbientAttribute>指示属性或需要的特性化的类型的所有属性应解释在 XAML 中的环境属性概念。 环境概念涉及 XAML 处理器如何确定成员的类型所有者。 环境属性是属性值的地方时创建对象图，但其直接的 XAML 节点集正在创建已挂起，典型的类型成员查找要分析器上下文中可用。  
  
 环境概念可以应用于可附加成员，它们以在 CLR 特性定义的方式方面的属性不表示<xref:System.AttributeTargets>。 方法特性用法应仅在的情况下应用`get`针对的 XAML 支持可附加的使用情况的访问器。  
  
### <a name="constructorargumentattribute"></a>ConstructorArgumentAttribute  
 **参考文档：**  <xref:System.Windows.Markup.ConstructorArgumentAttribute>  
  
 **适用于：**类  
  
 **自变量：**一个字符串，指定与单个构造函数自变量匹配的属性的名称。  
  
 <xref:System.Windows.Markup.ConstructorArgumentAttribute>指定可以通过使用一个非默认构造函数的语法来初始化的对象和指定名称的属性提供构造信息。 此信息主要用于 XAML 序列化。 有关详细信息，请参阅<xref:System.Windows.Markup.ConstructorArgumentAttribute>。  
  
### <a name="contentpropertyattribute"></a>ContentPropertyAttribute  
 **参考文档：**  <xref:System.Windows.Markup.ContentPropertyAttribute>  
  
 **适用于：**类  
  
 **自变量：**一个字符串，指定的一个成员的特性化类型的名称。  
  
 <xref:System.Windows.Markup.ContentPropertyAttribute>指示命名自变量的属性应作为该类型的 XAML 内容属性。 XAML 内容属性定义继承到可分配给定义的类型的所有派生类型。 您可以通过应用来覆盖特定的派生类型上定义<xref:System.Windows.Markup.ContentPropertyAttribute>上特定于派生类型。  
  
 用作 XAML 内容属性的属性，可以在 XAML 用法省略属性元素标记的属性。 通常情况下，你指定将提升简洁的 XAML 标记的内容和包含模型的 XAML 内容属性。 因为只有一个成员可以指定为 XAML 内容属性，有时需要设计让的选择有关哪个多个容器的一种类型的属性应被指定为 XAML 内容属性。 其他容器属性必须与显式属性元素一起使用。  
  
 在 XAML 节点流，XAML 内容属性仍生成`StartMember`和`EndMember`使用的属性的名称的节点<xref:System.Xaml.XamlMember>。 若要确定成员是否为 XAML 内容属性，请检查<xref:System.Xaml.XamlType>值从`StartObject`定位，并获取的值<xref:System.Xaml.XamlType.ContentProperty%2A>。  
  
### <a name="contentwrapperattribute"></a>ContentWrapperAttribute  
 **参考文档：**  <xref:System.Windows.Markup.ContentWrapperAttribute>  
  
 **适用于：**类，具体集合类型。  
  
 **自变量：** A <xref:System.Type> ，它指定要用作外部内容的内容包装类型的类型。  
  
 <xref:System.Windows.Markup.ContentWrapperAttribute>指定将用于包装外部内容的关联的集合类型上的一个或多个类型。 外部内容是指其中的内容的属性类型的类型系统约束不捕获所有可能的内容事例所属类型的 XAML 用法本来支持的情况下。 例如，XAML 支持特定类型的内容可能支持字符串中的强类型化的泛型<xref:System.Collections.ObjectModel.Collection%601>。 内容的包装器可用于将预先存在的标记约定迁移到可分配的值对于集合，如迁移与文本相关的内容模型的 XAML 的概念。  
  
 若要指定多个内容包装类型，请将该属性多次。  
  
### <a name="dependsonattribute"></a>DependsOnAttribute  
 **参考文档：**  <xref:System.Windows.Markup.DependsOnAttribute>  
  
 **适用于：**属性  
  
 **自变量：**一个字符串，指定的特性化类型的另一个成员的名称。  
  
 <xref:System.Windows.Markup.DependsOnAttribute>指示特性化的属性依赖于另一个属性的值。 将此特性应用于属性定义可确保在 XAML 对象编写首先处理依赖属性。 用法<xref:System.Windows.Markup.DependsOnAttribute>其中的分析特定的顺序必须遵循有效的对象创建的类型上指定这种例外情况的属性。  
  
 你可以应用多个<xref:System.Windows.Markup.DependsOnAttribute>用例链接到的属性定义。  
  
### <a name="markupextensionreturntypeattribute"></a>MarkupExtensionReturnTypeAttribute  
 **参考文档：**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>  
  
 **适用于：**类，应为<xref:System.Windows.Markup.MarkupExtension>派生类型。  
  
 **自变量：** A <xref:System.Type> ，它指定要作为期望的最精确类型`ProvideValue`的特性化的结果<xref:System.Windows.Markup.MarkupExtension>。  
  
 有关详细信息，请参阅[的标记扩展 XAML 概述](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md)。  
  
### <a name="namescopepropertyattribute"></a>NameScopePropertyAttribute  
 **参考文档：**  <xref:System.Windows.Markup.NameScopePropertyAttribute>  
  
 **适用于：**类  
  
 **自变量：**支持两种形式的归属：  
  
-   一个字符串，指定的特性化类型的属性名称。  
  
-   一个字符串，指定属性的名称和一<xref:System.Type>定义的命名的属性的类型。 此窗体是用于将 XAML 名称范围属性指定可附加成员。  
  
 <xref:System.Windows.Markup.NameScopePropertyAttribute>指定为特性化类提供 XAML 名称范围值的属性。 XAML 名称范围属性应引用实现的对象<xref:System.Windows.Markup.INameScope>并保存的实际的 XAML 名称范围、 其存储区，其行为。  
  
### <a name="runtimenamepropertyattribute"></a>RuntimeNamePropertyAttribute  
 **参考文档：**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>  
  
 **适用于：**类  
  
 **自变量：**一个字符串，指定的特性化类型上的运行时名称属性的名称。  
  
 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>报告的属性映射到 XAML 的特性化类型[X:name 指令](../../../docs/framework/xaml-services/x-name-directive.md)。 属性的类型必须为<xref:System.String>并且必须是读/写。  
  
 定义继承到可分配给定义的类型的所有派生类型。 您可以通过应用来覆盖特定的派生类型上定义<xref:System.Windows.Markup.RuntimeNamePropertyAttribute>上特定于派生类型。  
  
### <a name="trimsurroundingwhitespaceattribute"></a>TrimSurroundingWhitespaceAttribute  
 **参考文档：**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>  
  
 **适用于：**类型  
  
 **自变量：** None。  
  
 <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>将应用于可能显示为在空格重要内容中的子元素的特定类型 (由一个包含集合的内容持有<xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>)。 <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>保存与主要相关路径，但可在加载路径 XAML 类型系统中通过检查<xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=nameWithType>。 有关详细信息，请参阅[在 XAML 中的空白处理](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)。  
  
### <a name="typeconverterattribute"></a>TypeConverterAttribute  
 **参考文档：**  <xref:System.ComponentModel.TypeConverterAttribute>  
  
 **适用于：**类、 属性、 方法 (唯一 XAML 有效方法用例是`get`支持可附加成员的访问器)。  
  
 **自变量：** <xref:System.Type>的<xref:System.ComponentModel.TypeConverter>。  
  
 <xref:System.ComponentModel.TypeConverterAttribute>在 XAML 中上下文引用自定义<xref:System.ComponentModel.TypeConverter>。 这<xref:System.ComponentModel.TypeConverter>为自定义类型或该类型的成员提供类型转换行为。  
  
 你将应用<xref:System.ComponentModel.TypeConverterAttribute>属性设为你的类型，引用您的类型转换器实现。 在类、 结构或接口，可以为 XAML 中定义的类型转换器。 不需要提供类型转换为枚举，转换启用了本机。  
  
 类型转换器应该能够从字符串转换你预期的目标类型用于特性或在标记中，初始化文本转换。 有关详细信息，请参阅[对和 XAML](../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md)。  
  
 而不是将应用于类型的所有值，XAML 的类型转换器行为还可以建立上的特定属性。 在这种情况下，应用<xref:System.ComponentModel.TypeConverterAttribute>到属性定义 (外部定义，而不是特定`get`和`set`定义)。  
  
 可以通过应用分配的自定义的可附加成员的 XAML 用法的类型转换器行为<xref:System.ComponentModel.TypeConverterAttribute>到`get`支持 XAML 用法的方法访问器。  
  
 类似于<xref:System.ComponentModel.TypeConverter>， <xref:System.ComponentModel.TypeConverterAttribute> XAML 存在之前.NET Framework 中存在并已对类型转换器模型提供其他目的。 为了引用并使用<xref:System.ComponentModel.TypeConverterAttribute>，你必须完全限定它，或者提供`using`语句<xref:System.ComponentModel>。 您还必须在你的项目中包含的系统程序集。  
  
### <a name="uidpropertyattribute"></a>UidPropertyAttribute  
 **参考文档：**  <xref:System.Windows.Markup.UidPropertyAttribute>  
  
 **适用于：**类  
  
 **自变量：**按名称引用相关的属性的字符串。  
  
 指示该别名的一个类的 CLR 属性[X:uid 指令](../../../docs/framework/xaml-services/x-uid-directive.md)。  
  
### <a name="usableduringinitializationattribute"></a>UsableDuringInitializationAttribute  
 **参考文档：**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute>  
  
 **适用于：**类  
  
 **自变量：**一个布尔值。 如果用于该特性的预期用途，这应始终指定为`true`。  
  
 指示在 XAML 对象图创建期间是否自上而下生成此类型。 这是一种高级的概念，这与编程模型的定义可能密切相关。 有关详细信息，请参阅<xref:System.Windows.Markup.UsableDuringInitializationAttribute>。  
  
### <a name="valueserializerattribute"></a>ValueSerializerAttribute  
 **参考文档：**  <xref:System.Windows.Markup.ValueSerializerAttribute>  
  
 **适用于：**类、 属性、 方法 (唯一 XAML 有效方法用例是`get`支持可附加成员的访问器)。  
  
 **自变量：** A <xref:System.Type> ，指定要在序列化的特性化类型的所有属性时使用的值序列化程序支持类或特定于特性化属性。  
  
 <xref:System.Windows.Markup.ValueSerializer>指定一个值序列化类，需要更多状态和以外的上下文<xref:System.ComponentModel.TypeConverter>未。 <xref:System.Windows.Markup.ValueSerializer>可以通过将应用与可附加成员相关联<xref:System.Windows.Markup.ValueSerializerAttribute>静态属性`get`可附加成员的访问器方法。 值序列化也适用于枚举、 接口和结构，但不适用于委托。  
  
### <a name="whitespacesignificantcollectionattribute"></a>WhitespaceSignificantCollectionAttribute  
 **参考文档：**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>  
  
 **适用于：**类，具体而言应承载混合的内容，其中对象元素周围的空白区域可能会很明显的 UI 表示形式的集合类型。  
  
 **自变量：** None。  
  
 <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>指示集合类型应为空格处理由 XAML 处理器，这会影响集合中的 XAML 节点流的值节点的构造。 有关详细信息，请参阅[在 XAML 中的空白处理](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)。  
  
### <a name="xamldeferloadattribute"></a>XamlDeferLoadAttribute  
 **参考文档：**  <xref:System.Windows.Markup.XamlDeferLoadAttribute>  
  
 **适用于：**类、 属性。  
  
 **自变量：**支持两个归属窗体以字符串形式的类型或类型用作<xref:System.Type>。 请参阅 <xref:System.Windows.Markup.XamlDeferLoadAttribute>。  
  
 指示类或属性 （如模板行为），具有 xaml 的延迟的加载使用情况和报告类，使推迟行为和其目标中的内容类型。  
  
### <a name="xamlsetmarkupextensionattribute"></a>XamlSetMarkupExtensionAttribute  
 **参考文档：**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute>  
  
 **适用于：**类  
  
 **自变量：**名称回调。  
  
 指示类可以使用标记扩展提供的值为一个或多个属性，并引用 XAML 编写器应在执行标记扩展类的任何属性上设置操作之前调用的处理程序。  
  
### <a name="xamlsettypeconverterattribute"></a>XamlSetTypeConverterAttribute  
 **参考文档：**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute>  
  
 **适用于：**类  
  
 **自变量：**名称回调。  
  
 指示类可以使用的类型转换器提供的值为一个或多个属性，并引用 XAML 编写器应在执行上类的任何属性类型转换器设置操作之前调用的处理程序。  
  
### <a name="xmllangpropertyattribute"></a>XmlLangPropertyAttribute  
 **参考文档：**  <xref:System.Windows.Markup.XmlLangPropertyAttribute>  
  
 **适用于：**类  
  
 **自变量：**一个字符串，指定将属性设为别名的名称`xml:lang`上的特性化类型。  
  
 <xref:System.Windows.Markup.XmlLangPropertyAttribute>报告的属性映射到 XML 的特性化类型`lang`指令。 属性一定不属于类型<xref:System.String>，但必须从字符串 （这可以通过将与该属性的类型或特定属性相关联的类型转换器来实现） 赋值。 该属性必须是读/写。  
  
 映射的方案`xml:lang`以便运行时对象模型而不会专门处理与 XMLDOM 可以访问的 XML 指定语言信息。  
  
 定义继承到可分配给定义的类型的所有派生类型。 您可以通过应用来覆盖特定的派生类型上定义<xref:System.Windows.Markup.XmlLangPropertyAttribute>上特定于派生类型，但这一情况不常见。  
  
## <a name="xaml-related-clr-attributes-at-the-assembly-level"></a>程序集级别的与 XAML 相关 CLR 特性  
 以下各节描述了与 XAML 相关的属性不会应用于类型或成员定义，但改为应用于程序集。 这些特性是相关的定义包含要在 XAML 中使用的自定义类型的库的总体目标。 某些特性不一定影响 XAML 节点流直接，但在其他使用者可以使用节点流中上进行传递。 使用者的信息包括设计环境或需要 XAML 命名空间信息以及关联的前缀信息的序列化进程。 XAML 架构上下文 （包括.NET Framework XAML 服务默认值） 也使用此信息。  
  
### <a name="xmlnscompatiblewithattribute"></a>XmlnsCompatibleWithAttribute  
 **参考文档：**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>  
  
 **自变量：**  
  
-   一个字符串，指定要归类的 XAML 命名空间的标识符。  
  
-   一个字符串，指定可以归类从以前的自变量的 XAML 命名空间的 XAML 命名空间的标识符。  
  
 <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>指定 XAML 命名空间，可以归入其他 XAML 命名空间。 通常，表示包含 XAML 命令空间中之前定义<xref:System.Windows.Markup.XmlnsDefinitionAttribute>。 此方法可用于版本控制的 XAML 词汇库中并使其与以前版本的词汇针对以前定义的标记兼容。  
  
### <a name="xmlnsdefinitionattribute"></a>XmlnsDefinitionAttribute  
 **参考文档：**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>  
  
 **自变量：**  
  
-   一个字符串，指定要定义的 XAML 命名空间的标识符。  
  
-   命名的 CLR 命名空间的字符串。 CLR 命名空间应在程序集中定义公共类型和 CLR 命名空间类型至少应适用于 XAML 用法。  
  
 <xref:System.Windows.Markup.XmlnsDefinitionAttribute>指定每个程序集基于 XAML 命名空间和 CLR 命名空间，然后使用以进行类型解析由 XAML 对象编写器或 XAML 架构上下文之间的映射。  
  
 多个<xref:System.Windows.Markup.XmlnsDefinitionAttribute>可以应用于程序集。 这可能会出于以下原因的任意组合：  
  
-   库设计包含用于运行时 API 访问; 的逻辑组织的多个 CLR 命名空间但是，你希望这些命名空间中的所有类型，能够通过引用相同的 XAML 命名空间 XAML 可用。 在这种情况下，应用多个<xref:System.Windows.Markup.XmlnsDefinitionAttribute>属性使用相同<xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A>值但不同<xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A>值。 这是特别有用，如果要定义你 framework 或应用程序打算默认 XAML 命名空间处于常见用法的 XAML 命名空间的映射。  
  
-   库设计包含多个 CLR 命名空间，并且你希望故意的 XAML 命名空间分隔了这些 CLR 命名空间中类型的用法。  
  
-   你在程序集中，定义 CLR 命名空间，而您希望其可通过多个 XAML 命名空间进行访问。 当你支持多个具有相同的基本代码的词汇表，将出现这种情况。  
  
-   你可以在一个或多个 CLR 命名空间中定义 XAML 语言支持。 对于这些数据，<xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A>值应为`http://schemas.microsoft.com/winfx/2006/xaml`。  
  
### <a name="xmlnsprefixattribute"></a>XmlnsPrefixAttribute  
 **参考文档：**  <xref:System.Windows.Markup.XmlnsPrefixAttribute>  
  
 **自变量：**  
  
-   一个字符串，指定 XAML 命名空间的标识符。  
  
-   一个字符串，指定的推荐的前缀。  
  
 <xref:System.Windows.Markup.XmlnsDefinitionAttribute>指定要用于 XAML 命名空间的推荐的前缀。 在序列化.NET Framework XAML 服务 XAML 文件中编写元素和属性时，该前缀是有用<xref:System.Xaml.XamlXmlWriter>，或当 XAML 实现的库交互与具有 XAML 的设计环境编辑功能。  
  
 多个<xref:System.Windows.Markup.XmlnsPrefixAttribute>可以应用于程序集。 这可能会出于以下原因的任意组合：  
  
-   程序集定义多个 XAML 命名空间的类型。 在这种情况下应定义每个 XAML 命名空间不同的前缀的值。  
  
-   支持多个词汇，并为每个词汇和 XAML 命名空间中使用不同的前缀。  
  
-   在程序集中定义 XAML 语言支持和具有<xref:System.Windows.Markup.XmlnsDefinitionAttribute>为`http://schemas.microsoft.com/winfx/2006/xaml`。 在这种情况下，通常应提升前缀`x`。  
  
> [!NOTE]
>  .NET framework XAML 服务还定义了与 XAML 相关的特性<xref:System.Windows.Markup.RootNamespaceAttribute>。 此属性是用于项目系统支持一个程序集级别属性，但不与 XAML 自定义类型有关。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Attribute>  
 [定义与 .NET Framework XAML 服务一起使用的自定义类型](../../../docs/framework/xaml-services/defining-custom-types-for-use-with-net-framework-xaml-services.md)
