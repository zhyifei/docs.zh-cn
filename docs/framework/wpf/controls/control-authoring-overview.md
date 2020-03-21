---
title: 控件创作概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], authoring overview
- authoring overview for controls [WPF]
ms.assetid: 3d864748-cff0-4e63-9b23-d8e5a635b28f
ms.openlocfilehash: d5dd2d962c554b860fb6f68110945d56c4ee03ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401027"
---
# <a name="control-authoring-overview"></a>控件创作概述

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 控件模型的扩展性极大地减少了创建新控件的需要。 但在某些情况下，仍可能需要创建自定义控件。 本主题讨论可最大限度减少在 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中创建自定义控件以及其他控件创作模型的需要的功能。 本主题还演示如何创建新控件。

<a name="when_to_write_a_new_control"></a>

## <a name="alternatives-to-writing-a-new-control"></a>编写新控件的替代方法

以前，如果要通过现有控件获取自定义体验，只能更改控件的标准属性，例如背景色、边框宽度和字号。 如果希望在这些预定义参数的基础之上扩展控件的外观或行为，则需要创建新控件，常用的方法是继承现有控件并重写负责绘制该控件的方法。  虽然这仍是一种可选方法，但也可以利用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的丰富内容模型、样式、模板和触发器来自定义现有的控件。 下表提供了一些示例，演示如何在不创建新控件的情况下使用这些功能来实现一致的自定义体验。

- **丰富内容。** 很多标准 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件都支持丰富内容。 例如，内容<xref:System.Windows.Controls.Button>属性的类型<xref:System.Object>为 ，因此理论上任何内容都可以显示在<xref:System.Windows.Controls.Button>上。  要有一个按钮显示图像和文本，可以将图像和<xref:System.Windows.Controls.TextBlock>添加到<xref:System.Windows.Controls.StackPanel>，并将<xref:System.Windows.Controls.StackPanel>分配给 属性。 <xref:System.Windows.Controls.ContentControl.Content%2A> 由于这些控件可以显示 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 视觉元素和任意数据，因此，降低了创建新控件或修改现有控件来支持复杂可视化效果的需求。 有关 中<xref:System.Windows.Controls.Button>的内容模型和其他内容模型的详细信息[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，请参阅[WPF 内容模型](wpf-content-model.md)。

- **风格。** A<xref:System.Windows.Style>是表示控件属性的值的集合。 使用样式可创建所需控件外观和行为的可重用表示形式，而无需编写新控件。 例如，假设您希望所有<xref:System.Windows.Controls.TextBlock>控件具有字体大小为 14 的红色 Arial 字体。 可以创建一个样式作为资源，并相应设置适当属性。 然后，<xref:System.Windows.Controls.TextBlock>添加到应用程序的每个外观都将具有相同的外观。

- **数据模板。** A<xref:System.Windows.DataTemplate>使您能够自定义数据在控件上的显示方式。 例如，可用于<xref:System.Windows.DataTemplate>指定数据在 中的<xref:System.Windows.Controls.ListBox>显示方式。  有关这种情况的示例，请参阅[数据模块化概述](../data/data-templating-overview.md)。  除了自定义数据的外观外，a<xref:System.Windows.DataTemplate>还可以包含 UI 元素，这为您提供了自定义 UI 的很大灵活性。  例如，通过使用 ，<xref:System.Windows.DataTemplate>可以创建 一个<xref:System.Windows.Controls.ComboBox>，其中每个项目都包含一个复选框。

- **控件模板。** 中的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]许多控件使用<xref:System.Windows.Controls.ControlTemplate>定义控件的结构和外观，这将控件的外观与控件的功能分开。 您可以通过重新定义控件的外观来大幅更改其<xref:System.Windows.Controls.ControlTemplate>外观。  例如，假设需要一个看起来像交通信号灯的控件。 此控件具有简单的用户界面和功能。  该控件有三个圆圈，一次只有一个圆圈亮起。 经过一些思考后，您可能会意识到<xref:System.Windows.Controls.RadioButton>， 提供一次只选择一个功能的功能， 但 默认<xref:System.Windows.Controls.RadioButton>的外观看起来与红绿灯上的灯光一样。  由于<xref:System.Windows.Controls.RadioButton>使用控件模板定义其外观，因此很容易重新定义<xref:System.Windows.Controls.ControlTemplate>，以适应控件的要求，并使用单选按钮来使工作点亮。

  > [!NOTE]
  > 尽管<xref:System.Windows.Controls.RadioButton>可以使用<xref:System.Windows.DataTemplate>a<xref:System.Windows.DataTemplate>是不够的此示例中。  定义<xref:System.Windows.DataTemplate>控件内容的外观。 在 的情况下<xref:System.Windows.Controls.RadioButton>，内容是圆右侧显示的任何内容，指示是否选择了 。 <xref:System.Windows.Controls.RadioButton>  在交通信号灯的示例中，单选按钮只需要是可“点亮”的圆圈。 由于停止灯的外观要求与 的默认外观非常不同<xref:System.Windows.Controls.RadioButton>，因此有必要重新定义 。 <xref:System.Windows.Controls.ControlTemplate>  通常，用于<xref:System.Windows.DataTemplate>定义控件的内容（或数据），并且<xref:System.Windows.Controls.ControlTemplate>用于定义控件的结构。

