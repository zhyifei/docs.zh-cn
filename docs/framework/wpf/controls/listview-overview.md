---
title: ListView 概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ListView
- ListView controls [WPF], about ListView control
ms.assetid: 989e12b0-260e-4570-95c6-489284003ce2
ms.openlocfilehash: 2f336d1eb8dcdfec3c3c8059ba865147c6b6c825
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187520"
---
# <a name="listview-overview"></a><span data-ttu-id="052be-102">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="052be-102">ListView Overview</span></span>
<span data-ttu-id="052be-103">该<xref:System.Windows.Controls.ListView>控件提供基础结构以在不同的布局或视图中显示一组数据项。</span><span class="sxs-lookup"><span data-stu-id="052be-103">The <xref:System.Windows.Controls.ListView> control provides the infrastructure to display a set of data items in different layouts or views.</span></span> <span data-ttu-id="052be-104">例如，用户可能需要在表格中显示数据项，并同时对表格的列进行排序。</span><span class="sxs-lookup"><span data-stu-id="052be-104">For example, a user may want to display data items in a table and also to sort its columns.</span></span>  

<a name="WhatisaListView"></a>
## <a name="what-is-a-listview"></a><span data-ttu-id="052be-105">什么是 ListView？</span><span class="sxs-lookup"><span data-stu-id="052be-105">What Is a ListView?</span></span>  
 <span data-ttu-id="052be-106">控件<xref:System.Windows.Controls.ListView>是从<xref:System.Windows.Controls.ItemsControl>派生的<xref:System.Windows.Controls.ListBox>。</span><span class="sxs-lookup"><span data-stu-id="052be-106">The <xref:System.Windows.Controls.ListView> control is an <xref:System.Windows.Controls.ItemsControl> that is derived from <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="052be-107">通常，其项是数据收集的成员，并表示为<xref:System.Windows.Controls.ListViewItem>对象。</span><span class="sxs-lookup"><span data-stu-id="052be-107">Typically, its items are members of a data collection and are represented as <xref:System.Windows.Controls.ListViewItem> objects.</span></span> <span data-ttu-id="052be-108">a<xref:System.Windows.Controls.ListViewItem>是<xref:System.Windows.Controls.ContentControl>，只能包含单个子元素。</span><span class="sxs-lookup"><span data-stu-id="052be-108">A <xref:System.Windows.Controls.ListViewItem> is a <xref:System.Windows.Controls.ContentControl> and can contain only a single child element.</span></span> <span data-ttu-id="052be-109">但是，该子元素可以是任何视觉元素。</span><span class="sxs-lookup"><span data-stu-id="052be-109">However, that child element can be any visual element.</span></span>  
  
