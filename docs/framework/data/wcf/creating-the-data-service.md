---
title: 在 Visual Studio 中创建 WCF 数据服务
ms.date: 08/24/2018
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
ms.openlocfilehash: d7ab227a19eeb9bf054700f8d932b75cf3c1ddc9
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43417822"
---
# <a name="create-the-data-service"></a><span data-ttu-id="3aec4-102">创建数据服务</span><span class="sxs-lookup"><span data-stu-id="3aec4-102">Create the data service</span></span>

<span data-ttu-id="3aec4-103">在本主题中，创建使用 WCF 数据服务公开的示例数据服务[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]基于 Northwind 示例数据库的源。</span><span class="sxs-lookup"><span data-stu-id="3aec4-103">In this topic, you create a sample data service that uses WCF Data Services to expose an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed that's based on the Northwind sample database.</span></span> <span data-ttu-id="3aec4-104">此任务涉及以下几个基本步骤：</span><span class="sxs-lookup"><span data-stu-id="3aec4-104">The task involves the following basic steps:</span></span>

1. <span data-ttu-id="3aec4-105">创建 ASP.NET Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="3aec4-105">Create an ASP.NET Web application.</span></span>

2. <span data-ttu-id="3aec4-106">使用实体数据模型工具定义数据模型。</span><span class="sxs-lookup"><span data-stu-id="3aec4-106">Define the data model by using the Entity Data Model tools.</span></span>

3. <span data-ttu-id="3aec4-107">向 Web 应用程序添加数据服务。</span><span class="sxs-lookup"><span data-stu-id="3aec4-107">Add the data service to the Web application.</span></span>

4. <span data-ttu-id="3aec4-108">启用对数据服务的访问。</span><span class="sxs-lookup"><span data-stu-id="3aec4-108">Enable access to the data service.</span></span>

## <a name="create-the-aspnet-web-app"></a><span data-ttu-id="3aec4-109">创建 ASP.NET web 应用</span><span class="sxs-lookup"><span data-stu-id="3aec4-109">Create the ASP.NET web app</span></span>

1. <span data-ttu-id="3aec4-110">在 Visual Studio 中，在**文件**菜单中，选择**新建** > **项目**。</span><span class="sxs-lookup"><span data-stu-id="3aec4-110">In Visual Studio, on the **File** menu, select **New** > **Project**.</span></span>

1. <span data-ttu-id="3aec4-111">在**新的项目**对话框中的，在下，选择 Visual Basic 或 Visual C# **Web**类别中，并选择**ASP.NET Web 应用程序**。</span><span class="sxs-lookup"><span data-stu-id="3aec4-111">In the **New Project** dialog box, under either Visual Basic or Visual C# select the **Web** category, and then select **ASP.NET Web Application**.</span></span>

1. <span data-ttu-id="3aec4-112">输入`NorthwindService`作为名称的项目，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="3aec4-112">Enter `NorthwindService` as the name of the project and then select **OK**.</span></span>

1. <span data-ttu-id="3aec4-113">在中**新的 ASP.NET Web 应用程序**对话框中，选择**空**，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="3aec4-113">In the **New ASP.NET Web Application** dialog, select **Empty** and then select **OK**.</span></span>

1. <span data-ttu-id="3aec4-114">（可选）为 Web 应用程序指定一个特定的端口号。</span><span class="sxs-lookup"><span data-stu-id="3aec4-114">(Optional) Specify a specific port number for your Web application.</span></span> <span data-ttu-id="3aec4-115">注意： 端口号`12345`这一系列的快速入门主题中使用。</span><span class="sxs-lookup"><span data-stu-id="3aec4-115">Note: the port number `12345` is used in this series of quickstart topics.</span></span>

    1. <span data-ttu-id="3aec4-116">在中**解决方案资源管理器**，右键单击刚创建的 ASP.NET 项目，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="3aec4-116">In **Solution Explorer**, right-click on the ASP.NET project that you just created, and then choose **Properties**.</span></span>

    2. <span data-ttu-id="3aec4-117">选择**Web**选项卡，并设置的值**特定端口**向文本框`12345`。</span><span class="sxs-lookup"><span data-stu-id="3aec4-117">Select the **Web** tab, and set the value of the **Specific port** text box to `12345`.</span></span>