- **触发器。** 允许您<xref:System.Windows.Trigger>动态更改控件的外观和行为，而无需创建新控件。 例如，假设您应用程序中有多个<xref:System.Windows.Controls.ListBox>控件，并希望每个<xref:System.Windows.Controls.ListBox>控件中的项在选择时为粗体和红色。 您的第一本能可能是创建一个类，该类继承<xref:System.Windows.Controls.ListBox>并重写<xref:System.Windows.Controls.Primitives.Selector.OnSelectionChanged%2A>方法以更改所选项的外观，但更好的方法是将触发器添加到更改所选项外观的 样式<xref:System.Windows.Controls.ListBoxItem>。 触发器可以更改属性值或根据属性值执行操作。 使您能够<xref:System.Windows.EventTrigger>在发生事件时执行操作。

有关样式、模板和触发器的详细信息，请参阅[样式设置和模板化](styling-and-templating.md)。

一般情况下，如果控件可以镜像现有控件的功能，但希望该控件具有不同的外观，则应先考虑是否可以使用本节中讨论的某些方法来更改现有控件的外观。

<a name="models_for_control_authoring"></a>

## <a name="models-for-control-authoring"></a>控件创作模型

通过丰富内容模型、样式、模板和触发器，最大程度地减少创建新控件的需要。 但是，如果确实需要创建新控件，则理解 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中的不同控件创作模型就显得非常重要。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供三个用于创建控件的常规模型，每个模型都提供不同的功能集和灵活度。 三个模型的基础类是<xref:System.Windows.Controls.UserControl>，<xref:System.Windows.Controls.Control>和<xref:System.Windows.FrameworkElement>。

### <a name="deriving-from-usercontrol"></a>从 UserControl 派生

