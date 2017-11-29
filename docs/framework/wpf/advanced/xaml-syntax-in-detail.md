---
title: "XAML 语法详述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML [WPF], namespaces
- XAML [WPF], parsing of attributes
- parsing of attributes [WPF]
- XAML [WPF], markup extensions
- attached properties [WPF]
- tag syntax [XAML]
- markup extensions [WPF]
- XAML [WPF], object element syntax
- XAML [WPF], syntax terminology
- attached events [WPF]
- lookup semantics [WPF]
- XAML [WPF], attached events
- XAML [WPF], content syntax
- XAML [WPF], lookup semantics
- content syntax [WPF]
- object element syntax [WPF]
- syntax terminology [XAML]
- XAML [WPF], attached properties
- attributes [XAML], parsing
- XAML [WPF], tag syntax
- XAML [WPF], attribute syntax
- property element syntax [WPF]
- terminology [XAML]
- namespaces [WPF], XML
- attribute syntax [XAML]
- XAML [WPF], property element syntax
ms.assetid: 67cce290-ca26-4c41-a797-b68aabc45479
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0aa85c9ec6e6b911444b07a4169dc769ac4df816
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="xaml-syntax-in-detail"></a>XAML 语法详述
本主题定义用于描述 XAML 语法的元素的条款。 这些条款本文档中，同时用于 WPF 文档的其余部分具体而言，并为使用 XAML 或通过在 System.Xaml 级别的 XAML 语言支持的基本 XAML 概念的其他框架经常使用。 本主题扩展主题中介绍的基本术语[XAML 概述 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)。  
  

  
<a name="the_xaml_language_specification"></a>   
## <a name="the-xaml-language-specification"></a>XAML 语言规范  
 此处定义的 XAML 语法术语还定义或引用在 XAML 语言规范。 XAML 是基于 XML 的语言并遵循或根据 XML 结构化规则进行扩展。 某些术语从共享，或基于描述 XML 语言或 XML 文档对象模型时通常使用的术语。  
  
 有关 XAML 语言规范的详细信息，请下载[ \[MS-XAML\] ](http://go.microsoft.com/fwlink/?LinkId=114525)从 Microsoft 下载中心获取。  
  
<a name="xaml_and_clr"></a>   
## <a name="xaml-and-clr"></a>XAML 和 CLR  
 XAML 是一种标记语言。 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]、 为隐含按其名称，启用运行时执行。 XAML 不是按本身直接由 CLR 运行时的通用语言之一。 相反，你可以将 XAML 视为支持其自己的类型系统。 WPF 使用特定 XAML 分析系统基于 CLR 和 CLR 类型系统。 XAML 类型映射到 CLR 类型时要实例化的运行的时表示分析 wpf XAML。 出于此原因，本文档中的语法的讨论的其余部分将包括 CLR 类型系统，对引用，即使在 XAML 语言规范中的等效语法讨论不这样做。 （每 XAML 语言规范级别，XAML 类型无法映射到任何其他类型的系统，这不一定要 CLR，但这将需要创建和使用不同的 XAML 分析器。）  
  
#### <a name="members-of-types-and-class-inheritance"></a>类型和类继承的成员  
 属性和它们的事件显示为 XAML 成员的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]类型通常继承自基类型。 例如，请看以下示例： `<Button Background="Blue" .../>`。 <xref:System.Windows.Controls.Control.Background%2A>属性不是立即声明的属性上<xref:System.Windows.Controls.Button>类，如果你要查看的类定义，反射结果或文档。 相反，<xref:System.Windows.Controls.Control.Background%2A>继承自基类<xref:System.Windows.Controls.Control>类。  
  
 类继承行为的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]XAML 元素是大的不同之处，从 XML 标记的架构上强制实施的解释。 特别是在中间基类为抽象类，或当涉及到接口时，可以变得复杂，类继承。 这是一个很难表示准确、 完整地使用的架构类型的 XAML 元素和其允许的属性集通常用于原因[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]编程，如 DTD 或 XSD 格式。 另一个原因是该扩展性和 XAML 语言本身的类型映射功能无任何固定表示形式的允许的类型和成员的完整性。  
  
<a name="object_element_syntax"></a>   
## <a name="object-element-syntax"></a>对象元素语法  
 *对象元素语法*是通过声明的 XML 元素中实例化的 CLR 类或结构的 XAML 标记语法。 此语法类似于其他标记语言，如 HTML 元素语法。 对象元素语法开头是左尖括号 (\<) 后, 立即跟的类或结构进行实例化的类型名称。 类型名称，后面可以有零个或多个空格和零个或多个特性还可以声明的对象元素上一个或多个空格来分隔每个属性名 ="值"对。 最后，以下项之一必须为 true:  
  
