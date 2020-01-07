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
ms.openlocfilehash: 622b64fd7738b02cd72131e7e9fe91c04314b1d0
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559469"
---
# <a name="how-to-group-sort-and-filter-data-in-the-datagrid-control"></a><span data-ttu-id="f6d3a-102">如何：在 DataGrid 控件中对数据进行分组、排序和筛选</span><span class="sxs-lookup"><span data-stu-id="f6d3a-102">How to: Group, sort, and filter data in the DataGrid control</span></span>

<span data-ttu-id="f6d3a-103">通常情况下，通过对数据进行分组、排序和筛选来以不同方式查看 <xref:System.Windows.Controls.DataGrid> 中的数据是非常有用的。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-103">It is often useful to view data in a <xref:System.Windows.Controls.DataGrid> in different ways by grouping, sorting, and filtering the data.</span></span> <span data-ttu-id="f6d3a-104">若要在 <xref:System.Windows.Controls.DataGrid>中对数据进行分组、排序和筛选，请将其绑定到支持这些函数的 <xref:System.Windows.Data.CollectionView>。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-104">To group, sort, and filter the data in a <xref:System.Windows.Controls.DataGrid>, you bind it to a <xref:System.Windows.Data.CollectionView> that supports these functions.</span></span> <span data-ttu-id="f6d3a-105">然后，可以使用 <xref:System.Windows.Data.CollectionView> 中的数据，而不会影响基础数据源数据。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-105">You can then work with the data in the <xref:System.Windows.Data.CollectionView> without affecting the underlying source data.</span></span> <span data-ttu-id="f6d3a-106">集合视图中的更改会反映在 <xref:System.Windows.Controls.DataGrid> 用户界面（UI）中。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-106">The changes in the collection view are reflected in the <xref:System.Windows.Controls.DataGrid> user interface (UI).</span></span>

<span data-ttu-id="f6d3a-107"><xref:System.Windows.Data.CollectionView> 类为实现 <xref:System.Collections.IEnumerable> 接口的数据源提供了分组和排序功能。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-107">The <xref:System.Windows.Data.CollectionView> class provides grouping and sorting functionality for a data source that implements the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="f6d3a-108">通过 <xref:System.Windows.Data.CollectionViewSource> 类，您可以从 XAML 设置 <xref:System.Windows.Data.CollectionView> 的属性。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-108">The <xref:System.Windows.Data.CollectionViewSource> class enables you to set the properties of a <xref:System.Windows.Data.CollectionView> from XAML.</span></span>

<span data-ttu-id="f6d3a-109">在此示例中，`Task` 对象的集合绑定到 <xref:System.Windows.Data.CollectionViewSource>。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-109">In this example, a collection of `Task` objects is bound to a <xref:System.Windows.Data.CollectionViewSource>.</span></span> <span data-ttu-id="f6d3a-110"><xref:System.Windows.Data.CollectionViewSource> 用作 <xref:System.Windows.Controls.DataGrid>的 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-110">The <xref:System.Windows.Data.CollectionViewSource> is used as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="f6d3a-111">分组、排序和筛选是在 <xref:System.Windows.Data.CollectionViewSource> 上执行的，并显示在 <xref:System.Windows.Controls.DataGrid> UI 中。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-111">Grouping, sorting, and filtering are performed on the <xref:System.Windows.Data.CollectionViewSource> and are displayed in the <xref:System.Windows.Controls.DataGrid> UI.</span></span>

<span data-ttu-id="f6d3a-112">![DataGrid 中的分组数据](././media/wpf-datagridgroups.png "WPF_DataGridGroups")DataGrid 中的分组数据</span><span class="sxs-lookup"><span data-stu-id="f6d3a-112">![Grouped data in a DataGrid](././media/wpf-datagridgroups.png "WPF_DataGridGroups") Grouped data in a DataGrid</span></span>