创建 控件[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的最简单方法是派生自<xref:System.Windows.Controls.UserControl>。 生成从<xref:System.Windows.Controls.UserControl>继承的控件时，将现有组件添加到 中<xref:System.Windows.Controls.UserControl>的 命名组件和引用事件处理程序。 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 随后可以在代码中引用命名的元素和定义事件处理程序。 此开发模型与用于在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中开发应用程序的模型非常相似。

如果构建正确，则<xref:System.Windows.Controls.UserControl>可以利用丰富的内容、样式和触发器的优势。 但是，如果控件继承自<xref:System.Windows.Controls.UserControl>，则使用控件的用户将无法使用<xref:System.Windows.DataTemplate>或<xref:System.Windows.Controls.ControlTemplate>自定义其外观。  必须从<xref:System.Windows.Controls.Control>类或其派生类之一（除<xref:System.Windows.Controls.UserControl>）派生才能创建支持模板的自定义控件。

#### <a name="benefits-of-deriving-from-usercontrol"></a>从 UserControl 派生的优点

请考虑派生，<xref:System.Windows.Controls.UserControl>如果以下所有都适用：

- 希望采用与生成应用程序相似的方法生成控件。

- 控件仅包含现有组件。

- 无需支持复杂的自定义项。

### <a name="deriving-from-control"></a>从 Control 派生

从类<xref:System.Windows.Controls.Control>派生是大多数现有[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]控件使用的模型。 创建从<xref:System.Windows.Controls.Control>类继承的控件时，可以使用模板定义其外观。 通过这种方式，可以将运算逻辑从视觉表示形式中分离出来。 还可以通过使用命令和绑定而不是事件来确保 UI 和逻辑的分离，并尽可能避免引用 中<xref:System.Windows.Controls.ControlTemplate>的元素。  如果控件的 UI 和逻辑已正确分离，则控件的用户可以重新定义控件的<xref:System.Windows.Controls.ControlTemplate>，以自定义其外观。 尽管构建自定义<xref:System.Windows.Controls.Control>不像构建 一<xref:System.Windows.Controls.UserControl>样简单，但自定义<xref:System.Windows.Controls.Control>提供了最大的灵活性。

#### <a name="benefits-of-deriving-from-control"></a>从 Control 派生的优点

请考虑派生，<xref:System.Windows.Controls.Control>而不是使用类，<xref:System.Windows.Controls.UserControl>如果以下任一适用：

- 您希望控件的外观可以通过 进行<xref:System.Windows.Controls.ControlTemplate>自定义。

- 希望控件支持不同的主题。

### <a name="deriving-from-frameworkelement"></a>从 FrameworkElement 派生

派生或<xref:System.Windows.Controls.UserControl><xref:System.Windows.Controls.Control>依赖于组合现有元素的控件。 对于许多方案，这是一个可接受的解决方案，因为从<xref:System.Windows.FrameworkElement>继承的任何对象都可以位于 中。 <xref:System.Windows.Controls.ControlTemplate> 但是，某些时候，简单的元素组合不能满足控件的外观需要。 对于这些方案，基于<xref:System.Windows.FrameworkElement>组件是正确的选择。

基于构建<xref:System.Windows.FrameworkElement>的组件有两种标准方法：直接呈现和自定义元素组合。 直接呈现涉及重写<xref:System.Windows.UIElement.OnRender%2A>和<xref:System.Windows.FrameworkElement>提供<xref:System.Windows.Media.DrawingContext>显式定义组件视觉对象的操作。 这是<xref:System.Windows.Controls.Image>和<xref:System.Windows.Controls.Border>使用 的方法。 自定义元素组合涉及使用类型<xref:System.Windows.Media.Visual>对象来组合组件的外观。 有关示例，请参阅[使用 DrawingVisual 对象](../graphics-multimedia/using-drawingvisual-objects.md)。 <xref:System.Windows.Controls.Primitives.Track>是 中使用自定义元素组合的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]控件的示例。 在同一控件中，也可以混合使用直接呈现和自定义元素组合。

#### <a name="benefits-of-deriving-from-frameworkelement"></a>从 FrameworkElement 派生的优点

请考虑派生，<xref:System.Windows.FrameworkElement>如果以下任何一项适用：

- 希望对控件的外观进行精确控制，而不仅仅是简单的元素组合提供的效果。

- 希望通过定义自己的呈现逻辑来定义控件的外观。

- 您希望以新颖的方式撰写现有元素，超越 和<xref:System.Windows.Controls.UserControl><xref:System.Windows.Controls.Control>。

<a name="control_authoring_basics"></a>

## <a name="control-authoring-basics"></a>控件创作基础知识

如前所述，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的最强大功能之一在于，它能够在不需要创建自定义控件的情况下，不只是通过设置控件的基本属性来更改其外观和行为。 样式设置、数据绑定和触发器功能通过 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 属性系统和 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 事件系统实现。 以下各部分介绍应遵循的一些做法（与创建自定义控件时所用的模型无关），以便自定义控件的用户可以像使用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 附带的控件一样使用这些功能。

### <a name="use-dependency-properties"></a>使用依赖属性

当属性为依赖属性时，可以执行以下操作：

- 在样式中设置该属性。

