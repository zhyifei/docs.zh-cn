---
title: 定义 XAML 资源
description: 了解 WPF 中用于 .NET 核心的 XAML 资源。 了解 XAML 资源的类型，并了解如何定义 XAML 资源。
author: thraka
ms.author: adegeo
ms.date: 08/21/2019
ms.openlocfilehash: b278bb92afc308578d60e347871e0150b26a95db
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/31/2019
ms.locfileid: "81432568"
---
# <a name="overview-of-xaml-resources"></a>XAML 资源概述

资源是可在应用中不同位置重复使用的对象。 资源的示例包括画笔和样式。 本概述介绍如何在可扩展应用程序标记语言 （XAML） 中使用资源。 您还可以使用代码创建和访问资源。

> [!NOTE]
> 本文中描述的 XAML 资源与通常添加到*应用的应用资源*（如内容、数据或嵌入文件）不同。

<!-- TODO: File redirect from docs\framework\wpf\advanced\xaml-resources.md -->

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="using-resources-in-xaml"></a>使用 XAML 中的资源

下面的示例将 a<xref:System.Windows.Media.SolidColorBrush>定义为页面根元素上的资源。 然后，该示例引用资源，并用它来设置多个子元素的属性，包括 . <xref:System.Windows.Shapes.Ellipse>a<xref:System.Windows.Controls.TextBlock>和 。 <xref:System.Windows.Controls.Button>

