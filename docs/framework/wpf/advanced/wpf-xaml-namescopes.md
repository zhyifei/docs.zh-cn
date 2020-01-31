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
ms.openlocfilehash: 4383492157191f61cf04a2fdd6ce27e9183bda8b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744416"
---
# <a name="wpf-xaml-namescopes"></a>WPF XAML 이름 범위
XAML 이름 범위는 XAML에 정의된 개체를 식별하는 개념입니다. XAML 이름 범위의 이름은 XAML로 정의된 개체 이름과 개체 트리에서 그에 해당하는 인스턴스 간의 관계를 설정하는 데 사용할 수 있습니다. 일반적으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 관리 코드의 XAML 이름 범위는 XAML 애플리케이션의 개별 XAML 페이지 루트를 로드할 때 만들어집니다. 作为编程对象的 XAML 名称范围由 <xref:System.Windows.Markup.INameScope> 接口定义，并且也是由实际类 <xref:System.Windows.NameScope>实现的。  

<a name="Namescopes_in_Loaded_XAML_Applications"></a>   
## <a name="namescopes-in-loaded-xaml-applications"></a>로드된 XAML 애플리케이션의 이름 범위  
 더욱 폭넓은 프로그래밍이나 컴퓨터 과학의 측면에서 프로그래밍 개념에는 흔히 개체에 액세스하는 데 사용할 수 있는 고유한 식별자 또는 이름의 원칙이 포함됩니다. 식별자나 이름을 사용하는 시스템의 경우 이름 범위는 해당 이름의 개체가 요청되는 경우 프로세스 또는 기술을 통해 검색할 위치의 경계나 식별 이름의 고유성이 적용되는 경계를 정의합니다. 이러한 일반적인 원칙은 XAML 이름 범위에도 해당됩니다. WPF에서 XAML 이름 범위는 페이지가 로드될 때 XAML 페이지의 루트 요소에 만들어집니다. XAML 페이지 내의 페이지 루트에서부터 지정된 각 이름은 관련 XAML 이름 범위에 추가됩니다.  
  
 在 WPF XAML 中，作为常见根元素（例如 <xref:System.Windows.Controls.Page>和 <xref:System.Windows.Window>）的元素始终控制 XAML 名称范围。 如果某个元素（如 <xref:System.Windows.FrameworkElement> 或 <xref:System.Windows.FrameworkContentElement>）是标记中页面的根元素，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器将隐式添加 <xref:System.Windows.Controls.Page> 根，以便 <xref:System.Windows.Controls.Page> 可以提供工作的 XAML 名称范围。  
  
> [!NOTE]
> WPF 빌드 작업에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그의 모든 요소에 대해 `Name` 또는 `x:Name` 특성이 정의되지 않은 경우에도 XAML 프로덕션을 위한 XAML 이름 범위가 만들어집니다.  
  
 한 XAML 이름 범위에서 같은 이름을 두 번 사용하려고 하면 예외가 발생합니다. 코드 숨김 파일이 있고 컴파일된 애플리케이션의 일부인 WPF XAML의 경우에는 빌드 시 WPF 빌드 작업에서 초기 태그 컴파일 중 페이지에 대해 생성된 클래스를 만들 때 예외가 발생합니다. 빌드 작업을 통해 태그 컴파일되지 않은 XAML의 경우에는 XAML이 로드될 때 XAML 이름 범위 문제와 관련된 예외가 발생할 수 있습니다. XAML 디자이너가 디자인 타임에 XAML 이름 범위 문제를 예상할 수도 있습니다.  
  
### <a name="adding-objects-to-runtime-object-trees"></a>런타임 개체 트리에 개체 추가  
 XAML이 구문 분석되는 시점은 WPF XAML 이름 범위가 만들어지고 정의되는 시점입니다. 개체 트리를 생성한 XAML이 구문 분석된 후에 개체 트리에 개체를 추가할 경우에는 새 개체의 `Name` 또는 `x:Name` 값에 따라 XAML 이름 범위의 정보가 자동으로 업데이트되지 않습니다. 若要在加载 XAML 后将对象的名称添加到 WPF XAML 名称范围，则必须在定义 XAML 名称范围（通常为 XAML 页根）的对象上调用 <xref:System.Windows.Markup.INameScope.RegisterName%2A> 的适当实现。 如果该名称未注册，则无法通过 <xref:System.Windows.FrameworkElement.FindName%2A>等方法通过名称引用添加的对象，并且不能将该名称用于动画目标。  
  
 对于应用程序开发人员而言，最常见的方案是使用 <xref:System.Windows.FrameworkElement.RegisterName%2A> 将名称注册到页面当前根的 XAML 名称范围中。 <xref:System.Windows.FrameworkElement.RegisterName%2A> 是面向动画对象的情节提要的一个重要方案的一部分。 자세한 내용은 [스토리보드 개요](../graphics-multimedia/storyboards-overview.md)를 참조하세요.  
  
 如果对定义 XAML 名称范围的对象之外的对象调用 <xref:System.Windows.FrameworkElement.RegisterName%2A>，则该名称仍将注册到调用对象所在的 XAML 名称范围中，就像你在 XAML 名称范围定义对象上调用了 <xref:System.Windows.FrameworkElement.RegisterName%2A> 一样。  
  
