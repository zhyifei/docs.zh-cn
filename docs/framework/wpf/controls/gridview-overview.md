---
title: GridView 概述
ms.date: 03/30/2017
helpviewer_keywords:
- GridView view mode [WPF]
- ListView controls [WPF], GridView view mode
- controls [WPF], ListView
ms.assetid: b2d02267-32b3-40ce-8e9f-06972d8749d9
ms.openlocfilehash: 98bc7985172cabeab19469af4b4c21e13a6bce73
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181889"
---
# <a name="gridview-overview"></a>GridView 概述
<xref:System.Windows.Controls.GridView>视图模式是控件的视图模式之一<xref:System.Windows.Controls.ListView>。 类<xref:System.Windows.Controls.GridView>及其支持类使您和您的用户能够在通常使用按钮作为交互式列标题的表中查看项集合。 本主题介绍该<xref:System.Windows.Controls.GridView>类并概述其用途。  

<a name="DefiningaListViewthatusesGridViewView"></a>
## <a name="what-is-a-gridview-view"></a>什么是 GridView 视图？  
 视图<xref:System.Windows.Controls.GridView>模式通过将数据字段绑定到列以及显示列标题来标识该字段来显示数据项的列表。 默认<xref:System.Windows.Controls.GridView>样式将按钮作为列标题实现。 通过使用按钮进行列标题，可以实现重要的用户交互功能;例如，用户可以单击列标题根据特定列的内容对<xref:System.Windows.Controls.GridView>数据进行排序。  
  
> [!NOTE]
> <xref:System.Windows.Controls.GridView>用于列标题的按钮控件派生自<xref:System.Windows.Controls.Primitives.ButtonBase>。  
  
 下图显示了<xref:System.Windows.Controls.GridView>内容视图<xref:System.Windows.Controls.ListView>。  

 ![显示列表视图内容的 GridView 视图的屏幕截图。](./media/gridview-overview/styled-listview-content.png)  
  
 <xref:System.Windows.Controls.GridView>列由<xref:System.Windows.Controls.GridViewColumn>对象表示，对象可以自动调整其内容的大小。 或者，您可以显式将 设置为<xref:System.Windows.Controls.GridViewColumn>特定宽度。 可通过拖动列标题之间的手柄重设列的大小。 您还可以动态添加、删除、替换和重新排序列，因为此功能内置于<xref:System.Windows.Controls.GridView>中。 但是，<xref:System.Windows.Controls.GridView>无法直接更新它显示的数据。  
  
 下面的示例演示如何定义显示员工数据的<xref:System.Windows.Controls.GridView>。 在此示例中，<xref:System.Windows.Controls.ListView>将`EmployeeInfoDataSource`定义为 。 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>将内容绑定<xref:System.Windows.Controls.GridViewColumn>到`EmployeeInfoDataSource`数据类别的属性定义。  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 下图显示了上一示例创建的表格。 GridView 控件显示来自项目源对象的数据：

 ![显示带有 GridView 输出的 ListView 的屏幕截图。](./media/gridview-overview/listview-gridview-output.jpg)  
  
<a name="GridViewLayoutandStyle"></a>
## <a name="gridview-layout-and-style"></a>GridView 布局和样式  
 的列单元格和的列标题<xref:System.Windows.Controls.GridViewColumn>具有相同的宽度。 默认情况下，每一列都根据其内容来调整宽度大小。 也可以选择将列设置为固定宽度。  
  
 相关的数据内容显示在水平行中。 例如，在上图中，每个员工的姓氏、名字和 ID 号显示为一组，因为它们显示在一个水平行中。  
  
