---
title: 演练：在 DataGrid 控件中显示 SQL Server 数据库中的数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], displaying data from SQL Server
- controls [WPF], DataGrid
ms.assetid: 6810b048-0a23-4f86-bfa5-97f92b3cfab4
ms.openlocfilehash: fc8b35c89e76a415529d76db687bc96767384e11
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452118"
---
# <a name="walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control"></a><span data-ttu-id="a7963-102">演练：在 DataGrid 控件中显示 SQL Server 数据库中的数据</span><span class="sxs-lookup"><span data-stu-id="a7963-102">Walkthrough: Display data from a SQL Server database in a DataGrid control</span></span>

<span data-ttu-id="a7963-103">在本演练中，您将从 SQL Server 数据库中检索数据，并在 <xref:System.Windows.Controls.DataGrid> 控件中显示该数据。</span><span class="sxs-lookup"><span data-stu-id="a7963-103">In this walkthrough, you retrieve data from a SQL Server database and display that data in a <xref:System.Windows.Controls.DataGrid> control.</span></span> <span data-ttu-id="a7963-104">使用 ADO.NET 实体框架创建表示数据的实体类，并使用 LINQ 编写从实体类中检索指定数据的查询。</span><span class="sxs-lookup"><span data-stu-id="a7963-104">You use the ADO.NET Entity Framework to create the entity classes that represent the data, and use LINQ to write a query that retrieves the specified data from an entity class.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a7963-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="a7963-105">Prerequisites</span></span>

<span data-ttu-id="a7963-106">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="a7963-106">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="a7963-107">Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="a7963-107">Visual Studio.</span></span>

