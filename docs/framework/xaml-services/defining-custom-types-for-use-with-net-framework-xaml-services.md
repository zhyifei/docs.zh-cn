---
title: 定义与 .NET Framework XAML 服务一起使用的自定义类型
ms.date: 03/30/2017
helpviewer_keywords:
- defining custom types [XAML Services]
ms.assetid: c2667cbd-2f46-4a7f-9dfc-53696e35e8e4
ms.openlocfilehash: 7437add6795c1bb7f8a59807ebfc51dc2d0f987f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73972025"
---
# <a name="defining-custom-types-for-use-with-net-framework-xaml-services"></a>定义与 .NET Framework XAML 服务一起使用的自定义类型
在定义作为业务对象的自定义类型或不依赖于特定框架的类型时，可以遵循 XAML 的某些最佳实践。 如果遵循这些做法，.NET Framework XAML 服务及其 XAML 读取器和 XAML 编写器可以发现类型的 XAML 特征，并使用 XAML 类型系统在 XAML 节点流中为其指定适当的表示形式。 本主题介绍类型定义、成员定义和类型或成员的 CLR 特性的最佳实践。  
  
## <a name="constructor-patterns-and-type-definitions-for-xaml"></a>XAML 的构造函数模式和类型定义  
 若要在 XAML 中实例化为对象元素，自定义类必须满足以下要求：  
  
- 自定义类必须是公共的，并且必须公开无参数的公共构造函数。 （有关结构注释，请参阅下节内容。）  
  
- 自定义类不得为嵌套类。 完整名称路径中的多余 "点" 使类命名空间除法不明确，并与附加属性等其他 XAML 功能发生冲突。  
  
 如果对象可以实例化为对象元素，则创建的对象可以填充任何将对象作为其基础类型的属性的属性元素形式。  
  
 如果启用值转换器，则仍可为不满足这些条件的类型提供对象值。 有关详细信息，请参阅[XAML 的类型转换器和标记扩展](type-converters-and-markup-extensions-for-xaml.md)。  
  
### <a name="structures"></a>结构  
 结构始终能够按 CLR 定义在 XAML 中构造。 这是因为 CLR 编译器会为结构隐式创建一个无参数的构造函数。 此构造函数将所有属性值初始化为其默认值。  
  
 在某些情况下，结构的默认构造行为并不理想。 这可能是因为结构旨在将值和函数作为联合填充。 作为联合，包含的值可能具有互斥的解释，因此，其所有属性都是可设置的。 <xref:System.Windows.GridLength>，WPF 词汇中的此类结构的示例。 此类结构应实现类型转换器，以便可以使用创建结构值的不同解释或模式的字符串约定来用属性形式表示值。 结构还应通过非参数构造函数公开代码构造的类似行为。  
  
### <a name="interfaces"></a>接口  
 接口可用作成员的基础类型。 XAML 类型系统检查可赋值列表，并期望作为值提供的对象可以分配给接口。 只要相关的可赋值类型支持 XAML 构造要求，就必须将接口呈现为 XAML 类型。  
  
### <a name="factory-methods"></a>工厂方法  
 工厂方法为 XAML 2009 功能。 它们修改了对象必须具有无参数构造函数的 XAML 原则。 工厂方法未在本主题中介绍。 请参阅[X:FactoryMethod 指令](x-factorymethod-directive.md)。  
  
## <a name="enumerations"></a>枚举  
 枚举具有 XAML 本机类型转换行为。 XAML 中指定的枚举常量名称根据基础枚举类型进行解析，并将枚举值返回到 XAML 对象编写器。  
  
 XAML 支持 <xref:System.FlagsAttribute> 应用了的枚举的标志样式用法。 有关详细信息，请参阅[XAML 语法详述](../wpf/advanced/xaml-syntax-in-detail.md)。 （[Xaml 语法详细](../wpf/advanced/xaml-syntax-in-detail.md)信息是针对 WPF 受众编写的，但该主题中的大部分信息与不特定于特定实现框架的 XAML 相关。）  
  
## <a name="member-definitions"></a>成员定义  
 类型可以为 XAML 用法定义成员。 定义可 XAML 使用的成员的类型是可能的，即使该特定类型不能使用 XAML。 这是可能的，因为 CLR 继承。 只要继承成员的某个类型支持 XAML 用法作为类型，且该成员支持其基础类型的 XAML 用法或具有可用的本机 XAML 语法，则该成员是 XAML 可用的。  
  
