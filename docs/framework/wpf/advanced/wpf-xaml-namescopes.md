---
title: XAML 名称范围
ms.date: 03/30/2017
helpviewer_keywords:
- namescopes [WPF]
- styles [WPF], namescopes in
- templates [WPF], namescopes in
- APIs [WPF], name-related
- name-related APIs
- XAML [WPF], namescopes
- classes [WPF], FrameworkContentElement
ms.assetid: 52bbf4f2-15fc-40d4-837b-bb4c21ead7d4
ms.openlocfilehash: f9d4439c6b102d0d430b5201e3649985daee0b7f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186271"
---
# <a name="wpf-xaml-namescopes"></a>WPF XAML 名称范围
XAML 名称范围是关于标识 XAML 中定义的对象的一个概念。 XAML 名称范围中的名称可用于在对象树的对象 XAML 定义名称和其实例等效项之间建立关系。 通常，在加载 XAML 应用程序的各个 XAML 页面根时会以 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 托管代码创建 XAML 名称范围。 XAML名称范围作为编程对象由<xref:System.Windows.Markup.INameScope>接口定义，也由实用类<xref:System.Windows.NameScope>实现。  

<a name="Namescopes_in_Loaded_XAML_Applications"></a>
## <a name="namescopes-in-loaded-xaml-applications"></a>加载的 XAML 应用程序中的名称范围  
 从更广泛的编程或计算机科学来说，编程概念通常包括可用于访问对象的唯一标识符或名称的原则。 对于使用标识符或名称的系统，名称范围会定义边界，在该边界中，进程或技术会搜索是否请求了具有该名称的对象或者是否执行了标识名称唯一性。 这些一般原则适用于 XAML 名称范围。 在 WPF 中，当 XAML 页面加载时，会在该页面的根元素上创建 XAML 名称范围。 在 XAML 页面的页面根位置处指定的每个名称会添加到相关的 XAML 名称范围中。  
  
 在 WPF XAML 中，作为公共根元素的元素<xref:System.Windows.Controls.Page>（如<xref:System.Windows.Window>和 ） 始终控制 XAML 命名范围。 如果元素<xref:System.Windows.FrameworkElement>（如 或<xref:System.Windows.FrameworkContentElement>是标记中页面的根元素），[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]则处理器隐式添加<xref:System.Windows.Controls.Page>根，以便<xref:System.Windows.Controls.Page>可以提供有效的 XAML 命名范围。  
  
> [!NOTE]
> 即使在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 标记中的任何元素上都没有定义 `Name` 或 `x:Name` 特性，WPF 生成操作也将为 XAML 生产创建 XAML 名称范围。  
  
 如果尝试在任何 XAML 名称范围中两次使用相同的名称，将引发异常。 对于具有代码隐藏且作为已编译应用程序的一部分的 WPF XAML，在初始标记编译期间为页面创建生成类时，WPF 生成操作在生成时会引发异常。 对于不由任何生成操作进行标记编译的 XAML，加载 XAML 时可能会引发与 XAML 名称范围问题相关的异常。 XAML 设计器在设计时也可能会出现 XAML 名称范围问题。  
  
### <a name="adding-objects-to-runtime-object-trees"></a>将对象添加到运行时对象树  
 分析 XAML 时即意味着创建并定义 WPF XAML 名称范围的时刻。 如果在分析生成对象树的 XAML 之后的时间点将对象添加到对象树，新对象上的 `Name` 或 `x:Name` 值不会在 XAML 名称范围中自动更新信息。 要在加载 XAML 后将对象的名称添加到 WPF XAML 命名范围中，必须在定义 XAML 名称范围的对象<xref:System.Windows.Markup.INameScope.RegisterName%2A>上调用相应的实现，该名称范围通常是 XAML 页面根。 如果未注册该名称，则无法通过 方法（如<xref:System.Windows.FrameworkElement.FindName%2A>） 引用添加的对象，也不能将该名称用于动画定位。  
  
 对于应用程序开发人员来说，最常见的方案是，您将使用<xref:System.Windows.FrameworkElement.RegisterName%2A>在页面当前根目录上的 XAML 命名范围中注册名称。 <xref:System.Windows.FrameworkElement.RegisterName%2A>是面向动画对象的情节提要的重要方案的一部分。 有关详细信息，请参阅[情节提要概述](../graphics-multimedia/storyboards-overview.md)。  
  
 如果对定义<xref:System.Windows.FrameworkElement.RegisterName%2A>XAML 名称范围的对象以外的对象进行调用，则该名称仍注册到调用对象所持有的 XAML 命名范围，就像调用 XAML<xref:System.Windows.FrameworkElement.RegisterName%2A>命名对象一样。  
  
