---
title: "数据模板化概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], templates
- binding data [WPF], templates
- templates [WPF], data
- data templates [WPF]
ms.assetid: 0f4d9f8c-0230-4013-bd7b-e8e7fed01b4a
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 91ab838ec543e2cc17e380ee9ec0d629989a003e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="data-templating-overview"></a>数据模板化概述
WPF 数据模板化模型为定义数据的表示提供了很大的灵活性。 WPF 控件具有支持自定义数据表示的内置功能。 本主题首先演示了如何定义<xref:System.Windows.DataTemplate>，然后介绍其他数据模板化功能，例如选择了基于自定义逻辑和分层数据的显示的支持的模板。  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>先决条件  
 本主题重点介绍数据模板化功能，不介绍数据绑定概念。 有关基本数据绑定概念的信息，请参阅[数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)。  
  
 <xref:System.Windows.DataTemplate>是有关数据的表示形式，由 WPF 样式和模板化模型提供的许多功能之一。 有关 WPF 样式和模板化模型，例如如何使用的介绍<xref:System.Windows.Style>若要设置控件的属性，请参阅[样式和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)主题。  
  
 此外，务必了解`Resources`，这是实质上是什么启用对象例如<xref:System.Windows.Style>和<xref:System.Windows.DataTemplate>为了能够重新使用。 有关资源的详细信息，请参阅 [XAML 资源](../../../../docs/framework/wpf/advanced/xaml-resources.md)。  
  
