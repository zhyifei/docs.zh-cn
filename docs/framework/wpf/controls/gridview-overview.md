---
title: GridView 概述
ms.date: 03/30/2017
helpviewer_keywords:
- GridView view mode [WPF]
- ListView controls [WPF], GridView view mode
- controls [WPF], ListView
ms.assetid: b2d02267-32b3-40ce-8e9f-06972d8749d9
ms.openlocfilehash: 776897d490b2748e240cf7b9a4ea21364284c4c4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557675"
---
# <a name="gridview-overview"></a>GridView 概述
<xref:System.Windows.Controls.GridView> 视图模式是一种视图模式的<xref:System.Windows.Controls.ListView>控件。 <xref:System.Windows.Controls.GridView>类和支持类让你和你的用户可以查看按钮通常用作交互式列标题的表中的项的集合。 本主题介绍<xref:System.Windows.Controls.GridView>类，并概述了其使用。  
  
  
  
<a name="DefiningaListViewthatusesGridViewView"></a>   
## <a name="what-is-a-gridview-view"></a>什么是 GridView 视图？  
 <xref:System.Windows.Controls.GridView>视图模式通过将数据字段绑定到列以及显示列标题以标识的字段显示的数据项列表。 默认值<xref:System.Windows.Controls.GridView>样式实现作为列标题的按钮。 通过使用列标题按钮，你可以实现重要的用户交互功能;例如，用户可以单击列标题以进行排序<xref:System.Windows.Controls.GridView>根据特定列的内容的数据。  
  
