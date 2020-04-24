---
title: 数据模板化概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], templates
- binding data [WPF], templates
- templates [WPF], data
- data templates [WPF]
ms.assetid: 0f4d9f8c-0230-4013-bd7b-e8e7fed01b4a
ms.openlocfilehash: b9e55eac1c72cd3deec21754373da4364a7cfed2
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646458"
---
# <a name="data-templating-overview"></a>数据模板化概述
WPF 数据模板化模型为定义数据的表示提供了很大的灵活性。 WPF 控件具有支持自定义数据表示的内置功能。 本主题首先演示如何定义，<xref:System.Windows.DataTemplate>然后介绍其他数据模板化功能，例如基于自定义逻辑选择模板和支持显示分层数据。

<a name="Prerequisites"></a>
## <a name="prerequisites"></a>先决条件
 本主题重点介绍数据模板化功能，不介绍数据绑定概念。 有关基本数据绑定概念的信息，请参阅[数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)。

 <xref:System.Windows.DataTemplate>是关于数据的表示，是 WPF 样式和模板模型提供的众多功能之一。 有关 WPF 样式和模板模型的介绍（例如如何使用<xref:System.Windows.Style>在控件上设置属性），请参阅["样式"和"模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)"主题。

 此外，了解 这一点本质上是`Resources`使对象（如 和<xref:System.Windows.Style><xref:System.Windows.DataTemplate>） 可重用的原因，这一点很重要。 有关资源的详细信息，请参阅 [XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)。

<a name="DataTemplating_Basic"></a>
## <a name="data-templating-basics"></a>数据模板化基础知识

 为了演示为什么<xref:System.Windows.DataTemplate>很重要，让我们演练一个数据绑定示例。 在此示例中，我们有绑定到对象列表<xref:System.Windows.Controls.ListBox>的`Task`。 每个 `Task` 对象都有 `TaskName` (string)、`Description` (string)、`Priority` (int) 和 `TaskType` 类型的属性（它是一个 `Enum`，其值为 `Home` 和 `Work`）。

 [!code-xaml[DataTemplatingIntro_snip#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#resources)]
[!code-xaml[DataTemplatingIntro_snip#UI1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui1)]
[!code-xaml[DataTemplatingIntro_snip#UI2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui2)]

<a name="without_a_datatemplate"></a>
### <a name="without-a-datatemplate"></a>不提供 DataTemplate
 如果没有<xref:System.Windows.DataTemplate>，我们目前<xref:System.Windows.Controls.ListBox>如下所示：

 ![数据模板化示例屏幕截图](./media/datatemplatingintro-fig1.png "DataTemplatingIntro_fig1")

 发生的情况是，在没有任何具体说明的情况下，<xref:System.Windows.Controls.ListBox>默认情况下在尝试在集合中显示`ToString`对象时调用。 因此，`Task`如果对象重写`ToString`该方法，则 显示<xref:System.Windows.Controls.ListBox>基础集合中每个源对象的字符串表示形式。

 例如，如果 `Task` 类以这种方式重写 `ToString` 方法，其中 `name` 是 `TaskName` 属性的字段：

 [!code-csharp[DataTemplatingIntro_snip#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Data.cs#tostring)]
 [!code-vb[DataTemplatingIntro_snip#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/data.vb#tostring)]

 然后如下所示<xref:System.Windows.Controls.ListBox>：

 ![数据模板化示例屏幕截图](./media/datatemplatingintro-fig2.png "DataTemplatingIntro_fig2")

 但是，这会受到限制且不灵活。 此外，如果要绑定到 XML 数据，将无法覆盖`ToString`。

<a name="defining_simple_datatemplate"></a>
### <a name="defining-a-simple-datatemplate"></a>定义简单的 DataTemplate
 解决方案是定义 。 <xref:System.Windows.DataTemplate> 一种方法是将 的属性<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A><xref:System.Windows.Controls.ListBox>设置为 。 <xref:System.Windows.DataTemplate> 在 中<xref:System.Windows.DataTemplate>指定的内容将成为数据对象的可视结构。 以下内容<xref:System.Windows.DataTemplate>相当简单。 我们指示每个项目在 中显示为三<xref:System.Windows.Controls.TextBlock>个<xref:System.Windows.Controls.StackPanel>元素。 每个<xref:System.Windows.Controls.TextBlock>元素都绑定到`Task`类的属性。

 [!code-xaml[DataTemplatingIntro_snip#Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#inline)]

 本主题中示例的基础数据是 CLR 对象的集合。 如果要绑定到 XML 数据，基本概念是相同的，但语法差异很小。 例如，`Path=TaskName`而不是将 设置为<xref:System.Windows.Data.Binding.XPath%2A> `@TaskName` （如果是`TaskName`XML 节点的属性）

 现在，<xref:System.Windows.Controls.ListBox>我们如下所示：

 ![数据模板化示例屏幕截图](./media/datatemplatingintro-fig3.png "DataTemplatingIntro_fig3")

<a name="defining_datatemplate_as_a_resource"></a>
### <a name="creating-the-datatemplate-as-a-resource"></a>将 DataTemplate 创建为资源
 在上面的示例中，我们定义了<xref:System.Windows.DataTemplate>内联。 常常在资源部分中定义它，以使其成为一个可重复使用的对象，如以下示例所示：

 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]
[!code-xaml[DataTemplatingIntro_snip#AsResource](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#asresource)]
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]

 现在可以将 `myTaskTemplate` 用作资源，如以下示例所示：

 [!code-xaml[DataTemplatingIntro_snip#MyTaskTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#mytasktemplate)]

 因为`myTaskTemplate`是一个资源，现在您可以在具有采用<xref:System.Windows.DataTemplate>类型的属性的其他控件上使用它。 如上所示，对于<xref:System.Windows.Controls.ItemsControl>对象（如 ，<xref:System.Windows.Controls.ListBox>它是 属性<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>）。 对于<xref:System.Windows.Controls.ContentControl>对象，它是属性<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>。

<a name="Styling_DataType"></a>
### <a name="the-datatype-property"></a>DataType 属性
 类<xref:System.Windows.DataTemplate>的属性<xref:System.Windows.DataTemplate.DataType%2A>与<xref:System.Windows.Style.TargetType%2A><xref:System.Windows.Style>类的属性非常相似。 因此，您可以执行以下操作`x:Key`，而不是<xref:System.Windows.DataTemplate>为 中例中为 指定 。

 [!code-xaml[DataTemplatingIntro_snip#DataType](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#datatype)]

 这将<xref:System.Windows.DataTemplate>自动应用于所有`Task`对象。 请注意，在这种情况下，隐式设置 `x:Key`。 因此，如果为此赋值<xref:System.Windows.DataTemplate>`x:Key`，则重写隐式`x:Key`值，并且不会自动应用<xref:System.Windows.DataTemplate>。

 如果要将<xref:System.Windows.Controls.ContentControl>绑定 到`Task`对象集合，<xref:System.Windows.Controls.ContentControl>则 不会自动使用上述<xref:System.Windows.DataTemplate>内容。 这是因为，对 的绑定<xref:System.Windows.Controls.ContentControl>需要更多信息来区分是绑定到整个集合还是单个对象。 如果正在<xref:System.Windows.Controls.ContentControl>跟踪<xref:System.Windows.Controls.ItemsControl>类型的选择，则可以将<xref:System.Windows.Data.Binding.Path%2A><xref:System.Windows.Controls.ContentControl>绑定的属性设置为""`/`以指示您对当前项感兴趣。 有关示例，请参阅[绑定到集合并基于选择显示信息](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)。 否则，您需要通过设置<xref:System.Windows.DataTemplate><xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>属性显式指定 。

 当您<xref:System.Windows.DataTemplate.DataType%2A>具有不同类型的数据对象时，<xref:System.Windows.Data.CompositeCollection>该属性特别有用。 有关示例，请参阅[实现 CompositeCollection](how-to-implement-a-compositecollection.md)。

<a name="adding_more_to_datatemplate"></a>
## <a name="adding-more-to-the-datatemplate"></a>向 DataTemplate 添加更多信息
 当前，数据显示了必要信息，但还可以显示更多信息。 让我们通过添加 、<xref:System.Windows.Controls.Border>和<xref:System.Windows.Controls.Grid>一些<xref:System.Windows.Controls.TextBlock>描述显示的数据的元素来改进演示文稿。

 [!code-xaml[DataTemplatingIntro#AddingMore](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore)]
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]

 以下屏幕截图显示了此修改<xref:System.Windows.Controls.ListBox><xref:System.Windows.DataTemplate>的 ：

 ![数据模板化示例屏幕截图](./media/datatemplatingintro-fig4.png "DataTemplatingIntro_fig4")

 我们可以在<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A><xref:System.Windows.HorizontalAlignment.Stretch>上<xref:System.Windows.Controls.ListBox>设置为，以确保项目的宽度占用整个空间：

 [!code-xaml[DataTemplatingIntro_snip#Stretch](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#stretch)]

 将<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>属性设置为<xref:System.Windows.HorizontalAlignment.Stretch>，<xref:System.Windows.Controls.ListBox>现在如下所示：

 ![数据模板化示例屏幕截图](./media/datatemplatingintro-fig5.png "DataTemplatingIntro_fig5")

<a name="DataTrigger_to_Apply_Property_Values"></a>
### <a name="use-datatriggers-to-apply-property-values"></a>使用 DataTriggers 应用属性值
 当前表示形式并未指出 `Task` 是家庭任务还是办公室任务。 请记住，`Task` 对象具有类型为 `TaskType` 的 `TaskType` 属性（该属性是一个枚举，其值为 `Home` 和 `Work`）。

 <xref:System.Windows.DataTrigger>在下面的示例中，<xref:System.Windows.Controls.Border.BorderBrush%2A>`border``Yellow`如果`TaskType`属性为`TaskType.Home`，则设置所命名的元素的 。

 [!code-xaml[DataTemplatingIntro#DT](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#dt)]
[!code-xaml[DataTemplatingIntro#DataTrigger](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#datatrigger)]
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]

 应用程序现在如下所示。 家庭任务的边界显示为黄色，办公室任务的边界显示为浅绿色：

 ![数据模板化示例屏幕截图](./media/datatemplatingintro-fig6.png "DataTemplatingIntro_fig6")

 在此示例中，<xref:System.Windows.DataTrigger>使用<xref:System.Windows.Setter>设置属性值。 触发器类还具有<xref:System.Windows.TriggerBase.EnterActions%2A>和<xref:System.Windows.TriggerBase.ExitActions%2A>属性，允许您启动一组操作，如动画。 此外，还有一个<xref:System.Windows.MultiDataTrigger>类允许您基于多个数据绑定属性值应用更改。

 实现相同效果的另一种方法是将<xref:System.Windows.Controls.Border.BorderBrush%2A>属性绑定到属性，`TaskType`并使用值转换器根据`TaskType`值返回颜色。 就性能而言，使用转换器实现上述效果的效率要高一些。 另外，创建自己的转换器可以提供更多灵活性，因为提供了自己的逻辑。 最后，选择使用何种技术取决于当时的具体情况和偏好。 有关如何编写转换器的信息，请参阅<xref:System.Windows.Data.IValueConverter>。

<a name="what_belongs_in_datatemplate"></a>
### <a name="what-belongs-in-a-datatemplate"></a>DataTemplate 中有哪些内容？

在前面的示例中，我们将触发器放在<xref:System.Windows.DataTemplate>使用 属性<xref:System.Windows.DataTemplate.Triggers%2A?displayProperty=nameWithType>中。 触发器<xref:System.Windows.Setter>的 设置 的元素（<xref:System.Windows.Controls.Border>元素）中的属性的值。 <xref:System.Windows.DataTemplate> 但是`Setters`，如果所关注的属性不是<xref:System.Windows.DataTemplate>当前元素的属性，则使用<xref:System.Windows.Style>用于<xref:System.Windows.Controls.ListBoxItem>类的属性设置属性可能更合适（如果绑定的控件是 。 <xref:System.Windows.Controls.ListBox> 例如，如果希望在<xref:System.Windows.Trigger>鼠标指向项时为项<xref:System.Windows.UIElement.Opacity%2A>的值设置动画，则可以在<xref:System.Windows.Controls.ListBoxItem>样式中定义触发器。 有关示例，请参阅[样式设置和模板化示例简介](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。

 通常，请记住，<xref:System.Windows.DataTemplate>正在应用于每个生成的<xref:System.Windows.Controls.ListBoxItem>（有关它的实际应用方式和位置的详细信息，请参阅<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>页面）。 您<xref:System.Windows.DataTemplate>只关心数据对象的表示和外观。 在大多数情况下，列表示的所有其他方面（如项目选择时的外观或<xref:System.Windows.Controls.ListBox>布局项的方式）不属于<xref:System.Windows.DataTemplate>的定义。 有关示例，请参阅[对 ItemsControl 进行样式设置和模板化](#DataTemplating_ItemsControl)一节。

<a name="Styling_StyleSelection"></a>
## <a name="choosing-a-datatemplate-based-on-properties-of-the-data-object"></a>根据数据对象的属性选择 DataTemplate
 在 [DataType 属性](#Styling_DataType)一节中，我们讨论了可为不同的数据对象定义不同的数据模板。 当您具有<xref:System.Windows.Data.CompositeCollection>不同类型的项目或集合时，这一点特别有用。 在"[使用数据触发器应用属性值"](#DataTrigger_to_Apply_Property_Values)部分中，我们显示，如果您拥有相同类型的数据对象的集合，则可以创建 ，<xref:System.Windows.DataTemplate>然后使用触发器根据每个数据对象的属性值应用更改。 虽然触发器允许你应用属性值或启动动画，但是它们无法让你灵活地重构数据对象的结构。 某些方案可能需要为相同类型但具有不同属性<xref:System.Windows.DataTemplate>的数据对象创建不同的数据对象。

 例如，当 `Task` 对象的 `Priority` 值为 `1` 时，可能需要为它指定完全不同的外观，以给予你自己一个提醒。 在这种情况下，您将创建用于显示高<xref:System.Windows.DataTemplate>优先级`Task`对象的 。 让我们将以下内容<xref:System.Windows.DataTemplate>添加到资源部分：

 [!code-xaml[DataTemplatingIntro_snip#ImportantTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#importanttemplate)]

此示例使用[DataTemplate.Resources](xref:System.Windows.FrameworkTemplate.Resources%2A)属性。 该节中定义的资源由 中的<xref:System.Windows.DataTemplate>元素共享。

 要<xref:System.Windows.DataTemplate>提供逻辑以根据数据`Priority`对象的值选择要使用的，请创建 和 重写 方法的<xref:System.Windows.Controls.DataTemplateSelector><xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A>子类。 在下面的示例中，<xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A>该方法提供逻辑，以便根据`Priority`属性的值返回相应的模板。 要返回的模板位于包络<xref:System.Windows.Window>元素的资源中找到。

 [!code-csharp[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/TaskListDataTemplateSelector.cs#dtsclass)]
 [!code-vb[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/tasklistdatatemplateselector.vb#dtsclass)]

 然后，我们可以将 `TaskListDataTemplateSelector` 声明为资源：

 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]
[!code-xaml[DataTemplatingIntro_snip#DTS](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#dts)]
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]

 要使用模板选择器资源，请将其分配给<xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>的属性。 <xref:System.Windows.Controls.ListBox> 调用<xref:System.Windows.Controls.ListBox><xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A>基础集合中每个`TaskListDataTemplateSelector`项的 该调用会将数据对象作为项参数传递。 然后<xref:System.Windows.DataTemplate>，该方法返回的 将应用于该数据对象。

 [!code-xaml[DataTemplatingIntro_snip#ItemTemplateSelector](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemtemplateselector)]

 在模板选择器就位后，<xref:System.Windows.Controls.ListBox>现在如下所示：

 ![数据模板化示例屏幕截图](./media/datatemplatingintro-fig7.png "DataTemplatingIntro_fig7")

这正是此示例要得到的结果。 有关完整示例，请参阅[数据模板化示例简介](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/DataTemplatingIntro)。

<a name="DataTemplating_ItemsControl"></a>
## <a name="styling-and-templating-an-itemscontrol"></a>对 ItemsControl 进行样式设置和模板化
 即使<xref:System.Windows.Controls.ItemsControl>不是 可以使用<xref:System.Windows.DataTemplate>的唯一控件类型，但将 绑定 到<xref:System.Windows.Controls.ItemsControl>集合是很常见的方案。 在[DataTemplate 部分的"属于什么"部分中](#what_belongs_in_datatemplate)，我们讨论了<xref:System.Windows.DataTemplate>您的定义应只与数据的表示有关。 为了知道何时不适合使用 。 <xref:System.Windows.DataTemplate> <xref:System.Windows.Controls.ItemsControl> 以下示例旨在演示上述每个属性的功能。 此示例<xref:System.Windows.Controls.ItemsControl>中的 绑定到与上一个`Tasks`示例中相同的集合。 为便于演示，本示例中的样式和模板都进行了内联声明。

 [!code-xaml[DataTemplatingIntro_snip#ItemsControlProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemscontrolproperties)]

 下面是该示例在呈现时的屏幕快照：

 ![ItemsControl 示例屏幕快照](./media/databinding-itemscontrolproperties.png "DataBinding_ItemsControlProperties")

 请注意，可以使用 而不是<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>使用<xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>。 请参考上一节中的示例。 同样，可以使用 的选项，<xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>而不是使用<xref:System.Windows.Controls.ItemsControl.ItemContainerStyleSelector%2A>。

 此处未显示的 的 两<xref:System.Windows.Controls.ItemsControl>个与样式相关的属性是<xref:System.Windows.Controls.ItemsControl.GroupStyle%2A><xref:System.Windows.Controls.ItemsControl.GroupStyleSelector%2A>和 。

<a name="DataTemplating_HeirarchicalDataTemplate"></a>
## <a name="support-for-hierarchical-data"></a>对分层数据的支持
 到目前为止，我们仅讨论了如何绑定到并显示单个集合。 某些时候，具有的集合包含其他集合。 类<xref:System.Windows.HierarchicalDataTemplate>设计为用于显示此类数据<xref:System.Windows.Controls.HeaderedItemsControl>的类型。 在以下示例中，`ListLeagueList` 是 `League` 对象的列表。 每个 `League` 对象都有一个 `Name` 和 `Division` 对象的集合。 每个 `Division` 都有一个 `Name` 和 `Team` 对象的集合，并且每个 `Team` 对象都有一个 `Name`。

 [!code-xaml[HierarchicalDataTemplateSnippet#HDT](~/samples/snippets/csharp/VS_Snippets_Wpf/HierarchicalDataTemplateSnippet/CS/window1.xaml#hdt)]

 该示例显示，使用<xref:System.Windows.HierarchicalDataTemplate>时可以轻松地显示包含其他列表的列表数据。 下面是该示例的一个屏幕快照。

 ![分层数据模板示例屏幕截图](./media/databinding-hierarchicaldatatemplate.png "DataBinding_HierarchicalDataTemplate")

## <a name="see-also"></a>另请参阅

- [数据绑定](../advanced/optimizing-performance-data-binding.md)
- [查找数据模板生成的元素](how-to-find-datatemplate-generated-elements.md)
- [样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)
- [GridView 列标题的样式和模板概述](../controls/gridview-column-header-styles-and-templates-overview.md)