-   由正斜杠 （/） 后紧跟右尖括号 (>)，必须关闭的元素和标记。  
  
-   是右尖括号 (>)，必须完成的开始标记。 其他对象元素、 属性元素或内部文本，可以按照开始标记。 可能此处包含哪些内容的确切通常受元素的对象模型的约束。 等效的结束标记的对象元素也必须存在，但在正确的嵌套，并与其他开始和结束标记对平衡。  
  
 XAML.NET 的实施方式具有一套规则，将对象元素映射到类型、 将执行的属性或事件和 XAML 命名空间到 CLR 命名空间和程序集的特性。 有关 WPF 和.NET Framework，XAML 对象元素映射到[!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)]中定义的类型引用的程序集，并将属性映射到这些类型的成员。 在引用 XAML 中的 CLR 类型时，你有权以及该类型的继承的成员。  
  
 例如，下面的示例是在实例化的新实例的对象元素语法<xref:System.Windows.Controls.Button>类，并且还指定<xref:System.Windows.FrameworkElement.Name%2A>属性和该属性的值：  
  
 [!code-xaml[XAMLOvwSupport#SyntaxOE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxoe)]  
  
 下面的示例是还包括 XAML 内容属性语法的对象元素语法。 中包含的内部文本将用于设置<xref:System.Windows.Controls.TextBox>XAML 内容属性<xref:System.Windows.Controls.TextBox.Text%2A>。  
  
 [!code-xaml[XAMLOvwSupport#ThisIsATextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#thisisatextbox)]  
  
### <a name="content-models"></a>内容模型  
 类可能支持使用作为 XAML 对象元素根据语法，但该元素将仅正常运行的应用程序或页置于整体内容的模型或元素树的预期位置中时。 例如，<xref:System.Windows.Controls.MenuItem>通常只能放置的子级<xref:System.Windows.Controls.Primitives.MenuBase>派生类，如<xref:System.Windows.Controls.Menu>。 内容模型的特定元素编写为的控件和其他的类页上的备注部分一部分[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]可作为 XAML 元素的类。  
  
<a name="properties_of_object_elements"></a>   
## <a name="properties-of-object-elements"></a>对象元素的属性  
 在 XAML 中的属性是设置的各种可能的语法。 根据你设置的属性的基础类型系统特征，可以为特定的属性使用哪种语法将有所不同。  
  
 通过设置属性的值，你将添加功能或特征到对象因为它们存在于运行的时对象图。 从对象元素创建的对象的初始状态基于默认构造函数行为。 通常，你的应用程序将使用之外的任何给定的对象的完全默认实例的内容。  
  
<a name="attribute_syntax_properties"></a>   
## <a name="attribute-syntax-properties"></a>特性语法（属性）  
 特性语法是通过将属性声明在现有对象元素上设置属性的值的 XAML 标记语法。 属性名称必须匹配类支持的相关对象元素的属性的 CLR 成员名称。 属性名称后跟赋值运算符 （=）。 属性值必须括在引号内的字符串。  
  
> [!NOTE]
>  你可以使用交替引号将文本引号在特性中。 实例可以作为一种方法使用单引号来声明包含在其中一个双引号字符的字符串。 是否使用单引号或双引号时，你应使用匹配对用于打开和关闭属性值字符串。 也有转义序列或其他技术可用于解决所带来的任何特定的 XAML 语法的字符限制。 请参阅[XML 字符实体和 XAML](../../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)。  
  
 为了通过特性语法进行设置，属性必须是公共的并且必须可写。 中的后备类型系统的属性的值必须是值类型，或必须引用类型可以实例化或访问相关时引用由 XAML 处理器后备类型。  
  
 对于 WPF XAML 事件，属性名称作为引用的事件必须是公共的并具有公共委托。  
  
 属性或事件必须是类或结构，它包含的对象元素通过实例化的成员。  
  
### <a name="processing-of-attribute-values"></a>处理的属性值  
 包含在开始标记和结束引号引起来的字符串值由 XAML 处理器处理。 对于属性，默认处理行为由基础的 CLR 属性的类型确定。  
  
 属性值的内容由以下内容，之一使用此处理顺序：  
  
1.  如果 XAML 处理器遇到大括号或对象元素派生自<xref:System.Windows.Markup.MarkupExtension>、 然后引用的标记扩展而不是处理为字符串，值首先计算和标记扩展返回的对象用作值。 在许多情况下通过标记扩展返回的对象将对现有对象或将计算推迟到运行时并不是一个新实例化的对象的表达式的引用。  
  
2.  如果属性声明与特性化<xref:System.ComponentModel.TypeConverter>，或该属性的值类型声明与特性化<xref:System.ComponentModel.TypeConverter>、 该特性的字符串值提交到作为转换的输入，则类型转换器和转换器将返回新的对象实例。  
  
3.  如果没有任何<xref:System.ComponentModel.TypeConverter>，尝试直接转换为属性类型。 此最终级别是名为直接在 XAML 语言基元类型或检查枚举 （分析器随后将访问匹配的值） 中的已命名常数名称之间的分析器本机值。  
  
#### <a name="enumeration-attribute-values"></a>枚举属性值  
 在 XAML 中的枚举本质上处理的 XAML 分析程序，并且应指定枚举的命名常量之一的字符串名称指定枚举的成员。  
  
 对于无标志枚举值，本机行为是处理的属性值字符串并将其解析为枚举值之一。 您不指定格式枚举*枚举*。*值*，这一点与你在代码中。 作为替代，你指定仅*值*，和*枚举*由你设置的属性的类型推断。 如果指定中的属性*枚举*。*值*窗体中，它将无法正确解析。  
  
 对于按标志枚举，该行为取决于<xref:System.Enum.Parse%2A?displayProperty=nameWithType>方法。 可以通过用逗号隔开每个值指定标志枚举多个的值。 但是，不能将枚举值不按标志的组合。 例如，你不能使用逗号语法以尝试创建<xref:System.Windows.Trigger>作用于无标志枚举的多个条件：  
  
```  
<!--This will not compile, because Visibility is not a flagwise enumeration.-->  
...  
<Trigger Property="Visibility" Value="Collapsed,Hidden">  
  <Setter ... />  
</Trigger>  
...  
```  
  
 按标志枚举支持是可在 XAML 中设置的特性很少出现在 WPF 中。 但是，这样的一个枚举是<xref:System.Windows.Media.StyleSimulations>。 例如，可以使用逗号分隔按标志特性语法的备注部分中提供该示例修改<xref:System.Windows.Documents.Glyphs>类;`StyleSimulations = "BoldSimulation"`可能会变得`StyleSimulations = "BoldSimulation,ItalicSimulation"`。 <xref:System.Windows.Input.KeyBinding.Modifiers%2A?displayProperty=nameWithType>是另一个属性可以指定多个枚举值的位置。 但是，此属性恰好是一种特殊情况，因为<xref:System.Windows.Input.ModifierKeys>枚举支持其自己的类型转换器。 修饰符的类型转换器使用加号 （+） 作为分隔符，而不是逗号 （，）。 此转换支持更传统的语法来表示在 Microsoft Windows 编程中，如"Ctrl + Alt 键的组合键。  
  
### <a name="properties-and-event-member-name-references"></a>属性和事件成员名称引用  
 当指定特性时，你可以引用任何属性或作为你为包含的对象元素而实例化的 CLR 类型的成员存在的事件。  
  
 或者，你可以引用附加的属性或附加事件，独立于包含的对象元素。 （下一节讨论是附加的属性）。  
  
 此外可以将名称从任何对象使用可通过默认命名空间访问的任何事件*typeName*。*事件*部分限定的名称; 此附加路由事件的处理程序的支持用于处理从子元素，但父元素路由的事件处理程序还没有该事件在其成员表中的语法。 此语法类似于附加的事件的语法中，但此处该事件不是真正的附加的事件。 相反，所引用的限定名称的事件。 有关详细信息，请参阅[路由事件概述](../../../../docs/framework/wpf/advanced/routed-events-overview.md)。  
  
 在某些情况下，有时作为属性，而不是属性名称的值提供属性名称。 该属性名称还可以包括限定符，如窗体中指定的属性*所有者类型*。*依赖项属性名称*。 在 XAML 中编写样式或模板时，此方案中很常见。 提供作为属性值的属性名称的处理规则不相同，并且通过所设置的属性的类型或特定 WPF 子系统的行为控制。 有关详细信息，请参阅[样式和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)。  
  
 属性名称的另一个用法是当属性值描述 property 属性关系时。 此功能用于数据绑定和情节提要目标，以及是否启用<xref:System.Windows.PropertyPath>类和其类型转换器。 有关查找语义的更完整说明，请参阅[PropertyPath XAML 语法](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md)。  
  
<a name="property_element_syntax"></a>   
## <a name="property-element-syntax"></a>属性元素语法  
 *属性元素语法*是一种与元素的基本 XML 语法规则略有不同的语法。 在 XML 中，属性的值是一个实际的字符串，唯一可能的变化与被正在使用哪种字符串编码格式。 在 XAML 中，你可以分配其他对象元素要作为属性的值。 此功能被通过属性元素语法。 而不是指定为元素标记内的特性的属性，该属性使用指定的开始元素标记中*元素类型名称*。*propertyName*窗体中，指定的属性的值，然后关闭属性元素。  
  
 具体而言，该语法以左尖括号 (\<) 后, 立即跟的类或结构中包含的属性元素语法的类型名称。 这被紧跟为一个句点 （.），然后按名称的属性，然后是右尖括号 (>)。 与特性语法中，该属性必须存在于指定类型的已声明的公共成员。 要分配给属性的值将包含在属性元素。 通常，为给定的值为一个或多个对象元素，因为对象指定为值是该方案，属性元素语法的意图是地址。 最后，指定相同的等效的结束标记*元素类型名称*。*propertyName*组合必须提供，并正确的嵌套和与其他元素标记的平衡。  
  
 例如，以下是属性元素语法<xref:System.Windows.FrameworkElement.ContextMenu%2A>属性<xref:System.Windows.Controls.Button>。  
  
 [!code-xaml[XAMLOvwSupport#ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#contextmenu)]  
  
 给定的值中的属性元素可以还将为内部文本，在其中指定的属性类型是基元值类型的情况下如<xref:System.String>，或在指定名称的枚举。 这两种用法是某种程度上常见的因为每个这种情况下还可以使用简单的特性语法。 用字符串填充的属性元素的一个方案是，它们不 XAML 内容属性，但仍用于 UI 文本表示形式的属性和特定的空白元素 （如换行符） 需要该 UI 文本中显示。 特性语法不能保留换行符，但属性元素语法可以只要有意义的空白保留处于活动状态 (有关详细信息，请参阅[在 XAML 中的空白处理](../../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md))。 另一个方案是，以便[X:uid 指令](../../../../docs/framework/xaml-services/x-uid-directive.md)可应用于属性元素，并因此标记内的值，作为一个值，应本地化 WPF 中输出 BAML 或通过其他技术。  
  
 不在 WPF 逻辑树中表示的属性元素。 属性元素是只是一种特定的语法，来设置属性，并不是由实例或对象支持元素。 (有关的逻辑树概念的详细信息，请参阅[WPF 中的树](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)。)  
  
 对于其中支持特性和属性元素语法的属性，这两种语法通常具有相同的结果，但如空格处理的细微部分之间的语法略有不同。  
  
<a name="collection_syntax"></a>   
## <a name="collection-syntax"></a>集合语法  
 XAML 规范要求 XAML 处理器实现，以确定其中的值类型是集合的属性。 .NET 中的常规 XAML 处理器实现是在托管的代码和 CLR，和其所标识的集合类型通过以下项之一：  
  
-   类型实现<xref:System.Collections.IList>。  
  
-   类型实现<xref:System.Collections.IDictionary>。  
  
-   类型派生自<xref:System.Array>(有关在 XAML 中的数组的详细信息，请参阅[X:array 标记扩展](../../../../docs/framework/xaml-services/x-array-markup-extension.md)。)  
  
 如果属性的类型是一个集合，然后不需要指定在标记中作为对象元素推断的集合类型。 相反，旨在成为集合中的项的元素被指定为属性元素的一个或多个子元素。 在加载过程的对象计算每个此类项并将其添加到集合，通过调用`Add`默示的集合的方法。 例如，<xref:System.Windows.Style.Triggers%2A>属性<xref:System.Windows.Style>采用专用的集合类型<xref:System.Windows.TriggerCollection>，该类实现<xref:System.Collections.IList>。 不需要实例化<xref:System.Windows.TriggerCollection>对象标记中的元素。 作为替代，你指定一个或多个<xref:System.Windows.Trigger>项中的元素作为`Style.Triggers`属性元素中，其中<xref:System.Windows.Trigger>（或派生的类） 是强类型化和隐式为项类型的预期的类型<xref:System.Windows.TriggerCollection>。  
  
 [!code-xaml[XAMLOvwSupport#SyntaxPECollection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxpecollection)]  
  
 属性可能为集合类型，该类型的 XAML 内容属性和派生类型，这在本主题的下一节中讨论。  
  
 即使未出现在标记为元素，隐式集合元素在逻辑树表示中，创建的成员。 父类型的构造函数通常是其属性之一的集合执行实例化和最初为空集合将成为对象树的一部分。  
  
> [!NOTE]
>  泛型列表和字典接口 (<xref:System.Collections.Generic.IList%601>和<xref:System.Collections.Generic.IDictionary%602>) 不支持集合检测。 但是，你可以使用<xref:System.Collections.Generic.List%601>类用作基类，因为它实现<xref:System.Collections.IList>直接，或<xref:System.Collections.Generic.Dictionary%602>为基类，因为它实现了<xref:System.Collections.IDictionary>直接。  
  
 在集合类型的.NET 引用页面，此语法用于集合的对象元素故意省略偶尔需要注意 XAML 语法部分中为隐式集合语法。  
  
 除了根元素中，为另一个元素的子元素嵌套的 XAML 文件中的每个对象元素实际上是一个或两个以下情况下的元素： 其父元素的隐式集合属性的成员或指定的父元素 (XAML 内容属性将在下一节中讨论) 的 XAML 内容属性的值的元素。 换而言之，父元素和标记页面中的子元素的关系实际上是根目录，单个对象，它对根下的每个对象元素是提供的父级的属性值的单个实例或列中的项之一也是集合类型属性值的父级的 lection。 此单根概念是常见的 XML，并且还在如加载 XAML 的 Api 的行为经常进一步巩固<xref:System.Windows.Markup.XamlReader.Load%2A>。  
  
 下面的示例是集合的对象元素的语法 (<xref:System.Windows.Media.GradientStopCollection>) 显式指定。  
  
```xaml  
<LinearGradientBrush>  
  <LinearGradientBrush.GradientStops>  
    <GradientStopCollection>  
      <GradientStop Offset="0.0" Color="Red" />  
      <GradientStop Offset="1.0" Color="Blue" />  
    </GradientStopCollection>  
  </LinearGradientBrush.GradientStops>  
</LinearGradientBrush>  
```  
  
 请注意，它并不总是可以显式声明集合。 例如，尝试声明<xref:System.Windows.TriggerCollection>显式中前面显示<xref:System.Windows.Style.Triggers%2A>示例将失败。 集合类必须支持默认构造函数，显式声明集合要求和<xref:System.Windows.TriggerCollection>没有默认构造函数。  
  
<a name="xaml_content_properties"></a>   
## <a name="xaml-content-properties"></a>XAML 内容属性  
 XAML 内容语法是一种语法仅在指定的类启用<xref:System.Windows.Markup.ContentPropertyAttribute>作为其类声明的一部分。 <xref:System.Windows.Markup.ContentPropertyAttribute>引用该类型的元素 （包括派生的类） 的内容属性的属性名称。 当 XAML 处理器处理，将分配任何子元素或找到开始和结束标记的对象元素之间的内部文本，该对象的 XAML 内容属性的值。 允许你指定显式属性元素的内容的属性，但.NET 参考中的 XAML 语法部分中一般不介绍这种用法。 显式/详细的技术具有偶尔值为标记清楚起见，或作为一种标记样式，但通常内容属性的目的是简化标记，以便可以直接嵌套直观相关的父-子元素。 上一个元素的其他属性的属性元素标记不分配为"内容"每个严格的 XAML 语言定义;它们以前 XAML 分析器处理顺序进行处理，不被视为"内容"。  
  
### <a name="xaml-content-property-values-must-be-contiguous"></a>必须是连续的 XAML 内容属性值  
 XAML 内容属性的值必须在该对象元素完全之前或之后的任何其他属性元素指定。 XAML 内容属性的值指定为字符串，或作为一个或多个对象是否也是如此。 例如，以下的标记不会分析：  
  
```  
<Button>I am a   
  <Button.Background>Blue</Button.Background>  
  blue button</Button>  
```  
  
 这是非法实质上是因为如果通过使用内容的属性的属性元素语法，此语法进行显式，内容的属性将设置两次：  
  
```xml  
<Button>  
  <Button.Content>I am a </Button.Content>  
  <Button.Background>Blue</Button.Background>  
  <Button.Content> blue button</Button.Content>  
</Button>  
```  
  
 如果内容的属性是一个集合，并且子元素穿插属性元素，将是一个类似的非法示例：  
  
```xml  
<StackPanel>  
  <Button>This example</Button>  
  <StackPanel.Resources>  
    <SolidColorBrush x:Key="BlueBrush" Color="Blue"/>  
  </StackPanel.Resources>  
  <Button>... is illegal XAML</Button>  
</StackPanel>  
```  
  
<a name="content_properties_and_collection_syntax_combined"></a>   
## <a name="content-properties-and-collection-syntax-combined"></a>内容属性和集合语法组合  
 为了接受多个作为内容，单个对象元素内容的属性的类型专门必须是集合类型。 与集合类型的属性元素语法类似，XAML 处理器必须确定是集合类型的类型。 如果元素具有的 XAML 内容属性和 XAML 内容属性的类型是一个集合，然后隐含的集合类型不需要在作为对象元素的标记中指定并不需要指定为属性 el XAML 内容属性ement。 因此在标记中的明显内容模型现在可以具有多个分配作为内容的子元素。 以下是内容语法<xref:System.Windows.Controls.Panel>派生类。 所有<xref:System.Windows.Controls.Panel>派生的类建立 XAML 内容属性为<xref:System.Windows.Controls.Panel.Children%2A>，这需要类型的值<xref:System.Windows.Controls.UIElementCollection>。  
  
 [!code-xaml[XAMLOvwSupport#SyntaxContent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page5.xaml#syntaxcontent)]  
  
 请注意，既不的属性元素<xref:System.Windows.Controls.Panel.Children%2A>也的元素不<xref:System.Windows.Controls.UIElementCollection>需要在标记中。 这是 XAML 设计功能，以便以递归方式包含了用于定义元素[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]更直观地表示为具有直接父-子元素间的关系，而无需干预的属性元素标记嵌套元素的树或集合对象。 事实上，<xref:System.Windows.Controls.UIElementCollection>不能指定显式中标记为对象元素，设计使然。 因为其唯一的预期的用途是作为隐式的集合，<xref:System.Windows.Controls.UIElementCollection>不会公开公共默认构造函数，因此不能实例化作为对象元素。  
  
### <a name="mixing-property-elements-and-object-elements-in-an-object-with-a-content-property"></a>混合使用属性元素和具有内容的属性的对象中的对象元素  
 XAML 规范声明用于填充对象元素中的 XAML 内容属性的对象元素必须是连续的并且必须不能与混合 XAML 处理器可以强制执行。 由强制执行针对混合使用属性元素和内容的此限制[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]XAML 处理器。  
  
 你可以将子对象元素作为对象元素内的第一个即时标记。 然后，你可以引进属性元素。 或者，你可以指定一个或多个属性的元素，然后内容，然后更多属性元素。 但是，一旦的属性元素内容后面跟，不能引入任何进一步的内容，你可以仅添加属性元素。  
  
 此内容 / 属性元素顺序要求不适用于内部用作内容的文本。 但是，它仍是要保留内部文本连续的因为有意义的空白将很难直观地检测在标记中如果属性元素穿插内部文本的不错的标记样式。  
  
<a name="xaml_namespaces"></a>   
## <a name="xaml-namespaces"></a>XAML 命名空间  
 上面的语法示例中未指定 XAML 命名空间以外的默认 XAML 命名空间。 在典型[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序，默认 XAML 命名空间被指定为[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]命名空间。 您可以指定默认 XAML 命名空间之外的 XAML 命名空间，而且可以仍使用相似的语法。 但然后，任何位置其中类命名为不在默认 XAML 命名空间中, 访问该类的名称前必须是 XAML 命名空间的前缀映射到对应的 CLR 命名空间。 例如，`<custom:Example/>`是用于实例化的实例的对象元素语法`Example`类，其中包含此类 （和可能包含后备类型的外部程序集信息） 的 CLR 命名空间以前映射到`custom`前缀。  
  
 有关 XAML 命名空间的详细信息，请参阅[XAML 命名空间和 Namespace 映射为 WPF XAML](../../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)。  
  
<a name="markup_extensions"></a>   
## <a name="markup-extensions"></a>标记扩展  
 XAML 定义标记扩展编程启用从字符串特性值或对象元素的正常的 XAML 处理器处理转义，并将推迟到后备类处理的实体。 标识 XAML 处理器的标记扩展使用的特性语法时不使用右大括号 （}） 的任意字符后跟的左大括号 （{）） 字符。 后面的左大括号的第一个字符串必须引用此类提供的特定扩展行为，该引用可能会省略子字符串"扩展"，如果该子字符串是真正的类名的一部分。 随后，可能会出现一个空格，并且然后每个后续字符被用作输入扩展实现中，直至遇到的右大括号。  
  
 .NET XAML 实现使用<xref:System.Windows.Markup.MarkupExtension>抽象类为所有受支持的标记扩展的基础[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]以及其他框架或技术。 标记扩展的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]专门实现通常用于提供一种方法，以引用其他现有的对象，或以使延迟对将在运行时计算的对象的引用。 例如，简单的 WPF 数据绑定可以通过指定`{Binding}`来代替通常将采用的特定属性值的标记扩展。 WPF 标记扩展的许多启用其中的特性语法否则无法将属性的特性语法。 例如，<xref:System.Windows.Style>对象是相对复杂类型包含一系列嵌套的对象和属性。 WPF 中的样式通常定义为中的资源<xref:System.Windows.ResourceDictionary>，，然后引用通过其中一个请求资源的两个 WPF 标记扩展。 标记扩展将推迟到查找资源的属性值的计算，并使提供的值<xref:System.Windows.FrameworkElement.Style%2A>属性，采用类型<xref:System.Windows.Style>中特性语法如以下示例所示：  
  
 `<Button Style="{StaticResource MyStyle}">My button</Button>`  
  
 在这里，`StaticResource`标识<xref:System.Windows.StaticResourceExtension>类，用于提供标记扩展实现。 下一步字符串`MyStyle`作为输入用于非默认<xref:System.Windows.StaticResourceExtension>构造函数，从扩展字符串提取的参数声明请求<xref:System.Windows.ResourceKey>。 `MyStyle`应为[X:key](../../../../docs/framework/xaml-services/x-key-directive.md)值<xref:System.Windows.Style>定义为资源。 [否则标记扩展](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)用法要求资源可用于提供<xref:System.Windows.Style>静态资源查找逻辑在加载时通过属性值。  
  
 有关标记扩展的详细信息，请参阅[标记扩展和 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)。 有关标记扩展和其他 XAML 编程在普通的.NET XAML 实现中启用的功能的参考，请参阅[XAML Namespace （x:）语言功能](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md)。 有关特定于 WPF 的标记扩展，请参阅[WPF XAML 扩展](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md)。  
  
<a name="attached_properties"></a>   
## <a name="attached-properties"></a>附加属性  
 附加的属性是的 XAML 凭此可以拥有和定义的一个特定类型，属性中引入的编程概念但设置为属性或属性元素的任何元素。 主要方案用于附加的属性是启用而无需在所有元素之间的广泛共享的对象模型的报表信息传递到父元素的标记结构中的子元素。 相反，报表信息传递到子元素的父元素可以使用附加的属性。 有关详细信息的附加的属性以及如何创建你自己的目的附加属性，请参阅[附加属性概述](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)。  
  
 附加的属性使用一种语法看起来类似于属性元素语法中，您还指定*typeName*。*propertyName*组合。 有两个重要的差异：  
  
-   你可以使用*typeName*。*propertyName*即使设置附加的属性通过特性语法的组合。 附加的属性都是唯一的情况下，其中，限定属性名称是特性语法中的要求。  
  
-   此外可以使用附加属性的属性元素语法。 但是，对于典型的属性元素语法*typeName*指定是包含属性的元素的对象元素。 如果附加的属性，引用你则*typeName*是定义该附加的属性，不包含的对象元素的类。  
  
<a name="attached_events"></a>   
## <a name="attached-events"></a>附加事件  
 附加的事件是另一个 XAML 其中事件可以定义的特定类型，但可能在任何对象元素上附加处理程序中引入的编程概念。 在 WOF 实现中，定义附加的事件的类型通常是静态类型，它定义一种服务，并公开服务的类型中的路由的事件别名有时公开这些附加的事件。 附加事件的处理程序是通过属性语法指定的。 如附加事件的特性语法进行了扩展的附加事件，以允许*typeName*。*eventName*使用情况，其中*typeName*是提供的类`Add`和`Remove`附加的事件的基础结构，事件处理程序访问器和*eventName*是事件名称。  
  
<a name="anatomy_of_a_xaml_page_root_element"></a>   
## <a name="anatomy-of-a-xaml-root-element"></a>XAML 根元素的剖析  
 下表显示了一个典型 XAML 根元素分解结构，显示根元素的特定属性：  
  
|||  
|-|-|  
|`<Page`|打开对象的根元素的元素|  
|`xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`|默认值 ([!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]) XAML 命名空间|  
|`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`|在 XAML 语言 XAML 命名空间|  
|`x:Class="ExampleNamespace.ExampleCode"`|将标记连接到任何代码隐藏的分部类声明为分部类定义|  
|`>`|根对象元素的末尾。 对象是未关闭尚未，因为此元素包含子元素|  
  
<a name="optional_and_nonrecommended_xaml_usages"></a>   
## <a name="optional-and-nonrecommended-xaml-usages"></a>可选的推荐的 XAML 用法  
 下列各节描述从技术上讲受 XAML 处理器，但详细级别或剩余用户可读的 XAML 文件会干扰其他美观问题产生的 XAML 用法你开发包含 XAML 源的应用程序.  
  
### <a name="optional-property-element-usages"></a>可选属性元素用法  
 可选属性元素用法包括显式写出元素内容属性的 XAML 处理器视为隐式。 例如，当你声明的内容时，才<xref:System.Windows.Controls.Menu>，你可以选择显式声明<xref:System.Windows.Controls.ItemsControl.Items%2A>集合<xref:System.Windows.Controls.Menu>作为`<Menu.Items>`属性元素标记，并将每个<xref:System.Windows.Controls.MenuItem>内`<Menu.Items>`而不是比使用隐式的 XAML 处理器行为的所有子元素<xref:System.Windows.Controls.Menu>必须<xref:System.Windows.Controls.MenuItem>并放入<xref:System.Windows.Controls.ItemsControl.Items%2A>集合。 有时可选用法可以帮助直观地阐明对象结构中的标记表示的那样。 或者，显式属性元素用法有时可以避免从技术上讲功能，但在直观地令人费解的情况下，例如在属性值中的嵌套的标记扩展的标记。  
  
### <a name="full-typenamemembername-qualified-attributes"></a>完全限定的类型属性  
 *TypeName*。*memberName*窗体属性的实际工作比仅仅使用路由的事件的情况更为普遍。 但在其他情况下该窗体是多余的应避免它，如果只是为了实现标记样式和可读性。 在下面的示例中，这三个引用到<xref:System.Windows.Controls.Control.Background%2A>属性是完全等效：  
  
 [!code-xaml[XAMLOvwSupport#TypeNameProp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenameprop)]  
  
 `Button.Background`很有效，因为该属性的限定的查找<xref:System.Windows.Controls.Button>成功 (<xref:System.Windows.Controls.Control.Background%2A>从控件继承) 和<xref:System.Windows.Controls.Button>对象元素的类或基类。 `Control.Background`很有效，因为<xref:System.Windows.Controls.Control>类实际定义<xref:System.Windows.Controls.Control.Background%2A>和<xref:System.Windows.Controls.Control>是<xref:System.Windows.Controls.Button>基类。  
  
 但是，以下*typeName*。*memberName*窗体示例不起作用，因此显示为注释：  
  
 [!code-xaml[XAMLOvwSupport#TypeNameBadProp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenamebadprop)]  
  
 <xref:System.Windows.Controls.Label>是另一个派生的类的<xref:System.Windows.Controls.Control>，并且如果已指定`Label.Background`内<xref:System.Windows.Controls.Label>object 元素，这种用法会起作用。 但是，因为<xref:System.Windows.Controls.Label>不是类或基类<xref:System.Windows.Controls.Button>，指定的 XAML 处理器行为是然后处理`Label.Background`为附加属性。 `Label.Background`不是可用的附加的属性，并且这种用法失败。  
  
### <a name="basetypenamemembername-property-elements"></a>baseTypeName.memberName 属性元素  
 如何以类似方式*typeName*。*memberName*格式如何适用于特性语法*基类型名称*。*memberName*语法适用于属性元素语法。 例如，下面的语法适用：  
  
 [!code-xaml[XAMLOvwSupport#GoofyPE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofype)]  
  
 在这里，属性元素已被当作`Control.Background`即使属性元素中包含`Button`。  
  
 但是，正如*typeName*。*memberName*的属性，窗体*基类型名称*。*memberName*是在标记中，较差的样式，您应避免使用它。  
  
## <a name="see-also"></a>另请参阅  
 [XAML 概述 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [XAML 命名空间 (x:) 语言功能](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md)  
 [WPF XAML 扩展](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md)  
 [依赖项属性概述](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [TypeConverter 和 XAML](../../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md)  
 [XAML 及 WPF 的自定义类](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
