---
title: "定义与 .NET Framework XAML 服务一起使用的自定义类型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: defining custom types [XAML Services]
ms.assetid: c2667cbd-2f46-4a7f-9dfc-53696e35e8e4
caps.latest.revision: "11"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 0b35c35be7351fdf45157153ce6ca55fc763c3ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="defining-custom-types-for-use-with-net-framework-xaml-services"></a>定义与 .NET Framework XAML 服务一起使用的自定义类型
当你定义了业务对象的自定义类型或者不在特定框架具有依赖关系的类型时，有一些你可以遵循 xaml 某些最佳实践。 如果您遵循这些做法，.NET Framework XAML 服务和其 XAML 读取器和 XAML 编写器可以发现你的类型的 XAML 特征，并为其提供适当的表示形式，在 XAML 节点流中使用的 XAML 类型系统。 本主题介绍类型定义，成员定义和 CLR 特性化的类型或成员的最佳做法。  
  
## <a name="constructor-patterns-and-type-definitions-for-xaml"></a>构造函数模式和 XAML 的类型定义  
 要作为对象元素在 XAML 中实例化，自定义类必须满足以下要求：  
  
-   自定义类必须是公共的并且必须公开默认 （无参数） 公共构造函数。 （有关结构注释，请参阅下节内容。）  
  
-   自定义的类必须是嵌套的类。 额外的完整名称路径中的"点"使类命名空间除法不明确的并且会干扰其他 XAML 功能，例如附加属性。  
  
 作为对象元素，可实例化一个对象，如果所创建的对象可以填充属性元素形式将该对象作为其基础类型的任何属性。  
  
 如果启用了值转换器，你仍可以为不满足这些条件的类型中提供对象值。 有关详细信息，请参阅[类型转换器和 XAML 的标记扩展](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md)。  
  
### <a name="structures"></a>结构  
 结构始终是能够在 XAML 中，通过 CLR 定义构造的。 这是因为 CLR 编译器隐式创建一个结构的默认构造函数。 此构造函数初始化为其默认值的所有属性值。  
  
 在某些情况下，一个结构的默认构造行为是不需要的。 这可能是因为结构旨在在概念上作为联合填充值和函数。 作为一个联合，包含的值可能有相互排斥的解释，并因此，其属性都是不可设置。 这种结构中的 WPF 词汇的一个示例是<xref:System.Windows.GridLength>。 此类结构应实现的类型转换器，以便值可以在属性表单中，表示通过创建不同的解释或模式的结构值的字符串约定。 结构还应通过非默认构造函数对代码构造公开类似的行为。  
  
### <a name="interfaces"></a>接口  
 接口可以用作基础类型的成员。 XAML 类型系统检查可赋值的列表，并且期望作为值提供的对象可以分配给的接口。 没有如何接口必须表示为 XAML 类型，只要相关可赋值的类型支持的 XAML 构造要求的概念。  
  
### <a name="factory-methods"></a>工厂方法  
 工厂方法是 XAML 2009 功能。 他们修改对象必须具有默认构造函数的 XAML 原则。 在本主题不介绍工厂方法。 请参阅[X:factorymethod 指令](../../../docs/framework/xaml-services/x-factorymethod-directive.md)。  
  
## <a name="enumerations"></a>枚举  
 枚举具有 XAML 本机类型转换行为。 在 XAML 中指定的枚举常量名基础的枚举类型中，针对解析，并返回到 XAML 对象编写器的枚举值。  
  
 XAML 支持使用枚举标志样式用法<xref:System.FlagsAttribute>应用。 有关详细信息，请参阅[在详细信息的 XAML 语法](../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)。 ([在详细信息的 XAML 语法](../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)专为 WPF 受众，但并不特定于特定实现框架的 xaml 与大部分该主题中的信息。)  
  
## <a name="member-definitions"></a>成员定义  
 类型可以定义用于 XAML 的成员。 它是可能的类型的定义是 XAML 可用，即使该特定的类型不是 XAML 可用的成员。 这是因为 CLR 继承。 只要某种类型的继承成员支持 XAML 用法作为类型，并且该成员为其基础类型支持 XAML 用法，或具有可用的本机 XAML 语法，则该成员是 XAML 可用。  
  
