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
ms.openlocfilehash: 3ea5519259ba2ee31bfd6bc25f6bedf1f1250799
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401542"
---
# <a name="control-authoring-overview"></a>控件创作概述

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 控件模型的扩展性极大地减少了创建新控件的需要。 但在某些情况下，仍可能需要创建自定义控件。 本主题讨论可最大限度减少在 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中创建自定义控件以及其他控件创作模型的需要的功能。 本主题还演示如何创建新控件。

<a name="when_to_write_a_new_control"></a>

## <a name="alternatives-to-writing-a-new-control"></a>编写新控件的替代方法

以前，如果要通过现有控件获取自定义体验，只能更改控件的标准属性，例如背景色、边框宽度和字号。 如果希望在这些预定义参数的基础之上扩展控件的外观或行为，则需要创建新控件，常用的方法是继承现有控件并重写负责绘制该控件的方法。  虽然这仍是一种可选方法，但也可以利用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的丰富内容模型、样式、模板和触发器来自定义现有的控件。 下表提供了一些示例，演示如何在不创建新控件的情况下使用这些功能来实现一致的自定义体验。

- **丰富内容。** 很多标准 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件都支持丰富内容。 例如, 的内容属性<xref:System.Windows.Controls.Button>的类型<xref:System.Object>为, 因此理论上<xref:System.Windows.Controls.Button>可以在上显示任何内容。  若要让按钮显示图像和文本, 可以将图像<xref:System.Windows.Controls.TextBlock>和添加<xref:System.Windows.Controls.StackPanel>到, <xref:System.Windows.Controls.ContentControl.Content%2A>并将分配<xref:System.Windows.Controls.StackPanel>给属性。 由于这些控件可以显示 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 视觉元素和任意数据，因此，降低了创建新控件或修改现有控件来支持复杂可视化效果的需求。 有关中<xref:System.Windows.Controls.Button> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的和其他内容模型的内容模型的详细信息, 请参阅[WPF 内容模型](wpf-content-model.md)。

- **样式。** <xref:System.Windows.Style>是表示控件属性的值的集合。 使用样式可创建所需控件外观和行为的可重用表示形式，而无需编写新控件。 例如, 假设您希望所有<xref:System.Windows.Controls.TextBlock>控件都具有红色的 Arial 字体, 字体大小为14。 可以创建一个样式作为资源，并相应设置适当属性。 然后, <xref:System.Windows.Controls.TextBlock>添加到应用程序中的每个都具有相同的外观。

- **数据模板。** <xref:System.Windows.DataTemplate>利用, 您可以自定义数据在控件上的显示方式。 例如, <xref:System.Windows.DataTemplate>可用于指定如何<xref:System.Windows.Controls.ListBox>在中显示数据。  有关这种情况的示例，请参阅[数据模块化概述](../data/data-templating-overview.md)。  除了自定义数据的外观以外, <xref:System.Windows.DataTemplate>还可以包括 UI 元素, 这为你提供了自定义 ui 的很大灵活性。  例如, 通过使用<xref:System.Windows.DataTemplate>, 可以创建一个<xref:System.Windows.Controls.ComboBox> , 其中每一项都包含一个复选框。

- **控件模板。** 中的许多[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]控件都<xref:System.Windows.Controls.ControlTemplate>使用来定义控件的结构和外观, 将控件的外观与控件的功能分隔开来。 通过重新定义<xref:System.Windows.Controls.ControlTemplate>控件的外观, 可以极大地更改控件的外观。  例如，假设需要一个看起来像交通信号灯的控件。 此控件具有简单的用户界面和功能。  该控件有三个圆圈，一次只有一个圆圈亮起。 在某些反射后, 你可能会意识<xref:System.Windows.Controls.RadioButton>到, 一次只能选择一项功能, 但的默认外观<xref:System.Windows.Controls.RadioButton>看起来不像是交通信号灯上的灯。  由于使用控件模板来定义其外观, 因此, 可以轻松地<xref:System.Windows.Controls.ControlTemplate>重新定义以满足控件要求, 并使用单选按钮来创建停止信号。 <xref:System.Windows.Controls.RadioButton>

  > [!NOTE]
  > 尽管可以使用, 但在此示例中是不够的<xref:System.Windows.DataTemplate>。 <xref:System.Windows.DataTemplate> <xref:System.Windows.Controls.RadioButton>  <xref:System.Windows.DataTemplate>定义控件内容的外观。 如果<xref:System.Windows.Controls.RadioButton>是, 则内容将显示在圆右侧, 指示<xref:System.Windows.Controls.RadioButton>是否选中了。  在交通信号灯的示例中，单选按钮只需要是可“点亮”的圆圈。 由于停止信号的外观要求不同于的默认外观<xref:System.Windows.Controls.RadioButton>, 因此需要<xref:System.Windows.Controls.ControlTemplate>重新定义。  通常<xref:System.Windows.DataTemplate> , 用于定义控件的内容 (或数据), <xref:System.Windows.Controls.ControlTemplate>用于定义控件的构造方式。

