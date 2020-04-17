---
title: 定义与 .NET XAML 服务一起使用的自定义类型
ms.date: 03/30/2017
helpviewer_keywords:
- defining custom types [XAML Services]
ms.assetid: c2667cbd-2f46-4a7f-9dfc-53696e35e8e4
ms.openlocfilehash: ff7e4229450e801a6d618c5141efde8cdcbef03d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433072"
---
# <a name="define-custom-types-for-use-with-net-xaml-services"></a>定义用于 .NET XAML 服务的自定义类型

当您定义业务对象或对特定框架不依赖的类型时，您可以遵循 XAML 的某些最佳做法。 如果您遵循这些实践，.NET XAML 服务及其 XAML 读取器和 XAML 编写器可以发现您类型的 XAML 特征，并使用 XAML 类型系统在 XAML 节点流中为其提供适当的表示形式。 本主题介绍类型定义、成员定义和类型或成员的 CLR 归因的最佳做法。

## <a name="constructor-patterns-and-type-definitions-for-xaml"></a>XAML 的构造函数模式和类型定义

要在 XAML 中实例化为对象元素，自定义类必须满足以下要求：

- 自定义类必须是公共的，并且必须公开无参数的公共构造函数。 （有关结构注释，请参阅下节内容。）

- 自定义类不能是嵌套类。 全名路径中的额外"点"使类命名空间划分不明确，并干扰其他 XAML 功能（如附加属性）。
如果对象可以实例化为对象元素，则创建的对象可以填充将对象作为其基础类型的任何属性的属性元素形式。

如果启用值转换器，仍可以为不符合这些标准的类型提供对象值。 有关详细信息，请参阅[XAML 的类型转换器和标记扩展](type-converters-and-markup-extensions.md)。

### <a name="structures"></a>结构

结构始终能够在 XAML 中通过 CLR 定义构造。 这是因为 CLR 编译器隐式为结构创建了无参数构造函数。 此构造函数将所有属性值初始化到其默认值。

在某些情况下，结构的默认构造行为是不需要的。 这可能是因为结构旨在填充值，并在概念上作为联合进行函数。 作为联合，包含的值可能具有互斥的解释，因此，其属性都不是可设置的。 WPF 词汇中这种结构的一个示例是<xref:System.Windows.GridLength>。 此类结构应实现类型转换器，以便通过使用创建结构值的不同解释或模式的字符串约定，以属性形式表示值。 结构还应通过非参数构造函数公开代码构造的类似行为。

### <a name="interfaces"></a>接口

接口可用作成员的基础类型。 XAML 类型系统检查可分配列表，并期望作为值提供的对象可以分配给接口。 只要相关的可分配类型支持 XAML 构造要求，则对于接口必须作为 XAML 类型呈现的概念是没有概念的。

### <a name="factory-methods"></a>工厂方法

工厂方法是 XAML 2009 功能。 它们修改了 XAML 原则，即对象必须具有无参数构造函数。 本文没有记录工厂方法。 请参阅[x：工厂方法指令](xfactorymethod-directive.md)。

## <a name="enumerations"></a>枚举

枚举具有 XAML 本机类型转换行为。 根据基础枚举类型解析 XAML 中指定的枚举常量名称，并将枚举值返回给 XAML 对象编写器。

XAML 支持<xref:System.FlagsAttribute>应用的枚举标记样式用法。 有关详细信息，请参阅[XAML 语法详细信息](../../framework/wpf/advanced/xaml-syntax-in-detail.md)。 [（XAML 语法详细](../../framework/wpf/advanced/xaml-syntax-in-detail.md)为 WPF 受众编写，但该主题中的大多数信息与不特定于特定实现框架的 XAML 相关。

## <a name="member-definitions"></a>成员定义

类型可以为 XAML 使用定义成员。 类型可以定义 XAML 可用的成员，即使该特定类型不可用于 XAML。 这是可能的，因为CLR继承。 只要继承该成员的某些类型支持 XAML 使用作为类型，并且该成员支持其基础类型的 XAML 用法或具有本机 XAML 语法可用，该成员即可用于 XAML。

### <a name="properties"></a>属性