## <a name="define-the-data-model"></a><span data-ttu-id="3aec4-118">定义数据模型</span><span class="sxs-lookup"><span data-stu-id="3aec4-118">Define the data model</span></span>

1. <span data-ttu-id="3aec4-119">在中**解决方案资源管理器**，右键单击 ASP.NET 项目的名称，然后单击**添加** > **新项**。</span><span class="sxs-lookup"><span data-stu-id="3aec4-119">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="3aec4-120">在中**添加新项**对话框中，选择**数据**类别中，并选择**ADO.NET 实体数据模型**。</span><span class="sxs-lookup"><span data-stu-id="3aec4-120">In the **Add New Item** dialog box, select the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="3aec4-121">对于数据模型的名称，输入`Northwind.edmx`。</span><span class="sxs-lookup"><span data-stu-id="3aec4-121">For the name of the data model, enter `Northwind.edmx`.</span></span>

4. <span data-ttu-id="3aec4-122">在中**实体数据模型向导**，选择**EF 设计器从数据库**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="3aec4-122">In the **Entity Data Model Wizard**, select **EF Designer from Database**, and then click **Next**.</span></span>

5. <span data-ttu-id="3aec4-123">连接到数据库的数据模型，通过执行以下步骤之一，然后单击**下一步**:</span><span class="sxs-lookup"><span data-stu-id="3aec4-123">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>

    -   <span data-ttu-id="3aec4-124">如果没有已配置的数据库连接，请单击**新的连接**和创建新的连接。</span><span class="sxs-lookup"><span data-stu-id="3aec4-124">If you don't have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="3aec4-125">有关详细信息，请参阅[如何： 创建到 SQL Server 数据库的连接](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90))。</span><span class="sxs-lookup"><span data-stu-id="3aec4-125">For more information, see [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span></span> <span data-ttu-id="3aec4-126">此 SQL Server 实例必须附加了 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="3aec4-126">This SQL Server instance must have the Northwind sample database attached.</span></span>

         <span data-ttu-id="3aec4-127">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="3aec4-127">\- or -</span></span>

    -   <span data-ttu-id="3aec4-128">如果已配置一个连接到 Northwind 数据库的数据库连接，请从连接列表中选择该连接。</span><span class="sxs-lookup"><span data-stu-id="3aec4-128">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>

6. <span data-ttu-id="3aec4-129">在向导的最后一页中，选中数据库中所有表对应的复选框，并清除视图和存储过程对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="3aec4-129">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>

7. <span data-ttu-id="3aec4-130">单击**完成**以关闭向导。</span><span class="sxs-lookup"><span data-stu-id="3aec4-130">Click **Finish** to close the wizard.</span></span>

## <a name="create-the-wcf-data-service"></a><span data-ttu-id="3aec4-131">创建 WCF 数据服务</span><span class="sxs-lookup"><span data-stu-id="3aec4-131">Create the WCF data service</span></span>

1. <span data-ttu-id="3aec4-132">在中**解决方案资源管理器**，右键单击 ASP.NET 项目，然后选择**添加** > **新项**。</span><span class="sxs-lookup"><span data-stu-id="3aec4-132">In **Solution Explorer**, right-click on the ASP.NET project, and then choose **Add** > **New Item**.</span></span>