- **触发器。** <xref:System.Windows.Trigger>允许您动态更改控件的外观和行为, 而无需创建新的控件。 例如, 假设应用程序中有<xref:System.Windows.Controls.ListBox>多个控件, 并希望每个<xref:System.Windows.Controls.ListBox>控件在被选中时均为粗体和红色。 你的第一个 instinct 可能是创建一个继承自<xref:System.Windows.Controls.ListBox>的类, 并<xref:System.Windows.Controls.Primitives.Selector.OnSelectionChanged%2A>重写方法以更改所选项的外观, 但更好的方法是将一个触发器添加<xref:System.Windows.Controls.ListBoxItem>到的样式, 该样式将更改的外观选定的项。 触发器可以更改属性值或根据属性值执行操作。 使用<xref:System.Windows.EventTrigger>可以在发生事件时执行操作。

有关样式、模板和触发器的详细信息，请参阅[样式设置和模板化](styling-and-templating.md)。

一般情况下，如果控件可以镜像现有控件的功能，但希望该控件具有不同的外观，则应先考虑是否可以使用本节中讨论的某些方法来更改现有控件的外观。

<a name="models_for_control_authoring"></a>

## <a name="models-for-control-authoring"></a>控件创作模型

通过丰富内容模型、样式、模板和触发器，最大程度地减少创建新控件的需要。 但是，如果确实需要创建新控件，则理解 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中的不同控件创作模型就显得非常重要。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供三个用于创建控件的常规模型，每个模型都提供不同的功能集和灵活度。 这三个模型的基类分别<xref:System.Windows.Controls.UserControl>为、 <xref:System.Windows.Controls.Control>和。 <xref:System.Windows.FrameworkElement>

### <a name="deriving-from-usercontrol"></a>从 UserControl 派生

在中[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]创建控件的最简单方法是从<xref:System.Windows.Controls.UserControl>派生。 当生成从<xref:System.Windows.Controls.UserControl>继承的控件时, 可以将现有组件添加<xref:System.Windows.Controls.UserControl>到中, 将组件命名为, 并在中[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]引用事件处理程序。 随后可以在代码中引用命名的元素和定义事件处理程序。 此开发模型与用于在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中开发应用程序的模型非常相似。

如果已正确生成, <xref:System.Windows.Controls.UserControl>则可以利用丰富内容、样式和触发器的优点。 但是, 如果您的控件继承<xref:System.Windows.Controls.UserControl>自, 则使用您的<xref:System.Windows.DataTemplate>控件的用户将无法使用或<xref:System.Windows.Controls.ControlTemplate>来自定义其外观。  需要从<xref:System.Windows.Controls.Control>类或它的派生类之一 (而不<xref:System.Windows.Controls.UserControl>是) 派生, 以创建支持模板的自定义控件。

#### <a name="benefits-of-deriving-from-usercontrol"></a>从 UserControl 派生的优点

如果满足以下<xref:System.Windows.Controls.UserControl>所有条件, 请考虑从派生:

- 希望采用与生成应用程序相似的方法生成控件。

- 控件仅包含现有组件。

- 无需支持复杂的自定义项。

### <a name="deriving-from-control"></a>从 Control 派生

从<xref:System.Windows.Controls.Control>类派生是大多数现有[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]控件使用的模型。 创建从<xref:System.Windows.Controls.Control>类继承的控件时, 可以使用模板定义其外观。 通过这种方式，可以将运算逻辑从视觉表示形式中分离出来。 你还可以通过使用命令和绑定而不是事件, 并尽可能避免引用元素<xref:System.Windows.Controls.ControlTemplate> , 来确保分离 UI 和逻辑。  如果控件的 UI 和逻辑已正确分离, 则控件的用户可以重新定义控件的<xref:System.Windows.Controls.ControlTemplate>以自定义其外观。 尽管构建自定义<xref:System.Windows.Controls.Control>并不像<xref:System.Windows.Controls.UserControl>构建一样简单, 但自定义<xref:System.Windows.Controls.Control>可提供最大的灵活性。

