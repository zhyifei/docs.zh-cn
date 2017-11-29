---
title: "WPF XAML 名称范围"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- namescopes [WPF]
- styles [WPF], namescopes in
- templates [WPF], namescopes in
- APIs [WPF], name-related
- name-related APIs
- XAML [WPF], namescopes
- classes [WPF], FrameworkContentElement
ms.assetid: 52bbf4f2-15fc-40d4-837b-bb4c21ead7d4
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 22b0354a0821021239140527793dc34e3911a733
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="wpf-xaml-namescopes"></a>WPF XAML 名称范围
XAML 名称范围是关于标识 XAML 中定义的对象的一个概念。 XAML 名称范围中的名称可用于在对象树的对象 XAML 定义名称和其实例等效项之间建立关系。 通常，在加载 XAML 应用程序的各个 XAML 页面根时会以 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 托管代码创建 XAML 名称范围。 作为编程对象的 XAML 名称范围定义的<xref:System.Windows.Markup.INameScope>接口，并由实际类还实现<xref:System.Windows.NameScope>。  
  
  
  
<a name="Namescopes_in_Loaded_XAML_Applications"></a>   
## <a name="namescopes-in-loaded-xaml-applications"></a>加载的 XAML 应用程序中的名称范围  
 从更广泛的编程或计算机科学来说，编程概念通常包括可用于访问对象的唯一标识符或名称的原则。 对于使用标识符或名称的系统，名称范围会定义边界，在该边界中，进程或技术会搜索是否请求了具有该名称的对象或者是否执行了标识名称唯一性。 这些一般原则适用于 XAML 名称范围。 在 WPF 中，当 XAML 页面加载时，会在该页面的根元素上创建 XAML 名称范围。 在 XAML 页面的页面根位置处指定的每个名称会添加到相关的 XAML 名称范围中。  
  
 在 WPF XAML 中，是常见的根元素的元素 (如<xref:System.Windows.Controls.Page>，和<xref:System.Windows.Window>) 始终控制 XAML 名称范围。 如果如元素<xref:System.Windows.FrameworkElement>或<xref:System.Windows.FrameworkContentElement>是在标记中，页的根元素[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器将添加<xref:System.Windows.Controls.Page>隐式根以便<xref:System.Windows.Controls.Page>可以提供工作 XAML 名称范围。  
  
> [!NOTE]
>  即使在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 标记中的任何元素上都没有定义 `Name` 或 `x:Name` 特性，WPF 生成操作也将为 XAML 生产创建 XAML 名称范围。  
  
 如果尝试在任何 XAML 名称范围中两次使用相同的名称，将引发异常。 对于具有代码隐藏且作为已编译应用程序的一部分的 WPF XAML，在初始标记编译期间为页面创建生成类时，WPF 生成操作在生成时会引发异常。 对于不由任何生成操作进行标记编译的 XAML，加载 XAML 时可能会引发与 XAML 名称范围问题相关的异常。 XAML 设计器在设计时也可能会出现 XAML 名称范围问题。  
  
### <a name="adding-objects-to-runtime-object-trees"></a>将对象添加到运行时对象树  
 分析 XAML 时即意味着创建并定义 WPF XAML 名称范围的时刻。 如果在分析生成对象树的 XAML 之后的时间点将对象添加到对象树，新对象上的 `Name` 或 `x:Name` 值不会在 XAML 名称范围中自动更新信息。 若要将对象的名称添加到 WPF XAML 名称范围中，XAML 加载后，必须调用正确地实现<xref:System.Windows.Markup.INameScope.RegisterName%2A>上定义 XAML 名称范围的对象，这通常是 XAML 页面根。 名称未注册，如果添加的对象不能按名称引用通过方法如<xref:System.Windows.FrameworkElement.FindName%2A>，并且不能使用该名称用于动画目标。  
  
 应用程序开发人员的最常见方案是，你将使用<xref:System.Windows.FrameworkElement.RegisterName%2A>注册到当前页的根元素的 XAML 名称范围的名称。 <xref:System.Windows.FrameworkElement.RegisterName%2A>是的情节提要的重要方案一部分动画该目标对象。 有关详细信息，请参阅[情节提要概述](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)。  
  
 如果调用<xref:System.Windows.FrameworkElement.RegisterName%2A>以外定义 XAML 名称范围的对象的对象，该名称是否仍注册到 XAML 名称范围内，保存调用的对象就像已调用<xref:System.Windows.FrameworkElement.RegisterName%2A>定义对象的 XAML 名称范围。  
  
### <a name="xaml-namescopes-in-code"></a>代码中的 XAML 名称范围  
 可以通过代码创建然后使用 XAML 名称范围。 创建 XAML 名称范围所涉及的 API 和概念甚至与使用纯代码相同，因为 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的 XAML 处理器在自身处理 XAML 时就会使用这些 API 和概念。 这些概念和 API 存在的主要目的是为了能够在对象树中按名称查找对象（此对象树通常在 XAML 中完全或部分定义）。  
  
 有关以编程方式，创建的应用程序而不是从加载的 XAML，定义 XAML 名称范围的对象必须实现<xref:System.Windows.Markup.INameScope>，或者是<xref:System.Windows.FrameworkElement>或<xref:System.Windows.FrameworkContentElement>为了上支持的 XAML 名称范围的创建派生类，其实例。  
  
 此外，对于任何不由 XAML 处理器加载和处理的元素，默认情况下不会创建或初始化对象的 XAML 名称范围。 必须为随后要将名称注册到其中的任何对象显式创建新的 XAML 名称范围。 若要创建 XAML 名称范围，则可以调用静态<xref:System.Windows.NameScope.SetNameScope%2A>方法。 指定将拥有其作为对象`dependencyObject`参数，并且新<xref:System.Windows.NameScope.%23ctor%2A>作为构造函数调用`value`参数。  
  
 如果该对象用作`dependencyObject`为<xref:System.Windows.NameScope.SetNameScope%2A>不<xref:System.Windows.Markup.INameScope>实现，<xref:System.Windows.FrameworkElement>或<xref:System.Windows.FrameworkContentElement>，则调用<xref:System.Windows.FrameworkElement.RegisterName%2A>对任何子元素将产生任何影响。 如果你没有显式创建新的 XAML 名称范围，然后调用<xref:System.Windows.FrameworkElement.RegisterName%2A>将引发的异常。  
  
 有关以代码方式使用 XAML 名称范围 API 的示例，请参阅[定义名称范围](../../../../docs/framework/wpf/graphics-multimedia/how-to-define-a-name-scope.md)。  
  
<a name="Namescopes_in_Styles_and_Templates"></a>   
## <a name="xaml-namescopes-in-styles-and-templates"></a>样式和模板中的 XAML 名称范围  
 通过 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中的样式和模板，可以直接重复使用和重复应用内容。 但是，样式和模板可能还包含具有模板级别定义的 XAML 名称的元素。 此相同模板可在一个页面中多次使用。 出于此原因，样式和模板皆定义其自身的 XAML 名称范围，与在应用样式或模板的对象树中的位置无关。  
  
 请看下面的示例：  
  
 [!code-xaml[XamlOvwSupport#NameScopeTemplates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page6.xaml#namescopetemplates)]  
  
 此处，同一模板应用到两个不同的按钮。 如果模板不具有离散的 XAML 名称范围，则模板中使用的 `TheBorder` 名称会导致 XAML 名称范围中的名称冲突。 模板的每个实例都具有其自己的 XAML 名称范围，因此在本例中，每个实例化模板的 XAML 名称范围仅包含一个名称。  
  
 样式也定义其自身的 XAML 名称范围，因此情节提要的各部分均可分配有特定的名称。 即使在控件自定义过程中重新定义模板，这些名称也可实现控件特定行为，定位具有该名称的元素。  
  
 由于这些分开的 XAML 名称范围，在模板中查找命名元素比在页面中查找非模板命名元素难度更大。 你首先需要确定所应用的模板，通过获取<xref:System.Windows.Controls.Control.Template%2A>应用该模板的控件属性值。 然后，调用的模板版本<xref:System.Windows.FrameworkTemplate.FindName%2A>，将控件传递其中第二个参数应用模板。  
  
 如果要生成的特定命名应用的模板中的元素是定义由控件本身的行为的目标的其中一个约定是控件作者，你可以使用<xref:System.Windows.FrameworkElement.GetTemplateChild%2A>在控件实现代码中的方法。 <xref:System.Windows.FrameworkElement.GetTemplateChild%2A>受保护方法，因此只有控件作者有权访问它。  
  
 如果你正在从内模板，并需要获取 XAML 名称范围到应用该模板时，获取的值<xref:System.Windows.FrameworkElement.TemplatedParent%2A>，然后调用<xref:System.Windows.FrameworkElement.FindName%2A>存在。 从模板内入手的一个示例是编写事件将从已应用模板中的元素引发的事件处理程序实现。  
  
<a name="Namescopes_and_Name_related_APIs"></a>   
## <a name="xaml-namescopes-and-name-related-apis"></a>XAML 名称范围和与名称相关的 API  
 <xref:System.Windows.FrameworkElement>具有<xref:System.Windows.FrameworkElement.FindName%2A>，<xref:System.Windows.FrameworkElement.RegisterName%2A>和<xref:System.Windows.FrameworkElement.UnregisterName%2A>方法。 如果在其上调用这些方法的对象拥有 XAML 名称范围，则这些方法会调入相关 XAML 名称范围的方法。 否则，将检查父元素以查看其是否拥有 XAML 名称范围，此过程以递归方式持续发生，直到找到 XAML 名称范围（由于 XAML 处理器行为，根处必定存在一个 XAML 名称范围）。 <xref:System.Windows.FrameworkContentElement>具有类似的行为，出现异常，没有<xref:System.Windows.FrameworkContentElement>绝不会拥有 XAML 名称范围。 上存在上述方法<xref:System.Windows.FrameworkContentElement>以便在调用可以将最终为转发<xref:System.Windows.FrameworkElement>父元素。  
  
 <xref:System.Windows.NameScope.SetNameScope%2A>用于将新的 XAML 名称范围映射到现有对象。 你可以调用<xref:System.Windows.NameScope.SetNameScope%2A>多次才能重置或清除 XAML 名称范围，但不是常见的用法。 此外，<xref:System.Windows.NameScope.GetNameScope%2A>不常使用代码中。  
  
### <a name="xaml-namescope-implementations"></a>XAML 名称范围实现  
 下面的类实现<xref:System.Windows.Markup.INameScope>直接：  
  
-   <xref:System.Windows.NameScope>  
  
-   <xref:System.Windows.Style>  
  
-   <xref:System.Windows.ResourceDictionary>  
  
-   <xref:System.Windows.FrameworkTemplate>  
  
 <xref:System.Windows.ResourceDictionary>不使用 XAML 的名称范围;它使用的是键，因为它是一种字典实现。 唯一原因<xref:System.Windows.ResourceDictionary>实现<xref:System.Windows.Markup.INameScope>是使它可能会引发异常对于用户代码，可帮助阐明 true 的 XAML 名称范围之间的区别，以及如何<xref:System.Windows.ResourceDictionary>处理键，并且还可以保证 XAML 名称范围不会应用到<xref:System.Windows.ResourceDictionary>由父元素。  
  
 <xref:System.Windows.FrameworkTemplate>和<xref:System.Windows.Style>实现<xref:System.Windows.Markup.INameScope>通过显式接口定义。 显式实现允许常规行为时通过访问这些 XAML 名称范围<xref:System.Windows.Markup.INameScope>接口，该 XAML 名称范围的通信方式通过[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的内部流程。 但不属于的传统的 API 表面的显式接口定义。<xref:System.Windows.FrameworkTemplate>和<xref:System.Windows.Style>，这是因为你很少需要调用<xref:System.Windows.Markup.INameScope>方法<xref:System.Windows.FrameworkTemplate>和<xref:System.Windows.Style>直接，，而不是将使用其他 API如<xref:System.Windows.FrameworkElement.GetTemplateChild%2A>。  
  
 下面的类定义其自己的 XAML 名称范围，通过使用<xref:System.Windows.NameScope?displayProperty=nameWithType>帮助器类，并连接到通过其 XAML 名称范围实现<xref:System.Windows.NameScope.NameScope%2A?displayProperty=nameWithType>附加属性：  
  
-   <xref:System.Windows.FrameworkElement>  
  
-   <xref:System.Windows.FrameworkContentElement>  
  
## <a name="see-also"></a>另请参阅  
 [WPF XAML 的 XAML 命名空间和命名空间映射](../../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)  
 [x:Name 指令](../../../../docs/framework/xaml-services/x-name-directive.md)