### <a name="xaml-namescopes-in-code"></a>코드의 XAML 이름 범위  
 코드에서 XAML 이름 범위를 만든 다음 사용할 수 있습니다. XAML 이름 범위를 만드는 데 관련된 API 및 개념은 순수형 코드를 사용하는 경우에도 동일합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]용 XAML 프로세서에서는 XAML 자체를 처리할 때 이러한 API 및 개념을 사용하기 때문입니다. 이 개념 및 API는 대개 일부 또는 전체가 XAML로 정의된 개체 트리 내에서 개체를 이름으로 찾을 수 있도록 하기 위한 것입니다.  
  
 对于以编程方式创建的应用程序（而不是从加载的 XAML），定义 XAML 名称范围的对象必须实现 <xref:System.Windows.Markup.INameScope>，或者必须是 <xref:System.Windows.FrameworkElement> 或 <xref:System.Windows.FrameworkContentElement> 派生类，以便支持在其实例上创建 XAML 名称范围。  
  
 또한 XAML 프로세서로 로드 및 처리되지 않는 모든 요소에 대해서는 기본적으로 개체의 XAML 이름 범위가 만들어지거나 초기화되지 않습니다. 따라서 이후에 이름을 등록하려는 모든 개체에 대해 명시적으로 새 XAML 이름 범위를 만들어야 합니다. 若要创建 XAML 名称范围，请调用静态 <xref:System.Windows.NameScope.SetNameScope%2A> 方法。 指定将作为 `dependencyObject` 参数的对象，并指定一个新的 <xref:System.Windows.NameScope.%23ctor%2A> 构造函数调用作为 `value` 参数。  
  
 如果作为 <xref:System.Windows.NameScope.SetNameScope%2A> 的 `dependencyObject` 提供的对象不是 <xref:System.Windows.Markup.INameScope> 实现、<xref:System.Windows.FrameworkElement> 或 <xref:System.Windows.FrameworkContentElement>，则对任何子元素调用 <xref:System.Windows.FrameworkElement.RegisterName%2A> 都不起作用。 如果无法显式创建新的 XAML 名称范围，则对 <xref:System.Windows.FrameworkElement.RegisterName%2A> 的调用将引发异常。  
  
 코드에서 XAML 이름 범위 API를 사용하는 예제를 보려면 [이름 범위 정의](../graphics-multimedia/how-to-define-a-name-scope.md)를 참조하세요.  
  
