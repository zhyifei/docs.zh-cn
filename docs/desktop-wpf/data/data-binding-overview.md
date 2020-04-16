---
title: 数据绑定概述
description: 了解可在 .NET Core 的 Windows 演示文稿基础中添加到项目中的不同数据源。 数据源可以绑定到 XAML 元素以创建动态应用。
author: thraka
ms.date: 09/19/2019
ms.author: adegeo
dev_langs:
- csharp
- vb
ms.openlocfilehash: 7f17ff094a35c04ba880c87c6966d7d249817516
ms.sourcegitcommit: b75a45f0cfe012b71b45dd9bf723adf32369d40c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2020
ms.locfileid: "81433252"
---
# <a name="data-binding-overview-in-wpf"></a>WPF 中的数据绑定概述

Windows 演示基础 （WPF） 中的数据绑定为应用提供一种简单且一致的方式来呈现数据并与之交互。 元素可以绑定到来自各种数据源的数据，其形式是 .NET 对象和 XML。 任何<xref:System.Windows.Controls.ContentControl>（<xref:System.Windows.Controls.Button>如<xref:System.Windows.Controls.ItemsControl>和 ） <xref:System.Windows.Controls.ListBox> <xref:System.Windows.Controls.ListView>的任何 ，如 和 ， 都有内置功能，可灵活设置单个数据项或数据项集合的样式。 可基于数据生成排序、筛选和分组视图。

WPF 中的数据绑定功能与传统模型相比具有几个优势，包括通过多种属性对数据绑定的固有支持、数据灵活的 UI 表示形式以及业务逻辑与 UI 的完全分离。

本文首先讨论 WPF 数据绑定的基本概念，然后介绍数据绑定的<xref:System.Windows.Data.Binding>类和其他功能的用法。

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="what-is-data-binding"></a>什么是数据绑定？

数据绑定是在应用 UI 及其显示的数据之间建立连接的过程。 如果绑定具有正确的设置，并且数据提供适当的通知，则在数据更改其值时，绑定到该数据的元素会自动反映更改。 数据绑定还意味着，如果元素中数据的外部表示形式发生更改，则基础数据可以自动进行更新以反映更改。 例如，如果用户编辑`TextBox`元素中的值，则基础数据值将自动更新以反映该更改。

数据绑定的典型用途是将服务器或本地配置数据放入窗体或其他 UI 控件中。 在 WPF 中，这一概念被扩展为包括将各种属性绑定到各种数据源。 在 WPF 中，元素的依赖项属性可以绑定到 .NET 对象（包括与 Web 服务和 Web 属性关联的ADO.NET对象或对象）和 XML 数据。

有关数据绑定的示例，请查看[数据绑定演示][data-binding-demo]中的以下应用 UI，该演示显示拍卖项目的列表。

![数据绑定示例屏幕截图](./media/data-binding-overview/demo.png "DataBinding_DataBindingDemo")

该应用程序演示了数据绑定的以下功能：

- ListBox 的内容绑定到*拍卖项目对象*的集合。 *拍卖项目对象*具有*描述*、*启动价格*、*开始日期*、*类别*、*特殊功能*等属性。

