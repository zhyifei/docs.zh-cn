---
title: "如何：开发在 IIS 上运行的 WCF 数据服务"
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
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- WCF Data Services, hosting
ms.assetid: f6f768c5-4989-49e3-a36f-896ab4ded86e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b93b6e8b6e687f2e39fd5792aba08eaa47fa29fd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a><span data-ttu-id="8981f-102">如何：开发在 IIS 上运行的 WCF 数据服务</span><span class="sxs-lookup"><span data-stu-id="8981f-102">How to: Develop a WCF Data Service Running on IIS</span></span>
<span data-ttu-id="8981f-103">本主题演示如何使用[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]来创建基于 Northwind 示例数据库由 Internet 信息服务 (IIS) 上运行的 ASP.NET Web 应用程序承载数据服务。</span><span class="sxs-lookup"><span data-stu-id="8981f-103">This topic shows how to use [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] to create a data service that is based on the Northwind sample database that is hosted by an ASP.NET Web application that is running on Internet Information Services (IIS).</span></span> <span data-ttu-id="8981f-104">有关如何创建 ASP.NET Development Server 上运行的 ASP.NET Web 应用相同的 Northwind 数据服务的示例，请参阅[WCF 数据服务快速入门](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="8981f-104">For an example of how to create the same Northwind data service as an ASP.NET Web application that runs on the ASP.NET Development Server, see the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8981f-105">若要创建 Northwind 数据服务，您的本地计算机上必须已安装 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="8981f-105">To create the Northwind data service, you must have installed the Northwind sample database on the local computer.</span></span> <span data-ttu-id="8981f-106">若要下载此示例数据库，请访问 [SQL Server 的示例数据库](http://go.microsoft.com/fwlink/?linkid=24758)下载页。</span><span class="sxs-lookup"><span data-stu-id="8981f-106">To download this sample database, see the download page, [Sample Databases for SQL Server](http://go.microsoft.com/fwlink/?linkid=24758).</span></span>  
  
 <span data-ttu-id="8981f-107">本主题说明如何使用实体框架提供程序创建数据服务。</span><span class="sxs-lookup"><span data-stu-id="8981f-107">This topic shows how to create a data service by using the Entity Framework provider.</span></span> <span data-ttu-id="8981f-108">还有其他一些数据服务提供程序可以使用。</span><span class="sxs-lookup"><span data-stu-id="8981f-108">Other data services providers are available.</span></span> <span data-ttu-id="8981f-109">有关详细信息，请参阅[数据服务提供程序](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="8981f-109">For more information, see [Data Services Providers](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="8981f-110">在创建服务之后，您必须显式提供对数据服务资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="8981f-110">After you create the service, you must explicitly provide access to data service resources.</span></span> <span data-ttu-id="8981f-111">有关详细信息，请参阅[如何： 启用对数据服务的访问权限](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="8981f-111">For more information, see [How to: Enable Access to the Data Service](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md).</span></span>  
  
### <a name="to-create-the-aspnet-web-application-that-runs-on-iis"></a><span data-ttu-id="8981f-112">创建在 IIS 上运行的 ASP.NET Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="8981f-112">To create the ASP.NET Web application that runs on IIS</span></span>  
  
1.  <span data-ttu-id="8981f-113">在 Visual Studio 中，在**文件**菜单上，选择**新建**，然后选择**项目**。</span><span class="sxs-lookup"><span data-stu-id="8981f-113">In Visual Studio, on the **File** menu, select **New**, and then select **Project**.</span></span>  
  
2.  <span data-ttu-id="8981f-114">在**新项目**对话框框中，选择 Visual Basic 或 Visual C# 作为编程语言。</span><span class="sxs-lookup"><span data-stu-id="8981f-114">In the **New Project** dialog box, select either Visual Basic or Visual C# as the programming language.</span></span>  
  
3.  <span data-ttu-id="8981f-115">在**模板**窗格中，选择**ASP.NET Web 应用程序**。</span><span class="sxs-lookup"><span data-stu-id="8981f-115">In the **Templates** pane, select **ASP.NET Web Application**.</span></span> <span data-ttu-id="8981f-116">注意：如果使用的是 Visual Studio Web Developer，则必须创建新的网站，而不是新的 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="8981f-116">Note: If you use Visual Studio Web Developer, you must create a new Web site instead of a new Web application.</span></span>  
  
4.  <span data-ttu-id="8981f-117">类型`NorthwindService`作为项目的名称。</span><span class="sxs-lookup"><span data-stu-id="8981f-117">Type `NorthwindService` as the name of the project.</span></span>  
  
5.  <span data-ttu-id="8981f-118">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="8981f-118">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="8981f-119">上**项目**菜单上，选择**NorthwindService 属性**。</span><span class="sxs-lookup"><span data-stu-id="8981f-119">On the **Project** menu, select **NorthwindService Properties**.</span></span>  
  
7.  <span data-ttu-id="8981f-120">选择**Web**选项卡上，然后选择**使用本地 IIS Web 服务器**。</span><span class="sxs-lookup"><span data-stu-id="8981f-120">Select the **Web** tab, and then select **Use Local IIS Web Server**.</span></span>  
  
8.  <span data-ttu-id="8981f-121">单击**创建虚拟目录**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8981f-121">Click **Create Virtual Directory** and then click **OK**.</span></span>  
  
9. <span data-ttu-id="8981f-122">从具有管理员权限的命令提示符中，根据操作系统，执行以下命令之一：</span><span class="sxs-lookup"><span data-stu-id="8981f-122">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>  
  
    -   <span data-ttu-id="8981f-123">32 位系统：</span><span class="sxs-lookup"><span data-stu-id="8981f-123">32-bit systems:</span></span>  
  
        ```console
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i  
        ```  
  
    -   <span data-ttu-id="8981f-124">64 位系统：</span><span class="sxs-lookup"><span data-stu-id="8981f-124">64-bit systems:</span></span>  
  
        ```console
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i  
        ```  
  
     <span data-ttu-id="8981f-125">这样将确保在计算机上注册 Windows Communication Foundation (WCF)。</span><span class="sxs-lookup"><span data-stu-id="8981f-125">This makes sure that Windows Communication Foundation (WCF) is registered on the computer.</span></span>  
  
10. <span data-ttu-id="8981f-126">从具有管理员权限的命令提示符中，根据操作系统，执行以下命令之一：</span><span class="sxs-lookup"><span data-stu-id="8981f-126">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>  
  
    -   <span data-ttu-id="8981f-127">32 位系统：</span><span class="sxs-lookup"><span data-stu-id="8981f-127">32-bit systems:</span></span>  
  
        ```console
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable  
        ```  
  
    -   <span data-ttu-id="8981f-128">64 位系统：</span><span class="sxs-lookup"><span data-stu-id="8981f-128">64-bit systems:</span></span>  
  
        ```console
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable  
        ```  
  
     <span data-ttu-id="8981f-129">这将确保在计算机上安装了 WCF 之后，IIS 能够正常运行。</span><span class="sxs-lookup"><span data-stu-id="8981f-129">This makes sure that IIS runs correctly after WCF has been installed on the computer.</span></span> <span data-ttu-id="8981f-130">您可能必须重启 IIS。</span><span class="sxs-lookup"><span data-stu-id="8981f-130">You might have to also restart IIS.</span></span>  
  
11. <span data-ttu-id="8981f-131">当 ASP.NET 应用程序在 IIS7 上运行时，您还必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8981f-131">When the ASP.NET application runs on IIS7, you must also perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="8981f-132">打开 IIS 管理器并导航到下的 PhotoService 应用程序**Default Web Site**。</span><span class="sxs-lookup"><span data-stu-id="8981f-132">Open IIS Manager and navigate to the PhotoService application under **Default Web Site**.</span></span>  
  
    2.  <span data-ttu-id="8981f-133">在**功能视图**，双击**身份验证**。</span><span class="sxs-lookup"><span data-stu-id="8981f-133">In **Features View**, double-click **Authentication**.</span></span>  
  
    3.  <span data-ttu-id="8981f-134">上**身份验证**页上，选择**匿名身份验证**。</span><span class="sxs-lookup"><span data-stu-id="8981f-134">On the **Authentication** page, select **Anonymous Authentication**.</span></span>  
  
    4.  <span data-ttu-id="8981f-135">在**操作**窗格中，单击**编辑**设置安全主体的匿名用户下将连接到站点。</span><span class="sxs-lookup"><span data-stu-id="8981f-135">In the **Actions** pane, click **Edit** to set the security principal under which anonymous users will connect to the site.</span></span>  
  
    5.  <span data-ttu-id="8981f-136">在**编辑匿名身份验证凭据**对话框中，选择**应用程序池标识**。</span><span class="sxs-lookup"><span data-stu-id="8981f-136">In the **Edit Anonymous Authentication Credentials** dialog box, select **Application pool identity**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="8981f-137">使用 Network Service 帐户时，您必须授予匿名用户与该账户关联的所有内部网络访问权限。</span><span class="sxs-lookup"><span data-stu-id="8981f-137">When you use the Network Service account, you grant anonymous users all the internal network access associated with that account.</span></span>  
  
12. <span data-ttu-id="8981f-138">通过在 Visual Studio 中使用 SQL Server Management Studio、sqlcmd.exe 实用工具或 Transact-SQL Editor，针对附加有 Northwind 数据库的 SQL Server 实例执行下面的 Transact-SQL 命令：</span><span class="sxs-lookup"><span data-stu-id="8981f-138">By using SQL Server Management Studio, the sqlcmd.exe utility, or the Transact-SQL Editor in Visual Studio, execute the following Transact-SQL command against the instance of SQL Server that has the Northwind database attached:</span></span>  
  
    ```sql  
    CREATE LOGIN [NT AUTHORITY\NETWORK SERVICE] FROM WINDOWS;  
    GO   
    ```  
  
     <span data-ttu-id="8981f-139">这将在 SQL Server 实例中为用于运行 IIS 的 Windows 帐户创建一个登录名。</span><span class="sxs-lookup"><span data-stu-id="8981f-139">This creates a login in the SQL Server instance for the Windows account used to run IIS.</span></span> <span data-ttu-id="8981f-140">这样，IIS 即可连接到 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="8981f-140">This enables IIS to connect to the SQL Server instance.</span></span>  
  
13. <span data-ttu-id="8981f-141">附加 Northwind 数据库后，执行下面的 Transact-SQL 命令：</span><span class="sxs-lookup"><span data-stu-id="8981f-141">With the Northwind database attached, execute the following Transact-SQL commands:</span></span>  
  
    ```sql  
    USE Northwind  
    GO  
    CREATE USER [NT AUTHORITY\NETWORK SERVICE]   
    FOR LOGIN [NT AUTHORITY\NETWORK SERVICE] WITH DEFAULT_SCHEMA=[dbo];  
    GO  
    ALTER LOGIN [NT AUTHORITY\NETWORK SERVICE]   
    WITH DEFAULT_DATABASE=[Northwind];   
    GO  
    EXEC sp_addrolemember 'db_datareader', 'NT AUTHORITY\NETWORK SERVICE'  
    GO  
    EXEC sp_addrolemember 'db_datawriter', 'NT AUTHORITY\NETWORK SERVICE'  
    GO   
    ```  
  
     <span data-ttu-id="8981f-142">这将为新登录名授予相应权限，使得 IIS 能够在 Northwind 数据库中读出和写入数据。</span><span class="sxs-lookup"><span data-stu-id="8981f-142">This grants rights to the new login, which enables IIS to read data from and write data to the Northwind database.</span></span>  
  
### <a name="to-define-the-data-model"></a><span data-ttu-id="8981f-143">定义数据模型</span><span class="sxs-lookup"><span data-stu-id="8981f-143">To define the data model</span></span>  
  
1.  <span data-ttu-id="8981f-144">在**解决方案资源管理器**，右键单击 ASP.NET 项目的名称，然后单击**添加新项。**</span><span class="sxs-lookup"><span data-stu-id="8981f-144">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add New Item.**</span></span>  
  
2.  <span data-ttu-id="8981f-145">在**添加新项**对话框中，选择**ADO.NET 实体数据模型**。</span><span class="sxs-lookup"><span data-stu-id="8981f-145">In the **Add New Item** dialog box, select **ADO.NET Entity Data Model**.</span></span>  
  
3.  <span data-ttu-id="8981f-146">对于数据模型的名称，键入`Northwind.edmx`。</span><span class="sxs-lookup"><span data-stu-id="8981f-146">For the name of the data model, type `Northwind.edmx`.</span></span>  
  
4.  <span data-ttu-id="8981f-147">在实体数据模型向导中，选择**从数据库生成**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="8981f-147">In the Entity Data Model Wizard, select **Generate from Database**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="8981f-148">通过执行以下步骤中，连接到数据库的数据模型，然后单击**下一步**:</span><span class="sxs-lookup"><span data-stu-id="8981f-148">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>  
  
    -   <span data-ttu-id="8981f-149">如果你没有已配置的数据库连接，请单击**新连接**并创建新连接。</span><span class="sxs-lookup"><span data-stu-id="8981f-149">If you do not have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="8981f-150">有关详细信息，请参阅[如何： 创建到 SQL Server 数据库的连接](http://go.microsoft.com/fwlink/?LinkId=123631)。</span><span class="sxs-lookup"><span data-stu-id="8981f-150">For more information, see [How to: Create Connections to SQL Server Databases](http://go.microsoft.com/fwlink/?LinkId=123631).</span></span> <span data-ttu-id="8981f-151">此 [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] 实例必须附加了 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="8981f-151">This [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] instance must have the Northwind sample database attached.</span></span>  
  
         <span data-ttu-id="8981f-152">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="8981f-152">\- or -</span></span>  
  
    -   <span data-ttu-id="8981f-153">如果已配置一个连接到 Northwind 数据库的数据库连接，请从连接列表中选择该连接。</span><span class="sxs-lookup"><span data-stu-id="8981f-153">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>  
  
6.  <span data-ttu-id="8981f-154">在向导的最后一页中，选中数据库中所有表对应的复选框，并清除视图和存储过程对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="8981f-154">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>  
  
7.  <span data-ttu-id="8981f-155">单击**完成**关闭向导。</span><span class="sxs-lookup"><span data-stu-id="8981f-155">Click **Finish** to close the wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8981f-156">此生成的数据模型将在实体类型上公开外键属性。</span><span class="sxs-lookup"><span data-stu-id="8981f-156">This generated data model exposes foreign key properties on entity types.</span></span> <span data-ttu-id="8981f-157">使用 Visual Studio 2008 创建的数据模型不包括这些外键属性。</span><span class="sxs-lookup"><span data-stu-id="8981f-157">Data models created using Visual Studio 2008 do not include these foreign key properties.</span></span> <span data-ttu-id="8981f-158">因此，在尝试访问使用 Visual Studio 2008 创建的 Northwind 数据服务之前，必须更新已创建的任何客户端应用程序的客户端数据服务类才能访问这一版本的 Northwind 数据服务。</span><span class="sxs-lookup"><span data-stu-id="8981f-158">Because of this, you must update the client data service classes of any client applications that were created to access the Northwind data service that was created using Visual Studio 2008 before attempting to access this version of the Northwind data service.</span></span>  
  
### <a name="to-create-the-data-service"></a><span data-ttu-id="8981f-159">创建数据服务</span><span class="sxs-lookup"><span data-stu-id="8981f-159">To create the data service</span></span>  
  
1.  <span data-ttu-id="8981f-160">在**解决方案资源管理器**，右键单击 ASP.NET 项目中的名称，然后单击**添加新项**。</span><span class="sxs-lookup"><span data-stu-id="8981f-160">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="8981f-161">在**添加新项**对话框中，选择**ADO.NET 数据服务**。</span><span class="sxs-lookup"><span data-stu-id="8981f-161">In the **Add New Item** dialog box, select **ADO.NET Data Service**.</span></span>  
  
3.  <span data-ttu-id="8981f-162">有关服务的名称，键入`Northwind`。</span><span class="sxs-lookup"><span data-stu-id="8981f-162">For the name of the service, type `Northwind`.</span></span>  
  
     <span data-ttu-id="8981f-163">Visual Studio 将为新服务创建 XML 标记和代码文件。</span><span class="sxs-lookup"><span data-stu-id="8981f-163">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="8981f-164">默认情况下，代码编辑器窗口将打开。</span><span class="sxs-lookup"><span data-stu-id="8981f-164">By default, the code-editor window opens.</span></span> <span data-ttu-id="8981f-165">在**解决方案资源管理器**，服务将具有名称为 Northwind 扩展名。 svc.cs 或。 svc.vb。</span><span class="sxs-lookup"><span data-stu-id="8981f-165">In **Solution Explorer**, the service will have the name, Northwind, with the extension .svc.cs or .svc.vb.</span></span>  
  
4.  <span data-ttu-id="8981f-166">在数据服务的代码中，用数据模型的实体容器的类型（在此示例中为 `/* TODO: put your data source class name here */`）替换定义数据服务的类定义中的注释 `NorthwindEntities`。</span><span class="sxs-lookup"><span data-stu-id="8981f-166">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="8981f-167">该类定义应如下所示：</span><span class="sxs-lookup"><span data-stu-id="8981f-167">The class definition should look this the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
## <a name="see-also"></a><span data-ttu-id="8981f-168">请参阅</span><span class="sxs-lookup"><span data-stu-id="8981f-168">See Also</span></span>  
 [<span data-ttu-id="8981f-169">将数据公开为服务</span><span class="sxs-lookup"><span data-stu-id="8981f-169">Exposing Your Data as a Service</span></span>](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)