2. <span data-ttu-id="3aec4-133">在中**添加新项**对话框中，选择**WCF 数据服务**中的项模板**Web**类别。</span><span class="sxs-lookup"><span data-stu-id="3aec4-133">In the **Add New Item** dialog box, select the **WCF Data Service** item template from the **Web** category.</span></span>

   ![在 Visual Studio 2015 中的 WCF 数据服务项模板](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="3aec4-135">**WCF 数据服务**模板现已推出 Visual Studio 2015，但未在 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="3aec4-135">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017.</span></span>

3. <span data-ttu-id="3aec4-136">对于服务的名称，键入`Northwind`。</span><span class="sxs-lookup"><span data-stu-id="3aec4-136">For the name of the service, type `Northwind`.</span></span>

     <span data-ttu-id="3aec4-137">Visual Studio 将为新服务创建 XML 标记和代码文件。</span><span class="sxs-lookup"><span data-stu-id="3aec4-137">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="3aec4-138">默认情况下，代码编辑器窗口将打开。</span><span class="sxs-lookup"><span data-stu-id="3aec4-138">By default, the code-editor window opens.</span></span> <span data-ttu-id="3aec4-139">在中**解决方案资源管理器**，该服务具有扩展名的名称 Northwind *。 svc.cs*或 *。 svc.vb*。</span><span class="sxs-lookup"><span data-stu-id="3aec4-139">In **Solution Explorer**, the service has the name Northwind with the extension *.svc.cs* or *.svc.vb*.</span></span>

4. <span data-ttu-id="3aec4-140">在数据服务的代码中，用数据模型的实体容器的类型（在此示例中为 `/* TODO: put your data source class name here */`）替换定义数据服务的类定义中的注释 `NorthwindEntities`。</span><span class="sxs-lookup"><span data-stu-id="3aec4-140">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="3aec4-141">该类定义应如下所示：</span><span class="sxs-lookup"><span data-stu-id="3aec4-141">The class definition should look this the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]

## <a name="enable-access-to-data-service-resources"></a><span data-ttu-id="3aec4-142">启用对数据服务资源的访问</span><span class="sxs-lookup"><span data-stu-id="3aec4-142">Enable access to data service resources</span></span>

1. <span data-ttu-id="3aec4-143">在数据服务的代码中，用下列代码替换 `InitializeService` 函数中的占位符代码：</span><span class="sxs-lookup"><span data-stu-id="3aec4-143">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]

     <span data-ttu-id="3aec4-144">这使得授权客户端能够对指定实体集的资源进行读写访问。</span><span class="sxs-lookup"><span data-stu-id="3aec4-144">This enables authorized clients to have read and write access to resources for the specified entity sets.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3aec4-145">任何可以访问该 ASP.NET 应用程序的客户端也能够访问由数据服务公开的资源。</span><span class="sxs-lookup"><span data-stu-id="3aec4-145">Any client that can access the ASP.NET application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="3aec4-146">在生产数据服务中，为防止对资源进行未经授权的访问，还应保护应用程序本身的安全。</span><span class="sxs-lookup"><span data-stu-id="3aec4-146">In a production data service, to prevent unauthorized access to resources you should also secure the application itself.</span></span> <span data-ttu-id="3aec4-147">有关更多信息，请参见 [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="3aec4-147">For more information, see [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="3aec4-148">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3aec4-148">Next steps</span></span>

<span data-ttu-id="3aec4-149">已成功创建新的数据服务公开 OData 源的基于 Northwind 示例数据库，并已启用对该源的 ASP.NET Web 应用程序上具有权限的客户端的访问权限。</span><span class="sxs-lookup"><span data-stu-id="3aec4-149">You have successfully created a new data service that exposes an OData feed that is based on the Northwind sample database, and you have enabled access to the feed for clients that have permissions on the ASP.NET Web application.</span></span> <span data-ttu-id="3aec4-150">接下来，将从 Visual Studio 启动数据服务并访问 OData 数据源提交 HTTP GET 请求通过 Web 浏览器：</span><span class="sxs-lookup"><span data-stu-id="3aec4-150">Next, you'll start the data service from Visual Studio and access the OData feed by submitting HTTP GET requests through a Web browser:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3aec4-151">从 web 浏览器访问服务</span><span class="sxs-lookup"><span data-stu-id="3aec4-151">Access the service from a web browser</span></span>](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

## <a name="see-also"></a><span data-ttu-id="3aec4-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="3aec4-152">See also</span></span>

- [<span data-ttu-id="3aec4-153">ADO.NET 实体数据模型工具</span><span class="sxs-lookup"><span data-stu-id="3aec4-153">ADO.NET Entity Data Model Tools</span></span>](https://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)