<a name="DefiningaListViewView"></a>
## <a name="defining-a-view-mode-for-a-listview"></a><span data-ttu-id="052be-110">为 ListView 定义视图模式</span><span class="sxs-lookup"><span data-stu-id="052be-110">Defining a View Mode for a ListView</span></span>  
 <span data-ttu-id="052be-111">要为<xref:System.Windows.Controls.ListView>控件的内容指定视图模式，请设置 属性<xref:System.Windows.Controls.ListView.View%2A>。</span><span class="sxs-lookup"><span data-stu-id="052be-111">To specify a view mode for the content of a <xref:System.Windows.Controls.ListView> control, you set the <xref:System.Windows.Controls.ListView.View%2A> property.</span></span> <span data-ttu-id="052be-112">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]提供的一种视图模式是<xref:System.Windows.Controls.GridView>，它显示具有可自定义列的表中的数据项的集合。</span><span class="sxs-lookup"><span data-stu-id="052be-112">One view mode that [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] provides is <xref:System.Windows.Controls.GridView>, which displays a collection of data items in a table that has customizable columns.</span></span>  
  
 <span data-ttu-id="052be-113">下面的示例演示如何为显示员工信息的<xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView>控件定义 。</span><span class="sxs-lookup"><span data-stu-id="052be-113">The following example shows how to define a <xref:System.Windows.Controls.GridView> for a <xref:System.Windows.Controls.ListView> control that displays employee information.</span></span>  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 <span data-ttu-id="052be-114">下图演示上一个示例的数据显示方式。</span><span class="sxs-lookup"><span data-stu-id="052be-114">The following illustration shows how the data appears for the previous example.</span></span>  
  
 ![显示带有 GridView 输出的 ListView 的屏幕截图。](./media/gridview-overview/listview-gridview-output.jpg)  
  
 <span data-ttu-id="052be-116">可以通过定义从类继承的<xref:System.Windows.Controls.ViewBase>类来创建自定义视图模式。</span><span class="sxs-lookup"><span data-stu-id="052be-116">You can create a custom view mode by defining a class that inherits from the <xref:System.Windows.Controls.ViewBase> class.</span></span> <span data-ttu-id="052be-117">类<xref:System.Windows.Controls.ViewBase>提供创建自定义视图所需的基础结构。</span><span class="sxs-lookup"><span data-stu-id="052be-117">The <xref:System.Windows.Controls.ViewBase> class provides the infrastructure that you need to create a custom view.</span></span> <span data-ttu-id="052be-118">有关如何创建自定义视图的详细信息，请参阅[为 ListView 创建自定义视图模式](how-to-create-a-custom-view-mode-for-a-listview.md)。</span><span class="sxs-lookup"><span data-stu-id="052be-118">For more information about how to create a custom view, see [Create a Custom View Mode for a ListView](how-to-create-a-custom-view-mode-for-a-listview.md).</span></span>  
  
