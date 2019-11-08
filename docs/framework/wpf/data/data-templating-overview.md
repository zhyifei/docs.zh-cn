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
ms.openlocfilehash: 377ee76e7e3537e9cae010189306611a503acbed
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740634"
---
# <a name="data-templating-overview"></a>数据模板化概述
WPF 数据模板化模型为定义数据的表示提供了很大的灵活性。 WPF 控件具有支持自定义数据表示的内置功能。 本主题首先演示如何定义 <xref:System.Windows.DataTemplate>，然后引入其他数据模板化功能，如基于自定义逻辑的模板选择和对分层数据的显示的支持。  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisites  
 本主题重点介绍数据模板化功能，不介绍数据绑定概念。 有关基本数据绑定概念的信息，请参阅[数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)。  
  
 <xref:System.Windows.DataTemplate> 是数据的表示形式，是 WPF 样式设置和模板化模型所提供的众多功能之一。 如要介绍 WPF 样式设置和模板化模型（例如如何使用 <xref:System.Windows.Style> 设置控件的属性），请参阅[样式设置和模板化](../controls/styling-and-templating.md)主题。  
  
 此外，请务必了解 `Resources`，这一点实质上使对象（如 <xref:System.Windows.Style> 和 <xref:System.Windows.DataTemplate>）可重复使用。 有关资源的详细信息，请参阅 [XAML 资源](../advanced/xaml-resources.md)。  
  
