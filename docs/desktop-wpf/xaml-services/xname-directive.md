---
title: x:Name 指令
ms.date: 03/30/2017
f1_keywords:
- x:Name
- xName
- Name
helpviewer_keywords:
- x:Name attribute [XAML Services]
- XAML [XAML Services], x:Name attribute
- Name attribute in XAML [XAML Services]
ms.assetid: b7e61222-e8cf-48d2-acd0-6df3b7685d48
ms.openlocfilehash: 9f812a49a3217a563be1bd7f1d999b641c28463d
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432712"
---
# <a name="xname-directive"></a>x:Name 指令

唯一标识 XAML 定义的元素在 XAML 命名范围中。 当框架提供 API 或实现在运行时访问 XAML 创建的对象图的行为时，XAML 命名范围及其唯一性模型可以应用于实例化对象。

## <a name="xaml-attribute-usage"></a>XAML 属性用法

```xaml
<object x:Name="XAMLNameValue".../>
```

## <a name="xaml-values"></a>XAML 值

|||
|-|-|
|`XAMLNameValue`|符合[XamlName 语法](xamlname-grammar.md)限制的字符串。|

## <a name="remarks"></a>备注

应用于`x:Name`框架的备份编程模型后，名称等效于保存对象引用的变量或构造函数返回的实例。

`x:Name`指令用法的值必须在 XAML 名称范围内是唯一的。 默认情况下，当 .NET XAML 服务 API 使用时，主 XAML 命名范围在单个 XAML 生产的 XAML 根元素中定义，并包含该 XAML 生产中包含的元素。 框架可以定义单个 XAML 生产中可能发生的其他离散 XAML 命名范围，以解决特定方案。 例如，在 WPF 中，新的 XAML 命名范围由在 XAML 生产上定义的任何模板定义和创建。 有关 XAML 名称范围的详细信息（为 WPF 编写，但与许多 XAML 名称范围概念相关），请参阅[WPF XAML 名称范围](../../framework/wpf/advanced/wpf-xaml-namescopes.md)。

通常，`x:Name`不应应用于也使用`x:Key`的情况。 由特定现有框架实现的 XAML 在 和`x:Key``x:Name`之间引入了替换概念，但这不是建议的做法。 .NET XAML 服务在处理名称/密钥信息（如 或<xref:System.Windows.Markup.INameScope><xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>） 时不支持此类替换概念。

允许`x:Name`性规则以及名称唯一性实施可能由特定的实现框架定义。 但是，要与 .NET XAML 服务一起使用，XAML 命名范围的唯一性的框架定义应与本文档中<xref:System.Windows.Markup.INameScope>的信息定义一致，并且应该使用有关信息应用位置的相同规则。 例如，[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)]实现将各种标记元素划分为单独的<xref:System.Windows.NameScope>范围，例如资源字典、由页面级 XAML 创建的逻辑树、模板和其他延迟内容，然后在每个 XAML 命名范围内强制实施 XAML 名称唯一性。

对于使用 .NET XAML 服务 XAML 对象编写器的自定义类型`x:Name`，可以建立或更改映射到类型的属性。 通过引用要使用类型定义代码<xref:System.Windows.Markup.RuntimeNamePropertyAttribute>中映射的属性的名称来定义此行为。  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>是类型级属性。

Using.NET XAML 服务，可以通过实现<xref:System.Windows.Markup.INameScope>接口以框架中立的方式定义 XAML 命名范围支持的备份逻辑。

## <a name="wpf-usage-notes"></a>WPF 用法说明

在使用 XAML、[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]部分类和代码后面的应用程序的标准生成配置下，指定`x:Name`将成为在标记编译生成任务处理时[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]在基础代码中创建的字段的名称，并且该字段包含对对象的引用。 默认情况下，创建的字段是内部字段。 您可以通过指定[x：字段修改器属性](xfieldmodifier-directive.md)来更改字段访问。 在 WPF 和 Silverlight 中，序列是标记编译定义和命名部分类中的字段，但该值最初为空。 然后，从类构造函数`InitializeComponent`中调用名为 生成的方法。 `InitializeComponent`由`FindName`使用部分类 XAML 定义部分中存在的每个`x:Name`值作为输入字符串的调用组成。 然后，返回值分配给类似命名的字段引用，以使用从 XAML 分析创建的对象填充字段值。 执行 后`InitializeComponent`，可以直接使用`x:Name`/ 字段名称引用运行时对象图，而不必在需要引用 XAML`FindName`定义的对象时显式调用。