### <a name="properties"></a>属性  
 如果定义属性定义为使用典型的 CLR 的公共 CLR 属性`get`和`set`访问器模式和语言应建立关键词，XAML 类型系统可以提供相应的信息的成员作为属性进行报告<xref:System.Xaml.XamlMember>属性，如<xref:System.Xaml.XamlMember.IsReadPublic%2A>和<xref:System.Xaml.XamlMember.IsWritePublic%2A>。  
  
 特定属性可以通过应用启用文本语法<xref:System.ComponentModel.TypeConverterAttribute>。 有关详细信息，请参阅[类型转换器和 XAML 的标记扩展](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md)。  
  
 在没有文本语法或本机 XAML 转换和没有进一步间接寻址，如标记扩展用法，属性的类型 (<xref:System.Xaml.XamlMember.TargetType%2A>在 XAML 类型系统) 必须能够通过将 t 到 XAML 对象编写器返回的实例arget 作为 CLR 类型的类型。  
  
 如果使用 XAML 2009 [X:reference 标记扩展](../../../docs/framework/xaml-services/x-reference-markup-extension.md)可以用于提供值，如果不满足前面的注意事项; 但是，这是多个类型定义问题比使用情况问题。  
  
### <a name="events"></a>事件  
 如果为公共的 CLR 事件定义事件，XAML 类型系统可以将事件报告为成员，同时<xref:System.Xaml.XamlMember.IsEvent%2A>作为`true`。 连接事件处理程序不是.NET Framework XAML 服务功能; 的作用域内此功能由特定框架和实现。  
  
### <a name="methods"></a>方法  
 方法的内联代码不是默认的 XAML 功能。 在大多数情况下你不要直接引用方法成员从 XAML，并在 XAML 中的方法的角色是仅提供了特定 XAML 模式提供支持。 [X:factorymethod 指令](../../../docs/framework/xaml-services/x-factorymethod-directive.md)出现异常。  
  
### <a name="fields"></a>字段  
 CLR 设计准则禁止非静态字段。 对于静态字段，你可以访问静态字段值只能通过[X:static 标记扩展](../../../docs/framework/xaml-services/x-static-markup-extension.md); 在这种情况下你未执行任何特殊操作中要公开的字段的 CLR 定义[X:static](../../../docs/framework/xaml-services/x-static-markup-extension.md)用法。  
  
## <a name="attachable-members"></a>可附加成员  
 可附加的成员上定义的类型访问器方法模式通过公开给 XAML。 定义类型本身不必要 XAML 能够用作对象。 事实上，一种常见模式是以声明其角色是一个服务类拥有的可附加成员并实现相关的行为，但不提供如 UI 表示方式的任何其他功能。 有关以下各节，将占位符*PropertyName*表示可附加成员的名称。 该名称必须是有效中[XamlName 语法](../../../docs/framework/xaml-services/xamlname-grammar.md)。  
  
 请务必谨慎的这些模式和类型的其他方法之间的名称冲突。 如果存在匹配的模式之一的成员，它可以被视为可附加成员用法路径由 XAML 处理器即使这并不是您的意图。  
  
#### <a name="the-getpropertyname-accessor"></a>GetPropertyName 访问器  
 `Get` PropertyName 访问器的签名必须是：  
  
 `public static object Get` PropertyName `(object` `target` `)`  
  
-   `target` 对象在实现中可以指定为更具体的类型。 你可以使用此作用域可附加成员; 的使用情况你预期使用范围之外的用法将引发无效强制转换异常，然后会显示 XAML 分析错误。 参数名称`target`不是一种要求，但名为`target`受到约定的大多数实施方案。  
  
-   返回值在实现中可以指定为更具体的类型。  
  
 若要支持<xref:System.ComponentModel.TypeConverter>对于特性用法的可附加成员的已启用的文本语法应用<xref:System.ComponentModel.TypeConverterAttribute>到`Get` *PropertyName*访问器。 将应用于`get`而不是`set`可能看起来直观; 但是，此约定可支持这一概念的只读可附加成员进行序列化，这是设计器的方案中十分有用。  
  
#### <a name="the-setpropertyname-accessor"></a>SetPropertyName 访问器  
 集的签名*PropertyName*访问器必须是：  
  
 `public static void Set` PropertyName `(object`  `target` `, object`  `value` `)`  
  
-   `target`上一节中所述，可以在实现中，具有相同的逻辑和后果更具体的类型为指定对象。  
  
-   `value` 对象在实现中可以指定为更具体的类型。  
  
 请记住，此方法的值是来自 XAML 用法中，通常采用特性形式的输入。 在特性形式必须有值转换器支持文本语法，并且特性上`Get` *PropertyName*访问器。  
  