<a name="DataTemplating_Basic"></a>   
## <a name="data-templating-basics"></a>数据模板化基础知识  
  
 为了演示 <xref:System.Windows.DataTemplate> 很重要的原因，让我们来演练一个数据绑定示例。 在此示例中，我们有一个绑定到 `Task` 对象列表的 <xref:System.Windows.Controls.ListBox>。 每个 `Task` 对象都有 `TaskName` (string)、`Description` (string)、`Priority` (int) 和 `TaskType` 类型的属性（它是一个 `Enum`，其值为 `Home` 和 `Work`）。  
  
 [!code-xaml[DataTemplatingIntro_snip#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#resources)]  
[!code-xaml[DataTemplatingIntro_snip#UI1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui1)]  
[!code-xaml[DataTemplatingIntro_snip#UI2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui2)]  
  
<a name="without_a_datatemplate"></a>   
### <a name="without-a-datatemplate"></a>不提供 DataTemplate  
 如果没有 <xref:System.Windows.DataTemplate>，则 <xref:System.Windows.Controls.ListBox> 当前如下所示：  
  
 ![数据模板化示例屏幕快照](./media/datatemplatingintro-fig1.png "DataTemplatingIntro_fig1")  
  
 发生的情况是，在没有任何特定说明的情况下，<xref:System.Windows.Controls.ListBox> 默认情况下，在尝试显示集合中的对象时，会调用 `ToString`。 因此，如果 `Task` 对象重写 `ToString` 方法，则 <xref:System.Windows.Controls.ListBox> 会显示基础集合中每个源对象的字符串表示形式。  
  
 例如，如果 `Task` 类以这种方式重写 `ToString` 方法，其中 `name` 是 `TaskName` 属性的字段：  
  
 [!code-csharp[DataTemplatingIntro_snip#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Data.cs#tostring)]
 [!code-vb[DataTemplatingIntro_snip#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/data.vb#tostring)]  
  
 然后 <xref:System.Windows.Controls.ListBox> 如下所示：  
  
 ![数据模板化示例屏幕快照](./media/datatemplatingintro-fig2.png "DataTemplatingIntro_fig2")  
  
 但是，这会受到限制且不灵活。 此外，如果您要绑定到 XML 数据，您将无法重写 `ToString`。  
  
<a name="defining_simple_datatemplate"></a>   
### <a name="defining-a-simple-datatemplate"></a>定义简单的 DataTemplate  
 解决方法是定义 <xref:System.Windows.DataTemplate>。 实现此目的的一种方法是将 <xref:System.Windows.Controls.ListBox> 的 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 属性设置为 <xref:System.Windows.DataTemplate>。 您在 <xref:System.Windows.DataTemplate> 中指定的内容将成为您的数据对象的可视结构。 以下 <xref:System.Windows.DataTemplate> 非常简单。 我们将提供每个项在 <xref:System.Windows.Controls.StackPanel>中显示为三个 <xref:System.Windows.Controls.TextBlock> 元素的说明。 每个 <xref:System.Windows.Controls.TextBlock> 元素都绑定到 `Task` 类的属性。  
  
 [!code-xaml[DataTemplatingIntro_snip#Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#inline)]  
  
 本主题中的示例的基础数据是 CLR 对象的集合。 如果要绑定到 XML 数据，基本概念是相同的，但有一些细微的差别。 例如，将 <xref:System.Windows.Data.Binding.XPath%2A> 设置为 `@TaskName` （如果 `TaskName` 是 XML 节点的属性），而不是让 `Path=TaskName`。  
  
 现在，我们的 <xref:System.Windows.Controls.ListBox> 如下所示：  
  
 ![数据模板化示例屏幕快照](./media/datatemplatingintro-fig3.png "DataTemplatingIntro_fig3")  
  
<a name="defining_datatemplate_as_a_resource"></a>   
### <a name="creating-the-datatemplate-as-a-resource"></a>将 DataTemplate 创建为资源  
 在上面的示例中，我们定义了内联 <xref:System.Windows.DataTemplate>。 常常在资源部分中定义它，以使其成为一个可重复使用的对象，如以下示例所示：  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#AsResource](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#asresource)]  
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 现在可以将 `myTaskTemplate` 用作资源，如以下示例所示：  
  
 [!code-xaml[DataTemplatingIntro_snip#MyTaskTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#mytasktemplate)]  
  
 由于 `myTaskTemplate` 是资源，因此你现在可以在具有采用 <xref:System.Windows.DataTemplate> 类型的属性的其他控件上使用它。 如上所示，对于 <xref:System.Windows.Controls.ItemsControl> 对象，如 <xref:System.Windows.Controls.ListBox>，它是 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 属性。 对于 <xref:System.Windows.Controls.ContentControl> 对象，它是 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 属性。  
  
<a name="Styling_DataType"></a>   
### <a name="the-datatype-property"></a>DataType 属性  
 <xref:System.Windows.DataTemplate> 类的 <xref:System.Windows.DataTemplate.DataType%2A> 属性与 <xref:System.Windows.Style> 类的 <xref:System.Windows.Style.TargetType%2A> 属性非常相似。 因此，可以执行以下操作，而不是在上面的示例中为 <xref:System.Windows.DataTemplate> 指定 `x:Key`：  
  
 [!code-xaml[DataTemplatingIntro_snip#DataType](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#datatype)]  
  
 此 <xref:System.Windows.DataTemplate> 会自动应用到所有 `Task` 对象。 请注意，在这种情况下，隐式设置 `x:Key`。 因此，如果将此 <xref:System.Windows.DataTemplate> `x:Key` 值，则将重写隐式 `x:Key`，并且不会自动应用 <xref:System.Windows.DataTemplate>。  
  
 如果要将 <xref:System.Windows.Controls.ContentControl> 绑定到 `Task` 对象的集合，<xref:System.Windows.Controls.ContentControl> 不会自动使用以上 <xref:System.Windows.DataTemplate>。 这是因为 <xref:System.Windows.Controls.ContentControl> 上的绑定需要更多的信息来区分你是要绑定到整个集合还是单个对象。 如果 <xref:System.Windows.Controls.ContentControl> 跟踪 <xref:System.Windows.Controls.ItemsControl> 类型的选择，则可以将 <xref:System.Windows.Controls.ContentControl> 绑定的 <xref:System.Windows.Data.Binding.Path%2A> 属性设置为 "`/`"，以指示你对当前项感兴趣。 有关示例，请参阅[绑定到集合并基于选择显示信息](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)。 否则，需要通过设置 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 属性显式指定 <xref:System.Windows.DataTemplate>。  
  
 当您具有不同类型的数据对象的 <xref:System.Windows.Data.CompositeCollection> 时，<xref:System.Windows.DataTemplate.DataType%2A> 属性特别有用。 有关示例，请参阅[实现 CompositeCollection](how-to-implement-a-compositecollection.md)。  
  
<a name="adding_more_to_datatemplate"></a>   
## <a name="adding-more-to-the-datatemplate"></a>向 DataTemplate 添加更多信息  
 当前，数据显示了必要信息，但还可以显示更多信息。 接下来，我们将添加一个 <xref:System.Windows.Controls.Border>、一个 <xref:System.Windows.Controls.Grid>和一些 <xref:System.Windows.Controls.TextBlock> 元素，这些元素描述正在显示的数据。  
  
 [!code-xaml[DataTemplatingIntro#AddingMore](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 以下屏幕截图显示了此修改 <xref:System.Windows.DataTemplate>的 <xref:System.Windows.Controls.ListBox>：  
  
 ![数据模板化示例屏幕快照](./media/datatemplatingintro-fig4.png "DataTemplatingIntro_fig4")  
  
 我们可以将 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 设置为 <xref:System.Windows.HorizontalAlignment.Stretch> 在 <xref:System.Windows.Controls.ListBox> 上，以确保项的宽度占用整个空间：  
  
 [!code-xaml[DataTemplatingIntro_snip#Stretch](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#stretch)]  
  
 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 属性设置为 <xref:System.Windows.HorizontalAlignment.Stretch>后，<xref:System.Windows.Controls.ListBox> 现在如下所示：  
  
 ![数据模板化示例屏幕快照](./media/datatemplatingintro-fig5.png "DataTemplatingIntro_fig5")  
  
<a name="DataTrigger_to_Apply_Property_Values"></a>   
### <a name="use-datatriggers-to-apply-property-values"></a>使用 DataTriggers 应用属性值  
 当前表示形式并未指出 `Task` 是家庭任务还是办公室任务。 请记住，`Task` 对象具有类型为 `TaskType` 的 `TaskType` 属性（该属性是一个枚举，其值为 `Home` 和 `Work`）。  
  
 在下面的示例中，<xref:System.Windows.DataTrigger> 将名为 `border` 的元素的 <xref:System.Windows.Controls.Border.BorderBrush%2A> 设置为 `Yellow` （如果 `TaskType` 属性为 `TaskType.Home`）。  
  
 [!code-xaml[DataTemplatingIntro#DT](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#dt)]  
[!code-xaml[DataTemplatingIntro#DataTrigger](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#datatrigger)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 应用程序现在如下所示。 家庭任务的边界显示为黄色，办公室任务的边界显示为浅绿色：  
  
 ![数据模板化示例屏幕快照](./media/datatemplatingintro-fig6.png "DataTemplatingIntro_fig6")  
  
 在此示例中，<xref:System.Windows.DataTrigger> 使用 <xref:System.Windows.Setter> 设置属性值。 触发器类还具有 <xref:System.Windows.TriggerBase.EnterActions%2A> 和 <xref:System.Windows.TriggerBase.ExitActions%2A> 属性，可用于启动一组操作，例如动画。 此外，还有一个 <xref:System.Windows.MultiDataTrigger> 类，可用于基于多个数据绑定属性值应用更改。  
  
 实现相同效果的另一种方法是将 <xref:System.Windows.Controls.Border.BorderBrush%2A> 属性绑定到 `TaskType` 属性，并使用值转换器根据 `TaskType` 值返回颜色。 就性能而言，使用转换器实现上述效果的效率要高一些。 另外，创建自己的转换器可以提供更多灵活性，因为提供了自己的逻辑。 最后，选择使用何种技术取决于当时的具体情况和偏好。 有关如何编写转换器的信息，请参阅 <xref:System.Windows.Data.IValueConverter>。  
  
<a name="what_belongs_in_datatemplate"></a>   
### <a name="what-belongs-in-a-datatemplate"></a>DataTemplate 中有哪些内容？  

在上面的示例中，我们使用 <xref:System.Windows.DataTemplate>在 <xref:System.Windows.DataTemplate> 中放置了触发器。<xref:System.Windows.DataTemplate.Triggers%2A> 属性。 触发器的 <xref:System.Windows.Setter> 设置位于 <xref:System.Windows.DataTemplate>内的元素（<xref:System.Windows.Controls.Border> 元素）的属性的值。 但是，如果您的 `Setters` 与之相关的属性不是当前 <xref:System.Windows.DataTemplate>内的元素的属性，则更适合使用 <xref:System.Windows.Controls.ListBoxItem> 类的 <xref:System.Windows.Style> 设置属性（如果您绑定的控件是<xref:System.Windows.Controls.ListBox>）。 例如，如果你希望 <xref:System.Windows.Trigger> 在鼠标指向某个项时对该项的 <xref:System.Windows.UIElement.Opacity%2A> 值进行动画处理，则需要在 <xref:System.Windows.Controls.ListBoxItem> 样式中定义触发器。 有关示例，请参阅[样式设置和模板化示例简介](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。
  
 一般情况下，请记住，<xref:System.Windows.DataTemplate> 将应用于每个生成的 <xref:System.Windows.Controls.ListBoxItem> （有关其实际应用方式和位置的详细信息，请参阅 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 页）。 您的 <xref:System.Windows.DataTemplate> 仅涉及数据对象的显示和外观。 在大多数情况下，显示的所有其他方面（例如，选择项时的外观，或者 <xref:System.Windows.Controls.ListBox> 布局项的方式）不属于 <xref:System.Windows.DataTemplate>的定义。 有关示例，请参阅[对 ItemsControl 进行样式设置和模板化](#DataTemplating_ItemsControl)一节。  
  
<a name="Styling_StyleSelection"></a>   
## <a name="choosing-a-datatemplate-based-on-properties-of-the-data-object"></a>根据数据对象的属性选择 DataTemplate  
 在 [DataType 属性](#Styling_DataType)一节中，我们讨论了可为不同的数据对象定义不同的数据模板。 当你的不同类型或集合的 <xref:System.Windows.Data.CompositeCollection> 具有不同类型的项时，这特别有用。 在 "[使用 Datatrigger 应用属性值](#DataTrigger_to_Apply_Property_Values)" 部分中，我们已显示，如果你有一个相同类型的数据对象的集合，则可以创建 <xref:System.Windows.DataTemplate>，然后根据每个数据对象的属性值使用触发器来应用更改。 虽然触发器允许你应用属性值或启动动画，但是它们无法让你灵活地重构数据对象的结构。 某些情况下，可能需要为类型相同但具有不同属性的数据对象创建不同 <xref:System.Windows.DataTemplate>。  
  
 例如，当 `Task` 对象的 `Priority` 值为 `1` 时，可能需要为它指定完全不同的外观，以给予你自己一个提醒。 在这种情况下，将为高优先级 `Task` 对象的显示创建 <xref:System.Windows.DataTemplate>。 让我们将以下 <xref:System.Windows.DataTemplate> 添加到 resources 部分：  
  
 [!code-xaml[DataTemplatingIntro_snip#ImportantTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#importanttemplate)]  
  
 请注意，此示例使用 <xref:System.Windows.DataTemplate>。<xref:System.Windows.FrameworkTemplate.Resources%2A> 属性。 此部分中定义的资源由 <xref:System.Windows.DataTemplate>中的元素共享。  
  
 若要根据数据对象的 `Priority` 值提供逻辑来选择要使用的 <xref:System.Windows.DataTemplate>，请创建 <xref:System.Windows.Controls.DataTemplateSelector> 的子类并重写 <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> 方法。 在下面的示例中，<xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> 方法提供逻辑，以根据 `Priority` 属性的值返回相应的模板。 在封装 <xref:System.Windows.Window> 元素的资源中找到要返回的模板。  
  
 [!code-csharp[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/TaskListDataTemplateSelector.cs#dtsclass)]
 [!code-vb[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/tasklistdatatemplateselector.vb#dtsclass)]  
  
 然后，我们可以将 `TaskListDataTemplateSelector` 声明为资源：  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#DTS](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#dts)]  
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 若要使用模板选择器资源，请将其分配给 <xref:System.Windows.Controls.ListBox>的 <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> 属性。 <xref:System.Windows.Controls.ListBox> 为基础集合中的每个项调用 `TaskListDataTemplateSelector` 的 <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> 方法。 该调用会将数据对象作为项参数传递。 然后，将方法返回 <xref:System.Windows.DataTemplate> 应用于该数据对象。  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemTemplateSelector](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemtemplateselector)]  
  
 设置模板选择器后，<xref:System.Windows.Controls.ListBox> 现在如下所示：  
  
 ![数据模板化示例屏幕快照](./media/datatemplatingintro-fig7.png "DataTemplatingIntro_fig7")  

这正是此示例要得到的结果。 有关完整示例，请参阅[数据模板化示例简介](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/DataTemplatingIntro)。

<a name="DataTemplating_ItemsControl"></a>   
## <a name="styling-and-templating-an-itemscontrol"></a>对 ItemsControl 进行样式设置和模板化  
 即使 <xref:System.Windows.Controls.ItemsControl> 不是可以使用 <xref:System.Windows.DataTemplate> 的唯一控件类型，也是将 <xref:System.Windows.Controls.ItemsControl> 绑定到集合的一个非常常见的方案。 在[system.windows.datatemplate>](#what_belongs_in_datatemplate)部分中，我们讨论了 <xref:System.Windows.DataTemplate> 的定义只应涉及数据的显示。 为了了解何时不适合使用 <xref:System.Windows.DataTemplate>，了解 <xref:System.Windows.Controls.ItemsControl>提供的不同样式和模板属性是很重要的。 以下示例旨在演示上述每个属性的功能。 本示例中的 <xref:System.Windows.Controls.ItemsControl> 绑定到与上一示例中相同的 `Tasks` 集合。 为便于演示，本示例中的样式和模板都进行了内联声明。  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemsControlProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemscontrolproperties)]  
  
 下面是该示例在呈现时的屏幕快照：  
  
 ![System.windows.controls.itemscontrol> 示例屏幕快照](./media/databinding-itemscontrolproperties.png "DataBinding_ItemsControlProperties")  
  
 请注意，您可以使用 <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>，而不是使用 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>。 请参考上一节中的示例。 同样，您可以选择使用 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyleSelector%2A>，而不是使用 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>。  
  
 此处未显示的 <xref:System.Windows.Controls.ItemsControl> 的两个其他样式相关属性 <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> 和 <xref:System.Windows.Controls.ItemsControl.GroupStyleSelector%2A>。  
  
<a name="DataTemplating_HeirarchicalDataTemplate"></a>   
## <a name="support-for-hierarchical-data"></a>对分层数据的支持  
 到目前为止，我们仅讨论了如何绑定到并显示单个集合。 某些时候，具有的集合包含其他集合。 <xref:System.Windows.HierarchicalDataTemplate> 类旨在与 <xref:System.Windows.Controls.HeaderedItemsControl> 类型一起用于显示此类数据。 在以下示例中，`ListLeagueList` 是 `League` 对象的列表。 每个 `League` 对象都有一个 `Name` 和 `Division` 对象的集合。 每个 `Division` 都有一个 `Name` 和 `Team` 对象的集合，并且每个 `Team` 对象都有一个 `Name`。  
  
 [!code-xaml[HierarchicalDataTemplateSnippet#HDT](~/samples/snippets/csharp/VS_Snippets_Wpf/HierarchicalDataTemplateSnippet/CS/window1.xaml#hdt)]  
  
 该示例演示了使用 <xref:System.Windows.HierarchicalDataTemplate>，可以轻松地显示包含其他列表的列表数据。 下面是该示例的一个屏幕快照。  
  
 ![HierarchicalDataTemplate 示例屏幕快照](./media/databinding-hierarchicaldatatemplate.png "DataBinding_HierarchicalDataTemplate")  
  
## <a name="see-also"></a>请参阅

- [数据绑定](../advanced/optimizing-performance-data-binding.md)
- [查找由 DataTemplate 生成的元素](how-to-find-datatemplate-generated-elements.md)
- [样式设置和模板化](../controls/styling-and-templating.md)
- [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)
- [GridView 列标题的样式和模板概述](../controls/gridview-column-header-styles-and-templates-overview.md)
