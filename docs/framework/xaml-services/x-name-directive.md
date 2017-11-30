---
title: "x:Name 指令"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- x:Name
- xName
- Name
helpviewer_keywords:
- x:Name attribute [XAML Services]
- XAML [XAML Services], x:Name attribute
- Name attribute in XAML [XAML Services]
ms.assetid: b7e61222-e8cf-48d2-acd0-6df3b7685d48
caps.latest.revision: "27"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 90f0d27f3bf5adffe8a9b47940451e71fda082b9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="xname-directive"></a>x:Name 指令
唯一标识 XAML 定义 XAML 名称范围中的元素。 XAML 名称范围和其唯一性模型可以应用于实例化的对象，框架提供的 Api 或实现在运行时访问 XAML 创建的对象图的行为。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xaml  
<object x:Name="XAMLNameValue".../>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`XAMLNameValue`|符合的限制的字符串[XamlName 语法](../../../docs/framework/xaml-services/xamlname-grammar.md)。|  
  
## <a name="remarks"></a>备注  
 后`x:Name`应用于一个框架的支持的编程模型中，名称为等效于用于保存对象引用或实例返回由构造函数的变量。  
  
 值`x:Name`必须是唯一 XAML 名称范围内的指令的使用情况。 默认情况下时使用的.NET Framework XAML 服务 API，主 XAML 名称范围在 XAML 根元素的单个 XAML 生产型的定义中，并包含在该 XAML 生产环境中包含的元素。 由框架来实现特定方案，可以定义其他离散 XAML 名称范围中单个 XAML 生成可能发生的。 例如，在 WPF 中，新 XAML 名称范围定义并在该 XAML 生产也定义任何模板创建的。 有关 XAML 名称范围 （但适用于很多 XAML 名称范围概念编写为 WPF） 的详细信息，请参阅[WPF XAML Namescopes](../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)。  
  
 一般情况下，`x:Name`不应在也使用的情况下应用`x:Key`。 由特定的现有框架的 XAML 实现在引入之间的替换概念`x:Key`和`x:Name`，尽管这不是建议的做法。 .NET framework XAML 服务不支持此类替换概念，如处理的名称/密钥信息时<xref:System.Windows.Markup.INameScope>或<xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>。  
  
 规则的许可`x:Name`由特定实现框架可能定义以及名称强制唯一性。 但是，若要能够使用.NET Framework XAML 服务，框架的 XAML 名称范围唯一性应定义与的定义一致<xref:System.Windows.Markup.INameScope>本文档中的信息和有关在何处应使用相同的规则应用的信息。 例如，[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)]实现将各种标记元素分割成单独<xref:System.Windows.NameScope>范围，例如资源字典逻辑树中创建的页级别 XAML、 模板和其他延迟的内容，然后强制执行 XAML名称在每个这些 XAML 名称范围内的唯一性。  
  
 对于使用.NET Framework XAML 服务 XAML 对象编写器的自定义类型，属性映射到`x:Name`上可以建立一种类型，或者将其更改。 通过引用要使用映射的属性的名称定义此行为<xref:System.Windows.Markup.RuntimeNamePropertyAttribute>中的类型定义代码。  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>是一个类型级别属性。  
  
 可以通过实现特定于框架的方式定义 Using.NET Framework XAML 服务 XAML 命名空间支持的后备逻辑<xref:System.Windows.Markup.INameScope>接口。  
  