- 将该属性绑定到数据源。

- 使用动态资源作为该属性的值。

- 对该属性进行动画处理。

如果希望控件的属性支持以上任一功能，应将该属性实现为依赖属性。 下面的示例通过执行以下操作定义一个名为 `Value` 的依赖属性：

- 定义<xref:System.Windows.DependencyProperty>`ValueProperty`指定为字段的`public``static``readonly`标识符。

- 通过调用<xref:System.Windows.DependencyProperty.Register%2A?displayProperty=nameWithType>向属性系统注册属性名称，以指定以下内容：

  - 属性的名称。

  - 属性类型。

  - 拥有属性的类型。

  - 属性的元数据。 元数据包含属性的默认值 a<xref:System.Windows.CoerceValueCallback>和 。 <xref:System.Windows.PropertyChangedCallback>

- 定义名为 的`Value`CLR 包装器属性，该属性与用于注册依赖项属性的名称相同，通过实现属性`get`和`set`访问器。 请注意，`get`和`set`访问器仅分别调用<xref:System.Windows.DependencyObject.GetValue%2A><xref:System.Windows.DependencyObject.SetValue%2A>。 建议依赖项属性的访问器不包含其他逻辑，因为客户端可以[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]绕过访问器并<xref:System.Windows.DependencyObject.GetValue%2A><xref:System.Windows.DependencyObject.SetValue%2A>直接调用。 例如，如果属性绑定到数据源，则不会调用该属性的 `set` 访问器。  与其向 get 和设置访问器添加其他逻辑，请使用<xref:System.Windows.ValidateValueCallback>和<xref:System.Windows.CoerceValueCallback><xref:System.Windows.PropertyChangedCallback>委托在值更改时响应或检查该值。  有关这些回叫的详细信息，请参阅[依赖属性回叫和验证](../advanced/dependency-property-callbacks-and-validation.md)。

- 定义命名<xref:System.Windows.CoerceValueCallback>`CoerceValue`的方法。 `CoerceValue` 确保 `Value` 大于或等于 `MinValue` 且小于或等于 `MaxValue`。

- 定义 名为`OnValueChanged`的方法<xref:System.Windows.PropertyChangedCallback>。 `OnValueChanged`创建一<xref:System.Windows.RoutedPropertyChangedEventArgs%601>个对象并准备引发`ValueChanged`路由事件。 路由事件在下一节中讨论。

