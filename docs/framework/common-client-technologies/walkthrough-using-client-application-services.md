---
title: 演练：使用客户端应用程序服务
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application services host [client application services]
- client application services, walkthroughs
ms.assetid: bb7c8950-4517-4dae-b705-b74a14059b26
ms.openlocfilehash: 9193dc56a0f92daf486d95666ba820cb09d588d0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745365"
---
# <a name="walkthrough-using-client-application-services"></a><span data-ttu-id="e2cec-102">演练：使用客户端应用程序服务</span><span class="sxs-lookup"><span data-stu-id="e2cec-102">Walkthrough: Using Client Application Services</span></span>
<span data-ttu-id="e2cec-103">本主题介绍如何创建使用客户端应用程序服务对用户进行身份验证并检索用户角色和设置的 Windows 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e2cec-103">This topic describes how to create a Windows application that uses client application services to authenticate users and retrieve user roles and settings.</span></span>  
  
 <span data-ttu-id="e2cec-104">在本演练中，你将要执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="e2cec-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="e2cec-105">创建 Windows 窗体应用程序，并使用 Visual Studio 项目设计器启用和配置客户端应用程序服务。</span><span class="sxs-lookup"><span data-stu-id="e2cec-105">Create a Windows Forms application and use the Visual Studio project designer to enable and configure client application services.</span></span>  
  
-   <span data-ttu-id="e2cec-106">创建一个简单 ASP.NET Web 服务应用程序，以承载应用程序服务并测试客户端配置。</span><span class="sxs-lookup"><span data-stu-id="e2cec-106">Create a simple ASP.NET Web Service application to host the application services and test your client configuration.</span></span>  
  
-   <span data-ttu-id="e2cec-107">向应用程序添加 Forms 身份验证。</span><span class="sxs-lookup"><span data-stu-id="e2cec-107">Add forms authentication to your application.</span></span> <span data-ttu-id="e2cec-108">首先使用硬编码的用户名和密码测试服务。</span><span class="sxs-lookup"><span data-stu-id="e2cec-108">You will start by using a hard-coded user name and password to test the service.</span></span> <span data-ttu-id="e2cec-109">随后通过在应用程序配置中将一个登录窗体指定为凭据提供程序，来添加该窗体。</span><span class="sxs-lookup"><span data-stu-id="e2cec-109">You will then add a login form by specifying it as a credentials provider in your application configuration.</span></span>  
  
-   <span data-ttu-id="e2cec-110">添加基于角色的功能，从而仅对具有“manager”角色的用户启用并显示一个按钮。</span><span class="sxs-lookup"><span data-stu-id="e2cec-110">Add role-based functionality, enabling and displaying a button only for users in the "manager" role.</span></span>  
  
-   <span data-ttu-id="e2cec-111">访问 Web 设置。</span><span class="sxs-lookup"><span data-stu-id="e2cec-111">Access Web settings.</span></span> <span data-ttu-id="e2cec-112">首先在项目设计器的 **“设置”** 页上加载经过身份验证（测试）的用户的 Web 设置。</span><span class="sxs-lookup"><span data-stu-id="e2cec-112">You will start by loading Web settings for an authenticated (test) user on the **Settings** page of the project designer.</span></span> <span data-ttu-id="e2cec-113">随后使用 Windows 窗体设计器将文本框绑定到 Web 设置。</span><span class="sxs-lookup"><span data-stu-id="e2cec-113">You will then use the Windows Forms Designer to bind a text box to a Web setting.</span></span> <span data-ttu-id="e2cec-114">最后，将修改的值保存回服务器。</span><span class="sxs-lookup"><span data-stu-id="e2cec-114">Finally, you will save the modified value back to the server.</span></span>  
  
-   <span data-ttu-id="e2cec-115">实现注销。</span><span class="sxs-lookup"><span data-stu-id="e2cec-115">Implement logout.</span></span> <span data-ttu-id="e2cec-116">向窗体中添加一个注销选项，并调用一个注销方法。</span><span class="sxs-lookup"><span data-stu-id="e2cec-116">You will add a logout option to the form and call a logout method.</span></span>  
  
-   <span data-ttu-id="e2cec-117">启用脱机模式。</span><span class="sxs-lookup"><span data-stu-id="e2cec-117">Enable offline mode.</span></span> <span data-ttu-id="e2cec-118">提供一个复选框，以便用户可以指定其连接状态。</span><span class="sxs-lookup"><span data-stu-id="e2cec-118">You will provide a check box so that users can specify their connection status.</span></span> <span data-ttu-id="e2cec-119">随后使用此值指定客户端应用程序服务提供程序是否使用本地缓存的数据而不是访问其 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="e2cec-119">You will then use this value to specify whether the client application service providers will use locally cached data instead of accessing their Web services.</span></span> <span data-ttu-id="e2cec-120">最后，在应用程序返回联机模式时对当前用户重新进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="e2cec-120">Finally, you will re-authenticate the current user when the application returns to online mode.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e2cec-121">系统必备</span><span class="sxs-lookup"><span data-stu-id="e2cec-121">Prerequisites</span></span>  
 <span data-ttu-id="e2cec-122">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="e2cec-122">You need the following component to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_orcas_long](../../../includes/vs-orcas-long-md.md)]<span data-ttu-id="e2cec-123">。</span><span class="sxs-lookup"><span data-stu-id="e2cec-123">.</span></span>  
  
## <a name="creating-the-client-application"></a><span data-ttu-id="e2cec-124">创建客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="e2cec-124">Creating the Client Application</span></span>  
 <span data-ttu-id="e2cec-125">将执行的第一个操作是创建一个 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="e2cec-125">The first thing that you will do is create a Windows Forms project.</span></span> <span data-ttu-id="e2cec-126">本演练使用 Windows 窗体，因为更多的人熟悉它，不过过程类似于 Windows Presentation Foundation (WPF) 项目。</span><span class="sxs-lookup"><span data-stu-id="e2cec-126">This walkthrough uses Windows Forms because more people are familiar with it, but the process is similar for Windows Presentation Foundation (WPF) projects.</span></span>  
  
#### <a name="to-create-a-client-application-and-enable-client-application-services"></a><span data-ttu-id="e2cec-127">创建客户端应用程序和启用客户端应用程序服务</span><span class="sxs-lookup"><span data-stu-id="e2cec-127">To create a client application and enable client application services</span></span>  
  
1.  <span data-ttu-id="e2cec-128">在 Visual Studio 中，依次选择“文件”&#124;“新建”&#124;“项目”菜单选项。</span><span class="sxs-lookup"><span data-stu-id="e2cec-128">In Visual Studio, select the **File &#124; New &#124; Project** menu option.</span></span>  
  
2.  <span data-ttu-id="e2cec-129">在“新建项目”对话框的“项目类型”窗格中，展开“Visual Basic”或“Visual C#”节点，然后选择“Windows”项目类型。</span><span class="sxs-lookup"><span data-stu-id="e2cec-129">In the **New Project** dialog box, in the **Project types** pane, expand the **Visual Basic** or **Visual C#** node and select the **Windows** project type.</span></span>  
  
3.  <span data-ttu-id="e2cec-130">确保选择 **“.NET Framework 3.5”** ，然后选择 **“Windows 窗体应用程序”** 模板。</span><span class="sxs-lookup"><span data-stu-id="e2cec-130">Make sure that **.NET Framework 3.5** is selected, and then select the **Windows Forms Application** template.</span></span>  
  
4.  <span data-ttu-id="e2cec-131">将项目 **“名称”** 更改为 `ClientAppServicesDemo`，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-131">Change the project **Name** to `ClientAppServicesDemo`, and then click **OK**.</span></span>  
  
     <span data-ttu-id="e2cec-132">此时，新 Windows 窗体项目在 Visual Studio 中打开。</span><span class="sxs-lookup"><span data-stu-id="e2cec-132">A new Windows Forms project is opened in Visual Studio.</span></span>  
  
5.  <span data-ttu-id="e2cec-133">在 **“项目”** 菜单上，选择 **“ClientAppServicesDemo 属性”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-133">On the **Project** menu, select **ClientAppServicesDemo Properties**.</span></span>  
  
     <span data-ttu-id="e2cec-134">项目设计器随即出现。</span><span class="sxs-lookup"><span data-stu-id="e2cec-134">The project designer appears.</span></span>  
  
6.  <span data-ttu-id="e2cec-135">在 **“服务”** 选项卡上，选择 **“启用客户端应用程序服务”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-135">On the **Services** tab, select **Enable client application services**.</span></span>  
  
7.  <span data-ttu-id="e2cec-136">确保选择 **“使用 Forms 身份验证”** ，然后将 **“身份验证服务位置”**、 **“角色服务位置”** 和 **“Web 设置服务位置”** 设置为 `http://localhost:55555/AppServices`。</span><span class="sxs-lookup"><span data-stu-id="e2cec-136">Make sure that **Use Forms authentication** is selected, and then set **Authentication service location**, **Roles service location**, and **Web settings service location** to `http://localhost:55555/AppServices`.</span></span>  
  
8.  <span data-ttu-id="e2cec-137">对于 Visual Basic，在“应用程序”选项卡上，将“身份验证模式”设置为“由应用程序定义”。</span><span class="sxs-lookup"><span data-stu-id="e2cec-137">For Visual Basic, on the **Application** tab, set **Authentication mode** to **Application-defined**.</span></span>  
  
 <span data-ttu-id="e2cec-138">设计器会将指定设置存储在应用程序的 app.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="e2cec-138">The designer stores the specified settings in the application's app.config file.</span></span>  
  
 <span data-ttu-id="e2cec-139">此时，应用程序配置为从同一个主机访问所有三个服务。</span><span class="sxs-lookup"><span data-stu-id="e2cec-139">At this point, the application is configured to access all three services from the same host.</span></span> <span data-ttu-id="e2cec-140">在下一部分中，你会以简单 Web 服务应用程序的形式创建主机，从而使你可以测试客户端配置。</span><span class="sxs-lookup"><span data-stu-id="e2cec-140">In the next section, you will create the host as a simple Web service application, enabling you to test your client configuration.</span></span>  
  
