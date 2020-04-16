---
title: XAML 概述
description: 了解 XAML 语言如何由 .NET Core 的 Windows 演示基础 （WPF） 进行结构化和实现。
author: thraka
ms.date: 08/08/2019
ms.author: adegeo
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user interfaces [XAML]
- classes [XAML]
- root element [XAML]
- XAML [WPF], about XAML
- base classes [XAML]
- routed events [WPF]
- code-behind files [WPF], XAML
- collection properties [XAML]
- events [XAML]
- property element [XAML]
- content models [XAML]
- Extensible Application Markup Language (see XAML)
- attribute syntax [XAML]
ms.openlocfilehash: b0a9357b623fbde08731a5b1ddb8fee3a93824c2
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2020
ms.locfileid: "81433000"
---
# <a name="xaml-overview-in-wpf"></a>WPF 中的 XAML 概述

本文介绍了 XAML 语言的功能，并演示了如何使用 XAML 编写 Windows 演示文稿基础 （WPF） 应用。 本文专门介绍由 WPF 实现的 XAML。 XAML 本身是一个比 WPF 更大的语言概念。

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="what-is-xaml"></a>什么是 XAML

XAML 是一种声明性标记语言。 应用于 .NET 核心编程模型时，XAML 简化了为 .NET Core 应用创建 UI。 您可以在声明性 XAML 标记中创建可见的 UI 元素，然后通过使用通过部分类定义联接到标记的代码后面文件将 UI 定义与运行时逻辑分开。 XAML 直接以程序集中定义的一组特定后备类型表示对象的实例化。 这与大多数其他标记语言不同，后者通常是与后备类型系统没有此类直接关系的解释语言。 XAML 支持一个工作流，其中单独的各方可以使用可能不同的工具处理 UI 和应用的逻辑。

以文本表示时，XAML 文件是通常具有 `.xaml` 扩展名的 XML 文件。 可通过任何 XML 编码对文件进行编码，但通常以 UTF-8 编码。

下面的示例演示如何创建按钮作为 UI 的一部分。 此示例旨在让您了解 XAML 如何表示常见的 UI 编程隐喻（它不是一个完整的示例）。

