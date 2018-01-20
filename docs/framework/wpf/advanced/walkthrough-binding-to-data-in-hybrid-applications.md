---
title: "演练：绑定到混合应用程序中的数据"
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
- hybrid applications [WPF interoperability]
- data binding [WPF interoperability]
ms.assetid: 18997e71-745a-4425-9c69-2cbce1d8669e
caps.latest.revision: "39"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c1348f3a57dd04d58298c9746b74a7c3a1baf30c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-binding-to-data-in-hybrid-applications"></a><span data-ttu-id="8413a-102">演练：绑定到混合应用程序中的数据</span><span class="sxs-lookup"><span data-stu-id="8413a-102">Walkthrough: Binding to Data in Hybrid Applications</span></span>
<span data-ttu-id="8413a-103">将数据源绑定到控件而言至关重要向用户提供访问基础数据，无论使用[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]或[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8413a-103">Binding a data source to a control is essential for providing users with access to underlying data, whether you are using [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] or [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="8413a-104">本演练演示如何同时包含这两者的混合应用程序中使用数据绑定[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]和[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]控件。</span><span class="sxs-lookup"><span data-stu-id="8413a-104">This walkthrough shows how you can use data binding in hybrid applications that include both [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controls.</span></span>  
  
 <span data-ttu-id="8413a-105">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="8413a-105">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="8413a-106">创建项目。</span><span class="sxs-lookup"><span data-stu-id="8413a-106">Creating the project.</span></span>  
  
-   <span data-ttu-id="8413a-107">定义数据模板。</span><span class="sxs-lookup"><span data-stu-id="8413a-107">Defining the data template.</span></span>  
  
-   <span data-ttu-id="8413a-108">指定窗体布局。</span><span class="sxs-lookup"><span data-stu-id="8413a-108">Specifying the form layout.</span></span>  
  
-   <span data-ttu-id="8413a-109">指定数据绑定。</span><span class="sxs-lookup"><span data-stu-id="8413a-109">Specifying data bindings.</span></span>  
  
-   <span data-ttu-id="8413a-110">使用互操作功能显示数据。</span><span class="sxs-lookup"><span data-stu-id="8413a-110">Displaying data by using interoperation.</span></span>  
  
-   <span data-ttu-id="8413a-111">向项目添加数据源。</span><span class="sxs-lookup"><span data-stu-id="8413a-111">Adding the data source to the project.</span></span>  
  
-   <span data-ttu-id="8413a-112">绑定到数据源。</span><span class="sxs-lookup"><span data-stu-id="8413a-112">Binding to the data source.</span></span>  
  
 <span data-ttu-id="8413a-113">本演练的任务的完整代码清单，请参阅[混合应用程序示例中的数据绑定](http://go.microsoft.com/fwlink/?LinkID=159983)。</span><span class="sxs-lookup"><span data-stu-id="8413a-113">For a complete code listing of the tasks illustrated in this walkthrough, see [Data Binding in Hybrid Applications Sample](http://go.microsoft.com/fwlink/?LinkID=159983).</span></span>  
  
 <span data-ttu-id="8413a-114">完成本演练后，你将对混合应用程序中的数据绑定功能有所了解。</span><span class="sxs-lookup"><span data-stu-id="8413a-114">When you are finished, you will have an understanding of data binding features in hybrid applications.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8413a-115">系统必备</span><span class="sxs-lookup"><span data-stu-id="8413a-115">Prerequisites</span></span>  
 <span data-ttu-id="8413a-116">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="8413a-116">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="8413a-117">。</span><span class="sxs-lookup"><span data-stu-id="8413a-117">.</span></span>  
  
-   <span data-ttu-id="8413a-118">包含到 Northwind 示例数据库运行在 Microsoft SQL Server 上的访问。</span><span class="sxs-lookup"><span data-stu-id="8413a-118">Access to the Northwind sample database running on Microsoft SQL Server.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="8413a-119">创建项目</span><span class="sxs-lookup"><span data-stu-id="8413a-119">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="8413a-120">创建并设置项目</span><span class="sxs-lookup"><span data-stu-id="8413a-120">To create and set up the project</span></span>  
  
1.  <span data-ttu-id="8413a-121">创建一个名为的 WPF 应用程序项目`WPFWithWFAndDatabinding`。</span><span class="sxs-lookup"><span data-stu-id="8413a-121">Create a WPF Application project named `WPFWithWFAndDatabinding`.</span></span>  
  
2.  <span data-ttu-id="8413a-122">在解决方案资源管理器中，添加对下列程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="8413a-122">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="8413a-123">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="8413a-123">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="8413a-124">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="8413a-124">System.Windows.Forms</span></span>  
  
3.  <span data-ttu-id="8413a-125">打开在 MainWindow.xaml [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8413a-125">Open MainWindow.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
4.  <span data-ttu-id="8413a-126">在<xref:System.Windows.Window>元素中，添加以下[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]命名空间映射。</span><span class="sxs-lookup"><span data-stu-id="8413a-126">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespaces mapping.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  <span data-ttu-id="8413a-127">将默认值<xref:System.Windows.Controls.Grid>元素`mainGrid`通过分配<xref:System.Windows.FrameworkElement.Name%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="8413a-127">Name the default <xref:System.Windows.Controls.Grid> element `mainGrid` by assigning the <xref:System.Windows.FrameworkElement.Name%2A> property.</span></span>  
  
     [!code-xaml[WPFWithWFAndDatabinding#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]  
  
## <a name="defining-the-data-template"></a><span data-ttu-id="8413a-128">定义数据模板</span><span class="sxs-lookup"><span data-stu-id="8413a-128">Defining the Data Template</span></span>  
 <span data-ttu-id="8413a-129">中显示的客户的主列表<xref:System.Windows.Controls.ListBox>控件。</span><span class="sxs-lookup"><span data-stu-id="8413a-129">The master list of customers is displayed in a <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="8413a-130">下面的代码示例定义<xref:System.Windows.DataTemplate>对象名为`ListItemsTemplate`控制的可视化树<xref:System.Windows.Controls.ListBox>控件。</span><span class="sxs-lookup"><span data-stu-id="8413a-130">The following code example defines a <xref:System.Windows.DataTemplate> object named `ListItemsTemplate` that controls the visual tree of the <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="8413a-131">这<xref:System.Windows.DataTemplate>分配给<xref:System.Windows.Controls.ListBox>控件的<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="8413a-131">This <xref:System.Windows.DataTemplate> is assigned to the <xref:System.Windows.Controls.ListBox> control's <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> property.</span></span>  
  
#### <a name="to-define-the-data-template"></a><span data-ttu-id="8413a-132">定义数据模板</span><span class="sxs-lookup"><span data-stu-id="8413a-132">To define the data template</span></span>  
  
-   <span data-ttu-id="8413a-133">将复制到下面的 XAML<xref:System.Windows.Controls.Grid>元素的声明。</span><span class="sxs-lookup"><span data-stu-id="8413a-133">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>  
  
     [!code-xaml[WPFWithWFAndDatabinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]  
  
## <a name="specifying-the-form-layout"></a><span data-ttu-id="8413a-134">指定窗体布局</span><span class="sxs-lookup"><span data-stu-id="8413a-134">Specifying the Form Layout</span></span>  
 <span data-ttu-id="8413a-135">窗体的布局由一个三行三列的网格来定义。</span><span class="sxs-lookup"><span data-stu-id="8413a-135">The layout of the form is defined by a grid with three rows and three columns.</span></span> <span data-ttu-id="8413a-136"><xref:System.Windows.Controls.Label>控件可用于标识客户表中的每个列。</span><span class="sxs-lookup"><span data-stu-id="8413a-136"><xref:System.Windows.Controls.Label> controls are provided to identify each column in the Customers table.</span></span>  
  
#### <a name="to-set-up-the-grid-layout"></a><span data-ttu-id="8413a-137">设置网格布局</span><span class="sxs-lookup"><span data-stu-id="8413a-137">To set up the Grid layout</span></span>  
  
-   <span data-ttu-id="8413a-138">将复制到下面的 XAML<xref:System.Windows.Controls.Grid>元素的声明。</span><span class="sxs-lookup"><span data-stu-id="8413a-138">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>  
  
     [!code-xaml[WPFWithWFAndDatabinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]  
  
#### <a name="to-set-up-the-label-controls"></a><span data-ttu-id="8413a-139">设置 Label 控件</span><span class="sxs-lookup"><span data-stu-id="8413a-139">To set up the Label controls</span></span>  
  
-   <span data-ttu-id="8413a-140">将复制到下面的 XAML<xref:System.Windows.Controls.Grid>元素的声明。</span><span class="sxs-lookup"><span data-stu-id="8413a-140">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>  
  
     [!code-xaml[WPFWithWFAndDatabinding#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]  
  
## <a name="specifying-data-bindings"></a><span data-ttu-id="8413a-141">指定数据绑定</span><span class="sxs-lookup"><span data-stu-id="8413a-141">Specifying Data Bindings</span></span>  
 <span data-ttu-id="8413a-142">中显示的客户的主列表<xref:System.Windows.Controls.ListBox>控件。</span><span class="sxs-lookup"><span data-stu-id="8413a-142">The master list of customers is displayed in a <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="8413a-143">附加`ListItemsTemplate`将绑定<xref:System.Windows.Controls.TextBlock>控制转移到`ContactName`从数据库字段。</span><span class="sxs-lookup"><span data-stu-id="8413a-143">The attached `ListItemsTemplate` binds a <xref:System.Windows.Controls.TextBlock> control to the `ContactName` field from the database.</span></span>  
  
 <span data-ttu-id="8413a-144">每个客户记录的详细信息显示在多个<xref:System.Windows.Controls.TextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="8413a-144">The details of each customer record are displayed in several <xref:System.Windows.Controls.TextBox> controls.</span></span>  
  
#### <a name="to-specify-data-bindings"></a><span data-ttu-id="8413a-145">指定数据绑定</span><span class="sxs-lookup"><span data-stu-id="8413a-145">To specify data bindings</span></span>  
  
-   <span data-ttu-id="8413a-146">将复制到下面的 XAML<xref:System.Windows.Controls.Grid>元素的声明。</span><span class="sxs-lookup"><span data-stu-id="8413a-146">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>  
  
     <span data-ttu-id="8413a-147"><xref:System.Windows.Data.Binding>类绑定<xref:System.Windows.Controls.TextBox>到数据库中的相应字段的控件。</span><span class="sxs-lookup"><span data-stu-id="8413a-147">The <xref:System.Windows.Data.Binding> class binds the <xref:System.Windows.Controls.TextBox> controls to the appropriate fields in the database.</span></span>  
  
     [!code-xaml[WPFWithWFAndDatabinding#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]  
  
## <a name="displaying-data-by-using-interoperation"></a><span data-ttu-id="8413a-148">使用互操作功能显示数据</span><span class="sxs-lookup"><span data-stu-id="8413a-148">Displaying Data by Using Interoperation</span></span>  
 <span data-ttu-id="8413a-149">对应于所选客户的订单显示在<xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType>控件名为`dataGridView1`。</span><span class="sxs-lookup"><span data-stu-id="8413a-149">The orders corresponding to the selected customer are displayed in a <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> control named `dataGridView1`.</span></span> <span data-ttu-id="8413a-150">`dataGridView1`控件绑定到数据源中的代码隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="8413a-150">The `dataGridView1` control is bound to the data source in the code-behind file.</span></span> <span data-ttu-id="8413a-151">A<xref:System.Windows.Forms.Integration.WindowsFormsHost>控件是此父[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件。</span><span class="sxs-lookup"><span data-stu-id="8413a-151">A <xref:System.Windows.Forms.Integration.WindowsFormsHost> control is the parent of this [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
#### <a name="to-display-data-in-the-datagridview-control"></a><span data-ttu-id="8413a-152">在 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="8413a-152">To display data in the DataGridView control</span></span>  
  
-   <span data-ttu-id="8413a-153">将复制到下面的 XAML<xref:System.Windows.Controls.Grid>元素的声明。</span><span class="sxs-lookup"><span data-stu-id="8413a-153">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>  
  
     [!code-xaml[WPFWithWFAndDatabinding#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]  
  
## <a name="adding-the-data-source-to-the-project"></a><span data-ttu-id="8413a-154">向项目添加数据源</span><span class="sxs-lookup"><span data-stu-id="8413a-154">Adding the Data Source to the Project</span></span>  
 <span data-ttu-id="8413a-155">与[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]，你可以轻松添加到你的项目的数据源。</span><span class="sxs-lookup"><span data-stu-id="8413a-155">With [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], you can easily add a data source to your project.</span></span> <span data-ttu-id="8413a-156">此过程将向项目添加强类型数据集。</span><span class="sxs-lookup"><span data-stu-id="8413a-156">This procedure adds a strongly typed data set to your project.</span></span> <span data-ttu-id="8413a-157">还添加了其他支持类，例如每个所选表适用的表适配器。</span><span class="sxs-lookup"><span data-stu-id="8413a-157">Several other support classes, such as table adapters for each of the chosen tables, are also added.</span></span>  
  
#### <a name="to-add-the-data-source"></a><span data-ttu-id="8413a-158">添加数据源</span><span class="sxs-lookup"><span data-stu-id="8413a-158">To add the data source</span></span>  
  
1.  <span data-ttu-id="8413a-159">从**数据**菜单上，选择**添加新数据源**。</span><span class="sxs-lookup"><span data-stu-id="8413a-159">From the **Data** menu, select **Add New Data Source**.</span></span>  
  
2.  <span data-ttu-id="8413a-160">在**数据源配置向导**，通过使用数据集创建到 Northwind 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="8413a-160">In the **Data Source Configuration Wizard**, create a connection to the Northwind database by using a dataset.</span></span> <span data-ttu-id="8413a-161">有关详细信息，请参阅[如何： 连接到数据库中的数据](http://msdn.microsoft.com/library/6c56e54e-8834-4297-85aa-cc1a443ba556)。</span><span class="sxs-lookup"><span data-stu-id="8413a-161">For more information, see [How to: Connect to Data in a Database](http://msdn.microsoft.com/library/6c56e54e-8834-4297-85aa-cc1a443ba556).</span></span>  
  
3.  <span data-ttu-id="8413a-162">在提示你时通过**数据源配置向导**，保存连接字符串作为`NorthwindConnectionString`。</span><span class="sxs-lookup"><span data-stu-id="8413a-162">When you are prompted by the **Data Source Configuration Wizard**, save the connection string as `NorthwindConnectionString`.</span></span>  
  
4.  <span data-ttu-id="8413a-163">当系统提示你选择数据库对象时，选择`Customers`和`Orders`表和名称生成的数据集`NorthwindDataSet`。</span><span class="sxs-lookup"><span data-stu-id="8413a-163">When you are prompted to choose your database objects, select the `Customers` and `Orders` tables, and name the generated data set `NorthwindDataSet`.</span></span>  
  
## <a name="binding-to-the-data-source"></a><span data-ttu-id="8413a-164">绑定到数据源</span><span class="sxs-lookup"><span data-stu-id="8413a-164">Binding to the Data Source</span></span>  
 <span data-ttu-id="8413a-165"><xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType>组件提供统一的接口，用于应用程序的数据源。</span><span class="sxs-lookup"><span data-stu-id="8413a-165">The <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> component provides a uniform interface for the application's data source.</span></span> <span data-ttu-id="8413a-166">绑定到数据源是在代码隐藏文件中实现的。</span><span class="sxs-lookup"><span data-stu-id="8413a-166">Binding to the data source is implemented in the code-behind file.</span></span>  
  
#### <a name="to-bind-to-the-data-source"></a><span data-ttu-id="8413a-167">绑定到数据源</span><span class="sxs-lookup"><span data-stu-id="8413a-167">To bind to the data source</span></span>  
  
1.  <span data-ttu-id="8413a-168">打开名为 MainWindow.xaml.vb 或 MainWindow.xaml.cs 的代码隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="8413a-168">Open the code-behind file, which is named MainWindow.xaml.vb or MainWindow.xaml.cs.</span></span>  
  
2.  <span data-ttu-id="8413a-169">下面的代码复制到`MainWindow`类定义。</span><span class="sxs-lookup"><span data-stu-id="8413a-169">Copy the following code into the `MainWindow` class definition.</span></span>  
  
     <span data-ttu-id="8413a-170">此代码声明<xref:System.Windows.Forms.BindingSource>组件和连接到数据库的关联的帮助程序类。</span><span class="sxs-lookup"><span data-stu-id="8413a-170">This code declares the <xref:System.Windows.Forms.BindingSource> component and associated helper classes that connect to the database.</span></span>  
  
     [!code-csharp[WPFWithWFAndDatabinding#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]  
  
3.  <span data-ttu-id="8413a-171">将以下代码复制到构造函数中。</span><span class="sxs-lookup"><span data-stu-id="8413a-171">Copy the following code into the constructor.</span></span>  
  
     <span data-ttu-id="8413a-172">此代码创建并初始化<xref:System.Windows.Forms.BindingSource>组件。</span><span class="sxs-lookup"><span data-stu-id="8413a-172">This code creates and initializes the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
     [!code-csharp[WPFWithWFAndDatabinding#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]  
  
4.  <span data-ttu-id="8413a-173">打开 MainWindow.xaml。</span><span class="sxs-lookup"><span data-stu-id="8413a-173">Open MainWindow.xaml.</span></span>  
  
5.  <span data-ttu-id="8413a-174">在设计视图或 XAML 视图中，选择<xref:System.Windows.Window>元素。</span><span class="sxs-lookup"><span data-stu-id="8413a-174">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>  
  
6.  <span data-ttu-id="8413a-175">在属性窗口中，单击**事件**选项卡。</span><span class="sxs-lookup"><span data-stu-id="8413a-175">In the Properties window, click the **Events** tab.</span></span>  
  
7.  <span data-ttu-id="8413a-176">双击<xref:System.Windows.FrameworkElement.Loaded>事件。</span><span class="sxs-lookup"><span data-stu-id="8413a-176">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
8.  <span data-ttu-id="8413a-177">下面的代码复制到<xref:System.Windows.FrameworkElement.Loaded>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="8413a-177">Copy the following code into the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>  
  
     <span data-ttu-id="8413a-178">此代码将分配<xref:System.Windows.Forms.BindingSource>组件作为数据上下文，并填充`Customers`和`Orders`适配器对象。</span><span class="sxs-lookup"><span data-stu-id="8413a-178">This code assigns the <xref:System.Windows.Forms.BindingSource> component as the data context and populates the `Customers` and `Orders` adapter objects.</span></span>  
  
     [!code-csharp[WPFWithWFAndDatabinding#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]  
  
9. <span data-ttu-id="8413a-179">下面的代码复制到`MainWindow`类定义。</span><span class="sxs-lookup"><span data-stu-id="8413a-179">Copy the following code into the `MainWindow` class definition.</span></span>  
  
     <span data-ttu-id="8413a-180">此方法可处理<xref:System.Windows.Data.CollectionView.CurrentChanged>事件并更新数据绑定的当前项。</span><span class="sxs-lookup"><span data-stu-id="8413a-180">This method handles the <xref:System.Windows.Data.CollectionView.CurrentChanged> event and updates the current item of the data binding.</span></span>  
  
     [!code-csharp[WPFWithWFAndDatabinding#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]  
  
10. <span data-ttu-id="8413a-181">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="8413a-181">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8413a-182">请参阅</span><span class="sxs-lookup"><span data-stu-id="8413a-182">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="8413a-183">WPF 设计器</span><span class="sxs-lookup"><span data-stu-id="8413a-183">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="8413a-184">混合应用程序示例中的数据绑定</span><span class="sxs-lookup"><span data-stu-id="8413a-184">Data Binding in Hybrid Applications Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159983)  
 [<span data-ttu-id="8413a-185">演练：在 WPF 中托管 Windows 窗体复合控件</span><span class="sxs-lookup"><span data-stu-id="8413a-185">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="8413a-186">演练：在 Windows 窗体中承载 WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="8413a-186">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