## <a name="using-a-collectionviewsource-as-an-itemssource"></a><span data-ttu-id="f6d3a-113">使用 CollectionViewSource 作为 System.windows.controls.itemscontrol.itemssource</span><span class="sxs-lookup"><span data-stu-id="f6d3a-113">Using a CollectionViewSource as an ItemsSource</span></span>

<span data-ttu-id="f6d3a-114">若要对 <xref:System.Windows.Controls.DataGrid> 控件中的数据进行分组、排序和筛选，请将 <xref:System.Windows.Controls.DataGrid> 绑定到支持这些函数的 <xref:System.Windows.Data.CollectionView>。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-114">To group, sort, and filter data in a <xref:System.Windows.Controls.DataGrid> control, you bind the <xref:System.Windows.Controls.DataGrid> to a <xref:System.Windows.Data.CollectionView> that supports these functions.</span></span> <span data-ttu-id="f6d3a-115">在此示例中，<xref:System.Windows.Controls.DataGrid> 绑定到 <xref:System.Windows.Data.CollectionViewSource>，该为 `Task` 对象的 <xref:System.Collections.Generic.List%601> 提供这些函数。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-115">In this example, the <xref:System.Windows.Controls.DataGrid> is bound to a <xref:System.Windows.Data.CollectionViewSource> that provides these functions for a <xref:System.Collections.Generic.List%601> of `Task` objects.</span></span>

### <a name="to-bind-a-datagrid-to-a-collectionviewsource"></a><span data-ttu-id="f6d3a-116">将 DataGrid 绑定到 CollectionViewSource</span><span class="sxs-lookup"><span data-stu-id="f6d3a-116">To bind a DataGrid to a CollectionViewSource</span></span>

