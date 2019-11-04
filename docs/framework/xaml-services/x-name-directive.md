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
ms.openlocfilehash: 8a790ea964ffe399136a82ea298e1c7600f48366
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459964"
---
# <a name="xname-directive"></a>x:Name 指令
在 XAML 名称范围中唯一标识 XAML 定义的元素。 当框架提供 Api 或实现在运行时访问 XAML 创建的对象图的行为时，可以将 XAML 名称范围及其唯一性模型应用于实例化的对象。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xaml  
<object x:Name="XAMLNameValue".../>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`XAMLNameValue`|符合[XamlName 语法](xamlname-grammar.md)限制的字符串。|  
  
## <a name="remarks"></a>备注  
 将 `x:Name` 应用于框架的后备编程模型后，该名称等效于包含构造函数返回的对象引用或实例的变量。  
  
 `x:Name` 指令用法的值在 XAML 名称范围内必须是唯一的。 默认情况下，当由 .NET Framework XAML 服务 API 使用时，主 XAML 名称范围将在单个 XAML 生产的 XAML 根元素中定义，并且包含该 XAML 生产中包含的元素。 可能出现在单个 XAML 生产内的其他离散 XAML 名称范围可以由框架定义，以解决特定方案。 例如，在 WPF 中，新的 XAML 名称范围由也在该 XAML 生产环境中定义的任何模板来定义和创建。 有关 XAML 名称范围（针对 WPF 编写但与许多 XAML 名称范围概念相关的详细信息），请参阅[WPF XAML 名称范围](../wpf/advanced/wpf-xaml-namescopes.md)。  
  
 通常，不应在也使用 `x:Key`的情况下应用 `x:Name`。 特定现有框架的 XAML 实现在 `x:Key` 和 `x:Name`之间引入了替代概念，但这不是建议的做法。 在处理名称/键信息（如 <xref:System.Windows.Markup.INameScope> 或 <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>）时，.NET Framework XAML 服务不支持这种替换概念。  
  
 `x:Name` 的 permittance 和名称唯一性强制的规则可能由特定的实现框架定义。 但是，若要与 .NET Framework XAML 服务一起使用，XAML 名称范围唯一性的框架定义应该与本文档中 <xref:System.Windows.Markup.INameScope> 信息的定义一致，并且应使用与信息位置相同的规则已应用。 例如，[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 实现将各种标记元素分成不同的 <xref:System.Windows.NameScope> 范围，如资源字典、页面级别 XAML 创建的逻辑树、模板和其他延迟的内容，然后强制执行 XAML 名称其中每个 XAML 名称范围内的唯一性。  
  
 对于使用 .NET Framework XAML 服务 XAML 对象编写器的自定义类型，可以建立或更改映射到类型的 `x:Name` 的属性。 通过在类型定义代码中引用要 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> 映射的属性的名称来定义此行为。  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> 是一个类型级特性。  
  
 Using.NET Framework XAML 服务，可通过实现 <xref:System.Windows.Markup.INameScope> 接口以非特定于框架的方式定义 XAML 名称范围支持的支持逻辑。  
  
## <a name="wpf-usage-notes"></a>WPF 使用说明  
 在使用 XAML、分部类和代码隐藏的 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 应用程序的标准生成配置下，指定的 `x:Name` 成为标记编译生成处理 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 时在基础代码中创建的字段的名称任务，该字段包含对对象的引用。 默认情况下，创建的字段为内部字段。 可以通过指定[x:FieldModifier 属性](x-fieldmodifier-directive.md)来更改字段访问权限。 在 WPF 和 Silverlight 中，序列是标记编译定义并命名分部类中的字段，但该值最初为空。 然后，从类构造函数中调用名为 `InitializeComponent` 的生成方法。 `InitializeComponent` 包含 `FindName` 调用，它们使用在分部类的 XAML 定义部分中存在的每个 `x:Name` 值作为输入字符串。 然后，将返回值分配给赞命名字段引用，以用通过 XAML 分析创建的对象填充字段值。 执行 `InitializeComponent` 使你可以直接使用 `x:Name`/字段名称引用运行时对象关系图，而不必在需要引用 XAML 定义的对象时显式调用 `FindName`。  
  
 对于使用 Microsoft Visual Basic 目标的 WPF 应用程序，并包含具有 `Page` 生成操作的 XAML 文件，在编译过程中将创建一个单独的引用属性，该属性将 `WithEvents` 关键字添加到具有 `x:Name`的所有元素，以支持 @no事件处理程序委托的 __t_3_ 语法。 此属性始终是公共的。 有关详细信息，请参阅 [Visual Basic 和 WPF 事件处理](../wpf/advanced/visual-basic-and-wpf-event-handling.md)。  
  
 WPF XAML 处理器使用 `x:Name` 在加载时将名称注册到 XAML 名称范围，即使在页面未通过生成操作进行标记编译（例如，资源字典的松散 XAML）时也是如此。 此行为的一个原因是因为 `x:Name` 可能需要 <xref:System.Windows.Data.Binding.ElementName%2A> 绑定。 有关详细信息，请参阅[数据绑定概述](../../desktop-wpf/data/data-binding-overview.md)。  
  
 如前所述，在也使用 `x:Key`的情况下，不应应用 `x:Name` （或 `Name`）。 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.ResourceDictionary> 具有将自身定义为 XAML 名称范围的特殊行为，但不会为 <xref:System.Windows.Markup.INameScope> Api 返回值或 null 值，以实现此行为。 如果 WPF XAML 分析器在 XAML 定义的 <xref:System.Windows.ResourceDictionary>中遇到 `Name` 或 `x:Name`，则不会将该名称添加到任何 XAML 名称范围。 尝试从任何 XAML 名称范围和 `FindName` 方法中查找该名称将不会返回有效的结果。  
  
### <a name="xname-and-name"></a>X：Name 和名称  
 很多 WPF 应用程序方案都可以避免任何使用 `x:Name` 特性，因为在默认 XAML 命名空间中为多个重要基类（如 <xref:System.Windows.FrameworkElement> 和 <xref:System.Windows.FrameworkContentElement>）指定的 `Name` 依赖项属性将满足此相同目的。 还有一些常见 XAML 和 WPF 方案，在这些方案中，代码访问框架级别上没有 `Name` 属性的元素是非常重要的。 例如，某些动画和情节提要支持类不支持 `Name` 属性，但通常需要在代码中引用这些类才能控制动画。 如果你打算稍后从代码中引用它们，则应将 `x:Name` 指定为在 XAML 中创建的时间线和转换的属性。  
  
 如果 <xref:System.Windows.FrameworkElement.Name%2A> 作为类的属性提供，则可以将 <xref:System.Windows.FrameworkElement.Name%2A> 和 `x:Name` 交换为属性，但如果两者都在同一个元素上指定，则将导致分析异常。 如果 XAML 是标记编译的，则异常将在标记编译中发生，否则会在加载时发生。  
  
 可以使用 XAML 特性语法和使用 <xref:System.Windows.DependencyObject.SetValue%2A>的代码来设置 <xref:System.Windows.FrameworkElement.Name%2A>;但请注意，在代码中设置 <xref:System.Windows.FrameworkElement.Name%2A> 属性不会在已加载 XAML 的大多数情况下在 XAML 名称范围内创建代表字段引用。 不要尝试在代码中设置 <xref:System.Windows.FrameworkElement.Name%2A>，而是根据相应的名称范围使用代码中的 <xref:System.Windows.NameScope> 方法。  
  
 还可以通过对内部文本使用属性元素语法来设置 <xref:System.Windows.FrameworkElement.Name%2A>，但这种情况并不常见。 相反，不能在 XAML 属性元素语法中或使用 <xref:System.Windows.DependencyObject.SetValue%2A>的代码中设置 `x:Name`;它只能在对象上使用特性语法来设置，因为它是一个指令。  
  
## <a name="silverlight-usage-notes"></a>Silverlight 使用说明  
 Silverlight `x:Name` 分别进行了说明。 有关详细信息，请参阅[XAML 命名空间（x：）语言功能（Silverlight）](https://go.microsoft.com/fwlink/?LinkId=199081)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>
- <xref:System.Windows.FrameworkContentElement.Name%2A?displayProperty=nameWithType>
- [WPF 中的树](../wpf/advanced/trees-in-wpf.md)
