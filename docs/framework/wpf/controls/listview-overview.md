---
title: "ListView 概述"
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
- controls [WPF], ListView
- ListView controls [WPF], about ListView control
ms.assetid: 989e12b0-260e-4570-95c6-489284003ce2
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 62144217199a62da3e41bf381162c94c91d00e72
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="listview-overview"></a><span data-ttu-id="f7cae-102">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="f7cae-102">ListView Overview</span></span>
<span data-ttu-id="f7cae-103"><xref:System.Windows.Controls.ListView>控件提供的基础结构在不同的布局或视图中显示的数据项目集。</span><span class="sxs-lookup"><span data-stu-id="f7cae-103">The <xref:System.Windows.Controls.ListView> control provides the infrastructure to display a set of data items in different layouts or views.</span></span> <span data-ttu-id="f7cae-104">例如，用户可能需要在表格中显示数据项，并同时对表格的列进行排序。</span><span class="sxs-lookup"><span data-stu-id="f7cae-104">For example, a user may want to display data items in a table and also to sort its columns.</span></span>  
  
  
<a name="WhatisaListView"></a>   
## <a name="what-is-a-listview"></a><span data-ttu-id="f7cae-105">什么是 ListView？</span><span class="sxs-lookup"><span data-stu-id="f7cae-105">What Is a ListView?</span></span>  
 <span data-ttu-id="f7cae-106"><xref:System.Windows.Controls.ListView>控件是<xref:System.Windows.Controls.ItemsControl>、 派生自<xref:System.Windows.Controls.ListBox>。</span><span class="sxs-lookup"><span data-stu-id="f7cae-106">The <xref:System.Windows.Controls.ListView> control is an <xref:System.Windows.Controls.ItemsControl> that is derived from <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="f7cae-107">通常情况下，其项是数据集合的成员，表示为<xref:System.Windows.Controls.ListViewItem>对象。</span><span class="sxs-lookup"><span data-stu-id="f7cae-107">Typically, its items are members of a data collection and are represented as <xref:System.Windows.Controls.ListViewItem> objects.</span></span> <span data-ttu-id="f7cae-108">A<xref:System.Windows.Controls.ListViewItem>是<xref:System.Windows.Controls.ContentControl>，并且可以包含单个子元素。</span><span class="sxs-lookup"><span data-stu-id="f7cae-108">A <xref:System.Windows.Controls.ListViewItem> is a <xref:System.Windows.Controls.ContentControl> and can contain only a single child element.</span></span> <span data-ttu-id="f7cae-109">但是，该子元素可以是任何视觉元素。</span><span class="sxs-lookup"><span data-stu-id="f7cae-109">However, that child element can be any visual element.</span></span>  
  