## <a name="wpf-usage-notes"></a>WPF 用法说明  
 下的标准生成配置[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]使用 XAML，分部类和代码隐藏，指定的应用程序`x:Name`将成为在基础中创建的字段的名称的代码时[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]由标记处理编译生成任务，并该字段包含对对象的引用。 默认情况下，创建的字段是内部的。 你可以通过指定更改字段访问[X:fieldmodifier 特性](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md)。 在 WPF 和 Silverlight，序列是标记编译定义，并且名称中的分部类，但值的字段是最初为空。 然后，一个名为的生成的方法`InitializeComponent`从类构造函数中调用。 `InitializeComponent`组成`FindName`使用每个调用`x:Name`存在于作为分部类的 XAML 定义部分的值输入字符串。 返回值然后分配给名称类似的字段引用以填充分析使用从 XAML 创建的对象的字段值。 执行`InitializeComponent`使运行的时对象图使用的引用可能`x:Name`/ 直接，字段名称，而不是无需调用`FindName`随时显式你需要向 XAML 定义的对象的引用。  
  
 有关的 WPF 应用程序使用[!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)]目标并包括与 XAML 文件`Page`添加的编译期间创建生成操作，单独的参考属性`WithEvents`关键字具有的所有元素`x:Name`到支持`Handles`事件处理程序委托的语法。 此属性始终是公共的。 有关详细信息，请参阅 [Visual Basic 和 WPF 事件处理](../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md)。  
  
 `x:Name`用于通过 WPF XAML 处理器在加载时，即使对于其中的页面不是生成操作 (例如，资源字典中的宽松型 XAML) 进行标记编译的情况下注册到 XAML 名称范围的名称。 此行为的原因之一是因为`x:Name`可能需要为<xref:System.Windows.Data.Binding.ElementName%2A>绑定。 有关详细信息，请参阅[数据绑定概述](../../../docs/framework/wpf/data/data-binding-overview.md)。  
  
 如前所述， `x:Name` (或`Name`) 不应在也使用的情况下应用`x:Key`。 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.ResourceDictionary>具有特殊的行为定义本身为 XAML 名称范围，但返回未实现或为 null 值的<xref:System.Windows.Markup.INameScope>作为一种方式强制执行此行为的 Api。 如果 WPF XAML 分析器遇到`Name`或`x:Name`中的 XAML 定义<xref:System.Windows.ResourceDictionary>，名称不会添加到任何 XAML 名称范围。 尝试查找任何 XAML 名称范围从该名称与`FindName`方法不会返回有效的结果。  
  
### <a name="xname-and-name"></a>X:name 和名称  
 许多 WPF 应用程序方案可以避免任何使用`x:Name`属性，所以`Name`作为依赖项属性中指定默认 XAML 命名空间为多个重要基类如<xref:System.Windows.FrameworkElement>和<xref:System.Windows.FrameworkContentElement>满足此同一目的。 仍有一些常见的 XAML 和 WPF 方案其中的代码没有的元素的访问`Name`framework 级别的属性很重要。 例如，不支持某些动画和情节提要的支持类`Name`属性，但它们通常需要在代码中引用以便控制动画。 应指定`x:Name`作为在时间线和创建在 XAML 中，如果你想要从代码中供以后参考的转换的属性。  
  
 如果<xref:System.Windows.FrameworkElement.Name%2A>为属性类，可用<xref:System.Windows.FrameworkElement.Name%2A>和`x:Name`可以互换使用作为属性，但如果两者都在同一元素上指定将分析异常。 如果 XAML 进行标记编译，异常将在发生标记编译，否则将在加载时发生。  
  
 <xref:System.Windows.FrameworkElement.Name%2A>可以使用 XAML 特性语法中，设置和在代码中使用<xref:System.Windows.DependencyObject.SetValue%2A>; 但是请注意该设置<xref:System.Windows.FrameworkElement.Name%2A>在代码中的属性不会在大多数情况下，XAML 已创建 XAML 名称范围内的代表性字段引用加载。 而不是正在尝试设置<xref:System.Windows.FrameworkElement.Name%2A>在代码中，使用<xref:System.Windows.NameScope>从代码中根据相应的名称范围的方法。  
  
 <xref:System.Windows.FrameworkElement.Name%2A>此外可以通过使用内部文本的属性元素语法设置，但这不常见。 与此相反，`x:Name`不能在 XAML 属性元素语法中，或在代码中使用设置<xref:System.Windows.DependencyObject.SetValue%2A>; 它仅可设置对象上使用的特性语法，因为它是一个指令。  
  
## <a name="silverlight-usage-notes"></a>Silverlight 用法说明  
 `x:Name`适用于 Silverlight 是分开记录。 有关详细信息，请参阅[XAML Namespace （x:）语言功能 (Silverlight)](http://go.microsoft.com/fwlink/?LinkId=199081)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>  
 <xref:System.Windows.FrameworkContentElement.Name%2A?displayProperty=nameWithType>  
 [WPF 中的树](../../../docs/framework/wpf/advanced/trees-in-wpf.md)
