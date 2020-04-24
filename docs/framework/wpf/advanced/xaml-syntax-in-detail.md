---
title: XAML 语法详述
ms.date: 03/30/2017
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
ms.openlocfilehash: 5f8bb862ce443fd7397036b10f69cda65a6960bc
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646146"
---
# <a name="xaml-syntax-in-detail"></a>XAML 语法详述
本主题定义用于描述 XAML 语法元素的术语。 这些术语在本文档的其余部分中经常使用，具体用于 WPF 文档，以及使用 XAML 或其他框架的其他框架，这些框架或在 System.Xaml 级别启用的 XAML 语言支持。 本主题将展开主题[XAML 概述 （WPF）](../../../desktop-wpf/fundamentals/xaml.md)中介绍的基本术语。  

<a name="the_xaml_language_specification"></a>
## <a name="the-xaml-language-specification"></a>XAML 语言规范  
 此处定义的 XAML 语法术语也在 XAML 语言规范中定义或引用。 XAML 是基于 XML 的语言，它遵循或扩展了 XML 结构规则。 某些术语来自或基于描述 XML 语言或 XML 文档对象模型时常用的术语。  
  
 有关 XAML 语言规范的详细信息，请从 Microsoft 下载中心下载[\[MS-XAML。\] ](https://download.microsoft.com/download/0/A/6/0A6F7755-9AF5-448B-907D-13985ACCF53E/[MS-XAML].pdf)  
  
<a name="xaml_and_clr"></a>
## <a name="xaml-and-clr"></a>XAML 和 CLR  
 XAML 是一种标记语言。 通用语言运行时 （CLR） （CLR） 的名称所暗示，支持运行时执行。 XAML 本身并不是 CLR 运行时直接使用的常见语言之一。 相反，您可以将 XAML 视为支持其自己的类型系统。 WPF 使用的特定 XAML 解析系统构建在 CLR 和 CLR 类型系统上。 XAML 类型映射到 CLR 类型，以在分析 WPF 的 XAML 时实例化运行时表示。 因此，本文档中关于语法的讨论的其余部分将包括对 CLR 类型系统的引用，即使 XAML 语言规范中的等效语法讨论没有。 （根据 XAML 语言规范级别，XAML 类型可以映射到任何其他类型系统，其中不必是 CLR，但需要创建和使用不同的 XAML 解析器。  
  
#### <a name="members-of-types-and-class-inheritance"></a>类型和类继承的成员  
 属性和事件作为[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]类型的 XAML 成员显示时通常从基类型继承。 例如，请考虑此示例： `<Button Background="Blue" .../>`。 如果要<xref:System.Windows.Controls.Control.Background%2A>查看类定义、反射结果或文档，<xref:System.Windows.Controls.Button>则该属性不是类上的立即声明属性。 <xref:System.Windows.Controls.Control.Background%2A>而是从基<xref:System.Windows.Controls.Control>类继承的。  
  
 XAML 元素[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的类继承行为与 XML 标记的架构强制解释有重大背离。 类继承可能会变得复杂，尤其是在中间基类是抽象的，或者涉及接口时。 这是 XAML 元素集及其允许属性难以准确、完整地使用通常用于 XML 编程的架构类型（如 DTD 或 XSD 格式）的一个原因。 另一个原因是 XAML 语言本身的可扩展性和类型映射功能排除了允许类型和成员的任何固定表示形式的完整性。  
  
<a name="object_element_syntax"></a>
## <a name="object-element-syntax"></a>对象元素语法  
 *对象元素语法*是 XAML 标记语法，它通过声明 XML 元素实例化 CLR 类或结构。 此语法类似于其他标记语言（如 HTML）的元素语法。 对象元素语法以左角度括号 （），\<紧接着是实例化的类或结构的类型名称。 零个或多个空格可以遵循类型名称，也可以在对象元素上声明零个或多个属性，其中一个或多个空格分隔每个属性名称 ="值"对。 最后，以下必须为 true：  
  
- 元素和标记必须用前斜杠 （/） 紧接，然后紧跟直角支架 （>）。  
  
- 开口标记必须由直角支架（>）完成。 其他对象元素、属性元素或内部文本可以遵循打开标记。 此处可能包含的内容通常受元素的对象模型的约束。 对象元素的等效关闭标记也必须存在，以适当的嵌套并与其他打开和关闭标记对平衡。  
  
 .NET 实现的 XAML 具有一组规则，这些规则将对象元素映射到类型、属性或事件的属性以及 XAML 命名空间到 CLR 命名空间加上程序集。 对于 WPF 和 .NET，XAML 对象元素映射到引用程序集中定义的 .NET 类型，属性映射到这些类型的成员。 在 XAML 中引用 CLR 类型时，您也有权访问该类型的继承成员。  
  
 例如，以下示例是对象元素语法，它实例化<xref:System.Windows.Controls.Button>类的新实例，并指定该<xref:System.Windows.FrameworkElement.Name%2A>属性的属性和值：  
  
 [!code-xaml[XAMLOvwSupport#SyntaxOE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxoe)]  
  
 下面的示例是对象元素语法，该语法还包括 XAML 内容属性语法。 中包含的内部文本将用于设置<xref:System.Windows.Controls.TextBox>XAML 内容属性 。 <xref:System.Windows.Controls.TextBox.Text%2A>  
  
 [!code-xaml[XAMLOvwSupport#ThisIsATextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#thisisatextbox)]  
  
### <a name="content-models"></a>内容模型  
 类在语法方面可能支持作为 XAML 对象元素的用法，但该元素只有在放置在总体内容模型或元素树的预期位置时，才会在应用程序或页面中正常运行。 例如，通常<xref:System.Windows.Controls.MenuItem>应仅作为<xref:System.Windows.Controls.Primitives.MenuBase>派生类（如<xref:System.Windows.Controls.Menu>） 的子级放置。 特定元素的内容模型作为控件和其他[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]类可用作 XAML 元素的类页上的备注的一部分进行记录。  
  
<a name="properties_of_object_elements"></a>
## <a name="properties-of-object-elements"></a>对象元素的属性  
 XAML 中的属性由各种可能的语法设置。 哪些语法可用于特定属性将因所设置的属性的基础类型系统特征而异。  
  
 通过设置属性的值，可以像运行时对象图中存在的对象一样，向对象添加要素或特征。 从对象元素创建的对象的初始状态基于无参数构造函数行为。 通常，应用程序将使用任何给定对象的完全默认实例以外的内容。  
  
<a name="attribute_syntax_properties"></a>
## <a name="attribute-syntax-properties"></a>特性语法（属性）  
 属性语法是 XAML 标记语法，通过在现有对象元素上声明属性来设置属性的值。 属性名称必须与支持相关对象元素的类属性的 CLR 成员名称匹配。 属性名称后跟赋值运算符 （*）。 属性值必须是包含在引号中的字符串。  
  
> [!NOTE]
> 可以使用交替引号在属性中放置文本引号。 例如，可以使用单引号作为声明包含其中双引号字符的字符串的方法。 无论使用单引号还是双引号，都应使用匹配对来打开和关闭属性值字符串。 还有一些转义序列或其他技术可用于解决任何特定 XAML 语法施加的字符限制。 请参阅[XML 字符实体和 XAML](../../../desktop-wpf/xaml-services/xml-character-entities.md)。  
  
 要通过属性语法进行设置，属性必须是公共的，并且必须是可写入的。 支持类型系统中的属性值必须是值类型，或者必须是访问相关备份类型时 XAML 处理器可以实例化或引用的引用类型。  
  
 对于 WPF XAML 事件，引用为属性名称的事件必须是公共的，并且具有公共委托。  
  
 属性或事件必须是由包含对象元素实例化的类或结构的成员。  
  
### <a name="processing-of-attribute-values"></a>属性值的处理  
 首开和收盘引号中包含的字符串值由 XAML 处理器处理。 对于属性，默认处理行为由基础 CLR 属性的类型确定。  
  
 属性值由以下之一填充，使用此处理顺序：  
  
1. 如果 XAML 处理器遇到大括号或派生自<xref:System.Windows.Markup.MarkupExtension>的对象元素，则首先计算引用的标记扩展，而不是将该值作为字符串处理，标记扩展返回的对象用作值。 在许多情况下，标记扩展返回的对象将是对现有对象的引用，或将计算推迟到运行时的表达式，而不是新实例化的对象。  
  
2. 如果属性用属性声明<xref:System.ComponentModel.TypeConverter>，或者该属性的值类型用属性<xref:System.ComponentModel.TypeConverter>声明，则属性的字符串值将作为转换输入提交到类型转换器，转换器将返回一个新的对象实例。  
  
3. 如果没有<xref:System.ComponentModel.TypeConverter>，则尝试直接转换为属性类型。 此最终级别是 XAML 语言基元类型之间的解析器本机值的直接转换，或对枚举中命名常量的名称的检查（解析器随后访问匹配值）。  
  
#### <a name="enumeration-attribute-values"></a>枚举属性值  
 XAML 中的枚举由 XAML 解析器进行内在处理，枚举成员应通过指定枚举命名常量之一的字符串名称来指定枚举。  
  
 对于非标记枚举值，本机行为是处理属性值的字符串并将其解析为枚举值之一。 您不会在格式枚*举*中指定枚举。*值*，就像您在代码中所做的一样。 相反，您只指定*值*，而*枚举*则由要设置的属性的类型推断。 如果在*枚举*中指定属性。*值*形式，它将不会正确解析。  
  
 对于正面枚举，行为基于 方法<xref:System.Enum.Parse%2A?displayProperty=nameWithType>。 可以通过用逗号分隔每个值来为旗面枚举指定多个值。 但是，不能合并不按标志标记的枚举值。 例如，不能使用逗号语法尝试创建<xref:System.Windows.Trigger>对非标志枚举的多个条件具有作用的 语法：  
  
```xaml  
<!--This will not compile, because Visibility is not a flagwise enumeration.-->  
...  
<Trigger Property="Visibility" Value="Collapsed,Hidden">  
  <Setter ... />  
</Trigger>  
...  
```  
  
 在 WPF 中，支持在 XAML 中可设置的属性的标记枚举很少见。 但是，此类枚举之一是<xref:System.Windows.Media.StyleSimulations>。 例如，您可以使用逗号分隔的标记属性语法来修改<xref:System.Windows.Documents.Glyphs>类的备注中提供的示例;`StyleSimulations = "BoldSimulation"`可能变成`StyleSimulations = "BoldSimulation,ItalicSimulation"`。 <xref:System.Windows.Input.KeyBinding.Modifiers%2A?displayProperty=nameWithType>是另一个可以指定多个枚举值的属性。 但是，此属性恰好是一个特殊情况，因为<xref:System.Windows.Input.ModifierKeys>枚举支持其自己的类型转换器。 修改器的类型转换器使用加号 （+） 作为分隔符而不是逗号 （，）。 此转换支持更传统的语法，以表示 Microsoft Windows 编程中的关键组合，例如"Ctrl_Alt"。  
  
### <a name="properties-and-event-member-name-references"></a>属性和事件成员名称引用  
 指定属性时，可以引用作为为包含对象元素实例化的 CLR 类型的成员存在的任何属性或事件。  
  
 或者，您可以引用附加的属性或附加事件，而独立于包含的对象元素。 （附加属性将在接下来的部分中讨论。  
  
 还可以使用*typeName*从可通过默认命名空间访问的任何对象命名任何事件。*事件*部分限定名称;此语法支持为路由事件附加处理程序，其中处理程序旨在处理来自子元素的事件路由，但父元素的成员表中也没有该事件。 此语法类似于附加的事件语法，但此处的事件不是真正的附加事件。 相反，您引用的事件具有限定名称。 有关详细信息，请参阅[路由事件概述](routed-events-overview.md)。  
  
 对于某些方案，属性名称有时作为属性的值提供，而不是属性名称。 该属性名称还可以包括限定符，例如窗体*所有者类型*中指定的属性。*属项属性名称*。 在 XAML 中编写样式或模板时，此方案很常见。 作为属性值提供的属性名称的处理规则不同，并且受要设置的属性类型或特定 WPF 子系统的行为控制。 有关详细信息，请参阅[样式和模板](../../../desktop-wpf/fundamentals/styles-templates-overview.md)化。  
  
 属性名称的另一个用法是属性值描述属性-属性关系时。 此功能用于数据绑定和情节提要目标，并且由<xref:System.Windows.PropertyPath>类及其类型转换器启用。 有关查找语义的更完整说明，请参阅[属性路径 XAML 语法](propertypath-xaml-syntax.md)。  
  
<a name="property_element_syntax"></a>
## <a name="property-element-syntax"></a>属性元素语法  
 *属性元素语法*是一种语法，它在某种程度上与元素的基本 XML 语法规则不同。 在 XML 中，属性的值是事实字符串，唯一可能的变化是使用哪个字符串编码格式。 在 XAML 中，可以将其他对象元素指定为属性的值。 此属性元素语法启用此功能。 该属性使用*元素TypeName*中的打开元素标记指定该属性，而不是将属性指定为元素标记中的属性。*属性名称*窗体中，在 其中指定属性的值，然后关闭属性元素。  
  
 具体而言，语法以左角度括号 （）\<开头，紧接着是属性元素语法中包含的类或结构的类型名称。 紧接着是一个点 （.），然后是属性的名称，然后是直角括号 （>）。 与属性语法一样，该属性必须存在于指定类型的已声明的公共成员中。 要分配给该属性的值包含在属性元素中。 通常，该值作为一个或多个对象元素给出，因为将对象指定为值是属性元素语法旨在解决的方案。 最后，指定相同*元素TypeName*的等效结束标记。*属性名称*组合必须提供，以适当的嵌套和平衡与其他元素标记。  
  
 例如，以下是 属性的属性的属性元素语法<xref:System.Windows.FrameworkElement.ContextMenu%2A><xref:System.Windows.Controls.Button>。  
  
 [!code-xaml[XAMLOvwSupport#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#contextmenu)]  
  
 属性元素中的值也可以作为内部文本给出，在指定的属性类型为基元值类型的情况下，例如<xref:System.String>， 或指定名称的枚举。 这两个用法有些不常见，因为每个情况都可以使用更简单的属性语法。 使用字符串填充属性元素的一个方案是，对于不是 XAML 内容属性但仍用于表示 UI 文本的属性，并且特定的空白元素（如行馈送）必须出现在该 UI 文本中。 属性语法无法保留行馈，但属性元素语法可以，只要显著的空白保留处于活动状态（有关详细信息，请参阅[XAML 中的空白处理](../../../desktop-wpf/xaml-services/white-space-processing.md)）。 另一种情况是[，x：Uid 指令](../../../desktop-wpf/xaml-services/xuid-directive.md)可以应用于属性元素，从而将 中的值标记为应在 WPF 输出 BAML 或其他技术中本地化的值。  
  
 属性元素未在 WPF 逻辑树中表示。 属性元素只是设置属性的特定语法，而不是具有实例或对象支持它的元素。 （有关逻辑树概念的详细信息，请参阅[WPF 中的树](trees-in-wpf.md)。  
  
 对于同时支持属性和属性元素语法的属性，这两种语法通常具有相同的结果，尽管空格处理等细微之处在语法之间可能略有不同。  
  
<a name="collection_syntax"></a>
## <a name="collection-syntax"></a>集合语法  
 XAML 规范要求 XAML 处理器实现标识值类型为集合的属性。 .NET 中的常规 XAML 处理器实现基于托管代码和 CLR，它通过以下之一标识集合类型：  
  
- 类型实现<xref:System.Collections.IList>。  
  
- 类型实现<xref:System.Collections.IDictionary>。  
  
- 类型派生自<xref:System.Array>（有关 XAML 中的数组的详细信息，请参阅[x：数组标记扩展](../../../desktop-wpf/xaml-services/xarray-markup-extension.md)。  
  
 如果属性的类型是集合，则推断的集合类型不需要在标记中指定为对象元素。 相反，打算成为集合中的项的元素被指定为属性元素的一个或多个子元素。 每个此类项在加载期间计算到对象，并通过调用隐含集合`Add`的方法添加到集合中。 例如， 的<xref:System.Windows.Style.Triggers%2A><xref:System.Windows.Style>属性采用专用集合类型<xref:System.Windows.TriggerCollection>， 实现<xref:System.Collections.IList>。 不必实例化标记中<xref:System.Windows.TriggerCollection>的对象元素。 <xref:System.Windows.Trigger>相反，您将一个或多个项指定为`Style.Triggers`属性元素中的元素，其中<xref:System.Windows.Trigger>（或派生类）是强烈键入和隐式<xref:System.Windows.TriggerCollection>中的项类型所需的类型。  
  
 [!code-xaml[XAMLOvwSupport#SyntaxPECollection](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxpecollection)]  
  
 属性可以是集合类型，也可以是该类型和派生类型的 XAML 内容属性，本主题的下一部分将对此进行讨论。  
  
 隐式集合元素在逻辑树表示形式中创建成员，即使它不作为元素出现在标记中。 通常，父类型的构造函数对其属性之一的集合执行实例化，并且最初空集合将成为对象树的一部分。  
  
> [!NOTE]
> 泛型列表和字典接口<xref:System.Collections.Generic.IList%601>（<xref:System.Collections.Generic.IDictionary%602>和 ） 不支持用于集合检测。 但是，您可以将<xref:System.Collections.Generic.List%601>类用作基类，因为它直接实现<xref:System.Collections.IList>，或者<xref:System.Collections.Generic.Dictionary%602>作为基类实现，因为它直接实现。 <xref:System.Collections.IDictionary>  
  
 在集合类型的 .NET 参考页中，在 XAML 语法部分中偶尔会将此语法与集合对象元素的故意省略记录称为隐式集合语法。  
  
 除根元素外，作为另一个元素的子元素嵌套的 XAML 文件中的每个对象元素实际上是一个元素，它是以下一种情况之一或两种情况：其父元素的隐式集合属性的成员，或指定父元素 XAML 内容属性值的元素（XAML 内容属性将在下一节中讨论）。 换句话说，标记页中的父元素和子元素的关系实际上是根上的单个对象，根下方的每个对象元素要么是提供父项属性值的单个实例，要么是集合中的项之一，也是父级的集合类型属性值。 这种单根概念在 XML 中很常见，并且在加载 XAML（如<xref:System.Windows.Markup.XamlReader.Load%2A>） 的 API 行为中经常被强化。  
  
 下面的示例是显式指定的集合的对象元素 （<xref:System.Windows.Media.GradientStopCollection>的语法。  
  
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
  
 请注意，并不总是可以显式声明集合。 例如，尝试在前面显示<xref:System.Windows.TriggerCollection><xref:System.Windows.Style.Triggers%2A>的示例中显式声明将失败。 显式声明集合要求集合类必须支持无参数构造函数，并且<xref:System.Windows.TriggerCollection>没有无参数构造函数。  
  
<a name="xaml_content_properties"></a>
## <a name="xaml-content-properties"></a>XAML 内容属性  
 XAML 内容语法是仅在指定<xref:System.Windows.Markup.ContentPropertyAttribute>作为类声明的一部分的类上启用的语法。 引用<xref:System.Windows.Markup.ContentPropertyAttribute>作为该类型元素（包括派生类）的内容属性的属性名称。 当 XAML 处理器处理时，对象元素的打开和关闭标记之间找到的任何子元素或内部文本都将分配为该对象的 XAML 内容属性的值。 允许为内容属性指定显式属性元素，但此用法通常不显示在 .NET 引用中的 XAML 语法部分中。 显式/详细技术偶尔对标记清晰度或标记样式具有价值，但内容属性通常旨在简化标记，以便可以直接嵌套与父子关系且直观相关的元素。 根据严格的 XAML 语言定义，元素上其他属性的属性元素标记不会指定为"内容";因此，根据严格的 XAML 语言定义，元素的属性元素标记不会指定为"内容";它们以前在 XAML 解析器的处理顺序中处理，不被视为"内容"。  
  
### <a name="xaml-content-property-values-must-be-contiguous"></a>XAML 内容属性值必须是连续的  
 XAML 内容属性的值必须完全放在该对象元素上的任何其他属性元素之前或完全之后。 无论 XAML 内容属性的值指定为字符串，还是指定为一个或多个对象，都是如此。 例如，以下标记不解析：  
  
```xaml  
<Button>I am a
  <Button.Background>Blue</Button.Background>  
  blue button</Button>  
```  
  
 这是非法的，主要是因为如果使用属性元素语法对内容属性显式进行此语法，则内容属性将设置两次：  
  
```xaml  
<Button>  
  <Button.Content>I am a </Button.Content>  
  <Button.Background>Blue</Button.Background>  
  <Button.Content> blue button</Button.Content>  
</Button>  
```  
  
 同样非法的示例是，如果内容属性是集合，并且子元素与属性元素交织在一起：  
  
```xaml  
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
 为了接受多个对象元素作为内容，内容属性的类型必须特别为集合类型。 与集合类型的属性元素语法类似，XAML 处理器必须标识集合类型的类型。 如果元素具有 XAML 内容属性，并且 XAML 内容属性的类型是集合，则隐含集合类型不需要在标记中指定为对象元素，并且不需要将 XAML 内容属性指定为属性元素。 因此，标记中的明显内容模型现在可以将多个子元素指定为内容。 以下是<xref:System.Windows.Controls.Panel>派生类的内容语法。 所有<xref:System.Windows.Controls.Panel>派生类都建立 XAML 内容属性<xref:System.Windows.Controls.Panel.Children%2A>，这需要 类型的<xref:System.Windows.Controls.UIElementCollection>值 。  
  
 [!code-xaml[XAMLOvwSupport#SyntaxContent](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page5.xaml#syntaxcontent)]  
  
 请注意，标记中既不需要<xref:System.Windows.Controls.Panel.Children%2A>属性元素，也<xref:System.Windows.Controls.UIElementCollection>不需要 元素的元素。 这是 XAML 的设计功能，因此，在不影响属性元素标记或集合对象的情况下，[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]可以更直观地将定义 定义的 元素表示为具有直接父子元素关系的嵌套元素树。 事实上，<xref:System.Windows.Controls.UIElementCollection>无法在标记中显式指定为对象元素。设计。 因为它的唯一用途是作为隐式集合，<xref:System.Windows.Controls.UIElementCollection>因此不会公开公共无参数构造函数，因此不能实例化为对象元素。  
  
### <a name="mixing-property-elements-and-object-elements-in-an-object-with-a-content-property"></a>将对象中的属性元素和对象元素与内容属性混合  
 XAML 规范声明 XAML 处理器可以强制用于填充对象元素中的 XAML 内容属性的对象元素必须是连续的，并且不能混合。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML 处理器强制执行了对混合属性元素和内容的限制。  
  
 可以将子对象元素作为对象元素中的第一个直接标记。 然后，您可以引入属性元素。 或者，您可以指定一个或多个属性元素，然后指定内容，然后指定更多属性元素。 但是，一旦属性元素遵循内容，您就不能引入任何进一步的内容，您只能添加属性元素。  
  
 此内容/属性元素顺序要求不适用于用作内容的内部文本。 但是，保持内部文本连续仍然是一种良好的标记样式，因为如果属性元素与内部文本交织在一起，则很难在标记中直观地检测到显著的空白。  
  
<a name="xaml_namespaces"></a>
## <a name="xaml-namespaces"></a>XAML 命名空间  
 前面的语法示例均未指定 XAML 命名空间，而不是默认的 XAML 命名空间。 在典型的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序中，默认 XAML 命名空间指定为[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]命名空间。 您可以指定默认 XAML 命名空间以外的 XAML 命名空间，并且仍然使用类似的语法。 但是，在命名在默认 XAML 命名空间中无法访问的类的任何地方，该类名称必须前面加上映射到相应 CLR 命名空间的 XAML 命名空间的前缀。 例如，`<custom:Example/>`对象元素语法用于实例化`Example`类的实例，其中包含该类的 CLR 命名空间（可能还有包含支持类型的外部程序集信息）以前映射到`custom`前缀。  
  
 有关 XAML 命名空间的详细信息，请参阅[WPF XAML 的 XAML 命名空间和命名空间映射](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)。  
  
<a name="markup_extensions"></a>
## <a name="markup-extensions"></a>标记扩展  
 XAML 定义了标记扩展编程实体，该实体允许从字符串属性值或对象元素的正常 XAML 处理器处理中转义，并将处理延迟到备份类。 使用属性语法时标识 XAML 处理器的标记扩展的字符是首角大括号 （*），后跟关闭大括号 （*） 以外的任何字符。 开头大括号后的第一个字符串必须引用提供特定扩展行为的类，如果该子字符串是真实类名称的一部分，则引用可能会省略子字符串"扩展"。 此后，可能会出现单个空格，然后每个后续字符都用作扩展实现的输入，直到遇到关闭的大括号。  
  
 .NET XAML 实现使用<xref:System.Windows.Markup.MarkupExtension>抽象类作为其他[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]框架或技术支持的所有标记扩展的基础。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]专门实现的标记扩展通常旨在提供引用其他现有对象的方法，或对将在运行时计算的对象进行延迟引用。 例如，通过指定`{Binding}`标记扩展代替特定属性通常采用的值来完成简单的 WPF 数据绑定。 许多 WPF 标记扩展为无法进行属性语法的属性启用属性语法。 例如，<xref:System.Windows.Style>对象是一种相对复杂的类型，包含嵌套的对象和属性系列。 WPF 中的样式通常定义为<xref:System.Windows.ResourceDictionary>中的资源，然后通过请求资源的两个 WPF 标记扩展之一引用。 标记扩展将属性值的计算延迟到资源查找，并启用在属性语法中提供<xref:System.Windows.FrameworkElement.Style%2A>属性的值，采用类型<xref:System.Windows.Style>，如以下示例所示：  
  
 `<Button Style="{StaticResource MyStyle}">My button</Button>`  
  
 此处，`StaticResource`标识提供标记<xref:System.Windows.StaticResourceExtension>扩展实现的类。 下一个`MyStyle`字符串用作非默认<xref:System.Windows.StaticResourceExtension>构造函数的输入，其中从扩展字符串获取的参数声明请求<xref:System.Windows.ResourceKey>的 。 `MyStyle`应为<xref:System.Windows.Style>定义为资源的[x：键](../../../desktop-wpf/xaml-services/xkey-directive.md)值。 [静态资源标记扩展](staticresource-markup-extension.md)使用请求使用资源在加载时通过静态资源查找逻辑<xref:System.Windows.Style>提供属性值。  
  
 有关标记扩展的详细信息，请参阅[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。 有关在常规 .NET XAML 实现中启用的标记扩展和其他 XAML 编程功能的引用，请参阅[XAML 命名空间 （x：）语言功能](../../../desktop-wpf/xaml-services/namespace-language-features.md). 有关特定于 WPF 的标记扩展，请参阅[WPF XAML 扩展](wpf-xaml-extensions.md)。  
  
<a name="attached_properties"></a>
## <a name="attached-properties"></a>附加属性  
 附加属性是在 XAML 中引入的编程概念，根据该概念，属性可以由特定类型拥有和定义，但设置为任何元素的属性或属性元素。 附加属性的主要方案是使标记结构中的子元素能够将信息报告给父元素，而无需跨所有元素进行广泛共享的对象模型。 相反，父元素可以使用附加属性向子元素报告信息。 有关附加属性的用途以及如何创建自己的附加属性的详细信息，请参阅[附加属性概述](attached-properties-overview.md)。  
  
 附加属性使用表面上类似于属性元素语法的语法，因为您还指定了*typeName*。*属性名称*组合。 有两个重要的差异：  
  
- 您可以使用*类型名称*。*属性名称*组合，即使通过属性语法设置附加属性也是如此。 附加属性是唯一限定属性名称是属性语法中的要求。  
  
- 还可以对附加属性使用属性元素语法。 但是，对于典型的属性元素语法，指定的*类型Name*是包含属性元素的对象元素。 如果引用附加属性，则*typeName*是定义附加属性的类，而不是包含的对象元素。  
  
<a name="attached_events"></a>
## <a name="attached-events"></a>附加事件  
 附加事件是在 XAML 中引入的另一个编程概念，其中事件可以由特定类型定义，但处理程序可以附加到任何对象元素上。 在 WOF 实现中，定义附加事件的类型通常是定义服务的静态类型，有时这些附加事件由公开服务类型的路由事件别名公开。 附加事件的处理程序通过属性语法指定。 与附加事件一样，附加事件的属性语法将展开，以允许*typeName*。*事件名称*用法，其中*类型名称*是为附加的事件`Add`基础结构`Remove`提供和事件处理程序访问器的类，*事件名称*是事件名称。  
  
<a name="anatomy_of_a_xaml_page_root_element"></a>
## <a name="anatomy-of-a-xaml-root-element"></a>XAML 根元素的剖析  
 下表显示了分解的典型 XAML 根元素，显示了根元素的特定属性：  
  
|||  
|-|-|  
|`<Page`|打开根元素的对象元素|  
|`xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`|默认 （[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]） XAML 命名空间|  
|`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`|XAML 语言 XAML 命名空间|  
|`x:Class="ExampleNamespace.ExampleCode"`|将标记连接到为部分类定义的任何代码后面的任何部分类声明|  
|`>`|根对象元素的结束。 对象尚未关闭，因为元素包含子元素|  
  
<a name="optional_and_nonrecommended_xaml_usages"></a>
## <a name="optional-and-nonrecommended-xaml-usages"></a>可选和非推荐的 XAML 用法  
 以下各节介绍 XAML 处理器在技术上支持的 XAML 用法，但会产生详细性或其他美学问题，干扰在开发包含 XAML 源的应用程序时保持人类可读的 XAML 文件。  
  
### <a name="optional-property-element-usages"></a>可选属性元素用法  
 可选属性元素用法包括显式写入 XAML 处理器认为隐式的元素内容属性。 例如，当您声明 的内容时<xref:System.Windows.Controls.Menu>，可以选择显式声明 集合<xref:System.Windows.Controls.ItemsControl.Items%2A><xref:System.Windows.Controls.Menu>为`<Menu.Items>`属性元素标记，并将每个<xref:System.Windows.Controls.MenuItem>集合放在`<Menu.Items>`中，而不是使用隐式 XAML 处理器行为，所有<xref:System.Windows.Controls.Menu>子元素的所有子元素都必须是<xref:System.Windows.Controls.MenuItem>和 放置在<xref:System.Windows.Controls.ItemsControl.Items%2A>集合中。 有时，可选用法有助于直观地阐明标记中表示的对象结构。 或者有时显式属性元素使用可以避免在技术上起作用但视觉上令人困惑的标记，例如属性值中的嵌套标记扩展。  
  
### <a name="full-typenamemembername-qualified-attributes"></a>全类型名称.成员名称限定属性  
 *类型名称*。属性*的 iName*窗体实际上比路由事件案例更通用。 但在其他情况下，形式是多余的，你应该避免它，如果仅仅是标记风格和可读性的原因。 在下面的示例中，对<xref:System.Windows.Controls.Control.Background%2A>该属性的三个引用中的每一个都完全等效：  
  
 [!code-xaml[XAMLOvwSupport#TypeNameProp](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenameprop)]  
  
 `Button.Background`工作，因为 该<xref:System.Windows.Controls.Button>属性的限定查找成功（<xref:System.Windows.Controls.Control.Background%2A>从 Control 继承），并且<xref:System.Windows.Controls.Button>是对象元素或基类的类。 `Control.Background`工作，<xref:System.Windows.Controls.Control>因为类实际上定义<xref:System.Windows.Controls.Control.Background%2A>，是<xref:System.Windows.Controls.Control>一个<xref:System.Windows.Controls.Button>基类。  
  
 但是，以下*类型名称*。*成员名称*窗体示例不起作用，因此显示注释：  
  
 [!code-xaml[XAMLOvwSupport#TypeNameBadProp](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenamebadprop)]  
  
 <xref:System.Windows.Controls.Label>是另一派生类，<xref:System.Windows.Controls.Control>如果您在`Label.Background`<xref:System.Windows.Controls.Label>对象元素中指定，则此用法将起作用。 但是，由于<xref:System.Windows.Controls.Label>不是 的类或基类<xref:System.Windows.Controls.Button>，因此指定的 XAML 处理器行为是作为附加`Label.Background`属性进行处理。 `Label.Background`不是可用的附加属性，并且此用法将失败。  
  
### <a name="basetypenamemembername-property-elements"></a>基类型名称.成员名称属性元素  
 以类似的方式与*类型名称*。*成员名称*窗体适用于属性语法，*基类型名称*。*成员名称*语法适用于属性元素语法。 例如，以下语法有效：  
  
 [!code-xaml[XAMLOvwSupport#GoofyPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofype)]  
  
 此处，即使属性元素包含在 中`Control.Background``Button`，属性元素也给出为  
  
 但就像*类型名称*。*属性的成员名称*窗体，*基本类型名称*。*成员名称*在标记中是不好的样式，您应该避免它。  
  
## <a name="see-also"></a>另请参阅

- [XAML 概述 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [XAML 命名空间 (x:)语言功能](../../../desktop-wpf/xaml-services/namespace-language-features.md)
- [WPF XAML 扩展](wpf-xaml-extensions.md)
- [依赖项属性概述](dependency-properties-overview.md)
- [TypeConverters 和 XAML](typeconverters-and-xaml.md)
- [XAML 及 WPF 的自定义类](xaml-and-custom-classes-for-wpf.md)
