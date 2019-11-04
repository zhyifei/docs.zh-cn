---
title: 如何：在 DataGrid 控件中对数据进行分组、排序和筛选
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], sort
- DataGrid [WPF], group
- DataGrid [WPF], filter
ms.assetid: 03345e85-89e3-4aec-9ed0-3b80759df770
ms.openlocfilehash: 2632566b5b55ae641d2750e903bf94cdc681f8f8
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460236"
---
# <a name="how-to-group-sort-and-filter-data-in-the-datagrid-control"></a>如何：在 DataGrid 控件中对数据进行分组、排序和筛选

通常情况下，通过对数据进行分组、排序和筛选来以不同方式查看 <xref:System.Windows.Controls.DataGrid> 中的数据是非常有用的。 若要在 <xref:System.Windows.Controls.DataGrid>中对数据进行分组、排序和筛选，请将其绑定到支持这些函数的 <xref:System.Windows.Data.CollectionView>。 然后，可以使用 <xref:System.Windows.Data.CollectionView> 中的数据，而不会影响基础数据源数据。 集合视图中的更改会反映在 <xref:System.Windows.Controls.DataGrid> 用户界面（UI）中。

<xref:System.Windows.Data.CollectionView> 类为实现 <xref:System.Collections.IEnumerable> 接口的数据源提供了分组和排序功能。 通过 <xref:System.Windows.Data.CollectionViewSource> 类，您可以从 XAML 设置 <xref:System.Windows.Data.CollectionView> 的属性。

在此示例中，`Task` 对象的集合绑定到 <xref:System.Windows.Data.CollectionViewSource>。 <xref:System.Windows.Data.CollectionViewSource> 用作 <xref:System.Windows.Controls.DataGrid>的 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>。 分组、排序和筛选是在 <xref:System.Windows.Data.CollectionViewSource> 上执行的，并显示在 <xref:System.Windows.Controls.DataGrid> UI 中。

![DataGrid 中的分组数据](././media/wpf-datagridgroups.png "WPF_DataGridGroups")DataGrid 中的分组数据

## <a name="using-a-collectionviewsource-as-an-itemssource"></a>使用 CollectionViewSource 作为 System.windows.controls.itemscontrol.itemssource

若要对 <xref:System.Windows.Controls.DataGrid> 控件中的数据进行分组、排序和筛选，请将 <xref:System.Windows.Controls.DataGrid> 绑定到支持这些函数的 <xref:System.Windows.Data.CollectionView>。 在此示例中，<xref:System.Windows.Controls.DataGrid> 绑定到 <xref:System.Windows.Data.CollectionViewSource>，该为 `Task` 对象的 <xref:System.Collections.Generic.List%601> 提供这些函数。

### <a name="to-bind-a-datagrid-to-a-collectionviewsource"></a>将 DataGrid 绑定到 CollectionViewSource