[!code-xaml[FEResourceSH_snip#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xaml)]

每个框架级元素 （<xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement>或 ）<xref:System.Windows.FrameworkElement.Resources%2A>都有一个属性<xref:System.Windows.ResourceDictionary>，该属性是包含已定义资源的类型。 可以定义任何元素（如 ）<xref:System.Windows.Controls.Button>上的资源。 但是，资源最常在根元素上定义，该元素在<xref:System.Windows.Controls.Page>示例中。

资源字典中的每个资源都必须具有唯一键。 在标记中定义资源时，可以通过[x：Key 指令](../xaml-services/xkey-directive.md)分配唯一键。 通常情况下，这个键是一个字符串；但是，也可使用相应的标记扩展将其设置为其他对象类型。 WPF 中的某些要素区域（尤其是样式、组件资源和数据样式）使用资源的非字符串键。

可以将定义的资源与指定资源键名称的资源标记扩展语法一起使用。 例如，将资源用作另一个元素上属性的值。

[!code-xaml[FEResourceSH_snip#KeyNameUsage](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#keynameusage)]

在前面的示例中，当 XAML 加载程序处理`{StaticResource MyBrush}`属性的值<xref:System.Windows.Controls.Control.Background%2A>时<xref:System.Windows.Controls.Button>，资源查找逻辑首先检查<xref:System.Windows.Controls.Button>元素的资源字典。 如果没有<xref:System.Windows.Controls.Button>资源键`MyBrush`的定义（在此示例中没有;其资源集合为空），则下一个查找将检查 的<xref:System.Windows.Controls.Button>父元素，该元素为<xref:System.Windows.Controls.Page>。 如果在<xref:System.Windows.Controls.Page>根元素上定义资源，则 的逻辑<xref:System.Windows.Controls.Page>树中的所有元素都可以访问它。 您可以重用同一资源来设置接受资源表示的相同类型的任何属性的值。 在前面`MyBrush`的示例中，同一<xref:System.Windows.Controls.Control.Background%2A><xref:System.Windows.Controls.Button><xref:System.Windows.Shapes.Shape.Fill%2A>资源设置两个不同的属性：的 和 。 <xref:System.Windows.Shapes.Rectangle>

## <a name="static-and-dynamic-resources"></a>静态和动态资源

可以将资源引用为静态或动态。 引用是通过使用[静态资源标记扩展](../../framework/wpf/advanced/staticresource-markup-extension.md)或[动态资源标记扩展](../../framework/wpf/advanced/dynamicresource-markup-extension.md)创建的。 标记扩展是一种 XAML 功能，允许您通过让标记扩展处理属性字符串并将对象返回到 XAML 加载程序来指定对象引用。 有关标记扩展行为的详细信息，请参阅[标记扩展和 WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)。

使用标记扩展时，通常以字符串形式提供由该特定标记扩展处理的一个或多个参数。 [静态资源标记扩展](../../framework/wpf/advanced/staticresource-markup-extension.md)通过查找所有可用资源字典中该键的值来处理密钥。 处理发生在加载期间，即加载过程需要分配属性值时。 [动态资源标记扩展](../../framework/wpf/advanced/dynamicresource-markup-extension.md)通过创建表达式处理键，该表达式在应用运行之前保持未计算状态，此时将计算表达式并提供值。

在引用某个资源时，下列注意事项可能会对于使用静态资源引用还是使用动态资源引用产生影响：

- 在确定如何为应用创建资源的总体设计时（每页、应用中、松散 XAML 或仅资源程序集中），请考虑以下事项：

- 应用的功能。 更新资源是应用需求的实时部分吗？
- 该资源引用类型的相应查找行为。
- 特定的属性或资源类型，以及这些类型的本机行为。

## <a name="static-resources"></a>静态资源

在以下情况下，最适合使用静态资源引用：

- 应用设计将其大部分资源集中到页面或应用程序级资源字典中。 静态资源引用不会根据运行时行为（如重新加载页面）重新评估。 因此，在不需要基于您的资源和应用设计时，避免大量动态资源引用，可能会带来一些性能优势。

- 正在设置不在<xref:System.Windows.DependencyObject>或 上的属性的值。 <xref:System.Windows.Freezable>

- 您正在创建一个资源字典，该字典将编译到 DLL 中，并打包为应用的一部分或在应用之间共享。

- 您正在为自定义控件创建主题，并定义主题中使用的资源。 在这种情况下，您通常不希望动态资源引用查找行为;因此，您不希望出现动态资源引用查找行为。相反，您希望静态资源引用行为，以便查找是可预测和自包含的主题。 使用动态资源引用时，即使主题中的引用在运行时之前都处于未计算。 应用主题时，一些局部元素可能会重新定义主题尝试引用的键，并且本地元素将落在查找中的主题本身之前。 如果发生这种情况，您的主题将不按预期进行。

- 您正在使用资源来设置大量依赖项属性。 依赖项属性具有属性系统启用的有效值缓存，因此，如果为可在加载时计算的依赖项属性提供值，则依赖项属性不必检查重新评估的表达式，并可以返回最后一个有效值。 此项技术可以提高性能。

- 您希望更改所有使用者的基础资源，或者希望使用[x：共享属性](../xaml-services/xshared-attribute.md)为每个使用者维护单独的可写实例。

### <a name="static-resource-lookup-behavior"></a>静态资源查找行为

下面描述了当属性或元素引用静态资源时自动发生的查找过程：

01. 查找进程在用于设置属性的元素所定义的资源字典中查找请求的键。

01. 然后，查找过程向上遍历逻辑树到父元素及其资源字典。 此过程将继续，直到到达根元素。

01. 检查应用资源。 应用资源是资源字典中由 WPF 应用<xref:System.Windows.Application>的对象定义的资源资源。

从资源字典中进行的静态资源引用必须引用已在资源引用前进行过词法定义的资源。 静态资源引用无法解析前向引用。 因此，请设计资源字典结构，以便在每个资源字典的开头或附近定义资源。

静态资源查找可以扩展到主题或系统资源，但仅支持此查找，因为 XAML 加载程序延迟请求。 延迟是必需的，以便页面加载时运行时主题正确应用于应用。 但是，不建议对已知仅存在于主题或系统资源中的键进行静态资源引用，因为如果用户实时更改主题，则不会重新评估此类引用。 请求主题或系统资源时，动态资源引用更为可靠。 例外情况是当主题元素自身请求另一个资源。 出于上述原因，这些引用应该是静态资源引用。

如果未找到静态资源引用，则异常行为会有所不同。 如果资源被延迟，则异常会在运行时发生。 如果资源未延迟，则异常会在加载时发生。

## <a name="dynamic-resources"></a>动态资源

动态资源在：

- 资源的值（包括系统资源或其他用户可设置的资源）取决于在运行时之前不知道的条件。 例如，您可以创建 setter 值，这些值引用由 或 公开<xref:System.Windows.SystemColors><xref:System.Windows.SystemFonts>的系统属性<xref:System.Windows.SystemParameters>。 这些值是真正的动态值，因为它们最终来自用户和操作系统的运行时环境。 或许还拥有可能会发生变化的应用程序级主题，而页面级资源访问也必须捕获其中的变化。

- 您正在为自定义控件创建或引用主题样式。

- 您打算在应用生存期内调整<xref:System.Windows.ResourceDictionary>的内容。

- 拥有存在相互依赖关系且可能需要进行前向引用的复杂资源结构。 静态资源引用不支持转发引用，但动态资源引用确实支持它们，因为在运行时之前不需要计算资源，因此转发引用不是相关概念。

- 从编译或工作集的角度来看，您引用的是较大的资源，并且在页面加载时可能不会立即使用该资源。 当页面加载时，静态资源引用始终从 XAML 加载。 但是，动态资源引用在使用之前不会加载。

- 您正在创建一种样式，其中 setter 值可能来自受主题或其他用户设置影响的其他值。

- 正在将资源应用于在应用生存期内可能重新父化逻辑树中的元素。 父级更改后，资源查找范围也可能会随之更改；因此，如果希望重定父级的元素的资源基于新范围重新进行计算，请始终使用动态资源引用。

### <a name="dynamic-resource-lookup-behavior"></a>动态资源查找行为

动态资源引用的资源查找行为与代码中的查找行为平行，如果调用<xref:System.Windows.FrameworkElement.FindResource%2A>或<xref:System.Windows.FrameworkElement.SetResourceReference%2A>调用 ：

01. 查找检查由设置属性的元素定义的资源字典中请求的密钥：

    - 如果元素定义属性<xref:System.Windows.FrameworkElement.Style%2A>，则元素的<xref:System.Windows.FrameworkElement.Style?displayProperty=fullName>字典已<xref:System.Windows.Style.Resources>选中。

    - 如果元素定义属性<xref:System.Windows.Controls.Control.Template%2A>，<xref:System.Windows.FrameworkTemplate.Resources?displayProperty=fullName>则检查元素的字典。

01. 查找将逻辑树向上遍历父元素及其资源字典。 此过程将继续，直到到达根元素。

01. 检查应用资源。 应用资源是资源字典中由 WPF 应用<xref:System.Windows.Application>的对象定义的资源资源。

01. 检查主题资源字典以检查当前活动的主题。 如果主题在运行时发生更改，则会重新计算值。

01. 检查系统资源。

异常行为（如果有）各不相同：

- 如果<xref:System.Windows.FrameworkElement.FindResource%2A>调用请求了资源，但未找到资源，则引发异常。

- 如果<xref:System.Windows.FrameworkElement.TryFindResource%2A>调用请求了资源，但未找到资源，则不会引发异常，返回的值为`null`。 如果正在设置的属性不接受`null`，则仍可能引发更深的异常，具体取决于要设置的单个属性。

- 如果 XAML 中的动态资源引用请求了资源，但未找到资源，则该行为取决于常规属性系统。 一般行为就好像在资源所在的级别上没有发生属性设置操作一样。 例如，如果您尝试使用无法计算的资源在单个按钮元素上设置背景，则没有值设置结果，但有效值仍可能来自属性系统和值优先级中的其他参与者。 例如，背景值可能仍来自本地定义的按钮样式或主题样式。 对于主题样式未定义的属性，失败的资源计算后的有效值可能来自属性元数据中的默认值。

### <a name="restrictions"></a>限制

动态资源引用存在一些重要限制。 以下条件之一必须至少为 true：

- 正在设置的属性必须是<xref:System.Windows.FrameworkElement>或<xref:System.Windows.FrameworkContentElement>上的属性。 该属性必须由 的支持<xref:System.Windows.DependencyProperty>。

- 引用是 针对 中的值。 `StyleSetter`

- 正在<xref:System.Windows.Freezable>设置的属性必须是作为 或<xref:System.Windows.FrameworkElement><xref:System.Windows.FrameworkContentElement>属性的值提供的属性或<xref:System.Windows.Setter>值。

由于正在设置的属性必须是 或<xref:System.Windows.DependencyProperty><xref:System.Windows.Freezable>属性，因此大多数属性更改可以传播到 UI，因为属性系统确认属性更改（更改的动态资源值）。 大多数控件都包含逻辑，如果更改和该属性可能会影响布局，<xref:System.Windows.DependencyProperty>则该逻辑将强制控件的另一个布局。 但是，并非所有具有[动态资源标记扩展](../../framework/wpf/advanced/dynamicresource-markup-extension.md)的属性（其值）都保证在 UI 中提供实时更新。 该功能可能仍因属性而异，具体取决于拥有属性的类型，甚至应用的逻辑结构。

## <a name="styles-datatemplates-and-implicit-keys"></a>样式、数据模板和隐式键

尽管 中的所有<xref:System.Windows.ResourceDictionary>项都必须具有键，但这并不意味着所有资源都必须具有显式`x:Key`。 多种对象类型在定义为资源时都支持隐式键，其键值会与另一属性的值绑定。 这种类型的键称为隐式键，而`x:Key`属性是显式键。 任何隐式键都可通过指定显式键来覆盖。

资源的一个重要方案是定义 时<xref:System.Windows.Style>。 事实上，在资源<xref:System.Windows.Style>字典中，几乎总是定义为条目，因为样式本质上是要重用的。 有关样式的详细信息，请参阅[样式和模板](styles-templates-overview.md)化。

控件样式可通过隐式键来创建和引用。 用于定义控件默认外观的主题样式依赖于该隐式键。 从请求的角度来看，隐式键是<xref:System.Type>控件本身。 从定义资源的角度来看，隐式键是<xref:System.Windows.Style.TargetType%2A>样式的。 因此，如果要为自定义控件创建主题或创建与现有主题样式交互的样式，则无需为此<xref:System.Windows.Style>指定[x：Key 指令](../xaml-services/xkey-directive.md)。 另外，如果想要使用主题样式，则根本无需指定任何样式。 例如，以下样式定义有效，即使<xref:System.Windows.Style>资源似乎没有密钥：

[!code-xaml[FEResourceSH_snip#ImplicitStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#implicitstyle)]

这种风格确实有一个键：隐式键`typeof(System.Windows.Controls.Button)`。 在标记中，可以直接指定类型<xref:System.Windows.Style.TargetType%2A>名称（也可以选择使用[{x：Type...]](../xaml-services/xtype-markup-extension.md) 返回 。 <xref:System.Type>

通过 WPF 使用的默认主题样式机制，该样式将应用于页面上的 运行时<xref:System.Windows.Controls.Button>样式，即使<xref:System.Windows.Controls.Button>本身不尝试指定其<xref:System.Windows.FrameworkElement.Style%2A>属性或对该样式的特定资源引用。 在页面中定义的样式在查找序列中早于主题字典样式中找到，使用主题词典样式具有的相同键。 您可以只指定`<Button>Hello</Button>`页面中的任意位置，并且您<xref:System.Windows.Style.TargetType%2A>定义的样式`Button`将应用于该按钮。 如果需要，您仍然可以显式键入样式，其类型值与<xref:System.Windows.Style.TargetType%2A>标记中的明确性相同，但这是可选的。

如果<xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A>是`true`，则样式的隐式键不适用于控件。 （另请注意，<xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A>可能设置为控件类的本机行为的一部分，而不是在控件的实例上显式设置。此外，为了支持派生类方案的隐式键，控件必须重写<xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>（作为 WPF 的一部分提供的所有现有控件都包括此覆盖）。 有关样式、主题和控制设计的详细信息，请参阅[设计可手写控件的指南](../../framework/wpf/controls/guidelines-for-designing-stylable-controls.md)。

<xref:System.Windows.DataTemplate>也有一个隐式键。 的隐式键<xref:System.Windows.DataTemplate>是<xref:System.Windows.DataTemplate.DataType%2A>属性值。 <xref:System.Windows.DataTemplate.DataType%2A>也可以指定为类型的名称，而不是显式使用[[x：Type...]](../xaml-services/xtype-markup-extension.md)。 有关详细信息，请参阅[数据模板概述](../../framework/wpf/data/data-templating-overview.md)。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.ResourceDictionary>
- [应用程序资源](../../framework/wpf/advanced/optimizing-performance-application-resources.md)
- [资源和代码](../../framework/wpf/advanced/resources-and-code.md)
- [定义和引用资源](../../framework/wpf/advanced/how-to-define-and-reference-a-resource.md)
- [应用程序管理概述](../../framework/wpf/app-development/application-management-overview.md)
- [x：键入标记扩展](../xaml-services/xtype-markup-extension.md)
- [静态资源标记扩展](../../framework/wpf/advanced/staticresource-markup-extension.md)
- [动态资源标记扩展](../../framework/wpf/advanced/dynamicresource-markup-extension.md)