<a name="DefiningaListViewView"></a>   
## <a name="defining-a-view-mode-for-a-listview"></a><span data-ttu-id="f7cae-110">为 ListView 定义视图模式</span><span class="sxs-lookup"><span data-stu-id="f7cae-110">Defining a View Mode for a ListView</span></span>  
 <span data-ttu-id="f7cae-111">若要指定的内容视图模式<xref:System.Windows.Controls.ListView>控件，则设置<xref:System.Windows.Controls.ListView.View%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="f7cae-111">To specify a view mode for the content of a <xref:System.Windows.Controls.ListView> control, you set the <xref:System.Windows.Controls.ListView.View%2A> property.</span></span> <span data-ttu-id="f7cae-112">一个视图模式，[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]提供是<xref:System.Windows.Controls.GridView>，它具有可自定义列的表中会显示数据项的集合。</span><span class="sxs-lookup"><span data-stu-id="f7cae-112">One view mode that [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] provides is <xref:System.Windows.Controls.GridView>, which displays a collection of data items in a table that has customizable columns.</span></span>  
  
 <span data-ttu-id="f7cae-113">下面的示例演示如何定义<xref:System.Windows.Controls.GridView>为<xref:System.Windows.Controls.ListView>显示员工信息的控件。</span><span class="sxs-lookup"><span data-stu-id="f7cae-113">The following example shows how to define a <xref:System.Windows.Controls.GridView> for a <xref:System.Windows.Controls.ListView> control that displays employee information.</span></span>  
  
 [!code-xaml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 <span data-ttu-id="f7cae-114">下图演示上一个示例的数据显示方式。</span><span class="sxs-lookup"><span data-stu-id="f7cae-114">The following illustration shows how the data appears for the previous example.</span></span>  
  
 <span data-ttu-id="f7cae-115">![具有 GridView 输出的 ListView](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")</span><span class="sxs-lookup"><span data-stu-id="f7cae-115">![ListView with GridView output](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")</span></span>  
  
 <span data-ttu-id="f7cae-116">你可以通过定义继承自的类创建自定义视图模式<xref:System.Windows.Controls.ViewBase>类。</span><span class="sxs-lookup"><span data-stu-id="f7cae-116">You can create a custom view mode by defining a class that inherits from the <xref:System.Windows.Controls.ViewBase> class.</span></span> <span data-ttu-id="f7cae-117"><xref:System.Windows.Controls.ViewBase>类提供你需要创建自定义视图的基础结构。</span><span class="sxs-lookup"><span data-stu-id="f7cae-117">The <xref:System.Windows.Controls.ViewBase> class provides the infrastructure that you need to create a custom view.</span></span> <span data-ttu-id="f7cae-118">有关如何创建自定义视图的详细信息，请参阅[为 ListView 创建自定义视图模式](../../../../docs/framework/wpf/controls/how-to-create-a-custom-view-mode-for-a-listview.md)。</span><span class="sxs-lookup"><span data-stu-id="f7cae-118">For more information about how to create a custom view, see [Create a Custom View Mode for a ListView](../../../../docs/framework/wpf/controls/how-to-create-a-custom-view-mode-for-a-listview.md).</span></span>  
  
<a name="BindingDatatoaListView"></a>   
## <a name="binding-data-to-a-listview"></a><span data-ttu-id="f7cae-119">将数据绑定到 ListView</span><span class="sxs-lookup"><span data-stu-id="f7cae-119">Binding Data to a ListView</span></span>  
 <span data-ttu-id="f7cae-120">使用<xref:System.Windows.Controls.ItemsControl.Items%2A>和<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>属性以指定项<xref:System.Windows.Controls.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="f7cae-120">Use the <xref:System.Windows.Controls.ItemsControl.Items%2A> and <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> properties to specify items for a <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="f7cae-121">下面的示例设置<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>属性数据集合，它称为`EmployeeInfoDataSource`。</span><span class="sxs-lookup"><span data-stu-id="f7cae-121">The following example sets the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property to a data collection that is called `EmployeeInfoDataSource`.</span></span>  
  
 [!code-xaml[ListViewCode#ItemsSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#itemssource)]  
  
 <span data-ttu-id="f7cae-122">在<xref:System.Windows.Controls.GridView>，<xref:System.Windows.Controls.GridViewColumn>对象将绑定到指定的数据字段。</span><span class="sxs-lookup"><span data-stu-id="f7cae-122">In a <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridViewColumn> objects bind to specified data fields.</span></span> <span data-ttu-id="f7cae-123">下面的示例将绑定<xref:System.Windows.Controls.GridViewColumn>到通过指定数据字段的对象<xref:System.Windows.Data.Binding>为<xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="f7cae-123">The following example binds a <xref:System.Windows.Controls.GridViewColumn> object to a data field by specifying a <xref:System.Windows.Data.Binding> for the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property.</span></span>  
  
 [!code-csharp[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml.cs#gridviewcolumnproperties)]
 [!code-vb[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCode/visualbasic/window1.xaml.vb#gridviewcolumnproperties)]
 [!code-xaml[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#gridviewcolumnproperties)]  
  
 <span data-ttu-id="f7cae-124">你还可以指定<xref:System.Windows.Data.Binding>作为的一部分<xref:System.Windows.DataTemplate>使用来设置列中的单元格的样式的定义。</span><span class="sxs-lookup"><span data-stu-id="f7cae-124">You can also specify a <xref:System.Windows.Data.Binding> as part of a <xref:System.Windows.DataTemplate> definition that you use to style the cells in a column.</span></span> <span data-ttu-id="f7cae-125">在下面的示例中，<xref:System.Windows.DataTemplate>识别具有以下<xref:System.Windows.ResourceKey>设置<xref:System.Windows.Data.Binding>为<xref:System.Windows.Controls.GridViewColumn>。</span><span class="sxs-lookup"><span data-stu-id="f7cae-125">In the following example, the <xref:System.Windows.DataTemplate> that is identified with a <xref:System.Windows.ResourceKey> sets the <xref:System.Windows.Data.Binding> for a <xref:System.Windows.Controls.GridViewColumn>.</span></span> <span data-ttu-id="f7cae-126">请注意，此示例不会定义<xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>因为这样做将覆盖由指定的绑定<xref:System.Windows.DataTemplate>。</span><span class="sxs-lookup"><span data-stu-id="f7cae-126">Note that this example does not define the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> because doing so overrides the binding that is specified by <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
<a name="StylingaListView"></a>   
## <a name="styling-a-listview-that-implements-a-gridview"></a><span data-ttu-id="f7cae-127">为实现 GridView 的 ListView 设置样式</span><span class="sxs-lookup"><span data-stu-id="f7cae-127">Styling a ListView That Implements a GridView</span></span>  
 <span data-ttu-id="f7cae-128"><xref:System.Windows.Controls.ListView>控件包含<xref:System.Windows.Controls.ListViewItem>对象，表示显示的数据项。</span><span class="sxs-lookup"><span data-stu-id="f7cae-128">The <xref:System.Windows.Controls.ListView> control contains <xref:System.Windows.Controls.ListViewItem> objects, which represent the data items that are displayed.</span></span> <span data-ttu-id="f7cae-129">可使用以下属性定义数据项的内容和样式：</span><span class="sxs-lookup"><span data-stu-id="f7cae-129">You can use the following properties to define the content and style of data items:</span></span>  
  
-   <span data-ttu-id="f7cae-130">上<xref:System.Windows.Controls.ListView>控制，请使用<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>， <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>，和<xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="f7cae-130">On the <xref:System.Windows.Controls.ListView> control, use the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>, and <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> properties.</span></span>  
  
-   <span data-ttu-id="f7cae-131">上<xref:System.Windows.Controls.ListViewItem>控制，请使用<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>和<xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="f7cae-131">On the <xref:System.Windows.Controls.ListViewItem> control, use the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> and <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> properties.</span></span>  
  
 <span data-ttu-id="f7cae-132">若要避免中单元格之间的对齐方式问题<xref:System.Windows.Controls.GridView>，不要使用<xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>设置属性或将影响中的项的宽度的内容添加<xref:System.Windows.Controls.ListView>。</span><span class="sxs-lookup"><span data-stu-id="f7cae-132">To avoid alignment issues between cells in a <xref:System.Windows.Controls.GridView>, do not use the <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> to set properties or add content that affects the width of an item in a <xref:System.Windows.Controls.ListView>.</span></span> <span data-ttu-id="f7cae-133">例如，对齐问题可能会导致当您设置<xref:System.Windows.FrameworkElement.Margin%2A>中的属性<xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>。</span><span class="sxs-lookup"><span data-stu-id="f7cae-133">For example, an alignment issue can occur when you set the <xref:System.Windows.FrameworkElement.Margin%2A> property in the <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>.</span></span> <span data-ttu-id="f7cae-134">若要指定属性或定义中的项的宽度有影响的内容<xref:System.Windows.Controls.GridView>，使用的属性<xref:System.Windows.Controls.GridView>类和相关的类，如<xref:System.Windows.Controls.GridViewColumn>。</span><span class="sxs-lookup"><span data-stu-id="f7cae-134">To specify properties or define content that affects the width of items in a <xref:System.Windows.Controls.GridView>, use the properties of the <xref:System.Windows.Controls.GridView> class and its related classes, such as <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 <span data-ttu-id="f7cae-135">有关如何使用<xref:System.Windows.Controls.GridView>和其支持的类，请参阅[GridView 概述](../../../../docs/framework/wpf/controls/gridview-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="f7cae-135">For more information about how to use <xref:System.Windows.Controls.GridView> and its supporting classes, see [GridView Overview](../../../../docs/framework/wpf/controls/gridview-overview.md).</span></span>  
  
 <span data-ttu-id="f7cae-136">如果你定义<xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>为<xref:System.Windows.Controls.ListView>控制，还可定义<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>，必须包括<xref:System.Windows.Controls.ContentPresenter>顺序样式<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>正常工作。</span><span class="sxs-lookup"><span data-stu-id="f7cae-136">If you define an <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> for a <xref:System.Windows.Controls.ListView> control and also define an <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, you must include a <xref:System.Windows.Controls.ContentPresenter> in the style in order for the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> to work correctly.</span></span>  
  
 <span data-ttu-id="f7cae-137">不要使用<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>和<xref:System.Windows.Controls.Control.VerticalContentAlignment%2A>属性<xref:System.Windows.Controls.ListView>通过使用显示的内容<xref:System.Windows.Controls.GridView>。</span><span class="sxs-lookup"><span data-stu-id="f7cae-137">Do not use the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> and <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> properties for <xref:System.Windows.Controls.ListView> content that is displayed by using a <xref:System.Windows.Controls.GridView>.</span></span> <span data-ttu-id="f7cae-138">若要指定的列中的内容的对齐方式<xref:System.Windows.Controls.GridView>，定义<xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>。</span><span class="sxs-lookup"><span data-stu-id="f7cae-138">To specify the alignment of content in a column of a <xref:System.Windows.Controls.GridView>, define a <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>.</span></span>  
  
<a name="UsingtheSameViewMoreThanOnce"></a>   
## <a name="sharing-the-same-view-mode"></a><span data-ttu-id="f7cae-139">共享同一视图模式</span><span class="sxs-lookup"><span data-stu-id="f7cae-139">Sharing the Same View Mode</span></span>  
 <span data-ttu-id="f7cae-140">两个<xref:System.Windows.Controls.ListView>控件不能在同一时间共享相同的视图模式。</span><span class="sxs-lookup"><span data-stu-id="f7cae-140">Two <xref:System.Windows.Controls.ListView> controls cannot share the same view mode at the same time.</span></span> <span data-ttu-id="f7cae-141">如果你尝试使用带有多个相同的视图模式<xref:System.Windows.Controls.ListView>控制，则会发生异常。</span><span class="sxs-lookup"><span data-stu-id="f7cae-141">If you try to use the same view mode with more than one <xref:System.Windows.Controls.ListView> control, an exception occurs.</span></span>  
  
 <span data-ttu-id="f7cae-142">若要指定可同时由多个视图模式<xref:System.Windows.Controls.ListView>，使用模板或样式。</span><span class="sxs-lookup"><span data-stu-id="f7cae-142">To specify a view mode that can be simultaneously used by more than one <xref:System.Windows.Controls.ListView>, use templates or styles.</span></span> <span data-ttu-id="f7cae-143">有关如何定义为视图的示例<xref:System.Windows.FrameworkElement.Resources%2A>，请参阅[与多个视图示例 ListView](http://go.microsoft.com/fwlink/?LinkID=160013)。</span><span class="sxs-lookup"><span data-stu-id="f7cae-143">For an example of how to define views as <xref:System.Windows.FrameworkElement.Resources%2A>, see [ListView with Multiple Views Sample](http://go.microsoft.com/fwlink/?LinkID=160013).</span></span>  
  
<a name="CreatingaCustomView"></a>   
## <a name="creating-a-custom-view-mode"></a><span data-ttu-id="f7cae-144">创建自定义视图模式</span><span class="sxs-lookup"><span data-stu-id="f7cae-144">Creating a Custom View Mode</span></span>  
 <span data-ttu-id="f7cae-145">自定义等视图与<xref:System.Windows.Controls.GridView>派生自<xref:System.Windows.Controls.ViewBase>抽象类，该类提供的工具来显示表示为数据项目<xref:System.Windows.Controls.ListViewItem>对象。</span><span class="sxs-lookup"><span data-stu-id="f7cae-145">Customized views like <xref:System.Windows.Controls.GridView> are derived from the <xref:System.Windows.Controls.ViewBase> abstract class, which provides the tools to display data items that are represented as <xref:System.Windows.Controls.ListViewItem> objects.</span></span>  
  
 <span data-ttu-id="f7cae-146">有关自定义视图模式的示例，请参阅[具有多个视图的 ListView 示例](http://go.microsoft.com/fwlink/?LinkID=160013)。</span><span class="sxs-lookup"><span data-stu-id="f7cae-146">For an example of a custom view mode, see [ListView with Multiple Views Sample](http://go.microsoft.com/fwlink/?LinkID=160013).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7cae-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7cae-147">See Also</span></span>  
 <xref:System.Windows.Controls.GridView>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.ListViewItem>  
 <xref:System.Windows.Data.Binding>  
 [<span data-ttu-id="f7cae-148">GridView 概述</span><span class="sxs-lookup"><span data-stu-id="f7cae-148">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)  
 [<span data-ttu-id="f7cae-149">帮助主题</span><span class="sxs-lookup"><span data-stu-id="f7cae-149">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="f7cae-150">控件</span><span class="sxs-lookup"><span data-stu-id="f7cae-150">Controls</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