<a name="Namescopes_in_Styles_and_Templates"></a>   
## <a name="xaml-namescopes-in-styles-and-templates"></a>스타일 및 템플릿의 XAML 이름 범위  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 스타일 및 템플릿을 사용하면 간편하게 콘텐츠를 다시 사용 및 적용할 수 있지만 템플릿 수준에서 XAML 이름이 정의된 요소가 스타일 및 템플릿에 포함될 수 있습니다. 이런 템플릿은 한 페이지에서 여러 번 사용될 수 있기 때문에 스타일과 템플릿은 모두 해당 스타일 또는 템플릿이 적용되는 개체 트리 내의 위치와는 상관없이 고유한 XAML 이름 범위를 정의합니다.  
  
 다음 예제를 참조하세요.  
  
 [!code-xaml[XamlOvwSupport#NameScopeTemplates](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page6.xaml#namescopetemplates)]  
  
 여기에서는 두 개의 단추에 동일한 템플릿이 적용됩니다. 템플릿에 개별 XAML 이름 범위가 없으면 템플릿에 사용된 `TheBorder` 이름 때문에 XAML 이름 범위에서 이름 충돌이 발생합니다. 템플릿의 각 인스턴스에는 고유한 XAML 이름 범위가 있으므로 이 예제에서 인스턴스화된 각 템플릿의 XAML 이름 범위에는 정확하게 하나의 이름만 포함됩니다.  
  
 스타일도 고유한 XAML 이름 범위를 정의하므로 대부분의 경우 스토리보드의 각 부분에 특정 이름이 할당될 수 있습니다. 이러한 이름을 사용하면 컨트롤 사용자 지정 과정에서 템플릿이 재정의된 경우에도 해당 이름의 요소를 대상으로 하는 특정 동작을 제어할 수 있습니다.  
  
 XAML 이름 범위가 분리되어 있으므로 템플릿에서 명명된 요소를 찾는 것이 페이지에서 템플릿 형식이 아닌 명명된 요소를 찾는 것보다 복잡합니다. 首先需要通过获取应用模板的控件的 <xref:System.Windows.Controls.Control.Template%2A> 属性值来确定已应用的模板。 然后，调用 <xref:System.Windows.FrameworkTemplate.FindName%2A>的模板版本，并传递应用模板的控件作为第二个参数。  
  
 如果你是控件作者，而你正在生成一个约定，其中应用的模板中的特定命名元素是控件本身定义的行为的目标，则可以使用控件实现代码中的 <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> 方法。 <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> 方法是受保护的，因此只有控件作者可以访问它。  
  
 如果是在模板中工作，并且需要访问应用了模板的 XAML 名称范围，请获取 <xref:System.Windows.FrameworkElement.TemplatedParent%2A>的值，然后调用 <xref:System.Windows.FrameworkElement.FindName%2A>。 적용된 템플릿의 요소에서 이벤트가 발생되는 이벤트 처리기를 구현하는 경우가 템플릿 내에서 작업하는 예에 해당합니다.  
  
<a name="Namescopes_and_Name_related_APIs"></a>   
## <a name="xaml-namescopes-and-name-related-apis"></a>XAML 이름 범위 및 이름 관련 API  
 <xref:System.Windows.FrameworkElement> 具有 <xref:System.Windows.FrameworkElement.FindName%2A>、<xref:System.Windows.FrameworkElement.RegisterName%2A> 和 <xref:System.Windows.FrameworkElement.UnregisterName%2A> 方法。 이러한 메서드를 호출하는 개체에 고유한 XAML 이름 범위가 있는 경우 이러한 메서드는 관련 XAML 이름 범위의 메서드를 호출합니다. 그렇지 않은 경우에는 부모 요소에 고유한 XAML 이름 범위가 있는지 확인하며, 이 확인 과정은 XAML 이름 범위를 찾을 때까지 재귀적으로 계속됩니다(XAML 프로세서의 동작 때문에 루트에는 반드시 XAML 이름 범위가 있음). <xref:System.Windows.FrameworkContentElement> 具有类似的行为，但没有任何 <xref:System.Windows.FrameworkContentElement> 会拥有 XAML 名称范围的例外。 <xref:System.Windows.FrameworkContentElement> 中存在方法，以便可以将调用最终转发到 <xref:System.Windows.FrameworkElement> 的父元素。  
  
 <xref:System.Windows.NameScope.SetNameScope%2A> 用于将新的 XAML 名称范围映射到现有对象。 可以多次调用 <xref:System.Windows.NameScope.SetNameScope%2A> 以重置或清除 XAML 名称范围，但这不是常见的用法。 此外，<xref:System.Windows.NameScope.GetNameScope%2A> 通常不会从代码中使用。  
  
### <a name="xaml-namescope-implementations"></a>XAML 이름 범위 구현  
 以下类直接实现 <xref:System.Windows.Markup.INameScope>：  
  
- <xref:System.Windows.NameScope>  
  
- <xref:System.Windows.Style>  
  
- <xref:System.Windows.ResourceDictionary>  
  
- <xref:System.Windows.FrameworkTemplate>  
  
 <xref:System.Windows.ResourceDictionary> 不使用 XAML 名称或名称范围;它使用键，因为它是字典实现。 <xref:System.Windows.ResourceDictionary> 实现 <xref:System.Windows.Markup.INameScope> 的唯一原因是，它可能会向用户代码引发异常，以帮助阐明真正的 XAML 名称范围与 <xref:System.Windows.ResourceDictionary> 处理键之间的区别，还可以确保不会将 XAML 名称范围应用于父元素的 <xref:System.Windows.ResourceDictionary>。  
  
 <xref:System.Windows.FrameworkTemplate> 和 <xref:System.Windows.Style> 通过显式接口定义实现 <xref:System.Windows.Markup.INameScope>。 当通过 <xref:System.Windows.Markup.INameScope> 接口访问 xaml 名称范围时，显式实现允许这些 XAML 名称范围正常运行，这是 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内部进程传达 XAML 名称范围的方式。 但显式接口定义不是 <xref:System.Windows.FrameworkTemplate> 和 <xref:System.Windows.Style>的传统 API 图面的一部分，因为您很少需要直接对 <xref:System.Windows.FrameworkTemplate> 和 <xref:System.Windows.Style> 调用 <xref:System.Windows.Markup.INameScope> 方法，而是使用其他 API，如 <xref:System.Windows.FrameworkElement.GetTemplateChild%2A>。  
  
 以下类定义自己的 XAML 名称范围，方法是使用 <xref:System.Windows.NameScope?displayProperty=nameWithType> 帮助器类并通过 <xref:System.Windows.NameScope.NameScope%2A?displayProperty=nameWithType> 附加属性连接到其 XAML 名称范围实现：  
  
- <xref:System.Windows.FrameworkElement>  
  
- <xref:System.Windows.FrameworkContentElement>  
  
## <a name="see-also"></a>另请参阅

- [WPF XAML을 위한 XAML 네임스페이스 및 네임스페이스 매핑](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)
- [x:Name 지시문](../../../desktop-wpf/xaml-services/xname-directive.md)
