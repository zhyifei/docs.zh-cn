---
title: "创建数据服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 57e305fd8b03e8d46c1fdcb7dd551f32062a1009
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="creating-the-data-service"></a><span data-ttu-id="e23bf-102">创建数据服务</span><span class="sxs-lookup"><span data-stu-id="e23bf-102">Creating the Data Service</span></span>
<span data-ttu-id="e23bf-103">在此任务中，你将创建使用示例数据服务[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]公开[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]基于 Northwind 示例数据库的源。</span><span class="sxs-lookup"><span data-stu-id="e23bf-103">In this task, you will create a sample data service that uses [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] to expose an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed that is based on the Northwind sample database.</span></span> <span data-ttu-id="e23bf-104">此任务涉及以下几个基本步骤：</span><span class="sxs-lookup"><span data-stu-id="e23bf-104">The task involves the following basic steps:</span></span>  
  
1.  <span data-ttu-id="e23bf-105">创建一个 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e23bf-105">Create an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web application.</span></span>  
  
2.  <span data-ttu-id="e23bf-106">使用[!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)]工具定义数据模型。</span><span class="sxs-lookup"><span data-stu-id="e23bf-106">Define the data model by using the [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] tools.</span></span>  
  
3.  <span data-ttu-id="e23bf-107">向 Web 应用程序添加数据服务。</span><span class="sxs-lookup"><span data-stu-id="e23bf-107">Add the data service to the Web application.</span></span>  
  
4.  <span data-ttu-id="e23bf-108">启用对数据服务的访问。</span><span class="sxs-lookup"><span data-stu-id="e23bf-108">Enable access to the data service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e23bf-109">在完成此任务时创建的 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 应用程序将在 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 提供的 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Development Server 上运行。</span><span class="sxs-lookup"><span data-stu-id="e23bf-109">The [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web application that you create when you complete this task runs on the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Development Server provided by [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span> [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="e23bf-110"> Development Server 仅支持来自本地计算机的访问。</span><span class="sxs-lookup"><span data-stu-id="e23bf-110"> Development Server only supports access from the local computer.</span></span> <span data-ttu-id="e23bf-111">为了便于在开发的过程中测试数据服务和解决问题，可考虑通过使用 Internet Information Services (IIS) 运行承载数据服务的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e23bf-111">To also make it easier to test and troubleshoot the data service during development, consider running the application that hosts the data service by using Internet Information Services (IIS).</span></span> <span data-ttu-id="e23bf-112">有关详细信息，请参阅 [How to: Develop a WCF Data Service Running on IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)。</span><span class="sxs-lookup"><span data-stu-id="e23bf-112">For more information, see [How to: Develop a WCF Data Service Running on IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).</span></span>  
  
### <a name="to-create-the-aspnet-web-application"></a><span data-ttu-id="e23bf-113">创建 ASP.NET Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="e23bf-113">To create the ASP.NET Web application</span></span>  
  
1.  <span data-ttu-id="e23bf-114">在[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]上**文件**菜单上，选择**新建**，然后选择**项目**。</span><span class="sxs-lookup"><span data-stu-id="e23bf-114">In [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], on the **File** menu, select **New**, and then select **Project**.</span></span>  
  