[!code-csharp[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#dependencyproperty)]
[!code-vb[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#dependencyproperty)]

有关详细信息，请参阅[自定义依赖属性](../advanced/custom-dependency-properties.md)。

### <a name="use-routed-events"></a>使用路由事件

正如依赖项属性扩展了具有附加功能的 CLR 属性的概念一样，路由事件扩展了标准 CLR 事件的概念。 在创建新的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件时，将事件实现为路由事件也是一种好方法，因为路由事件支持以下行为：

- 事件可以在多个控件的父级上进行处理。 如果事件是浮升事件，元素树中的单个父级可订阅该事件。 然后，应用程序作者可以使用一个处理程序来响应多个控件的该事件。 例如，如果控件是 中<xref:System.Windows.Controls.ListBox>每个项的一部分（因为它包含在<xref:System.Windows.DataTemplate>中），则应用程序开发人员可以在 上为控件的事件定义事件处理程序。 <xref:System.Windows.Controls.ListBox> 每当其中任何控件发生该事件时，都会调用该事件处理程序。

- 路由事件可以在 中使用 ，<xref:System.Windows.EventSetter>这使应用程序开发人员能够在样式中指定事件的处理程序。

- 路由事件可用于 中，<xref:System.Windows.EventTrigger>这可用于使用[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]对属性进行动画处理。 有关详细信息，请参阅 [动画概述](../graphics-multimedia/animation-overview.md)。

下面的示例通过执行以下操作定义了一个路由事件：

- 定义<xref:System.Windows.RoutedEvent>`ValueChangedEvent`指定为字段的`public``static``readonly`标识符。

- 通过调用<xref:System.Windows.EventManager.RegisterRoutedEvent%2A?displayProperty=nameWithType>方法注册路由事件。 该示例指定调用 时的以下信息<xref:System.Windows.EventManager.RegisterRoutedEvent%2A>：

  - 事件名称是 `ValueChanged`。

  - 路由策略为<xref:System.Windows.RoutingStrategy.Bubble>，这意味着首先调用源上的事件处理程序（引发事件的对象），然后连续调用源父元素上的事件处理程序，从最近父元素上的事件处理程序开始。

  - 事件处理程序的类型是<xref:System.Windows.RoutedPropertyChangedEventHandler%601>， 用<xref:System.Decimal>类型构造。

  - 该事件的所属类型为 `NumericUpDown`。

- 声明一个名为 `ValueChanged` 的公共事件，并包含事件访问器声明。 访问器声明<xref:System.Windows.UIElement.AddHandler%2A>和`add`<xref:System.Windows.UIElement.RemoveHandler%2A>`remove`访问器声明中的示例调用使用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]事件服务。

- 创建一个名为 `OnValueChanged` 的受保护的虚拟方法，该方法会引发 `ValueChanged` 事件。

[!code-csharp[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#routedevent)]
[!code-vb[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#routedevent)]

有关详细信息，请参阅[路由事件概述](../advanced/routed-events-overview.md)和[创建自定义路由事件](../advanced/how-to-create-a-custom-routed-event.md)。

### <a name="use-binding"></a>使用绑定

若要将控件的 UI 与其逻辑分离，请考虑使用数据绑定。 如果使用 定义控件的外观，则这一点尤其重要<xref:System.Windows.Controls.ControlTemplate>。 使用数据绑定时，或许可以避免在代码中引用 UI 的特定部分。 最好避免引用<xref:System.Windows.Controls.ControlTemplate>中的元素，因为当代码引用 中<xref:System.Windows.Controls.ControlTemplate>的元素并<xref:System.Windows.Controls.ControlTemplate>更改时，引用的元素需要包含在新的<xref:System.Windows.Controls.ControlTemplate>中。

下面的示例更新<xref:System.Windows.Controls.TextBlock>控件，`NumericUpDown`为其分配名称，并在代码中按名称引用文本框。

[!code-xaml[UserControlNumericUpDownSimple#UIRefMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml#uirefmarkup)]

[!code-csharp[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml.cs#uirefcode)]
[!code-vb[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDownSimple/VisualBasic/NumericUpDown.xaml.vb#uirefcode)]

下面的示例使用绑定来达到相同的目的。

[!code-xaml[UserControlNumericUpDown#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml#binding)]

有关数据绑定的详细信息，请参阅[数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)。

### <a name="design-for-designers"></a>设计器的设计

要在 Visual Studio 的 WPF 设计器中接收对自定义 WPF 控件的支持（例如，使用"属性"窗口进行属性编辑），请遵循以下准则。  有关为 WPF 设计器进行开发的详细信息，请参阅[可视化工作室中的 XAML 设计](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)。

#### <a name="dependency-properties"></a>依赖项属性

请务必实现 CLR`get`和`set`访问器，如前面所述，在"使用依赖项属性"。 设计器可以使用包装器来检测某个依赖属性是否存在，但与 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 和控件客户端一样，在获取或设置属性时不需要使用设计器来调用访问器。

#### <a name="attached-properties"></a>附加属性

应使用以下准则在自定义控件上实现附加属性：

- `readonly`<xref:System.Windows.DependencyProperty>*PropertyName*`Property`具有使用<xref:System.Windows.DependencyProperty.RegisterAttached%2A>方法创建的窗体属性名称。 `public` `static` 传递给的属性名称<xref:System.Windows.DependencyProperty.RegisterAttached%2A>必须与*属性名称匹配*。

- 实现一对名为`Set`*属性名称*和`Get`*属性名称*的 `public` `static` CLR 方法。 这两种方法都应接受派生为<xref:System.Windows.DependencyProperty>第一个参数的类。 `Set`*属性名称*方法还接受其类型与属性的注册数据类型匹配的参数。 `Get`*属性名称* 方法应返回相同类型的值。 如果缺少 `Set`*属性名称*方法，则该属性标记为只读。

- `Set`*属性名称*和`Get`*属性名称*必须分别直接路由到<xref:System.Windows.DependencyObject.GetValue%2A><xref:System.Windows.DependencyObject.SetValue%2A>目标依赖项对象和 上的方法。 通过调用方法包装器或直接调用目标依赖对象，设计器可以访问附加属性。

有关附加属性的详细信息，请参阅[附加属性概述](../advanced/attached-properties-overview.md)。

### <a name="define-and-use-shared-resources"></a>定义和使用共享资源

可以将控件包含在应用程序所在的程序集中，也可以将控件打包到可在多个应用程序中使用的单独程序集中。 大多数情况下，不管使用什么方法，本主题中讨论的信息都适用。  但有一处差异值得注意。  将控件放入应用程序所在的程序集中时，可以随意向 App.xaml 文件添加全局资源。 但是，仅包含控件的程序集没有与其关联的<xref:System.Windows.Application>对象，因此 App.xaml 文件不可用。

当应用程序查找资源时，它会按以下顺序在三个级别进行查找：

1. 元素级别。

   系统从引用该资源的元素开始搜索，接着搜索逻辑父级的资源，依此类推，直至到达根元素。

2. 应用程序级别。

   由<xref:System.Windows.Application>对象定义的资源。

3. 主题级别。

   主题级别的字典存储在名为“Themes”的子文件夹中。  Themes 文件夹中的文件与主题对应。  例如，可能有 Aero.NormalColor.xaml、Luna.NormalColor.xaml、Royale.NormalColor.xaml 等。  可能还有一个名为 generic.xaml 的文件。  当系统在主题级别查找资源时，它会先在特定于主题的文件中查找相应资源，然后在 generic.xaml 中进行查找。

当控件位于独立于应用程序的程序集中时，必须将全局资源放在元素级别或主题级别。 这两种方法都各有优点。

#### <a name="defining-resources-at-the-element-level"></a>在元素级别定义资源

可以通过创建自定义资源字典并将其与控件的资源字典合并，在元素级别定义共享资源。  采用此方法时，可以为资源文件指定任意名称，并且资源文件可以与控件位于同一文件夹中。 元素级别的资源还可以使用简单字符串作为键。 下面的示例创建名为<xref:System.Windows.Media.LinearGradientBrush>字典1.xaml的资源文件。

[!code-xaml[SharedResources#1](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/Dictionary1.xaml#1)]

定义字典后，需要将其与控件的资源字典合并。  可以使用 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 或代码执行此操作。

下面的示例通过使用 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 合并资源字典。

[!code-xaml[SharedResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml#2)]

此方法的缺点是每次引用对象时都会<xref:System.Windows.ResourceDictionary>创建对象。  例如，如果库中有 10 个自定义控件，并且使用 XAML 合并每个控件的共享资源字典，则创建 10 个<xref:System.Windows.ResourceDictionary>相同的对象。  可以通过创建一个静态类来合并代码中的资源并返回生成的<xref:System.Windows.ResourceDictionary>，来避免这种情况。

下面的示例创建一个返回共享<xref:System.Windows.ResourceDictionary>的 类。

[!code-csharp[SharedResources#3](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/SharedDictionaryManager.cs#3)]

下面的示例先在一个自定义控件的构造函数中将共享资源与该控件的资源合并，然后再调用 `InitializeComponent`。  由于`SharedDictionaryManager.SharedDictionary`是静态属性，<xref:System.Windows.ResourceDictionary>因此仅创建一次 。 因为资源字典在调用 `InitializeComponent` 前已合并，所以控件可以在它的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件中使用资源。

[!code-csharp[SharedResources#4](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml.cs#4)]

#### <a name="defining-resources-at-the-theme-level"></a>在主题级别定义资源

通过 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 可以为不同的 Windows 主题创建资源。  作为控件作者，可以为特定主题定义资源，以根据所使用的主题更改控件的外观。 例如，Windows<xref:System.Windows.Controls.Button>经典主题（Windows 2000 的默认主题）的外观不同于<xref:System.Windows.Controls.Button>Windows Luna 主题（Windows XP 的默认主题），因为<xref:System.Windows.Controls.Button>每个主题使用不同的<xref:System.Windows.Controls.ControlTemplate>主题。

特定于主题的资源以特定文件名保留在资源字典中。 这些文件必须位于一个名为 `Themes` 的文件夹中，此文件夹是包含该控件的文件夹的子文件夹。 下表列出了资源字典文件以及与每个文件关联的主题：

|资源字典文件名|Windows 主题|
|-----------------------------------|-------------------|
|`Classic.xaml`|Windows XP 中的经典 Windows 9x/2000 外观|
|`Luna.NormalColor.xaml`|Windows XP 上的默认蓝色主题|
|`Luna.Homestead.xaml`|Windows XP 上的橄榄色主题|
|`Luna.Metallic.xaml`|Windows XP 上的银色主题|
|`Royale.NormalColor.xaml`|Windows XP Media Center Edition 上的默认主题|
|`Aero.NormalColor.xaml`|Windows Vista 上的默认主题|

无需为每一种主题都定义资源。 如果没有为特定主题定义资源，控件将在 `Classic.xaml` 中检查资源。 如果在与当前主题对应的文件或 `Classic.xaml` 中没有定义资源，控件将使用常规资源，该资源位于名为 `generic.xaml` 的资源字典文件中。  `generic.xaml` 文件与特定于主题的资源词典文件位于同一文件夹中。 尽管 `generic.xaml` 不与特定的 Windows 主题对应，但它仍是一个主题级别字典。

包含主题和 UI 自动化支持的[C#](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp)或[可视化基本](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic)数字 UpDown 自定义控件包含`NumericUpDown`两个用于该控件的资源字典：一个在泛型.xaml 中，另一个位于 Luna.NormalColor.xaml 中。

将 放入<xref:System.Windows.Controls.ControlTemplate>任何特定于主题的资源字典文件中时，必须为控件创建静态构造函数，并在 上<xref:System.Windows.DependencyProperty.OverrideMetadata%28System.Type%2CSystem.Windows.PropertyMetadata%29><xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>调用 方法，如以下示例所示。

[!code-csharp[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/CSharp/NumericUpDown.cs#staticconstructor)]
[!code-vb[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/visualbasic/numericupdown.vb#staticconstructor)]

##### <a name="defining-and-referencing-keys-for-theme-resources"></a>定义和引用主题资源的键

在元素级别定义资源时，可以指定一个字符串作为它的键，然后通过该字符串访问该资源。 在主题级别定义资源时，必须使用 作为<xref:System.Windows.ComponentResourceKey>键。  以下示例定义 generic.xaml 中的资源。

[!code-xaml[ThemeResourcesControlLibrary#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/Themes/generic.xaml#5)]

下面的示例通过指定<xref:System.Windows.ComponentResourceKey>为键来引用资源。

[!code-xaml[ThemeResourcesControlLibrary#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/NumericUpDown.xaml#6)]

##### <a name="specifying-the-location-of-theme-resources"></a>指定主题资源的位置

若要找到控件的资源，承载应用程序需要知道相应程序集包含特定于控件的资源。 可以通过将 添加到<xref:System.Windows.ThemeInfoAttribute>包含控件的程序集来实现此目的。 具有<xref:System.Windows.ThemeInfoAttribute>指定通用<xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A>资源位置的属性，以及指定特定于主题的资源的位置<xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A>的属性。

下面的示例将 和<xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A><xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A>属性设置<xref:System.Windows.ResourceDictionaryLocation.SourceAssembly>到 ，以指定泛型和主题特定的资源与控件位于同一程序集中。

[!code-csharp[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/Properties/AssemblyInfo.cs#themessection)]
[!code-vb[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/my project/assemblyinfo.vb#themessection)]

## <a name="see-also"></a>另请参阅

- [在 Visual Studio 中设计 XAML](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [WPF 中的 Pack URI](../app-development/pack-uris-in-wpf.md)
- [控件自定义](control-customization.md)