> [!NOTE]
>  按钮控件，<xref:System.Windows.Controls.GridView>列标题的使用派生自<xref:System.Windows.Controls.Primitives.ButtonBase>。  
  
 下图显示<xref:System.Windows.Controls.GridView>视图<xref:System.Windows.Controls.ListView>内容。  
  
 **ListView 内容的 GridView 视图**  
  
 ![带样式的 ListView](../../../../docs/framework/wpf/controls/media/styledlistview.PNG "StyledListView")  
  
 <xref:System.Windows.Controls.GridView> 列由表示<xref:System.Windows.Controls.GridViewColumn>对象，可以对其内容自动调整大小。 （可选） 你可以显式设置<xref:System.Windows.Controls.GridViewColumn>为特定的宽度。 可通过拖动列标题之间的手柄重设列的大小。 你可以还可以动态地添加、 删除、 替换和对列重新排序，因为此功能已内置于<xref:System.Windows.Controls.GridView>。 但是，<xref:System.Windows.Controls.GridView>无法直接更新它显示的数据。  
  
 下面的示例演示如何定义<xref:System.Windows.Controls.GridView>显示雇员数据。 在此示例中，<xref:System.Windows.Controls.ListView>定义`EmployeeInfoDataSource`作为<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>。 属性定义<xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>绑定<xref:System.Windows.Controls.GridViewColumn>内容到`EmployeeInfoDataSource`数据类别。  
  
 [!code-xaml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 下图显示了上一示例创建的表格。  
  
 **显示 ItemsSource 中的数据的 GridView**  
  
 ![具有 GridView 输出的 ListView](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")  
  
<a name="GridViewLayoutandStyle"></a>   
## <a name="gridview-layout-and-style"></a>GridView 布局和样式  
 列单元格和列标题的<xref:System.Windows.Controls.GridViewColumn>具有相同的宽度。 默认情况下，每一列都根据其内容来调整宽度大小。 也可以选择将列设置为固定宽度。  
  
 相关的数据内容显示在水平行中。 例如，在上图中，每个员工的姓氏、名字和 ID 号显示为一组，因为它们显示在一个水平行中。  
  
<a name="DefiningandStylingColumnsinaGridView"></a>   
### <a name="defining-and-styling-columns-in-a-gridview"></a>在 GridView 中定义列并设置其样式  
 定义要在中显示的数据字段时<xref:System.Windows.Controls.GridViewColumn>，使用<xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>， <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>，或<xref:System.Windows.Controls.GridViewColumn.CellTemplateSelector%2A>属性。 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>属性优先于在模板属性之一。  
  
 若要指定的列中的内容的对齐方式<xref:System.Windows.Controls.GridView>，定义<xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>。 不要使用<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>和<xref:System.Windows.Controls.Control.VerticalContentAlignment%2A>属性<xref:System.Windows.Controls.ListView>通过使用显示的内容<xref:System.Windows.Controls.GridView>。  
  
 若要指定列标题的模板和样式属性，使用<xref:System.Windows.Controls.GridView>， <xref:System.Windows.Controls.GridViewColumn>，和<xref:System.Windows.Controls.GridViewColumnHeader>类。 有关详细信息，请参阅 [GridView 列标题的样式和模板概述](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md)。  
  
<a name="AddingVisualElementstoaGridViewView"></a>   
### <a name="adding-visual-elements-to-a-gridview"></a>将可视元素添加到 GridView  
 若要添加视觉元素，如<xref:System.Windows.Controls.CheckBox>和<xref:System.Windows.Controls.Button>控件，为<xref:System.Windows.Controls.GridView>视图模式中，使用模板或样式。  
  
 如果您显式定义为数据项的可视元素，它可以只出现一次在<xref:System.Windows.Controls.GridView>。 之所以存在此限制，是因为元素只能有一个父级，因此，只能在可视化树中出现一次。  
  
<a name="StylingRowsinaGridViewView"></a>   
### <a name="styling-rows-in-a-gridview"></a>设置 GridView 中的行的样式  
 使用<xref:System.Windows.Controls.GridViewRowPresenter>和<xref:System.Windows.Controls.GridViewHeaderRowPresenter>类进行格式化和显示的行<xref:System.Windows.Controls.GridView>。 有关如何的示例样式中的行<xref:System.Windows.Controls.GridView>查看模式，请参阅[GridView 在 ListView，实现中的样式行](../../../../docs/framework/wpf/controls/how-to-style-a-row-in-a-listview-that-implements-a-gridview.md)。  
  
<a name="AlignmentIssuesWhenUsingItemContainerStyle"></a>   
### <a name="alignment-issues-when-you-use-itemcontainerstyle"></a>使用 ItemContainerStyle 时的对齐问题  
 为了防止列标题和单元格之间的对齐方式问题，未设置的属性或指定的模板中的项的宽度有影响， <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>。 例如，未设置<xref:System.Windows.FrameworkElement.Margin%2A>属性或指定<xref:System.Windows.Controls.ControlTemplate>，它将<xref:System.Windows.Controls.CheckBox>到<xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>上定义<xref:System.Windows.Controls.ListView>控件。 相反，指定的属性和影响直接在定义的类上的列宽度的模板<xref:System.Windows.Controls.GridView>视图模式。  
  
 例如，若要添加<xref:System.Windows.Controls.CheckBox>到中的行<xref:System.Windows.Controls.GridView>视图模式中，添加<xref:System.Windows.Controls.CheckBox>到<xref:System.Windows.DataTemplate>，然后设置<xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>属性， <xref:System.Windows.DataTemplate>。  
  
<a name="InteractingwithaGridViewControl"></a>   
## <a name="user-interactions-with-a-gridview"></a>与 GridView 的用户交互  
 当你使用<xref:System.Windows.Controls.GridView>中你的应用程序，用户可以交互使用和修改的格式<xref:System.Windows.Controls.GridView>。 例如，用户可以对列重新排序、重设列的大小、选择表中的项以及滚动查看内容。 还可定义当用户单击列标题按钮时响应的事件处理程序。 事件处理程序可以执行操作，如对显示在数据进行排序<xref:System.Windows.Controls.GridView>根据列的内容。  
  
 以下列表详细的使用的功能介绍了<xref:System.Windows.Controls.GridView>用于用户交互：  
  
-   **使用拖放方法对列重新排序。**  
  
     用户可以对中的列重新排序<xref:System.Windows.Controls.GridView>通过在列标题上时按鼠标左键，然后将该列拖到新位置。 当用户拖动列标题时，将显示标题的浮动版本以及显示列的插入位置的黑色实线。  
  
     如果你想要修改的标头的浮点版本的默认样式，指定<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.GridViewColumnHeader>类型，触发时<xref:System.Windows.Controls.GridViewColumnHeader.Role%2A>属性设置为<xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>。 有关详细信息，请参阅[为拖动的 GridView 列标题创建样式](../../../../docs/framework/wpf/controls/how-to-create-a-style-for-a-dragged-gridview-column-header.md)。  
  
-   **根据列的内容重设其大小。**  
  
     用户可双击列标题右侧的手柄来根据列的内容重设其大小。  
  
    > [!NOTE]
    >  你可以设置<xref:System.Windows.Controls.GridViewColumn.Width%2A>属性`Double.NaN`生成相同的效果。  
  
-   **选择行项目。**  
  
     用户可以选择中的一个或多个项<xref:System.Windows.Controls.GridView>。  
  
     如果你想要更改<xref:System.Windows.Style>的选定的项目，请参阅[使用触发器来样式 ListView 中的选定项](../../../../docs/framework/wpf/controls/how-to-use-triggers-to-style-selected-items-in-a-listview.md)。  
  
-   **滚动查看最初未显示在屏幕上的内容。**  
  
     如果的大小<xref:System.Windows.Controls.GridView>是不足够大以显示所有项，用户可以滚动水平或垂直通过使用滚动条，这由<xref:System.Windows.Controls.ScrollViewer>控件。 A<xref:System.Windows.Controls.Primitives.ScrollBar>按特定方向可见的所有内容是否隐藏。 列标题不会随着垂直滚动条滚动，但可水平滚动。  
  
-   **通过单击列标题按钮与列交互。**  
  
     如果提供了排序算法，则当用户单击列标题按钮时，可以对列中显示的数据进行排序。  
  
     你可以处理<xref:System.Windows.Controls.Primitives.ButtonBase.Click>以便提供功能，例如，排序算法的列标题按钮的事件。 若要处理<xref:System.Windows.Controls.Primitives.ButtonBase.Click>单个列标题，为事件设置事件处理程序<xref:System.Windows.Controls.GridViewColumnHeader>。 若要设置的事件处理程序处理<xref:System.Windows.Controls.Primitives.ButtonBase.Click>对于所有列标题，事件上设置处理程序<xref:System.Windows.Controls.ListView>控件。  
  
<a name="Obtaining_Other_Custom_Views"></a>   
## <a name="obtaining-other-custom-views"></a>获取其他自定义视图  
 <xref:System.Windows.Controls.GridView>类，该类派生自<xref:System.Windows.Controls.ViewBase>抽象类，只是其中一个的可能的视图模式的<xref:System.Windows.Controls.ListView>类。 你可以创建的其他自定义视图<xref:System.Windows.Controls.ListView>由派生自<xref:System.Windows.Controls.ViewBase>类。 有关自定义视图模式的示例，请参阅[为 ListView 创建自定义视图模式](../../../../docs/framework/wpf/controls/how-to-create-a-custom-view-mode-for-a-listview.md)。  
  
<a name="GridViewSupportingClasses"></a>   
## <a name="gridview-supporting-classes"></a>GridView 支持类  
 下面的类支持<xref:System.Windows.Controls.GridView>视图模式。  
  
-   <xref:System.Windows.Controls.GridViewColumn>  
  
-   <xref:System.Windows.Controls.GridViewColumnHeader>  
  
-   <xref:System.Windows.Controls.GridViewRowPresenter>  
  
-   <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
  
-   <xref:System.Windows.Controls.GridViewColumnCollection>  
  
-   <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.ListViewItem>  
 <xref:System.Windows.Controls.GridViewColumn>  
 <xref:System.Windows.Controls.GridViewColumnHeader>  
 <xref:System.Windows.Controls.GridViewRowPresenter>  
 <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
 <xref:System.Windows.Controls.ViewBase>  
 [ListView 概述](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [在标题获得单击时对 GridView 列进行排序](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)  
 [帮助主题](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)
