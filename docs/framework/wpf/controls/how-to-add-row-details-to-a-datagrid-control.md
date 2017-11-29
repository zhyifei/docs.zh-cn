---
title: "如何：向 DataGrid 控件中添加行详细信息"
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
- DataTemplate [WPF], DataGrid
- row details [WPF], DataGrid
- DataGrid [WPF], row details
ms.assetid: 0bdc6f50-9b4c-483f-9df6-a47a1fde998b
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 036e06d110df8900ab46f0d501f30b4a163c8eb9
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-add-row-details-to-a-datagrid-control"></a><span data-ttu-id="c6b3a-102">如何：向 DataGrid 控件中添加行详细信息</span><span class="sxs-lookup"><span data-stu-id="c6b3a-102">How to: Add Row Details to a DataGrid Control</span></span>
<span data-ttu-id="c6b3a-103">使用时<xref:System.Windows.Controls.DataGrid>控件，你可以自定义数据表示通过添加行详细信息部分。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-103">When using the <xref:System.Windows.Controls.DataGrid> control, you can customize the data presentation by adding a row details section.</span></span> <span data-ttu-id="c6b3a-104">添加行详细信息部分，可根据需要可见还是折叠的模板中的某些数据进行分组。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-104">Adding a row details section enables you to group some data in a template that is optionally visible or collapsed.</span></span> <span data-ttu-id="c6b3a-105">例如，你可以添加行详细信息，以便<xref:System.Windows.Controls.DataGrid>这将显示仅用于中的每一行的数据的摘要<xref:System.Windows.Controls.DataGrid>，但当用户选择某一行显示更多数据字段。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-105">For example, you can add row details to a <xref:System.Windows.Controls.DataGrid> that presents only a summary of the data for each row in the <xref:System.Windows.Controls.DataGrid>, but presents more data fields when the user selects a row.</span></span> <span data-ttu-id="c6b3a-106">定义行详细信息部分中的模板<xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-106">You define the template for the row details section in the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property.</span></span> <span data-ttu-id="c6b3a-107">下图显示行详细信息部分的示例。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-107">The following illustration shows an example of a row details section.</span></span>  
  
 <span data-ttu-id="c6b3a-108">![显示与行详细信息的 DataGrid](../../../../docs/framework/wpf/controls/media/ndp-rowdetails.png "NDP_RowDetails")</span><span class="sxs-lookup"><span data-stu-id="c6b3a-108">![DataGrid shown with row details](../../../../docs/framework/wpf/controls/media/ndp-rowdetails.png "NDP_RowDetails")</span></span>  
  
 <span data-ttu-id="c6b3a-109">为任一内联 XAML 或作为资源定义行详细信息模板。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-109">You define the row details template as either inline XAML or as a resource.</span></span> <span data-ttu-id="c6b3a-110">这两种方法的以下过程所示。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-110">Both approaches are shown in the following procedures.</span></span> <span data-ttu-id="c6b3a-111">可以在整个项目能使用作为资源添加的数据模板，而无需重新创建模板。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-111">A data template that is added as a resource can be used throughout the project without re-creating the template.</span></span> <span data-ttu-id="c6b3a-112">添加，如内联 XAML，才可以访问从控件定义数据模板。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-112">A data template that is added as inline XAML is only accessible from the control where it is defined.</span></span>  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a><span data-ttu-id="c6b3a-113">若要使用内联 XAML 显示行详细信息</span><span class="sxs-lookup"><span data-stu-id="c6b3a-113">To display row details by using inline XAML</span></span>  
  
1.  <span data-ttu-id="c6b3a-114">创建<xref:System.Windows.Controls.DataGrid>显示来自数据源的数据。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-114">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2.  <span data-ttu-id="c6b3a-115">在 <xref:System.Windows.Controls.DataGrid> 元素内，添加一个 <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> 元素。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-115">In the <xref:System.Windows.Controls.DataGrid> element, add a <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> element.</span></span>  
  