<a name="DataTemplating_Basic"></a>   
## <a name="data-templating-basics"></a>数据模板化基础知识  
  
 为了演示原因<xref:System.Windows.DataTemplate>很重要，让我们演练一下数据绑定示例。 在此示例中，我们有<xref:System.Windows.Controls.ListBox>，它绑定到的列表`Task`对象。 每个 `Task` 对象都有 `TaskName` (string)、`Description` (string)、`Priority` (int) 和 `TaskType` 类型的属性（它是一个 `Enum`，其值为 `Home` 和 `Work`）。  
  
 [!code-xaml[DataTemplatingIntro_snip#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#resources)]  
[!code-xaml[DataTemplatingIntro_snip#UI1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui1)]  
[!code-xaml[DataTemplatingIntro_snip#UI2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui2)]  
  
<a name="without_a_datatemplate"></a>   
### <a name="without-a-datatemplate"></a>不提供 DataTemplate  
 而无需<xref:System.Windows.DataTemplate>，我们<xref:System.Windows.Controls.ListBox>当前如下所示：  
  
 ![数据模板化示例屏幕快照](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig1.png "DataTemplatingIntro_fig1")  
  
 发生了什么情况是，如果没有任何特殊说明<xref:System.Windows.Controls.ListBox>默认调用`ToString`时尝试在集合中显示的对象。 因此，如果`Task`对象重写`ToString`方法，则<xref:System.Windows.Controls.ListBox>基础集合中显示的每个源对象的字符串表示。  
  
 例如，如果 `Task` 类以这种方式重写 `ToString` 方法，其中 `name` 是 `TaskName` 属性的字段：  
  
 [!code-csharp[DataTemplatingIntro_snip#ToString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Data.cs#tostring)]
 [!code-vb[DataTemplatingIntro_snip#ToString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/data.vb#tostring)]  
  
 则<xref:System.Windows.Controls.ListBox>如下所示：  
  
 ![数据模板化示例屏幕快照](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig2.png "DataTemplatingIntro_fig2")  
  
 但是，这会受到限制且不灵活。 此外，如果要绑定到 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 数据，将不能重写 `ToString`。  
  
<a name="defining_simple_datatemplate"></a>   
### <a name="defining-a-simple-datatemplate"></a>定义简单的 DataTemplate  
 解决方法是定义<xref:System.Windows.DataTemplate>。 若要这样做的一种方法是设置<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>属性<xref:System.Windows.Controls.ListBox>到<xref:System.Windows.DataTemplate>。 在中指定你<xref:System.Windows.DataTemplate>变成您的数据对象的可视结构。 以下<xref:System.Windows.DataTemplate>非常简单。 我们将向每个项都显示为三个说明<xref:System.Windows.Controls.TextBlock>中的元素<xref:System.Windows.Controls.StackPanel>。 每个<xref:System.Windows.Controls.TextBlock>元素绑定到的属性`Task`类。  
  
 [!code-xaml[DataTemplatingIntro_snip#Inline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#inline)]  
  
 本主题中示例的基础数据是 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 对象的一个集合。 如果要绑定到 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 数据，基本概念都相同，只不过语法稍微不同。 例如，而不是`Path=TaskName`，则会将设置<xref:System.Windows.Data.Binding.XPath%2A>到`@TaskName`(如果`TaskName`是特性你[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]节点)。  
  
 现在我们<xref:System.Windows.Controls.ListBox>如下所示：  
  
 ![数据模板化示例屏幕快照](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig3.png "DataTemplatingIntro_fig3")  
  
<a name="defining_datatemplate_as_a_resource"></a>   
### <a name="creating-the-datatemplate-as-a-resource"></a>将 DataTemplate 创建为资源  
 在上面的示例中，我们定义<xref:System.Windows.DataTemplate>内联。 常常在资源部分中定义它，以使其成为一个可重复使用的对象，如以下示例所示：  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#AsResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#asresource)]  
[!code-xaml[DataTemplatingIntro_snip#R2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 现在可以将 `myTaskTemplate` 用作资源，如以下示例所示：  
  
 [!code-xaml[DataTemplatingIntro_snip#MyTaskTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#mytasktemplate)]  
  
 因为`myTaskTemplate`是一种资源，你现在可以具有一个属性，采用其他控件使用其<xref:System.Windows.DataTemplate>类型。 如上所示，为<xref:System.Windows.Controls.ItemsControl>对象，如<xref:System.Windows.Controls.ListBox>，它是<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>属性。 有关<xref:System.Windows.Controls.ContentControl>对象，它是<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>属性。  
  
<a name="Styling_DataType"></a>   
### <a name="the-datatype-property"></a>DataType 属性  
 <xref:System.Windows.DataTemplate>类具有<xref:System.Windows.DataTemplate.DataType%2A>属性都非常类似于<xref:System.Windows.Style.TargetType%2A>属性<xref:System.Windows.Style>类。 因此，而不是指定`x:Key`为<xref:System.Windows.DataTemplate>在上面的示例中，你可以执行以下操作：  
  
 [!code-xaml[DataTemplatingIntro_snip#DataType](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#datatype)]  
  
 这<xref:System.Windows.DataTemplate>获取自动应用到所有`Task`对象。 请注意，在这种情况下，隐式设置 `x:Key`。 因此，如果将此分配<xref:System.Windows.DataTemplate>`x:Key`值，您要重写的隐式`x:Key`和<xref:System.Windows.DataTemplate>不会自动应用。  
  
 如果你正在绑定<xref:System.Windows.Controls.ContentControl>到的集合`Task`对象，<xref:System.Windows.Controls.ContentControl>不使用上述<xref:System.Windows.DataTemplate>自动。 这是因为上的绑定<xref:System.Windows.Controls.ContentControl>需要区分你是否想要将绑定到整个集合或单个对象的详细信息。 如果你<xref:System.Windows.Controls.ContentControl>跟踪的选定内容<xref:System.Windows.Controls.ItemsControl>类型，你可以设置<xref:System.Windows.Data.Binding.Path%2A>属性<xref:System.Windows.Controls.ContentControl>绑定到"`/`"以指示你感兴趣的当前项。 有关示例，请参阅[绑定到集合并基于选择显示信息](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)。 否则，你需要指定<xref:System.Windows.DataTemplate>显式通过设置<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>属性。  
  
 <xref:System.Windows.DataTemplate.DataType%2A>必须时特别有用属性<xref:System.Windows.Data.CompositeCollection>的不同类型的数据对象。 有关示例，请参阅[实现 CompositeCollection](../../../../docs/framework/wpf/data/how-to-implement-a-compositecollection.md)。  
  
<a name="adding_more_to_datatemplate"></a>   
## <a name="adding-more-to-the-datatemplate"></a>向 DataTemplate 添加更多信息  
 当前，数据显示了必要信息，但还可以显示更多信息。 让我们对其进行改进演示文稿通过添加<xref:System.Windows.Controls.Border>、 <xref:System.Windows.Controls.Grid>，和某些<xref:System.Windows.Controls.TextBlock>描述正在显示的数据的元素。  
  
 [!code-xaml[DataTemplatingIntro#AddingMore](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 以下屏幕快照显示<xref:System.Windows.Controls.ListBox>与此修改<xref:System.Windows.DataTemplate>:  
  
 ![数据模板化示例屏幕快照](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig4.png "DataTemplatingIntro_fig4")  
  
 我们可以设置<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>到<xref:System.Windows.HorizontalAlignment.Stretch>上<xref:System.Windows.Controls.ListBox>若要确保的项的宽度占用整个空间：  
  
 [!code-xaml[DataTemplatingIntro_snip#Stretch](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#stretch)]  
  
 与<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>属性设置为<xref:System.Windows.HorizontalAlignment.Stretch>、<xref:System.Windows.Controls.ListBox>现在如下所示：  
  
 ![数据模板化示例屏幕快照](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig5.png "DataTemplatingIntro_fig5")  
  
<a name="DataTrigger_to_Apply_Property_Values"></a>   
### <a name="use-datatriggers-to-apply-property-values"></a>使用 DataTriggers 应用属性值  
 当前表示形式并未指出 `Task` 是家庭任务还是办公室任务。 请记住，`Task` 对象具有类型为 `TaskType` 的 `TaskType` 属性（该属性是一个枚举，其值为 `Home` 和 `Work`）。  
  
 在下面的示例中，<xref:System.Windows.DataTrigger>设置<xref:System.Windows.Controls.Border.BorderBrush%2A>的名为的元素`border`到`Yellow`如果`TaskType`属性是`TaskType.Home`。  
  
 [!code-xaml[DataTemplatingIntro#DT](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#dt)]  
[!code-xaml[DataTemplatingIntro#DataTrigger](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#datatrigger)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 应用程序现在如下所示。 家庭任务的边界显示为黄色，办公室任务的边界显示为浅绿色：  
  
 ![数据模板化示例屏幕快照](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig6.png "DataTemplatingIntro_fig6")  
  
 在此示例中<xref:System.Windows.DataTrigger>使用<xref:System.Windows.Setter>设置属性值。 触发器类也有<xref:System.Windows.TriggerBase.EnterActions%2A>和<xref:System.Windows.TriggerBase.ExitActions%2A>，你可以启动一组操作，例如动画的属性。 此外，还有<xref:System.Windows.MultiDataTrigger>类，该类允许你以应用更改基于多个数据绑定属性值。  
  
 一种替代方式来实现相同的效果是将绑定<xref:System.Windows.Controls.Border.BorderBrush%2A>属性`TaskType`属性和值转换器来返回颜色基于的使用`TaskType`值。 就性能而言，使用转换器实现上述效果的效率要高一些。 另外，创建自己的转换器可以提供更多灵活性，因为提供了自己的逻辑。 最后，选择使用何种技术取决于当时的具体情况和偏好。 有关如何编写转换器的信息，请参阅<xref:System.Windows.Data.IValueConverter>。  
  
<a name="what_belongs_in_datatemplate"></a>   
### <a name="what-belongs-in-a-datatemplate"></a>DataTemplate 中有哪些内容？  
 在前面的示例中，我们放置内的触发器<xref:System.Windows.DataTemplate>使用<xref:System.Windows.DataTemplate>。<xref:System.Windows.DataTemplate.Triggers%2A>属性。 <xref:System.Windows.Setter>的触发器设置元素的属性的值 (<xref:System.Windows.Controls.Border>元素)，位于<xref:System.Windows.DataTemplate>。 但是，如果属性，你`Setters`关注不在当前的元素的属性<xref:System.Windows.DataTemplate>，它可能更适合于设置使用的属性<xref:System.Windows.Style>对于就是<xref:System.Windows.Controls.ListBoxItem>类 (如果你正在绑定的控件是<xref:System.Windows.Controls.ListBox>)。 例如，如果你希望你<xref:System.Windows.Trigger>要进行动画处理<xref:System.Windows.UIElement.Opacity%2A>值的项时鼠标指向某一项，定义内的触发器<xref:System.Windows.Controls.ListBoxItem>样式。 有关示例，请参阅[样式设置和模板化示例简介](http://go.microsoft.com/fwlink/?LinkID=160010)。  
  
 一般情况下，请记住，<xref:System.Windows.DataTemplate>被应用到每个生成<xref:System.Windows.Controls.ListBoxItem>(有关如何以及在何处，它实际应用的详细信息，请参阅<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>页。)。 你<xref:System.Windows.DataTemplate>是关心的演示文稿和数据对象的外观。 在大多数情况下，所有其他方面的演示文稿，如哪些项看起来像选择此项时或如何<xref:System.Windows.Controls.ListBox>排列项，不属于的定义中<xref:System.Windows.DataTemplate>。 有关示例，请参阅[对 ItemsControl 进行样式设置和模板化](#DataTemplating_ItemsControl)一节。  
  
<a name="Styling_StyleSelection"></a>   
## <a name="choosing-a-datatemplate-based-on-properties-of-the-data-object"></a>根据数据对象的属性选择 DataTemplate  
 在 [DataType 属性](#Styling_DataType)一节中，我们讨论了可为不同的数据对象定义不同的数据模板。 这是特别有用时必须<xref:System.Windows.Data.CompositeCollection>的不同类型或使用不同类型的项的集合。 在[使用数据来应用属性值的触发器](#DataTrigger_to_Apply_Property_Values)部分中，我们已经演示，是否你具有的相同类型的数据对象集合你可以创建<xref:System.Windows.DataTemplate>，然后使用触发器应用基于的属性值的更改每个数据对象。 虽然触发器允许你应用属性值或启动动画，但是它们无法让你灵活地重构数据对象的结构。 某些情况下，可能需要创建其他<xref:System.Windows.DataTemplate>数据属于相同的对象类型，但具有不同的属性。  
  
 例如，当 `Task` 对象的 `Priority` 值为 `1` 时，可能需要为它指定完全不同的外观，以给予你自己一个提醒。 在这种情况下，创建<xref:System.Windows.DataTemplate>优先级较高显示`Task`对象。 让我们将以下代码添加<xref:System.Windows.DataTemplate>到资源部分：  
  
 [!code-xaml[DataTemplatingIntro_snip#ImportantTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#importanttemplate)]  
  
 请注意此示例使用<xref:System.Windows.DataTemplate>。<xref:System.Windows.FrameworkTemplate.Resources%2A>属性。 资源定义中，部分共享中的元素的<xref:System.Windows.DataTemplate>。  
  
 若要提供逻辑选择哪个<xref:System.Windows.DataTemplate>使用基于`Priority`值的数据对象，创建一个子类<xref:System.Windows.Controls.DataTemplateSelector>，并重写<xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A>方法。 在下面的示例中，<xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A>方法提供逻辑来返回适当的模板的值基于`Priority`属性。 要返回的模板文件位于封装的资源<xref:System.Windows.Window>元素。  
  
 [!code-csharp[DataTemplatingIntro_snip#DTSClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/TaskListDataTemplateSelector.cs#dtsclass)]
 [!code-vb[DataTemplatingIntro_snip#DTSClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/tasklistdatatemplateselector.vb#dtsclass)]  
  
 然后，我们可以将 `TaskListDataTemplateSelector` 声明为资源：  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#DTS](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#dts)]  
[!code-xaml[DataTemplatingIntro_snip#R2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 若要使用的模板选择器资源，将其分配给<xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>属性<xref:System.Windows.Controls.ListBox>。 <xref:System.Windows.Controls.ListBox>调用<xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A>方法`TaskListDataTemplateSelector`为每个项在基础集合。 该调用会将数据对象作为项参数传递。 <xref:System.Windows.DataTemplate>返回方法然后应用于该数据对象。  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemTemplateSelector](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemtemplateselector)]  
  
 使用就地情况下，模板选择器<xref:System.Windows.Controls.ListBox>现在显示，如下所示：  
  
 ![数据模板化示例屏幕快照](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig7.png "DataTemplatingIntro_fig7")  
  
 这正是此示例要得到的结果。 有关完整示例，请参阅[数据模板化示例简介](http://go.microsoft.com/fwlink/?LinkID=160009)。  
  
<a name="DataTemplating_ItemsControl"></a>   
## <a name="styling-and-templating-an-itemscontrol"></a>对 ItemsControl 进行样式设置和模板化  
 即使<xref:System.Windows.Controls.ItemsControl>不是唯一的控件类型，你可以使用<xref:System.Windows.DataTemplate>，它是非常常见的方案将绑定<xref:System.Windows.Controls.ItemsControl>到集合。 在[什么所属 DataTemplate 中](#what_belongs_in_datatemplate)部分所述的定义你<xref:System.Windows.DataTemplate>只应关心数据的表示形式。 才能知道当不适合用于<xref:System.Windows.DataTemplate>务必了解提供的不同样式和模板属性<xref:System.Windows.Controls.ItemsControl>。 以下示例旨在演示上述每个属性的功能。 <xref:System.Windows.Controls.ItemsControl>在此示例将绑定到相同`Tasks`如同前面的示例的集合。 为便于演示，本示例中的样式和模板都进行了内联声明。  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemsControlProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemscontrolproperties)]  
  
 下面是该示例在呈现时的屏幕快照：  
  
 ![ItemsControl 示例屏幕快照](../../../../docs/framework/wpf/data/media/databinding-itemscontrolproperties.png "DataBinding_ItemsControlProperties")  
  
 请注意，而不是使用<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>，你可以使用<xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>。 请参考上一节中的示例。 同样，而不是使用<xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>，你可以选择要使用<xref:System.Windows.Controls.ItemsControl.ItemContainerStyleSelector%2A>。  
  
 两个其他样式相关的属性<xref:System.Windows.Controls.ItemsControl>，不会显示如下<xref:System.Windows.Controls.ItemsControl.GroupStyle%2A>和<xref:System.Windows.Controls.ItemsControl.GroupStyleSelector%2A>。  
  
<a name="DataTemplating_HeirarchicalDataTemplate"></a>   
## <a name="support-for-hierarchical-data"></a>对分层数据的支持  
 到目前为止，我们仅讨论了如何绑定到并显示单个集合。 某些时候，具有的集合包含其他集合。 <xref:System.Windows.HierarchicalDataTemplate>类旨在用于<xref:System.Windows.Controls.HeaderedItemsControl>要显示此类数据类型。 在以下示例中，`ListLeagueList` 是 `League` 对象的列表。 每个 `League` 对象都有一个 `Name` 和 `Division` 对象的集合。 每个 `Division` 都有一个 `Name` 和 `Team` 对象的集合，并且每个 `Team` 对象都有一个 `Name`。  
  
 [!code-xaml[HierarchicalDataTemplateSnippet#HDT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HierarchicalDataTemplateSnippet/CS/window1.xaml#hdt)]  
  
 该示例演示使用<xref:System.Windows.HierarchicalDataTemplate>，您可以轻松地显示包含其他列表的列表数据。 下面是该示例的一个屏幕快照。  
  
 ![HierarchicalDataTemplate 示例屏幕快照](../../../../docs/framework/wpf/data/media/databinding-hierarchicaldatatemplate.png "DataBinding_HierarchicalDataTemplate")  
  
## <a name="see-also"></a>另请参阅  
 [数据绑定](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [查找由 DataTemplate 生成的元素](../../../../docs/framework/wpf/data/how-to-find-datatemplate-generated-elements.md)  
 [样式设置和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [GridView 列标题的样式和模板概述](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md)
