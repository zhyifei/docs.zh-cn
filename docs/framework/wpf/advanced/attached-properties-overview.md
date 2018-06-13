---
title: 附加属性概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- attached properties [WPF Designer]
ms.assetid: 75928354-dc01-47e8-a018-8409aec1f32d
ms.openlocfilehash: 626cc0a5ddb1ba51be14eb045bcedcf7574cfb11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542166"
---
# <a name="attached-properties-overview"></a>附加属性概述
附加属性是由 XAML 定义的概念。 附加属性旨在用作可在任何对象上设置的一类全局属性。 在 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中，附加属性通常定义为没有常规属性“包装器”的依赖性属性的专用形式。  
  
   
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>系统必备  
 本主题假定你从 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 类的现有依赖属性的使用者角度了解依赖属性，并且已阅读[依赖属性概述](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)。 若要采用本主题中的示例，还应了解并知道 XAML 如何编写 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序。  
  
<a name="attached_properties_usage"></a>   
## <a name="why-use-attached-properties"></a>使用附加属性的原因  
 附加属性的一个用途是允许不同的子元素为实际在父元素中定义的属性指定唯一值。 此方案的一个具体应用是，让子元素通知父元素它们在 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 中的呈现方式。 一个示例是<xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>属性。 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>作为附加的属性创建属性，因为它用于在中包含的元素上设置<xref:System.Windows.Controls.DockPanel>，而不是在<xref:System.Windows.Controls.DockPanel>本身。 <xref:System.Windows.Controls.DockPanel>类定义静态<xref:System.Windows.DependencyProperty>名为字段<xref:System.Windows.Controls.DockPanel.DockProperty>，，然后提供<xref:System.Windows.Controls.DockPanel.GetDock%2A>和<xref:System.Windows.Controls.DockPanel.SetDock%2A>作为公共访问器的附加属性的方法。  
  