1. 创建实现 <xref:System.Collections.IEnumerable> 接口的数据集合。

    如果使用 <xref:System.Collections.Generic.List%601> 创建集合，则应创建一个继承自 <xref:System.Collections.Generic.List%601> 的新类，而不是实例化 <xref:System.Collections.Generic.List%601>的实例。 这使您可以将数据绑定到 XAML 中的集合。

    > [!NOTE]
    > 集合中的对象必须实现 <xref:System.ComponentModel.INotifyPropertyChanged> 更改的接口和 <xref:System.ComponentModel.IEditableObject> 接口，以便 <xref:System.Windows.Controls.DataGrid> 正确地响应属性更改和编辑。 有关详细信息，请参阅[实现属性更改通知](../data/how-to-implement-property-change-notification.md)。

    [!code-csharp[DataGrid_GroupSortFilter#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#101)]
    [!code-vb[DataGrid_GroupSortFilter#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#101)]

2. 在 XAML 中，创建集合类的实例并设置[X：Key 指令](../../xaml-services/x-key-directive.md)。

3. 在 XAML 中，创建 <xref:System.Windows.Data.CollectionViewSource> 类的实例，设置[X：Key 指令](../../xaml-services/x-key-directive.md)，并将集合类的实例设置为 <xref:System.Windows.Data.CollectionViewSource.Source%2A>。

    [!code-xaml[DataGrid_GroupSortFilter#201](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml#201)]

4. 创建 <xref:System.Windows.Controls.DataGrid> 类的实例，并将 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 属性设置为 <xref:System.Windows.Data.CollectionViewSource>。

    [!code-xaml[DataGrid_GroupSortFilter#002](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#002)]

5. 若要从代码访问 <xref:System.Windows.Data.CollectionViewSource>，请使用 <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> 方法获取对 <xref:System.Windows.Data.CollectionViewSource>的引用。

    [!code-csharp[DataGrid_GroupSortFilter#102](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#102)]
    [!code-vb[DataGrid_GroupSortFilter#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#102)]

## <a name="grouping-items-in-a-datagrid"></a>对 DataGrid 中的项进行分组

若要指定如何在 <xref:System.Windows.Controls.DataGrid>中对项进行分组，请使用 <xref:System.Windows.Data.PropertyGroupDescription> 类型对源视图中的项进行分组。

### <a name="to-group-items-in-a-datagrid-using-xaml"></a>使用 XAML 对 DataGrid 中的项进行分组

1. 创建指定按其进行分组的属性的 <xref:System.Windows.Data.PropertyGroupDescription>。 可以在 XAML 或代码中指定属性。

   1. 在 XAML 中，将 <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> 设置为要按其进行分组的属性的名称。

   2. 在 "代码" 中，将 "分组依据" 属性的名称传递到构造函数。

2. 将 <xref:System.Windows.Data.PropertyGroupDescription> 添加到 <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> 集合。

3. 向 <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> 集合添加 <xref:System.Windows.Data.PropertyGroupDescription> 的其他实例，以便添加更多级别的分组。

    [!code-xaml[DataGrid_GroupSortFilter#012](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#012)]
    [!code-csharp[DataGrid_GroupSortFilter#112](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#112)]
    [!code-vb[DataGrid_GroupSortFilter#112](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#112)]

4. 若要删除组，请从 <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> 集合中删除 <xref:System.Windows.Data.PropertyGroupDescription>。

5. 若要删除所有组，请调用 <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> 集合的 <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> 方法。

    [!code-csharp[DataGrid_GroupSortFilter#114](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#114)]
    [!code-vb[DataGrid_GroupSortFilter#114](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#114)]

在 <xref:System.Windows.Controls.DataGrid>中对项进行分组时，可以定义一个指定每个组的外观的 <xref:System.Windows.Controls.GroupStyle>。 可以通过将 <xref:System.Windows.Controls.GroupStyle> 添加到 DataGrid 的 <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> 集合来应用该。 如果有多个级别的分组，则可以对每个组级别应用不同的样式。 样式按其定义顺序进行应用。 例如，如果您定义两种样式，则第一个样式将应用于顶层行组。 第二个样式将应用于第二级和下的所有行组。 <xref:System.Windows.Controls.GroupStyle> 的 <xref:System.Windows.FrameworkElement.DataContext%2A> 是组所表示的 <xref:System.Windows.Data.CollectionViewGroup>。

### <a name="to-change-the-appearance-of-row-group-headers"></a>更改行组标题的外观

1. 创建定义行组外观的 <xref:System.Windows.Controls.GroupStyle>。

2. 将 <xref:System.Windows.Controls.GroupStyle> 放置在 `<DataGrid.GroupStyle>` 标记中。

    [!code-xaml[DataGrid_GroupSortFilter#003](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#003)]

## <a name="sorting-items-in-a-datagrid"></a>对 DataGrid 中的项进行排序

若要指定如何在 <xref:System.Windows.Controls.DataGrid>中对项进行排序，请使用 <xref:System.ComponentModel.SortDescription> 类型对源视图中的项进行排序。

### <a name="to-sort-items-in-a-datagrid"></a>对 DataGrid 中的项进行排序

1. 创建一个指定要按其排序的属性的 <xref:System.ComponentModel.SortDescription>。 可以在 XAML 或代码中指定属性。

    1. 在 XAML 中，将 <xref:System.ComponentModel.SortDescription.PropertyName%2A> 设置为要作为排序依据的属性的名称。

    2. 在代码中，传递要排序的属性的名称，并将 <xref:System.ComponentModel.ListSortDirection> 传递到构造函数。

2. 将 <xref:System.ComponentModel.SortDescription> 添加到 <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> 集合。

3. 向 <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> 集合添加 <xref:System.ComponentModel.SortDescription> 的其他实例，以按其他属性进行排序。

    [!code-xaml[DataGrid_GroupSortFilter#011](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#011)]
    [!code-csharp[DataGrid_GroupSortFilter#211](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml.cs#211)]
    [!code-vb[DataGrid_GroupSortFilter#211](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#211)]

## <a name="filtering-items-in-a-datagrid"></a>筛选 DataGrid 中的项

若要使用 <xref:System.Windows.Data.CollectionViewSource>筛选 <xref:System.Windows.Controls.DataGrid> 中的项，请在 <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> 事件的处理程序中提供筛选逻辑。

### <a name="to-filter-items-in-a-datagrid"></a>筛选 DataGrid 中的项

1. 为 <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> 事件添加处理程序。

2. 在 <xref:System.Windows.Data.CollectionViewSource.Filter> 事件处理程序中，定义筛选逻辑。

    此筛选器将在每次刷新视图时应用。

    [!code-xaml[DataGrid_GroupSortFilter#013](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#013)]
    [!code-csharp[DataGrid_GroupSortFilter#113](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#113)]
    [!code-vb[DataGrid_GroupSortFilter#113](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#113)]

或者，您可以通过创建一个提供筛选逻辑并将 <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> 属性设置为应用筛选器的方法，来筛选 <xref:System.Windows.Controls.DataGrid> 中的项。 若要查看此方法的示例，请参阅[在视图中筛选数据](../data/how-to-filter-data-in-a-view.md)。

## <a name="example"></a>示例

下面的示例演示如何对 <xref:System.Windows.Data.CollectionViewSource> 中的 `Task` 数据进行分组、排序和筛选，以及如何在 <xref:System.Windows.Controls.DataGrid>中显示分组、排序和筛选的 `Task` 数据。 <xref:System.Windows.Data.CollectionViewSource> 用作 <xref:System.Windows.Controls.DataGrid>的 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>。 分组、排序和筛选是在 <xref:System.Windows.Data.CollectionViewSource> 上执行的，并显示在 <xref:System.Windows.Controls.DataGrid> UI 中。

若要测试此示例，需调整 DGGroupSortFilterExample 名称，使其与项目名称匹配。 如果使用 Visual Basic，则需要将 <xref:System.Windows.Window> 的类名称更改为以下项。

`<Window x:Class="MainWindow"`

[!code-xaml[DataGrid_GroupSortFilter#000](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#000)]
[!code-csharp[DataGrid_GroupSortFilter#100](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#100)]
[!code-vb[DataGrid_GroupSortFilter#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#100)]

## <a name="see-also"></a>请参阅

- [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)
- [创建和绑定到 ObservableCollection](../data/how-to-create-and-bind-to-an-observablecollection.md)
- [在视图中筛选数据](../data/how-to-filter-data-in-a-view.md)
- [在视图中对数据进行排序](../data/how-to-sort-data-in-a-view.md)
- [在 XAML 中使用视图对数据进行排序和分组](../data/how-to-sort-and-group-data-using-a-view-in-xaml.md)