<a name="BindingDatatoaListView"></a>
## <a name="binding-data-to-a-listview"></a><span data-ttu-id="052be-119">将数据绑定到 ListView</span><span class="sxs-lookup"><span data-stu-id="052be-119">Binding Data to a ListView</span></span>  
 <span data-ttu-id="052be-120">使用<xref:System.Windows.Controls.ItemsControl.Items%2A>和<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>属性为控件指定项<xref:System.Windows.Controls.ListView>。</span><span class="sxs-lookup"><span data-stu-id="052be-120">Use the <xref:System.Windows.Controls.ItemsControl.Items%2A> and <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> properties to specify items for a <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="052be-121">下面的示例将<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>属性设置到称为`EmployeeInfoDataSource`的数据收集。</span><span class="sxs-lookup"><span data-stu-id="052be-121">The following example sets the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property to a data collection that is called `EmployeeInfoDataSource`.</span></span>  
  
 [!code-xaml[ListViewCode#ItemsSource](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#itemssource)]  
  
 <span data-ttu-id="052be-122">在<xref:System.Windows.Controls.GridView>中<xref:System.Windows.Controls.GridViewColumn>，对象绑定到指定的数据字段。</span><span class="sxs-lookup"><span data-stu-id="052be-122">In a <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridViewColumn> objects bind to specified data fields.</span></span> <span data-ttu-id="052be-123">下面的示例通过为<xref:System.Windows.Controls.GridViewColumn><xref:System.Windows.Data.Binding><xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>属性指定 的 将对象绑定到数据字段。</span><span class="sxs-lookup"><span data-stu-id="052be-123">The following example binds a <xref:System.Windows.Controls.GridViewColumn> object to a data field by specifying a <xref:System.Windows.Data.Binding> for the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property.</span></span>  
  
 [!code-csharp[ListViewCode#GridViewColumnProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml.cs#gridviewcolumnproperties)]
 [!code-vb[ListViewCode#GridViewColumnProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCode/visualbasic/window1.xaml.vb#gridviewcolumnproperties)]
 [!code-xaml[ListViewCode#GridViewColumnProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#gridviewcolumnproperties)]  
  
 <span data-ttu-id="052be-124">还可以指定 作为<xref:System.Windows.Data.Binding>用于设置列单元格样式<xref:System.Windows.DataTemplate>的定义的一部分。</span><span class="sxs-lookup"><span data-stu-id="052be-124">You can also specify a <xref:System.Windows.Data.Binding> as part of a <xref:System.Windows.DataTemplate> definition that you use to style the cells in a column.</span></span> <span data-ttu-id="052be-125">在下面的<xref:System.Windows.DataTemplate>示例中，使用<xref:System.Windows.ResourceKey>集<xref:System.Windows.Data.Binding>标识 的 。 <xref:System.Windows.Controls.GridViewColumn></span><span class="sxs-lookup"><span data-stu-id="052be-125">In the following example, the <xref:System.Windows.DataTemplate> that is identified with a <xref:System.Windows.ResourceKey> sets the <xref:System.Windows.Data.Binding> for a <xref:System.Windows.Controls.GridViewColumn>.</span></span> <span data-ttu-id="052be-126">请注意，此示例不定义，<xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>因为这样做会覆盖 由<xref:System.Windows.DataTemplate>指定的绑定。</span><span class="sxs-lookup"><span data-stu-id="052be-126">Note that this example does not define the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> because doing so overrides the binding that is specified by <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
<a name="StylingaListView"></a>
## <a name="styling-a-listview-that-implements-a-gridview"></a><span data-ttu-id="052be-127">为实现 GridView 的 ListView 设置样式</span><span class="sxs-lookup"><span data-stu-id="052be-127">Styling a ListView That Implements a GridView</span></span>  
 <span data-ttu-id="052be-128">控件<xref:System.Windows.Controls.ListView>包含<xref:System.Windows.Controls.ListViewItem>表示显示的数据项的对象。</span><span class="sxs-lookup"><span data-stu-id="052be-128">The <xref:System.Windows.Controls.ListView> control contains <xref:System.Windows.Controls.ListViewItem> objects, which represent the data items that are displayed.</span></span> <span data-ttu-id="052be-129">可使用以下属性定义数据项的内容和样式：</span><span class="sxs-lookup"><span data-stu-id="052be-129">You can use the following properties to define the content and style of data items:</span></span>  
  
- <span data-ttu-id="052be-130">在控件<xref:System.Windows.Controls.ListView>上，使用<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>、<xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>和<xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="052be-130">On the <xref:System.Windows.Controls.ListView> control, use the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>, and <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> properties.</span></span>  
  
- <span data-ttu-id="052be-131">在控件<xref:System.Windows.Controls.ListViewItem>上，使用<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>和<xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="052be-131">On the <xref:System.Windows.Controls.ListViewItem> control, use the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> and <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> properties.</span></span>  
  
 <span data-ttu-id="052be-132">为了避免 在<xref:System.Windows.Controls.GridView>的单元格之间对齐问题，请勿使用<xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>来设置 属性或添加影响 中项宽度的内容<xref:System.Windows.Controls.ListView>。</span><span class="sxs-lookup"><span data-stu-id="052be-132">To avoid alignment issues between cells in a <xref:System.Windows.Controls.GridView>, do not use the <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> to set properties or add content that affects the width of an item in a <xref:System.Windows.Controls.ListView>.</span></span> <span data-ttu-id="052be-133">例如，在 中设置<xref:System.Windows.FrameworkElement.Margin%2A>属性时，可能会出现对齐问题。 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A></span><span class="sxs-lookup"><span data-stu-id="052be-133">For example, an alignment issue can occur when you set the <xref:System.Windows.FrameworkElement.Margin%2A> property in the <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>.</span></span> <span data-ttu-id="052be-134">要指定影响 中项宽度的属性或定义内容<xref:System.Windows.Controls.GridView>，请使用<xref:System.Windows.Controls.GridView>类及其相关类的属性，如<xref:System.Windows.Controls.GridViewColumn>。</span><span class="sxs-lookup"><span data-stu-id="052be-134">To specify properties or define content that affects the width of items in a <xref:System.Windows.Controls.GridView>, use the properties of the <xref:System.Windows.Controls.GridView> class and its related classes, such as <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 <span data-ttu-id="052be-135">有关如何使用<xref:System.Windows.Controls.GridView>及其支持类的详细信息，请参阅[GridView 概述](gridview-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="052be-135">For more information about how to use <xref:System.Windows.Controls.GridView> and its supporting classes, see [GridView Overview](gridview-overview.md).</span></span>  
  
 <span data-ttu-id="052be-136">如果<xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>为<xref:System.Windows.Controls.ListView>控件定义 。 ，并且还定义了<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>， 必须在样式<xref:System.Windows.Controls.ContentPresenter><xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>中包括 。</span><span class="sxs-lookup"><span data-stu-id="052be-136">If you define an <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> for a <xref:System.Windows.Controls.ListView> control and also define an <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, you must include a <xref:System.Windows.Controls.ContentPresenter> in the style in order for the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> to work correctly.</span></span>  
  
 <span data-ttu-id="052be-137">不要对使用<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>显示<xref:System.Windows.Controls.Control.VerticalContentAlignment%2A><xref:System.Windows.Controls.ListView>的内容使用 和 属性<xref:System.Windows.Controls.GridView>。</span><span class="sxs-lookup"><span data-stu-id="052be-137">Do not use the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> and <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> properties for <xref:System.Windows.Controls.ListView> content that is displayed by using a <xref:System.Windows.Controls.GridView>.</span></span> <span data-ttu-id="052be-138">要指定 内容在 的列中的对齐方式<xref:System.Windows.Controls.GridView>，请定义<xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>。</span><span class="sxs-lookup"><span data-stu-id="052be-138">To specify the alignment of content in a column of a <xref:System.Windows.Controls.GridView>, define a <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>.</span></span>  
  
<a name="UsingtheSameViewMoreThanOnce"></a>
## <a name="sharing-the-same-view-mode"></a><span data-ttu-id="052be-139">共享同一视图模式</span><span class="sxs-lookup"><span data-stu-id="052be-139">Sharing the Same View Mode</span></span>  
 <span data-ttu-id="052be-140">两<xref:System.Windows.Controls.ListView>个控件不能同时共享同一视图模式。</span><span class="sxs-lookup"><span data-stu-id="052be-140">Two <xref:System.Windows.Controls.ListView> controls cannot share the same view mode at the same time.</span></span> <span data-ttu-id="052be-141">如果尝试对多个<xref:System.Windows.Controls.ListView>控件使用相同的视图模式，则会发生异常。</span><span class="sxs-lookup"><span data-stu-id="052be-141">If you try to use the same view mode with more than one <xref:System.Windows.Controls.ListView> control, an exception occurs.</span></span>  
  
 <span data-ttu-id="052be-142">要指定可以由多个<xref:System.Windows.Controls.ListView>多个同时使用的视图模式，请使用模板或样式。</span><span class="sxs-lookup"><span data-stu-id="052be-142">To specify a view mode that can be simultaneously used by more than one <xref:System.Windows.Controls.ListView>, use templates or styles.</span></span>
  
<a name="CreatingaCustomView"></a>
## <a name="creating-a-custom-view-mode"></a><span data-ttu-id="052be-143">创建自定义视图模式</span><span class="sxs-lookup"><span data-stu-id="052be-143">Creating a Custom View Mode</span></span>  
 <span data-ttu-id="052be-144">自定义视图如<xref:System.Windows.Controls.GridView>从<xref:System.Windows.Controls.ViewBase>抽象类派生，它提供了显示表示为<xref:System.Windows.Controls.ListViewItem>对象的数据项的工具。</span><span class="sxs-lookup"><span data-stu-id="052be-144">Customized views like <xref:System.Windows.Controls.GridView> are derived from the <xref:System.Windows.Controls.ViewBase> abstract class, which provides the tools to display data items that are represented as <xref:System.Windows.Controls.ListViewItem> objects.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="052be-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="052be-145">See also</span></span>

- <xref:System.Windows.Controls.GridView>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.ListViewItem>
- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="052be-146">GridView 概述</span><span class="sxs-lookup"><span data-stu-id="052be-146">GridView Overview</span></span>](gridview-overview.md)
- [<span data-ttu-id="052be-147">如何使用主题</span><span class="sxs-lookup"><span data-stu-id="052be-147">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="052be-148">控制</span><span class="sxs-lookup"><span data-stu-id="052be-148">Controls</span></span>](../advanced/optimizing-performance-controls.md)