对于使用`Page`Microsoft Visual Basic 目标并包含包含生成操作的 XAML 文件的 WPF 应用程序，在编译过程中将`WithEvents`关键字添加到 具有`x:Name`的所有元素，以支持`Handles`事件处理程序委托的语法。 此属性始终是公共的。 有关详细信息，请参阅 [Visual Basic 和 WPF 事件处理](../../framework/wpf/advanced/visual-basic-and-wpf-event-handling.md)。

`x:Name`WPF XAML 处理器在加载时使用该名称注册到 XAML 命名范围中，即使对于页面未通过生成操作进行标记编译的情况也是如此（例如，资源字典的松散 XAML）。 此行为的一个原因是绑定可能需要`x:Name`<xref:System.Windows.Data.Binding.ElementName%2A>。 有关详细信息，请参阅[数据绑定概述](../data/data-binding-overview.md)。

如前所述，（`x:Name`或`Name`）不应应用于也使用`x:Key`的情况。 具有特殊[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.ResourceDictionary>行为，将自身定义为 XAML 命名范围，但返回 API 的<xref:System.Windows.Markup.INameScope>未实现或 null 值，作为强制执行此行为的一种方式。 如果 WPF XAML 解析`Name`器`x:Name`遇到或在 XAML<xref:System.Windows.ResourceDictionary>定义中，则名称不会添加到任何 XAML 名称范围。 尝试从任何 XAML 名称范围查找该名称和方法`FindName`将不会返回有效结果。

### <a name="xname-and-name"></a>x：名称和名称

许多 WPF 应用程序方案`x:Name`可以避免对属性的任何使用，因为在默认`Name`的 XAML 命名空间中指定的依赖项属性适用于几个重要基类，如<xref:System.Windows.FrameworkElement>和<xref:System.Windows.FrameworkContentElement>满足此相同的用途。 仍有一些常见的 XAML 和 WPF 方案，其中代码访问框架级别`Name`上没有属性的元素非常重要。 例如，某些动画和情节提要支持类不支持`Name`属性，但它们通常需要在代码中引用才能控制动画。 如果以后打算`x:Name`从代码中引用它们，则应在时间线上指定为属性，并在 XAML 中创建的转换中指定属性。

如果在<xref:System.Windows.FrameworkElement.Name%2A>类上作为属性可用，<xref:System.Windows.FrameworkElement.Name%2A>`x:Name`并且可以作为属性互换使用，但如果在同一元素上指定两者，则会产生解析异常。 如果编译了 XAML，则异常将在标记编译上发生，否则将在加载时发生。

<xref:System.Windows.FrameworkElement.Name%2A>可以使用 XAML 属性语法和 在 代码中使用<xref:System.Windows.DependencyObject.SetValue%2A>。但是请注意，在已<xref:System.Windows.FrameworkElement.Name%2A>加载 XAML 的大多数情况下，在代码中设置属性不会在 XAML 命名范围内创建具有代表性的字段引用。 不要尝试在代码中设置<xref:System.Windows.FrameworkElement.Name%2A>，而是根据相应的<xref:System.Windows.NameScope>名称范围使用代码中的方法。

<xref:System.Windows.FrameworkElement.Name%2A>也可以使用包含内部文本的属性元素语法进行设置，但这种情况并不常见。 相反，`x:Name`不能在 XAML 属性元素语法中设置，也不能在<xref:System.Windows.DependencyObject.SetValue%2A>代码中使用 。它只能使用对象的属性语法进行设置，因为它是指令。

## <a name="silverlight-usage-notes"></a>银光使用说明

`x:Name`银光单独记录。 有关详细信息，请参阅[XAML 命名空间 （x：）语言功能（银光）](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).

## <a name="see-also"></a>请参阅

- <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>
- <xref:System.Windows.FrameworkContentElement.Name%2A?displayProperty=nameWithType>
- [WPF 中的树](../../framework/wpf/advanced/trees-in-wpf.md)
