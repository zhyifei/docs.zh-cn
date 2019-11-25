---
title: 创建 .NET Framework 客户端应用程序（WCF 数据服务快速入门）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 41ade767-eeab-437d-9121-9797e8fb8045
ms.openlocfilehash: 4beaba24e42b15ebc45ece6e5319a2b14df54ab6
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975383"
---
# <a name="creating-the-net-framework-client-application-wcf-data-services-quickstart"></a><span data-ttu-id="7f215-102">创建 .NET Framework 客户端应用程序（WCF 数据服务快速入门）</span><span class="sxs-lookup"><span data-stu-id="7f215-102">Creating the .NET Framework Client Application (WCF Data Services Quickstart)</span></span>

<span data-ttu-id="7f215-103">这是 WCF 数据服务快速入门的最后一任务。</span><span class="sxs-lookup"><span data-stu-id="7f215-103">This is the final task of the WCF Data Services quickstart.</span></span> <span data-ttu-id="7f215-104">在此任务中，你将向解决方案添加一个控制台应用程序，将对 Open Data Protocol （OData）源的引用添加到此新的客户端应用程序，并使用生成的客户端数据服务类和客户端从客户端应用程序访问 OData 源库.</span><span class="sxs-lookup"><span data-stu-id="7f215-104">In this task, you will add a console application to the solution, add a reference to the Open Data Protocol (OData) feed into this new client application, and access the OData feed from the client application by using the generated client data service classes and client libraries.</span></span>