[!code-xaml[XAMLOvwSupport#DirtSimple](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#dirtsimple)]

## <a name="xaml-syntax-in-brief"></a>简单介绍 XAML 语法

下面章节介绍 XAML 语法的基本形式，并提供一个简短的标记示例。 这些章节并不提供每个语法形式的完整信息，例如这些语法形式如何在后备类型系统中表示。 有关 XAML 语法的详细信息，请参阅[XAML 语法详细信息](../../framework/wpf/advanced/xaml-syntax-in-detail.md)。

如果您以前熟悉 XML 语言，则以下几个部分中的许多材料对您来说都是基本内容。 这得益于 XAML 的一个基本设计原则。 XAML 语言定义其自身的概念，但这些概念在 XML 语言和标记窗体中工作。

### <a name="xaml-object-elements"></a>XAML 对象元素

对象元素通常声明类型的实例。 该类型在使用 XAML 作为语言的技术引用的程序集中定义。

对象元素语法始终以左尖括号 (`<`) 开头。 后跟要创建实例的类型的名称。 （名称可以包括前缀，稍后将解释这一概念。在此之后，您可以选择声明对象元素的属性。 要完成对象元素标记，以右角括号 （）`>`结尾。 相反，您可以使用不包含任何内容的自闭式窗体，通过连续使用前斜杠和闭合角度括号 （）`/>`完成标记。 例如，再次查看前面显示的标记代码段。

[!code-xaml[XAMLOvwSupport#DirtSimple](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#dirtsimple)]

这指定了两个对象元素：`<StackPanel>`（含有内容，后面有一个结束标记）和 `<Button .../>`（自结束形式，包含几个特性）。 对象元素`StackPanel`和`Button`每个映射到由 WPF 定义的类的名称，并且是 WPF 程序集的一部分。 指定对象元素标记时，为 XAML 处理创建指令以创建基础类型的新实例。 在分析和加载 XAML 时，通过调用基础类型的无参数构造函数创建每个实例。

### <a name="attribute-syntax-properties"></a>属性语法（属性）

对象的属性通常可表示为对象元素的特性。 属性语法命名要设置的对象属性，后跟赋值运算符 （*）。 特性的值始终指定为包含在引号中的字符串。

特性语法是最简化的属性设置语法，并且对曾使用过标记语言的开发人员而言是最直观的语法。 例如，以下标记将创建一个具有红色文本和蓝色背景的按钮，还将创建指定为 `Content` 的显示文本。

[!code-xaml[XAMLOvwSupport#BlueRedButton](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#blueredbutton)]

### <a name="property-element-syntax"></a>属性元素语法

对于对象元素的某些属性，无法使用特性语法，因为无法在特性语法的引号和字符串限制内充分地表达提供属性值所必需的对象或信息。 对于这些情况，可以使用另一个语法，即属性元素语法。

属性元素开始标记的语法为`<TypeName.PropertyName>`。 通常，该标记的内容是属性作为其值的类型的对象元素。 指定内容后，必须使用结束标记关闭属性元素。 结束标记的语法为`</TypeName.PropertyName>`。

如果可以使用特性语法，那么使用特性语法通常更为方便，且能够实现更为精简的标记，但这通常只是样式问题，而不是技术限制。 以下示例演示在前面的特性语法示例中设置的相同属性，但这次对 `Button` 的所有属性使用属性元素语法。

[!code-xaml[XAMLOvwSupport#BlueRedButtonPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#blueredbuttonpe)]

### <a name="collection-syntax"></a>集合语法

XAML 语言包含一些优化，可以生成更易于阅读的标记。 其中一项优化是：如果某个特定属性采用集合类型，则在标记中声明为该属性的值内的子元素的项将成为集合的一部分。 在这种情况下，子对象元素的集合是设置为集合属性的值。

下面的示例显示用于设置<xref:System.Windows.Media.GradientBrush.GradientStops%2A>属性值的集合语法。

```xaml
<LinearGradientBrush>
  <LinearGradientBrush.GradientStops>
    <!-- no explicit new GradientStopCollection, parser knows how to find or create -->
    <GradientStop Offset="0.0" Color="Red" />
    <GradientStop Offset="1.0" Color="Blue" />
  </LinearGradientBrush.GradientStops>
</LinearGradientBrush>
```

### <a name="xaml-content-properties"></a>XAML 内容属性

XAML 指定一种语言功能，类可以将其属性之一准确指定为 XAML_内容_属性。 该对象元素的子元素用于设置该内容属性的值。 换言之，仅对内容属性而言，可以在 XAML 标记中设置该属性时省略属性元素，并在标记中生成更直观的父级/子级形式。

例如，<xref:System.Windows.Controls.Border>指定<xref:System.Windows.Controls.Decorator.Child%2A>的内容_属性。_ 以下两<xref:System.Windows.Controls.Border>个元素的处理方式相同。 第一个元素利用内容属性语法并省略 `Border.Child` 属性元素。 第二个元素显式显示 `Border.Child`。

```xaml
<Border>
  <TextBox Width="300"/>
</Border>
<!--explicit equivalent-->
<Border>
  <Border.Child>
    <TextBox Width="300"/>
  </Border.Child>
</Border>
```

作为 XAML 语言的规则，XAML 内容属性的值必须完全在该对象元素的其他任何属性元素之前或之后指定。 例如，以下标记不编译。

```xaml
<Button>I am a
  <Button.Background>Blue</Button.Background>
  blue button</Button>
```

有关 XAML 语法的详细信息，请参阅[XAML 语法详细信息](../../framework/wpf/advanced/xaml-syntax-in-detail.md)。

### <a name="text-content"></a>文本内容

有少量 XAML 元素可直接将文本作为其内容来处理。 若要实现此功能，必须满足以下条件之一：

- 类必须声明内容属性，并且内容属性必须为可分配给字符串的类型（类型可以是<xref:System.Object>）。 例如，任何<xref:System.Windows.Controls.ContentControl>使用<xref:System.Windows.Controls.ContentControl.Content%2A>都用作其内容属性，并且它是 type，<xref:System.Object>并且支持<xref:System.Windows.Controls.ContentControl>在 如<xref:System.Windows.Controls.Button>：`<Button>Hello</Button>`上使用以下用法。

- 类型必须声明一个类型转换器，该类型转换器将文本内容用作初始化文本。 例如，`<Brush>Blue</Brush>`将 的内容`Blue`值转换为画笔。 这种情况实际上并不常见。

- 类型必须为已知的 XAML 语言基元。

### <a name="content-properties-and-collection-syntax-combined"></a>内容属性和集合语法组合在一起

请考虑此示例。

```xaml
<StackPanel>
  <Button>First Button</Button>
  <Button>Second Button</Button>
</StackPanel>
```

在这里，每个<xref:System.Windows.Controls.Button>元素都是 的<xref:System.Windows.Controls.StackPanel>子元素。 这是一个简单直观的标记，此标记由于两个不同的原因省略了两个标记。

- **省略堆栈面板.子属性元素：**<xref:System.Windows.Controls.StackPanel>派生自<xref:System.Windows.Controls.Panel>。 <xref:System.Windows.Controls.Panel>定义为<xref:System.Windows.Controls.Panel.Children%2A?displayProperty=nameWithType>其 XAML 内容属性。

- **省略的 UIElement 集合对象元素：** 属性<xref:System.Windows.Controls.Panel.Children%2A?displayProperty=nameWithType>采用 实现<xref:System.Collections.IList><xref:System.Windows.Controls.UIElementCollection>的类型 。 可以根据用于处理集合（如<xref:System.Collections.IList>）的 XAML 规则省略集合的元素标记。 （在这种情况下，<xref:System.Windows.Controls.UIElementCollection>实际上无法实例化，因为它不公开无参数构造函数，这就是为什么<xref:System.Windows.Controls.UIElementCollection>对象元素被显示出来）。

```xaml
<StackPanel>
  <StackPanel.Children>
    <!--<UIElementCollection>-->
    <Button>First Button</Button>
    <Button>Second Button</Button>
    <!--</UIElementCollection>-->
  </StackPanel.Children>
</StackPanel>
```

### <a name="attribute-syntax-events"></a>属性语法（事件）

特性语法还可用于事件成员，而非属性成员。 在这种情况下，特性的名称为事件的名称。 在 XAML 事件的 WPF 实现中，特性的值是实现该事件的委托的处理程序的名称。 例如，以下标记将<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件的处理程序分配给在标记中创建的处理程序： <xref:System.Windows.Controls.Button>

[!code-xaml[XAMLOvwSupport#ButtonWithCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml#buttonwithcodebehind)]

除此特性语法示例外，还有更多关于 WPF 中的事件和 XAML 的内容。 例如，可了解此处引用的 `ClickHandler` 表示什么，以及它是如何定义的。 本文即将推出的[事件和 XAML 代码后面](#events-and-xaml-code-behind)部分将对此进行说明。

## <a name="case-and-white-space-in-xaml"></a>XAML 中的外壳和空白

通常，XAML 区分大小写。 为了解决支持类型，WPF XAML 受 CLR 区分大小写的规则区分大小写。 以下情况下，对象元素、属性元素和特性名称均必须使用区分大小写的形式指定：按名称与程序集中的基础类型进行比较或者与类型的成员进行比较。 XAML 语言关键字和基元也区分大小写。 值并不总是区分大小写。 值是否区分大小写将取决于与采用该值的属性关联的类型转换器行为，或取决于属性值类型。 例如，<xref:System.Boolean>采用该类型的属性可以采用`true`或`True`作为等效值，但仅因为本机 WPF XAML 解析器类型转换字符串<xref:System.Boolean>已允许这些值作为等效值。

WPF XAML 处理器和序列化器将忽略或丢弃所有非显著的空白，并将规范化任何重要的空白。 这与 XAML 规范的默认空白行为建议一致。 仅当在 XAML 内容属性中指定字符串时，此行为才会产生后果。 简单来说，XAML 将空格、换行符和制表符转换为空格，然后在连续字符串的任一端找到，则保留一个空格。 本文未介绍 XAML 空白处理的完整说明。 有关详细信息，请参阅[XAML 中的空白处理](../xaml-services/white-space-processing.md)。

## <a name="markup-extensions"></a>标记扩展

标记扩展是一个 XAML 语言概念。 用于提供特性语法的值时，大括号（`{` 和 `}`）表示标记扩展用法。 此用法指示 XAML 处理不要像通常那样将特性值视为文本字符串或者可转换为字符串的值。

WPF 应用编程中使用的最常见的标记扩展是[`Binding`](../../framework/wpf/advanced/binding-markup-extension.md)，用于数据绑定表达式以及资源引用[`StaticResource`](../../framework/wpf/advanced/staticresource-markup-extension.md)和[`DynamicResource`](../../framework/wpf/advanced/dynamicresource-markup-extension.md)。 通过使用标记扩展，即使属性通常不支持特性语法，也可以使用特性语法为属性提供值。 标记扩展通常使用中间表达式类型来启用诸如延迟值或引用仅在运行时存在的其他对象等功能。

例如，以下标记使用属性语法设置<xref:System.Windows.FrameworkElement.Style%2A>属性的值。 属性<xref:System.Windows.FrameworkElement.Style%2A>采用<xref:System.Windows.Style>类的实例，默认情况下，属性语法字符串无法实例化该实例。 但在这种情况下，属性引用特定的标记扩展。 `StaticResource` 处理该标记扩展时，将返回对以前在资源字典中作为键控资源进行实例化的某个样式的引用。

[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources)]
[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources2](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources2)]
[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources3](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources3)]

有关特定在 WPF 中实现的所有 XAML 标记扩展的参考列表，请参阅 [WPF XAML 扩展](../../framework/wpf/advanced/wpf-xaml-extensions.md)。 有关由 System.Xaml 定义且更广泛地可用于 .NET Core XAML 实现的标记扩展的引用列表，请参阅[XAML 命名空间 （x：）语言功能](../xaml-services/namespace-language-features.md). 有关标记扩展概念的详细信息，请参阅[标记扩展和 WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)。

## <a name="type-converters"></a>类型转换器

在 [XAML 语法概述](#xaml-syntax-in-brief)一节中，曾提到特性值必须能够通过字符串进行设置。 除了某些类型（如<xref:System.String><xref:System.DateTime>或<xref:System.Uri>） 的本机处理外，如何将字符串转换为其他对象类型或基元值的基本本机处理基于类型本身。 但是，许多 WPF 类型或这些类型的成员扩展基本字符串属性处理行为，以便将更复杂的对象类型的实例指定为字符串和属性。

该<xref:System.Windows.Thickness>结构是已启用类型转换以用于 XAML 用法的类型的示例。 <xref:System.Windows.Thickness>指示嵌套矩形中的度量值，并用作属性（如<xref:System.Windows.FrameworkElement.Margin%2A>）的值。 通过在 上<xref:System.Windows.Thickness>放置类型转换器，使用 的所有<xref:System.Windows.Thickness>属性都更容易在 XAML 中指定，因为它们可以指定为属性。 下面的示例使用类型转换和属性语法为<xref:System.Windows.FrameworkElement.Margin%2A>提供 的值。

[!code-xaml[XAMLOvwSupport#MarginTCE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#margintce)]

前面的属性语法示例等效于以下更详细语法示例，在该示例中，通过包含<xref:System.Windows.FrameworkElement.Margin%2A><xref:System.Windows.Thickness>对象元素的属性元素语法来设置。 的<xref:System.Windows.Thickness>四个关键属性设置为新实例的属性：

[!code-xaml[XAMLOvwSupport#MarginVerbose](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#marginverbose)]

> [!NOTE]
> 也有数量有限的对象，其中类型转换是设置属性到该类型而不涉及子类的唯一公共方法，因为类型本身没有无参数构造函数。 示例为 <xref:System.Windows.Input.Cursor>。

有关类型转换的详细信息，请参阅[类型转换器和 XAML](../../framework/wpf/advanced/typeconverters-and-xaml.md)。

## <a name="xaml-root-elements-and-xaml-namespaces"></a>XAML 根元素和 XAML 命名空间

XAML 文件必须只有一个根元素，才能同时成为格式良好的 XML 文件和有效的 XAML 文件。 对于典型的 WPF 方案，使用在 WPF 应用模型中具有突出含义的根元素（<xref:System.Windows.Window>例如，对于<xref:System.Windows.Controls.Page>页面、<xref:System.Windows.ResourceDictionary>外部字典或<xref:System.Windows.Application>应用定义）。 下面的示例显示了 WPF 页的典型 XAML 文件的根元素，其根元素为<xref:System.Windows.Controls.Page>。

[!code-xaml[XAMLOvwSupport#RootOnly](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#rootonly)]
[!code-xaml[XAMLOvwSupport#RootOnly2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#rootonly2)]

根元素还包含特性 `xmlns` 和 `xmlns:x`。 这些特性向 XAML 处理器指示哪些 XAML 命名空间包含标记将其作为元素引用的后备类型的类型定义。 `xmlns` 特性明确指示默认的 XAML 命名空间。 在默认的 XAML 命名空间中，可以不使用前缀指定标记中的对象元素。 对于大多数 WPF 应用方案，以及 SDK 的 WPF 部分中给出的几乎所有示例，默认 XAML 命名空间将映射到 WPF 命名空间`http://schemas.microsoft.com/winfx/2006/xaml/presentation`。 `xmlns:x` 特性指示另一个 XAML 命名空间，该命名空间映射 XAML 语言命名空间`http://schemas.microsoft.com/winfx/2006/xaml`。

使用 `xmlns` 定义用法范围和名称范围映射的做法符合 XML 1.0 规范。 XAML 名称范围与 XML 名称范围的不同仅在于：XAML 名称范围还包含有关进行类型解析和分析 XAML 时名称范围的元素如何受类型支持的信息。

这些`xmlns`属性仅在每个 XAML 文件的根元素上是绝对必要的。 `xmlns` 定义将适用于根元素的所有子代元素（此行为也符合 `xmlns` 的 XML 1.0 规范）。同时允许根以下的其他元素上具有 `xmlns` 特性，这些特性将适用于定义元素的任何子代元素。 但是，频繁定义或重新定义 XAML 命名空间会导致难以阅读 XAML 标记样式。

其 XAML 处理器的 WPF 实现包括一个能够了解 WPF 核心程序集的基础结构。 众所周知，WPF 核心程序集包含支持 WPF 映射到默认 XAML 命名空间的类型。 这是通过项目生成文件中的配置以及 WPF 生成和项目系统实现的。 因此，将默认 XAML 命名空间声明为`xmlns`默认值是引用来自 WPF 程序集的 XAML 元素所必须的。

### <a name="the-x-prefix"></a>x： 前缀

在之前的根元素示例中，前缀 `x:` 用于映射 XAML 命名空间 `http://schemas.microsoft.com/winfx/2006/xaml`，该命名空间是支持 XAML 语言构造的专用 XAML 命名空间。 此`x:`前缀用于映射此 XAML 命名空间的项目模板、示例和整个 SDK 的文档。 XAML 语言的 XAML 命名空间包含多个编程构造，您将在 XAML 中经常使用这些构造。 下面列出了最常用的 `x:` 前缀编程构造：

- [x：键](../xaml-services/xkey-directive.md)：为（或其他框架中的类似字典概念<xref:System.Windows.ResourceDictionary>）中的每个资源设置一个唯一的键。 `x:Key`可能占您在典型 WPF 应用`x:`标记中看到的用法的 90%。

- [x：类](../xaml-services/xclass-directive.md)：为 XAML 页提供代码后面的类指定 CLR 命名空间和类名称。 必须具有这样一个类才能支持每个 WPF 编程模型的代码隐藏，因此即使没有资源，也几乎总是能看到映射的 `x:`。

- [x:Name](../xaml-services/xname-directive.md)：处理对象元素后，为运行时代码中存在的实例指定运行时对象名称。 通常，经常为 [x:Name](../xaml-services/xname-directive.md) 使用 WPF 定义的等效属性。 此类属性专门映射到 CLR 支持属性，因此对于应用编程更加方便，在应用中，您经常使用运行时代码从初始化的 XAML 中查找命名元素。 最常见的此类属性是<xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>。 当特定类型不支持等效的 WPF 框架级<xref:System.Windows.FrameworkElement.Name%2A>属性时，您仍可以使用[x：Name。](../xaml-services/xname-directive.md) 某些动画方案中会发生这种情况。

- [x:Static](../xaml-services/xstatic-markup-extension.md)：启用一个返回静态值的引用，该静态值不是与 XAML 兼容的属性。

- [x：类型](../xaml-services/xtype-markup-extension.md)：基于类型名称<xref:System.Type>构造引用。 这用于指定<xref:System.Type>采用 的属性，如<xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>，尽管属性通常具有本机字符串到<xref:System.Type>转换，其方式使[x：Type](../xaml-services/xtype-markup-extension.md)标记扩展用法是可选的。

`x:` 前缀/XAML 命名空间中还有其他一些不太常见的编程构造。 有关详细信息，请参阅 [XAML 命名空间 (x:) 语言功能](../xaml-services/namespace-language-features.md)。

## <a name="custom-prefixes-and-custom-types-in-xaml"></a>XAML 中的自定义前缀和自定义类型

对于您自己的自定义程序集，或者对于**演示文稿核心**、**演示文稿框架**和**WindowsBase**的 WPF 核心外的程序集，可以将程序集指定为自定义`xmlns`映射的一部分。 只要该类型能够正确地实现以支持正在尝试的 XAML 用法，就可以在 XAML 中引用该程序集中的类型。

下面是自定义前缀在 XAML 标记中工作的基本示例。 前缀`custom`在根元素标记中定义，并映射到与应用一起打包和可用的特定程序集。 此程序集包含 `NumericUpDown` 类型，实现该类型的目的是在支持常规 XAML 用法之外，还可以使用允许在 WPF XAML 内容模型的此特定点执行插入的类继承。 通过使用该前缀，此 `NumericUpDown` 控件的一个实例声明为对象元素，以便 XAML 分析程序可找到包含该类型的 XAML 命名空间，从而找到包含该类型定义的后备程序集的位置。

```xaml
<Page
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:custom="clr-namespace:NumericUpDownCustomControl;assembly=CustomLibrary"
    >
  <StackPanel Name="LayoutRoot">
    <custom:NumericUpDown Name="numericCtrl1" Width="100" Height="60"/>
...
  </StackPanel>
</Page>
```

有关 XAML 中自定义类型的详细信息，请参阅 [XAML 及 WPF 的自定义类](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)。

有关程序集中的 XML 命名空间和代码命名空间如何相关的详细信息，请参阅[WPF XAML 的 XAML 命名空间和命名空间映射](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)。

## <a name="events-and-xaml-code-behind"></a>事件和 XAML 代码背后

大多数 WPF 应用都包含 XAML 标记和代码后面。 在项目中，XAML 编写为`.xaml`文件，CLR 语言（如 Microsoft Visual Basic 或 C#）用于编写代码背后的文件。 在 WPF 编程和应用程序模型中对 XAML 文件进行标记编译时，XAML 文件的 XAML 代码隐藏文件的位置是通过如下方式来标识的：以 XAML 根元素的 `x:Class` 特性形式指定一个命名空间和类。

通过目前已介绍的示例，你已了解了几个按钮，但这其中没有一个按钮具有任何与其关联的逻辑行为。 为对象元素添加行为的主要应用程序级机制是使用元素类的现有事件，并为该事件编写特定处理程序，该处理程序在运行时引发该事件时调用。 在标记中指定事件名称以及要使用的处理程序的名称，而在代码隐藏中定义实现处理程序的代码。

[!code-xaml[XAMLOvwSupport#ButtonWithCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml#buttonwithcodebehind)]

[!code-csharp[XAMLOvwSupport#ButtonWithCodeBehindHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml.cs#buttonwithcodebehindhandler)]
[!code-vb[XAMLOvwSupport#ButtonWithCodeBehindHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XAMLOvwSupport/VisualBasic/Page1.xaml.vb#buttonwithcodebehindhandler)]

请注意，代码隐藏文件使用 CLR 命名空间 `ExampleNamespace` 并将 `ExamplePage` 声明为该命名空间内的一个分部类。 这相当于 `ExampleNamespace`.`ExamplePage` 的 `x:Class` 特性值， 前者在标记根中提供。 WPF 标记编译器将通过从根元素类型派生一个类，为编译的任何 XAML 文件创建一个分部类。 当您提供定义同一部分类的代码后方时，生成的代码将合并到已编译应用的同一命名空间和类中。

有关 WPF 中代码后编程要求的详细信息，请参阅[WPF 中的代码后面、事件处理程序和部分类要求](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md#code-behind-event-handler-and-partial-class-requirements-in-wpf)。

如果不需要创建单独的代码隐藏文件，还可以将代码内联到 XAML 文件中。 但是，内联代码是一种通用性较低的方法，具有很多的限制。 有关更多信息，请参阅[WPF 中的代码背后和 XAML。](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)

### <a name="routed-events"></a>路由事件

WPF 基础的特定事件功能是路由事件。 路由事件使一个元素可以处理另一个元素引发的事件，前提是这些元素通过树关系连接在一起。 使用 XAML 特性指定事件处理时，可以对任何元素（包括未在类成员表中列出该特定事件的元素）侦听和处理该路由事件。 这是通过以所属类名限定事件名特性来实现的。 例如，`StackPanel`正在进行的`StackPanel` / `Button`示例中的父级可以通过<xref:System.Windows.Controls.Primitives.ButtonBase.Click>在`Button.Click``StackPanel`对象元素上指定属性（将处理程序名称为属性值）来注册子元素按钮事件处理程序。 有关详细信息，请参阅[路由事件概述](../../framework/wpf/advanced/routed-events-overview.md)。

## <a name="xaml-named-elements"></a>XAML 命名元素

默认情况下，通过处理 XAML 对象元素在对象图中创建的对象实例没有唯一标识符或对象引用。 相反，如果在代码中调用构造函数，则几乎总是使用构造函数结果为构造的实例设置变量，以便以后在代码中引用该实例。 为了对通过标记定义创建的对象提供标准化访问，XAML 定义了 [x:Name 特性](../xaml-services/xname-directive.md)。 可以在任何对象元素上设置 `x:Name` 特性的值。 在代码隐藏中，所选标识符等效于引用所构造的实例的实例变量。 在所有方面，命名元素的功能就像它们是对象实例（该实例的名称引用）一样，而代码隐藏可以引用命名元素来处理应用中的运行时交互。 实例和变量之间的此连接由 WPF XAML 标记编译器完成，更具体地说，涉及的功能和模式，例如<xref:System.Windows.Markup.IComponentConnector.InitializeComponent%2A>本文中不会详细讨论的功能和模式。

WPF 框架级 XAML 元素<xref:System.Windows.FrameworkElement.Name%2A>继承一个属性，该属性等效于 XAML 定义的`x:Name`属性。 其他某些类也为 `x:Name`（通常也定义为 `Name` 属性）提供属性级等效项。 一般而言，如果在所选元素/类型的成员表中找不到 `Name` 属性，则可以改用 `x:Name`。 这些`x:Name`值将为 XAML 元素提供标识符，该元素可在运行时由特定子系统或实用程序方法（如<xref:System.Windows.FrameworkElement.FindName%2A>）使用。

下面的示例在<xref:System.Windows.Controls.StackPanel>元素<xref:System.Windows.FrameworkElement.Name%2A>上设置。 <xref:System.Windows.Controls.Button>然后，在 中<xref:System.Windows.Controls.StackPanel>引用 的 上的<xref:System.Windows.Controls.StackPanel>处理程序引用`buttonContainer`<xref:System.Windows.FrameworkElement.Name%2A>

[!code-xaml[XAMLOvwSupport#NamedE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#namede)]
[!code-xaml[XAMLOvwSupport#NamedE2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#namede2)]

[!code-csharp[XAMLOvwSupport#NameCode](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml.cs#namecode)]
[!code-vb[XAMLOvwSupport#NameCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XAMLOvwSupport/VisualBasic/Page1.xaml.vb#namecode)]

和变量一样，实例的 XAML 名称受范围概念约束，因此可以在可预测的某个范围内强制名称唯一。 定义页面的主标记表示一个唯一的 XAML 名称范围，而该 XAML 名称范围的边界是该页面的根元素。 但是，其他标记源可以在运行时与页面进行交互，例如样式中的样式或模板，并且此类标记源通常有自己的 XAML 命名范围，不一定与页面的 XAML 命名范围连接。 有关`x:Name`和 XAML 名称范围的详细信息，请参阅<xref:System.Windows.FrameworkElement.Name%2A> [：x：名称指令](../xaml-services/xname-directive.md)或[WPF XAML 名称范围](../../framework/wpf/advanced/wpf-xaml-namescopes.md)。

## <a name="attached-properties-and-attached-events"></a>附加属性和附加事件

XAML 指定了一个语言功能，该功能允许对任何元素指定某些属性或事件，而不管要设置属性或事件的元素的类型定义中是否存在该属性或事件。 该功能的属性版本称为附加属性，事件版本称为附加事件。 从概念上讲，可以将附加属性和附加事件视为可以在任何 XAML 元素/对象实例上设置的全局成员。 但是，元素/类或更大的基础结构必须支持附加值的后备属性存储。

通常通过特性语法来使用 XAML 中的附加属性。 在属性语法中，在窗体`ownerType.propertyName`中指定附加属性。

从表面上看，这类似于属性元素的使用，但在这种情况下，`ownerType`您指定的始终与正在设置附加属性的对象元素类型不同。 `ownerType`是提供 XAML 处理器为获取或设置附加属性值所需的访问器方法的类型。

附加属性的最常见方案是使子元素向其父元素报告属性值。

下面的示例说明了<xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>附加的属性。 类<xref:System.Windows.Controls.DockPanel>定义访问<xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>器，因此拥有附加属性。 类<xref:System.Windows.Controls.DockPanel>还包括逻辑，用于对子元素进行重新集中，并专门检查每个元素的<xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>设定值。 如果找到一个值，将在布局过程中使用该值定位子元素。 使用<xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>附加属性和这种定位功能实际上是类的<xref:System.Windows.Controls.DockPanel>激励方案。

[!code-xaml[XAMLOvwSupport#DockAP](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#dockap)]

在 WPF 中，大多数或所有附加属性也作为依赖项属性实现。 有关详细信息，请参阅[附加属性概述](../../framework/wpf/advanced/attached-properties-overview.md)。

附加的事件使用类似的`ownerType.eventName`属性语法形式。 和非附加事件一样，XAML 中附加事件的特性值指定对元素处理事件时调用的处理程序方法的名称。 在 WPF XAML 中使用附加事件并不常见。 有关详细信息，请参阅[附加事件概述](../../framework/wpf/advanced/attached-events-overview.md)。

## <a name="base-types-and-xaml"></a>基类型和 XAML

基础 WPF XAML 及其 XAML 命名空间是对应于 CLR 对象的类型的集合，此外还有 XAML 的标记元素。 但是，并不是所有的类都能映射到元素。 抽象类（如<xref:System.Windows.Controls.Primitives.ButtonBase>）和某些非抽象基类用于 CLR 对象模型中的继承。 基类（包括抽象类）对于 XAML 开发仍然很重要，因为每个具体的 XAML 元素都从其层次结构中的某个基类继承成员。 通常，这些成员包括可以设置为元素特性的属性或者可以处理的事件。 <xref:System.Windows.FrameworkElement>是 WPF 框架级别 WPF 的具体基础 UI 类。 设计 UI 时，将使用各种形状、面板、修饰器或控件类，这些类都派生自<xref:System.Windows.FrameworkElement>。 相关的基类<xref:System.Windows.FrameworkContentElement>支持适用于流布局表示的文档元素，使用有意镜像 中的<xref:System.Windows.FrameworkElement>API 的 API。 元素级别的属性和 CLR 对象模型的组合为您提供了一组公共属性，这些属性在大多数具体的 XAML 元素上是可设置的，而不考虑特定的 XAML 元素及其基础类型。

## <a name="xaml-security"></a>XAML 安全性

XAML 是一种直接表示对象实例化和执行的标记语言。 因此，在 XAML 中创建的元素能够像等效的生成代码那样与系统资源（如网络访问、文件系统 IO）进行交互。 加载到完全受信任的应用中的 XAML 对系统资源的访问与托管应用相同。

### <a name="code-access-security-cas-in-wpf"></a>WPF 中的代码访问安全 （CAS）

**本节仅适用于 .NET 框架。.NET 核心的 WPF 不支持 CAS。有关详细信息，请参阅[代码访问安全差异](../migration/differences-from-net-framework.md#code-access-security)。**

.NET 框架的 WPF 支持代码访问安全性 （CAS）。 这意味着在 Internet 区域中运行的 WPF 内容已减少执行权限。 "Loose XAML"（未编译的 XAML 页面由 XAML 查看器在加载时解释）和 XBAP 通常在此 Internet 区域中运行，并使用相同的权限集。 但是，加载到完全受信任的应用程序中的 XAML 与承载应用程序具有相同的系统资源访问权限。 有关详细信息，请参阅[WPF 部分信任安全](../../framework/wpf/wpf-partial-trust-security.md)。

## <a name="loading-xaml-from-code"></a>从代码加载 XAML

XAML 可用于定义整个 UI，但有时也适合在 XAML 中定义一部分 UI。 此功能可用于实现部分自定义、在本地存储信息，使用 XAML 提供业务对象或者各种可能的方案。 这些方案的关键是<xref:System.Windows.Markup.XamlReader>类及其<xref:System.Windows.Markup.XamlReader.Load%2A>方法。 输入是 XAML 文件，而输出是对象，该对象表示从该标记创建的整个运行时对象树。 然后，可以将该对象插入为应用中已存在的另一个对象的属性。 只要该属性是内容模型中具有最终显示功能的适当属性，并且该属性将通知执行引擎新内容已添加到应用中，则可以通过在 XAML 中加载轻松修改正在运行的应用的内容。 对于 .NET Framework，此功能通常仅在完全信任应用程序中可用，因为在文件运行时将文件加载到应用程序中具有明显的安全影响。

## <a name="see-also"></a>请参阅

- [XAML 语法详述](../../framework/wpf/advanced/xaml-syntax-in-detail.md)
- [XAML 及 WPF 的自定义类](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [XAML 命名空间 (x:)语言功能](../xaml-services/namespace-language-features.md)
- [WPF XAML 扩展](../../framework/wpf/advanced/wpf-xaml-extensions.md)
- [基元素概述](../../framework/wpf/advanced/base-elements-overview.md)
- [WPF 中的树](../../framework/wpf/advanced/trees-in-wpf.md)
