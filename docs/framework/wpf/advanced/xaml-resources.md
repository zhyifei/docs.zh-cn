---
title: XAML 资源
ms.date: 03/30/2017
helpviewer_keywords:
- reusing resources [WPF]
- resources [WPF], reusing
- reusing commonly defined objects [WPF]
- XAML [WPF], reusing resources
ms.assetid: 91580b89-a0a8-4889-aecb-fddf8e63175f
ms.openlocfilehash: 738a4f397b1677b867126c7bb439b027f951baa0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958817"
---
# <a name="xaml-resources"></a>XAML 资源
资源是可以在应用程序中的不同位置重复使用的对象。 资源的示例包括画笔和样式。 本概述介绍如何使用中的[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]资源。 你还可以使用代码创建和访问资源, 或者在代码和[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]之间交换。 有关详细信息, 请参阅[资源和代码](resources-and-code.md)。  
  
> [!NOTE]
> 本主题中所述的资源文件不同于[WPF 应用程序资源、内容和数据文件](../app-development/wpf-application-resource-content-and-data-files.md)中所述的资源文件, 与[管理应用程序资源 (.net) 中所述的嵌入或链接的资源不同](/visualstudio/ide/managing-application-resources-dotnet)。  

<a name="usingresources"></a>   
## <a name="using-resources-in-xaml"></a>在 XAML 中使用资源  
 下面的示例将定义<xref:System.Windows.Media.SolidColorBrush>为页面根元素上的资源。 然后, 该示例引用资源并使用它来设置多个子元素的属性, 包括<xref:System.Windows.Shapes.Ellipse> <xref:System.Windows.Controls.TextBlock>、和<xref:System.Windows.Controls.Button>。  
  
 [!code-xaml[FEResourceSH_snip#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xaml)]  
  
 每个框架级别的元素<xref:System.Windows.FrameworkElement> ( <xref:System.Windows.FrameworkContentElement>或) 都<xref:System.Windows.FrameworkElement.Resources%2A>有一个属性, 该属性包含资源定义的资源 (作为<xref:System.Windows.ResourceDictionary>)。 您可以在任意元素上定义资源。 但是, 资源通常是在根元素上定义的, <xref:System.Windows.Controls.Page>该元素在示例中。  
  
 资源字典中的每个资源都必须具有唯一键。 在标记中定义资源时, 可以通过[X:Key 指令](../../xaml-services/x-key-directive.md)分配唯一键。 通常情况下，这个键是一个字符串；但是，也可使用相应的标记扩展将其设置为其他对象类型。 资源的非字符串项用于中[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的某些功能区, 特别是对于样式、组件资源和数据样式。  
  
 在定义好资源后，可以使用能够指定键名称的资源标记扩展语法来引用该资源以用于属性值，例如：  
  
 [!code-xaml[FEResourceSH_snip#KeyNameUsage](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#keynameusage)]  
  
 在前面的示例中, 当[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]加载程序处理上`{StaticResource MyBrush}` <xref:System.Windows.Controls.Button>的<xref:System.Windows.Controls.Control.Background%2A>属性的值时, 资源查找逻辑首先检查<xref:System.Windows.Controls.Button>元素的资源字典。 如果<xref:System.Windows.Controls.Button>没有资源键`MyBrush`的定义 (不是, 它的资源集合为空), 则查找将在下一步<xref:System.Windows.Controls.Button>检查的父<xref:System.Windows.Controls.Page>元素, 即。 因此, 当你在<xref:System.Windows.Controls.Page>根元素上定义资源时, 的<xref:System.Windows.Controls.Page>逻辑树中的所有元素都可以访问它, 并且你可以重复使用同一资源来设置<xref:System.Type>任何接受该资源的属性的值。表示. 在上面的示例中, 同一`MyBrush`资源设置了两个不同的<xref:System.Windows.Controls.Control.Background%2A>属性: <xref:System.Windows.Controls.Button>的和<xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Rectangle>的。  
  
<a name="staticdynamic"></a>   
## <a name="static-and-dynamic-resources"></a>静态和动态资源  
 资源可以作为静态资源或动态资源加以引用。 这可以通过使用[StaticResource 标记扩展](staticresource-markup-extension.md)或[DynamicResource 标记扩展](dynamicresource-markup-extension.md)来完成。 标记扩展是一项功能, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]通过该功能, 您可以通过使标记扩展处理属性字符串并将对象返回[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]到加载程序来指定对象引用。 有关标记扩展行为的详细信息, 请参阅[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。  
  
 当使用标记扩展时，通常会以字符串的形式提供一个或多个参数，这些参数由该特定标记扩展来处理，而不是在所设置属性的上下文中进行计算。 [StaticResource 标记扩展](staticresource-markup-extension.md)通过在所有可用资源字典中查找该密钥的值来处理该键。 这个操作会在加载期间执行；执行时，加载进程需要分配采用静态资源引用的属性值。 [DynamicResource 标记扩展](dynamicresource-markup-extension.md)改为通过创建表达式来处理键, 并且该表达式保持未计算状态, 直到应用程序实际运行, 此时将计算表达式并提供一个值。  
  
 在引用某个资源时，下列注意事项可能会对于使用静态资源引用还是使用动态资源引用产生影响：  
  
- 如何为应用程序创建资源的整体设计 (每页, 应用程序[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]中的资源, 在仅资源的程序集中)。  
  
- 应用程序的功能：实时更新资源是应用程序的要求之一吗?  
  
- 该资源引用类型的相应查找行为。  
  
- 特定的属性或资源类型，以及这些类型的本机行为。  
  
### <a name="static-resources"></a>静态资源  
 在以下情况下，最适合使用静态资源引用：  
  
- 所采用的应用程序设计将其所含的大多数资源都集中到了页面级或应用程序级资源字典中。 静态资源引用不会基于运行时行为（如重载页面）重新进行计算，因此可以通过以下方式在一定程度上提高性能：当资源和所采用的应用程序设计无需使用大量动态资源引用时，就避免使用。  
  
- 你正在设置不在<xref:System.Windows.DependencyObject> <xref:System.Windows.Freezable>或上的属性的值。  
  
- 正在创建的资源字典将编译成 DLL，并将打包为应用程序的一部分或在应用程序间共享。  
  
- 正在为自定义控件创建主题，并定义要在主题中使用的资源。 在这种情况下，通常不希望执行动态资源引用查找行为，而是希望执行静态资源引用行为，以确保查找可预测且自包含到主题中。 使用动态资源引用时，即使主题中的引用会保持未计算状态直至运行时，且主题可能会得到应用，但某个本地元素仍会重新定义主题正尝试引用的键，并且该本地元素在查找期间会排在主题前面。 如果发生这种情况，主题的行为将偏离预期方式。  
  
- 正在使用资源设置大量依赖属性。 依赖属性会通过属性系统启用有效值缓存功能；因此，如果为可在加载时进行计算的依赖属性提供了值，则该依赖属性不必检查是否存在重新计算的表达式并可返回上一个有效值。 此项技术可以提高性能。  
  
- 你需要更改所有使用者的基础资源, 或者想要使用[X:Shared 属性](../../xaml-services/x-shared-attribute.md)为每个使用者维护单独的可写实例。  
  
#### <a name="static-resource-lookup-behavior"></a>静态资源查找行为  
  
1. 查找进程在用于设置属性的元素所定义的资源字典中查找请求的键。  
  
2. 查找进程随后会向上遍历逻辑树，以查找父元素及其资源字典。 直至到达根元素，遍历操作才会停止。  
  
3. 接下来，将检查应用程序资源。 应用程序资源是资源字典中的资源, 由<xref:System.Windows.Application> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序的对象定义。  
  
 从资源字典中进行的静态资源引用必须引用已在资源引用前进行过词法定义的资源。 静态资源引用无法解析前向引用。 因此，如果使用静态资源引用，则必须对资源字典的结构进行设计，以便在每个相应资源字典的开头或临近位置定义要按资源使用的资源。  
  
 静态资源查找可以扩展到主题或系统资源中, 但这种情况仅受支持, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]因为加载程序会延迟请求。 为了让页面加载时的运行时主题正确地应用至该应用程序，这种延迟是必需的。 但是，如果某些键已知仅存在于主题中或属于系统资源，则建议不要使用针对这类键的静态资源引用。 这是因为如果用户实时更改主题，此类引用不会重新计算。 请求主题或系统资源时，动态资源引用更为可靠。 例外情况是当主题元素自身请求另一个资源。 出于上述原因，这些引用应该是静态资源引用。  
  
 因找不到静态资源引用而引发的异常行为各不相同。 如果资源被延迟，则异常会在运行时发生。 如果资源未延迟，则异常会在加载时发生。  
  
### <a name="dynamic-resources"></a>动态资源  
 在以下情况下，最适合使用动态资源：  
  
- 资源的值取决于直到运行时才能获悉的条件。 这包括系统资源或用户可设置的资源。 例如, 你可以创建引用系统属性的 setter 值, 如<xref:System.Windows.SystemColors>、 <xref:System.Windows.SystemFonts>或<xref:System.Windows.SystemParameters>公开。 这些值是真正的动态值，因为它们最终来自用户和操作系统的运行时环境。 或许还拥有可能会发生变化的应用程序级主题，而页面级资源访问也必须捕获其中的变化。  
  
- 正在为自定义控件创建或引用主题样式。  
  
- 你打算<xref:System.Windows.ResourceDictionary>在应用程序生存期内调整的内容。  
  
- 拥有存在相互依赖关系且可能需要进行前向引用的复杂资源结构。 静态资源引用不支持正向引用, 但动态资源引用支持这些引用, 因为在运行时之前不需要计算资源, 而向前引用则不是相关的概念。  
  
- 从编译或工作集的角度来看，所引用的资源特别大，而且该资源在页面加载时可能不会立即使用。 静态资源引用总是在页面[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]加载时从加载; 但是, 在实际使用动态资源引用之前, 不会加载它。  
  
- 所创建样式中的 Setter 值可能来自受主题或其他用户设置影响的其他值。  
  
- 正在将资源应用于可能会在应用程序生存期内在逻辑树中重定父级的元素。 父级更改后，资源查找范围也可能会随之更改；因此，如果希望重定父级的元素的资源基于新范围重新进行计算，请始终使用动态资源引用。  
  
#### <a name="dynamic-resource-lookup-behavior"></a>动态资源查找行为  
 如果调用<xref:System.Windows.FrameworkElement.FindResource%2A>或<xref:System.Windows.FrameworkElement.SetResourceReference%2A>, 动态资源引用的资源查找行为会与代码中的查找行为相似。  
  
1. 查找进程在用于设置属性的元素所定义的资源字典中查找请求的键。  
  
    - 如果元素定义<xref:System.Windows.FrameworkElement.Style%2A>属性<xref:System.Windows.Style.Resources%2A> , 则将检查中<xref:System.Windows.Style>的字典。  
  
    - 如果元素定义<xref:System.Windows.Controls.Control.Template%2A>属性<xref:System.Windows.FrameworkTemplate.Resources%2A> , 则将检查中<xref:System.Windows.FrameworkTemplate>的字典。  
  
2. 查找进程随后会向上遍历逻辑树，以查找父元素及其资源字典。 直至到达根元素，遍历操作才会停止。  
  
3. 接下来，将检查应用程序资源。 应用程序资源是资源字典中的资源, 由<xref:System.Windows.Application> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序的对象定义。  
  
4. 在主题资源字典中查找当前处于活动状态的主题。 如果主题在运行时发生更改，则会重新计算值。  
  
5. 检查系统资源。  
  
 异常行为（如果有）各不相同：  
  
- 如果<xref:System.Windows.FrameworkElement.FindResource%2A>调用请求了资源, 但找不到该资源, 则会引发异常。  
  
- 如果<xref:System.Windows.FrameworkElement.TryFindResource%2A>调用请求了资源, 但找不到该资源, 则不会引发异常, 但返回的值为`null`。 如果要设置的属性不接受`null`, 则仍可能会引发更深的异常 (这取决于所设置的单个属性)。  
  
- 如果中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]的动态资源引用请求了某个资源, 但找不到该资源, 则该行为取决于常规属性系统, 但常规行为就如同在该资源所在的级别未发生任何属性设置操作一样。 例如，如果尝试使用无法计算的资源来设置个别按钮元素上的背景，则值设置操作不会产生任何结果，但是有效的值可能仍来自属性系统和值优先级中的其他参与者。 例如，背景值可能仍来自在本地定义的某个按钮样式，或来自主题样式。 对于并非由主题样式定义的属性，资源计算失败后的有效值可能来自属性元数据中的默认值。  
  
#### <a name="restrictions"></a>限制  
 动态资源引用存在一些重要限制。 必须至少满足以下条件之一：  
  
- 要设置的属性必须是<xref:System.Windows.FrameworkElement>或<xref:System.Windows.FrameworkContentElement>的属性。 该属性必须由<xref:System.Windows.DependencyProperty>支持。  
  
- 引用适用于中<xref:System.Windows.Style> <xref:System.Windows.Setter>的值。  
  
- 要设置的属性必须是的属性<xref:System.Windows.Freezable> , 该属性是作为<xref:System.Windows.FrameworkElement> <xref:System.Windows.Setter>或<xref:System.Windows.FrameworkContentElement>属性或值的值提供的。  
  
 由于所设置的属性必须是<xref:System.Windows.DependencyProperty>或<xref:System.Windows.Freezable>属性, 因此大多数属性更改都可以传播给 UI, 因为属性更改 (更改的动态资源值) 由属性系统确认。 大多数控件都包含逻辑, 该逻辑将强制控件的另一<xref:System.Windows.DependencyProperty>布局 (如果更改和该属性可能影响布局)。 但是, 并不是所有将[DynamicResource 标记扩展](dynamicresource-markup-extension.md)作为其值的属性都能以用户在 UI 中实时更新的方式提供值。 此功能可能仍会因属性、属性所属的类型，甚至因应用程序的逻辑结果而异。  
  
<a name="stylesimplicitkeys"></a>   
## <a name="styles-datatemplates-and-implicit-keys"></a>样式、数据模板和隐式键  
 之前, 声明中<xref:System.Windows.ResourceDictionary>的所有项都必须有一个键。 但是, 这并不意味着所有资源都必须具有显式`x:Key`的。 多种对象类型在定义为资源时都支持隐式键，其键值会与另一属性的值绑定。 这称为隐式键, 而`x:Key`属性是显式键。 任何隐式键都可通过指定显式键来覆盖。  
  
 资源的一个非常重要的方案是在定义<xref:System.Windows.Style>。 事实上, <xref:System.Windows.Style>几乎总是在资源字典中定义为项, 因为样式原本就是用于重用。 有关样式的详细信息, 请参阅样式[设置和模板化](../controls/styling-and-templating.md)。  
  
 控件样式可通过隐式键来创建和引用。 用于定义控件默认外观的主题样式依赖于该隐式键。 从请求角度来看, 隐式键是<xref:System.Type>控件本身的。 自定义资源的角度来看, 隐式键是<xref:System.Windows.Style.TargetType%2A>样式的。 因此, 如果要为自定义控件创建主题, 创建与现有主题样式交互的样式, 则无需为其指定[X:Key 指令](../../xaml-services/x-key-directive.md) <xref:System.Windows.Style>。 另外，如果想要使用主题样式，则根本无需指定任何样式。 例如, 即使<xref:System.Windows.Style>资源看上去没有键, 以下样式定义仍有效:  
  
 [!code-xaml[FEResourceSH_snip#ImplicitStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#implicitstyle)]  
  
 该样式实际上有一个键: 隐式键`typeof(`。 <xref:System.Windows.Controls.Button> `)` 在标记中, 可以指定<xref:System.Windows.Style.TargetType%2A>直接作为类型名称 (或者可以选择使用[{x:Type...}](../../xaml-services/x-type-markup-extension.md) 若为, <xref:System.Type>则返回。  
  
 通过使用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的默认主题样式机制, 将样式作为<xref:System.Windows.Controls.Button>页面<xref:System.Windows.Controls.Button>上的的运行时样式应用, 即使本身不尝试指定其<xref:System.Windows.FrameworkElement.Style%2A>属性或特定资源对样式的引用。 在此页中定义的样式在查找序列中与主题字典样式具有的相同键一样, 在查找序列中找到。 只需在页面`<Button>Hello</Button>`的任何位置指定, `Button`使用<xref:System.Windows.Style.TargetType%2A>定义的样式将应用于该按钮。 如果需要, 仍可以用与相同的类型值<xref:System.Windows.Style.TargetType%2A>显式为样式的键, 这是一个可选的。  
  
 如果<xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A>为, 则`true`样式的隐式键不适用于控件 (另请注意<xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> , 可能设置为控件类的本机行为的一部分, 而不是显式地在控件实例上)。 此外, 为了支持派生类方案的隐式键, 控件必须重写<xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> (作为的一部分提供的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]所有现有控件)。 有关样式、主题和控件设计的详细信息, 请参阅[设计准则控件的准则](../controls/guidelines-for-designing-stylable-controls.md)。  
  
 <xref:System.Windows.DataTemplate>还具有一个隐式键。 的隐式键<xref:System.Windows.DataTemplate> <xref:System.Windows.DataTemplate.DataType%2A>是属性值。 <xref:System.Windows.DataTemplate.DataType%2A>还可以指定为类型的名称, 而不是使用[{x:Type...}](../../xaml-services/x-type-markup-extension.md)显式指定。 有关详细信息, 请参阅[数据模板化概述](../data/data-templating-overview.md)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.ResourceDictionary>
- [应用程序资源](optimizing-performance-application-resources.md)
- [资源和代码](resources-and-code.md)
- [定义和引用资源](how-to-define-and-reference-a-resource.md)
- [应用程序管理概述](../app-development/application-management-overview.md)
- [x:Type 标记扩展](../../xaml-services/x-type-markup-extension.md)
- [StaticResource 标记扩展](staticresource-markup-extension.md)
- [DynamicResource 标记扩展](dynamicresource-markup-extension.md)
