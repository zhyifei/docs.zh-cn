---
title: 数据绑定概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data conversion for binding [WPF]
- binding data [WPF], about data binding
- data binding [WPF], about data binding
- conversion for data binding [WPF]
ms.assetid: c707c95f-7811-401d-956e-2fffd019a211
ms.openlocfilehash: 44a35131273c6f191ab5da5bc1639d97bd961ff1
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567513"
---
# <a name="data-binding-overview"></a>数据绑定概述
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 数据绑定为应用程序呈现数据并与数据交互提供了一种简单且一致的方式。 元素可以绑定到各种数据源中的数据, 格式为公共语言运行时 (CLR) 对象和[!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]。 <xref:System.Windows.Controls.ContentControl><xref:System.Windows.Controls.Button>等和<xref:System.Windows.Controls.ItemsControl>都具有内置功能,可实现单一数据项或数据项集合的灵活样式。<xref:System.Windows.Controls.ListBox> <xref:System.Windows.Controls.ListView> 可基于数据生成排序、筛选和分组视图。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中的数据绑定功能与传统模型相比具有几个优点，包括本质上支持数据绑定的大量属性、灵活的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 数据 UI 表示形式以及业务逻辑与 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 的完全分离。  
  
 本主题首先讨论有关[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]数据绑定的基本概念, 并探讨<xref:System.Windows.Data.Binding>类的用法和数据绑定的其他功能。  