### <a name="xaml-namescopes-in-code"></a>代码中的 XAML 名称范围  
 可以通过代码创建然后使用 XAML 名称范围。 创建 XAML 名称范围所涉及的 API 和概念甚至与使用纯代码相同，因为 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的 XAML 处理器在自身处理 XAML 时就会使用这些 API 和概念。 这些概念和 API 存在的主要目的是为了能够在对象树中按名称查找对象（此对象树通常在 XAML 中完全或部分定义）。  
  
 对于以编程方式创建而不是从加载的 XAML 创建的应用程序，定义 XAML 名称范围的对象必须实现<xref:System.Windows.Markup.INameScope>或 或<xref:System.Windows.FrameworkElement><xref:System.Windows.FrameworkContentElement>派生类，以支持在其实例上创建 XAML 命名范围。  
  
 此外，对于任何不由 XAML 处理器加载和处理的元素，默认情况下不会创建或初始化对象的 XAML 名称范围。 必须为随后要将名称注册到其中的任何对象显式创建新的 XAML 名称范围。 要创建 XAML 命名范围，请调用静态<xref:System.Windows.NameScope.SetNameScope%2A>方法。 指定将具有该对象为`dependencyObject`参数的对象，并将新的<xref:System.Windows.NameScope.%23ctor%2A>构造函数调用作为`value`参数。  
  
 如果所`dependencyObject`<xref:System.Windows.NameScope.SetNameScope%2A>提供的对象<xref:System.Windows.Markup.INameScope>不是实现，<xref:System.Windows.FrameworkElement>或者<xref:System.Windows.FrameworkContentElement>调用<xref:System.Windows.FrameworkElement.RegisterName%2A>任何子元素将不起作用。 如果无法显式创建新的 XAML 命名范围，则调用 将<xref:System.Windows.FrameworkElement.RegisterName%2A>引发异常。  
  
 有关以代码方式使用 XAML 名称范围 API 的示例，请参阅[定义名称范围](../graphics-multimedia/how-to-define-a-name-scope.md)。  
  