> [!NOTE]
> <span data-ttu-id="7f215-105">访问数据源不需要基于 .NET Framework 的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="7f215-105">A .NET Framework-based client application is not required to access a data feed.</span></span> <span data-ttu-id="7f215-106">使用 OData 源的任何应用程序组件都可以访问该数据服务。</span><span class="sxs-lookup"><span data-stu-id="7f215-106">The data service can be accessed by any application component that consumes an OData feed.</span></span> <span data-ttu-id="7f215-107">有关详细信息，请参阅[在客户端应用程序中使用数据服务](using-a-data-service-in-a-client-application-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="7f215-107">For more information, see [Using a Data Service in a Client Application](using-a-data-service-in-a-client-application-wcf-data-services.md).</span></span>

## <a name="to-create-the-client-application-by-using-visual-studio"></a><span data-ttu-id="7f215-108">使用 Visual Studio 创建客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="7f215-108">To create the client application by using Visual Studio</span></span>

1. <span data-ttu-id="7f215-109">在**解决方案资源管理器**中，右键单击解决方案，单击 "**添加**"，然后单击 "**新建项目**"。</span><span class="sxs-lookup"><span data-stu-id="7f215-109">In **Solution Explorer**, right-click the solution, click **Add**, and then click **New Project**.</span></span>

2. <span data-ttu-id="7f215-110">在左窗格中，选择 **"已安装**> [**视觉对象C#** 或**Visual Basic**]" > **Windows 桌面**"，然后选择" **WPF 应用程序**"模板。</span><span class="sxs-lookup"><span data-stu-id="7f215-110">In the left pane, select **Installed** > [**Visual C#** or **Visual Basic**] > **Windows Desktop**, and then select the **WPF App** template.</span></span>

3. <span data-ttu-id="7f215-111">输入项目名称 `NorthwindClient`，然后单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="7f215-111">Enter `NorthwindClient` for the project name, and then click **OK**.</span></span>

4. <span data-ttu-id="7f215-112">打开文件 MainWindow.xaml 并用下列代码替换 XAML 代码：</span><span class="sxs-lookup"><span data-stu-id="7f215-112">Open the file MainWindow.xaml and replace the XAML code with the following code:</span></span>

     [!code-xaml[Astoria Quickstart Client#Window1Xaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml#window1xaml)]

## <a name="to-add-a-data-service-reference-to-the-project"></a><span data-ttu-id="7f215-113">在项目中添加数据服务引用</span><span class="sxs-lookup"><span data-stu-id="7f215-113">To add a data service reference to the project</span></span>

1. <span data-ttu-id="7f215-114">在**解决方案资源管理器**中，右键单击 NorthwindClient 项目，单击 "**添加** > **服务引用**"，然后单击 "**发现**"。</span><span class="sxs-lookup"><span data-stu-id="7f215-114">In **Solution Explorer**, right-click the NorthwindClient project, click **Add** > **Service Reference**, and then click **Discover**.</span></span>

     <span data-ttu-id="7f215-115">这将显示在第一个任务中创建的 Northwind 数据服务。</span><span class="sxs-lookup"><span data-stu-id="7f215-115">This displays the Northwind data service that you created in the first task.</span></span>

2. <span data-ttu-id="7f215-116">在 "**命名空间**" 文本框中，键入 `Northwind`，然后单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="7f215-116">In the **Namespace** text box, type `Northwind`, and then click **OK**.</span></span>

     <span data-ttu-id="7f215-117">这将在项目中添加一个新的代码文件，其中包含用于作为对象访问数据服务资源并与其交互的数据类。</span><span class="sxs-lookup"><span data-stu-id="7f215-117">This adds a new code file to the project, which contains the data classes that are used to access and interact with data service resources as objects.</span></span> <span data-ttu-id="7f215-118">这些数据类是在命名空间 `NorthwindClient.Northwind` 中创建的。</span><span class="sxs-lookup"><span data-stu-id="7f215-118">The data classes are created in the namespace `NorthwindClient.Northwind`.</span></span>

## <a name="to-access-data-service-data-in-the-wpf-application"></a><span data-ttu-id="7f215-119">在 WPF 应用程序中访问数据服务数据</span><span class="sxs-lookup"><span data-stu-id="7f215-119">To access data service data in the WPF application</span></span>

1. <span data-ttu-id="7f215-120">在 " **NorthwindClient**" 下的 "**解决方案资源管理器**中，右键单击项目，然后单击"**添加引用**"。</span><span class="sxs-lookup"><span data-stu-id="7f215-120">In **Solution Explorer** under **NorthwindClient**, right-click the project and click **Add Reference**.</span></span>

2. <span data-ttu-id="7f215-121">在 "**添加引用**" 对话框中，单击 " **.net** " 选项卡，选择 ""，然后单击 **"确定**"。</span><span class="sxs-lookup"><span data-stu-id="7f215-121">In the **Add Reference** dialog box, click the **.NET** tab, select the System.Data.Services.Client.dll assembly, and then click **OK**.</span></span>

3. <span data-ttu-id="7f215-122">在 " **NorthwindClient**" 下的 "**解决方案资源管理器**中，打开 mainwindow.xaml 文件的代码页，然后添加以下 `using` 语句（`Imports` Visual Basic 中）。</span><span class="sxs-lookup"><span data-stu-id="7f215-122">In **Solution Explorer** under **NorthwindClient**, open the code page for the MainWindow.xaml file, and add the following `using` statement (`Imports` in Visual Basic).</span></span>

    [!code-csharp[Astoria Quickstart Client#Using](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#using)]
    [!code-vb[Astoria Quickstart Client#Using](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#using)]

4. <span data-ttu-id="7f215-123">将用于查询数据服务并将结果绑定到 <xref:System.Data.Services.Client.DataServiceCollection%601> 的下列代码插入到 `MainWindow` 类：</span><span class="sxs-lookup"><span data-stu-id="7f215-123">Insert the following code that queries that data service and binds the result to a <xref:System.Data.Services.Client.DataServiceCollection%601> into the `MainWindow` class:</span></span>

    > [!NOTE]
    > <span data-ttu-id="7f215-124">必须用承载 Northwind 数据服务的实例的服务器和端口替换主机名 `localhost:12345`。</span><span class="sxs-lookup"><span data-stu-id="7f215-124">You must replace the host name `localhost:12345` with the server and port that is hosting your instance of the Northwind data service.</span></span>

     [!code-csharp[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#querycode)]
     [!code-vb[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#querycode)]

5. <span data-ttu-id="7f215-125">将用于保存更改的下列代码插入到 `MainWindow` 类：</span><span class="sxs-lookup"><span data-stu-id="7f215-125">Insert the following code that saves changes into the `MainWindow` class:</span></span>

     [!code-csharp[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#savechanges)]
     [!code-vb[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#savechanges)]

## <a name="to-build-and-run-the-northwindclient-application"></a><span data-ttu-id="7f215-126">生成并运行 NorthwindClient 应用程序</span><span class="sxs-lookup"><span data-stu-id="7f215-126">To build and run the NorthwindClient application</span></span>

1. <span data-ttu-id="7f215-127">在**解决方案资源管理器**中，右键单击 NorthwindClient 项目，然后选择 "**设为启动项目**"。</span><span class="sxs-lookup"><span data-stu-id="7f215-127">In **Solution Explorer**, right-click the NorthwindClient project and select **Set as startup project**.</span></span>

2. <span data-ttu-id="7f215-128">按**F5**启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="7f215-128">Press **F5** to start the application.</span></span>

     <span data-ttu-id="7f215-129">这将生成解决方案并启动客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="7f215-129">This builds the solution and starts the client application.</span></span> <span data-ttu-id="7f215-130">将从服务请求数据并将其显示在控制台中。</span><span class="sxs-lookup"><span data-stu-id="7f215-130">Data is requested from the service and displayed in the console.</span></span>

3. <span data-ttu-id="7f215-131">编辑数据网格的 "**数量**" 列中的值，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="7f215-131">Edit a value in the **Quantity** column of the data grid, and then click **Save**.</span></span>

     <span data-ttu-id="7f215-132">将更改保存到数据服务。</span><span class="sxs-lookup"><span data-stu-id="7f215-132">Changes are saved to the data service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7f215-133">此版本的 NorthwindClient 应用程序不支持添加和删除实体。</span><span class="sxs-lookup"><span data-stu-id="7f215-133">This version of the NorthwindClient application does not support adding and deleting of entities.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7f215-134">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7f215-134">Next Steps</span></span>

<span data-ttu-id="7f215-135">你已成功创建了访问示例 Northwind OData 源的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="7f215-135">You have successfully created the client application that accesses the sample Northwind OData feed.</span></span> <span data-ttu-id="7f215-136">你还完成了 WCF 数据服务快速入门！</span><span class="sxs-lookup"><span data-stu-id="7f215-136">You've also completed the WCF Data Services quickstart!</span></span>

<span data-ttu-id="7f215-137">有关从 .NET Framework 应用程序访问 OData 源的详细信息，请参阅[WCF 数据服务客户端库](wcf-data-services-client-library.md)。</span><span class="sxs-lookup"><span data-stu-id="7f215-137">For more information about accessing an OData feed from a .NET Framework application, see [WCF Data Services Client Library](wcf-data-services-client-library.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7f215-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="7f215-138">See also</span></span>

- [<span data-ttu-id="7f215-139">入门</span><span class="sxs-lookup"><span data-stu-id="7f215-139">Getting Started</span></span>](getting-started-with-wcf-data-services.md)
- [<span data-ttu-id="7f215-140">资源</span><span class="sxs-lookup"><span data-stu-id="7f215-140">Resources</span></span>](wcf-data-services-resources.md)