### <a name="properties"></a>属性  
 如果你使用典型的 CLR `get` 和 `set` 访问器模式和语言适当的 keywording 将属性定义为公共 CLR 属性，则 XAML 类型系统可将该属性报告为具有为 <xref:System.Xaml.XamlMember> 属性（如 <xref:System.Xaml.XamlMember.IsReadPublic%2A> 和 <xref:System.Xaml.XamlMember.IsWritePublic%2A>）提供的适当信息的成员。  
  
 特定属性可通过应用 <xref:System.ComponentModel.TypeConverterAttribute>来启用文本语法。 有关详细信息，请参阅[XAML 的类型转换器和标记扩展](type-converters-and-markup-extensions-for-xaml.md)。  
  
 在缺少文本语法或本机 XAML 转换并且没有进一步的间接寻址（如标记扩展用法）的情况下，属性的类型（在 XAML 类型系统中为<xref:System.Xaml.XamlMember.TargetType%2A>）必须能够通过将目标类型视为 CLR 类型，将实例返回到 XAML 对象编写器。  
  
 如果使用 XAML 2009，则在未满足前面的注意事项时，可以使用[X:Reference 标记扩展](x-reference-markup-extension.md)来提供值;但是，这比类型定义问题更是使用问题。  
  
### <a name="events"></a>事件  
 如果将事件定义为公共 CLR 事件，则 XAML 类型系统可将事件报告为具有 `true`<xref:System.Xaml.XamlMember.IsEvent%2A> 的成员。 线路事件处理程序不在 .NET Framework XAML 服务功能的范围内;这留给了特定的框架和实现。  
  
### <a name="methods"></a>方法  
 方法的内联代码不是默认的 XAML 功能。 在大多数情况下，你不会直接从 XAML 引用方法成员，XAML 中的方法的角色只是为特定 XAML 模式提供支持。 [X:FactoryMethod 指令](x-factorymethod-directive.md)是一个异常。  
  
### <a name="fields"></a>字段  
 CLR 设计准则不鼓励非静态字段。 对于静态字段，只能通过[X:Static 标记扩展](x-static-markup-extension.md)访问静态字段值;在这种情况下，你不会在 CLR 定义中执行任何特殊操作来公开[x:Static](x-static-markup-extension.md)使用的字段。  
  
## <a name="attachable-members"></a>可附加成员  
 可附加成员通过定义类型的访问器方法模式向 XAML 公开。 定义类型本身无需作为对象使用 XAML。 事实上，一种常见的模式是声明一个服务类，该服务类的角色将拥有该可附加成员，并实现相关的行为，但不会提供任何其他函数（如 UI 表示形式）。 对于以下各节，placeholder*属性*名称表示可附加成员的名称。 该名称在[XamlName 语法](xamlname-grammar.md)中必须有效。  
  
 请注意这些模式与类型的其他方法之间的名称冲突。 如果存在与某个模式匹配的成员，则它可以被 XAML 处理器解释为可附加成员使用通道，即使这不是你的意图。  
  
#### <a name="the-getpropertyname-accessor"></a>GetPropertyName 访问器  
 `Get` PropertyName 访问器的签名必须是：  
  
 `public static object Get` PropertyName `(object` `target` `)`  
  
- `target` 对象在实现中可以指定为更具体的类型。 可以使用它来确定可附加成员的使用范围;预期范围外的使用情况将引发无效的强制转换异常，然后由 XAML 分析错误引发。 参数名称 `target` 不是必需的，但在大多数实现中按约定命名为 `target`。  
  
- 返回值在实现中可以指定为更具体的类型。  
  
 若要支持可附加成员的属性用法的 <xref:System.ComponentModel.TypeConverter> 启用文本语法，请将 <xref:System.ComponentModel.TypeConverterAttribute> 应用到 `Get`*PropertyName*访问器。 应用于 `get` 而不是 `set` 似乎 nonintuitive;但是，此约定可以支持可序列化的只读可附加成员的概念，这在设计器方案中非常有用。  
  
#### <a name="the-setpropertyname-accessor"></a>SetPropertyName 访问器  
 Set*PropertyName*访问器的签名必须是：  
  
 `public static void Set` PropertyName `(object`  `target` `, object`  `value` `)`  
  
- 在实现中，可以将 `target` 对象指定为更具体的类型，与上一节中所述的逻辑和结果相同。  
  
- `value` 对象在实现中可以指定为更具体的类型。  
  
 请记住，此方法的值是来自 XAML 使用情况的输入，通常采用属性格式。 从属性窗体中必须存在对文本语法的值转换器支持，并在 `Get`*PropertyName*访问器上进行属性。  
  