<a name="what_is_data_binding"></a>   
## <a name="what-is-data-binding"></a>什么是数据绑定？  
 数据绑定是在应用程序 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 和业务逻辑之间建立连接的过程。 如果绑定具有正确的设置，并且数据提供适当的通知，则在数据更改其值时，绑定到该数据的元素会自动反映更改。 数据绑定还意味着，如果元素中数据的外部表示形式发生更改，则基础数据可以自动进行更新以反映更改。 例如, 如果用户编辑<xref:System.Windows.Controls.TextBox>元素中的值, 则基础数据值会自动更新以反映此更改。  
  
 数据绑定的典型用法是将服务器或本地配置数据放置到窗体或其他 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 控件中。 在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中，此概念得到扩展，包括将大量属性绑定到各种数据源。 在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]中, 元素的依赖项属性可以绑定到 CLR 对象 (包括与 web 服务和 web 属性相关联的 ADO.NET 对象或[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]对象) 和数据。  
  
 有关数据绑定的示例，请参阅[数据绑定演示](https://go.microsoft.com/fwlink/?LinkID=163703)中的以下应用程序 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]：  
  
 ![数据绑定示例屏幕快照](./media/databinding-databindingdemo.png "DataBinding_DataBindingDemo")  
  
 以上是一个显示拍卖项列表的应用程序 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。 应用程序演示了数据绑定的以下功能：  
  
- 的<xref:System.Windows.Controls.ListBox>内容绑定到*AuctionItem*对象的集合。 *AuctionItem* 对象具有 *Description*、*StartPrice*、*StartDate*、*Category*、*SpecialFeatures* 等属性。  
  
- 中显示的 <xref:System.Windows.Controls.ListBox>数据 (AuctionItem 对象) 为模板化, 以便为每个项目显示说明和当前价格。 这是使用来完成<xref:System.Windows.DataTemplate>的。 此外，每个项的外观取决于要显示的 *AuctionItem* 的 *SpecialFeatures* 值。 如果 *AuctionItem* 的 *SpecialFeatures* 值为 *Color*，则该项具有蓝色边框。 如果值为 *Highlight*，则该项具有橙色边框和一个星号。 [数据模板化](#data_templating)部分提供了数据模板化的相关信息。  
  
- 用户可以使用所提供的<xref:System.Windows.Controls.CheckBox>es 对数据进行分组、筛选或排序。 在上面的图像中, 选择了 "按类别分组" 和 "按类别排序和<xref:System.Windows.Controls.CheckBox>日期排序"。 你可能已注意到，数据按产品类别分组，类别名称按字母顺序排序。 这些项还按每个类别中的开始日期排序，但难以从图中注意到这一点。 这可使用*集合视图*来实现。 [绑定到集合](#binding_to_collections)部分讨论了集合视图。  
  
- 当用户选择某一项时, <xref:System.Windows.Controls.ContentControl>将显示所选项的详细信息。 这称为*主从方案*。 [主从方案](#master_detail_scenario)部分提供了有关此类型的绑定方案的信息。  
  
- 开始属性的类型为<xref:System.DateTime>, 它返回包含毫秒的时间的日期。 在此应用程序中，使用了一个自定义转换器，以便显示较短的日期字符串。 [数据转换](#data_conversion)部分提供了有关转换器的信息。  
  
 当用户单击“添加产品”按钮时，会出现以下窗体：  
  
 ![添加产品清单页](./media/databinding-demo-addproductlisting.png "DataBinding_Demo_AddProductListing")  
  
 用户可以编辑窗体中的字段，使用简略预览和详细预览窗格来预览产品清单，然后单击“提交”以添加新的产品清单。 任何现有的分组、筛选和排序功能都将应用于新项。 在这种特殊情况下，上图中输入的项会作为 *Computer* 类别中的第二项显示。  
  
 此图中未显示的是在*开始日期* <xref:System.Windows.Controls.TextBox>提供的验证逻辑。 如果用户输入无效的日期 (格式无效或过去的日期), 则将向用户通知<xref:System.Windows.Controls.ToolTip> , 旁边<xref:System.Windows.Controls.TextBox>有一个红色的感叹号。 [数据验证](#data_validation)一节讨论了如何创建验证逻辑。  
  
 在详细介绍数据绑定的上述不同功能之前，我们会先在下一节中讨论一些对理解 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 数据绑定非常重要的基本概念。  
  
## <a name="basic-data-binding-concepts"></a>数据绑定基本概念  
  
 不论要绑定什么元素，也不论数据源的特性是什么，每个绑定都始终遵循下图所示的模型：  
  
 ![显示基本数据绑定模型的关系图。](./media/data-binding-overview/basic-data-binding-diagram.png)  
  
 如上图所示，数据绑定实质上是绑定目标与绑定源之间的桥梁。 该图演示了以下基本的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 数据绑定概念：  
  
- 通常，每个绑定都具有以下四个组件：绑定目标对象、目标属性、绑定源，以及要使用的绑定源中的值路径。 例如, 如果想要将的<xref:System.Windows.Controls.TextBox>内容绑定到*Employee*对象的<xref:System.Windows.Controls.TextBox> *Name*属性, 则目标对象为, 目标属性是<xref:System.Windows.Controls.TextBox.Text%2A>属性, 要使用的值为*Name*,源对象是*Employee*对象。  
  
- 目标属性必须为依赖属性。 大多数<xref:System.Windows.UIElement>属性都是依赖属性, 大多数依赖属性 (只读属性除外) 默认支持数据绑定。 (仅<xref:System.Windows.DependencyObject>类型可以定义依赖属性, 而<xref:System.Windows.UIElement>所有的都<xref:System.Windows.DependencyObject>是从派生的。)  
  
- 虽然图中未指定, 但应注意, 绑定源对象并不限于自定义 CLR 对象。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]数据绑定支持 CLR 对象和[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]格式的数据。 若要提供一些示例, 绑定源可以是<xref:System.Windows.UIElement>、任何列表对象、与 ADO.NET 数据或 Web 服务关联的 CLR 对象, 也可以是[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]包含数据的 XmlNode。 有关详细信息，请参阅[绑定源概述](binding-sources-overview.md)。  
  
 当你通读其他 SDK 主题时, 请务必记住, 在建立绑定时, 将绑定目标绑定*到*绑定源。 例如, 如果<xref:System.Windows.Controls.ListBox>使用数据绑定显示某些基础[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]数据<xref:System.Windows.Controls.ListBox> , 则[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]会将绑定到数据。  
  
 若要建立绑定, 请使用<xref:System.Windows.Data.Binding>对象。 本主题的其余部分讨论与相关联的许多概念以及<xref:System.Windows.Data.Binding>对象的一些属性和用法。  
  
<a name="direction_of_data_flow"></a>   
### <a name="direction-of-the-data-flow"></a>数据流的方向  
 如前所述, 如上图中的箭头所示, 绑定的数据流可以从绑定目标传输到绑定源 (例如, 当用户编辑的<xref:System.Windows.Controls.TextBox>值时, 源值将更改) 和/或从绑定源如果绑定源提供了正确的通知, <xref:System.Windows.Controls.TextBox>则为绑定目标 (例如, 内容会更新到绑定源中的更改)。  
  
 可能希望应用程序允许用户更改数据，然后将该数据传播回源对象。 或者，可能不希望允许用户更新源数据。 可以通过设置<xref:System.Windows.Data.Binding>对象的属性对<xref:System.Windows.Data.Binding.Mode%2A>此进行控制。 下图演示了不同类型的数据流：  
  
 ![数据绑定数据流](./media/databinding-dataflow.png "DataBinding_DataFlow")  
  
- <xref:System.Windows.Data.BindingMode.OneWay>绑定会导致对源属性的更改自动更新目标属性, 但对目标属性所做的更改不会传播回 source 属性。 如果绑定的控件为隐式只读，则此类型的绑定适用。 例如，可能绑定到如股票行情自动收录器这样的源，或许目标属性没有用于进行更改的控件接口（如表的数据绑定背景色）。 如果无需监视目标属性的更改，则使用 <xref:System.Windows.Data.BindingMode.OneWay> 绑定模式可避免 <xref:System.Windows.Data.BindingMode.TwoWay> 绑定模式的系统开销。  
  
- <xref:System.Windows.Data.BindingMode.TwoWay>绑定会导致对源属性或目标属性的更改自动更新。 此类型的绑定适用于可编辑窗体或其他完整交互式的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 方案。 大多数属性默认为<xref:System.Windows.Data.BindingMode.OneWay>绑定, 但某些依赖属性 (通常是用户可编辑控件的属性<xref:System.Windows.Controls.TextBox> , 例如<xref:System.Windows.Controls.TextBox.Text%2A>的属性和<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>的属性<xref:System.Windows.Controls.CheckBox>) 默认为<xref:System.Windows.Data.BindingMode.TwoWay>绑定。 确定依赖属性绑定在默认情况下是单向还是双向的编程方法是：使用 <xref:System.Windows.DependencyProperty.GetMetadata%2A> 获取属性的属性元数据，然后检查 <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A> 属性的布尔值。  
  
- <xref:System.Windows.Data.BindingMode.OneWayToSource>是反向<xref:System.Windows.Data.BindingMode.OneWay>绑定; 当目标属性发生更改时, 它将更新源属性。 一个示例方案是只需要从 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 重新计算源值的情况。  
  
- 图中未说明<xref:System.Windows.Data.BindingMode.OneTime>绑定, 这会导致源属性初始化目标属性, 但后续更改不会传播。 这意味着，如果数据上下文发生了更改，或者数据上下文中的对象发生了更改，该更改不会反映在目标属性中。 如果你在适合使用当前状态的快照或数据实际为静态数据的位置使用数据，则此类型的绑定适合。 如果你想使用源属性中的某个值来初始化目标属性，且提前不知道数据上下文，则此类型的绑定也有用。 这是实质上是 <xref:System.Windows.Data.BindingMode.OneWay> 绑定的一种简化形式，它在源值不更改的情况下提供更好的性能。  
  
 请注意, 若要检测源更改 ( <xref:System.Windows.Data.BindingMode.OneWay>适用<xref:System.Windows.Data.BindingMode.TwoWay>于和绑定), 源必须实现适当的属性<xref:System.ComponentModel.INotifyPropertyChanged>更改通知机制, 例如。 有关<xref:System.ComponentModel.INotifyPropertyChanged>实现的示例, 请参阅[实现属性更改通知](how-to-implement-property-change-notification.md)。  
  
 <xref:System.Windows.Data.Binding.Mode%2A>属性页提供了有关绑定模式的详细信息, 以及如何指定绑定方向的示例。  
  
<a name="what_triggers_source_updates"></a>   
### <a name="what-triggers-source-updates"></a>触发源更新的因素  
 作为<xref:System.Windows.Data.BindingMode.TwoWay> 或<xref:System.Windows.Data.BindingMode.OneWayToSource>侦听目标属性中的更改并将其传播回源的绑定。 这称为更新源。 例如，可以编辑文本框的文本以更改基础源值。 如最后一部分所述, 数据流的方向由绑定的<xref:System.Windows.Data.Binding.Mode%2A>属性值决定。  
  
 但是，源值是在编辑文本的同时进行更新，还是在结束编辑文本并将鼠标指针从文本框移走后才进行更新呢？ 绑定<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>的属性确定源更新的触发因素。 下图中右箭头的点说明了<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>属性的角色:  
  
 ![显示 System.windows.data.binding.updatesourcetrigger 属性的角色的关系图。](./media/data-binding-overview/data-binding-updatesource-trigger.png)  
  
 如果值为<xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, 则<xref:System.Windows.Data.BindingMode.TwoWay>或<xref:System.Windows.Data.BindingMode.OneWayToSource>的右箭头指向的值将在目标属性更改后立即更新。 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 但是, 如果<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>该值为, <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>则只有当目标属性失去焦点时, 该值才会更新为新值。  
  
 与属性类似, 不同的依赖属性具有不同的<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>默认值。 <xref:System.Windows.Data.Binding.Mode%2A> 大多数依赖属性的默认值为 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>，而 <xref:System.Windows.Controls.TextBox.Text%2A> 属性的默认值为 <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>。 这意味着, 当目标属性发生更改时, 通常会发生源更新, 这<xref:System.Windows.Controls.CheckBox>对于 es 和其他简单控件来说是很不错的。 但对于文本字段，每次击键之后都进行更新会降低性能，用户也没有机会在提交新值之前使用 Backspace 键修改键入错误。 这就是为什么<xref:System.Windows.Controls.TextBox.Text%2A>属性具有默认<xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>值而不是的<xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>原因。  
  
 有关如何查找依赖属性的默认<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>值的信息, 请参阅属性页。<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>  
  
 下表提供了<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> <xref:System.Windows.Controls.TextBox>使用作为示例的每个值的示例方案:  
  
|UpdateSourceTrigger 值|源值何时进行更新|文本框的示例方案|  
|-------------------------------|----------------------------------------|----------------------------------|  
|LostFocus (默认值<xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>)|当 TextBox 控件失去焦点时|<xref:System.Windows.Controls.TextBox>与验证逻辑关联的 (请参阅 "数据验证" 一节)|  
|PropertyChanged|当你键入<xref:System.Windows.Controls.TextBox>|<xref:System.Windows.Controls.TextBox>聊天室窗口中的控件|  
|Explicit|当应用程序调用<xref:System.Windows.Data.BindingExpression.UpdateSource%2A>|<xref:System.Windows.Controls.TextBox>可编辑窗体中的控件 (仅当用户单击 "提交" 按钮时才更新源值)|  
  
 有关示例，请参阅[控制文本框文本更新源的时间](how-to-control-when-the-textbox-text-updates-the-source.md)。  
  
<a name="creating_a_binding"></a>   
## <a name="creating-a-binding"></a>创建绑定  
  
 若要 recapitulate 前面几节中讨论的一些概念, 请使用<xref:System.Windows.Data.Binding>对象建立绑定, 每个绑定通常具有四个组件: 绑定目标、目标属性、绑定源和要使用的源值的路径。 本节讨论如何设置绑定。  
  
 请考虑以下示例，其中的绑定源对象是一个名为 *MyData* 的类，该类在 *SDKSample* 命名空间中定义。 出于演示目的，*MyData* 类具有一个名为 *ColorName* 的字符串属性，该属性的值设置为“Red”。 因此，此示例生成一个具有红色背景的按钮。  
  
 [!code-xaml[BindNonTextProperty#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindNonTextProperty/CS/Page1.xaml#1)]  
  
 有关绑定声明语法的详细信息以及如何在代码中设置绑定的示例，请参阅[绑定声明概述](binding-declarations-overview.md)。  
  
 如果将此示例应用于基本关系图，则生成的图如下所示。 这是一个<xref:System.Windows.Data.BindingMode.OneWay>绑定, 因为默认情况下<xref:System.Windows.Data.BindingMode.OneWay> , 该后台属性支持绑定。  
  
 ![显示数据绑定背景属性的关系图。](./media/data-binding-overview/data-binding-button-background-example.png)  
  
 尽管*ColorName*属性的类型为字符串<xref:System.Windows.Controls.Control.Background%2A> , 但该属性的类型<xref:System.Windows.Media.Brush>为, 但你可能想知道为什么此操作有效。 这是由于进行了默认类型转换，此类型转换在[数据转换](#data_conversion)一节中进行讨论。  
  
<a name="specifying_the_binding_source"></a>   
### <a name="specifying-the-binding-source"></a>指定绑定源  
 请注意, 在上面的示例中, 通过在<xref:System.Windows.FrameworkElement.DataContext%2A> <xref:System.Windows.Controls.DockPanel>元素上设置属性来指定绑定源。 然后从中继承<xref:System.Windows.FrameworkElement.DataContext%2A>值,该值是其父元素。<xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.Button> 重申一下，绑定源对象是绑定的四个必需组件之一。 因此，如果未指定绑定源对象，则绑定将没有任何作用。  
  
 可通过多种方法指定绑定源对象。 将多个属性绑定到同一个源时, 对父元素使用属性非常有用。<xref:System.Windows.FrameworkElement.DataContext%2A> 不过，有时在个别绑定声明中指定绑定源可能更为合适。 对于前面的示例, <xref:System.Windows.FrameworkElement.DataContext%2A>可以通过直接在按钮的绑定声明上<xref:System.Windows.Data.Binding.Source%2A>设置属性来指定绑定源, 如以下示例中所示:  
  
 [!code-xaml[BindNonTextProperty#BackgroundBindingCompact](~/samples/snippets/csharp/VS_Snippets_Wpf/BindNonTextProperty/CS/Page2.xaml#backgroundbindingcompact)]  
  
 除了直接在元素<xref:System.Windows.FrameworkElement.DataContext%2A>上设置属性, 还会从祖先<xref:System.Windows.FrameworkElement.DataContext%2A>继承值 (如第一个示例中的按钮), 并通过设置中的<xref:System.Windows.Data.Binding.Source%2A>属性显式指定绑定源。<xref:System.Windows.Data.Binding>(如最后一个示例中的按钮), 也可以使用<xref:System.Windows.Data.Binding.ElementName%2A>属性<xref:System.Windows.Data.Binding.RelativeSource%2A>或属性来指定绑定源。 如果要绑定到应用程序中的其他元素 (例如, 当使用滑块调整按钮的宽度时),属性会很有用。<xref:System.Windows.Data.Binding.ElementName%2A> 如果<xref:System.Windows.Data.Binding.RelativeSource%2A> 在或<xref:System.Windows.Style>中指定了绑定, 则属性很有用。 <xref:System.Windows.Controls.ControlTemplate> 有关详细信息，请参阅[指定绑定源](how-to-specify-the-binding-source.md)。  
  
<a name="specifying_the_path_to_the_value"></a>   
### <a name="specifying-the-path-to-the-value"></a>指定值的路径  
 如果绑定源是一个对象, 则可以使用<xref:System.Windows.Data.Binding.Path%2A>属性来指定要用于绑定的值。 如果要绑定到[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]数据, 请<xref:System.Windows.Data.Binding.XPath%2A>使用属性指定值。 在某些情况下, 即使在您的数据为<xref:System.Windows.Data.Binding.Path%2A> [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]时也可能会使用属性。 例如, 如果想要访问返回的 XmlNode 的 Name 属性 (作为 XPath 查询的结果), 则应使用<xref:System.Windows.Data.Binding.Path%2A>属性以及<xref:System.Windows.Data.Binding.XPath%2A>属性。  
  
 有关语法信息和示例, 请参见<xref:System.Windows.Data.Binding.Path%2A>和<xref:System.Windows.Data.Binding.XPath%2A>属性页。  
  
 请注意, 尽管我们已经强调<xref:System.Windows.Data.Binding.Path%2A> , 要使用的值是绑定的四个必需组件之一, 但在要绑定到整个对象的情况下, 要使用的值将与绑定源对象的值相同。 在这些情况下, 它适用于不指定<xref:System.Windows.Data.Binding.Path%2A>。 请看下面的示例：  
  
 [!code-xaml[MasterDetail#EmptyBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetail/CSharp/Page1.xaml#emptybinding)]  
  
 以上示例使用空绑定语法：{Binding}。 在这种情况下<xref:System.Windows.Controls.ListBox> , 将从父 system.windows.controls.dockpanel> 元素继承 DataContext (在本示例中未显示)。 未指定路径时，默认为绑定到整个对象。 换句话说, 在此示例中, 路径已被省略, 因为我们要将<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>属性绑定到整个对象。 （有关深入讨论，请参阅[绑定到集合](#binding_to_collections)一节。）  
  
 除了绑定到集合以外，在希望绑定到整个对象，而不是仅绑定到对象的单个属性时，也可以使用此方案。 例如，在源对象为类型字符串，并且仅仅希望绑定到该字符串本身时。 另一种常见情况是希望将一个元素绑定到一个具有多个属性的对象。  
  
 请注意，可能需要应用自定义逻辑，以便数据对于绑定的目标属性有意义。 自定义逻辑可能采用自定义转换器形式（如果不存在默认的类型转换）。 有关转换器的信息，请参阅[数据转换](#data_conversion)。  
  
<a name="binding_bindingexpression"></a>   
### <a name="binding-and-bindingexpression"></a>Binding 和 BindingExpression  
 在进入数据绑定的其他功能和用法之前, 引入<xref:System.Windows.Data.BindingExpression>类将十分有用。 正如您在前面的<xref:System.Windows.Data.Binding>部分中所示, 类是绑定声明的高级类<xref:System.Windows.Data.Binding> ; 类提供了许多允许您指定绑定特性的属性。 相关类<xref:System.Windows.Data.BindingExpression>是维护源与目标之间的连接的基础对象。 一个绑定包含了可以在多个绑定表达式之间共享的所有信息。 是无法共享的实例表达式, 它包含的所有实例信息<xref:System.Windows.Data.Binding>。 <xref:System.Windows.Data.BindingExpression>  
  
 例如, 请考虑以下情况, 其中*myDataObject*是*MyData*类的实例, *myBinding*是源<xref:System.Windows.Data.Binding>对象, *MyData*类是包含名为*MyDataProperty*。 此示例将*mytext*(实例<xref:System.Windows.Controls.TextBlock>) 的文本内容绑定到*MyDataProperty*。  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 可以使用同一 *myBinding* 对象来创建其他绑定。 例如，可以使用 *myBinding* 对象将复选框的文本内容绑定到 *MyDataProperty*。 在这种情况下, 将有两个<xref:System.Windows.Data.BindingExpression>共享*myBinding*对象的实例。  
  
 可以通过对数据绑定对象调用<xref:System.Windows.Data.BindingOperations.GetBindingExpression%2A>的返回值来获取对象。<xref:System.Windows.Data.BindingExpression> 以下主题演示了<xref:System.Windows.Data.BindingExpression>类的一些用法:  
  
- [从已绑定的目标属性获取绑定对象](how-to-get-the-binding-object-from-a-bound-target-property.md)  
  
- [控制文本框文本更新源的时间](how-to-control-when-the-textbox-text-updates-the-source.md)  
  
<a name="data_conversion"></a>   
## <a name="data-conversion"></a>数据转换  
 在上面的示例中, 按钮是红色的, <xref:System.Windows.Controls.Control.Background%2A>因为其属性已绑定到值为 "red" 的字符串属性。 这是因为类型转换器在<xref:System.Windows.Media.Brush>类型上存在, 以将字符串值转换<xref:System.Windows.Media.Brush>为。  
  
 若要将此信息添加到[创建绑定](#creating_a_binding)一节的图中，关系图如下所示：  
  
 ![显示数据绑定默认属性的关系图。](./media/data-binding-overview/data-binding-button-default-conversion.png)  
  
 但是, 如果绑定源对象的*颜色*属性<xref:System.Windows.Media.Color>不是字符串类型, 则会发生什么情况呢？ 在这种情况下, 为了使绑定正常工作, 需要首先将*颜色*属性值转换为<xref:System.Windows.Controls.Control.Background%2A>属性接受的内容。 需要通过实现<xref:System.Windows.Data.IValueConverter>接口来创建自定义转换器, 如以下示例中所示:  
  
 [!code-csharp[ColorPicker_snip#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ColorPicker_snip/CSharp/ColorPickerLib/ColorPicker.cs#16)]
 [!code-vb[ColorPicker_snip#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ColorPicker_snip/visualbasic/colorpickerlib/colorpicker.vb#16)]  
  
 <xref:System.Windows.Data.IValueConverter>参考页提供了详细信息。  
  
 现在使用自定义转换器而不是默认转换，关系图如下所示：  
  
 ![显示数据绑定自定义转换器的关系图。](./media/data-binding-overview/data-binding-converter-color-example.png)  
  
 重申一下，由于要绑定到的类型中提供了类型转换器，因此可以使用默认转换。 此行为取决于目标中可用的类型转换器。 如果无法确定，请创建自己的转换器。  
  
 下面提供了一些典型方案，在这些方案中，实现数据转换器非常有意义：  
  
- 数据应根据区域性以不同方式显示。 例如，可能需要根据在特定区域性中使用的值或标准，实现货币转换器或日历日期/时间转换器。  
  
- 使用的数据不一定会更改属性的文本值，但会更改其他某个值（如图像的源，或显示文本的颜色或样式）。 在这种情况下，可以通过转换可能不合适的属性绑定（如将文本字段绑定到表单元格的 Background 属性）来使用转换器。  
  
- 将多个控件或控件的多个属性绑定到相同数据。 在这种情况下，主绑定可能仅显示文本，而其他绑定则处理特定的显示问题，但仍使用同一绑定作为源信息。  
  
- 到目前为止, 我们尚未讨论<xref:System.Windows.Data.MultiBinding>, 其中目标属性具有绑定的集合。 对于<xref:System.Windows.Data.MultiBinding>, 你可以使用自定义<xref:System.Windows.Data.IMultiValueConverter>从绑定值生成最终值。 例如，可以从红色、蓝色和绿色的值来计算颜色，这些值可能来自相同绑定源对象，也可能来自不同绑定源对象。 有关示例和信息, 请参阅类页。<xref:System.Windows.Data.MultiBinding>  
  
<a name="binding_to_collections"></a>   
## <a name="binding-to-collections"></a>绑定到集合  
  
 绑定源对象可以视为其属性包含数据的单个对象，也可以视为通常组合在一起的多态对象的数据集合（如数据库的查询结果）。 到目前为止，我们仅讨论了绑定到单个对象，但绑定到数据集合才是一种常见方案。 例如, 一种常见<xref:System.Windows.Controls.ItemsControl>方案是使用<xref:System.Windows.Controls.ListBox>、 <xref:System.Windows.Controls.ListView>或<xref:System.Windows.Controls.TreeView>来显示数据集合, 如在[什么是数据绑定？](#what_is_data_binding)一节中显示的应用程序中。  
  
 幸运的是，基本关系图仍然适用。 如果要将绑定<xref:System.Windows.Controls.ItemsControl>到集合, 关系图如下所示:  
  
 ![显示数据绑定 System.windows.controls.itemscontrol> 对象的关系图。](./media/data-binding-overview/data-binding-itemscontrol.png)  
  
 如图所示, 若要将绑定<xref:System.Windows.Controls.ItemsControl>到集合对象, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>属性是要使用的属性。 可以<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>将属性视为的内容<xref:System.Windows.Controls.ItemsControl>。 请注意, 此绑定<xref:System.Windows.Data.BindingMode.OneWay>是因为<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>默认情况<xref:System.Windows.Data.BindingMode.OneWay>下, 该属性支持绑定。  
  
<a name="how_to_implement_collections"></a>   
### <a name="how-to-implement-collections"></a>如何实现集合  
 可以枚举实现<xref:System.Collections.IEnumerable>接口的任何集合。 但是, 若要设置动态绑定, 以便集合中的插入或删除操作[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]自动更新, 该集合必须<xref:System.Collections.Specialized.INotifyCollectionChanged>实现接口。 此接口公开一个事件，只要基础集合发生更改，就应该引发该事件。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]提供类, 该类是<xref:System.Collections.Specialized.INotifyCollectionChanged>公开接口的数据集合的内置实现。 <xref:System.Collections.ObjectModel.ObservableCollection%601> 请注意, 若要完全支持将数据值从源对象传输到目标, 则支持可绑定属性的集合中的每个<xref:System.ComponentModel.INotifyPropertyChanged>对象还必须实现接口。 有关详细信息，请参阅[绑定源概述](binding-sources-overview.md)。  
  
 在实现自己的集合之前, 请<xref:System.Collections.ObjectModel.ObservableCollection%601>考虑使用或一个现有的集合类, <xref:System.Collections.Generic.List%601>例如、 <xref:System.Collections.ObjectModel.Collection%601>和<xref:System.ComponentModel.BindingList%601>。 如果你有一个高级方案, 并且想要实现自己的集合, 请<xref:System.Collections.IList>考虑使用, 它提供了一个对象的非泛型集合, 该集合可按索引单独访问, 从而获得最佳性能。  
  
<a name="collection_views"></a>   
### <a name="collection-views"></a>集合视图  
 <xref:System.Windows.Controls.ItemsControl>将绑定到数据集合后, 您可能需要对数据进行排序、筛选或分组。 为此, 需要使用集合视图, 这些视图是实现<xref:System.ComponentModel.ICollectionView>接口的类。  

#### <a name="what-are-collection-views"></a>什么是集合视图？  
 集合视图这一层基于绑定源集合，它允许基于排序、筛选和分组查询来导航并显示源集合，而无需更改基础源集合本身。 集合视图还维护一个指向集合中当前项的指针。 如果源集合实现了<xref:System.Collections.Specialized.INotifyCollectionChanged>接口, 则会将<xref:System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged>事件引发的更改传播到视图。  
  
 由于视图不会更改基础源集合，因此每个源集合都可以有多个关联的视图。 例如，可以有 *Task* 对象的集合。 使用视图，可以通过不同方式显示相同数据。 例如，可能希望在页面左侧显示按优先级排序的任务，而在页面右侧显示按区域分组的任务。  
  
<a name="how_to_create_a_view"></a>   
#### <a name="how-to-create-a-view"></a>如何创建视图  
 创建并使用视图的一种方式是直接实例化视图对象，然后将它用作绑定源。 例如，请考虑在[什么是数据绑定？](#what_is_data_binding)一节中显示的[数据绑定演示](https://go.microsoft.com/fwlink/?LinkID=163703)应用程序。 实现应用程序, 以便在<xref:System.Windows.Controls.ListBox>数据集合而不是直接对数据集合绑定到视图。 下面的示例摘自[数据绑定演示](https://go.microsoft.com/fwlink/?LinkID=163703)应用程序。 类是继承自<xref:System.Windows.Data.CollectionView>的类的代理。[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] <xref:System.Windows.Data.CollectionViewSource> 在此特定示例中, <xref:System.Windows.Data.CollectionViewSource.Source%2A>视图的绑定到当前应用程序对象的*AuctionItems*集合 ( <xref:System.Collections.ObjectModel.ObservableCollection%601>类型为)。  
  
 [!code-xaml[DataBindingLab#WindowResources1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#windowresources1)]  
[!code-xaml[DataBindingLab#CollectionViewSource](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#collectionviewsource)]  
[!code-xaml[DataBindingLab#WindowResources2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#windowresources2)]  
  
 然后, 资源*listingDataView*充当应用程序中的元素的绑定源, 例如<xref:System.Windows.Controls.ListBox>:  
  
 [!code-xaml[DataBindingLab#Master1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master1)]  
[!code-xaml[DataBindingLab#Master2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master2)]  
  
 若要为同一集合创建另一个视图, 可以创建另<xref:System.Windows.Data.CollectionViewSource>一个实例, 并为其`x:Key`指定一个不同的名称。  
  
 下表显示了将哪些视图数据类型创建为默认集合视图或<xref:System.Windows.Data.CollectionViewSource>基于源集合类型。  
  
|源集合类型|集合视图类型|说明|  
|----------------------------|--------------------------|-----------|  
|<xref:System.Collections.IEnumerable>|基于的内部类型<xref:System.Windows.Data.CollectionView>|无法对项进行分组。|  
|<xref:System.Collections.IList>|<xref:System.Windows.Data.ListCollectionView>|最快。|  
|<xref:System.ComponentModel.IBindingList>|<xref:System.Windows.Data.BindingListCollectionView>||  
  
##### <a name="using-a-default-view"></a>使用默认视图  
 创建并使用集合视图的一种方式是指定集合视图作为绑定源。 WPF 还会为用作绑定源的每个集合创建一个默认集合视图。 如果直接绑定到集合，WPF 会绑定到该集合的默认视图。 请注意，此默认视图由同一集合的所有绑定共享，因此一个绑定控件或代码对默认视图所做的更改（如排序或对当前项指针的更改，下文将对此进行讨论）会反映到同一集合的所有其他绑定中。  
  
 若要获取默认视图, 请使用<xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A>方法。 有关示例，请参阅[获取数据集合的默认视图](how-to-get-the-default-view-of-a-data-collection.md)。  
  
##### <a name="collection-views-with-adonet-datatables"></a>包含 ADO.NET DataTables 的集合视图  
 为了提高性能, ADO.NET <xref:System.Data.DataTable>或<xref:System.Data.DataView>对象的集合视图将对<xref:System.Data.DataView>进行排序和筛选。 这会导致排序和筛选任务由数据源的所有集合视图分担。 若要使每个集合视图分别进行排序和筛选, 请使用其自己<xref:System.Data.DataView>的对象初始化每个集合视图。  
  
#### <a name="sorting"></a>排序  
 如前所述，视图可以将排序顺序应用于集合。 如同在基础集合中一样，数据可能具有或不具有相关的固有顺序。 借助集合视图，可以根据自己提供的比较条件来强制确定顺序，或更改默认顺序。 由于这是基于客户端的数据视图，因此一种常见情况是用户可能希望根据列对应的值，对多列表格数据进行排序。 通过使用视图，可以应用这种用户实施的排序，而无需对基础集合进行任何更改，甚至不必再次查询集合内容。 有关示例，请参阅[在单击标题时对 GridView 列进行排序](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)。  
  
 下面的示例演示了 "[什么是数据绑定？](#what_is_data_binding) " 一节中的<xref:System.Windows.Controls.CheckBox> "按类别[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]和日期排序" 应用程序的排序逻辑:  
  
 [!code-csharp[DataBindingLab#8](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#8)]
 [!code-vb[DataBindingLab#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#8)]  
  
#### <a name="filtering"></a>筛选  
 视图还可以将筛选器应用于集合。 这意味着即使集合中可能存在一个项，此特定视图也仅用于显示整个集合的某个子集。 可以根据条件在数据中进行筛选。 例如, 当应用程序在[什么是数据绑定？](#what_is_data_binding)一节中完成, "仅显示 bargains" <xref:System.Windows.Controls.CheckBox>包含用于筛选出成本 $25 或更高的项的逻辑。 选择以下代码时<xref:System.Windows.Controls.CheckBox> , 将*ShowOnlyBargainsFilter* <xref:System.Windows.Data.CollectionViewSource.Filter>设置为事件处理程序:  
  
 [!code-csharp[DataBindingLab#10](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 *ShowOnlyBargainsFilter* 事件处理程序具有以下实现：  
  
 [!code-csharp[DataBindingLab#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
 如果直接使用某个<xref:System.Windows.Data.CollectionView>类<xref:System.Windows.Data.CollectionViewSource>而不是<xref:System.Windows.Data.CollectionView.Filter%2A> , 则可以使用属性来指定回调。 有关示例，请参阅[筛选视图中的数据](how-to-filter-data-in-a-view.md)。  
  
#### <a name="grouping"></a>分组  
 除查看<xref:System.Collections.IEnumerable>集合的内部类之外, 所有集合视图都支持分组功能, 这允许用户将集合视图中的集合分区为逻辑组。 这些组可以是显式的，由用户提供组列表；也可以是隐式的，这些组依据数据动态生成。  
  
 下面的示例显示 "Group by category" <xref:System.Windows.Controls.CheckBox>的逻辑:  
  
 [!code-csharp[DataBindingLab#6](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#6)]
 [!code-vb[DataBindingLab#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#6)]  
  
 有关其他分组示例，请参阅[对实现 GridView 的 ListView 中的项进行分组](../controls/how-to-group-items-in-a-listview-that-implements-a-gridview.md)。  
  
#### <a name="current-item-pointers"></a>当前项指针  
 视图还支持当前项的概念。 可以在集合视图中的对象之间导航。 在导航时，你是在移动项指针，该指针可用于检索存在于集合中特定位置的对象。 有关示例，请参阅[在数据集合视图中的对象之间导航](how-to-navigate-through-the-objects-in-a-data-collectionview.md)。  
  
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
  
 当前项指针可能会受对集合应用的任何排序或筛选操作的影响。 排序操作将当前项指针保留在所选的最后一项上，但集合视图现已围绕此指针重构。 （或许所选项以前曾位于列表的开头，但现在所选项可能位于中间的某个位置。）如果所选内容在筛选之后保留在视图中，则筛选操作会保留所选项。 否则，当前项指针会设置为经过筛选的集合视图的第一项。  
  
<a name="master_detail_scenario"></a>   
#### <a name="master-detail-binding-scenario"></a>主-从绑定方案  
 当前项的概念不仅适用于集合中各项的导航，也适用于主-从绑定方案。 再考虑一下[什么是数据绑定？](#what_is_data_binding)一节中的应用程序 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。 在该应用程序中, 中<xref:System.Windows.Controls.ListBox>的选择确定<xref:System.Windows.Controls.ContentControl>中显示的内容。 若要以另一种方式将其<xref:System.Windows.Controls.ListBox>放在选定项时<xref:System.Windows.Controls.ContentControl> , 将显示所选项的详细信息。  
  
 只需将两个或更多控件绑定到同一视图即可实现主-从方案。 以下来自[数据绑定演示](https://go.microsoft.com/fwlink/?LinkID=163703)的示例显示<xref:System.Windows.Controls.ListBox>了的标记, 以及<xref:System.Windows.Controls.ContentControl>在[什么是数据绑定？](#what_is_data_binding)一[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]节中的应用程序上看到的标记:  
  
 [!code-xaml[DataBindingLab#Master1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master1)]  
[!code-xaml[DataBindingLab#Master2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master2)]  
[!code-xaml[DataBindingLab#Detail](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#detail)]  
  
 请注意，这两个控件都绑定到同一个源，即 *listingDataView* 静态资源（请参阅[如何创建视图](#how_to_create_a_view)一节中此资源的定义）。 这是因为当单一实例对象 ( <xref:System.Windows.Controls.ContentControl>在本例中为) 绑定到集合视图时, 它会自动绑定到该<xref:System.Windows.Data.CollectionView.CurrentItem%2A>视图的。 请注意<xref:System.Windows.Data.CollectionViewSource> , 对象会自动同步货币和选择。 如果列表控件未绑定到<xref:System.Windows.Data.CollectionViewSource>对象 (如本示例所示), 则需要将其<xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A>属性设置为`true` , 以便此工作。  
  
 有关其他示例，请参阅[绑定到集合并基于选择显示信息](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)和[对分层数据使用主-从模式](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)。  
  
 你可能已经注意到上述示例使用了一个模板。 事实上, 数据不会以我们所需的方式显示, 无需使用模板 (显式<xref:System.Windows.Controls.ContentControl>使用的模板和<xref:System.Windows.Controls.ListBox>由隐式使用的模板)。 现在，我们开始介绍下一节中的数据模板化。  
  
<a name="data_templating"></a>   
## <a name="data-templating"></a>数据模板化  
 如果不使用数据模板，[什么是数据绑定？](#what_is_data_binding)一节中的应用程序 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 将如下所示：  
  
 ![没有数据模板的数据绑定演示](./media/data-binding-overview/data-binding-demo-templates.png)  
  
 如上一部分的示例中所示, <xref:System.Windows.Controls.ListBox>控件<xref:System.Windows.Controls.ContentControl>和都绑定到*AuctionItem*s 的整个集合对象 (或更具体地说, 是集合对象上的视图)。 如果没有关于如何显示数据集合的特定说明, <xref:System.Windows.Controls.ListBox>将显示基础集合中每个对象的字符串表示形式, <xref:System.Windows.Controls.ContentControl>并显示它所绑定到的对象的字符串表示形式。  
  
 若要解决此问题, 应用程序<xref:System.Windows.DataTemplate>将定义。 如上一部分的示例中所示, <xref:System.Windows.Controls.ContentControl>显式使用*detailsProductListingTemplate*<xref:System.Windows.DataTemplate>。 显示<xref:System.Windows.Controls.ListBox>集合中的*AuctionItem*对象<xref:System.Windows.DataTemplate>时, 控件隐式使用以下内容:  
  
 [!code-xaml[DataBindingLab#AuctionItemDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#auctionitemdatatemplate)]  
  
 使用这两个<xref:System.Windows.DataTemplate>, 生成的 UI 就是在[什么是数据绑定？](#what_is_data_binding)一节中显示的 UI。 从该屏幕截图中可以看到, 除了允许您将数据放置在控件中外, <xref:System.Windows.DataTemplate>还允许您为数据定义引人注目的视觉对象。 例如, 在<xref:System.Windows.DataTrigger>上述<xref:System.Windows.DataTemplate>示例中使用了, 这样, 带有*SpecialFeatures*值*突出*显示的*AuctionItem*将显示为橙色边框和星形。  
  
 有关数据模板的详细信息，请参阅[数据模板化概述](data-templating-overview.md)。  
  
<a name="data_validation"></a>   
## <a name="data-validation"></a>数据验证  
  
 接受用户输入的大多数应用程序都需要具有验证逻辑，以确保用户输入了预期信息。 可基于类型、范围、格式或特定于应用程序的其他要求执行验证检查。 本节讨论了数据验证在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中的工作原理。  
  
### <a name="associating-validation-rules-with-a-binding"></a>将验证规则与绑定关联  
 数据绑定模型允许您将与您<xref:System.Windows.Data.Binding>的对象相关联<xref:System.Windows.Data.Binding.ValidationRules%2A>。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 例如, 下面的<xref:System.Windows.Controls.TextBox>示例将绑定到名`StartPrice`为的属性, 并<xref:System.Windows.Data.Binding.ValidationRules%2A?displayProperty=nameWithType>将<xref:System.Windows.Controls.ExceptionValidationRule>对象添加到属性。  
  
 [!code-xaml[DataBindingLab#DefaultValidation](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#defaultvalidation)]  
  
 <xref:System.Windows.Controls.ValidationRule>对象检查属性的值是否有效。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]具有以下两种类型的内置<xref:System.Windows.Controls.ValidationRule>对象:  
  
- <xref:System.Windows.Controls.ExceptionValidationRule>检查在绑定源属性更新过程中引发的异常。 在以上示例中，`StartPrice` 为整数类型。 当用户输入的值无法转换为整数时，将引发异常，这会导致将绑定标记为无效。 用于显式设置<xref:System.Windows.Controls.ExceptionValidationRule>的替代语法是将<xref:System.Windows.Data.Binding>或<xref:System.Windows.Data.MultiBinding>对象的<xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>属性设置`true`为。  
  
- 对象检查由<xref:System.ComponentModel.IDataErrorInfo>实现接口的对象引发的错误。 <xref:System.Windows.Controls.DataErrorValidationRule> 有关使用此验证规则的示例, 请参阅<xref:System.Windows.Controls.DataErrorValidationRule>。 用于显式设置<xref:System.Windows.Controls.DataErrorValidationRule>的替代语法是将<xref:System.Windows.Data.Binding>或<xref:System.Windows.Data.MultiBinding>对象的<xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>属性设置`true`为。  
  
 你还可以通过从<xref:System.Windows.Controls.ValidationRule>类派生并<xref:System.Windows.Controls.ValidationRule.Validate%2A>实现方法来创建自己的验证规则。 下面的示例显示了 "[什么是数据绑定？](#what_is_data_binding) " 部分<xref:System.Windows.Controls.TextBox>中 "*添加产品列表*" 开始日期所使用的规则:  
  
 [!code-csharp[DataBindingLab#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/FutureDateRule.cs#2)]
 [!code-vb[DataBindingLab#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/FutureDateRule.vb#2)]  
  
 StartDateEntryForm<xref:System.Windows.Controls.TextBox>使用此*FutureDateRule*, 如以下示例中所示:  
  
 [!code-xaml[DataBindingLab#CustomValidation](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#customvalidation)]  
  
 请注意, 由于<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>值为<xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, 因此绑定引擎将在每次击键时更新源值, 这意味着它还会检查每个<xref:System.Windows.Data.Binding.ValidationRules%2A>击键的集合中的每个规则。 我们会在“验证过程”一节中对此深入讨论。  
  
<a name="invalidation_feedback"></a>   
### <a name="providing-visual-feedback"></a>提供视觉反馈  
 如果用户输入的值无效，你可能希望在应用程序 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 上提供一些有关错误的反馈。 提供此类反馈的一种方法是将<xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType>附加属性设置为自<xref:System.Windows.Controls.ControlTemplate>定义。 如上一节所示, *StartDateEntryForm* <xref:System.Windows.Controls.TextBox>使用<xref:System.Windows.Controls.Validation.ErrorTemplate%2A>称为*validationTemplate*。 以下示例显示了 *validationTemplate* 的定义：  
  
 [!code-xaml[DataBindingLab#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#1)]  
  
 <xref:System.Windows.Controls.AdornedElementPlaceholder>元素指定要装饰的控件的放置位置。  
  
 此外, 你还可以使用<xref:System.Windows.Controls.ToolTip>来显示错误消息。 *StartDateEntryForm*和*StartPriceEntryForm*<xref:System.Windows.Controls.TextBox>es 都使用 style *textStyleTextBox*, 这会创建一个<xref:System.Windows.Controls.ToolTip>显示错误消息的。 以下示例显示了 *textStyleTextBox* 的定义。 当绑定元素<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>的`true`属性上的一个或多个绑定出错时, 附加属性为。  
  
 [!code-xaml[DataBindingLab#14](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#14)]  
  
 如果存在验证<xref:System.Windows.Controls.Validation.ErrorTemplate%2A>错误<xref:System.Windows.Controls.ToolTip>, 则使用自定义和时, *StartDateEntryForm* <xref:System.Windows.Controls.TextBox>如下所示:  
  
 ![数据绑定验证错误](./media/databindingdemo-validation.PNG "DataBindingDemo_Validation")  
  
 如果你<xref:System.Windows.Data.Binding>具有关联的验证规则, 但你未<xref:System.Windows.Controls.Validation.ErrorTemplate%2A>在绑定控件上指定, 则将<xref:System.Windows.Controls.Validation.ErrorTemplate%2A>使用默认值来在发生验证错误时通知用户。 默认值<xref:System.Windows.Controls.Validation.ErrorTemplate%2A>是在装饰器层中定义红色边框的控件模板。 如果存在验证<xref:System.Windows.Controls.Validation.ErrorTemplate%2A>错误<xref:System.Windows.Controls.ToolTip>, 则默认[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]值为, *StartPriceEntryForm* <xref:System.Windows.Controls.TextBox>的如下所示:  
  
 ![数据绑定验证错误](./media/databindingdemo-validationdefault.PNG "DataBindingDemo_ValidationDefault")  
  
 有关如何提供逻辑以验证对话框中所有控件的示例，请参阅[对话框概述](../app-development/dialog-boxes-overview.md)中的“自定义对话框”一节。  
  
### <a name="validation-process"></a>验证过程  
 通常，在目标的值传输到绑定源属性时会进行验证。 此操作发生<xref:System.Windows.Data.BindingMode.TwoWay>在<xref:System.Windows.Data.BindingMode.OneWayToSource>和绑定上。 重申一下, 源更新的原因取决于<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>属性的值, 如[什么触发器源更新](#what_triggers_source_updates)部分所述。  
  
 下面描述了*验证*过程。 注意，只要在验证过程中发生验证错误或其他类型的错误，该过程就会中断。  
  
1. 绑定引擎检查是否存在<xref:System.Windows.Controls.ValidationRule> <xref:System.Windows.Controls.ValidationStep.RawProposedValue> <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> <xref:System.Windows.Controls.ValidationRule.Validate%2A> 为设置<xref:System.Windows.Controls.ValidationRule>为的自定义对象,在这种情况下,将在每个对象上调用方法,直到其中一个对象出现错误<xref:System.Windows.Data.Binding>或直到全部通过。  
  
2. 绑定引擎随后会调用转换器（如果存在）。  
  
3. 如果转换器成功, 绑定引擎会检查是否有定义的任何自<xref:System.Windows.Controls.ValidationRule>定义对象<xref:System.Windows.Data.Binding>( <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>将其设置<xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue>为), 在这种情况下, <xref:System.Windows.Controls.ValidationRule.Validate%2A>它<xref:System.Windows.Controls.ValidationRule>将对具有设置为<xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> , 直到其中一个错误发生, 或直到全部通过为止。 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>  
  
4. 绑定引擎设置源属性。  
  
5. 绑定<xref:System.Windows.Controls.ValidationRule>引擎检查是否有<xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> <xref:System.Windows.Controls.ValidationRule.Validate%2A> <xref:System.Windows.Controls.ValidationStep.UpdatedValue> 为设置为的<xref:System.Windows.Controls.ValidationRule>自定义对象,该对象的设置为,在这种情况下,它将在设置为的每个上调用方法。<xref:System.Windows.Data.Binding><xref:System.Windows.Controls.ValidationStep.UpdatedValue>直到其中一个出现错误, 或直到全部通过为止。 如果与某个绑定相关联, 并且其<xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>设置为默认值, <xref:System.Windows.Controls.ValidationStep.UpdatedValue> <xref:System.Windows.Controls.DataErrorValidationRule>则此时会检查。 <xref:System.Windows.Controls.DataErrorValidationRule> 这也是在检查设置为<xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> `true`的绑定时的点。  
  
6. 绑定<xref:System.Windows.Controls.ValidationRule>引擎检查是否有<xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> <xref:System.Windows.Controls.ValidationRule.Validate%2A> <xref:System.Windows.Controls.ValidationStep.CommittedValue> 为设置为的<xref:System.Windows.Controls.ValidationRule>自定义对象,该对象的设置为,在这种情况下,它将在设置为的每个上调用方法。<xref:System.Windows.Data.Binding><xref:System.Windows.Controls.ValidationStep.CommittedValue>直到其中一个出现错误, 或直到全部通过为止。  
  
 如果在此过程中的任何时间都未通过, 则绑定引擎将创建<xref:System.Windows.Controls.ValidationError>一个对象<xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType>并将其添加到绑定元素的集合中。 <xref:System.Windows.Controls.ValidationRule> 在绑定引擎运行任何给定<xref:System.Windows.Controls.ValidationRule>步骤的对象之前, 它会删除在<xref:System.Windows.Controls.ValidationError>该步骤中添加到<xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType>绑定元素的附加属性的任何。 例如, 如果设置为<xref:System.Windows.Controls.ValidationRule> <xref:System.Windows.Controls.ValidationStep.UpdatedValue> " <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>失败" 的, 则下一次执行验证过程时, 绑定<xref:System.Windows.Controls.ValidationRule>引擎会立即删除<xref:System.Windows.Controls.ValidationError> , 然后再调用已<xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>设置为<xref:System.Windows.Controls.ValidationStep.UpdatedValue>.  
  
 如果<xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType>不为空<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> , 则元素的附加属性设置为`true`。 此外, 如果<xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>将的<xref:System.Windows.Data.Binding>属性设置为`true`, 则绑定引擎将在元素上引发<xref:System.Windows.Controls.Validation.Error?displayProperty=nameWithType>附加事件。  
  
 另请注意, 在任一方向 (目标到源或源到目标) 的有效值传输都将<xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType>清除附加属性。  
  
 如果绑定具有与之关联<xref:System.Windows.Controls.ExceptionValidationRule>的, 或<xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>将属性设置为`true` , 并且在绑定引擎设置源时引发异常, 则绑定<xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>引擎会检查是否存在。 您可以选择使用<xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>回调提供自定义处理程序来处理异常。 如果未<xref:System.Windows.Controls.ValidationError> <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType>在上指定, 则绑定引擎将创建一个具有异常的, 并将其添加到绑定元素的集合中。 <xref:System.Windows.Data.Binding> <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>  
  
## <a name="debugging-mechanism"></a>调试机制  
 您可以对与绑定相关<xref:System.Diagnostics.PresentationTraceSources.TraceLevel%2A?displayProperty=nameWithType>的对象设置附加属性, 以接收有关特定绑定的状态的信息。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.DataErrorValidationRule>
- [WPF 版本 4.5 中的新增功能](../getting-started/whats-new.md)
- [绑定到 LINQ 查询结果](how-to-bind-to-the-results-of-a-linq-query.md)
- [数据绑定](../advanced/optimizing-performance-data-binding.md)
- [数据绑定演示](https://go.microsoft.com/fwlink/?LinkID=163703)
- [帮助主题](data-binding-how-to-topics.md)
- [绑定到 ADO.NET 数据源](how-to-bind-to-an-ado-net-data-source.md)