### <a name="attachable-member-stores"></a>可附加成员存储  
 访问器方法通常是不足够，以提供一种可附加成员值放在对象图，或检索值超出对象图和序列化这些正确。 若要提供此功能，`target`以前的访问器签名中的对象必须能够存储值。 存储机制应与成员是可附加到目标的可附加成员不在成员列表中的可附加成员原则一致。 .NET framework XAML 服务提供实现的一种技术，可附加成员存储通过 Api<xref:System.Xaml.IAttachedPropertyStore>和<xref:System.Xaml.AttachablePropertyServices>。 <xref:System.Xaml.IAttachedPropertyStore>XAML 编写器用于发现的存储实现，并应在为的类型中实现`target`访问器。 静态<xref:System.Xaml.AttachablePropertyServices>Api 访问器中，主体中使用和的可附加成员是指其<xref:System.Xaml.AttachableMemberIdentifier>。  
  
## <a name="xaml-related-clr-attributes"></a>与 XAML 相关 CLR 特性  
 正确的归类型、 成员和程序集是重要到报表的.NET Framework XAML 服务 XAML 类型系统信息的顺序。 如果希望你的类型用于直接基于.NET Framework XAML 服务 XAML 读取器和 XAML 编写的 XAML 系统，或如果你定义或使用 XAML 利用框架基于这些 XAML 读取器和 XAML 编写器，这是相关。  
  
 有关相关的自定义类型的 XAML 支持的每个与 XAML 相关的属性的列表，请参阅[的自定义类型和库的 XAML-Related CLR 特性](../../../docs/framework/xaml-services/xaml-related-clr-attributes-for-custom-types-and-libraries.md)。  
  
## <a name="usage"></a>用法  
 使用自定义类型需要标记作者必须映射包含自定义类型的程序集和 CLR 命名空间的前缀。 本主题中不记录此过程。  
  
## <a name="access-level"></a>访问级别  
 XAML 提供一种方法来加载和实例化类型具有`internal`访问级别。 提供此功能，以便用户代码可以定义自己的类型，然后实例化也是相同的用户代码作用域的一部分的标记从这些类。  
  
 WPF 的一个示例是只要用户代码定义<xref:System.Windows.Controls.UserControl>打算作为一种方法重构 UI 行为，但不是可能会隐式声明的支持类与任何可能的扩展机制的一部分`public`访问级别。 此类<xref:System.Windows.Controls.UserControl>可使用声明`internal`访问如果后备代码会编译成从中它引用了作为 XAML 类型的相同程序集。  
  
 为应用程序在完全信任下加载 XAML 并使用<xref:System.Xaml.XamlObjectWriter>，类加载`internal`访问级别始终处于启用状态。  
  
 对于在部分信任下加载 XAML 的应用，你可以通过使用控制的访问级别特征<xref:System.Xaml.Permissions.XamlAccessLevel>API。 此外，必须能够传播任何访问级别权限，并保留它们的最终的运行的时评估; 进行延期机制 （如 WPF 模板系统）这通过传递在内部处理<xref:System.Xaml.Permissions.XamlAccessLevel>信息。  
  
### <a name="wpf-implementation"></a>WPF 实现  
 WPF XAML 使用部分信任访问模型，其中如果 BAML 加载在部分信任下，访问仅限于<xref:System.Xaml.Permissions.XamlAccessLevel.AssemblyAccessTo%2A>的程序集的 BAML 源。 对于延迟，WPF 使用<xref:System.Xaml.IXamlObjectWriterFactory.GetParentSettings%2A?displayProperty=nameWithType>作为传递访问级别信息的机制。  
  
 在 WPF XAML 术语中，*内部类型*是由同一程序集，还包括引用的 XAML 定义的类型。 这样的类型可以映射通过 XAML 命名空间的有意省略了程序集 = 一部分的映射，例如， `xmlns:local="clr-namespace:WPFApplication1"`。  如果 BAML 引用的内部类型，并且该类型具有`internal`访问级别时，这将生成`GeneratedInternalTypeHelper`程序集的类。 如果你想要避免`GeneratedInternalTypeHelper`，则必须使用`public`访问级别时，或必须相关类分解为单独的程序集，并将该程序集依赖。  
  
## <a name="see-also"></a>另请参阅  
 [自定义类型和库的 XAML 相关 CLR 特性](../../../docs/framework/xaml-services/xaml-related-clr-attributes-for-custom-types-and-libraries.md)  
 [XAML 服务](../../../docs/framework/xaml-services/index.md)