- 中显示的数据（*拍卖项目*对象）`ListBox`是模板化的，以便显示每个项目的说明和当前价格。 模板是使用 创建的<xref:System.Windows.DataTemplate>。 此外，每个项的外观取决于要显示的 *AuctionItem* 的 *SpecialFeatures* 值。 如果 *AuctionItem* 的 *SpecialFeatures* 值为 *Color*，则该项具有蓝色边框。 如果值为 *Highlight*，则该项具有橙色边框和一个星号。 [数据模板化](#data-templating)部分提供了数据模板化的相关信息。

- 用户可以使用`CheckBoxes`提供的对数据进行分组、筛选或排序。 在上面的图中，按**类别**分组和**按类别和日期**`CheckBoxes`排序。 你可能已注意到，数据按产品类别分组，类别名称按字母顺序排序。 这些项还按每个类别中的开始日期排序，但难以从图中注意到这一点。 排序是使用*集合视图*完成的。 [绑定到集合](#binding-to-collections)部分讨论集合视图。

- 当用户选择项目时，<xref:System.Windows.Controls.ContentControl>将显示所选项目的详细信息。 此体验称为*主详细信息方案*。 [主详细信息方案](#master-detail-binding-scenario)部分提供有关此类型的绑定的信息。

- *StartDate*属性的类型为<xref:System.DateTime>，它返回包含时间到毫秒的日期。 在此应用中，已使用自定义转换器，以便显示较短的日期字符串。 "[数据转换](#data-conversion)"部分提供有关转换器的信息。

当用户选择"*添加产品*"按钮时，将出现以下窗体。

![“添加产品清单”页](./media/data-binding-overview/demo-addproductlisting.png "DataBinding_Demo_AddProductListing")

用户可以编辑表单中的字段，使用简短或详细的预览窗格预览产品列表，然后选择`Submit`添加新产品列表。 任何现有的分组、筛选和排序设置都将应用于新条目。 在这种特殊情况下，上图中输入的项会作为 *Computer* 类别中的第二项显示。

此图像中未显示的验证逻辑是*开始日期*<xref:System.Windows.Controls.TextBox>中提供的验证逻辑。 如果用户输入无效日期（格式无效或过去日期），则会在 旁边使用 和<xref:System.Windows.Controls.ToolTip>红色感叹号通知用户。 <xref:System.Windows.Controls.TextBox> [数据验证](#data-validation)一节讨论了如何创建验证逻辑。

在讨论上述数据绑定的不同功能之前，我们将首先讨论对理解 WPF 数据绑定至关重要的基本概念。

## <a name="basic-data-binding-concepts"></a>基本数据绑定概念

无论您绑定的是哪个元素，以及数据源的性质如何，每个绑定始终遵循下图所示的模型。

![显示基本数据绑定模型的图表。](./media/data-binding-overview/basic-data-binding-diagram.png)

如图所示，数据绑定实质上是绑定目标和绑定源之间的桥梁。 该图演示了以下基本 WPF 数据绑定概念：

- 通常，每个绑定有四个组件：

  - 绑定目标对象。
  - 目标属性。
  - 绑定源。
  - 要使用的绑定源中值的路径。
  
  > 例如，如果要`TextBox`将 的内容绑定到`Employee.Name`属性，则目标对象是`TextBox`，目标属性是<xref:System.Windows.Controls.TextBox.Text%2A>属性，要使用的值是*Name，* 源对象是*Employ*对象。

- 目标属性必须为依赖属性。 大多数<xref:System.Windows.UIElement>属性都是依赖项属性，大多数依赖项属性（只读属性除外）默认支持数据绑定。 （只有派生自<xref:System.Windows.DependencyObject>的类型才能定义依赖项属性;并且<xref:System.Windows.UIElement>所有类型都`DependencyObject`派生自 。

- 虽然图中未显示，但需要注意的是，绑定源对象不仅限于自定义 .NET 对象。 WPF 数据绑定支持以 .NET 对象和 XML 形式的数据。 为了提供一些示例，绑定源可以是<xref:System.Windows.UIElement>任何列表对象、ADO.NET或 Web 服务对象或包含 XML 数据的 XmlNode。 有关详细信息，请参阅[绑定源概述](../../framework/wpf/data/binding-sources-overview.md)。

请务必记住，在建立绑定时，您将绑定目标绑定*到*绑定源。 例如，如果要在<xref:System.Windows.Controls.ListBox>使用数据绑定中显示某些基础 XML 数据，则对 XML 数据`ListBox`进行绑定。

要建立绑定，请使用 对象<xref:System.Windows.Data.Binding>。 本文的其余部分讨论了与`Binding`对象相关的许多概念以及对象的一些属性和用法。

### <a name="direction-of-the-data-flow"></a>数据流的方向

如上图中的箭头所示，如果绑定源提供正确的通知，绑定的数据流可以从绑定目标转到绑定源（例如，当用户编辑`TextBox`值 时，源值会更改） 和/或绑定源到绑定目标（例如，您的`TextBox`内容会随着绑定源中的更改而更新）。

您可能希望你的应用允许用户更改数据并将其传播回源对象。 或者，可能不希望允许用户更新源数据。 您可以通过设置 来控制<xref:System.Windows.Data.Binding.Mode?displayProperty=nameWithType>数据流。

下图说明了不同类型的数据流：

![数据绑定数据流](./media/data-binding-overview/databinding-dataflow.png "DataBinding_DataFlow")

- <xref:System.Windows.Data.BindingMode.OneWay>绑定会导致对源属性的更改自动更新目标属性，但对目标属性的更改不会传播回源属性。 如果绑定的控件为隐式只读，则此类型的绑定适用。 例如，您可以绑定到源（如股票代码，或者目标属性没有为进行更改（如表的数据绑定背景颜色）提供控制接口。 如果无需监视目标属性的更改，则使用 <xref:System.Windows.Data.BindingMode.OneWay> 绑定模式可避免 <xref:System.Windows.Data.BindingMode.TwoWay> 绑定模式的系统开销。

- <xref:System.Windows.Data.BindingMode.TwoWay>绑定会导致对源属性或目标属性的更改，以自动更新另一个属性。 这种类型的绑定适用于可编辑的窗体或其他完全交互式 UI 方案。 大多数属性默认为<xref:System.Windows.Data.BindingMode.OneWay>绑定，但某些依赖项属性（通常是用户可编辑控件的属性，如<xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType>和[CheckBox.IsCheck](xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked)默认<xref:System.Windows.Data.BindingMode.TwoWay>绑定。 确定依赖项属性在默认情况下是单向绑定还是双向绑定的编程方法是获取属性元数据<xref:System.Windows.DependencyProperty.GetMetadata%2A?displayProperty=nameWithType>，然后检查属性的<xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A?displayProperty=nameWithType>布尔值。

- <xref:System.Windows.Data.BindingMode.OneWayToSource>是绑定的<xref:System.Windows.Data.BindingMode.OneWay>反面;当目标属性发生更改时，它将更新源属性。 一个示例方案是，如果您只需要从 UI 重新评估源值。

- 图中未说明的是<xref:System.Windows.Data.BindingMode.OneTime>绑定，这将导致源属性初始化目标属性，但不会传播后续更改。 如果数据上下文发生更改或数据上下文中的对象发生更改，则更改*不会*反映在目标属性中。 如果当前状态的快照是适当的，或者数据是真正的静态的，则这种类型的绑定是合适的。 如果你想使用源属性中的某个值来初始化目标属性，且提前不知道数据上下文，则此类型的绑定也有用。 此模式本质上是一种更简单的<xref:System.Windows.Data.BindingMode.OneWay>绑定形式，在源值不变的情况下提供更好的性能。

要检测源更改（适用于<xref:System.Windows.Data.BindingMode.OneWay>和<xref:System.Windows.Data.BindingMode.TwoWay>绑定），源必须实现适当的属性更改通知机制，如<xref:System.ComponentModel.INotifyPropertyChanged>。 [请参阅如何：实现属性更改通知](../../framework/wpf/data/how-to-implement-property-change-notification.md)，了解<xref:System.ComponentModel.INotifyPropertyChanged>实现的示例。

该<xref:System.Windows.Data.Binding.Mode?displayProperty=nameWithType>属性提供了有关绑定模式的详细信息以及如何指定绑定的方向的示例。

### <a name="what-triggers-source-updates"></a>触发源更新的内容

正在<xref:System.Windows.Data.BindingMode.TwoWay>或<xref:System.Windows.Data.BindingMode.OneWayToSource>侦听目标属性中的更改并将其传播回源（称为更新源）的绑定。 例如，可以编辑文本框的文本以更改基础源值。

但是，在编辑文本或完成文本编辑后是否更新了源值，控件会失去焦点？ 属性<xref:System.Windows.Data.Binding.UpdateSourceTrigger?displayProperty=nameWithType>确定触发源更新的原因。 下图中右箭头的点说明了<xref:System.Windows.Data.Binding.UpdateSourceTrigger?displayProperty=nameWithType>属性的作用。

![显示 UpdateSourceTrigger 属性角色的图表。](./media/data-binding-overview/data-binding-updatesource-trigger.png)

如果`UpdateSourceTrigger`值为<xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged?displayProperty=nameWithType>，则当目标属性发生更改时，将更新<xref:System.Windows.Data.BindingMode.TwoWay>右箭头<xref:System.Windows.Data.BindingMode.OneWayToSource>指向 的值或绑定。 但是，如果`UpdateSourceTrigger`值为<xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>，则仅当目标属性失去焦点时，该值仅会使用新值更新。

与 属性<xref:System.Windows.Data.Binding.Mode%2A>类似，不同的依赖项属性具有不同的<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>默认值。 大多数依赖属性的默认值为 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>，而 `TextBox.Text` 属性的默认值为 <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>。 `PropertyChanged`表示源更新通常在目标属性更改时发生。 对于复选框和其他简单控件，即时更改是可以的。 但是，对于文本字段，每次击键后更新都会降低性能，并剥夺用户在提交到新值之前回空间和修复键入错误的通常机会。

有关如何查找<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>依赖项属性的默认值的信息，请参阅属性页。

下表提供了每个<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>值的示例方案，<xref:System.Windows.Controls.TextBox>该示例用作示例。

| UpdateSourceTrigger 值 | 更新源值时 | 文本框的示例方案 |
| ------------------------- | ---------------------------------- | ---------------------------- |
| `LostFocus`（默认为<xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>） | 当 TextBox 控件失去焦点时。 | 与验证逻辑关联的文本框（请参阅下面的[数据验证](#data-validation)）。 |
| `PropertyChanged` | 当您键入 中<xref:System.Windows.Controls.TextBox>时。 | 聊天室窗口中的 TextBox 控件。 |
| `Explicit` | 当应用程序调用<xref:System.Windows.Data.BindingExpression.UpdateSource%2A>时。 | TextBox 控件为可编辑窗体（仅在用户单击提交按钮时更新源值）。 |

例如，请参阅[如何：控制文本盒文本何时更新源](../../framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md)。

## <a name="creating-a-binding"></a>创建绑定

为了重构前面各节中讨论的某些概念，可以使用<xref:System.Windows.Data.Binding>对象建立绑定，并且每个绑定通常有四个组件：绑定目标、目标属性、绑定源和要使用的源值的路径。 本节讨论如何设置绑定。

请考虑以下示例，其中的绑定源对象是一个名为 *MyData* 的类，该类在 *SDKSample* 命名空间中定义。 出于演示目的 *，MyData*具有名为*ColorName*的字符串属性，其值设置为"红色"。 因此，此示例生成一个具有红色背景的按钮。

[!code-xaml[BindNonTextProperty](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/AutoConvertPropertyToColor.xaml#BindAutoConvertColor)]

有关绑定声明语法的详细信息以及如何在代码中设置绑定的示例，请参阅[绑定声明概述](../../framework/wpf/data/binding-declarations-overview.md)。

如果将此示例应用于基本关系图，则生成的图如下所示。 此图描述绑定<xref:System.Windows.Data.BindingMode.OneWay>，因为默认情况下，背景属性<xref:System.Windows.Data.BindingMode.OneWay>支持绑定。

![显示数据绑定背景属性的图表。](./media/data-binding-overview/data-binding-button-background-example.png)

您可能想知道为什么此绑定有效，即使*ColorName*属性是类型字符串，<xref:System.Windows.Controls.Control.Background%2A>而属性是类型<xref:System.Windows.Media.Brush>。 此绑定使用默认类型转换，在["数据转换](#data-conversion)"部分中讨论。

### <a name="specifying-the-binding-source"></a>指定绑定源

请注意，在前面的示例中，绑定源是通过设置[DockPanel.DataContext](xref:System.Windows.FrameworkElement.DataContext)属性来指定的。 <xref:System.Windows.Controls.Button>然后从 继承<xref:System.Windows.FrameworkElement.DataContext%2A>的值从<xref:System.Windows.Controls.DockPanel>，这是其父元素。 重申一下，绑定源对象是绑定的四个必需组件之一。 因此，如果未指定绑定源对象，则绑定将没有任何作用。

可通过多种方法指定绑定源对象。 将多个<xref:System.Windows.FrameworkElement.DataContext%2A>属性绑定到同一源时，在父元素上使用 该属性非常有用。 不过，有时在个别绑定声明中指定绑定源可能更为合适。 对于前面的示例，<xref:System.Windows.FrameworkElement.DataContext%2A>可以通过直接在按钮的绑定声明中设置<xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType>属性来指定绑定源，如下例所示。

[!code-xaml[BindNonTextPropertyCompactBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/AutoConvertPropertyToColor.xaml#BindAutoConvertColorCompactBinding)]

除了直接在元素<xref:System.Windows.FrameworkElement.DataContext%2A>上设置属性外，<xref:System.Windows.FrameworkElement.DataContext%2A>从祖先继承值（如第一个示例中的按钮），并通过在绑定上设置<xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType>属性（如最后一个示例的按钮）显式指定绑定源，还可以使用<xref:System.Windows.Data.Binding.ElementName?displayProperty=nameWithType>属性或<xref:System.Windows.Data.Binding.RelativeSource?displayProperty=nameWithType>属性指定绑定源。 当您<xref:System.Windows.Data.Binding.ElementName%2A>绑定到应用中的其他元素时，该属性很有用，例如，当您使用滑块调整按钮的宽度时。 在<xref:System.Windows.Data.Binding.RelativeSource%2A><xref:System.Windows.Controls.ControlTemplate>或 中指定绑定时，该属性很有用<xref:System.Windows.Style>。 有关详细信息，请参阅[操作：指定绑定源](../../framework/wpf/data/how-to-specify-the-binding-source.md)。

### <a name="specifying-the-path-to-the-value"></a>指定值的路径

如果绑定源是对象，则可以使用 属性<xref:System.Windows.Data.Binding.Path?displayProperty=nameWithType>指定用于绑定的值。 如果要绑定到 XML 数据，请使用 属性<xref:System.Windows.Data.Binding.XPath?displayProperty=nameWithType>指定值。 在某些情况下，即使数据为 XML，<xref:System.Windows.Data.Binding.Path%2A>也可以使用 该属性。 例如，如果要访问返回的 XmlNode 的 Name 属性（作为 XPath 查询的结果），则应除<xref:System.Windows.Data.Binding.Path%2A><xref:System.Windows.Data.Binding.XPath%2A>该属性之外使用 该属性。

有关详细信息，请参阅 和<xref:System.Windows.Data.Binding.Path%2A><xref:System.Windows.Data.Binding.XPath%2A>属性。

尽管我们强调<xref:System.Windows.Data.Binding.Path%2A>要使用的值是绑定的四个必要组件之一，但在要绑定到整个对象的方案中，要使用的值将与绑定源对象相同。 在这些情况下，它适用于不指定 。 <xref:System.Windows.Data.Binding.Path%2A> 请考虑以下示例。

[!code-xaml[EmptyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/EmptyBinding.xaml#EmptyBinding)]

以上示例使用空绑定语法：{Binding}。 在这种情况下，从<xref:System.Windows.Controls.ListBox>父 DockPanel 元素继承 DataContext（此示例中未显示）。 未指定路径时，默认为绑定到整个对象。 换句话说，在此示例中，路径被遗漏了，因为我们将<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>属性绑定到整个对象。 （有关深入讨论[，请参阅绑定到集合](#binding-to-collections)部分。

除了绑定到集合以外，在希望绑定到整个对象，而不是仅绑定到对象的单个属性时，也可以使用此方案。 例如，如果源对象的类型<xref:System.String>，您可能只想绑定到字符串本身。 另一种常见情况是希望将一个元素绑定到一个具有多个属性的对象。

您可能需要应用自定义逻辑，以便数据对绑定的目标属性有意义。 如果不存在默认类型转换，自定义逻辑可能采用自定义转换器的形式。 有关转换器的信息，请参阅[数据转换](#data-conversion)。

### <a name="binding-and-bindingexpression"></a>Binding 和 BindingExpression

在介绍数据绑定的其他功能和用法之前，引入类<xref:System.Windows.Data.BindingExpression>非常有用。 如前一节所示，<xref:System.Windows.Data.Binding>类是声明绑定的高级类;它提供了许多属性，允许您指定绑定的特征。 相关类<xref:System.Windows.Data.BindingExpression>是维护源和目标之间连接的基础对象。 一个绑定包含了可以在多个绑定表达式之间共享的所有信息。 a<xref:System.Windows.Data.BindingExpression>是不能共享的实例表达式，它包含 的所有<xref:System.Windows.Data.Binding>实例信息。

请考虑`myDataObject`以下示例，其中是类的`MyData`实例，`myBinding`是源<xref:System.Windows.Data.Binding>对象，`MyData`是包含名为 的`MyDataProperty`字符串属性的已定义类。 此示例将`myText`的文本内容绑定到<xref:System.Windows.Controls.TextBlock>`MyDataProperty`。

[!code-csharp[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/ManualBinding.cs#CodeOnlyBinding)]
[!code-vb[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/ManualBinding.vb#CodeOnlyBinding)]

可以使用同一 *myBinding* 对象来创建其他绑定。 例如，可以使用*myBinding*对象将复选框的文本内容绑定到*MyDataProperty*。 在这种情况下，将有两个共享*myBinding*对象的<xref:System.Windows.Data.BindingExpression>实例。

通过<xref:System.Windows.Data.BindingExpression>调用<xref:System.Windows.Data.BindingOperations.GetBindingExpression%2A>数据绑定对象来返回对象。 以下文章演示了<xref:System.Windows.Data.BindingExpression>类的一些用法：

- [从已绑定的目标属性获取绑定对象](../../framework/wpf/data/how-to-get-the-binding-object-from-a-bound-target-property.md)

- [控件 文本框文本何时更新源](../../framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md)

## <a name="data-conversion"></a>数据转换

在"[创建绑定](#creating-a-binding)"部分中，按钮为红色，因为它<xref:System.Windows.Controls.Control.Background%2A>的属性绑定到值为"红色"的字符串属性。 此字符串值之所以有效，是因为类型转换器存在于类型上<xref:System.Windows.Media.Brush>，用于将字符串值转换为 。 <xref:System.Windows.Media.Brush>

将此信息添加到图"[创建绑定](#creating-a-binding)"部分如下所示。

![显示数据绑定 Default 属性的图表。](./media/data-binding-overview/data-binding-button-default-conversion.png)

但是，如果绑定源对象没有类型字符串的属性，而是具有<xref:System.Windows.Media.Color>*类型的颜色*属性，该怎么办？ 在这种情况下，为了使绑定正常工作，您需要首先将*Color*属性值转换为<xref:System.Windows.Controls.Control.Background%2A>属性接受的内容。 您需要通过实现<xref:System.Windows.Data.IValueConverter>接口来创建自定义转换器，如以下示例所示。

[!code-csharp[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/ColorBrushConverter.cs#ColorBrushConverter)]
[!code-vb[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/ColorBrushConverter.vb#ColorBrushConverter)]

有关详细信息，请参阅<xref:System.Windows.Data.IValueConverter>。

现在使用自定义转换器而不是默认转换，我们的图表如下所示。

![显示数据绑定自定义转换器的图表。](./media/data-binding-overview/data-binding-converter-color-example.png)

重申一下，由于要绑定到的类型中提供了类型转换器，因此可以使用默认转换。 此行为取决于目标中可用的类型转换器。 如果无法确定，请创建自己的转换器。

以下是一些典型方案，其中实现数据转换器是有意义的：

- 数据应根据区域性以不同方式显示。 例如，您可能希望基于特定区域性中使用的约定实现货币转换器或日历日期/时间转换器。

- 使用的数据不一定会更改属性的文本值，但会更改其他某个值（如图像的源，或显示文本的颜色或样式）。 在这种情况下，可以通过转换可能不合适的属性绑定（如将文本字段绑定到表单元格的 Background 属性）来使用转换器。

- 控件的多个控件或多个属性绑定到同一数据。 在这种情况下，主绑定可能仅显示文本，而其他绑定则处理特定的显示问题，但仍使用同一绑定作为源信息。

- 目标属性具有绑定的集合，称为<xref:System.Windows.Data.MultiBinding>。 对于<xref:System.Windows.Data.MultiBinding>，使用自定义<xref:System.Windows.Data.IMultiValueConverter>从绑定的值生成最终值。 例如，可以从红色、蓝色和绿色的值来计算颜色，这些值可能来自相同绑定源对象，也可能来自不同绑定源对象。 有关<xref:System.Windows.Data.MultiBinding>示例和信息，请参阅。

## <a name="binding-to-collections"></a>绑定到集合

绑定源对象可以被视为属性包含数据的单个对象，也可以被视为通常分组在一起的多态对象的数据收集（例如对数据库的查询结果）。 到目前为止，我们只讨论了绑定到单个对象。 但是，绑定到数据收集是常见方案。 例如，常见方案是使用<xref:System.Windows.Controls.ItemsControl>等<xref:System.Windows.Controls.ListBox>，<xref:System.Windows.Controls.ListView>或<xref:System.Windows.Controls.TreeView>显示数据收集，例如在["什么是数据绑定"](#what-is-data-binding)部分中显示的应用中。

幸运的是，基本关系图仍然适用。 如果要将 绑定<xref:System.Windows.Controls.ItemsControl>到集合，则关系图如下所示。

![显示数据绑定项控制对象的关系图。](./media/data-binding-overview/data-binding-itemscontrol.png)

如此关系图所示，要将<xref:System.Windows.Controls.ItemsControl>绑定 到集合对象<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A?displayProperty=nameWithType>，属性是要使用的属性。 您可以将`ItemsSource`其视为 的内容<xref:System.Windows.Controls.ItemsControl>。 绑定的原因是<xref:System.Windows.Data.BindingMode.OneWay>默认情况下属性`ItemsSource`支持`OneWay`绑定。

### <a name="how-to-implement-collections"></a>如何实现集合

可以枚举实现<xref:System.Collections.IEnumerable>接口的任何集合。 但是，要设置动态绑定，以便集合中的插入或删除自动更新 UI，集合必须实现<xref:System.Collections.Specialized.INotifyCollectionChanged>接口。 此接口公开一个事件，只要基础集合发生更改，就应该引发该事件。

WPF 提供<xref:System.Collections.ObjectModel.ObservableCollection%601>类，它是公开<xref:System.Collections.Specialized.INotifyCollectionChanged>接口的数据收集的内置实现。 要完全支持将数据值从源对象传输到目标，集合中支持可绑定属性的每个对象还必须实现<xref:System.ComponentModel.INotifyPropertyChanged>接口。 有关详细信息，请参阅[绑定源概述](../../framework/wpf/data/binding-sources-overview.md)。

在实现自己的<xref:System.Collections.ObjectModel.ObservableCollection%601>集合之前，请考虑使用或现有集合类之一，例如<xref:System.Collections.Generic.List%601>，<xref:System.Collections.ObjectModel.Collection%601>和<xref:System.ComponentModel.BindingList%601>等。 如果您有高级方案并希望实现自己的集合，请考虑使用<xref:System.Collections.IList>，它提供一个非泛型的对象集合，该集合可以由索引单独访问，从而提供最佳性能。

### <a name="collection-views"></a>集合视图

<xref:System.Windows.Controls.ItemsControl>绑定到数据收集后，可能需要对数据进行排序、筛选或分组。 为此，可以使用集合视图，集合视图是实现接口的<xref:System.ComponentModel.ICollectionView>类。

#### <a name="what-are-collection-views"></a>什么是集合视图？

集合视图这一层基于绑定源集合，它允许基于排序、筛选和分组查询来导航并显示源集合，而无需更改基础源集合本身。 集合视图还维护一个指向集合中当前项的指针。 如果源集合实现<xref:System.Collections.Specialized.INotifyCollectionChanged>接口，<xref:System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged>则事件引发的更改将传播到视图。

由于视图不会更改基础源集合，因此每个源集合都可以有多个关联的视图。 例如，可以有 *Task* 对象的集合。 使用视图，可以通过不同方式显示相同数据。 例如，可能希望在页面左侧显示按优先级排序的任务，而在页面右侧显示按区域分组的任务。

#### <a name="how-to-create-a-view"></a>视图创建方法

创建并使用视图的一种方式是直接实例化视图对象，然后将它用作绑定源。 例如，请考虑["什么是数据绑定"](#what-is-data-binding)部分中显示的[数据绑定演示][data-binding-demo]应用。 应用的实现使<xref:System.Windows.Controls.ListBox>绑定到数据集上的视图，而不是直接绑定到数据收集。 以下示例从[数据绑定演示][data-binding-demo]应用中提取。 类<xref:System.Windows.Data.CollectionViewSource>是从 继承的类的 XAML 代理<xref:System.Windows.Data.CollectionView>。 在此特定示例中，<xref:System.Windows.Data.CollectionViewSource.Source%2A>视图的绑定到当前应用对象的*拍卖项目*集合（类型）。 <xref:System.Collections.ObjectModel.ObservableCollection%601>

[!code-xaml[CollectionView](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#CollectionView)]

然后，资源*列表 DataView*充当应用中的元素（如 中的绑定<xref:System.Windows.Controls.ListBox>源）。

[!code-xaml[ListBoxCollectionView](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#ListBoxCollectionView)]

要为同一集合创建另一个视图，可以创建<xref:System.Windows.Data.CollectionViewSource>另一个实例并为其`x:Key`指定其他名称。

下表显示了哪些视图数据类型创建为默认集合视图或<xref:System.Windows.Data.CollectionViewSource>基于源集合类型创建。

| 源集合类型                    | 集合视图类型 | 说明 |
| ----------------------------------------- | -------------------- | ----- |
| <xref:System.Collections.IEnumerable>     | 基于内部类型<xref:System.Windows.Data.CollectionView> | 无法对项进行分组。 |
| <xref:System.Collections.IList>           | <xref:System.Windows.Data.ListCollectionView> | Fastest。 |
| <xref:System.ComponentModel.IBindingList> | <xref:System.Windows.Data.BindingListCollectionView> | |

#### <a name="using-a-default-view"></a>使用默认视图

创建并使用集合视图的一种方式是指定集合视图作为绑定源。 WPF 还会为用作绑定源的每个集合创建一个默认集合视图。 如果直接绑定到集合，WPF 会绑定到该集合的默认视图。 此默认视图由同一集合的所有绑定共享，因此由一个绑定控件或代码对默认视图所做的更改（如排序或对当前项指针的更改，稍后讨论）将反映在对同一集合的所有其他绑定中。

要获取默认视图，请使用 方法<xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A>。 例如，请参阅[获取数据收集的默认视图](../../framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)。

#### <a name="collection-views-with-adonet-datatables"></a>具有ADO.NET数据表的集合视图

为了提高性能，ADO.NET<xref:System.Data.DataTable>或<xref:System.Data.DataView>对象的集合视图将排序和筛选委托给 ，<xref:System.Data.DataView>这将导致在数据源的所有集合视图中共享排序和筛选。 要使每个集合视图能够独立排序和筛选，使用自己的<xref:System.Data.DataView>对象初始化每个集合视图。

#### <a name="sorting"></a>排序

如前所述，视图可以将排序顺序应用于集合。 如同在基础集合中一样，数据可能具有或不具有相关的固有顺序。 借助集合视图，可以根据自己提供的比较条件来强制确定顺序，或更改默认顺序。 由于这是基于客户端的数据视图，因此一种常见情况是用户可能希望根据列对应的值，对多列表格数据进行排序。 通过使用视图，可以应用这种用户实施的排序，而无需对基础集合进行任何更改，甚至不必再次查询集合内容。 例如，请参阅[单击标题时对 GridView 列进行排序](../../framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)。

下面的示例显示了应用 UI 在"[什么是数据绑定"](#what-is-data-binding)部分中的"<xref:System.Windows.Controls.CheckBox>按类别和日期排序"的排序逻辑。

[!code-csharp[AddSortChecked](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#AddSortChecked)]
[!code-vb[AddSortChecked](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#AddSortChecked)]

#### <a name="filtering"></a>筛选

视图还可以将筛选器应用于集合，以便视图仅显示完整集合的特定子集。 可以根据条件在数据中进行筛选。 例如，正如应用在"[什么是数据绑定"](#what-is-data-binding)部分所做的那样，"仅显示便宜货"<xref:System.Windows.Controls.CheckBox>包含筛选出成本为 25 美元或更多的项目的逻辑。 执行以下代码以在选择时将 *"只显示只讨价还价"筛选器*设置为<xref:System.Windows.Data.CollectionViewSource.Filter>事件处理程序<xref:System.Windows.Controls.CheckBox>。

[!code-csharp[ListingViewFilter](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#ListingViewFilter)]
[!code-vb[ListingViewFilter](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#ListingViewFilter)]

*"只显示讨价还价"* 事件处理程序具有以下实现。

[!code-csharp[FilterEvent](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#FilterEvent)]
[!code-vb[FilterEvent](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#FilterEvent)]

如果直接使用其中一个<xref:System.Windows.Data.CollectionView>类而不是<xref:System.Windows.Data.CollectionViewSource>，则可以使用 属性<xref:System.Windows.Data.CollectionView.Filter%2A>指定回调。 有关示例，请参阅[筛选视图中的数据](../../framework/wpf/data/how-to-filter-data-in-a-view.md)。

#### <a name="grouping"></a>分组

除了查看<xref:System.Collections.IEnumerable>集合的内部类外，所有集合视图都支持*分组*，这允许用户将集合视图中的集合分区为逻辑组。 这些组可以是显式的，由用户提供组列表；也可以是隐式的，这些组依据数据动态生成。

下面的示例显示了"按类别分组"<xref:System.Windows.Controls.CheckBox>的逻辑。

[!code-csharp[ListingGroupCheck](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#ListingGroupCheck)]
[!code-vb[ListingGroupCheck](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#ListingGroupCheck)]

有关其他分组示例，请参阅[对实现 GridView 的 ListView 中的项进行分组](../../framework/wpf/controls/how-to-group-items-in-a-listview-that-implements-a-gridview.md)。

#### <a name="current-item-pointers"></a>当前项指针

视图还支持当前项的概念。 可以在集合视图中的对象之间导航。 在导航时，你是在移动项指针，该指针可用于检索存在于集合中特定位置的对象。 例如，请参阅[浏览数据收集视图中的对象](../../framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md)。

由于 WPF 只通过使用视图（你指定的视图或集合的默认视图）绑定到集合，因此集合的所有绑定都有一个当前项指针。 绑定到视图时，`Path` 值中的斜杠（“/”）字符用于指定视图的当前项。 在下面的示例中，数据上下文是一个集合视图。 第一行绑定到集合。 第二行绑定到集合中的当前项。 第三行绑定到集合中当前项的 `Description` 属性。

```xaml
<Button Content="{Binding }" />
<Button Content="{Binding Path=/}" />
<Button Content="{Binding Path=/Description}" />
```

还可以连着使用斜杠和属性语法以遍历集合的分层。 以下示例绑定到一个名为 `Offices` 的集合的当前项，此集合是源集合的当前项的属性。

```xaml
<Button Content="{Binding /Offices/}" />
```

当前项指针可能会受对集合应用的任何排序或筛选操作的影响。 排序操作将当前项指针保留在所选的最后一项上，但集合视图现已围绕此指针重构。 （可能所选项目以前位于列表的开头，但现在所选项可能位于中间的某个位置。如果筛选后该选择仍保留在视图中，则筛选将保留所选项。 否则，当前项指针会设置为经过筛选的集合视图的第一项。

#### <a name="master-detail-binding-scenario"></a>主详细信息绑定方案

当前项的概念不仅适用于集合中各项的导航，也适用于主-从绑定方案。 再次考虑["什么是数据绑定"](#what-is-data-binding)部分中的应用 UI。 在该应用程序中，中的选择<xref:System.Windows.Controls.ListBox>确定 中显示的内容。 <xref:System.Windows.Controls.ContentControl> 要以另一种方式放置它，在<xref:System.Windows.Controls.ListBox>选择项目时，<xref:System.Windows.Controls.ContentControl>将显示所选项的详细信息。

只需将两个或更多控件绑定到同一视图即可实现主-从方案。 [数据绑定演示][data-binding-demo]中的以下示例在"[什么是数据绑定"](#what-is-data-binding)部分中<xref:System.Windows.Controls.ListBox>显示<xref:System.Windows.Controls.ContentControl>应用 UI 上的标记和中看到的。

[!code-xaml[ListBoxContentControl](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#ListBoxContentControl)]

请注意，两个控件都绑定到同一源，*即列表 DataView*静态资源（请参阅["如何创建视图"部分](#how-to-create-a-view)中此资源的定义）。 此绑定有效，因为当单例对象（本<xref:System.Windows.Controls.ContentControl>例中）绑定到集合视图时，它会自动绑定到视图<xref:System.Windows.Data.CollectionView.CurrentItem%2A>。 对象<xref:System.Windows.Data.CollectionViewSource>会自动同步货币和选择。 如果列表控件未绑定到<xref:System.Windows.Data.CollectionViewSource>对象，例如本示例中所示，则需要将其<xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A>属性设置为`true`以正常工作。

有关其他示例，请参阅[绑定到集合并基于选择显示信息](../../framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)，并使用[具有分层数据的主详细信息模式](../../framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)。

你可能已经注意到上述示例使用了一个模板。 事实上，如果不使用模板（由 和<xref:System.Windows.Controls.ContentControl>隐式使用模板）来显示数据，数据就不会按我们希望的方式显示。 <xref:System.Windows.Controls.ListBox> 现在，我们开始介绍下一节中的数据模板化。

## <a name="data-templating"></a>数据模板化

如果不使用数据模板，我们在["什么是数据绑定"](#what-is-data-binding)部分中的应用 UI 如下所示。

![没有数据模板的数据绑定演示](./media/data-binding-overview/demo-no-template.png)

如上一节中的示例所示，<xref:System.Windows.Controls.ListBox>控件和<xref:System.Windows.Controls.ContentControl>绑定都绑定到*拍卖项目*的整个集合对象（或更具体地说，对集合对象的视图）。 如果没有有关如何显示数据收集的特定说明，则<xref:System.Windows.Controls.ListBox>显示基础集合中每个对象的字符串表示形式，<xref:System.Windows.Controls.ContentControl>并显示绑定到的对象的字符串表示形式。

要解决此问题，应用程序定义<xref:System.Windows.DataTemplate?text=DataTemplates>。 如上一节中的示例所示，<xref:System.Windows.Controls.ContentControl>显式使用*详细信息产品列表模板*。 当<xref:System.Windows.Controls.ListBox>集合中显示*拍卖项目*对象时，控件隐式使用以下数据模板。

[!code-xaml[AuctionItemDataTemplate](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#AuctionItemDataTemplate)]

使用这两个 DataTemplate 时，生成的 UI 就是["什么是数据绑定"](#what-is-data-binding)部分中显示的 UI。 正如您从该屏幕截图中看到的，除了允许您将数据放置在控件中之外，DataTemplate 还允许您为数据定义引人注目的视觉对象。 <xref:System.Windows.DataTrigger>例如，上面<xref:System.Windows.DataTemplate>使用 s，以便具有*高光**特殊功能*值的*拍卖项目*将显示橙色边框和星形。

有关数据模板的详细信息，请参阅[数据模板概述](../../framework/wpf/data/data-templating-overview.md)。

## <a name="data-validation"></a>数据验证

大多数采用用户输入的应用都需要具有验证逻辑，以确保用户已输入预期信息。 验证检查可以基于类型、范围、格式或其他特定于应用的要求。 本节讨论数据验证在 WPF 中的工作原理。

### <a name="associating-validation-rules-with-a-binding"></a>将验证规则与绑定关联

WPF 数据绑定模型允许您与<xref:System.Windows.Data.Binding.ValidationRules%2A><xref:System.Windows.Data.Binding>对象关联。 例如，下面的示例<xref:System.Windows.Controls.TextBox>将 绑定 到名为`StartPrice`的属性，并将<xref:System.Windows.Controls.ExceptionValidationRule>对象添加到该<xref:System.Windows.Data.Binding.ValidationRules%2A?displayProperty=nameWithType>属性。

[!code-xaml[TextboxStartPrice](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#TextboxStartPrice)]

<xref:System.Windows.Controls.ValidationRule>对象检查属性的值是否有效。 WPF 有两种类型的内置<xref:System.Windows.Controls.ValidationRule>对象：

- <xref:System.Windows.Controls.ExceptionValidationRule>检查在更新绑定源属性期间引发的异常。 在以上示例中，`StartPrice` 为整数类型。 当用户输入的值无法转换为整数时，将引发异常，这会导致将绑定标记为无效。 <xref:System.Windows.Controls.ExceptionValidationRule>显式设置 的替代语法是<xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>将 属性设置为`true`或<xref:System.Windows.Data.Binding><xref:System.Windows.Data.MultiBinding>对象。

- <xref:System.Windows.Controls.DataErrorValidationRule>对象检查由实现<xref:System.ComponentModel.IDataErrorInfo>接口的对象引发的错误。 有关使用此验证规则的示例，请参阅<xref:System.Windows.Controls.DataErrorValidationRule>。 <xref:System.Windows.Controls.DataErrorValidationRule>显式设置 的替代语法是<xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>将 属性设置为`true`或<xref:System.Windows.Data.Binding><xref:System.Windows.Data.MultiBinding>对象。

还可以通过派生<xref:System.Windows.Controls.ValidationRule>类和实现<xref:System.Windows.Controls.ValidationRule.Validate%2A>方法创建自己的验证规则。 下面的示例显示了 *"添加产品列表*"开始日期"在<xref:System.Windows.Controls.TextBox>["什么是数据绑定](#what-is-data-binding)"部分使用的规则。

[!code-csharp[FutureDateRule](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/FutureDateRule.cs#FutureDateRule)]
[!code-vb[FutureDateRule](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/FutureDateRule.vb#FutureDateRule)]

*StartDateEntryForm*<xref:System.Windows.Controls.TextBox>使用此*未来日期规则*，如以下示例所示。

[!code-xaml[TextboxStartDate](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#TextboxStartDate)]

由于<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>值为<xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>，绑定引擎会更新每个击键的源值，这意味着它还会检查集合中<xref:System.Windows.Data.Binding.ValidationRules%2A>每个击键中的每个规则。 我们会在“验证过程”一节中对此深入讨论。

### <a name="providing-visual-feedback"></a>提供视觉反馈

如果用户输入无效值，您可能需要提供有关应用 UI 上的错误的一些反馈。 提供此类反馈的一种方法是将<xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType>附加属性设置为自定义<xref:System.Windows.Controls.ControlTemplate>。 如上一节所示 *，StartDateEntryForm*<xref:System.Windows.Controls.TextBox>使用<xref:System.Windows.Controls.Validation.ErrorTemplate%2A>称为*验证模板*。 下面的示例显示了*验证模板*的定义。

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#ControlTemplate)]

该<xref:System.Windows.Controls.AdornedElementPlaceholder>元素指定应放置要修饰的控件的位置。

此外，您还可以使用 显示<xref:System.Windows.Controls.ToolTip>错误消息。 *StartDateEntryForm*和*StartPriceentryForm*<xref:System.Windows.Controls.TextBox>都使用样式*文本样式文本Box*，它创建显示<xref:System.Windows.Controls.ToolTip>错误消息的 样式文本文本Box 。 以下示例显示了 *textStyleTextBox* 的定义。 附加属性<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>是在`true`绑定元素的属性上的一个或多个绑定出错时。

[!code-xaml[TextBoxStyle](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#TextBoxStyle)]

当出现验证<xref:System.Windows.Controls.Validation.ErrorTemplate%2A>错误时<xref:System.Windows.Controls.ToolTip>，使用 自定义和 启动*日期输入窗体*<xref:System.Windows.Controls.TextBox>如下所示。

![数据绑定验证错误](./media/data-binding-overview/demo-validation-date.png "DataBindingDemo_Validation")

<xref:System.Windows.Data.Binding>如果具有关联的验证规则，但未在绑定控件上<xref:System.Windows.Controls.Validation.ErrorTemplate%2A>指定 ， 则当存在<xref:System.Windows.Controls.Validation.ErrorTemplate%2A>验证错误时，将使用默认值通知用户。 默认值<xref:System.Windows.Controls.Validation.ErrorTemplate%2A>是定义装饰层中的红色边框的控制模板。 当出现验证<xref:System.Windows.Controls.Validation.ErrorTemplate%2A>错误时<xref:System.Windows.Controls.ToolTip>，使用默认值和 的 UI 时 *，StartPriceEntryForm*<xref:System.Windows.Controls.TextBox>的 UI 如下所示。

![数据绑定验证错误](./media/data-binding-overview/demo-validation-price.png "DataBindingDemo_ValidationDefault")

有关如何提供逻辑以验证对话框中的所有控件的示例，请参阅[对话框概述](../../framework/wpf/app-development/dialog-boxes-overview.md)中的"自定义对话框"部分。

### <a name="validation-process"></a>验证过程

通常，在目标的值传输到绑定源属性时会进行验证。 此传输发生在<xref:System.Windows.Data.BindingMode.TwoWay>和<xref:System.Windows.Data.BindingMode.OneWayToSource>绑定上。 要重申，源更新的原因取决于<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>属性的值，如["什么触发源更新](#what-triggers-source-updates)"部分所述。

以下项描述*验证*过程。 如果在此过程中的任何时间发生验证错误或其他类型的错误，则进程将停止：

1. 绑定引擎检查<xref:System.Windows.Controls.ValidationRule>是否有任何自定义对象定义其<xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>设置为<xref:System.Windows.Controls.ValidationStep.RawProposedValue>该<xref:System.Windows.Data.Binding>，在这种情况下，它调用每个<xref:System.Windows.Controls.ValidationRule.Validate%2A><xref:System.Windows.Controls.ValidationRule>对象上的方法，直到其中一个运行错误或直到所有对象都通过。

2. 绑定引擎随后会调用转换器（如果存在）。

3. 如果转换器成功，绑定引擎将检查是否有任何自定义<xref:System.Windows.Controls.ValidationRule>对象定义其<xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>设置为<xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue>该<xref:System.Windows.Data.Binding>对象，在这种情况下，它会调用每个<xref:System.Windows.Controls.ValidationRule.Validate%2A><xref:System.Windows.Controls.ValidationRule><xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>已设置为<xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue>的方法，直到其中一个对象遇到错误或直到所有对象都通过。

4. 绑定引擎设置源属性。

5. 绑定引擎<xref:System.Windows.Controls.ValidationRule>检查是否有任何自定义对象定义其<xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>设置为<xref:System.Windows.Controls.ValidationStep.UpdatedValue>该<xref:System.Windows.Data.Binding>对象，在这种情况下，它会调用每个<xref:System.Windows.Controls.ValidationRule.Validate%2A><xref:System.Windows.Controls.ValidationRule><xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>已设置为<xref:System.Windows.Controls.ValidationStep.UpdatedValue>的方法，直到其中一个对象遇到错误或直到所有对象都通过。 如果<xref:System.Windows.Controls.DataErrorValidationRule>与绑定关联，并且其<xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>设置为默认值 ，<xref:System.Windows.Controls.ValidationStep.UpdatedValue>此时将检查 。 <xref:System.Windows.Controls.DataErrorValidationRule> 此时，<xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>`true`将检查具有集的任何绑定。

6. 绑定引擎<xref:System.Windows.Controls.ValidationRule>检查是否有任何自定义对象定义其<xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>设置为<xref:System.Windows.Controls.ValidationStep.CommittedValue>该<xref:System.Windows.Data.Binding>对象，在这种情况下，它会调用每个<xref:System.Windows.Controls.ValidationRule.Validate%2A><xref:System.Windows.Controls.ValidationRule><xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>已设置为<xref:System.Windows.Controls.ValidationStep.CommittedValue>的方法，直到其中一个对象遇到错误或直到所有对象都通过。

如果<xref:System.Windows.Controls.ValidationRule>在整个过程中任何时候都未传递 ，绑定引擎将创建一个<xref:System.Windows.Controls.ValidationError>对象并将其添加到绑定元素<xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType>的集合中。 在绑定引擎在任何给定步骤<xref:System.Windows.Controls.ValidationRule>上运行对象之前，它会删除该步骤期间<xref:System.Windows.Controls.ValidationError>添加到绑定元素<xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType>的附加属性的任何内容。 例如，如果 设置为<xref:System.Windows.Controls.ValidationRule><xref:System.Windows.Controls.ValidationRule.ValidationStep%2A><xref:System.Windows.Controls.ValidationStep.UpdatedValue>失败的<xref:System.Windows.Controls.ValidationError>，则下次发生验证过程时，绑定引擎将删除它调用任何<xref:System.Windows.Controls.ValidationRule>已<xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>设置为<xref:System.Windows.Controls.ValidationStep.UpdatedValue>之前。

当<xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType>不为空时，<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>元素的附加属性将设置为`true`。 此外，如果<xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>的属性<xref:System.Windows.Data.Binding>设置为`true`，则绑定引擎将<xref:System.Windows.Controls.Validation.Error?displayProperty=nameWithType>附加事件引发元素。

另请注意，向任一方向（目标到源或源到目标）的有效值转移将清除<xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType>附加属性。

如果绑定具有与其关联的绑定<xref:System.Windows.Controls.ExceptionValidationRule>，或者将<xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>属性设置为`true`，并在绑定引擎设置源时引发异常，则绑定引擎将检查是否有 。 <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> 您可以选择使用<xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>回调来提供用于处理异常的自定义处理程序。 如果在<xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>上<xref:System.Windows.Data.Binding>未指定 ， 绑定引擎将创建<xref:System.Windows.Controls.ValidationError>具有异常的 ， 并将其添加到<xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType>绑定元素的集合中。

## <a name="debugging-mechanism"></a>调试机制

您可以在绑定相关对象上设置<xref:System.Diagnostics.PresentationTraceSources.TraceLevel%2A?displayProperty=nameWithType>附加属性以接收有关特定绑定状态的信息。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.DataErrorValidationRule>
- [绑定到 LINQ 查询的结果](../../framework/wpf/data/how-to-bind-to-the-results-of-a-linq-query.md)
- [数据绑定](../../framework/wpf/advanced/optimizing-performance-data-binding.md)
- [数据绑定演示][data-binding-demo]
- [如何使用的文章](../../framework/wpf/data/data-binding-how-to-topics.md)
- [绑定到 ADO.NET 数据源](../../framework/wpf/data/how-to-bind-to-an-ado-net-data-source.md)

[data-binding-demo]: https://github.com/microsoft/WPF-Samples/tree/master/Sample%20Applications/DataBindingDemo "数据绑定演示应用程序"
