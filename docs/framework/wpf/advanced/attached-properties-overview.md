---
title: 附加属性概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- attached properties [WPF Designer]
ms.assetid: 75928354-dc01-47e8-a018-8409aec1f32d
ms.openlocfilehash: cee80ca0880e046870f699f45624df61ee507a47
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/25/2019
ms.locfileid: "72919862"
---
# <a name="attached-properties-overview"></a>附加属性概述

附加属性是由 XAML 定义的概念。 附加属性旨在用作可在任何对象上设置的一类全局属性。 在 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中，附加属性通常定义为没有常规属性“包装器”的依赖性属性的专用形式。

## 先决条件<a name="prerequisites"></a>

本主题假定你从 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 类的现有依赖属性的使用者角度了解依赖属性，并且已阅读[依赖属性概述](dependency-properties-overview.md)。 若要按照本主题中的示例进行操作，还应了解 XAML 并了解如何编写 WPF 应用程序。

## 为什么使用附加属性<a name="attached_properties_usage"></a>

附加属性的一个用途是允许不同的子元素为实际在父元素中定义的属性指定唯一值。 此方案的一个具体应用是，让子元素通知父元素它们在 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 中的呈现方式。 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> 属性就是一个示例。 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> 属性将创建为附加属性，因为该属性设计为在包含在 <xref:System.Windows.Controls.DockPanel>中的元素上设置，而不是在 <xref:System.Windows.Controls.DockPanel> 本身上设置。 <xref:System.Windows.Controls.DockPanel> 类定义名为 <xref:System.Windows.Controls.DockPanel.DockProperty>的静态 <xref:System.Windows.DependencyProperty> 字段，然后提供作为附加属性公共访问器的 <xref:System.Windows.Controls.DockPanel.GetDock%2A> 和 <xref:System.Windows.Controls.DockPanel.SetDock%2A> 方法。

## XAML 中的附加属性<a name="attached_properties_xaml"></a>

在 XAML 中，可以使用语法 AttachedPropertyProvider.PropertyName 来设置附加属性

下面是如何在 XAML 中设置 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> 的示例：