<a name="DefiningandStylingColumnsinaGridView"></a>
### <a name="defining-and-styling-columns-in-a-gridview"></a>在 GridView 中定义列并设置其样式  
 <xref:System.Windows.Controls.GridViewColumn>定义要在 中显示的数据字段时，请使用<xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>。 <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> <xref:System.Windows.Controls.GridViewColumn.CellTemplateSelector%2A> 属性<xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>优先于任一模板属性。  
  
 要指定 内容在 的列中的对齐方式<xref:System.Windows.Controls.GridView>，请定义<xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>。 不要对使用<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>显示<xref:System.Windows.Controls.Control.VerticalContentAlignment%2A><xref:System.Windows.Controls.ListView>的内容使用 和 属性<xref:System.Windows.Controls.GridView>。  
  
 要为列标题指定模板和样式属性，请使用<xref:System.Windows.Controls.GridView>和<xref:System.Windows.Controls.GridViewColumn><xref:System.Windows.Controls.GridViewColumnHeader>类。 有关详细信息，请参阅 [GridView 列标题的样式和模板概述](gridview-column-header-styles-and-templates-overview.md)。  
  
<a name="AddingVisualElementstoaGridViewView"></a>
### <a name="adding-visual-elements-to-a-gridview"></a>将可视元素添加到 GridView  
 要将可视元素（如<xref:System.Windows.Controls.CheckBox>和<xref:System.Windows.Controls.Button>控件）添加到<xref:System.Windows.Controls.GridView>视图模式，请使用模板或样式。  
  
 如果显式将可视元素定义为数据项，则它只能在 中<xref:System.Windows.Controls.GridView>出现一次。 之所以存在此限制，是因为元素只能有一个父级，因此，只能在可视化树中出现一次。  
  
<a name="StylingRowsinaGridViewView"></a>
### <a name="styling-rows-in-a-gridview"></a>设置 GridView 中的行的样式  
 使用<xref:System.Windows.Controls.GridViewRowPresenter>和<xref:System.Windows.Controls.GridViewHeaderRowPresenter>类格式化和显示 行<xref:System.Windows.Controls.GridView>。 有关如何在<xref:System.Windows.Controls.GridView>视图模式下设置行样式的示例，请参阅[实现 GridView 的 ListView 中对行的样式](how-to-style-a-row-in-a-listview-that-implements-a-gridview.md)。  
  
<a name="AlignmentIssuesWhenUsingItemContainerStyle"></a>
### <a name="alignment-issues-when-you-use-itemcontainerstyle"></a>使用 ItemContainerStyle 时的对齐问题  
 为了防止列标题和单元格之间的对齐问题，请不要设置属性或指定影响 中项宽度的模板<xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>。 例如，不要设置<xref:System.Windows.FrameworkElement.Margin%2A>属性或指定<xref:System.Windows.Controls.ControlTemplate>将 添加到<xref:System.Windows.Controls.CheckBox>控件上<xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A><xref:System.Windows.Controls.ListView>定义的 的 。 相反，请指定直接影响列宽度的属性和模板，这些属性和模板直接影响定义视图<xref:System.Windows.Controls.GridView>模式的类。  
  
 例如，要<xref:System.Windows.Controls.CheckBox>向<xref:System.Windows.Controls.GridView>视图模式下的行添加 ， 将 添加到<xref:System.Windows.Controls.CheckBox>，<xref:System.Windows.DataTemplate>然后将<xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>属性设置为 该<xref:System.Windows.DataTemplate>。  
  
<a name="InteractingwithaGridViewControl"></a>
## <a name="user-interactions-with-a-gridview"></a>与 GridView 的用户交互  
 在应用程序中使用<xref:System.Windows.Controls.GridView>时，用户可以与 进行交互并修改 的<xref:System.Windows.Controls.GridView>格式。 例如，用户可以对列重新排序、重设列的大小、选择表中的项以及滚动查看内容。 还可定义当用户单击列标题按钮时响应的事件处理程序。 事件处理程序可以执行操作，例如<xref:System.Windows.Controls.GridView>根据列的内容对 中显示的数据进行排序。  
  
 下面的列表更详细地讨论了用于<xref:System.Windows.Controls.GridView>用户交互的功能：  
  