- <span data-ttu-id="a7963-108">访问附加了 AdventureWorks 示例数据库的 SQL Server 或 SQL Server Express 的正在运行的实例。</span><span class="sxs-lookup"><span data-stu-id="a7963-108">Access to a running instance of SQL Server or SQL Server Express that has the AdventureWorks sample database attached to it.</span></span> <span data-ttu-id="a7963-109">可以从[GitHub](https://github.com/Microsoft/sql-server-samples/releases)下载 AdventureWorks 数据库。</span><span class="sxs-lookup"><span data-stu-id="a7963-109">You can download the AdventureWorks database from the [GitHub](https://github.com/Microsoft/sql-server-samples/releases).</span></span>

## <a name="create-entity-classes"></a><span data-ttu-id="a7963-110">创建实体类</span><span class="sxs-lookup"><span data-stu-id="a7963-110">Create entity classes</span></span>

1. <span data-ttu-id="a7963-111">在 Visual Basic 或C#中创建新的 WPF 应用程序项目，并将其命名为 `DataGridSQLExample`。</span><span class="sxs-lookup"><span data-stu-id="a7963-111">Create a new WPF Application project in Visual Basic or C#, and name it `DataGridSQLExample`.</span></span>

2. <span data-ttu-id="a7963-112">在解决方案资源管理器中，右键单击项目，指向 "**添加**"，然后选择 "**新建项**"。</span><span class="sxs-lookup"><span data-stu-id="a7963-112">In Solution Explorer, right-click your project, point to **Add**, and then select **New Item**.</span></span>

     <span data-ttu-id="a7963-113">将显示“添加新项”对话框。</span><span class="sxs-lookup"><span data-stu-id="a7963-113">The Add New Item dialog box appears.</span></span>

3. <span data-ttu-id="a7963-114">在 "已安装的模板" 窗格中，选择 "**数据**"，然后在模板列表中，选择 " **ADO.NET 实体数据模型**"。</span><span class="sxs-lookup"><span data-stu-id="a7963-114">In the Installed Templates pane, select **Data** and in the list of templates, select **ADO.NET Entity Data Model**.</span></span>

     ![ADO.NET 实体数据模型项模板](../../wcf/feature-details/./media/ado-net-entity-data-model-item-template.png)

4. <span data-ttu-id="a7963-116">将该文件命名 `AdventureWorksModel.edmx` 然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="a7963-116">Name the file `AdventureWorksModel.edmx` and then click **Add**.</span></span>

     <span data-ttu-id="a7963-117">此时将出现“实体数据模型向导”。</span><span class="sxs-lookup"><span data-stu-id="a7963-117">The Entity Data Model Wizard appears.</span></span>

5. <span data-ttu-id="a7963-118">在 "选择模型内容" 屏幕上，**从数据库中选择 EF 设计器**，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a7963-118">In the Choose Model Contents screen, select **EF Designer from database** and then click **Next**.</span></span>

6. <span data-ttu-id="a7963-119">在 "选择你的数据连接" 屏幕中，提供与 AdventureWorksLT2008 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="a7963-119">In the Choose Your Data Connection screen, provide the connection to your AdventureWorksLT2008 database.</span></span> <span data-ttu-id="a7963-120">有关详细信息，请参阅 "[选择您的数据连接" 对话框](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399244(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="a7963-120">For more information, see [Choose Your Data Connection Dialog Box](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399244(v=vs.100)).</span></span>

    <span data-ttu-id="a7963-121">请确保名称为 "`AdventureWorksLT2008Entities`"，并选中 "将 app.config**中的实体连接设置另存为**" 复选框，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a7963-121">Make sure that the name is `AdventureWorksLT2008Entities` and that the **Save entity connection settings in App.Config as** check box is selected, and then click **Next**.</span></span>

7. <span data-ttu-id="a7963-122">在 "选择数据库对象" 屏幕上，展开 "表" 节点，然后选择 " **Product** " 和 " **ProductCategory** " 表。</span><span class="sxs-lookup"><span data-stu-id="a7963-122">In the Choose Your Database Objects screen, expand the Tables node, and select the **Product** and **ProductCategory** tables.</span></span>

     <span data-ttu-id="a7963-123">您可以为所有表生成实体类;但是，在此示例中，只检索这两个表中的数据。</span><span class="sxs-lookup"><span data-stu-id="a7963-123">You can generate entity classes for all of the tables; however, in this example you only retrieve data from those two tables.</span></span>

     <span data-ttu-id="a7963-124">![从表中选择 Product and ProductCategory](./media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")</span><span class="sxs-lookup"><span data-stu-id="a7963-124">![Select Product and ProductCategory from tables](./media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")</span></span>

8. <span data-ttu-id="a7963-125">单击 **“完成”** 。</span><span class="sxs-lookup"><span data-stu-id="a7963-125">Click **Finish**.</span></span>

     <span data-ttu-id="a7963-126">"产品" 和 "ProductCategory" 实体将显示在 Entity Designer 中。</span><span class="sxs-lookup"><span data-stu-id="a7963-126">The Product and ProductCategory entities are displayed in the Entity Designer.</span></span>

     <span data-ttu-id="a7963-127">![Product 和 ProductCategory 实体模型](./media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")</span><span class="sxs-lookup"><span data-stu-id="a7963-127">![Product and ProductCategory entity models](./media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")</span></span>

## <a name="retrieve-and-present-the-data"></a><span data-ttu-id="a7963-128">检索和显示数据</span><span class="sxs-lookup"><span data-stu-id="a7963-128">Retrieve and present the data</span></span>

1. <span data-ttu-id="a7963-129">打开 Mainwindow.xaml 文件。</span><span class="sxs-lookup"><span data-stu-id="a7963-129">Open the MainWindow.xaml file.</span></span>

2. <span data-ttu-id="a7963-130">将 <xref:System.Windows.Window> 上的 <xref:System.Windows.FrameworkElement.Width%2A> 属性设置为450。</span><span class="sxs-lookup"><span data-stu-id="a7963-130">Set the <xref:System.Windows.FrameworkElement.Width%2A> property on the <xref:System.Windows.Window> to 450.</span></span>

3. <span data-ttu-id="a7963-131">在 XAML 编辑器中，在 `<Grid>` 和 `</Grid>` 标记之间添加以下 <xref:System.Windows.Controls.DataGrid> 标记，以添加名为 `dataGrid1`的 <xref:System.Windows.Controls.DataGrid>。</span><span class="sxs-lookup"><span data-stu-id="a7963-131">In the XAML editor, add the following <xref:System.Windows.Controls.DataGrid> tag between the `<Grid>` and `</Grid>` tags to add a <xref:System.Windows.Controls.DataGrid> named `dataGrid1`.</span></span>

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#3)]

     <span data-ttu-id="a7963-132">![带 DataGrid 的窗口](./media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")</span><span class="sxs-lookup"><span data-stu-id="a7963-132">![Window with DataGrid](./media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")</span></span>

4. <span data-ttu-id="a7963-133">选择 <xref:System.Windows.Window>。</span><span class="sxs-lookup"><span data-stu-id="a7963-133">Select the <xref:System.Windows.Window>.</span></span>

5. <span data-ttu-id="a7963-134">使用属性窗口或 XAML 编辑器，为 <xref:System.Windows.FrameworkElement.Loaded> 事件的名为 `Window_Loaded` 的 <xref:System.Windows.Window> 创建事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="a7963-134">Using the Properties window or XAML editor, create an event handler for the <xref:System.Windows.Window> named `Window_Loaded` for the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span> <span data-ttu-id="a7963-135">有关详细信息，请参阅[如何：创建简单的事件处理程序](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="a7963-135">For more information, see [How to: Create a Simple Event Handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

     <span data-ttu-id="a7963-136">下面显示了 Mainwindow.xaml 的 XAML。</span><span class="sxs-lookup"><span data-stu-id="a7963-136">The following shows the XAML for MainWindow.xaml.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a7963-137">如果使用 Visual Basic，请在 Mainwindow.xaml 的第一行中，用 `x:Class="MainWindow"`替换 `x:Class="DataGridSQLExample.MainWindow"`。</span><span class="sxs-lookup"><span data-stu-id="a7963-137">If you are using Visual Basic, in the first line of MainWindow.xaml, replace `x:Class="DataGridSQLExample.MainWindow"` with `x:Class="MainWindow"`.</span></span>

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#1)]

6. <span data-ttu-id="a7963-138">打开 <xref:System.Windows.Window>的代码隐藏文件（Mainwindow.xaml 或 MainWindow.xaml.cs）。</span><span class="sxs-lookup"><span data-stu-id="a7963-138">Open the code-behind file (MainWindow.xaml.vb or MainWindow.xaml.cs) for the <xref:System.Windows.Window>.</span></span>

7. <span data-ttu-id="a7963-139">添加以下代码以仅检索联接的表中的特定值，并将 <xref:System.Windows.Controls.DataGrid> 的 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 属性设置为查询结果。</span><span class="sxs-lookup"><span data-stu-id="a7963-139">Add the following code to retrieve only specific values from the joined tables and set the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.DataGrid> to the results of the query.</span></span>

     [!code-csharp[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml.cs#2)]
     [!code-vb[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/VB/MainWindow.xaml.vb#2)]

8. <span data-ttu-id="a7963-140">运行示例。</span><span class="sxs-lookup"><span data-stu-id="a7963-140">Run the example.</span></span>

     <span data-ttu-id="a7963-141">应该会看到显示数据的 <xref:System.Windows.Controls.DataGrid>。</span><span class="sxs-lookup"><span data-stu-id="a7963-141">You should see a <xref:System.Windows.Controls.DataGrid> that displays data.</span></span>

     <span data-ttu-id="a7963-142">![包含来自 SQL 数据库的数据的 DataGrid](./media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")</span><span class="sxs-lookup"><span data-stu-id="a7963-142">![DataGrid with data from SQL database](./media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")</span></span>

## <a name="see-also"></a><span data-ttu-id="a7963-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7963-143">See also</span></span>

- <xref:System.Windows.Controls.DataGrid>