#### <a name="benefits-of-deriving-from-control"></a>从 Control 派生的优点

如果满足以下<xref:System.Windows.Controls.Control>任一条件, 请<xref:System.Windows.Controls.UserControl>考虑从派生而不是使用类:

- 希望可以通过<xref:System.Windows.Controls.ControlTemplate>自定义控件的外观。

- 希望控件支持不同的主题。

### <a name="deriving-from-frameworkelement"></a>从 FrameworkElement 派生

派生自<xref:System.Windows.Controls.UserControl>或<xref:System.Windows.Controls.Control>依赖于组合现有元素的控件。 在许多情况下, 这是一个可接受的解决方案, 因为从<xref:System.Windows.FrameworkElement>继承的任何对象都可以位于中。 <xref:System.Windows.Controls.ControlTemplate> 但是，某些时候，简单的元素组合不能满足控件的外观需要。 在这些情况下, 基于<xref:System.Windows.FrameworkElement>的组件是正确的选择。

基于生成<xref:System.Windows.FrameworkElement>的组件有两种标准方法: 直接呈现和自定义元素组合。 直接呈现涉及重写<xref:System.Windows.UIElement.OnRender%2A>的<xref:System.Windows.FrameworkElement>方法和提供<xref:System.Windows.Media.DrawingContext>显式定义组件视觉对象的操作。 这是<xref:System.Windows.Controls.Image>和<xref:System.Windows.Controls.Border>使用的方法。 自定义元素组合涉及使用类型<xref:System.Windows.Media.Visual>的对象来编写组件的外观。 有关示例，请参阅[使用 DrawingVisual 对象](../graphics-multimedia/using-drawingvisual-objects.md)。 <xref:System.Windows.Controls.Primitives.Track>是中[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的控件的一个示例, 它使用自定义元素组合。 在同一控件中，也可以混合使用直接呈现和自定义元素组合。

#### <a name="benefits-of-deriving-from-frameworkelement"></a>从 FrameworkElement 派生的优点

如果满足以下<xref:System.Windows.FrameworkElement>任一情况, 请考虑从派生:

- 希望对控件的外观进行精确控制，而不仅仅是简单的元素组合提供的效果。

- 希望通过定义自己的呈现逻辑来定义控件的外观。

- 你需要以 novel 的方式撰写现有元素, 这超出了<xref:System.Windows.Controls.UserControl>和<xref:System.Windows.Controls.Control>的可能。

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

- 将名`ValueProperty`为的<xref:System.Windows.DependencyProperty> `public`标识符定义为字段。`static` `readonly`

- 通过调用<xref:System.Windows.DependencyProperty.Register%2A?displayProperty=nameWithType>将属性名称注册到属性系统, 以指定以下各项:

  - 属性的名称。

  - 属性的类型。

  - 拥有属性的类型。

  - 属性的元数据。 元数据包含属性的默认值<xref:System.Windows.CoerceValueCallback> <xref:System.Windows.PropertyChangedCallback>和。

- 通过实现属性的`Value` `get`和`set`访问器, 定义一个名为的 CLR 包装器属性, 该属性与用于注册依赖属性的名称相同。 请注意, `set` <xref:System.Windows.DependencyObject.GetValue%2A> <xref:System.Windows.DependencyObject.SetValue%2A>和访问器只能分别调用和。 `get` 建议依赖属性的访问器不包含其他逻辑, 因为客户端和[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]可以绕过访问器并直接调用<xref:System.Windows.DependencyObject.SetValue%2A> <xref:System.Windows.DependencyObject.GetValue%2A>和。 例如，如果属性绑定到数据源，则不会调用该属性的 `set` 访问器。  不要将其他逻辑添加到 get 和 set 访问器, 而是<xref:System.Windows.ValidateValueCallback>使用<xref:System.Windows.CoerceValueCallback>、和<xref:System.Windows.PropertyChangedCallback>委托来响应或检查其更改时的值。  有关这些回叫的详细信息，请参阅[依赖属性回叫和验证](../advanced/dependency-property-callbacks-and-validation.md)。

- 定义名<xref:System.Windows.CoerceValueCallback> `CoerceValue`为的方法。 `CoerceValue` 确保 `Value` 大于或等于 `MinValue` 且小于或等于 `MaxValue`。

- 定义名<xref:System.Windows.PropertyChangedCallback> `OnValueChanged`为的方法。 `OnValueChanged`创建一个<xref:System.Windows.RoutedPropertyChangedEventArgs%601>对象并准备`ValueChanged`引发路由事件。 路由事件在下一节中讨论。

[!code-csharp[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#dependencyproperty)]
[!code-vb[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#dependencyproperty)]

有关详细信息，请参阅[自定义依赖属性](../advanced/custom-dependency-properties.md)。

### <a name="use-routed-events"></a>使用路由事件

正如依赖属性扩展具有其他功能的 CLR 属性的概念一样, 路由事件扩展了标准 CLR 事件的概念。 在创建新的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件时，将事件实现为路由事件也是一种好方法，因为路由事件支持以下行为：

- 事件可以在多个控件的父级上进行处理。 如果事件是浮升事件，元素树中的单个父级可订阅该事件。 然后，应用程序作者可以使用一个处理程序来响应多个控件的该事件。 例如, 如果您的控件是中<xref:System.Windows.Controls.ListBox>的每一项的一部分 (因为它包含<xref:System.Windows.DataTemplate>在中), 则应用程序开发人员可以在上定义<xref:System.Windows.Controls.ListBox>控件的事件的事件处理程序。 每当其中任何控件发生该事件时，都会调用该事件处理程序。

- 可以在中<xref:System.Windows.EventSetter>使用路由事件, 使应用程序开发人员能够在样式中指定事件的处理程序。

- 路由事件可在中<xref:System.Windows.EventTrigger>使用, 这对通过使用[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]对属性进行动画处理非常有用。 有关详细信息，请参阅 [动画概述](../graphics-multimedia/animation-overview.md)。

下面的示例通过执行以下操作定义了一个路由事件：

- 将名`ValueChangedEvent`为的<xref:System.Windows.RoutedEvent> `public`标识符定义为字段。`static` `readonly`

- 通过调用<xref:System.Windows.EventManager.RegisterRoutedEvent%2A?displayProperty=nameWithType>方法来注册路由事件。 该示例在调用<xref:System.Windows.EventManager.RegisterRoutedEvent%2A>时指定以下信息:

  - 事件名称是 `ValueChanged`。

  - 路由策略是<xref:System.Windows.RoutingStrategy.Bubble>, 这意味着将首先调用源 (引发事件的对象) 上的事件处理程序, 然后连续调用源的父元素上的事件处理程序, 并从最近父元素。

  - 事件处理程序的类型为<xref:System.Windows.RoutedPropertyChangedEventHandler%601>, <xref:System.Decimal>使用类型构造。

  - 该事件的所属类型为 `NumericUpDown`。

- 声明一个名为 `ValueChanged` 的公共事件，并包含事件访问器声明。 <xref:System.Windows.UIElement.AddHandler%2A>该示例<xref:System.Windows.UIElement.RemoveHandler%2A> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]在`add`访问器声明和访问器声明`remove`中调用, 以使用事件服务。

- 创建一个名为 `OnValueChanged` 的受保护的虚拟方法，该方法会引发 `ValueChanged` 事件。

[!code-csharp[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#routedevent)]
[!code-vb[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#routedevent)]

有关详细信息，请参阅[路由事件概述](../advanced/routed-events-overview.md)和[创建自定义路由事件](../advanced/how-to-create-a-custom-routed-event.md)。

### <a name="use-binding"></a>使用绑定

若要将控件的 UI 与其逻辑分离，请考虑使用数据绑定。 如果你使用<xref:System.Windows.Controls.ControlTemplate>定义控件的外观, 则这一点尤其重要。 使用数据绑定时，或许可以避免在代码中引用 UI 的特定部分。 最好避免引用<xref:System.Windows.Controls.ControlTemplate>中的元素, 因为当代码引用<xref:System.Windows.Controls.ControlTemplate>中的元素并且<xref:System.Windows.Controls.ControlTemplate>更改时, 所引用的元素需要包括在新<xref:System.Windows.Controls.ControlTemplate>的中。

下面的示例更新<xref:System.Windows.Controls.TextBlock> `NumericUpDown`控件的, 并为其指定名称并按名称在代码中引用 textbox。

[!code-xaml[UserControlNumericUpDownSimple#UIRefMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml#uirefmarkup)]

[!code-csharp[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml.cs#uirefcode)]
[!code-vb[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDownSimple/VisualBasic/NumericUpDown.xaml.vb#uirefcode)]

下面的示例使用绑定来达到相同的目的。

[!code-xaml[UserControlNumericUpDown#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml#binding)]

有关数据绑定的详细信息，请参阅[数据绑定概述](../data/data-binding-overview.md)。

### <a name="design-for-designers"></a>设计器的设计

若要在 [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] 中获得对自定义 WPF 控件的支持（例如，使用“属性”窗口编辑属性），请遵循以下准则。  有关针对[!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]开发的详细信息, 请参阅[在 Visual Studio 中设计 XAML](/visualstudio/designers/designing-xaml-in-visual-studio)。

#### <a name="dependency-properties"></a>依赖项属性

请确保按前面介绍`get`的`set` "使用依赖属性" 中所述实现 CLR 和取值函数。 设计器可以使用包装器来检测某个依赖属性是否存在，但与 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 和控件客户端一样，在获取或设置属性时不需要使用设计器来调用访问器。

#### <a name="attached-properties"></a>附加属性

应使用以下准则在自定义控件上实现附加属性：

- `public` 具有使用方法创建`Property`的窗体 PropertyName 的。  <xref:System.Windows.DependencyProperty.RegisterAttached%2A> `static` `readonly` <xref:System.Windows.DependencyProperty> 传递给<xref:System.Windows.DependencyProperty.RegisterAttached%2A>的属性名称必须与*PropertyName*匹配。

- 实现一对名为`Set`*属性名称*和`Get`*属性名称*的 `public` `static` CLR 方法。 这两种方法都应接受从<xref:System.Windows.DependencyProperty>派生的类作为其第一个参数。 `Set`*属性名称*方法还接受其类型与属性的注册数据类型匹配的参数。 `Get`*属性名称* 方法应返回相同类型的值。 如果缺少 `Set`*属性名称*方法，则该属性标记为只读。

- `Set`*Propertyname*和`Get` *propertyname*必须分别直接路由到<xref:System.Windows.DependencyObject.GetValue%2A>目标<xref:System.Windows.DependencyObject.SetValue%2A>依赖对象上的和方法。 通过调用方法包装器或直接调用目标依赖对象，设计器可以访问附加属性。

有关附加属性的详细信息，请参阅[附加属性概述](../advanced/attached-properties-overview.md)。

### <a name="define-and-use-shared-resources"></a>定义和使用共享资源

可以将控件包含在应用程序所在的程序集中，也可以将控件打包到可在多个应用程序中使用的单独程序集中。 大多数情况下，不管使用什么方法，本主题中讨论的信息都适用。  但有一处差异值得注意。  将控件放入应用程序所在的程序集中时，可以随意向 App.xaml 文件添加全局资源。 但仅包含控件的程序集不具有<xref:System.Windows.Application>与其关联的对象, 因此无法使用该应用程序 .xaml 文件。

当应用程序查找资源时，它会按以下顺序在三个级别进行查找：

1. 元素级别。

   系统从引用该资源的元素开始搜索，接着搜索逻辑父级的资源，依此类推，直至到达根元素。

2. 应用程序级别。

   由<xref:System.Windows.Application>对象定义的资源。

3. 主题级别。

   主题级别的字典存储在名为“Themes”的子文件夹中。  Themes 文件夹中的文件与主题对应。  例如，可能有 Aero.NormalColor.xaml、Luna.NormalColor.xaml、Royale.NormalColor.xaml 等。  可能还有一个名为 generic.xaml 的文件。  当系统在主题级别查找资源时，它会先在特定于主题的文件中查找相应资源，然后在 generic.xaml 中进行查找。

当控件位于独立于应用程序的程序集中时，必须将全局资源放在元素级别或主题级别。 这两种方法都各有优点。

#### <a name="defining-resources-at-the-element-level"></a>在元素级别定义资源

可以通过创建自定义资源字典并将其与控件的资源字典合并，在元素级别定义共享资源。  采用此方法时，可以为资源文件指定任意名称，并且资源文件可以与控件位于同一文件夹中。 元素级别的资源还可以使用简单字符串作为键。 以下示例创建名为<xref:System.Windows.Media.LinearGradientBrush> Dictionary1 的资源文件。

[!code-xaml[SharedResources#1](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/Dictionary1.xaml#1)]

定义字典后，需要将其与控件的资源字典合并。  可以使用 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 或代码执行此操作。

下面的示例通过使用 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 合并资源字典。

[!code-xaml[SharedResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml#2)]

此方法的缺点是每次引用<xref:System.Windows.ResourceDictionary>对象时都会创建一个对象。  例如, 如果库中有10个自定义控件, 并使用 XAML 合并了每个控件的共享资源字典, 则可以创建 10 <xref:System.Windows.ResourceDictionary>个相同的对象。  可以通过创建一个在代码中合并资源并返回生成<xref:System.Windows.ResourceDictionary>的静态类来避免这种情况。

下面的示例创建一个返回共享<xref:System.Windows.ResourceDictionary>的类。

[!code-csharp[SharedResources#3](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/SharedDictionaryManager.cs#3)]

下面的示例先在一个自定义控件的构造函数中将共享资源与该控件的资源合并，然后再调用 `InitializeComponent`。  由于是静态属性, 因此仅创建一次。 <xref:System.Windows.ResourceDictionary> `SharedDictionaryManager.SharedDictionary` 因为资源字典在调用 `InitializeComponent` 前已合并，所以控件可以在它的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件中使用资源。

[!code-csharp[SharedResources#4](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml.cs#4)]

#### <a name="defining-resources-at-the-theme-level"></a>在主题级别定义资源

通过 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 可以为不同的 Windows 主题创建资源。  作为控件作者，可以为特定主题定义资源，以根据所使用的主题更改控件的外观。 例如, <xref:System.Windows.Controls.Button>在 windows 经典主题中的外观 (windows 2000 的默认主题) 不同<xref:System.Windows.Controls.Button>于 windows Luna 主题中的 (windows XP 的默认主题), 因为<xref:System.Windows.Controls.Button>使用了不同<xref:System.Windows.Controls.ControlTemplate>的适用于每个主题。

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

[带有主题和 UI 自动化支持的 NumericUpDown 自定义控件示例](https://go.microsoft.com/fwlink/?LinkID=160025)包含两个用于 `NumericUpDown` 控件的资源字典：一个在 generic.xaml 中，另一个在 Luna.NormalColor.xaml 中。  可以运行应用程序并在 Windows XP 中的银色主题和另一主题之间切换，以查看这两个控件模板之间的差别。 （如果运行的是 Windows Vista，可以将 Luna.NormalColor.xaml 重命名为 Aero.NormalColor.xaml，然后在两个主题之间切换，例如在 Windows 经典主题和 Windows Vista 的默认主题之间切换。）

当你将添加<xref:System.Windows.Controls.ControlTemplate>到任何特定于主题的资源字典文件中时, 必须为控件创建一个静态构造函数并对<xref:System.Windows.DependencyProperty.OverrideMetadata%28System.Type%2CSystem.Windows.PropertyMetadata%29>调用方法<xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>, 如下面的示例中所示。

[!code-csharp[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/CSharp/NumericUpDown.cs#staticconstructor)]
[!code-vb[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/visualbasic/numericupdown.vb#staticconstructor)]

##### <a name="defining-and-referencing-keys-for-theme-resources"></a>定义和引用主题资源的键

在元素级别定义资源时，可以指定一个字符串作为它的键，然后通过该字符串访问该资源。 在主题级别定义资源时, 必须使用<xref:System.Windows.ComponentResourceKey>作为键。  以下示例定义 generic.xaml 中的资源。

[!code-xaml[ThemeResourcesControlLibrary#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/Themes/generic.xaml#5)]

下面的示例通过将<xref:System.Windows.ComponentResourceKey>指定为键来引用资源。

[!code-xaml[ThemeResourcesControlLibrary#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/NumericUpDown.xaml#6)]

##### <a name="specifying-the-location-of-theme-resources"></a>指定主题资源的位置

若要找到控件的资源，承载应用程序需要知道相应程序集包含特定于控件的资源。 可以通过将添加<xref:System.Windows.ThemeInfoAttribute>到包含控件的程序集来实现此目的。 具有一个<xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A>属性, 该属性指定泛型资源的位置, 并指定<xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A>一个属性, 该属性指定特定于主题的资源的位置。 <xref:System.Windows.ThemeInfoAttribute>

下面的示例将<xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A>和<xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A>属性设置为<xref:System.Windows.ResourceDictionaryLocation.SourceAssembly>, 以指定泛型和特定于主题的资源与控件位于同一程序集中。

[!code-csharp[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/Properties/AssemblyInfo.cs#themessection)]
[!code-vb[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/my project/assemblyinfo.vb#themessection)]

## <a name="see-also"></a>请参阅

- [在 Visual Studio 中设计 XAML](/visualstudio/designers/designing-xaml-in-visual-studio)
- [WPF 中的 Pack URI](../app-development/pack-uris-in-wpf.md)
- [控件自定义](control-customization.md)