<a name="attached_properties_xaml"></a>   
## <a name="attached-properties-in-xaml"></a>XAML 中的附加属性  
 在 XAML 中，可以使用语法 AttachedPropertyProvider.PropertyName 来设置附加属性  
  
 以下是举例说明如何设置<xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>在 XAML 中：  
  
 [!code-xaml[PropertiesOvwSupport#APBasicUsage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml#apbasicusage)]  
  
 请注意，使用情况是某种程度上类似于静态属性;始终引用的类型<xref:System.Windows.Controls.DockPanel>，拥有并注册附加的属性，而不是引用由名称指定的任何实例。  
  
 此外，由于 XAML 中的附加属性是在标记中设置的属性，因此，只有设置操作具有相关性。 尽管存在一些用于比较值的间接机制（如在样式中触发），但无法直接在 XAML 中直接获取属性（有关详细信息，请参阅[样式设置和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)）。  
  
### <a name="attached-property-implementation-in-wpf"></a>WPF 中的附加属性实现  
 在 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 类型（与 UI 表示形式相关）上存在的大多数附加属性都实现为依赖属性。 附加属性是一个 XAML 概念，而依赖属性则是一个 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 概念。 因为 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 附加属性是依赖属性，所以它们支持依赖属性概念，如属性元数据和属性元数据默认值。  
  
<a name="howused"></a>   
## <a name="how-attached-properties-are-used-by-the-owning-type"></a>所属类型如何使用附加属性  
 尽管可以在任何对象上设置附加属性，但这并不自动意味着设置该属性会产生实际的结果，或者该值会被其他对象使用。 通常，附加属性是为了使来自各种可能的类层次结构或逻辑关系的对象都可以向用于定义附加属性的类型报告公用信息。 定义附加属性的类型通常采用以下模型之一：  
  
-   设计定义附加属性的类型，以便它可以是将为附加属性设置值的元素的父元素。 随后，该类型将在内部逻辑中对照某些对象树结构循环访问其子对象，获取值，并以某种方式作用于这些值。  
  
-   定义附加属性的类型将用作各种可能的父元素和内容模型的子元素。  
  
-   定义附加属性的类型表示一项服务。 其他类型为该附加属性设置值。 然后，当在服务的上下文中计算设置该属性的元素时，将通过服务类的内部逻辑获取附加属性的值。  
  
### <a name="an-example-of-a-parent-defined-attached-property"></a>父级定义的附加属性示例  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 定义附加属性的最典型方案是：父元素支持子元素集合，并实现分别为每个子元素报告行为细节的行为。  
  
 <xref:System.Windows.Controls.DockPanel> 定义<xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>附加属性，和<xref:System.Windows.Controls.DockPanel>作为其呈现逻辑的一部分具有类级别的代码 (具体而言，<xref:System.Windows.Controls.DockPanel.MeasureOverride%2A>和<xref:System.Windows.Controls.DockPanel.ArrangeOverride%2A>)。 A<xref:System.Windows.Controls.DockPanel>实例将始终检查是否任何直接子元素设置的值<xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>。 如果已设置，这些值将变为应用于该特定子元素的呈现逻辑的输入。 嵌套<xref:System.Windows.Controls.DockPanel>实例都处理自己的即时子元素集合，但该行为是特定于实现的如何<xref:System.Windows.Controls.DockPanel>进程<xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>值。 理论上，可以有影响直接父级之外的元素的附加属性。 如果<xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>未包含任何元素上设置附加的属性<xref:System.Windows.Controls.DockPanel>引发要遵照它时，没有错误或异常的父元素。 这只是表示设置全局属性值，但它具有无当前<xref:System.Windows.Controls.DockPanel>父无法使用该信息。  
  
<a name="attached_properties_code"></a>   
## <a name="attached-properties-in-code"></a>代码中的附加属性  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中的附加属性没有用于简化 get/set 访问的典型 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]“包装”方法。 这是因为附加属性不是必须属于设置它的实例的 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 命名空间的一部分。 但是，分析 XAML 时，XAML 处理器必须能够设置这些值。 若要支持有效的附加属性用法，附加属性的所有者类型必须在 `Get`PropertyName 和 `Set`PropertyName 窗体中实现专用访问器方法。 这些专用访问器方法对在代码中设置附加属性也很有帮助。 从代码的角度来看，附加属性类似于具有方法访问器而不是属性访问器的支持字段，且支持字段可在任何对象上存在，无需专门定义。  
  
 下面的示例演示如何在代码中设置附加属性。 在此示例中，`myCheckBox`是的一个实例<xref:System.Windows.Controls.CheckBox>类。  
  
 [!code-csharp[PropertiesOvwSupport#APCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#apcode)]
 [!code-vb[PropertiesOvwSupport#APCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#apcode)]  
  
 与 XAML 类似情况下，如果`myCheckBox`具有尚未添加的子元素作为`myDockPanel`由代码的第三个行，代码的第四个行不会引发异常，但属性值不会与交互<xref:System.Windows.Controls.DockPanel>父，因此将不执行任何操作。 仅<xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>值加上是否存在子元素上的设置<xref:System.Windows.Controls.DockPanel>父元素将导致在呈现的应用程序中的有效的行为。 （在这种情况下，可以设置附加属性，然后附加到树。 或者，可以先附加到该树中，然后设置附加属性。 这两种操作顺序结果都相同。）  
  
<a name="attached_properties_metadata"></a>   
## <a name="attached-property-metadata"></a>附加属性元数据  
 当注册属性时，<xref:System.Windows.FrameworkPropertyMetadata>设置为指定的属性，如的属性会影响呈现、 测量，等特征。 附加属性的元数据通常与依赖属性上的元数据基本上都相同。 如果在附加属性元数据替代中指定默认值，该值将成为替代类实例上显式附加属性的默认值。 具体而言，当某些进程通过该属性的 `Get` 方法访问器请求附加属性值，并指定在其中指定元数据的类的示例时，将报告默认值，而不会设置该附加属性的值。  
  
 如果希望对属性启用属性值继承，应使用附加属性，而不是非附加的依赖属性。 有关详细信息，请参阅[属性值继承](../../../../docs/framework/wpf/advanced/property-value-inheritance.md)。  
  
<a name="custom"></a>   
## <a name="custom-attached-properties"></a>自定义附加属性  
  
<a name="create_attached_properties"></a>   
### <a name="when-to-create-an-attached-property"></a>何时创建附加属性  
 当需要有一个可用于定义类之外的其他类的属性设置机制时，建议创建附加属性。 对于这一情况，最常见的方案是布局。 现有的布局属性的示例有<xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>， <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType>，和<xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>。 这里启用的方案是，作为布局控制元素的子元素存在的元素能够分别向其布局父级元素表达布局要求，其中每个元素都设置一个被父级定义为附加属性的属性值。  
  
 使用附加属性的另一种情况是，你的类表示一种服务，且你希望类能够以更透明的方式继承该服务。  
  
 但还有一种情况是接收 [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] 支持，例如“属性”窗口编辑。 有关详细信息，请参阅[控件创作概述](../../../../docs/framework/wpf/controls/control-authoring-overview.md)。  
  
 如前文所述，如果想要使用属性值继承，你应该注册为附加属性。  
  
<a name="how_do_i_create_attached_properties"></a>   
### <a name="how-to-create-an-attached-property"></a>如何创建附加属性  
 如果你的类定义使用严格的附加的属性上其他类型，则不需要派生自类<xref:System.Windows.DependencyObject>。 但需要为派生自<xref:System.Windows.DependencyObject>如果遵循整体[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]拥有附加的属性的模型也是依赖项属性。  
  
 定义为依赖项属性的附加的属性，通过声明`public` `static` `readonly`字段类型<xref:System.Windows.DependencyProperty>。 你使用的返回值定义此字段<xref:System.Windows.DependencyProperty.RegisterAttached%2A>方法。 字段名称必须匹配附加属性名称，且追加字符串 `Property`，以遵循命名标识字段及其所表示的属性的既定 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 模式。 附加属性提供程序还必须提供静态的 `Get`PropertyName 和 `Set`PropertyName 方法，作为附加属性访问器，否则将导致属性系统无法使用附加属性。  
  
> [!NOTE]
>  如果省略附加的属性 get 访问器时，数据绑定的属性上不会在设计工具，例如 Visual Studio 和 Expression Blend。  
  
#### <a name="the-get-accessor"></a>Get 访问器  
 `Get` PropertyName 访问器的签名必须是：  
  
 `public static object Get` PropertyName `(object` `target` `)`  
  
-   `target` 对象在实现中可以指定为更具体的类型。 例如，<xref:System.Windows.Controls.DockPanel.GetDock%2A?displayProperty=nameWithType>方法类型参数作为<xref:System.Windows.UIElement>，这是因为附加的属性仅用于设置<xref:System.Windows.UIElement>实例。  
  
-   返回值在实现中可以指定为更具体的类型。 例如，<xref:System.Windows.Controls.DockPanel.GetDock%2A>方法的类型为<xref:System.Windows.Controls.Dock>，因为值只能设置为此枚举。  
  
#### <a name="the-set-accessor"></a>Set 访问器  
 `Set` PropertyName 访问器的签名必须是：  
  
 `public static void Set` PropertyName `(object`  `target` `, object`  `value` `)`  
  
-   `target` 对象在实现中可以指定为更具体的类型。 例如，<xref:System.Windows.Controls.DockPanel.SetDock%2A>方法的类型为<xref:System.Windows.UIElement>，这是因为附加的属性仅用于设置<xref:System.Windows.UIElement>实例。  
  
-   `value` 对象在实现中可以指定为更具体的类型。 例如，<xref:System.Windows.Controls.DockPanel.SetDock%2A>方法的类型为<xref:System.Windows.Controls.Dock>，因为值只能设置为此枚举。 请记住，此方法的值是 XAML 加载器在标记中的附加属性用法中遇到附加属性时的输入。 该输入是在标记中指定为 XAML 属性值的值。 因此必须存在可用于你所使用的类型的类型转换、值序列化程序或标记扩展支持，以便可以从属性值（最终仅仅是一个字符串）创建相应的类型。  
  
 下面的示例演示注册依赖属性 (使用<xref:System.Windows.DependencyProperty.RegisterAttached%2A>方法)，以及`Get` *PropertyName*和`Set` *PropertyName*访问器. 在此示例中，附加属性名称为 `IsBubbleSource`。 因此，访问器必须名为 `GetIsBubbleSource` 和 `SetIsBubbleSource`。  
  
 [!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
 [!code-vb[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]  
  
#### <a name="attached-property-attributes"></a>附加属性特性  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 定义了多个 [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)]，后者用于向反射进程和反射的典型用户提供关于附加属性的信息以及如设计器等属性信息。 由于附加属性的类型没有范围限制，因此设计者需要一种方法来避免用户查看全局列表时，看到使用 XAML 的特定技术实现中定义的所有附加属性。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 针对附加属性定义的 [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] 可用于限制属性窗口的显示范围，只显示给定的附加属性。 你还可考虑对自己的自定义附加属性应用这些特性。 有关 [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] 的用途和语法说明，请参阅相应的参考页面：  
  
-   <xref:System.Windows.AttachedPropertyBrowsableAttribute>  
  
-   <xref:System.Windows.AttachedPropertyBrowsableForChildrenAttribute>  
  
-   <xref:System.Windows.AttachedPropertyBrowsableForTypeAttribute>  
  
-   <xref:System.Windows.AttachedPropertyBrowsableWhenAttributePresentAttribute>  
  
<a name="more"></a>   
## <a name="learning-more-about-attached-properties"></a>深入了解附加属性  
  
-   有关如何创建附加属性的详细信息，请参阅[注册附加属性](../../../../docs/framework/wpf/advanced/how-to-register-an-attached-property.md)。  
  
-   有关依赖属性和附加属性的更多高级使用方案，请参阅[自定义依赖属性](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)。  
  
-   还可将属性注册为附加属性和依赖属性，但仍需公开“包装器”实现。 在这种情况下，属性可在该元素上设置，也可通过 XAML 附加属性语法在任何元素上设置。 具有标准的和附加用法的相应方案的属性的一个示例是<xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.DependencyProperty>  
 [依赖项属性概述](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [自定义依赖属性](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [XAML 概述 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [注册附加属性](../../../../docs/framework/wpf/advanced/how-to-register-an-attached-property.md)