<a name="Namescopes_in_Styles_and_Templates"></a>
## <a name="xaml-namescopes-in-styles-and-templates"></a>样式和模板中的 XAML 名称范围  
 通过 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中的样式和模板，可以直接重复使用和重复应用内容。 但是，样式和模板可能还包含具有模板级别定义的 XAML 名称的元素。 此相同模板可在一个页面中多次使用。 出于此原因，样式和模板皆定义其自身的 XAML 名称范围，与在应用样式或模板的对象树中的位置无关。  
  
 请考虑以下示例：  
  
 [!code-xaml[XamlOvwSupport#NameScopeTemplates](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page6.xaml#namescopetemplates)]  
  
 此处，同一模板应用到两个不同的按钮。 如果模板不具有离散的 XAML 名称范围，则模板中使用的 `TheBorder` 名称会导致 XAML 名称范围中的名称冲突。 模板的每个实例都具有其自己的 XAML 名称范围，因此在本例中，每个实例化模板的 XAML 名称范围仅包含一个名称。  
  
 样式也定义其自身的 XAML 名称范围，因此情节提要的各部分均可分配有特定的名称。 即使在控件自定义过程中重新定义模板，这些名称也可实现控件特定行为，定位具有该名称的元素。  
  
 由于这些分开的 XAML 名称范围，在模板中查找命名元素比在页面中查找非模板命名元素难度更大。 首先需要通过获取应用模板的控件<xref:System.Windows.Controls.Control.Template%2A>的属性值来确定应用的模板。 然后，调用 的<xref:System.Windows.FrameworkTemplate.FindName%2A>模板版本，传递作为第二个参数应用模板的控件。  
  
 如果您是控件作者，并且正在生成一个约定，其中应用模板中的特定命名元素是控件本身定义的行为的目标，则可以使用控件实现代码中<xref:System.Windows.FrameworkElement.GetTemplateChild%2A>的方法。 该方法<xref:System.Windows.FrameworkElement.GetTemplateChild%2A>受到保护，因此只有控件作者才能访问它。  
  
 如果您正在模板内工作，并且需要访问应用模板的 XAML 名称范围，请获取 的值<xref:System.Windows.FrameworkElement.TemplatedParent%2A>，然后调用<xref:System.Windows.FrameworkElement.FindName%2A>该值。 从模板内入手的一个示例是编写事件将从已应用模板中的元素引发的事件处理程序实现。  
  
<a name="Namescopes_and_Name_related_APIs"></a>
## <a name="xaml-namescopes-and-name-related-apis"></a>XAML 名称范围和与名称相关的 API  
 <xref:System.Windows.FrameworkElement>有<xref:System.Windows.FrameworkElement.FindName%2A> <xref:System.Windows.FrameworkElement.RegisterName%2A> ，<xref:System.Windows.FrameworkElement.UnregisterName%2A>和方法。 如果在其上调用这些方法的对象拥有 XAML 名称范围，则这些方法会调入相关 XAML 名称范围的方法。 否则，将检查父元素以查看其是否拥有 XAML 名称范围，此过程以递归方式持续发生，直到找到 XAML 名称范围（由于 XAML 处理器行为，根处必定存在一个 XAML 名称范围）。 <xref:System.Windows.FrameworkContentElement>具有类似行为，但没有任何<xref:System.Windows.FrameworkContentElement>人拥有 XAML 名称范围。 这些方法存在，<xref:System.Windows.FrameworkContentElement>以便最终可以将调用转发到<xref:System.Windows.FrameworkElement>父元素。  
  
 <xref:System.Windows.NameScope.SetNameScope%2A>用于将新的 XAML 命名范围映射到现有对象。 您可以多次调用<xref:System.Windows.NameScope.SetNameScope%2A>以重置或清除 XAML 名称范围，但这不是常见用法。 此外，<xref:System.Windows.NameScope.GetNameScope%2A>通常不从代码中使用。  
  
### <a name="xaml-namescope-implementations"></a>XAML 名称范围实现  
 以下类直接实现<xref:System.Windows.Markup.INameScope>：  
  
- <xref:System.Windows.NameScope>  
  
- <xref:System.Windows.Style>  
  
- <xref:System.Windows.ResourceDictionary>  
  
- <xref:System.Windows.FrameworkTemplate>  
  
 <xref:System.Windows.ResourceDictionary>不使用 XAML 名称或名称范围;它使用键，因为它是字典实现。 实现<xref:System.Windows.ResourceDictionary><xref:System.Windows.Markup.INameScope>的唯一原因是，它可以对用户代码引发异常，以帮助阐明真正的 XAML 命名范围与<xref:System.Windows.ResourceDictionary>处理密钥的方式之间的区别，并确保 XAML 命名码不<xref:System.Windows.ResourceDictionary>应用于父元素。  
  
 <xref:System.Windows.FrameworkTemplate>并通过<xref:System.Windows.Style>显式<xref:System.Windows.Markup.INameScope>接口定义实现。 显式实现允许这些 XAML 命名范围在通过<xref:System.Windows.Markup.INameScope>接口访问时按常规方式执行，这是[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内部进程传达 XAML 名称范围的方式。 但是显式接口定义不是<xref:System.Windows.FrameworkTemplate>和<xref:System.Windows.Style>的常规 API 表面的一部分，因为您很少需要直接调用<xref:System.Windows.Markup.INameScope>方法<xref:System.Windows.FrameworkTemplate><xref:System.Windows.Style>，而是使用其他 API（如<xref:System.Windows.FrameworkElement.GetTemplateChild%2A>）。  
  
 以下类通过使用<xref:System.Windows.NameScope?displayProperty=nameWithType>帮助器类并通过<xref:System.Windows.NameScope.NameScope%2A?displayProperty=nameWithType>附加属性连接到其 XAML 命名范围实现，定义它们自己的 XAML 命名范围：  
  
- <xref:System.Windows.FrameworkElement>  
  
- <xref:System.Windows.FrameworkContentElement>  
  
## <a name="see-also"></a>另请参阅

- [WPF XAML 的 XAML 命名空间和命名空间映射](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)
- [x:Name 指令](../../../desktop-wpf/xaml-services/xname-directive.md)