- **使用拖放方法对列重新排序。**  
  
     用户可以在列标题上按鼠标<xref:System.Windows.Controls.GridView>左键重新排序，然后将该列拖动到新位置。 当用户拖动列标题时，将显示标题的浮动版本以及显示列的插入位置的黑色实线。  
  
     如果要修改标头的浮动版本的默认样式，<xref:System.Windows.Controls.ControlTemplate>请为在<xref:System.Windows.Controls.GridViewColumnHeader><xref:System.Windows.Controls.GridViewColumnHeader.Role%2A>属性设置为<xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>时触发的类型指定 。 有关详细信息，请参阅[为拖动的 GridView 列标题创建样式](how-to-create-a-style-for-a-dragged-gridview-column-header.md)。  
  
- **根据列的内容重设其大小。**  
  
     用户可双击列标题右侧的手柄来根据列的内容重设其大小。  
  
    > [!NOTE]
    > 您可以将 该<xref:System.Windows.Controls.GridViewColumn.Width%2A>属性设置为`Double.NaN`以生成相同的效果。  
  
- **选择行项目。**  
  
     用户可以在 中选择 一<xref:System.Windows.Controls.GridView>个或多个项目。  
  
     如果要更改<xref:System.Windows.Style>所选项目的 ，请参阅[在 ListView 中使用触发器来设置所选项目。](how-to-use-triggers-to-style-selected-items-in-a-listview.md)  
  
- **滚动查看最初未显示在屏幕上的内容。**  
  
     如果 的大小<xref:System.Windows.Controls.GridView>不足以显示所有项目，则用户可以使用<xref:System.Windows.Controls.ScrollViewer>控件提供的滚动条水平或垂直滚动。 如果<xref:System.Windows.Controls.Primitives.ScrollBar>所有内容在特定方向上可见，则隐藏 。 列标题不会随着垂直滚动条滚动，但可水平滚动。  
  
- **通过单击列标题按钮与列交互。**  
  
     如果提供了排序算法，则当用户单击列标题按钮时，可以对列中显示的数据进行排序。  
  
     您可以处理列标题<xref:System.Windows.Controls.Primitives.ButtonBase.Click>按钮的事件，以便提供排序算法等功能。 要处理单个<xref:System.Windows.Controls.Primitives.ButtonBase.Click>列标头的事件，在 上设置事件处理程序<xref:System.Windows.Controls.GridViewColumnHeader>。 要设置处理所有列标题<xref:System.Windows.Controls.Primitives.ButtonBase.Click>的事件处理程序，在<xref:System.Windows.Controls.ListView>控件上设置处理程序。  
  
<a name="Obtaining_Other_Custom_Views"></a>
## <a name="obtaining-other-custom-views"></a>获取其他自定义视图  
 从<xref:System.Windows.Controls.GridView>抽象类派生的<xref:System.Windows.Controls.ViewBase>类只是<xref:System.Windows.Controls.ListView>类的可能视图模式之一。 可以通过从<xref:System.Windows.Controls.ListView><xref:System.Windows.Controls.ViewBase>类派生来创建其他自定义视图。 有关自定义视图模式的示例，请参阅[为 ListView 创建自定义视图模式](how-to-create-a-custom-view-mode-for-a-listview.md)。  
  
<a name="GridViewSupportingClasses"></a>
## <a name="gridview-supporting-classes"></a>GridView 支持类  
 以下类支持<xref:System.Windows.Controls.GridView>视图模式。  
  
- <xref:System.Windows.Controls.GridViewColumn>  
  
- <xref:System.Windows.Controls.GridViewColumnHeader>  
  
- <xref:System.Windows.Controls.GridViewRowPresenter>  
  
- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
  
- <xref:System.Windows.Controls.GridViewColumnCollection>  
  
- <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.ListViewItem>
- <xref:System.Windows.Controls.GridViewColumn>
- <xref:System.Windows.Controls.GridViewColumnHeader>
- <xref:System.Windows.Controls.GridViewRowPresenter>
- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
- <xref:System.Windows.Controls.ViewBase>
- [ListView 概述](listview-overview.md)
- [在标题获得单击时对 GridView 列进行排序](how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [如何使用主题](listview-how-to-topics.md)