## <a name="creating-the-application-services-host"></a><span data-ttu-id="e2cec-141">创建应用程序服务主机</span><span class="sxs-lookup"><span data-stu-id="e2cec-141">Creating the Application Services Host</span></span>  
 <span data-ttu-id="e2cec-142">在本部分中，你会创建一个简单 Web 服务应用程序，该应用程序从本地 SQL Server Compact 数据库文件访问用户数据。</span><span class="sxs-lookup"><span data-stu-id="e2cec-142">In this section, you will create a simple Web service application that accesses user data from a local SQL Server Compact database file.</span></span> <span data-ttu-id="e2cec-143">然后，你将使用 [ASP.NET Web Site Administration Tool](http://msdn.microsoft.com/library/100ddd8b-7d11-4df9-91ef-0bbbe92e5aec)填充数据库。</span><span class="sxs-lookup"><span data-stu-id="e2cec-143">Then, you will populate the database using the [ASP.NET Web Site Administration Tool](http://msdn.microsoft.com/library/100ddd8b-7d11-4df9-91ef-0bbbe92e5aec).</span></span> <span data-ttu-id="e2cec-144">通过这种简单配置可以快速测试客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="e2cec-144">This simple configuration enables you to quickly test your client application.</span></span> <span data-ttu-id="e2cec-145">作为替代方法，可以配置 Web 服务主机以从完整 SQL Server 数据库或通过自定义 <xref:System.Web.Security.MembershipProvider> 和 <xref:System.Web.Security.RoleProvider> 类访问用户数据。</span><span class="sxs-lookup"><span data-stu-id="e2cec-145">As an alternative, you can configure the Web service host to access user data from a full SQL Server database or through custom <xref:System.Web.Security.MembershipProvider> and <xref:System.Web.Security.RoleProvider> classes.</span></span> <span data-ttu-id="e2cec-146">有关详细信息，请参阅 [Creating and Configuring the Application Services Database for SQL Server](http://msdn.microsoft.com/library/ab894e83-7e2f-4af8-a116-b1bff8f815b2)。</span><span class="sxs-lookup"><span data-stu-id="e2cec-146">For more information, see [Creating and Configuring the Application Services Database for SQL Server](http://msdn.microsoft.com/library/ab894e83-7e2f-4af8-a116-b1bff8f815b2).</span></span>  
  
 <span data-ttu-id="e2cec-147">在下面的过程中，会创建和配置 AppServices Web 服务。</span><span class="sxs-lookup"><span data-stu-id="e2cec-147">In the following procedure, you create and configure the AppServices Web service.</span></span>  
  
#### <a name="to-create-and-configure-the-application-services-host"></a><span data-ttu-id="e2cec-148">创建和配置应用程序服务主机</span><span class="sxs-lookup"><span data-stu-id="e2cec-148">To create and configure the application services host</span></span>  
  
1.  <span data-ttu-id="e2cec-149">在“解决方案资源管理器”中，选择 ClientAppServicesDemo 解决方案，然后在“文件”菜单上，选择“添加”|“新建项目”。</span><span class="sxs-lookup"><span data-stu-id="e2cec-149">In **Solution Explorer**, select the ClientAppServicesDemo solution, and then on the **File** menu, select **Add &#124; New Project**.</span></span>  
  
2.  <span data-ttu-id="e2cec-150">在“添加新项目”对话框的“项目类型”窗格中，展开“Visual Basic”或“Visual C#”节点，然后选择“Web”项目类型。</span><span class="sxs-lookup"><span data-stu-id="e2cec-150">In the **Add New Project** dialog box, in the **Project types** pane, expand the **Visual Basic** or **Visual C#** node and select the **Web** project type.</span></span>  
  
3.  <span data-ttu-id="e2cec-151">确保选择 **“.NET Framework 3.5”** ，然后选择 **“ASP.NET Web 服务应用程序”** 模板。</span><span class="sxs-lookup"><span data-stu-id="e2cec-151">Make sure that **.NET Framework 3.5** is selected, and then select the **ASP.NET Web Service Application** template.</span></span>  
  
4.  <span data-ttu-id="e2cec-152">将项目 **“名称”** 更改为 `AppServices` ，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-152">Change the project **Name** to `AppServices` and then click **OK**.</span></span>  
  
     <span data-ttu-id="e2cec-153">一个新 ASP.NET Web 服务应用程序项目随即添加到解决方案中，并且 Service1.asmx.vb 或 Service1.asmx.cs 文件会出现在编辑器中。</span><span class="sxs-lookup"><span data-stu-id="e2cec-153">A new ASP.NET Web service application project is added to the solution, and the Service1.asmx.vb or Service1.asmx.cs file appears in the editor.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e2cec-154">此示例中不使用 Service1.asmx.vb 或 Service1.asmx.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="e2cec-154">The Service1.asmx.vb or Service1.asmx.cs file is not used in this example.</span></span> <span data-ttu-id="e2cec-155">如果要使工作环境整洁，可以关闭它，并从 **“解决方案资源管理器”** 中删除。</span><span class="sxs-lookup"><span data-stu-id="e2cec-155">If you want to keep your work environment uncluttered, you can close it and delete it from **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="e2cec-156">在 **“解决方案资源管理器”** 中，选择 AppServices 项目，然后在 **“项目”** 菜单上，选择 **“AppServices 属性”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-156">In **Solution Explorer**, select the AppServices project, and then on the **Project** menu, select **AppServices Properties**.</span></span>  
  
     <span data-ttu-id="e2cec-157">项目设计器随即出现。</span><span class="sxs-lookup"><span data-stu-id="e2cec-157">The project designer appears.</span></span>  
  
6.  <span data-ttu-id="e2cec-158">在 **“Web”** 选项卡上，确保选择 **“使用 Visual Studio 开发服务器”** 。</span><span class="sxs-lookup"><span data-stu-id="e2cec-158">On the **Web** tab, make sure that **Use Visual Studio Development Server** is selected.</span></span>  
  
7.  <span data-ttu-id="e2cec-159">选择 **“特定端口”**，指定值 `55555`，然后将 **“虚拟路径”** 设置为 `/AppServices`。</span><span class="sxs-lookup"><span data-stu-id="e2cec-159">Select **Specific port**, specify a value of `55555`, and then set **Virtual path** to `/AppServices`.</span></span>  
  
8.  <span data-ttu-id="e2cec-160">保存所有文件。</span><span class="sxs-lookup"><span data-stu-id="e2cec-160">Save all files.</span></span>  
  
9. <span data-ttu-id="e2cec-161">在 **“解决方案资源管理器”** 中，打开 Web.config 并找到 `<system.web>` 开始标记。</span><span class="sxs-lookup"><span data-stu-id="e2cec-161">In **Solution Explorer**, open Web.config and find the `<system.web>` opening tag.</span></span>  
  
10. <span data-ttu-id="e2cec-162">在 `<system.web>` 标记之前添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="e2cec-162">Add the following markup before the `<system.web>` tag.</span></span>  
  
     <span data-ttu-id="e2cec-163">此标记中的 `authenticationService`、 `profileService`和 `roleService` 元素会启用并配置应用程序服务。</span><span class="sxs-lookup"><span data-stu-id="e2cec-163">The `authenticationService`, `profileService`, and `roleService` elements in this markup enable and configure the application services.</span></span> <span data-ttu-id="e2cec-164">为进行测试， `requireSSL` 元素的 `authenticationService` 特性设置为“false”。</span><span class="sxs-lookup"><span data-stu-id="e2cec-164">For testing purposes, the `requireSSL` attribute of the `authenticationService` element is set to "false".</span></span> <span data-ttu-id="e2cec-165">`readAccessProperties` 元素的 `writeAccessProperties` 和 `profileService` 特性指示 `WebSettingsTestText` 属性为读/写。</span><span class="sxs-lookup"><span data-stu-id="e2cec-165">The `readAccessProperties` and `writeAccessProperties` attributes of the `profileService` element indicate that the `WebSettingsTestText` property is read/write.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e2cec-166">在生产代码中，应始终通过安全套接字层（SSL，使用 HTTPS 协议）访问身份验证服务。</span><span class="sxs-lookup"><span data-stu-id="e2cec-166">In production code, you should always access the authentication service over the secure sockets layer (SSL, by using the HTTPS protocol).</span></span> <span data-ttu-id="e2cec-167">有关如何设置 SSL 的信息，请参阅 [配置安全套接字层（IIS 6.0 操作指南）](http://go.microsoft.com/fwlink/?LinkId=91844)。</span><span class="sxs-lookup"><span data-stu-id="e2cec-167">For information about how to set up SSL, see [Configuring Secure Sockets Layer (IIS 6.0 Operations Guide)](http://go.microsoft.com/fwlink/?LinkId=91844).</span></span>  
  
    ```xml  
    <system.web.extensions>  
      <scripting>  
        <webServices>  
          <authenticationService enabled="true" requireSSL = "false"/>  
          <profileService enabled="true"  
            readAccessProperties="WebSettingsTestText"  
            writeAccessProperties="WebSettingsTestText" />  
          <roleService enabled="true"/>  
        </webServices>  
      </scripting>  
    </system.web.extensions>  
    ```  
  
11. <span data-ttu-id="e2cec-168">在 `<system.web>` 开始标记之后添加以下标记，以便它位于 `<system.web>` 元素中。</span><span class="sxs-lookup"><span data-stu-id="e2cec-168">Add the following markup after the `<system.web>` opening tag so that it is within the `<system.web>` element.</span></span>  
  
     <span data-ttu-id="e2cec-169">`profile` 元素会配置一个名为 `WebSettingsTestText`的 Web 设置。</span><span class="sxs-lookup"><span data-stu-id="e2cec-169">The `profile` element configures a single Web setting named `WebSettingsTestText`.</span></span>  
  
    ```xml  
    <profile enabled="true" >  
      <properties>  
        <add name="WebSettingsTestText" type="string"   
          readOnly="false" defaultValue="DefaultText"   
          serializeAs="String" allowAnonymous="false" />  
      </properties>  
    </profile>  
    ```  
  
 <span data-ttu-id="e2cec-170">在下面的过程中，会使用 ASP.NET 网站管理工具完成服务配置并填充本地数据库文件。</span><span class="sxs-lookup"><span data-stu-id="e2cec-170">In the following procedure, you use the ASP.NET Web Site Administration tool to complete the service configuration and populate the local database file.</span></span> <span data-ttu-id="e2cec-171">将添加两个名为 `employee` 和 `manager` 的用户，它们属于两个具有相同名称的角色。</span><span class="sxs-lookup"><span data-stu-id="e2cec-171">You will add two users named `employee` and `manager` belonging to two roles with the same names.</span></span> <span data-ttu-id="e2cec-172">用户密码分别为 `employee!` 和 `manager!` 。</span><span class="sxs-lookup"><span data-stu-id="e2cec-172">The user passwords are `employee!` and `manager!` respectively.</span></span>  
  
#### <a name="to-configure-membership-and-roles"></a><span data-ttu-id="e2cec-173">配置成员资格和角色</span><span class="sxs-lookup"><span data-stu-id="e2cec-173">To configure membership and roles</span></span>  
  
1.  <span data-ttu-id="e2cec-174">在 **“解决方案资源管理器”** 中，选择 AppServices 项目，然后在 **“项目”** 菜单上，选择 **“ASP.NET 配置”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-174">In **Solution Explorer**, select the AppServices project, and then on the **Project** menu, select **ASP.NET Configuration**.</span></span>  
  
     <span data-ttu-id="e2cec-175">**“ASP.NET 网站管理工具”** 随即出现。</span><span class="sxs-lookup"><span data-stu-id="e2cec-175">The **ASP.NET Web Site Administration Tool** appears.</span></span>  
  
2.  <span data-ttu-id="e2cec-176">在 **“安全”** 选项卡上，单击 **“使用安全设置向导按部就班地配置安全性”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-176">On the **Security** tab, click **Use the security Setup Wizard to configure security step by step**.</span></span>  
  
     <span data-ttu-id="e2cec-177">**“安全设置向导”** 随即出现并显示 **“欢迎使用”** 步骤。</span><span class="sxs-lookup"><span data-stu-id="e2cec-177">The **Security Setup Wizard** appears and displays the **Welcome** step.</span></span>  
  
3.  <span data-ttu-id="e2cec-178">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-178">Click **Next**.</span></span>  
  
     <span data-ttu-id="e2cec-179">**“选择访问方法”** 步骤随即出现。</span><span class="sxs-lookup"><span data-stu-id="e2cec-179">The **Select Access Method** step appears.</span></span>  
  
4.  <span data-ttu-id="e2cec-180">选择 **“通过 Internet”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-180">Select **From the internet**.</span></span> <span data-ttu-id="e2cec-181">这会将服务配置为使用 Forms 身份验证，而不是 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="e2cec-181">This configures the service to use Forms authentication instead of Windows authentication.</span></span>  
  
5.  <span data-ttu-id="e2cec-182">单击两次 **“下一步”** 。</span><span class="sxs-lookup"><span data-stu-id="e2cec-182">Click **Next** twice.</span></span>  
  
     <span data-ttu-id="e2cec-183">**“定义角色”** 步骤随即出现。</span><span class="sxs-lookup"><span data-stu-id="e2cec-183">The **Define Roles** step appears.</span></span>  
  
6.  <span data-ttu-id="e2cec-184">选择 **“为此网站启用角色”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-184">Select **Enable roles for this Web site**.</span></span>  
  
7.  <span data-ttu-id="e2cec-185">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-185">Click **Next**.</span></span> <span data-ttu-id="e2cec-186">**“创建新角色”** 窗体随即出现。</span><span class="sxs-lookup"><span data-stu-id="e2cec-186">The **Create New Role** form appears.</span></span>  
  
8.  <span data-ttu-id="e2cec-187">在 **“新角色名称”** 文本框中，输入 `manager` ，然后单击 **“添加角色”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-187">In the **New Role Name** text box, type `manager` and then click **Add Role**.</span></span>  
  
     <span data-ttu-id="e2cec-188">**“现有角色”** 表随即出现，其中包含指定值。</span><span class="sxs-lookup"><span data-stu-id="e2cec-188">The **Existing Roles** table appears with the specified value.</span></span>  
  
9. <span data-ttu-id="e2cec-189">在 **“新角色名称”** 文本框中，将 `manager` 替换为 `employee` ，然后单击 **“添加角色”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-189">In the **New Role Name** text box, replace `manager` with `employee` and then click **Add Role**.</span></span>  
  
     <span data-ttu-id="e2cec-190">新值随即出现在 **“现有角色”** 表。</span><span class="sxs-lookup"><span data-stu-id="e2cec-190">The new value appears in the **Existing Roles** table.</span></span>  
  
10. <span data-ttu-id="e2cec-191">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-191">Click **Next**.</span></span>  
  
     <span data-ttu-id="e2cec-192">**“添加新用户”** 步骤随即出现。</span><span class="sxs-lookup"><span data-stu-id="e2cec-192">The **Add New Users** step appears.</span></span>  
  
11. <span data-ttu-id="e2cec-193">在 **“创建用户”** 窗体中，指定以下值。</span><span class="sxs-lookup"><span data-stu-id="e2cec-193">In the **Create User** form, specify the following values.</span></span>  
  
  	|||  
  	|-|-|  
  	|<span data-ttu-id="e2cec-194">**用户名**</span><span class="sxs-lookup"><span data-stu-id="e2cec-194">**User Name**</span></span>|`manager`|  
  	|<span data-ttu-id="e2cec-195">**密码**</span><span class="sxs-lookup"><span data-stu-id="e2cec-195">**Password**</span></span>|`manager!`|  
  	|<span data-ttu-id="e2cec-196">**确认密码**</span><span class="sxs-lookup"><span data-stu-id="e2cec-196">**Confirm Password**</span></span>|`manager!`|  
  	|<span data-ttu-id="e2cec-197">**电子邮件**</span><span class="sxs-lookup"><span data-stu-id="e2cec-197">**Email**</span></span>|`manager@contoso.com`|  
  	|<span data-ttu-id="e2cec-198">**安全提示问题**</span><span class="sxs-lookup"><span data-stu-id="e2cec-198">**Security Question**</span></span>|`manager`|  
  	|<span data-ttu-id="e2cec-199">**安全提示问题的答案**</span><span class="sxs-lookup"><span data-stu-id="e2cec-199">**Security Answer**</span></span>|`manager`|  
  
12. <span data-ttu-id="e2cec-200">单击 **“创建用户”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-200">Click **Create User**.</span></span>  
  
     <span data-ttu-id="e2cec-201">一条成功消息随即出现。</span><span class="sxs-lookup"><span data-stu-id="e2cec-201">A success message appears.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e2cec-202">窗体需要有“电子邮件”、“安全性问题”和“安全性问题答案”值，但本示例没有使用。</span><span class="sxs-lookup"><span data-stu-id="e2cec-202">The **Email**, **Security Question**, and **Security Answer** values are required by the form, but are not used in this example.</span></span>  
  
13. <span data-ttu-id="e2cec-203">单击 **“继续”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-203">Click **Continue**.</span></span>  
  
     <span data-ttu-id="e2cec-204">**“创建用户”** 窗体随即再次显示。</span><span class="sxs-lookup"><span data-stu-id="e2cec-204">The **Create User** form reappears.</span></span>  
  
14. <span data-ttu-id="e2cec-205">在 **“创建用户”** 窗体中，指定以下值。</span><span class="sxs-lookup"><span data-stu-id="e2cec-205">In the **Create User** form, specify the following values.</span></span>  
  
  	|||  
  	|-|-|  
  	|<span data-ttu-id="e2cec-206">**用户名**</span><span class="sxs-lookup"><span data-stu-id="e2cec-206">**User Name**</span></span>|`employee`|  
  	|<span data-ttu-id="e2cec-207">**密码**</span><span class="sxs-lookup"><span data-stu-id="e2cec-207">**Password**</span></span>|`employee!`|  
  	|<span data-ttu-id="e2cec-208">**确认密码**</span><span class="sxs-lookup"><span data-stu-id="e2cec-208">**Confirm Password**</span></span>|`employee!`|  
  	|<span data-ttu-id="e2cec-209">**电子邮件**</span><span class="sxs-lookup"><span data-stu-id="e2cec-209">**Email**</span></span>|`employee@contoso.com`|  
  	|<span data-ttu-id="e2cec-210">**安全提示问题**</span><span class="sxs-lookup"><span data-stu-id="e2cec-210">**Security Question**</span></span>|`Employee`|  
  	|<span data-ttu-id="e2cec-211">**安全提示问题的答案**</span><span class="sxs-lookup"><span data-stu-id="e2cec-211">**Security Answer**</span></span>|`employee`|  
  
15. <span data-ttu-id="e2cec-212">单击 **“创建用户”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-212">Click **Create User**.</span></span>  
  
     <span data-ttu-id="e2cec-213">一条成功消息随即出现。</span><span class="sxs-lookup"><span data-stu-id="e2cec-213">A success message appears.</span></span>  
  
16. <span data-ttu-id="e2cec-214">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-214">Click **Finish**.</span></span>  
  
     <span data-ttu-id="e2cec-215">**“网站管理工具”** 随即再次出现。</span><span class="sxs-lookup"><span data-stu-id="e2cec-215">The **Web Site Administration Tool** reappears.</span></span>  
  
17. <span data-ttu-id="e2cec-216">单击 **“管理用户”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-216">Click **Manager users**.</span></span>  
  
     <span data-ttu-id="e2cec-217">用户列表随即出现。</span><span class="sxs-lookup"><span data-stu-id="e2cec-217">The list of users appears.</span></span>  
  
18. <span data-ttu-id="e2cec-218">对 **“employee”** 用户单击 **“编辑角色”** ，然后选择 **“employee”** 角色。</span><span class="sxs-lookup"><span data-stu-id="e2cec-218">Click **Edit roles** for the **employee** user, and then select the **employee** role.</span></span>  
  
19. <span data-ttu-id="e2cec-219">对 **“manager”** 用户单击 **“编辑角色”** ，然后选择 **“manager”** 角色。</span><span class="sxs-lookup"><span data-stu-id="e2cec-219">Click **Edit roles** for the **manager** user, and then select the **manager** role.</span></span>  
  
20. <span data-ttu-id="e2cec-220">关闭承载 **“网站管理工具”** 的浏览器窗口。</span><span class="sxs-lookup"><span data-stu-id="e2cec-220">Close the browser window that hosts the **Web Site Administration Tool**.</span></span>  
  
21. <span data-ttu-id="e2cec-221">如果一个消息框出现，询问是否要重载修改后的 Web.config 文件，请单击 **“是”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-221">If a message box appears asking if you want to reload the modified Web.config file, click **Yes**.</span></span>  
  
 <span data-ttu-id="e2cec-222">这会完成 Web 服务设置。</span><span class="sxs-lookup"><span data-stu-id="e2cec-222">This completes the Web service setup.</span></span> <span data-ttu-id="e2cec-223">此时，可以按 F5 以运行客户端应用程序， **“ASP.NET Development Server”** 会随客户端应用程序自动启动。</span><span class="sxs-lookup"><span data-stu-id="e2cec-223">At this point, you can press F5 to run the client application, and the **ASP.NET Development Server** will start automatically along with your client application.</span></span> <span data-ttu-id="e2cec-224">该服务器会在你退出应用程序之后继续运行，但是会在你重新启动应用程序时重新启动。</span><span class="sxs-lookup"><span data-stu-id="e2cec-224">The server will continue to run after you exit the application, but will restart when you restart the application.</span></span> <span data-ttu-id="e2cec-225">这使它可以检测对 Web.config 进行的任何更改。</span><span class="sxs-lookup"><span data-stu-id="e2cec-225">This allows it to detect any changes you have made to Web.config.</span></span>  
  
 <span data-ttu-id="e2cec-226">若要手动停止服务器，请在任务栏的通知区域中右键单击“ASP.NET Development Server”图标，然后单击 **“停止”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-226">To stop the server manually, right-click the ASP.NET Development Server icon in the notification area of the taskbar and then click **Stop**.</span></span> <span data-ttu-id="e2cec-227">这有时可用于确保进行正常的重新启动。</span><span class="sxs-lookup"><span data-stu-id="e2cec-227">This is useful occasionally to make sure that a clean restart occurs.</span></span>  
  
## <a name="adding-forms-authentication"></a><span data-ttu-id="e2cec-228">添加 Forms 身份验证</span><span class="sxs-lookup"><span data-stu-id="e2cec-228">Adding Forms Authentication</span></span>  
 <span data-ttu-id="e2cec-229">在下面的过程中，会将代码添加到主窗体，该代码会尝试验证用户，并在用户提供的凭据无效时拒绝访问。</span><span class="sxs-lookup"><span data-stu-id="e2cec-229">In the following procedure, you add code to the main form that attempts to validate the user, and denies access when the user supplies invalid credentials.</span></span> <span data-ttu-id="e2cec-230">使用硬编码的用户名和密码测试服务。</span><span class="sxs-lookup"><span data-stu-id="e2cec-230">You use a hard-coded user name and password to test the service.</span></span>  
  
#### <a name="to-validate-the-user-in-your-application-code"></a><span data-ttu-id="e2cec-231">在应用程序代码中验证用户</span><span class="sxs-lookup"><span data-stu-id="e2cec-231">To validate the user in your application code</span></span>  
  
1.  <span data-ttu-id="e2cec-232">在“解决方案资源管理器”的 ClientAppServicesDemo 项目中，添加对 System.Web 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="e2cec-232">In **Solution Explorer**, in the ClientAppServicesDemo project, add a reference to the System.Web assembly.</span></span>  
  
2.  <span data-ttu-id="e2cec-233">选择“Form1”文件，再依次选择 Visual Studio 主菜单中的“视图”&#124;“代码”。</span><span class="sxs-lookup"><span data-stu-id="e2cec-233">Select the Form1 file and then select **View &#124; Code** from the Visual Studio main menu.</span></span>  
  
3.  <span data-ttu-id="e2cec-234">在代码编辑器中，将以下语句添加到 Form1 文件顶部：</span><span class="sxs-lookup"><span data-stu-id="e2cec-234">In the code editor, add the following statements to the top of the Form1 file.</span></span>  
  
     [!code-csharp[ClientApplicationServices#001](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#001)]
     [!code-vb[ClientApplicationServices#001](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#001)]  
  
4.  <span data-ttu-id="e2cec-235">在 **“解决方案资源管理器”** 中，双击 Form1 以显示设计器。</span><span class="sxs-lookup"><span data-stu-id="e2cec-235">In **Solution Explorer**, double-click Form1 to display the designer.</span></span>  
  
5.  <span data-ttu-id="e2cec-236">在设计器中，双击窗体图面，以生成名为 <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType> 的 `Form1_Load`事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e2cec-236">In the designer, double-click the form surface to generate a <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType> event handler named `Form1_Load`.</span></span>  
  
     <span data-ttu-id="e2cec-237">代码编辑器随即出现，光标位于 `Form1_Load` 方法中。</span><span class="sxs-lookup"><span data-stu-id="e2cec-237">The code editor appears with the cursor in the `Form1_Load` method.</span></span>  
  
6.  <span data-ttu-id="e2cec-238">将以下代码添加到 `Form1_Load` 方法中。</span><span class="sxs-lookup"><span data-stu-id="e2cec-238">Add the following code to the `Form1_Load` method.</span></span>  
  
     <span data-ttu-id="e2cec-239">此代码通过退出应用程序，对未通过身份验证的用户拒绝访问。</span><span class="sxs-lookup"><span data-stu-id="e2cec-239">This code denies access to unauthenticated users by exiting the application.</span></span> <span data-ttu-id="e2cec-240">或者，可以允许未通过身份验证的用户访问窗体，但拒绝对特定功能的访问。</span><span class="sxs-lookup"><span data-stu-id="e2cec-240">Alternatively, you could allow unauthenticated users access to the form, but deny access to specific functionality.</span></span> <span data-ttu-id="e2cec-241">通常不会像这样对用户名和密码进行硬编码，但对于测试十分有用。</span><span class="sxs-lookup"><span data-stu-id="e2cec-241">Normally, you will not hard-code the user name and password like this, but it is useful for testing purposes.</span></span> <span data-ttu-id="e2cec-242">在下一部分中，你会将此代码替换为显示登录对话框并包含异常处理的更可靠代码。</span><span class="sxs-lookup"><span data-stu-id="e2cec-242">In the next section, you will replace this code with more robust code that displays a login dialog box and includes exception handling.</span></span>  
  
     <span data-ttu-id="e2cec-243">请注意， `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> 方法处于 [!INCLUDE[dnprdnext](../../../includes/dnprdnext-md.md)]中。</span><span class="sxs-lookup"><span data-stu-id="e2cec-243">Note that the `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> method is in the [!INCLUDE[dnprdnext](../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="e2cec-244">此方法将其工作委托给配置的身份验证提供程序，并在身份验证成功时返回 `true` 。</span><span class="sxs-lookup"><span data-stu-id="e2cec-244">This method delegates its work to the configured authentication provider, and returns `true` if authentication is successful.</span></span> <span data-ttu-id="e2cec-245">应用程序不需要直接引用客户端身份验证提供程序。</span><span class="sxs-lookup"><span data-stu-id="e2cec-245">Your application does not require a direct reference to the client authentication provider.</span></span>  
  
     [!code-csharp[ClientApplicationServices#300](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#300)]
     [!code-vb[ClientApplicationServices#300](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#300)]  
  
 <span data-ttu-id="e2cec-246">现在可以按 F5 以运行应用程序，因为提供了正确的用户名和密码，所以会看到窗体。</span><span class="sxs-lookup"><span data-stu-id="e2cec-246">You can now press F5 to run the application, and because you provide a correct user name and password, you will see the form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2cec-247">如果无法运行应用程序，请尝试停止 ASP.NET Development Server。</span><span class="sxs-lookup"><span data-stu-id="e2cec-247">If you are unable to run the application, try stopping the ASP.NET Development Server.</span></span> <span data-ttu-id="e2cec-248">该服务器重新启动时，验证该端口是否设置为 55555。</span><span class="sxs-lookup"><span data-stu-id="e2cec-248">When the server restarts, verify that the port is set to 55555.</span></span>  
  
 <span data-ttu-id="e2cec-249">若要改为查看错误消息，请更改 <xref:System.Web.Security.Membership.ValidateUser%2A> 参数。</span><span class="sxs-lookup"><span data-stu-id="e2cec-249">To see the error message instead, change the <xref:System.Web.Security.Membership.ValidateUser%2A> parameters.</span></span> <span data-ttu-id="e2cec-250">例如，将第二个 `"manager!"` 参数替换为不正确的密码（如 `"MANAGER"`）。</span><span class="sxs-lookup"><span data-stu-id="e2cec-250">For example, replace the second `"manager!"` parameter with an incorrect password like `"MANAGER"`.</span></span>  
  
## <a name="adding-a-login-form-as-a-credentials-provider"></a><span data-ttu-id="e2cec-251">添加一个登录窗体作为凭据提供程序</span><span class="sxs-lookup"><span data-stu-id="e2cec-251">Adding a Login Form as a Credentials Provider</span></span>  
 <span data-ttu-id="e2cec-252">可以在应用程序代码中获取用户凭据，并将它们传递给 <xref:System.Web.Security.Membership.ValidateUser%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="e2cec-252">You can acquire the user credentials in your application code and pass them to the <xref:System.Web.Security.Membership.ValidateUser%2A> method.</span></span> <span data-ttu-id="e2cec-253">但是，使凭据获取代码独立于应用程序代码通常会十分有用，以免你以后要更改它。</span><span class="sxs-lookup"><span data-stu-id="e2cec-253">However, it is often useful to keep your credentials-acquiring code separate from your application code, in case you want to change it later.</span></span>  
  
 <span data-ttu-id="e2cec-254">在下面的过程中，会将应用程序配置为使用凭据提供程序，然后更改 <xref:System.Web.Security.Membership.ValidateUser%2A> 方法调用以便为两个参数传递 <xref:System.String.Empty> 。</span><span class="sxs-lookup"><span data-stu-id="e2cec-254">In the following procedure, you configure your application to use a credentials provider, and then change your <xref:System.Web.Security.Membership.ValidateUser%2A> method call to pass <xref:System.String.Empty> for both parameters.</span></span> <span data-ttu-id="e2cec-255">空字符串指示 <xref:System.Web.Security.Membership.ValidateUser%2A> 方法调用配置的凭据提供程序的 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="e2cec-255">The empty strings signal the <xref:System.Web.Security.Membership.ValidateUser%2A> method to call the <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> method of the configured credentials provider.</span></span>  
  
#### <a name="to-configure-your-application-to-use-a-credentials-provider"></a><span data-ttu-id="e2cec-256">将应用程序配置为使用凭据提供程序</span><span class="sxs-lookup"><span data-stu-id="e2cec-256">To configure your application to use a credentials provider</span></span>  
  
1.  <span data-ttu-id="e2cec-257">在 **“解决方案资源管理器”** 中，选择 ClientAppServicesDemo 项目，然后在 **“项目”** 菜单上，选择 **“ClientAppServicesDemo 属性”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-257">In **Solution Explorer**, select the ClientAppServicesDemo project, and then on the **Project** menu, select **ClientAppServicesDemo Properties**.</span></span>  
  
     <span data-ttu-id="e2cec-258">项目设计器随即出现。</span><span class="sxs-lookup"><span data-stu-id="e2cec-258">The project designer appears.</span></span>  
  
2.  <span data-ttu-id="e2cec-259">在 **“服务”** 选项卡上，将 **“可选: 凭据提供程序”** 设置为以下值。</span><span class="sxs-lookup"><span data-stu-id="e2cec-259">On the **Services** tab, set **Optional: Credential provider** to the following value.</span></span> <span data-ttu-id="e2cec-260">此值指示程序集限定的类型名。</span><span class="sxs-lookup"><span data-stu-id="e2cec-260">This value indicates the assembly-qualified type name.</span></span>  
  
    ```  
    ClientAppServicesDemo.Login, ClientAppServicesDemo  
    ```  
  
3.  <span data-ttu-id="e2cec-261">在 Form1 代码文件中，将 `Form1_Load` 方法中的代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="e2cec-261">In the Form1 code file, replace the code in the `Form1_Load` method with the following code.</span></span>  
  
     <span data-ttu-id="e2cec-262">此代码会显示一条欢迎消息，然后调用会在下一步中添加的 `ValidateUsingCredentialsProvider` 方法。</span><span class="sxs-lookup"><span data-stu-id="e2cec-262">This code displays a welcome message and then calls the `ValidateUsingCredentialsProvider` method that you will add in the next step.</span></span> <span data-ttu-id="e2cec-263">如果用户未通过身份验证，则 `ValidateUsingCredentialsProvider` 方法会返回 `false` ，并且 `Form1_Load` 方法会返回。</span><span class="sxs-lookup"><span data-stu-id="e2cec-263">If the user is not authenticated, the `ValidateUsingCredentialsProvider` method returns `false` and the `Form1_Load` method returns.</span></span> <span data-ttu-id="e2cec-264">这会在应用程序退出之前阻止任何其他代码运行。</span><span class="sxs-lookup"><span data-stu-id="e2cec-264">This prevents any additional code from running before the application exits.</span></span> <span data-ttu-id="e2cec-265">欢迎消息可用于清楚地表明应用程序重新启动。</span><span class="sxs-lookup"><span data-stu-id="e2cec-265">The welcome message is useful to make it clear when the application restarts.</span></span> <span data-ttu-id="e2cec-266">你会在本演练后面实现注销时添加用于重新启动应用程序的代码。</span><span class="sxs-lookup"><span data-stu-id="e2cec-266">You will add code to restart the application when you implement logout later in this walkthrough.</span></span>  
  
     [!code-csharp[ClientApplicationServices#011](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#011)]
     [!code-vb[ClientApplicationServices#011](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#011)]  
  
4.  <span data-ttu-id="e2cec-267">在 `Form1_Load` 方法之后添加以下方法。</span><span class="sxs-lookup"><span data-stu-id="e2cec-267">Add the following method after the `Form1_Load` method.</span></span>  
  
     <span data-ttu-id="e2cec-268">此方法将空字符串传递给 `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> 方法，这会使登录对话框出现。</span><span class="sxs-lookup"><span data-stu-id="e2cec-268">This method passes empty strings to the `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> method, which causes the Login dialog box to appear.</span></span> <span data-ttu-id="e2cec-269">如果身份验证服务不可用，则 <xref:System.Web.Security.Membership.ValidateUser%2A> 方法会引发 <xref:System.Net.WebException>。</span><span class="sxs-lookup"><span data-stu-id="e2cec-269">If the authentication service is unavailable, the <xref:System.Web.Security.Membership.ValidateUser%2A> method will throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="e2cec-270">在这种情况下， `ValidateUsingCredentialsProvider` 方法会显示一条警告消息，并询问用户是否要在脱机模式下重试。</span><span class="sxs-lookup"><span data-stu-id="e2cec-270">In this case, the `ValidateUsingCredentialsProvider` method displays a warning message and asks if the user wants to try again in offline mode.</span></span> <span data-ttu-id="e2cec-271">此功能需要 **How to: Configure Client Application Services** 中介绍的 [“将密码哈希保存在本地以实现脱机登录”](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)功能。</span><span class="sxs-lookup"><span data-stu-id="e2cec-271">This functionality requires the **Save password hash locally to enable offline login** feature described in [How to: Configure Client Application Services](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md).</span></span> <span data-ttu-id="e2cec-272">此功能会在默认情况下为新项目启用。</span><span class="sxs-lookup"><span data-stu-id="e2cec-272">This feature is enabled by default for new projects.</span></span>  
  
     <span data-ttu-id="e2cec-273">如果用户未通过验证，则 `ValidateUsingCredentialsProvider` 方法会显示一条错误消息并退出应用程序。</span><span class="sxs-lookup"><span data-stu-id="e2cec-273">If the user is not validated, the `ValidateUsingCredentialsProvider` method displays an error message and exits the application.</span></span> <span data-ttu-id="e2cec-274">最后，此方法会返回身份验证尝试的结果。</span><span class="sxs-lookup"><span data-stu-id="e2cec-274">Finally, this method returns the result of the authentication attempt.</span></span>  
  
     [!code-csharp[ClientApplicationServices#020](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#020)]
     [!code-vb[ClientApplicationServices#020](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#020)]  
  
### <a name="creating-a-login-form"></a><span data-ttu-id="e2cec-275">创建一个登录窗体</span><span class="sxs-lookup"><span data-stu-id="e2cec-275">Creating a Login Form</span></span>  
 <span data-ttu-id="e2cec-276">凭据提供程序是实现 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> 接口的类。</span><span class="sxs-lookup"><span data-stu-id="e2cec-276">A credentials provider is a class that implements the <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> interface.</span></span> <span data-ttu-id="e2cec-277">此接口具有名为 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> 的单一方法，它返回 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials> 对象。</span><span class="sxs-lookup"><span data-stu-id="e2cec-277">This interface has a single method named <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> that returns a <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials> object.</span></span> <span data-ttu-id="e2cec-278">以下过程介绍如何创建一个登录对话框，它实现 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> 以显示本身并返回用户指定的凭据。</span><span class="sxs-lookup"><span data-stu-id="e2cec-278">The following procedures describe how to create a login dialog box that implements <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> to display itself and return the user-specified credentials.</span></span>  
  
 <span data-ttu-id="e2cec-279">为 Visual Basic 和 C# 提供了单独的过程，因为 Visual Basic 提供“登录窗体”模板。</span><span class="sxs-lookup"><span data-stu-id="e2cec-279">Separate procedures are provided for Visual Basic and C# because Visual Basic provides a **Login Form** template.</span></span> <span data-ttu-id="e2cec-280">这可节省一些时间并减少编码工作。</span><span class="sxs-lookup"><span data-stu-id="e2cec-280">This saves some time and coding effort.</span></span>  
  
##### <a name="to-create-a-login-dialog-box-as-a-credentials-provider-in-visual-basic"></a><span data-ttu-id="e2cec-281">在 Visual Basic 中创建一个登录对话框作为凭据提供程序</span><span class="sxs-lookup"><span data-stu-id="e2cec-281">To create a login dialog box as a credentials provider in Visual Basic</span></span>  
  
1.  <span data-ttu-id="e2cec-282">在 **“解决方案资源管理器”** 中，选择 ClientAppServicesDemo 项目，然后在 **“项目”** 菜单上，选择 **“添加新项”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-282">In **Solution Explorer**, select the ClientAppServicesDemo project, and then on the **Project** menu, select **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="e2cec-283">在 **“添加新项”** 对话框中，选择 **“登录窗体”** 模板，将项 **“名称”** 更改为 `Login.vb`，然后单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-283">In the **Add New Item** dialog box, select the **Login Form** template, change the item **Name** to `Login.vb`, and then click **Add**.</span></span>  
  
     <span data-ttu-id="e2cec-284">登录对话框随即出现在 Windows 窗体设计器中。</span><span class="sxs-lookup"><span data-stu-id="e2cec-284">The login dialog box appears in the Windows Forms Designer.</span></span>  
  
3.  <span data-ttu-id="e2cec-285">在该设计器中，选择 **“确定”** 按钮，然后在 **“属性”** 窗口中，将 `DialogResult` 设置为 `OK`。</span><span class="sxs-lookup"><span data-stu-id="e2cec-285">In the designer, select the **OK** button and then, in the **Properties** window, set `DialogResult` to `OK`.</span></span>  
  
4.  <span data-ttu-id="e2cec-286">在设计器中，在 `CheckBox` “密码” **文本框下将一个** 控件添加到窗体。</span><span class="sxs-lookup"><span data-stu-id="e2cec-286">In the designer, add a `CheckBox` control to the form under the **Password** text box.</span></span>  
  
5.  <span data-ttu-id="e2cec-287">在“属性”窗口中，将“(Name)”值指定为 `rememberMeCheckBox`，并将“Text”值指定为 `&Remember me`。</span><span class="sxs-lookup"><span data-stu-id="e2cec-287">In the **Properties** window, specify a **(Name)** value of `rememberMeCheckBox` and a **Text** value of `&Remember me`.</span></span>  
  
6.  <span data-ttu-id="e2cec-288">依次选择 Visual Studio 主菜单中的“视图”&#124;“代码”。</span><span class="sxs-lookup"><span data-stu-id="e2cec-288">Select **View &#124; Code** from the Visual Studio main menu.</span></span>  
  
7.  <span data-ttu-id="e2cec-289">在代码编辑器中，将以下代码添加到文件顶部：</span><span class="sxs-lookup"><span data-stu-id="e2cec-289">In the code editor, add the following code to the top of the file.</span></span>  
  
     [!code-vb[ClientApplicationServices#101](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Login.vb#101)]  
  
8.  <span data-ttu-id="e2cec-290">修改类签名，以便类实现 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> 接口。</span><span class="sxs-lookup"><span data-stu-id="e2cec-290">Modify the class signature so that the class implements the <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> interface.</span></span>  
  
     [!code-vb[ClientApplicationServices#110](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#110)]  
  
9. <span data-ttu-id="e2cec-291">确保光标位于 `IClientformsAuthenticationCredentialsProvider`之后，然后按 Enter 以生成 `GetCredentials` 方法。</span><span class="sxs-lookup"><span data-stu-id="e2cec-291">Make sure that the cursor is after `IClientformsAuthenticationCredentialsProvider`, and then press ENTER to generate the `GetCredentials` method.</span></span>  
  
10. <span data-ttu-id="e2cec-292">找到 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> 实现，然后将它替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="e2cec-292">Locate the <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> implementation and then replace it with the following code.</span></span>  
  
     [!code-vb[ClientApplicationServices#120](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Login.vb#120)]  
  
 <span data-ttu-id="e2cec-293">下面的 C# 过程为简单登录对话框提供了完整代码清单。</span><span class="sxs-lookup"><span data-stu-id="e2cec-293">The following C# procedure provides the entire code listing for a simple login dialog box.</span></span> <span data-ttu-id="e2cec-294">此对话框的布局有点粗糙，但重要的部分是 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> 实现。</span><span class="sxs-lookup"><span data-stu-id="e2cec-294">The layout for this dialog box is a bit crude, but the important part is the <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> implementation.</span></span>  
  
##### <a name="to-create-a-login-dialog-box-as-a-credentials-provider-in-c"></a><span data-ttu-id="e2cec-295">在 C# 中创建一个登录对话框作为凭据提供程序</span><span class="sxs-lookup"><span data-stu-id="e2cec-295">To create a login dialog box as a credentials provider in C#</span></span>  
  
1.  <span data-ttu-id="e2cec-296">在 **“解决方案资源管理器”** 中，选择 ClientAppServicesDemo 项目，然后在 **“项目”** 菜单上，选择 **“添加类”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-296">In **Solution Explorer**, select the ClientAppServicesDemo project, and then on the **Project** menu, select **Add Class**.</span></span>  
  
2.  <span data-ttu-id="e2cec-297">在 **“添加新项”** 对话框中，将 **“名称”** 更改为 `Login.cs`，然后单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-297">In the **Add New Item** dialog box, change the **Name** to `Login.cs`, and then click **Add**.</span></span>  
  
     <span data-ttu-id="e2cec-298">Login.cs 文件随即在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="e2cec-298">The Login.cs file opens in the code editor.</span></span>  
  
3.  <span data-ttu-id="e2cec-299">将默认代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="e2cec-299">Replace the default code with the following code.</span></span>  
  
     [!code-csharp[ClientApplicationServices#200](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Login.cs#200)]  
  
 <span data-ttu-id="e2cec-300">现在可以运行应用程序，并看到登录对话框出现。</span><span class="sxs-lookup"><span data-stu-id="e2cec-300">You can now run the application and see the login dialog box appear.</span></span> <span data-ttu-id="e2cec-301">若要测试此代码，请尝试不同的凭据（有效和无效），并确认只能使用有效凭据访问窗体。</span><span class="sxs-lookup"><span data-stu-id="e2cec-301">To test this code, try different credentials, both valid and invalid, and confirm that you can access the form only with valid credentials.</span></span> <span data-ttu-id="e2cec-302">有效用户名分别为 `employee` 和 `manager` ，密码分别为 `employee!` 和 `manager!` 。</span><span class="sxs-lookup"><span data-stu-id="e2cec-302">Valid user names are `employee` and `manager` with passwords `employee!` and `manager!` respectively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2cec-303">此时不要选择 **“记住我”** ，否则在本演练后面实现注销之前，无法以其他用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="e2cec-303">Do not select **Remember me** at this point or you will not be able to login as another user until you implement logout later in this walkthrough.</span></span>  
  
## <a name="adding-role-based-functionality"></a><span data-ttu-id="e2cec-304">添加基于角色的功能</span><span class="sxs-lookup"><span data-stu-id="e2cec-304">Adding Role-Based Functionality</span></span>  
 <span data-ttu-id="e2cec-305">在下面的过程中，会向窗体添加一个按钮，仅对采用 manager 角色的用户显示它。</span><span class="sxs-lookup"><span data-stu-id="e2cec-305">In the following procedure, you add a button to the form and display it only for users in the manager role.</span></span>  
  
#### <a name="to-change-the-user-interface-based-on-user-role"></a><span data-ttu-id="e2cec-306">基于用户角色更改用户界面</span><span class="sxs-lookup"><span data-stu-id="e2cec-306">To change the user interface based on user role</span></span>  
  
1.  <span data-ttu-id="e2cec-307">在“解决方案资源管理器”的 ClientAppServicesDemo 项目中，选择“Form1”，再依次选择 Visual Studio 主菜单中的“视图”&#124;“设计器”。</span><span class="sxs-lookup"><span data-stu-id="e2cec-307">In **Solution Explorer**, in the ClientAppServicesDemo project, select Form1 and then select **View &#124; Designer** from the Visual Studio main menu.</span></span>  
  
2.  <span data-ttu-id="e2cec-308">在设计器中，从“工具箱”向窗体添加一个 <xref:System.Windows.Forms.Button> 控件。</span><span class="sxs-lookup"><span data-stu-id="e2cec-308">In the designer, add a <xref:System.Windows.Forms.Button> control to the form from the **ToolBox**.</span></span>  
  
3.  <span data-ttu-id="e2cec-309">在 **“属性”** 窗口中，为该按钮设置以下属性。</span><span class="sxs-lookup"><span data-stu-id="e2cec-309">In the **Properties** window, set the following properties for the button.</span></span>  
  
  	|<span data-ttu-id="e2cec-310">属性</span><span class="sxs-lookup"><span data-stu-id="e2cec-310">Property</span></span>|<span data-ttu-id="e2cec-311">“值”</span><span class="sxs-lookup"><span data-stu-id="e2cec-311">Value</span></span>|  
  	|--------------|-----------|  
  	|<span data-ttu-id="e2cec-312">**“(名称)”**</span><span class="sxs-lookup"><span data-stu-id="e2cec-312">**(Name)**</span></span>|<span data-ttu-id="e2cec-313">managerOnlyButton</span><span class="sxs-lookup"><span data-stu-id="e2cec-313">managerOnlyButton</span></span>|  
  	|<span data-ttu-id="e2cec-314">**“文本”**</span><span class="sxs-lookup"><span data-stu-id="e2cec-314">**Text**</span></span>|<span data-ttu-id="e2cec-315">&Manager task</span><span class="sxs-lookup"><span data-stu-id="e2cec-315">&Manager task</span></span>|  
  	|<span data-ttu-id="e2cec-316">**可见**</span><span class="sxs-lookup"><span data-stu-id="e2cec-316">**Visible**</span></span>|`False`|  
  
4.  <span data-ttu-id="e2cec-317">在 Form1 的代码编辑器中，将以下代码添加到 `Form1_Load` 方法的末尾。</span><span class="sxs-lookup"><span data-stu-id="e2cec-317">In the code editor for Form1, add the following code to the end of the `Form1_Load` method.</span></span>  
  
     <span data-ttu-id="e2cec-318">此代码会调用将在下一步中添加的 `DisplayButtonForManagerRole` 方法。</span><span class="sxs-lookup"><span data-stu-id="e2cec-318">This code calls the `DisplayButtonForManagerRole` method that you will add in the next step.</span></span>  
  
     [!code-csharp[ClientApplicationServices#012](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#012)]
     [!code-vb[ClientApplicationServices#012](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#012)]  
  
5.  <span data-ttu-id="e2cec-319">将以下方法添加到 Form1 类的末尾。</span><span class="sxs-lookup"><span data-stu-id="e2cec-319">Add the following method to the end of the Form1 class.</span></span>  
  
     <span data-ttu-id="e2cec-320">此方法会调用 `static` <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> 属性返回的 <xref:System.Security.Principal.IPrincipal> 的 <xref:System.Security.Principal.IPrincipal.IsInRole%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="e2cec-320">This method calls the <xref:System.Security.Principal.IPrincipal.IsInRole%2A> method of the <xref:System.Security.Principal.IPrincipal> returned by the `static` <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="e2cec-321">对于配置为使用客户端应用程序服务的应用程序，此属性会返回 <xref:System.Web.ClientServices.ClientRolePrincipal>。</span><span class="sxs-lookup"><span data-stu-id="e2cec-321">For applications configured to use client application services, this property returns a <xref:System.Web.ClientServices.ClientRolePrincipal>.</span></span> <span data-ttu-id="e2cec-322">因为此类实现 <xref:System.Security.Principal.IPrincipal> 接口，所以无需显式引用它。</span><span class="sxs-lookup"><span data-stu-id="e2cec-322">Because this class implements the <xref:System.Security.Principal.IPrincipal> interface, you do not need to reference it explicitly.</span></span>  
  
     <span data-ttu-id="e2cec-323">如果用户采用“manager”角色，则 `DisplayButtonForManagerRole` 方法会将 <xref:System.Windows.Forms.Control.Visible%2A> 的 `managerOnlyButton` 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="e2cec-323">If the user is in the "manager" role, the `DisplayButtonForManagerRole` method sets the <xref:System.Windows.Forms.Control.Visible%2A> property of the `managerOnlyButton` to `true`.</span></span> <span data-ttu-id="e2cec-324">如果引发了 <xref:System.Net.WebException> （它表示角色服务不可用），则此方法还会显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="e2cec-324">This method also displays an error message if a <xref:System.Net.WebException> is thrown, which indicates that the roles service is unavailable.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e2cec-325">如果用户登录名已过期，则 <xref:System.Web.ClientServices.ClientRolePrincipal.IsInRole%2A> 方法会始终返回 `false` 。</span><span class="sxs-lookup"><span data-stu-id="e2cec-325">The <xref:System.Web.ClientServices.ClientRolePrincipal.IsInRole%2A> method will always return `false` if the user login has expired.</span></span> <span data-ttu-id="e2cec-326">如果应用程序在身份验证之后很快调用 <xref:System.Security.Principal.IPrincipal.IsInRole%2A> 方法一次（在本演练的代码示例中所示），则不会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="e2cec-326">This will not occur if your application calls the <xref:System.Security.Principal.IPrincipal.IsInRole%2A> method one time shortly after authentication, as shown in the example code for this walkthrough.</span></span> <span data-ttu-id="e2cec-327">如果应用程序必须在其他时间检索用户角色，则可能要添加代码以重新验证登录名已过期的用户。</span><span class="sxs-lookup"><span data-stu-id="e2cec-327">If your application must retrieve user roles at other times, you might want to add code to revalidate users whose login has expired.</span></span> <span data-ttu-id="e2cec-328">如果所有有效用户都分配给角色，则可以通过调用 <xref:System.Web.ClientServices.Providers.ClientRoleProvider.GetRolesForUser%2A?displayProperty=nameWithType> 方法来确定登录名是否已过期。</span><span class="sxs-lookup"><span data-stu-id="e2cec-328">If all valid users are assigned to roles, you can determine whether the login has expired by calling the <xref:System.Web.ClientServices.Providers.ClientRoleProvider.GetRolesForUser%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="e2cec-329">如果不返回任何角色，则登录名已过期。</span><span class="sxs-lookup"><span data-stu-id="e2cec-329">If no roles are returned, the login has expired.</span></span> <span data-ttu-id="e2cec-330">有关此功能的示例，请参阅 <xref:System.Web.ClientServices.Providers.ClientRoleProvider.GetRolesForUser%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="e2cec-330">For an example of this functionality, see the <xref:System.Web.ClientServices.Providers.ClientRoleProvider.GetRolesForUser%2A> method.</span></span> <span data-ttu-id="e2cec-331">仅当在应用程序配置中选择了 **“每次服务器 Cookie 到期时要求用户重新登录”** 时，此功能才是必需的。</span><span class="sxs-lookup"><span data-stu-id="e2cec-331">This functionality is only necessary if you have selected **Require users to log on again whenever the server cookie expires** in your application configuration.</span></span> <span data-ttu-id="e2cec-332">有关详细信息，请参阅[如何：配置客户端应用程序服务](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)。</span><span class="sxs-lookup"><span data-stu-id="e2cec-332">For more information, see [How to: Configure Client Application Services](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md).</span></span>  
  
     [!code-csharp[ClientApplicationServices#030](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#030)]
     [!code-vb[ClientApplicationServices#030](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#030)]  
  
 <span data-ttu-id="e2cec-333">如果身份验证成功，则客户端身份验证提供程序会将 <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> 属性设置为 <xref:System.Web.ClientServices.ClientRolePrincipal> 类的实例。</span><span class="sxs-lookup"><span data-stu-id="e2cec-333">If authentication is successful, the client authentication provider sets the <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> property to an instance of the <xref:System.Web.ClientServices.ClientRolePrincipal> class.</span></span> <span data-ttu-id="e2cec-334">此类实现 <xref:System.Security.Principal.IPrincipal.IsInRole%2A> 方法，以便将工作委托给配置的角色提供程序。</span><span class="sxs-lookup"><span data-stu-id="e2cec-334">This class implements the <xref:System.Security.Principal.IPrincipal.IsInRole%2A> method so that the work is delegated to the configured role provider.</span></span> <span data-ttu-id="e2cec-335">如前面一样，应用程序无需直接引用服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="e2cec-335">As before, your application code does not require a direct reference to the service provider.</span></span>  
  
 <span data-ttu-id="e2cec-336">现在可以运行应用程序，并以 employee 身份登录以看到按钮不会出现，然后以 manager 身份登录以看到按钮。</span><span class="sxs-lookup"><span data-stu-id="e2cec-336">You can now run the application and log in as employee to see that the button does not appear, and then log in as manager to see the button.</span></span>  
  
## <a name="accessing-web-settings"></a><span data-ttu-id="e2cec-337">访问 Web 设置</span><span class="sxs-lookup"><span data-stu-id="e2cec-337">Accessing Web Settings</span></span>  
 <span data-ttu-id="e2cec-338">在下面的过程中，会将一个文本框添加到窗体，然后将它绑定到 Web 设置。</span><span class="sxs-lookup"><span data-stu-id="e2cec-338">In the following procedure, you add a text box to the form and bind it to a Web setting.</span></span> <span data-ttu-id="e2cec-339">与前面使用身份验证和角色的代码一样，设置代码不直接访问设置提供程序。</span><span class="sxs-lookup"><span data-stu-id="e2cec-339">Like the previous code that uses authentication and roles, your settings code does not access the settings provider directly.</span></span> <span data-ttu-id="e2cec-340">而是使用 Visual Studio 为项目生成的强类型 `Settings` 类（在 C# 中作为 `Properties.Settings.Default` 访问，在 Visual Basic 中作为 `My.Settings` 访问）。</span><span class="sxs-lookup"><span data-stu-id="e2cec-340">Instead, it uses the strongly-typed `Settings` class (accessed as `Properties.Settings.Default` in C# and `My.Settings` in Visual Basic) generated for your project by Visual Studio.</span></span>  
  
#### <a name="to-use-web-settings-in-your-user-interface"></a><span data-ttu-id="e2cec-341">在用户界面中使用 Web 设置</span><span class="sxs-lookup"><span data-stu-id="e2cec-341">To use Web settings in your user interface</span></span>  
  
1.  <span data-ttu-id="e2cec-342">通过检查任务栏的通知区域来确保 **“ASP.NET Web Development Server”** 仍在运行。</span><span class="sxs-lookup"><span data-stu-id="e2cec-342">Make sure that the **ASP.NET Web Development Server** is still running by checking the notification area of the taskbar.</span></span> <span data-ttu-id="e2cec-343">如果已停止了该服务器，请重新启动应用程序（这会自动启动服务器），然后关闭登录对话框。</span><span class="sxs-lookup"><span data-stu-id="e2cec-343">If you have stopped the server, restart the application (which starts the server automatically) then close the login dialog box.</span></span>  
  
2.  <span data-ttu-id="e2cec-344">在 **“解决方案资源管理器”** 中，选择 ClientAppServicesDemo 项目，然后在 **“项目”** 菜单上，选择 **“ClientAppServicesDemo 属性”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-344">In **Solution Explorer**, select the ClientAppServicesDemo project, and then on the **Project** menu, select **ClientAppServicesDemo Properties**.</span></span>  
  
     <span data-ttu-id="e2cec-345">项目设计器随即出现。</span><span class="sxs-lookup"><span data-stu-id="e2cec-345">The project designer appears.</span></span>  
  
3.  <span data-ttu-id="e2cec-346">在 **“设置”** 选项卡上，单击 **“加载 Web 设置”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-346">On the **Settings** tab, click **Load Web Settings**.</span></span>  
  
     <span data-ttu-id="e2cec-347">**“登录”** 对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="e2cec-347">A **Login** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="e2cec-348">输入 employee 或 manager 的凭据，然后单击 **“登录”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-348">Enter credentials for employee or manager and click **Log In**.</span></span> <span data-ttu-id="e2cec-349">将使用的 Web 设置配置为仅供经过身份验证的用户访问，因此单击 **“跳过登录”** 不会加载任何设置。</span><span class="sxs-lookup"><span data-stu-id="e2cec-349">The Web setting you will use is configured for access by authenticated users only, so clicking **Skip Login** will not load any settings.</span></span>  
  
     <span data-ttu-id="e2cec-350">`WebSettingsTestText` 设置随即出现在设计器中，具有默认值 `DefaultText`。</span><span class="sxs-lookup"><span data-stu-id="e2cec-350">The `WebSettingsTestText` setting appears in the designer with the default value of `DefaultText`.</span></span> <span data-ttu-id="e2cec-351">此外，会为项目生成包含 `WebSettingsTestText` 属性的 `Settings` 类。</span><span class="sxs-lookup"><span data-stu-id="e2cec-351">Additionally, a `Settings` class that contains a `WebSettingsTestText` property is generated for your project.</span></span>  
  
5.  <span data-ttu-id="e2cec-352">在“解决方案资源管理器”的 ClientAppServicesDemo 项目中，选择“Form1”，再依次选择 Visual Studio 主菜单中的“视图”&#124;“设计器”。</span><span class="sxs-lookup"><span data-stu-id="e2cec-352">In **Solution Explorer**, in the ClientAppServicesDemo project, select Form1 and then select **View &#124; Designer** from the Visual Studio main menu.</span></span>  
  
6.  <span data-ttu-id="e2cec-353">在设计器中，向窗体添加一个 <xref:System.Windows.Forms.TextBox> 控件。</span><span class="sxs-lookup"><span data-stu-id="e2cec-353">In the designer, add a <xref:System.Windows.Forms.TextBox> control to the form.</span></span>  
  
7.  <span data-ttu-id="e2cec-354">在 **“属性”** 窗口中，将 **“(名称)”** 值指定为 `webSettingsTestTextBox`。</span><span class="sxs-lookup"><span data-stu-id="e2cec-354">In the **Properties** window, specify a **(Name)** value of `webSettingsTestTextBox`.</span></span>  
  
8.  <span data-ttu-id="e2cec-355">在代码编辑器中，将以下代码添加到 `Form1_Load` 方法末尾：</span><span class="sxs-lookup"><span data-stu-id="e2cec-355">In the code editor, add the following code to the end of the `Form1_Load` method.</span></span>  
  
     <span data-ttu-id="e2cec-356">此代码会调用将在下一步中添加的 `BindWebSettingsTestTextBox` 方法。</span><span class="sxs-lookup"><span data-stu-id="e2cec-356">This code calls the `BindWebSettingsTestTextBox` method that you will add in the next step.</span></span>  
  
     [!code-csharp[ClientApplicationServices#013](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#013)]
     [!code-vb[ClientApplicationServices#013](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#013)]  
  
9. <span data-ttu-id="e2cec-357">将以下方法添加到 Form1 类的末尾。</span><span class="sxs-lookup"><span data-stu-id="e2cec-357">Add the following method to the end of the Form1 class.</span></span>  
  
     <span data-ttu-id="e2cec-358">此方法将 <xref:System.Windows.Forms.TextBox.Text%2A> 的 `webSettingsTestTextBox` 属性绑定到此过程前面生成的 `WebSettingsTestText` 类的 `Settings` 属性。</span><span class="sxs-lookup"><span data-stu-id="e2cec-358">This method binds the <xref:System.Windows.Forms.TextBox.Text%2A> property of the `webSettingsTestTextBox` to the `WebSettingsTestText` property of the `Settings` class generated earlier in this procedure.</span></span> <span data-ttu-id="e2cec-359">如果引发了 <xref:System.Net.WebException> （它表示 Web 设置服务不可用），则此方法还会显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="e2cec-359">This method also displays an error message if a <xref:System.Net.WebException> is thrown, which indicates that the Web settings service is unavailable.</span></span>  
  
     [!code-csharp[ClientApplicationServices#040](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#040)]
     [!code-vb[ClientApplicationServices#040](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#040)]  
  
    > [!NOTE]
    >  <span data-ttu-id="e2cec-360">通常会使用数据绑定在控件与 Web 设置之间实现自动双向通信。</span><span class="sxs-lookup"><span data-stu-id="e2cec-360">You will typically use data binding to enable automatic two-way communication between a control and a Web setting.</span></span> <span data-ttu-id="e2cec-361">但是，还可以直接访问 Web 设置，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="e2cec-361">However, you can also access Web settings directly as shown in the following example:</span></span>  
  
     [!code-csharp[ClientApplicationServices#322](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#322)]
     [!code-vb[ClientApplicationServices#322](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#322)]  
  
10. <span data-ttu-id="e2cec-362">在设计器中，选择窗体，然后在 **“属性”** 窗口中，单击 **“事件”** 按钮。</span><span class="sxs-lookup"><span data-stu-id="e2cec-362">In the designer, select the form, and then, in the **Properties** window, click the **Events** button.</span></span>  
  
11. <span data-ttu-id="e2cec-363">选择 <xref:System.Windows.Forms.Form.FormClosing> 事件，然后按 Enter 以生成事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e2cec-363">Select the <xref:System.Windows.Forms.Form.FormClosing> event and then press ENTER to generate an event handler.</span></span>  
  
12. <span data-ttu-id="e2cec-364">将生成的方法替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="e2cec-364">Replace the generated method with the following code.</span></span>  
  
     <span data-ttu-id="e2cec-365"><xref:System.Windows.Forms.Form.FormClosing> 事件处理程序会调用 `SaveSettings` 方法，将在下一部分中添加的注销功能也使用该方法。</span><span class="sxs-lookup"><span data-stu-id="e2cec-365">The <xref:System.Windows.Forms.Form.FormClosing> event handler calls the `SaveSettings` method, which is also used by the logout functionality that you will add in the next section.</span></span> <span data-ttu-id="e2cec-366">`SaveSettings` 方法首先确认用户尚未注销。可通过当前主体返回的 <xref:System.Security.Principal.IIdentity.AuthenticationType%2A> 的 <xref:System.Security.Principal.IIdentity> 属性来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="e2cec-366">The `SaveSettings` method first confirms that the user has not logged out. It does this by checking the <xref:System.Security.Principal.IIdentity.AuthenticationType%2A> property of the <xref:System.Security.Principal.IIdentity> returned by the current principal.</span></span> <span data-ttu-id="e2cec-367">可通过 `static` <xref:System.Threading.Thread.CurrentPrincipal%2A> 属性检索当前主体。</span><span class="sxs-lookup"><span data-stu-id="e2cec-367">The current principal is retrieved through the `static` <xref:System.Threading.Thread.CurrentPrincipal%2A> property.</span></span> <span data-ttu-id="e2cec-368">如果用户针对客户端应用程序服务进行了身份验证，则身份验证类型将是“ClientForms”。</span><span class="sxs-lookup"><span data-stu-id="e2cec-368">If the user has been authenticated for client application services, the authentication type will be "ClientForms".</span></span> <span data-ttu-id="e2cec-369">`SaveSettings` 方法不能只检查 <xref:System.Security.Principal.IIdentity.IsAuthenticated%2A?displayProperty=nameWithType> 属性，因为用户在注销之后可能具有有效的 Windows 标识。</span><span class="sxs-lookup"><span data-stu-id="e2cec-369">The `SaveSettings` method cannot just check the <xref:System.Security.Principal.IIdentity.IsAuthenticated%2A?displayProperty=nameWithType> property because the user might have a valid Windows identity after logout.</span></span>  
  
     <span data-ttu-id="e2cec-370">如果用户尚未注销，则 `SaveSettings` 方法调用在此过程前面生成的 <xref:System.Configuration.ApplicationSettingsBase.Save%2A> 类的 `Settings` 方法。</span><span class="sxs-lookup"><span data-stu-id="e2cec-370">If the user has not logged out, the `SaveSettings` method calls the <xref:System.Configuration.ApplicationSettingsBase.Save%2A> method of the `Settings` class generated earlier in this procedure.</span></span> <span data-ttu-id="e2cec-371">如果身份验证 Cookie 已过期，则此方法可能会引发 <xref:System.Net.WebException> 。</span><span class="sxs-lookup"><span data-stu-id="e2cec-371">This method can throw a <xref:System.Net.WebException> if the authentication cookie has expired.</span></span> <span data-ttu-id="e2cec-372">仅当在应用程序配置中选择了 **“每次服务器 Cookie 到期时要求用户重新登录”** 时，才会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="e2cec-372">This occurs only if you have selected **Require users to log on again whenever the server cookie expires** in your application configuration.</span></span> <span data-ttu-id="e2cec-373">有关详细信息，请参阅[如何：配置客户端应用程序服务](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)。</span><span class="sxs-lookup"><span data-stu-id="e2cec-373">For more information, see [How to: Configure Client Application Services](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md).</span></span> <span data-ttu-id="e2cec-374">`SaveSettings` 方法通过调用 <xref:System.Web.Security.Membership.ValidateUser%2A> 以显示登录对话框，来处理 Cookie 过期。</span><span class="sxs-lookup"><span data-stu-id="e2cec-374">The `SaveSettings` method handles cookie expiration by calling <xref:System.Web.Security.Membership.ValidateUser%2A> to display the login dialog box.</span></span> <span data-ttu-id="e2cec-375">如果用户成功登录，则 `SaveSettings` 方法尝试通过调用自身来再次保存设置。</span><span class="sxs-lookup"><span data-stu-id="e2cec-375">If the user logs in successfully, the `SaveSettings` method tries to save the settings again by calling itself.</span></span>  
  
     <span data-ttu-id="e2cec-376">与前面的代码一样，如果远程服务不可用，则 `SaveSettings` 方法会显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="e2cec-376">Like in previous code, the `SaveSettings` method displays an error message if the remote service is unavailable.</span></span> <span data-ttu-id="e2cec-377">如果设置提供程序无法访问远程服务，则设置仍会保存到本地缓存，并在应用程序重新启动时重载。</span><span class="sxs-lookup"><span data-stu-id="e2cec-377">If the settings provider cannot access the remote service, the settings are still saved to the local cache and reloaded when the application restarts.</span></span>  
  
     [!code-csharp[ClientApplicationServices#050](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#050)]
     [!code-vb[ClientApplicationServices#050](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#050)]  
  
13. <span data-ttu-id="e2cec-378">将以下方法添加到 Form1 类的末尾。</span><span class="sxs-lookup"><span data-stu-id="e2cec-378">Add the following method to the end of the Form1 class.</span></span>  
  
     <span data-ttu-id="e2cec-379">此代码处理 <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved?displayProperty=nameWithType> 事件，并在任何设置无法保存时显示警告。</span><span class="sxs-lookup"><span data-stu-id="e2cec-379">This code handles the <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved?displayProperty=nameWithType> event and displays a warning if any of the settings could not be saved.</span></span> <span data-ttu-id="e2cec-380">如果设置服务不可用，或者如果身份验证 Cookie 已过期，则 <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved> 事件不会发生。</span><span class="sxs-lookup"><span data-stu-id="e2cec-380">The <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved> event does not occur if the settings service is unavailable or if the authentication cookie has expired.</span></span> <span data-ttu-id="e2cec-381"><xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved> 事件会发生的一个示例是如果用户已注销。可以通过直接在 `SaveSettings` 方法调用之前向 <xref:System.Configuration.ApplicationSettingsBase.Save%2A> 方法添加注销代码，来测试此事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e2cec-381">One example of when the <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved> event will occur is if the user has already logged out. You can test this event handler by adding logout code to the `SaveSettings` method directly before the <xref:System.Configuration.ApplicationSettingsBase.Save%2A> method call.</span></span> <span data-ttu-id="e2cec-382">可以使用的注销代码在下一部分中进行介绍。</span><span class="sxs-lookup"><span data-stu-id="e2cec-382">Logout code that you can use is described in the next section.</span></span>  
  
     [!code-csharp[ClientApplicationServices#090](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#090)]
     [!code-vb[ClientApplicationServices#090](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#090)]  
  
14. <span data-ttu-id="e2cec-383">对于 C#，在 `Form1_Load` 方法的末尾添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="e2cec-383">For C#, add the following code to the end of the `Form1_Load` method.</span></span> <span data-ttu-id="e2cec-384">此代码将上一步中添加的方法与 <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved> 事件相关联。</span><span class="sxs-lookup"><span data-stu-id="e2cec-384">This code associates the method you added in the last step with the <xref:System.Web.ClientServices.Providers.ClientSettingsProvider.SettingsSaved> event.</span></span>  
  
     [!code-csharp[ClientApplicationServices#015](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#015)]  
  
 <span data-ttu-id="e2cec-385">此时若要测试应用程序，请以 employee 和 manager 身份多次运行它，并在文本框中输入不同的值。</span><span class="sxs-lookup"><span data-stu-id="e2cec-385">To test the application at this point, run it multiple times as both employee and manager, and type different values into the text box.</span></span> <span data-ttu-id="e2cec-386">值会针对每个用户在会话之间保持。</span><span class="sxs-lookup"><span data-stu-id="e2cec-386">The values will persist across sessions on a per-user basis.</span></span>  
  
## <a name="implementing-logout"></a><span data-ttu-id="e2cec-387">实现注销</span><span class="sxs-lookup"><span data-stu-id="e2cec-387">Implementing Logout</span></span>  
 <span data-ttu-id="e2cec-388">当用户在登录时选中 **“记住我”** 复选框时，应用程序会在后续运行中自动对用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="e2cec-388">When the user selects the **Remember me** check box when logging in, the application will automatically authenticate the user on subsequent runs.</span></span> <span data-ttu-id="e2cec-389">应用程序处于脱机模式时，或在身份验证 Cookie 过期之前，自动身份验证随后会继续进行。</span><span class="sxs-lookup"><span data-stu-id="e2cec-389">Automatic authentication will then continue while the application is in offline mode or until the authentication cookie expires.</span></span> <span data-ttu-id="e2cec-390">但是，有时多个用户需要访问应用程序，或单个用户偶尔可能会使用不同的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="e2cec-390">Sometimes, however, multiple users will need access to the application or a single user might occasionally log in with different credentials.</span></span> <span data-ttu-id="e2cec-391">若要实现此方案，必须实现注销功能，如下面的过程中所述。</span><span class="sxs-lookup"><span data-stu-id="e2cec-391">To enable this scenario, you must implement logout functionality, as described in the following procedure.</span></span>  
  
#### <a name="to-implement-logout-functionality"></a><span data-ttu-id="e2cec-392">实现注销功能</span><span class="sxs-lookup"><span data-stu-id="e2cec-392">To implement logout functionality</span></span>  
  
1.  <span data-ttu-id="e2cec-393">在 Form1 设计器中，从“工具箱”向窗体添加一个 <xref:System.Windows.Forms.Button> 控件。</span><span class="sxs-lookup"><span data-stu-id="e2cec-393">In the Form1 designer, add a <xref:System.Windows.Forms.Button> control to the form from the **ToolBox**.</span></span>  
  
2.  <span data-ttu-id="e2cec-394">在“属性”窗口中，将“(Name)”值指定为 `logoutButton`，将“Text”值指定为“&Log Out”。</span><span class="sxs-lookup"><span data-stu-id="e2cec-394">In the **Properties** window, specify a **(Name)** value of `logoutButton` and a **Text** value of **&Log Out**.</span></span>  
  
3.  <span data-ttu-id="e2cec-395">双击 `logoutButton` 以生成 <xref:System.Windows.Forms.Control.Click> 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e2cec-395">Double-click the `logoutButton` to generate a <xref:System.Windows.Forms.Control.Click> event handler.</span></span>  
  
     <span data-ttu-id="e2cec-396">代码编辑器随即出现，光标位于 `logoutButton_Click` 方法中。</span><span class="sxs-lookup"><span data-stu-id="e2cec-396">The code editor appears with the cursor in the `logoutButton_Click` method.</span></span>  
  
4.  <span data-ttu-id="e2cec-397">将生成的 `logoutButton_Click` 方法替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="e2cec-397">Replace the generated `logoutButton_Click` method with the following code.</span></span>  
  
     <span data-ttu-id="e2cec-398">此事件处理程序首先调用在上一部分中添加的 `SaveSettings` 方法。</span><span class="sxs-lookup"><span data-stu-id="e2cec-398">This event handler first calls the `SaveSettings` method that you added in the previous section.</span></span> <span data-ttu-id="e2cec-399">随后，事件处理程序会调用 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider.Logout%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="e2cec-399">Then, the event handler calls the <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider.Logout%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="e2cec-400">如果身份验证服务不可用，则 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider.Logout%2A> 方法会引发 <xref:System.Net.WebException>。</span><span class="sxs-lookup"><span data-stu-id="e2cec-400">If the authentication service is unavailable, the <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider.Logout%2A> method will throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="e2cec-401">在这种情况下， `logoutButton_Click` 方法会显示一条警告消息，并暂时切换为脱机模式以使用户注销。下一部分中介绍了脱机模式。</span><span class="sxs-lookup"><span data-stu-id="e2cec-401">In this case, the `logoutButton_Click` method displays a warning message and switches temporarily to offline mode to log the user out. Offline mode is described in the next section.</span></span>  
  
     <span data-ttu-id="e2cec-402">注销会删除本地身份验证 Cookie，以便在应用程序重新启动时要求提供登录名。</span><span class="sxs-lookup"><span data-stu-id="e2cec-402">Logout deletes the local authentication cookie so that login will be required when the application is restarted.</span></span> <span data-ttu-id="e2cec-403">注销之后，事件处理程序会重新启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="e2cec-403">After logout, the event handler restarts the application.</span></span> <span data-ttu-id="e2cec-404">应用程序重新启动时，它会显示一条欢迎消息，后跟登录对话框。</span><span class="sxs-lookup"><span data-stu-id="e2cec-404">When the application restarts, it displays the welcome message followed by the login dialog box.</span></span> <span data-ttu-id="e2cec-405">欢迎消息可清楚地表明应用程序已重新启动。</span><span class="sxs-lookup"><span data-stu-id="e2cec-405">The welcome message makes it clear that the application has restarted.</span></span> <span data-ttu-id="e2cec-406">如果用户必须登录才能保存设置，并且随后因为应用程序重新启用而必须再次登录序，这样可防止可能的混淆。</span><span class="sxs-lookup"><span data-stu-id="e2cec-406">This prevents potential confusion if the user must log in to save settings, and then must log in again because the application has restarted.</span></span>  
  
     [!code-csharp[ClientApplicationServices#070](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#070)]
     [!code-vb[ClientApplicationServices#070](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#070)]  
  
 <span data-ttu-id="e2cec-407">若要测试注销功能，请运行应用程序，然后在登录对话框中选择 **“记住我”** 。</span><span class="sxs-lookup"><span data-stu-id="e2cec-407">To test the logout functionality, run the application and select **Remember me** on the Login dialog box.</span></span> <span data-ttu-id="e2cec-408">接下来，关闭并重新启动应用程序，以确认不必再登录。</span><span class="sxs-lookup"><span data-stu-id="e2cec-408">Next, close and restart the application to confirm that you no longer have to log in.</span></span> <span data-ttu-id="e2cec-409">最后，通过单击“注销”来重新启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="e2cec-409">Finally, restart the application by clicking Log out.</span></span>  
  
## <a name="enabling-offline-mode"></a><span data-ttu-id="e2cec-410">启用脱机模式</span><span class="sxs-lookup"><span data-stu-id="e2cec-410">Enabling Offline Mode</span></span>  
 <span data-ttu-id="e2cec-411">在下面的过程中，会向窗体添加一个复选框，以使用户可以进入脱机模式。</span><span class="sxs-lookup"><span data-stu-id="e2cec-411">In the following procedure, you add a check box to the form to enable the user to enter offline mode.</span></span> <span data-ttu-id="e2cec-412">应用程序通过将 `static` <xref:System.Web.ClientServices.ConnectivityStatus.IsOffline%2A?displayProperty=nameWithType> 属性设置为 `true`来指示脱机模式。</span><span class="sxs-lookup"><span data-stu-id="e2cec-412">Your application indicates offline mode by setting the `static` <xref:System.Web.ClientServices.ConnectivityStatus.IsOffline%2A?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="e2cec-413">脱机状态存储在本地硬盘上由 <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> 属性指示的位置处。</span><span class="sxs-lookup"><span data-stu-id="e2cec-413">The offline status is stored on the local hard disk at the location indicated by the <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="e2cec-414">这意味着会针对每个用户、每个应用程序来存储脱机状态。</span><span class="sxs-lookup"><span data-stu-id="e2cec-414">This means that the offline status is stored on a per-user, per-application basis.</span></span>  
  
 <span data-ttu-id="e2cec-415">在脱机模式下，所有客户端应用程序服务请求都从本地缓存检索数据而不是尝试访问服务。</span><span class="sxs-lookup"><span data-stu-id="e2cec-415">In offline mode, all client application service requests retrieve data from the local cache instead of trying to access the services.</span></span> <span data-ttu-id="e2cec-416">在默认配置中，本地数据包括用户密码的加密形式。</span><span class="sxs-lookup"><span data-stu-id="e2cec-416">In the default configuration, the local data includes an encrypted form of the user's password.</span></span> <span data-ttu-id="e2cec-417">这使用户可以应用程序处于脱机模式时登录。</span><span class="sxs-lookup"><span data-stu-id="e2cec-417">This enables the user to log in while the application is in offline mode.</span></span> <span data-ttu-id="e2cec-418">有关更多信息，请参见 [How to: Configure Client Application Services](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)。</span><span class="sxs-lookup"><span data-stu-id="e2cec-418">For more information, see [How to: Configure Client Application Services](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md).</span></span>  
  
#### <a name="to-enable-offline-mode-in-your-application"></a><span data-ttu-id="e2cec-419">在应用程序中启用脱机模式</span><span class="sxs-lookup"><span data-stu-id="e2cec-419">To enable offline mode in your application</span></span>  
  
1.  <span data-ttu-id="e2cec-420">在“解决方案资源管理器”的 ClientAppServicesDemo 项目中，选择“Form1”，再依次选择 Visual Studio 主菜单中的“视图”&#124;“设计器”。</span><span class="sxs-lookup"><span data-stu-id="e2cec-420">In **Solution Explorer**, in the ClientAppServicesDemo project, select Form1 and then select **View &#124; Designer** from the Visual Studio main menu.</span></span>  
  
2.  <span data-ttu-id="e2cec-421">在设计器中，向窗体添加一个 <xref:System.Windows.Forms.CheckBox> 控件。</span><span class="sxs-lookup"><span data-stu-id="e2cec-421">In the designer, add a <xref:System.Windows.Forms.CheckBox> control to the form.</span></span>  
  
3.  <span data-ttu-id="e2cec-422">在“属性”窗口中，将“(Name)”值指定为 `workOfflineCheckBox`，将“Text”值指定为“&Work offline”。</span><span class="sxs-lookup"><span data-stu-id="e2cec-422">In the **Properties** window, specify a **(Name)** value of `workOfflineCheckBox` and a **Text** value of **&Work offline**.</span></span>  
  
4.  <span data-ttu-id="e2cec-423">在 **“属性”** 窗口中，单击 **“事件”** 按钮。</span><span class="sxs-lookup"><span data-stu-id="e2cec-423">In the **Properties** window, click the **Events** button.</span></span>  
  
5.  <span data-ttu-id="e2cec-424">选择 <xref:System.Windows.Forms.CheckBox.CheckedChanged> 事件，然后按 Enter 以生成事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e2cec-424">Select the <xref:System.Windows.Forms.CheckBox.CheckedChanged> event and then press ENTER to generate an event handler.</span></span>  
  
6.  <span data-ttu-id="e2cec-425">将生成的方法替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="e2cec-425">Replace the generated method with the following code.</span></span>  
  
     <span data-ttu-id="e2cec-426">此代码会更新 <xref:System.Web.ClientServices.ConnectivityStatus.IsOffline%2A> 值，并在他们返回联机模式时以静默方式重新验证用户。</span><span class="sxs-lookup"><span data-stu-id="e2cec-426">This code updates the <xref:System.Web.ClientServices.ConnectivityStatus.IsOffline%2A> value and silently revalidates the user when they return to online mode.</span></span> <span data-ttu-id="e2cec-427"><xref:System.Web.ClientServices.ClientFormsIdentity.RevalidateUser%2A?displayProperty=nameWithType> 方法使用缓存的凭据，以便用户不必显式登录。</span><span class="sxs-lookup"><span data-stu-id="e2cec-427">The <xref:System.Web.ClientServices.ClientFormsIdentity.RevalidateUser%2A?displayProperty=nameWithType> method uses the cached credentials so that the user does not have to explicitly log in.</span></span> <span data-ttu-id="e2cec-428">如果身份验证服务不可用，则会出现警告消息，应用程序会保持脱机状态。</span><span class="sxs-lookup"><span data-stu-id="e2cec-428">If the authentication service is unavailable, a warning message appears and the application stays offline.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e2cec-429"><xref:System.Web.ClientServices.ClientFormsIdentity.RevalidateUser%2A> 方法只是为了方便。</span><span class="sxs-lookup"><span data-stu-id="e2cec-429">The <xref:System.Web.ClientServices.ClientFormsIdentity.RevalidateUser%2A> method is for convenience only.</span></span> <span data-ttu-id="e2cec-430">因为它没有返回值，所以无法指示重新验证是否失败。</span><span class="sxs-lookup"><span data-stu-id="e2cec-430">Because it does not have a return value, it cannot indicate whether revalidation has failed.</span></span> <span data-ttu-id="e2cec-431">例如，如果在服务器上更改了用户凭据，则重新验证可能会失败。</span><span class="sxs-lookup"><span data-stu-id="e2cec-431">Revalidation can fail, for example, if the user credentials have changed on the server.</span></span> <span data-ttu-id="e2cec-432">在这种情况下，你可能要包含在服务调用失败之后显式验证用户的代码。</span><span class="sxs-lookup"><span data-stu-id="e2cec-432">In this case, you might want to include code that explicitly validates users after a service call fails.</span></span> <span data-ttu-id="e2cec-433">有关详细信息，请参阅本演练前面的“访问 Web 设置”部分。</span><span class="sxs-lookup"><span data-stu-id="e2cec-433">For more information, see the Accessing Web Settings section earlier in this walkthrough.</span></span>  
  
     <span data-ttu-id="e2cec-434">重新验证之后，此代码会将任何更改都保存到本地 Web 设置，具体方法是调用以前添加的 `SaveSettings` 方法。</span><span class="sxs-lookup"><span data-stu-id="e2cec-434">After revalidation, this code saves any changes to the local Web settings by calling the `SaveSettings` method that you added previously.</span></span> <span data-ttu-id="e2cec-435">它随后通过调用项目的 `Settings` 类的 <xref:System.Configuration.ApplicationSettingsBase.Reload%2A> 方法（在 C# 中作为 `Properties.Settings.Default` 并且在 Visual Basic 中作为 `My.Settings` 来访问），来检索服务器上的任何新值。</span><span class="sxs-lookup"><span data-stu-id="e2cec-435">It then retrieves any new values on the server by calling the <xref:System.Configuration.ApplicationSettingsBase.Reload%2A> method of the project's `Settings` class (accessed as `Properties.Settings.Default` in C# and `My.Settings` in Visual Basic).</span></span>  
  
     [!code-csharp[ClientApplicationServices#080](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#080)]
     [!code-vb[ClientApplicationServices#080](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#080)]  
  
7.  <span data-ttu-id="e2cec-436">将以下代码添加到 `Form1_Load` 方法的末尾，以确保复选框显示当前连接状态。</span><span class="sxs-lookup"><span data-stu-id="e2cec-436">Add the following code to the end of the `Form1_Load` method to make sure that the check box displays the current connection state.</span></span>  
  
     [!code-csharp[ClientApplicationServices#014](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Form1.cs#014)]
     [!code-vb[ClientApplicationServices#014](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Form1.vb#014)]  
  
 <span data-ttu-id="e2cec-437">这样便完成了示例应用程序。</span><span class="sxs-lookup"><span data-stu-id="e2cec-437">This completes the example application.</span></span> <span data-ttu-id="e2cec-438">若要测试脱机功能，请运行应用程序，以 employee 或 manager 身份登录，然后选择 **“脱机工作”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-438">To test the offline capability, run the application, log in as either employee or manager, and then select **Work offline**.</span></span> <span data-ttu-id="e2cec-439">修改文本框中的值，然后关闭应用程序。</span><span class="sxs-lookup"><span data-stu-id="e2cec-439">Modify the value in the text box, and then close the application.</span></span> <span data-ttu-id="e2cec-440">重新启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="e2cec-440">Restart the application.</span></span> <span data-ttu-id="e2cec-441">登录之前，请在任务栏的通知区域中右键单击“ASP.NET 开发服务器”图标，然后单击 **“停止”**。</span><span class="sxs-lookup"><span data-stu-id="e2cec-441">Before you log in, right-click the ASP.NET Development Server icon in the notification area of the taskbar and then click **Stop**.</span></span> <span data-ttu-id="e2cec-442">随后照常登录。</span><span class="sxs-lookup"><span data-stu-id="e2cec-442">Then, log in like normal.</span></span> <span data-ttu-id="e2cec-443">即使服务器未运行时，仍可以登录。</span><span class="sxs-lookup"><span data-stu-id="e2cec-443">Even when the server is not running, you can still log in.</span></span> <span data-ttu-id="e2cec-444">修改文本框值，退出，然后重新启动以查看修改后的值。</span><span class="sxs-lookup"><span data-stu-id="e2cec-444">Modify the text box value, exit, and restart to see the modified value.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="e2cec-445">总结</span><span class="sxs-lookup"><span data-stu-id="e2cec-445">Summary</span></span>  
 <span data-ttu-id="e2cec-446">在本演练中，学习了如何在 Windows 窗体应用程序中启用并使用客户端应用程序服务。</span><span class="sxs-lookup"><span data-stu-id="e2cec-446">In this walkthrough, you learned how to enable and use client application services in a Windows Forms application.</span></span> <span data-ttu-id="e2cec-447">设置测试服务器之后，向应用程序添加了代码以对用户进行身份验证，并从服务器检索用户角色和应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="e2cec-447">After setting up a test server, you added code to your application to authenticate users and retrieve user roles and application settings from the server.</span></span> <span data-ttu-id="e2cec-448">还学习了如何启用脱机模式，以便应用程序在连接不可用时使用本地数据缓存而不是远程服务。</span><span class="sxs-lookup"><span data-stu-id="e2cec-448">You also learned how to enable offline mode so that your application uses a local data cache instead of the remote services when connectivity is not available.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e2cec-449">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e2cec-449">Next Steps</span></span>  
 <span data-ttu-id="e2cec-450">在实际应用程序中，你会从可能并不始终可用，或可能在不进行通知的情况下停机的远程服务器访问许多用户的数据。</span><span class="sxs-lookup"><span data-stu-id="e2cec-450">In a real-world application, you will access data for many users from a remote server that may not always be available, or may go down without notice.</span></span> <span data-ttu-id="e2cec-451">若要使应用程序可靠，必须正确响应服务不可用的情况。</span><span class="sxs-lookup"><span data-stu-id="e2cec-451">To make your application robust, you must respond appropriately to situations where the service is not available.</span></span> <span data-ttu-id="e2cec-452">本演练包含 try/catch 块来捕获 <xref:System.Net.WebException> ，并在服务不可用时显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="e2cec-452">This walkthrough includes try/catch blocks to catch a <xref:System.Net.WebException> and display an error message when the service is not available.</span></span> <span data-ttu-id="e2cec-453">在生产代码中，可能要通过切换为脱机模式、退出应用程序或拒绝对特定功能的访问来处理这种情况。</span><span class="sxs-lookup"><span data-stu-id="e2cec-453">In production code, you might want to handle this case by switching to offline mode, exiting the application, or denying access to specific functionality.</span></span>  
  
 <span data-ttu-id="e2cec-454">若要提高应用程序的安全性，请确保在部署之前全面测试应用程序和服务器。</span><span class="sxs-lookup"><span data-stu-id="e2cec-454">To increase the security of your application, make sure to thoroughly test the application and server before deployment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2cec-455">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2cec-455">See Also</span></span>  
 [<span data-ttu-id="e2cec-456">客户端应用程序服务</span><span class="sxs-lookup"><span data-stu-id="e2cec-456">Client Application Services</span></span>](../../../docs/framework/common-client-technologies/client-application-services.md)  
 [<span data-ttu-id="e2cec-457">客户端应用程序服务概述</span><span class="sxs-lookup"><span data-stu-id="e2cec-457">Client Application Services Overview</span></span>](../../../docs/framework/common-client-technologies/client-application-services-overview.md)  
 [<span data-ttu-id="e2cec-458">如何：配置客户端应用程序服务</span><span class="sxs-lookup"><span data-stu-id="e2cec-458">How to: Configure Client Application Services</span></span>](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)  
 [<span data-ttu-id="e2cec-459">ASP.NET Web Site Administration Tool</span><span class="sxs-lookup"><span data-stu-id="e2cec-459">ASP.NET Web Site Administration Tool</span></span>](http://msdn.microsoft.com/library/100ddd8b-7d11-4df9-91ef-0bbbe92e5aec)  
 [<span data-ttu-id="e2cec-460">为 SQL Server 创建和配置应用程序服务数据库</span><span class="sxs-lookup"><span data-stu-id="e2cec-460">Creating and Configuring the Application Services Database for SQL Server</span></span>](http://msdn.microsoft.com/library/ab894e83-7e2f-4af8-a116-b1bff8f815b2)  
 [<span data-ttu-id="e2cec-461">演练：使用 ASP.NET 应用程序服务</span><span class="sxs-lookup"><span data-stu-id="e2cec-461">Walkthrough: Using ASP.NET Application Services</span></span>](http://msdn.microsoft.com/library/f3f394f0-20d6-4361-aa8f-4b21bf4933eb)