### <a name="attachable-member-stores"></a>可附加成员存储  
 通常，访问器方法不能提供将可附加成员值置于对象图中的方法，也不能从对象图中检索值并正确地对其进行序列化。 为了提供此功能，上一个访问器签名中的 `target` 对象必须能够存储值。 存储机制应该与可附加成员原则一致，成员可附加到可附加成员不在成员列表中的目标。 .NET Framework XAML 服务通过 Api <xref:System.Xaml.IAttachedPropertyStore> 和 <xref:System.Xaml.AttachablePropertyServices>为可附加成员存储提供实现方法。 <xref:System.Xaml.IAttachedPropertyStore> 由 XAML 编写器用于发现存储实现，并且应在作为访问器 `target` 的类型上实现。 静态 <xref:System.Xaml.AttachablePropertyServices> Api 在访问器的主体中使用，并通过其 <xref:System.Xaml.AttachableMemberIdentifier>引用可附加成员。  
  
## <a name="xaml-related-clr-attributes"></a>XAML 相关 CLR 特性  
 正确地对类型、成员和程序集进行排序非常重要，因为要将 XAML 类型系统信息报告给 .NET Framework XAML 服务。 如果你希望你的类型与直接基于 .NET Framework XAML 服务 XAML 读取器和 XAML 编写器的 XAML 系统一起使用，或者你定义或使用基于 xaml 读取器和 XAML 编写器的 XAML 利用框架，则这一点很有用。  
  
 有关与自定义类型的 XAML 支持相关的每个与 XAML 相关的属性的列表，请参阅[自定义类型和库的 Xaml 相关 CLR 特性](xaml-related-clr-attributes-for-custom-types-and-libraries.md)。  
  
## <a name="usage"></a>用法  
 使用自定义类型需要标记作者必须为包含自定义类型的程序集和 CLR 命名空间映射前缀。 本主题不介绍此过程。  
  
## <a name="access-level"></a>访问级别  
 XAML 提供了一个方法，用于加载和实例化具有 `internal` 访问级别的类型。 提供此功能的目的是使用户代码可以定义自己的类型，然后从同时也属于相同用户代码范围的标记中实例化这些类。  
  
 每当用户代码定义一个旨在作为重构 UI 行为的方法的 <xref:System.Windows.Controls.UserControl> 时，WPF 的示例就是这样的，而不是通过使用 `public` 访问级别声明支持类而隐含的任何可能的扩展机制的一部分。 如果将支持代码编译到将其作为 XAML 类型引用的同一程序集中，则可以使用 `internal` 访问来声明此类 <xref:System.Windows.Controls.UserControl>。  
  
 对于在完全信任下加载 XAML 并使用 <xref:System.Xaml.XamlObjectWriter>的应用程序，将始终启用使用 `internal` 访问级别加载类。  
  
 对于在部分信任环境下加载 XAML 的应用程序，可以通过使用 <xref:System.Xaml.Permissions.XamlAccessLevel> API 来控制访问级别特性。 此外，延迟机制（如 WPF 模板系统）必须能够传播任何访问级别权限，并在最终运行时评估中保留这些权限;这是通过传递 <xref:System.Xaml.Permissions.XamlAccessLevel> 信息在内部处理的。  
  
### <a name="wpf-implementation"></a>WPF 实现  
 WPF XAML 使用部分信任访问模型，其中，如果在部分信任环境下加载 BAML，则访问权限将限制为作为 BAML 源的程序集的 <xref:System.Xaml.Permissions.XamlAccessLevel.AssemblyAccessTo%2A>。 对于延迟，WPF 使用 <xref:System.Xaml.IXamlObjectWriterFactory.GetParentSettings%2A?displayProperty=nameWithType> 作为传递访问级别信息的机制。  
  
 在 WPF XAML 术语中，*内部类型*是由同一程序集定义的类型，该程序集也包括引用 XAML。 可以通过 XAML 命名空间来映射此类类型，该命名空间有意省略了映射的 assembly 部分，例如 `xmlns:local="clr-namespace:WPFApplication1"`。  如果 BAML 引用内部类型，并且该类型具有 `internal` 访问级别，则会为该程序集生成一个 `GeneratedInternalTypeHelper` 类。 如果要避免 `GeneratedInternalTypeHelper`，则必须使用 `public` 访问级别，或者必须将相关类因式分解为单独的程序集，并使该程序集依赖。  
  
## <a name="see-also"></a>请参阅

- [自定义类型和库的 XAML 相关 CLR 特性](xaml-related-clr-attributes-for-custom-types-and-libraries.md)
- [XAML 服务](index.md)