[!code-xaml[PropertiesOvwSupport#APBasicUsage](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml#apbasicusage)]

请注意，使用情况有些类似于静态属性;始终引用拥有和注册附加属性的类型 <xref:System.Windows.Controls.DockPanel>，而不是引用由 name 指定的任何实例。

此外，由于 XAML 中的附加属性是在标记中设置的属性，因此，只有设置操作具有相关性。 尽管存在一些用于比较值的间接机制（如在样式中触发），但无法直接在 XAML 中直接获取属性（有关详细信息，请参阅[样式设置和模板化](../controls/styling-and-templating.md)）。

### <a name="attached-property-implementation-in-wpf"></a>WPF 中的附加属性实现

在 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]中，与 UI 表示形式相关的 WPF 类型上存在的大多数附加属性都实现为依赖属性。 附加属性是 XAML 概念，而依赖属性是 WPF 概念。 因为 WPF 附加属性是依赖属性，所以它们支持依赖属性概念（如属性元数据）和来自该属性元数据的默认值。

## 所属类型使用附加属性的方式<a name="howused"></a>

尽管可以在任何对象上设置附加属性，但这并不自动意味着设置该属性会产生实际的结果，或者该值会被其他对象使用。 通常，附加属性是为了使来自各种可能的类层次结构或逻辑关系的对象都可以向用于定义附加属性的类型报告公用信息。 定义附加属性的类型通常采用以下模型之一：

- 设计定义附加属性的类型，以便它可以是将为附加属性设置值的元素的父元素。 随后，该类型将在内部逻辑中对照某些对象树结构循环访问其子对象，获取值，并以某种方式作用于这些值。

- 定义附加属性的类型将用作各种可能的父元素和内容模型的子元素。

- 定义附加属性的类型表示一项服务。 其他类型为该附加属性设置值。 然后，当在服务的上下文中计算设置该属性的元素时，将通过服务类的内部逻辑获取附加属性的值。

### <a name="an-example-of-a-parent-defined-attached-property"></a>父级定义的附加属性示例

WPF 定义附加属性的最典型方案是：当父元素支持子元素集合时，还实现了一种行为，其中为每个子元素单独报告了行为的细节。

<xref:System.Windows.Controls.DockPanel> 定义 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> 附加属性，<xref:System.Windows.Controls.DockPanel> 具有类级别代码作为其呈现逻辑（具体而言，<xref:System.Windows.Controls.DockPanel.MeasureOverride%2A> 和 <xref:System.Windows.Controls.DockPanel.ArrangeOverride%2A>）的一部分。 <xref:System.Windows.Controls.DockPanel> 实例将始终检查其任意直接子元素是否已为 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>设置了值。 如果已设置，这些值将变为应用于该特定子元素的呈现逻辑的输入。 嵌套的 <xref:System.Windows.Controls.DockPanel> 实例分别处理它们自己的直接子元素集合，但该行为是特定于实现的，它是 <xref:System.Windows.Controls.DockPanel> 处理 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> 值的方式。 理论上，可以有影响直接父级之外的元素的附加属性。 如果在没有要对其执行操作的 <xref:System.Windows.Controls.DockPanel> 父元素的元素上设置 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> 附加属性，则不会引发错误或异常。 这只是表示已设置全局属性值，但没有可使用该信息的当前 <xref:System.Windows.Controls.DockPanel> 父级。

## 代码中的附加属性<a name="attached_properties_code"></a>

WPF 中的附加属性没有用于轻松获取/设置访问的典型 CLR "包装器" 方法。 这是因为，附加属性不一定是设置了属性的实例的 CLR 命名空间的一部分。 但是，分析 XAML 时，XAML 处理器必须能够设置这些值。 若要支持有效的附加属性用法，附加属性的所有者类型必须以**Get_PropertyName_** 和**Set_PropertyName_** 的形式实现专用访问器方法。 这些专用访问器方法对在代码中设置附加属性也很有帮助。 从代码的角度来看，附加属性类似于具有方法访问器而不是属性访问器的支持字段，且支持字段可在任何对象上存在，无需专门定义。

下面的示例演示如何在代码中设置附加属性。 在此示例中，`myCheckBox` 是 <xref:System.Windows.Controls.CheckBox> 类的实例。

[!code-csharp[PropertiesOvwSupport#APCode](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#apcode)]
[!code-vb[PropertiesOvwSupport#APCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#apcode)]

与 XAML 情况类似，如果 `myCheckBox` 尚未添加为第三行代码 `myDockPanel` 的子元素，则第四行代码不会引发异常，但属性值不会与 <xref:System.Windows.Controls.DockPanel> 父代交互，从而没. 只有在子元素上设置的 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> 值与 <xref:System.Windows.Controls.DockPanel> 父元素的存在相结合将导致呈现的应用程序中出现有效的行为。 （在这种情况下，可以设置附加属性，然后附加到树。 或者，可以先附加到该树中，然后设置附加属性。 这两种操作顺序结果都相同。）

## 附加属性元数据<a name="attached_properties_metadata"></a>

注册属性时，<xref:System.Windows.FrameworkPropertyMetadata> 设置为指定属性的特性，例如属性是否影响呈现、度量等。 附加属性的元数据通常与依赖属性上的元数据基本上都相同。 如果在附加属性元数据替代中指定默认值，该值将成为替代类实例上显式附加属性的默认值。 具体而言，当某些进程通过该属性的 `Get` 方法访问器请求附加属性值，并指定在其中指定元数据的类的示例时，将报告默认值，而不会设置该附加属性的值。

如果希望对属性启用属性值继承，应使用附加属性，而不是非附加的依赖属性。 有关详细信息，请参阅[属性值继承](property-value-inheritance.md)。

## 自定义附加属性<a name="custom"></a>

### 何时创建附加属性<a name="create_attached_properties"></a>

当需要有一个可用于定义类之外的其他类的属性设置机制时，建议创建附加属性。 对于这一情况，最常见的方案是布局。 现有布局属性的示例包括 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>、<xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType>和 <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>。 这里启用的方案是，作为布局控制元素的子元素存在的元素能够分别向其布局父级元素表达布局要求，其中每个元素都设置一个被父级定义为附加属性的属性值。

使用附加属性的另一种情况是，你的类表示一种服务，且你希望类能够以更透明的方式继承该服务。

但另一种情况是接收 Visual Studio WPF 设计器支持，如 "**属性**" 窗口编辑。 有关详细信息，请参阅[控件创作概述](../controls/control-authoring-overview.md)。

如前文所述，如果想要使用属性值继承，你应该注册为附加属性。

### 如何创建附加属性<a name="how_do_i_create_attached_properties"></a>

如果你的类将严格定义附加属性以用于其他类型，则该类不必从 <xref:System.Windows.DependencyObject>派生。 但是，如果遵循使附加属性也是依赖属性的总体 WPF 模型，则确实需要从 <xref:System.Windows.DependencyObject> 派生。

通过声明类型 <xref:System.Windows.DependencyProperty>的 `public static readonly` 字段，将附加属性定义为依赖属性。 使用 <xref:System.Windows.DependencyProperty.RegisterAttached%2A> 方法的返回值定义此字段。 字段名称必须与附加属性名称相匹配，并追加字符串 `Property`，才能遵循建立的、标识字段与它们所表示的属性的命名的 WPF 模式。 附加属性提供程序还必须提供静态**Get_PropertyName_** 和**Set_PropertyName_** 方法作为附加属性的访问器;如果无法执行此操作，则会导致属性系统无法使用附加属性。

> [!NOTE]
> 如果省略附加属性的 get 访问器，则属性上的数据绑定将无法在设计工具（如 Visual Studio 和 Blend for Visual Studio）中工作。

#### <a name="the-get-accessor"></a>Get 访问器

**Get_PropertyName_** 访问器的签名必须是：

`public static object GetPropertyName(object target)`

- `target` 对象在实现中可以指定为更具体的类型。 例如，<xref:System.Windows.Controls.DockPanel.GetDock%2A?displayProperty=nameWithType> 方法将参数键入为 <xref:System.Windows.UIElement>，因为附加属性只用于在 <xref:System.Windows.UIElement> 实例上进行设置。

- 返回值在实现中可以指定为更具体的类型。 例如，<xref:System.Windows.Controls.DockPanel.GetDock%2A> 方法将其类型设置为 <xref:System.Windows.Controls.Dock>，因为该值只能设置为该枚举。

#### <a name="the-set-accessor"></a>Set 访问器

**Set_PropertyName_** 访问器的签名必须是：

`public static void SetPropertyName(object target, object value)`

- `target` 对象在实现中可以指定为更具体的类型。 例如，<xref:System.Windows.Controls.DockPanel.SetDock%2A> 方法将其类型设置为 <xref:System.Windows.UIElement>，因为附加属性只应在 <xref:System.Windows.UIElement> 实例上设置。

- `value` 对象在实现中可以指定为更具体的类型。 例如，<xref:System.Windows.Controls.DockPanel.SetDock%2A> 方法将其类型设置为 <xref:System.Windows.Controls.Dock>，因为该值只能设置为该枚举。 请记住，此方法的值是 XAML 加载器在标记中的附加属性用法中遇到附加属性时的输入。 该输入是在标记中指定为 XAML 属性值的值。 因此必须存在可用于你所使用的类型的类型转换、值序列化程序或标记扩展支持，以便可以从属性值（最终仅仅是一个字符串）创建相应的类型。

下面的示例演示了依赖属性注册（使用 <xref:System.Windows.DependencyProperty.RegisterAttached%2A> 方法）以及**Get_PropertyName_** 和**Set_PropertyName_** 访问器。 在此示例中，附加属性名称为 `IsBubbleSource`。 因此，访问器必须名为 `GetIsBubbleSource` 和 `SetIsBubbleSource`。

[!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
[!code-vb[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]

#### <a name="attached-property-attributes"></a>附加属性特性

WPF 定义了多个 [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)]，旨在向反射进程提供附加属性的相关信息，并定义了反射的典型用户和属性信息（如设计器）。 由于附加属性的类型没有范围限制，因此设计者需要一种方法来避免用户查看全局列表时，看到使用 XAML 的特定技术实现中定义的所有附加属性。 WPF 为附加属性定义的 [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] 可用于确定应该在 "属性" 窗口中显示给定附加属性的情况的作用域。 你还可考虑对自己的自定义附加属性应用这些特性。 有关 [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] 的用途和语法说明，请参阅相应的参考页面：

- <xref:System.Windows.AttachedPropertyBrowsableAttribute>

- <xref:System.Windows.AttachedPropertyBrowsableForChildrenAttribute>

- <xref:System.Windows.AttachedPropertyBrowsableForTypeAttribute>

- <xref:System.Windows.AttachedPropertyBrowsableWhenAttributePresentAttribute>

## 了解有关附加属性的详细信息<a name="more"></a>

- 有关如何创建附加属性的详细信息，请参阅[注册附加属性](how-to-register-an-attached-property.md)。

- 有关依赖属性和附加属性的更多高级使用方案，请参阅[自定义依赖属性](custom-dependency-properties.md)。

- 还可将属性注册为附加属性和依赖属性，但仍需公开“包装器”实现。 在这种情况下，属性可在该元素上设置，也可通过 XAML 附加属性语法在任何元素上设置。 <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>使用适用于标准和附加用法的适当方案的属性示例。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.DependencyProperty>
- [依赖项属性概述](dependency-properties-overview.md)
- [自定义依赖属性](custom-dependency-properties.md)
- [XAML 概述 (WPF)](xaml-overview-wpf.md)
- [注册附加属性](how-to-register-an-attached-property.md)