3.  <span data-ttu-id="c6b3a-116">创建<xref:System.Windows.DataTemplate>定义行详细信息部分的外观。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-116">Create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="c6b3a-117">下面的 XAML 演示<xref:System.Windows.Controls.DataGrid>以及如何定义<xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>内联。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-117">The following XAML shows the <xref:System.Windows.Controls.DataGrid> and how to define the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> inline.</span></span> <span data-ttu-id="c6b3a-118"><xref:System.Windows.Controls.DataGrid>显示三个值中的每一行和第三个更多的值选择的行时。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-118">The <xref:System.Windows.Controls.DataGrid> displays three values in each row and three more values when the row is selected.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     <span data-ttu-id="c6b3a-119">下面的代码演示用于选择中显示的数据的查询<xref:System.Windows.Controls.DataGrid>。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-119">The following code shows the query that is used to select the data that is displayed in the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="c6b3a-120">在此示例中，查询从包含客户信息的实体中选择数据。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-120">In this example, the query selects data from an entity that contains customer information.</span></span>  
  
     [!code-csharp[DataGrid_RowDetails#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a><span data-ttu-id="c6b3a-121">若要使用的资源显示行详细信息</span><span class="sxs-lookup"><span data-stu-id="c6b3a-121">To display row details by using a resource</span></span>  
  
1.  <span data-ttu-id="c6b3a-122">创建<xref:System.Windows.Controls.DataGrid>显示来自数据源的数据。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-122">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2.  <span data-ttu-id="c6b3a-123">添加<xref:System.Windows.FrameworkElement.Resources%2A>元素到根元素，如<xref:System.Windows.Window>控件或<xref:System.Windows.Controls.Page>控制，或添加<xref:System.Windows.Application.Resources%2A>元素<xref:System.Windows.Application>App.xaml （或 Application.xaml） 文件中的类。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-123">Add a <xref:System.Windows.FrameworkElement.Resources%2A> element to the root element, such as a <xref:System.Windows.Window> control or a <xref:System.Windows.Controls.Page> control, or add a <xref:System.Windows.Application.Resources%2A> element to the <xref:System.Windows.Application> class in the App.xaml (or Application.xaml) file.</span></span>  
  
3.  <span data-ttu-id="c6b3a-124">在资源元素中，创建<xref:System.Windows.DataTemplate>定义行详细信息部分的外观。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-124">In the resources element, create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="c6b3a-125">下面的 XAML 演示<xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>中定义<xref:System.Windows.Application>类。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-125">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> defined in the <xref:System.Windows.Application> class.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4.  <span data-ttu-id="c6b3a-126">上<xref:System.Windows.DataTemplate>，将其设置[X:key 指令](../../../../docs/framework/xaml-services/x-key-directive.md)为唯一标识数据模板的值。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-126">On the <xref:System.Windows.DataTemplate>, set the [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md) to a value that uniquely identifies the data template.</span></span>  
  
5.  <span data-ttu-id="c6b3a-127">在<xref:System.Windows.Controls.DataGrid>元素，设置<xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>属性设置为前面步骤中定义的资源。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-127">In the <xref:System.Windows.Controls.DataGrid> element, set the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property to the resource defined in the previous steps.</span></span> <span data-ttu-id="c6b3a-128">将资源分配为静态资源。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-128">Assign the resource as a static resource.</span></span>  
  
     <span data-ttu-id="c6b3a-129">下面的 XAML 演示<xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>属性设置为资源从前面的示例。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-129">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property set to the resource from the previous example.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a><span data-ttu-id="c6b3a-130">若要设置可见性，并且允许水平滚动的行详细信息</span><span class="sxs-lookup"><span data-stu-id="c6b3a-130">To set visibility and prevent horizontal scrolling for row details</span></span>  
  
1.  <span data-ttu-id="c6b3a-131">如果需要设置<xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A>属性<xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode>值。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-131">If needed, set the <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> property to a <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> value.</span></span>  
  
     <span data-ttu-id="c6b3a-132">默认情况下，值设置为<xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-132">By default, the value is set to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>.</span></span> <span data-ttu-id="c6b3a-133">你可以将其设置为<xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible>以显示的所有行的详细信息或<xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed>隐藏所有行的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-133">You can set it to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> to show the details for all of the rows or <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> to hide the details for all rows.</span></span>  
  
2.  <span data-ttu-id="c6b3a-134">如果需要设置<xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A>属性`true`禁止行详细信息中水平滚动的部分。</span><span class="sxs-lookup"><span data-stu-id="c6b3a-134">If needed, set the <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> property to `true` to prevent the row details section from scrolling horizontally.</span></span>