1. <span data-ttu-id="f6d3a-117">创建实现 <xref:System.Collections.IEnumerable> 接口的数据集合。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-117">Create a data collection that implements the <xref:System.Collections.IEnumerable> interface.</span></span>

    <span data-ttu-id="f6d3a-118">如果使用 <xref:System.Collections.Generic.List%601> 创建集合，则应创建一个继承自 <xref:System.Collections.Generic.List%601> 的新类，而不是实例化 <xref:System.Collections.Generic.List%601>的实例。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-118">If you use <xref:System.Collections.Generic.List%601> to create your collection, you should create a new class that inherits from <xref:System.Collections.Generic.List%601> instead of instantiating an instance of <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="f6d3a-119">这使您可以将数据绑定到 XAML 中的集合。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-119">This enables you to data bind to the collection in XAML.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f6d3a-120">集合中的对象必须实现 <xref:System.ComponentModel.INotifyPropertyChanged> 更改的接口和 <xref:System.ComponentModel.IEditableObject> 接口，以便 <xref:System.Windows.Controls.DataGrid> 正确地响应属性更改和编辑。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-120">The objects in the collection must implement the <xref:System.ComponentModel.INotifyPropertyChanged> changed interface and the <xref:System.ComponentModel.IEditableObject> interface in order for the <xref:System.Windows.Controls.DataGrid> to respond correctly to property changes and edits.</span></span> <span data-ttu-id="f6d3a-121">有关详细信息，请参阅[实现属性更改通知](../data/how-to-implement-property-change-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-121">For more information, see [Implement Property Change Notification](../data/how-to-implement-property-change-notification.md).</span></span>

    [!code-csharp[DataGrid_GroupSortFilter#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#101)]
    [!code-vb[DataGrid_GroupSortFilter#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#101)]

2. <span data-ttu-id="f6d3a-122">在 XAML 中，创建集合类的实例并设置[X：Key 指令](../../../desktop-wpf/xaml-services/xkey-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-122">In XAML, create an instance of the collection class and set the [x:Key Directive](../../../desktop-wpf/xaml-services/xkey-directive.md).</span></span>

3. <span data-ttu-id="f6d3a-123">在 XAML 中，创建 <xref:System.Windows.Data.CollectionViewSource> 类的实例，设置[X：Key 指令](../../../desktop-wpf/xaml-services/xkey-directive.md)，并将集合类的实例设置为 <xref:System.Windows.Data.CollectionViewSource.Source%2A>。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-123">In XAML, create an instance of the <xref:System.Windows.Data.CollectionViewSource> class, set the [x:Key Directive](../../../desktop-wpf/xaml-services/xkey-directive.md), and set the instance of your collection class as the <xref:System.Windows.Data.CollectionViewSource.Source%2A>.</span></span>

    [!code-xaml[DataGrid_GroupSortFilter#201](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml#201)]

4. <span data-ttu-id="f6d3a-124">创建 <xref:System.Windows.Controls.DataGrid> 类的实例，并将 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 属性设置为 <xref:System.Windows.Data.CollectionViewSource>。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-124">Create an instance of the <xref:System.Windows.Controls.DataGrid> class, and set the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property to the <xref:System.Windows.Data.CollectionViewSource>.</span></span>

    [!code-xaml[DataGrid_GroupSortFilter#002](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#002)]

5. <span data-ttu-id="f6d3a-125">若要从代码访问 <xref:System.Windows.Data.CollectionViewSource>，请使用 <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> 方法获取对 <xref:System.Windows.Data.CollectionViewSource>的引用。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-125">To access the <xref:System.Windows.Data.CollectionViewSource> from your code, use the <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> method to get a reference to the <xref:System.Windows.Data.CollectionViewSource>.</span></span>

    [!code-csharp[DataGrid_GroupSortFilter#102](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#102)]
    [!code-vb[DataGrid_GroupSortFilter#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#102)]

## <a name="grouping-items-in-a-datagrid"></a><span data-ttu-id="f6d3a-126">对 DataGrid 中的项进行分组</span><span class="sxs-lookup"><span data-stu-id="f6d3a-126">Grouping items in a DataGrid</span></span>

<span data-ttu-id="f6d3a-127">若要指定如何在 <xref:System.Windows.Controls.DataGrid>中对项进行分组，请使用 <xref:System.Windows.Data.PropertyGroupDescription> 类型对源视图中的项进行分组。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-127">To specify how items are grouped in a <xref:System.Windows.Controls.DataGrid>, you use the <xref:System.Windows.Data.PropertyGroupDescription> type to group the items in the source view.</span></span>

### <a name="to-group-items-in-a-datagrid-using-xaml"></a><span data-ttu-id="f6d3a-128">使用 XAML 对 DataGrid 中的项进行分组</span><span class="sxs-lookup"><span data-stu-id="f6d3a-128">To group items in a DataGrid using XAML</span></span>

1. <span data-ttu-id="f6d3a-129">创建指定按其进行分组的属性的 <xref:System.Windows.Data.PropertyGroupDescription>。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-129">Create a <xref:System.Windows.Data.PropertyGroupDescription> that specifies the property to group by.</span></span> <span data-ttu-id="f6d3a-130">可以在 XAML 或代码中指定属性。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-130">You can specify the property in XAML or in code.</span></span>

   1. <span data-ttu-id="f6d3a-131">在 XAML 中，将 <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> 设置为要按其进行分组的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-131">In XAML, set the <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> to the name of the property to group by.</span></span>

   2. <span data-ttu-id="f6d3a-132">在 "代码" 中，将 "分组依据" 属性的名称传递到构造函数。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-132">In code, pass the name of the property to group by to the constructor.</span></span>

2. <span data-ttu-id="f6d3a-133">将 <xref:System.Windows.Data.PropertyGroupDescription> 添加到 <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> 集合。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-133">Add the <xref:System.Windows.Data.PropertyGroupDescription> to the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> collection.</span></span>

3. <span data-ttu-id="f6d3a-134">向 <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> 集合添加 <xref:System.Windows.Data.PropertyGroupDescription> 的其他实例，以便添加更多级别的分组。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-134">Add additional instances of <xref:System.Windows.Data.PropertyGroupDescription> to the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection to add more levels of grouping.</span></span>

    [!code-xaml[DataGrid_GroupSortFilter#012](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#012)]
    [!code-csharp[DataGrid_GroupSortFilter#112](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#112)]
    [!code-vb[DataGrid_GroupSortFilter#112](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#112)]

4. <span data-ttu-id="f6d3a-135">若要删除组，请从 <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> 集合中删除 <xref:System.Windows.Data.PropertyGroupDescription>。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-135">To remove a group, remove the <xref:System.Windows.Data.PropertyGroupDescription> from the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection.</span></span>

5. <span data-ttu-id="f6d3a-136">若要删除所有组，请调用 <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> 集合的 <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-136">To remove all groups, call the <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> method of the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection.</span></span>

    [!code-csharp[DataGrid_GroupSortFilter#114](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#114)]
    [!code-vb[DataGrid_GroupSortFilter#114](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#114)]

<span data-ttu-id="f6d3a-137">在 <xref:System.Windows.Controls.DataGrid>中对项进行分组时，可以定义一个指定每个组的外观的 <xref:System.Windows.Controls.GroupStyle>。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-137">When items are grouped in the <xref:System.Windows.Controls.DataGrid>, you can define a <xref:System.Windows.Controls.GroupStyle> that specifies the appearance of each group.</span></span> <span data-ttu-id="f6d3a-138">可以通过将 <xref:System.Windows.Controls.GroupStyle> 添加到 DataGrid 的 <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> 集合来应用该。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-138">You apply the <xref:System.Windows.Controls.GroupStyle> by adding it to the <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> collection of the DataGrid.</span></span> <span data-ttu-id="f6d3a-139">如果有多个级别的分组，则可以对每个组级别应用不同的样式。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-139">If you have multiple levels of grouping, you can apply different styles to each group level.</span></span> <span data-ttu-id="f6d3a-140">样式按其定义顺序进行应用。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-140">Styles are applied in the order in which they are defined.</span></span> <span data-ttu-id="f6d3a-141">例如，如果您定义两种样式，则第一个样式将应用于顶层行组。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-141">For example, if you define two styles, the first will be applied to top level row groups.</span></span> <span data-ttu-id="f6d3a-142">第二个样式将应用于第二级和下的所有行组。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-142">The second style will be applied to all row groups at the second level and lower.</span></span> <span data-ttu-id="f6d3a-143"><xref:System.Windows.Controls.GroupStyle> 的 <xref:System.Windows.FrameworkElement.DataContext%2A> 是组所表示的 <xref:System.Windows.Data.CollectionViewGroup>。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-143">The <xref:System.Windows.FrameworkElement.DataContext%2A> of the <xref:System.Windows.Controls.GroupStyle> is the <xref:System.Windows.Data.CollectionViewGroup> that the group represents.</span></span>

### <a name="to-change-the-appearance-of-row-group-headers"></a><span data-ttu-id="f6d3a-144">更改行组标题的外观</span><span class="sxs-lookup"><span data-stu-id="f6d3a-144">To change the appearance of row group headers</span></span>

1. <span data-ttu-id="f6d3a-145">创建定义行组外观的 <xref:System.Windows.Controls.GroupStyle>。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-145">Create a <xref:System.Windows.Controls.GroupStyle> that defines the appearance of the row group.</span></span>

2. <span data-ttu-id="f6d3a-146">将 <xref:System.Windows.Controls.GroupStyle> 放置在 `<DataGrid.GroupStyle>` 标记中。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-146">Put the <xref:System.Windows.Controls.GroupStyle> inside the `<DataGrid.GroupStyle>` tags.</span></span>

    [!code-xaml[DataGrid_GroupSortFilter#003](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#003)]

## <a name="sorting-items-in-a-datagrid"></a><span data-ttu-id="f6d3a-147">对 DataGrid 中的项进行排序</span><span class="sxs-lookup"><span data-stu-id="f6d3a-147">Sorting items in a DataGrid</span></span>

<span data-ttu-id="f6d3a-148">若要指定如何在 <xref:System.Windows.Controls.DataGrid>中对项进行排序，请使用 <xref:System.ComponentModel.SortDescription> 类型对源视图中的项进行排序。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-148">To specify how items are sorted in a <xref:System.Windows.Controls.DataGrid>, you use the <xref:System.ComponentModel.SortDescription> type to sort the items in the source view.</span></span>

### <a name="to-sort-items-in-a-datagrid"></a><span data-ttu-id="f6d3a-149">对 DataGrid 中的项进行排序</span><span class="sxs-lookup"><span data-stu-id="f6d3a-149">To sort items in a DataGrid</span></span>

1. <span data-ttu-id="f6d3a-150">创建一个指定要按其排序的属性的 <xref:System.ComponentModel.SortDescription>。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-150">Create a <xref:System.ComponentModel.SortDescription> that specifies the property to sort by.</span></span> <span data-ttu-id="f6d3a-151">可以在 XAML 或代码中指定属性。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-151">You can specify the property in XAML or in code.</span></span>

    1. <span data-ttu-id="f6d3a-152">在 XAML 中，将 <xref:System.ComponentModel.SortDescription.PropertyName%2A> 设置为要作为排序依据的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-152">In XAML, set the <xref:System.ComponentModel.SortDescription.PropertyName%2A> to the name of the property to sort by.</span></span>

    2. <span data-ttu-id="f6d3a-153">在代码中，传递要排序的属性的名称，并将 <xref:System.ComponentModel.ListSortDirection> 传递到构造函数。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-153">In code, pass the name of the property to sort by and the <xref:System.ComponentModel.ListSortDirection> to the constructor.</span></span>

2. <span data-ttu-id="f6d3a-154">将 <xref:System.ComponentModel.SortDescription> 添加到 <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> 集合。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-154">Add the <xref:System.ComponentModel.SortDescription> to the <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> collection.</span></span>

3. <span data-ttu-id="f6d3a-155">向 <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> 集合添加 <xref:System.ComponentModel.SortDescription> 的其他实例，以按其他属性进行排序。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-155">Add additional instances of <xref:System.ComponentModel.SortDescription> to the <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> collection to sort by additional properties.</span></span>

    [!code-xaml[DataGrid_GroupSortFilter#011](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#011)]
    [!code-csharp[DataGrid_GroupSortFilter#211](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml.cs#211)]
    [!code-vb[DataGrid_GroupSortFilter#211](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#211)]

## <a name="filtering-items-in-a-datagrid"></a><span data-ttu-id="f6d3a-156">筛选 DataGrid 中的项</span><span class="sxs-lookup"><span data-stu-id="f6d3a-156">Filtering items in a DataGrid</span></span>

<span data-ttu-id="f6d3a-157">若要使用 <xref:System.Windows.Data.CollectionViewSource>筛选 <xref:System.Windows.Controls.DataGrid> 中的项，请在 <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> 事件的处理程序中提供筛选逻辑。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-157">To filter items in a <xref:System.Windows.Controls.DataGrid> using a <xref:System.Windows.Data.CollectionViewSource>, you provide the filtering logic in the handler for the <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> event.</span></span>

### <a name="to-filter-items-in-a-datagrid"></a><span data-ttu-id="f6d3a-158">筛选 DataGrid 中的项</span><span class="sxs-lookup"><span data-stu-id="f6d3a-158">To filter items in a DataGrid</span></span>

1. <span data-ttu-id="f6d3a-159">为 <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> 事件添加处理程序。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-159">Add a handler for the <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> event.</span></span>

2. <span data-ttu-id="f6d3a-160">在 <xref:System.Windows.Data.CollectionViewSource.Filter> 事件处理程序中，定义筛选逻辑。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-160">In the <xref:System.Windows.Data.CollectionViewSource.Filter> event handler, define the filtering logic.</span></span>

    <span data-ttu-id="f6d3a-161">此筛选器将在每次刷新视图时应用。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-161">The filter will be applied every time the view is refreshed.</span></span>

    [!code-xaml[DataGrid_GroupSortFilter#013](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#013)]
    [!code-csharp[DataGrid_GroupSortFilter#113](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#113)]
    [!code-vb[DataGrid_GroupSortFilter#113](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#113)]

<span data-ttu-id="f6d3a-162">或者，您可以通过创建一个提供筛选逻辑并将 <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> 属性设置为应用筛选器的方法，来筛选 <xref:System.Windows.Controls.DataGrid> 中的项。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-162">Alternatively, you can filter items in a <xref:System.Windows.Controls.DataGrid> by creating a method that provides the filtering logic and setting the <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> property to apply the filter.</span></span> <span data-ttu-id="f6d3a-163">若要查看此方法的示例，请参阅[在视图中筛选数据](../data/how-to-filter-data-in-a-view.md)。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-163">To see an example of this method, see [Filter Data in a View](../data/how-to-filter-data-in-a-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="f6d3a-164">示例</span><span class="sxs-lookup"><span data-stu-id="f6d3a-164">Example</span></span>

<span data-ttu-id="f6d3a-165">下面的示例演示如何对 <xref:System.Windows.Data.CollectionViewSource> 中的 `Task` 数据进行分组、排序和筛选，以及如何在 <xref:System.Windows.Controls.DataGrid>中显示分组、排序和筛选的 `Task` 数据。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-165">The following example demonstrates grouping, sorting, and filtering `Task` data in a <xref:System.Windows.Data.CollectionViewSource> and displaying the grouped, sorted, and filtered `Task` data in a <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="f6d3a-166"><xref:System.Windows.Data.CollectionViewSource> 用作 <xref:System.Windows.Controls.DataGrid>的 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-166">The <xref:System.Windows.Data.CollectionViewSource> is used as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="f6d3a-167">分组、排序和筛选是在 <xref:System.Windows.Data.CollectionViewSource> 上执行的，并显示在 <xref:System.Windows.Controls.DataGrid> UI 中。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-167">Grouping, sorting, and filtering are performed on the <xref:System.Windows.Data.CollectionViewSource> and are displayed in the <xref:System.Windows.Controls.DataGrid> UI.</span></span>

<span data-ttu-id="f6d3a-168">若要测试此示例，需调整 DGGroupSortFilterExample 名称，使其与项目名称匹配。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-168">To test this example, you will need to adjust the DGGroupSortFilterExample name to match your project name.</span></span> <span data-ttu-id="f6d3a-169">如果使用 Visual Basic，则需要将 <xref:System.Windows.Window> 的类名称更改为以下项。</span><span class="sxs-lookup"><span data-stu-id="f6d3a-169">If you are using Visual Basic, you will need to change the class name for <xref:System.Windows.Window> to the following.</span></span>

`<Window x:Class="MainWindow"`

[!code-xaml[DataGrid_GroupSortFilter#000](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#000)]
[!code-csharp[DataGrid_GroupSortFilter#100](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#100)]
[!code-vb[DataGrid_GroupSortFilter#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#100)]

## <a name="see-also"></a><span data-ttu-id="f6d3a-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6d3a-170">See also</span></span>

- [<span data-ttu-id="f6d3a-171">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="f6d3a-171">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="f6d3a-172">创建和绑定到 ObservableCollection</span><span class="sxs-lookup"><span data-stu-id="f6d3a-172">Create and Bind to an ObservableCollection</span></span>](../data/how-to-create-and-bind-to-an-observablecollection.md)
- [<span data-ttu-id="f6d3a-173">在视图中筛选数据</span><span class="sxs-lookup"><span data-stu-id="f6d3a-173">Filter Data in a View</span></span>](../data/how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="f6d3a-174">在视图中对数据进行排序</span><span class="sxs-lookup"><span data-stu-id="f6d3a-174">Sort Data in a View</span></span>](../data/how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="f6d3a-175">在 XAML 中使用视图对数据进行排序和分组</span><span class="sxs-lookup"><span data-stu-id="f6d3a-175">Sort and Group Data Using a View in XAML</span></span>](../data/how-to-sort-and-group-data-using-a-view-in-xaml.md)
