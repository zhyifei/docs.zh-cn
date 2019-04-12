---
title: 创建 .NET Framework 客户端应用程序（WCF 数据服务快速入门）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 41ade767-eeab-437d-9121-9797e8fb8045
ms.openlocfilehash: dfc08d4623f124a41412907f5a118e8d9ee7833d
ms.sourcegitcommit: 680a741667cf6859de71586a0caf6be14f4f7793
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2019
ms.locfileid: "59517767"
---
# <a name="creating-the-net-framework-client-application-wcf-data-services-quickstart"></a><span data-ttu-id="35bf6-102">创建 .NET Framework 客户端应用程序（WCF 数据服务快速入门）</span><span class="sxs-lookup"><span data-stu-id="35bf6-102">Creating the .NET Framework Client Application (WCF Data Services Quickstart)</span></span>

<span data-ttu-id="35bf6-103">这是 WCF 数据服务快速入门的最后一项任务。</span><span class="sxs-lookup"><span data-stu-id="35bf6-103">This is the final task of the WCF Data Services quickstart.</span></span> <span data-ttu-id="35bf6-104">在此任务中，你将添加到解决方案的控制台应用程序，请添加对引用[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]馈送到此新的客户端应用程序，并访问 OData 数据源从客户端应用程序通过使用生成的客户端数据服务类和客户端库.</span><span class="sxs-lookup"><span data-stu-id="35bf6-104">In this task, you will add a console application to the solution, add a reference to the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed into this new client application, and access the OData feed from the client application by using the generated client data service classes and client libraries.</span></span>