如果使用典型的`get`CLR 和访问模式以及`set`语言适当的关键字将属性定义为公共 CLR 属性，则 XAML 类型系统可以将该属性报告为成员，并提供有关<xref:System.Xaml.XamlMember>属性（如<xref:System.Xaml.XamlMember.IsReadPublic%2A>和<xref:System.Xaml.XamlMember.IsWritePublic%2A>）等属性的适当信息。

特定属性可以通过应用<xref:System.ComponentModel.TypeConverterAttribute>启用文本语法来启用文本语法。 有关详细信息，请参阅[XAML 的类型转换器和标记扩展](type-converters-and-markup-extensions.md)。

在没有文本语法或本机 XAML 转换的情况下，在没有进一步间接（如标记扩展用法）的情况下，属性的类型（<xref:System.Xaml.XamlMember.TargetType%2A>在 XAML 类型系统中）必须能够将实例视为 CLR 类型，将实例返回到 XAML 对象编写器。

如果使用 XAML 2009，则如果未满足以前的注意事项，可以使用[x：参考标记扩展](xreference-markup-extension.md)提供值;但是，这更多的是使用问题，而不是类型定义问题。

### <a name="events"></a>事件

如果将事件定义为公共 CLR 事件，XAML 类型系统可以将事件报告为 具有<xref:System.Xaml.XamlMember.IsEvent%2A>的成员。 `true` 连接事件处理程序不在 .NET XAML 服务功能范围内;因此，在 .NET XAML 服务功能范围内，则对事件处理程序进行布线。线路留给特定的框架和实现。

### <a name="methods"></a>方法

方法的内联代码不是默认的 XAML 功能。 在大多数情况下，您不会直接引用 XAML 中的方法成员，并且方法在 XAML 中的角色只是为特定的 XAML 模式提供支持。 [x：工厂方法指令](xfactorymethod-directive.md)是一个例外。

### <a name="fields"></a>字段

CLR 设计指南阻止非静态字段。 对于静态字段，只能通过[x：静态标记扩展](xstatic-markup-extension.md)访问静态字段值。在这种情况下，您没有在 CLR 定义中执行任何特殊操作来公开[x：静态](xstatic-markup-extension.md)用法的字段。

## <a name="attachable-members"></a>可附加成员

可附加成员通过定义类型上的访问器方法模式向 XAML 公开。 定义类型本身不需要 XAML 作为对象可用。 实际上，一种常见模式是声明服务类，其作用是拥有可附加成员并实现相关行为，但不提供其他函数，如 UI 表示形式。 对于以下部分，占位符*属性名称*表示可附加成员的名称。 该名称必须在[XamlName 语法](xamlname-grammar.md)中有效。

小心这些模式和类型的其他方法之间的名称冲突。 如果存在与其中一种模式匹配的成员，则 XAML 处理器可以将其解释为可附加成员使用路径，即使这不是您的意图。

#### <a name="the-getpropertyname-accessor"></a>获取属性名称访问器

访问器的签名`GetPropertyName`必须为：

`public static object GetPropertyName(object target)`

- `target` 对象在实现中可以指定为更具体的类型。 您可以使用它来限定可附加成员的使用范围;预期范围以外的用法将引发无效强制转换异常，然后由 XAML 分析错误显示。 参数名称`target`不是要求，但在大多数实现中按约定`target`命名。

- 返回值在实现中可以指定为更具体的类型。

要支持<xref:System.ComponentModel.TypeConverter>启用的文本语法，以便附加成员的属性使用，请应用于<xref:System.ComponentModel.TypeConverterAttribute>`GetPropertyName`访问器。 申请`get`，而不是`set`可能看起来不直观;但是，此约定可以支持可序列化的只读可附加成员的概念，这在设计器方案中很有用。

#### <a name="the-setpropertyname-accessor"></a>设置属性名称访问器

访问器的签名`SetPropertyName`必须为：

`public static void SetPropertyName(object target, object value)`

- 该`target`对象可以指定为实现中更具体的类型，其逻辑和后果与上一节所述相同。

- `value` 对象在实现中可以指定为更具体的类型。

请记住，此方法的值是来自 XAML 用法的输入，通常以属性形式提供。 从属性窗体中，必须支持文本语法的值转换器，并且对`GetPropertyName`s 访问器的属性。

### <a name="attachable-member-stores"></a>可附加会员商店