2.  <span data-ttu-id="e23bf-115">在**新项目**对话框中下,[!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]或[!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]选择**Web**模板，，然后选择**ASP.NET Web 应用程序**。</span><span class="sxs-lookup"><span data-stu-id="e23bf-115">In the **New Project** dialog box, under either [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] select the **Web** template, and then select **ASP.NET Web Application**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e23bf-116">如果使用的是 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Web Developer，则必须创建新的网站，而不是创建新的 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e23bf-116">If you use [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Web Developer, you must create a new Web site instead of a new Web application.</span></span>  
  
3.  <span data-ttu-id="e23bf-117">类型`NorthwindService`作为项目的名称。</span><span class="sxs-lookup"><span data-stu-id="e23bf-117">Type `NorthwindService` as the name of the project.</span></span>  
  
4.  <span data-ttu-id="e23bf-118">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="e23bf-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="e23bf-119">（可选）为 Web 应用程序指定一个特定的端口号。</span><span class="sxs-lookup"><span data-stu-id="e23bf-119">(Optional) Specify a specific port number for your Web application.</span></span> <span data-ttu-id="e23bf-120">注意：在快速入门的其余部分使用端口号 `12345`。</span><span class="sxs-lookup"><span data-stu-id="e23bf-120">Note: the port number `12345` is used in the rest of the quickstart.</span></span>  
  
    1.  <span data-ttu-id="e23bf-121">在**解决方案资源管理器**，右键单击的名称[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]项目你刚创建的，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="e23bf-121">In **Solution Explorer**, right-click the name of the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project that you just created, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="e23bf-122">选择**Web**选项卡，并设置的值**特定端口**向文本框`12345`。</span><span class="sxs-lookup"><span data-stu-id="e23bf-122">Select the **Web** tab, and set the value of the **Specific port** text box to `12345`.</span></span>  
  
### <a name="to-define-the-data-model"></a><span data-ttu-id="e23bf-123">定义数据模型</span><span class="sxs-lookup"><span data-stu-id="e23bf-123">To define the data model</span></span>  
  
1.  <span data-ttu-id="e23bf-124">在**解决方案资源管理器**，右键单击的名称[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]项目，，然后单击**添加新项。**</span><span class="sxs-lookup"><span data-stu-id="e23bf-124">In **Solution Explorer**, right-click the name of the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project, and then click **Add New Item.**</span></span>  
  
2.  <span data-ttu-id="e23bf-125">在**添加新项**对话框中，单击**数据**模板，然后选择**ADO.NET 实体数据模型**。</span><span class="sxs-lookup"><span data-stu-id="e23bf-125">In the **Add New Item** dialog box, click the **Data** template and then select **ADO.NET Entity Data Model**.</span></span>  
  
3.  <span data-ttu-id="e23bf-126">对于数据模型的名称，键入`Northwind.edmx`。</span><span class="sxs-lookup"><span data-stu-id="e23bf-126">For the name of the data model, type `Northwind.edmx`.</span></span>  
  
4.  <span data-ttu-id="e23bf-127">在[!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)]向导中，选择**从数据库生成**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e23bf-127">In the [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] Wizard, select **Generate from Database**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="e23bf-128">通过执行以下步骤中，连接到数据库的数据模型，然后单击**下一步**:</span><span class="sxs-lookup"><span data-stu-id="e23bf-128">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>  
  
    -   <span data-ttu-id="e23bf-129">如果你没有已配置的数据库连接，请单击**新连接**并创建新连接。</span><span class="sxs-lookup"><span data-stu-id="e23bf-129">If you do not have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="e23bf-130">有关详细信息，请参阅[如何： 创建到 SQL Server 数据库的连接](http://go.microsoft.com/fwlink/?LinkId=123631)。</span><span class="sxs-lookup"><span data-stu-id="e23bf-130">For more information, see [How to: Create Connections to SQL Server Databases](http://go.microsoft.com/fwlink/?LinkId=123631).</span></span> <span data-ttu-id="e23bf-131">此 [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] 实例必须附加了 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="e23bf-131">This [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] instance must have the Northwind sample database attached.</span></span>  
  
         <span data-ttu-id="e23bf-132">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="e23bf-132">\- or -</span></span>  
  
    -   <span data-ttu-id="e23bf-133">如果已配置一个连接到 Northwind 数据库的数据库连接，请从连接列表中选择该连接。</span><span class="sxs-lookup"><span data-stu-id="e23bf-133">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>  
  
6.  <span data-ttu-id="e23bf-134">在向导的最后一页中，选中数据库中所有表对应的复选框，并清除视图和存储过程对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="e23bf-134">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>  
  
7.  <span data-ttu-id="e23bf-135">单击**完成**关闭向导。</span><span class="sxs-lookup"><span data-stu-id="e23bf-135">Click **Finish** to close the wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e23bf-136">此生成的数据模型将在实体类型上公开外键属性。</span><span class="sxs-lookup"><span data-stu-id="e23bf-136">This generated data model exposes foreign key properties on entity types.</span></span> <span data-ttu-id="e23bf-137">使用 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 2008 创建的数据模型不包括这些外键属性。</span><span class="sxs-lookup"><span data-stu-id="e23bf-137">Data models created using [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 2008 do not include these foreign key properties.</span></span> <span data-ttu-id="e23bf-138">因此，在尝试访问使用 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 2008 创建的 Northwind 数据服务之前，必须更新已创建的所有客户端应用程序的客户端数据服务类，然后才能访问这一版本的 Northwind 数据服务。</span><span class="sxs-lookup"><span data-stu-id="e23bf-138">Because of this, you must update the client data service classes of any client applications that were created to access the Northwind data service that was created using [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 2008 before attempting to access this version of the Northwind data service.</span></span>  
  
### <a name="to-create-the-data-service"></a><span data-ttu-id="e23bf-139">创建数据服务</span><span class="sxs-lookup"><span data-stu-id="e23bf-139">To create the data service</span></span>  
  
1.  <span data-ttu-id="e23bf-140">在**解决方案资源管理器**，右键单击的名称你[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]项目，，然后单击**添加新项**。</span><span class="sxs-lookup"><span data-stu-id="e23bf-140">In **Solution Explorer**, right-click the name of your [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project, and then click **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="e23bf-141">在**添加新项**对话框中，选择**WCF 数据服务**。</span><span class="sxs-lookup"><span data-stu-id="e23bf-141">In the **Add New Item** dialog box, select **WCF Data Service**.</span></span>  
  
3.  <span data-ttu-id="e23bf-142">有关服务的名称，键入`Northwind`。</span><span class="sxs-lookup"><span data-stu-id="e23bf-142">For the name of the service, type `Northwind`.</span></span>  
  
     [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]<span data-ttu-id="e23bf-143"> 将为新服务创建 XML 标记和代码文件。</span><span class="sxs-lookup"><span data-stu-id="e23bf-143">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="e23bf-144">默认情况下，代码编辑器窗口将打开。</span><span class="sxs-lookup"><span data-stu-id="e23bf-144">By default, the code-editor window opens.</span></span> <span data-ttu-id="e23bf-145">在**解决方案资源管理器**，服务将具有名称为 Northwind 扩展名。 svc.cs 或。 svc.vb。</span><span class="sxs-lookup"><span data-stu-id="e23bf-145">In **Solution Explorer**, the service will have the name, Northwind, with the extension .svc.cs or .svc.vb.</span></span>  
  
4.  <span data-ttu-id="e23bf-146">在数据服务的代码中，用数据模型的实体容器的类型（在此示例中为 `/* TODO: put your data source class name here */`）替换定义数据服务的类定义中的注释 `NorthwindEntities`。</span><span class="sxs-lookup"><span data-stu-id="e23bf-146">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="e23bf-147">该类定义应如下所示：</span><span class="sxs-lookup"><span data-stu-id="e23bf-147">The class definition should look this the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
### <a name="to-enable-access-to-data-service-resources"></a><span data-ttu-id="e23bf-148">启用对数据服务资源的访问</span><span class="sxs-lookup"><span data-stu-id="e23bf-148">To enable access to data service resources</span></span>  
  
1.  <span data-ttu-id="e23bf-149">在数据服务的代码中，用下列代码替换 `InitializeService` 函数中的占位符代码：</span><span class="sxs-lookup"><span data-stu-id="e23bf-149">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     <span data-ttu-id="e23bf-150">这使得授权客户端能够对指定实体集的资源进行读写访问。</span><span class="sxs-lookup"><span data-stu-id="e23bf-150">This enables authorized clients to have read and write access to resources for the specified entity sets.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e23bf-151">任何可以访问该 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 应用程序的客户端也能够访问由数据服务公开的资源。</span><span class="sxs-lookup"><span data-stu-id="e23bf-151">Any client that can access the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="e23bf-152">在生产数据服务中，为防止对资源进行未经授权的访问，还应保护应用程序本身的安全。</span><span class="sxs-lookup"><span data-stu-id="e23bf-152">In a production data service, to prevent unauthorized access to resources you should also secure the application itself.</span></span> <span data-ttu-id="e23bf-153">有关更多信息，请参见 [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="e23bf-153">For more information, see [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e23bf-154">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e23bf-154">Next Steps</span></span>  
 <span data-ttu-id="e23bf-155">您已成功创建新的数据服务公开[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]必须启用到客户端上具有权限的数据源的访问，基于 Northwind 示例数据库，并且你的源[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e23bf-155">You have successfully created a new data service that exposes an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed that is based on the Northwind sample database, and you have enabled access to the feed for clients that have permissions on the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web application.</span></span> <span data-ttu-id="e23bf-156">接下来，将开始从数据服务[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]和将访问[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]源通过 Web 浏览器提交 HTTP GET 请求：</span><span class="sxs-lookup"><span data-stu-id="e23bf-156">Next, you will start the data service from [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] and you will access the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed by submitting HTTP GET requests through a Web browser:</span></span>  
  
 [<span data-ttu-id="e23bf-157">从 Web 浏览器访问服务</span><span class="sxs-lookup"><span data-stu-id="e23bf-157">Accessing the Service from a Web Browser</span></span>](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)  
  
## <a name="see-also"></a><span data-ttu-id="e23bf-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="e23bf-158">See Also</span></span>  
 [<span data-ttu-id="e23bf-159">ADO.NET 实体数据模型工具</span><span class="sxs-lookup"><span data-stu-id="e23bf-159">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)