> [!NOTE]
> <span data-ttu-id="35bf6-105">访问数据源不需要基于 .NET Framework 的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="35bf6-105">A .NET Framework-based client application is not required to access a data feed.</span></span> <span data-ttu-id="35bf6-106">可以通过任何应用程序组件，使用 OData 源访问数据服务。</span><span class="sxs-lookup"><span data-stu-id="35bf6-106">The data service can be accessed by any application component that consumes an OData feed.</span></span> <span data-ttu-id="35bf6-107">有关详细信息，请参阅[在客户端应用程序中使用数据服务](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="35bf6-107">For more information, see [Using a Data Service in a Client Application](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md).</span></span>

## <a name="to-create-the-client-application-by-using-visual-studio"></a><span data-ttu-id="35bf6-108">使用 Visual Studio 创建客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="35bf6-108">To create the client application by using Visual Studio</span></span>

1. <span data-ttu-id="35bf6-109">在中**解决方案资源管理器**，右键单击该解决方案，单击**添加**，然后单击**新项目**。</span><span class="sxs-lookup"><span data-stu-id="35bf6-109">In **Solution Explorer**, right-click the solution, click **Add**, and then click **New Project**.</span></span>

2. <span data-ttu-id="35bf6-110">在左窗格中，选择**已安装**> [**Visual C#** 或**Visual Basic**] > **Windows 桌面**，然后选择**WPF 应用**模板。</span><span class="sxs-lookup"><span data-stu-id="35bf6-110">In the left pane, select **Installed** > [**Visual C#** or **Visual Basic**] > **Windows Desktop**, and then select the **WPF App** template.</span></span>

3. <span data-ttu-id="35bf6-111">输入`NorthwindClient`以及该项目名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="35bf6-111">Enter `NorthwindClient` for the project name, and then click **OK**.</span></span>

4. <span data-ttu-id="35bf6-112">打开文件 MainWindow.xaml 并用下列代码替换 XAML 代码：</span><span class="sxs-lookup"><span data-stu-id="35bf6-112">Open the file MainWindow.xaml and replace the XAML code with the following code:</span></span>

     [!code-xaml[Astoria Quickstart Client#Window1Xaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml#window1xaml)]

## <a name="to-add-a-data-service-reference-to-the-project"></a><span data-ttu-id="35bf6-113">在项目中添加数据服务引用</span><span class="sxs-lookup"><span data-stu-id="35bf6-113">To add a data service reference to the project</span></span>

1. <span data-ttu-id="35bf6-114">在中**解决方案资源管理器**中右击 NorthwindClient 项目，单击**添加** > **服务引用**，然后单击**发现**.</span><span class="sxs-lookup"><span data-stu-id="35bf6-114">In **Solution Explorer**, right-click the NorthwindClient project, click **Add** > **Service Reference**, and then click **Discover**.</span></span>

     <span data-ttu-id="35bf6-115">这将显示在第一个任务中创建的 Northwind 数据服务。</span><span class="sxs-lookup"><span data-stu-id="35bf6-115">This displays the Northwind data service that you created in the first task.</span></span>

2. <span data-ttu-id="35bf6-116">在中**Namespace**文本框中，键入`Northwind`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="35bf6-116">In the **Namespace** text box, type `Northwind`, and then click **OK**.</span></span>

     <span data-ttu-id="35bf6-117">这将在项目中添加一个新的代码文件，其中包含用于作为对象访问数据服务资源并与其交互的数据类。</span><span class="sxs-lookup"><span data-stu-id="35bf6-117">This adds a new code file to the project, which contains the data classes that are used to access and interact with data service resources as objects.</span></span> <span data-ttu-id="35bf6-118">这些数据类是在命名空间 `NorthwindClient.Northwind` 中创建的。</span><span class="sxs-lookup"><span data-stu-id="35bf6-118">The data classes are created in the namespace `NorthwindClient.Northwind`.</span></span>

## <a name="to-access-data-service-data-in-the-wpf-application"></a><span data-ttu-id="35bf6-119">在 WPF 应用程序中访问数据服务数据</span><span class="sxs-lookup"><span data-stu-id="35bf6-119">To access data service data in the WPF application</span></span>

1. <span data-ttu-id="35bf6-120">在中**解决方案资源管理器**下**NorthwindClient**，右键单击项目，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="35bf6-120">In **Solution Explorer** under **NorthwindClient**, right-click the project and click **Add Reference**.</span></span>

2. <span data-ttu-id="35bf6-121">在中**添加引用**对话框中，单击 **.NET**选项卡上，选择 System.Data.Services.Client.dll 程序集，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="35bf6-121">In the **Add Reference** dialog box, click the **.NET** tab, select the System.Data.Services.Client.dll assembly, and then click **OK**.</span></span>

3. <span data-ttu-id="35bf6-122">在中**解决方案资源管理器**下**NorthwindClient**，打开 MainWindow.xaml 文件的代码页，并添加以下`using`语句 (`Imports`在 Visual Basic 中)。</span><span class="sxs-lookup"><span data-stu-id="35bf6-122">In **Solution Explorer** under **NorthwindClient**, open the code page for the MainWindow.xaml file, and add the following `using` statement (`Imports` in Visual Basic).</span></span>

     [!code-csharp[Astoria Quickstart Client#Using](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#using)]
     [!code-vb[Astoria Quickstart Client#Using](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#using)]

3. <span data-ttu-id="35bf6-123">将用于查询数据服务并将结果绑定到 <xref:System.Data.Services.Client.DataServiceCollection%601> 的下列代码插入到 `MainWindow` 类：</span><span class="sxs-lookup"><span data-stu-id="35bf6-123">Insert the following code that queries that data service and binds the result to a <xref:System.Data.Services.Client.DataServiceCollection%601> into the `MainWindow` class:</span></span>

    > [!NOTE]
    > <span data-ttu-id="35bf6-124">必须用承载 Northwind 数据服务的实例的服务器和端口替换主机名 `localhost:12345`。</span><span class="sxs-lookup"><span data-stu-id="35bf6-124">You must replace the host name `localhost:12345` with the server and port that is hosting your instance of the Northwind data service.</span></span>

     [!code-csharp[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#querycode)]
     [!code-vb[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#querycode)]

4. <span data-ttu-id="35bf6-125">将用于保存更改的下列代码插入到 `MainWindow` 类：</span><span class="sxs-lookup"><span data-stu-id="35bf6-125">Insert the following code that saves changes into the `MainWindow` class:</span></span>

     [!code-csharp[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#savechanges)]
     [!code-vb[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#savechanges)]

## <a name="to-build-and-run-the-northwindclient-application"></a><span data-ttu-id="35bf6-126">生成并运行 NorthwindClient 应用程序</span><span class="sxs-lookup"><span data-stu-id="35bf6-126">To build and run the NorthwindClient application</span></span>

1. <span data-ttu-id="35bf6-127">在中**解决方案资源管理器**，右键单击 NorthwindClient 项目并选择**设为启动项目**。</span><span class="sxs-lookup"><span data-stu-id="35bf6-127">In **Solution Explorer**, right-click the NorthwindClient project and select **Set as startup project**.</span></span>

2. <span data-ttu-id="35bf6-128">按**F5**启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="35bf6-128">Press **F5** to start the application.</span></span>

     <span data-ttu-id="35bf6-129">这将生成解决方案并启动客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="35bf6-129">This builds the solution and starts the client application.</span></span> <span data-ttu-id="35bf6-130">将从服务请求数据并将其显示在控制台中。</span><span class="sxs-lookup"><span data-stu-id="35bf6-130">Data is requested from the service and displayed in the console.</span></span>

3. <span data-ttu-id="35bf6-131">编辑中的值**Quantity**列的数据网格，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="35bf6-131">Edit a value in the **Quantity** column of the data grid, and then click **Save**.</span></span>

     <span data-ttu-id="35bf6-132">将更改保存到数据服务。</span><span class="sxs-lookup"><span data-stu-id="35bf6-132">Changes are saved to the data service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="35bf6-133">此版本的 NorthwindClient 应用程序不支持添加和删除实体。</span><span class="sxs-lookup"><span data-stu-id="35bf6-133">This version of the NorthwindClient application does not support adding and deleting of entities.</span></span>

## <a name="next-steps"></a><span data-ttu-id="35bf6-134">后续步骤</span><span class="sxs-lookup"><span data-stu-id="35bf6-134">Next Steps</span></span>

<span data-ttu-id="35bf6-135">已成功创建访问的示例 Northwind odata 的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="35bf6-135">You have successfully created the client application that accesses the sample Northwind OData feed.</span></span> <span data-ttu-id="35bf6-136">你已经完成 WCF Data Services 快速入门 ！</span><span class="sxs-lookup"><span data-stu-id="35bf6-136">You've also completed the WCF Data Services quickstart!</span></span>

<span data-ttu-id="35bf6-137">有关从馈送的有关访问 OData 的详细信息[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]应用程序，请参阅[WCF Data Services 客户端库](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)。</span><span class="sxs-lookup"><span data-stu-id="35bf6-137">For more information about accessing an OData feed from a [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] application, see [WCF Data Services Client Library](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="35bf6-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="35bf6-138">See also</span></span>

- [<span data-ttu-id="35bf6-139">入门</span><span class="sxs-lookup"><span data-stu-id="35bf6-139">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)
- [<span data-ttu-id="35bf6-140">资源</span><span class="sxs-lookup"><span data-stu-id="35bf6-140">Resources</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)