访问器方法通常不足以提供将可附加成员值放入对象图形的方法，或从对象图中检索值并正确序列化它们。 要提供此功能，`target`以前访问器签名中的对象必须能够存储值。 存储机制应符合可附加成员原则，即成员可附加到可附加成员不在成员列表中的目标。 .NET XAML 服务通过 API<xref:System.Xaml.IAttachedPropertyStore>和<xref:System.Xaml.AttachablePropertyServices>为可附加成员存储提供了一种实现技术。 <xref:System.Xaml.IAttachedPropertyStore>XAML 编写器用于发现存储实现，并且应在访问器`target`的类型上实现。 静态<xref:System.Xaml.AttachablePropertyServices>API 在访问器的正文中使用，并通过 其<xref:System.Xaml.AttachableMemberIdentifier>引用可连接成员。

## <a name="xaml-related-clr-attributes"></a>与 XAML 相关的 CLR 属性

正确分配类型、成员和程序集对于向 .NET XAML 服务报告 XAML 类型系统信息非常重要。 如果适用以下任一情况，报告 XAML 类型系统信息是相关的：

- 您希望类型与直接基于 .NET XAML 服务 XAML 服务读取器和 XAML 写入器的 XAML 系统一起使用。
- 您定义或使用基于这些 XAML 读取器和 XAML 编写器的 XAML 利用框架。

有关与自定义类型的 XAML 支持相关的每个 XAML 相关属性的列表，请参阅[自定义类型和库的 XAML 相关 CLR 属性](clr-attributes-with-custom-types-and-libraries.md)。

## <a name="usage"></a>使用情况

自定义类型的使用要求标记作者必须映射包含自定义类型的程序集和 CLR 命名空间的前缀。 本主题中未记录此过程。

## <a name="access-level"></a>访问级别

XAML 提供了一种加载和实例化具有`internal`访问级别的类型的方法。 提供此功能，以便用户代码可以定义自己的类型，然后从也是同一用户代码作用域的标记实例化这些类。

WPF 的一个示例是，每当用户代码<xref:System.Windows.Controls.UserControl>定义 旨在重构 UI 行为的方法时，而不是作为任何可能的扩展机制的一部分，这些扩展机制可能通过声明具有`public`访问级别的支持类来暗示。 如果支持<xref:System.Windows.Controls.UserControl>代码编译到引用`internal`为 XAML 类型的同一程序集中，则可以通过访问权限声明此类 。

对于在完全信任下加载 XAML 并使用<xref:System.Xaml.XamlObjectWriter>的应用程序，始终启用具有`internal`访问级别的加载类。

对于在部分信任下加载 XAML 的应用程序，可以使用<xref:System.Xaml.Permissions.XamlAccessLevel>API 来控制访问级别特征。 此外，延迟机制（如 WPF 模板系统）必须能够传播任何访问级别权限，并将其保留为最终的运行时评估;这通过传递信息在<xref:System.Xaml.Permissions.XamlAccessLevel>内部处理。

### <a name="wpf-implementation"></a>WPF 实施

WPF XAML 使用部分信任访问模型，其中如果 BAML 在部分信任下加载，则<xref:System.Xaml.Permissions.XamlAccessLevel.AssemblyAccessTo%2A>访问仅限于作为 BAML 源的程序集。 对于延迟，WPF 用作<xref:System.Xaml.IXamlObjectWriterFactory.GetParentSettings%2A?displayProperty=nameWithType>传递访问级别信息的机制。

在 WPF XAML 术语中，*内部类型*是由同一程序集定义的类型，该程序集还包括引用 XAML。 此类类型可以通过 XAML 命名空间映射，该命名空间有意省略映射的程序集部分，`xmlns:local="clr-namespace:WPFApplication1"`例如 。 如果 BAML 引用内部类型，并且该`internal`类型具有访问级别，这将`GeneratedInternalTypeHelper`为程序集生成一个类。 如果要避免`GeneratedInternalTypeHelper`，则必须使用`public`访问级别，或者必须将相关类考虑到单独的程序集中，并使该程序集与程序集相关。

## <a name="see-also"></a>请参阅

- [自定义类型和库的 XAML 相关 CLR 特性](clr-attributes-with-custom-types-and-libraries.md)
- [XAML 服务](../../../api/index.md)
