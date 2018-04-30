---
title: 如何：使用 Windows Server App Fabric 承载工作流服务
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83b62cce-5fc2-4c6d-b27c-5742ba3bac73
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ef60a291af39a39d3427d74b8a6ea7d00382c8d6
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-host-a-workflow-service-with-windows-server-app-fabric"></a><span data-ttu-id="aad60-102">如何：使用 Windows Server App Fabric 承载工作流服务</span><span class="sxs-lookup"><span data-stu-id="aad60-102">How to: Host a Workflow Service with Windows Server App Fabric</span></span>
<span data-ttu-id="aad60-103">在 App Fabric 中承载工作流服务类似于在 IIS/WAS 下承载。</span><span class="sxs-lookup"><span data-stu-id="aad60-103">Hosting workflow services in App Fabric is similar to hosting under IIS/WAS.</span></span> <span data-ttu-id="aad60-104">唯一的区别在于 App Fabric 提供的用于部署、监控和管理工作流服务的工具。</span><span class="sxs-lookup"><span data-stu-id="aad60-104">The only difference is the tools App Fabric provides for deploying, monitoring, and managing workflow services.</span></span> <span data-ttu-id="aad60-105">本主题使用在创建的工作流服务[创建长时间运行工作流服务](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md)。</span><span class="sxs-lookup"><span data-stu-id="aad60-105">This topic uses the workflow service created in the [Creating a Long-running Workflow Service](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md).</span></span> <span data-ttu-id="aad60-106">本主题将指导您创建工作流服务。</span><span class="sxs-lookup"><span data-stu-id="aad60-106">That topic will walk you through creating a workflow service.</span></span> <span data-ttu-id="aad60-107">本主题将介绍如何使用 App Fabric 承载工作流服务。</span><span class="sxs-lookup"><span data-stu-id="aad60-107">This topic will explain how to host the workflow service using App Fabric.</span></span> <span data-ttu-id="aad60-108">有关 Windows Server App Fabric 的详细信息，请参阅[Windows Server App Fabric 文档](http://go.microsoft.com/fwlink/?LinkID=193037&clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="aad60-108">For more information about Windows Server App Fabric, see [Windows Server App Fabric Documentation](http://go.microsoft.com/fwlink/?LinkID=193037&clcid=0x409).</span></span> <span data-ttu-id="aad60-109">完成以下步骤之前，请确保已安装 Windows Server App Fabric。</span><span class="sxs-lookup"><span data-stu-id="aad60-109">Before completing the steps below make sure you have Windows Server App Fabric installed.</span></span>  <span data-ttu-id="aad60-110">为此，请打开 Internet Information services (inetmgr.exe)，请单击服务器名称**连接**查看，单击站点，然后单击**Default Web Site**。</span><span class="sxs-lookup"><span data-stu-id="aad60-110">To do this open up Internet Information Services (inetmgr.exe), click your server name in the **Connections** view, click Sites, and click **Default Web Site**.</span></span> <span data-ttu-id="aad60-111">在屏幕的右侧，你应该看到名为一节**App Fabric**。</span><span class="sxs-lookup"><span data-stu-id="aad60-111">In the right-hand side of the screen you should see a section called **App Fabric**.</span></span> <span data-ttu-id="aad60-112">如果您看不到这一部分（它位于右侧窗格的顶部），则表示您还未安装 App Fabric。</span><span class="sxs-lookup"><span data-stu-id="aad60-112">If you don’t see this section (it will be on the top of the right-hand pane) you do not have App Fabric installed.</span></span> <span data-ttu-id="aad60-113">有关安装 Windows Server App Fabric 的详细信息请参阅[安装 Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=193136)。</span><span class="sxs-lookup"><span data-stu-id="aad60-113">For more information about installing Windows Server App Fabric see [Installing Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=193136).</span></span>  
  
### <a name="creating-a-simple-workflow-service"></a><span data-ttu-id="aad60-114">创建简单工作流服务</span><span class="sxs-lookup"><span data-stu-id="aad60-114">Creating a Simple Workflow Service</span></span>  
  
1.  <span data-ttu-id="aad60-115">打开[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]和加载 OrderProcessing 解决方案中创建[创建长时间运行工作流服务](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md)主题。</span><span class="sxs-lookup"><span data-stu-id="aad60-115">Open [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] and load the OrderProcessing solution you created in the [Creating a Long-running Workflow Service](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md) topic.</span></span>  
  
2.  <span data-ttu-id="aad60-116">右键单击**OrderService**项目，然后选择**属性**和选择**Web**选项卡。</span><span class="sxs-lookup"><span data-stu-id="aad60-116">Right click the **OrderService** project and select **Properties** and select the **Web** tab.</span></span>  
  
3.  <span data-ttu-id="aad60-117">在**启动操作**部分的属性页上，选择**特定页**和编辑框中键入 Service1.xamlx。</span><span class="sxs-lookup"><span data-stu-id="aad60-117">In the **Start Action** section of the property page select **Specific Page** and type Service1.xamlx in the edit box.</span></span>  
  
4.  <span data-ttu-id="aad60-118">在**服务器**部分的属性页上，选择**使用本地 IIS Web 服务器**并键入以下 URL: `http://localhost/OrderService`。</span><span class="sxs-lookup"><span data-stu-id="aad60-118">In the **Servers** section of the property page select **Use Local IIS Web Server** and type in the following URL: `http://localhost/OrderService`.</span></span>  
  
5.  <span data-ttu-id="aad60-119">单击**创建虚拟目录**按钮。</span><span class="sxs-lookup"><span data-stu-id="aad60-119">Click the **Create Virtual Directory** button.</span></span> <span data-ttu-id="aad60-120">这将新建一个虚拟目录，并将项目设置为在生成项目时将所需文件复制到此虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="aad60-120">This will create a new virtual directory and set up the project to copy the needed files to the virtual directory when the project is built.</span></span>  <span data-ttu-id="aad60-121">或者，你也可以手动将 .xamlx、web.config 以及任何所需的 DLL 复制到此虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="aad60-121">Alternatively you could manually copy the .xamlx, the web.config, and any needed DLLs to the virtual directory.</span></span>  
  
### <a name="configuring-a-workflow-service-hosted-in-windows-server-app-fabric"></a><span data-ttu-id="aad60-122">配置承载于 Windows Server App Fabric 中的工作流服务</span><span class="sxs-lookup"><span data-stu-id="aad60-122">Configuring a Workflow Service Hosted in Windows Server App Fabric</span></span>  
  
1.  <span data-ttu-id="aad60-123">打开 Internet 信息服务管理器 (inetmgr.exe)。</span><span class="sxs-lookup"><span data-stu-id="aad60-123">Open Internet Information Services Manager (inetmgr.exe).</span></span>  
  
2.  <span data-ttu-id="aad60-124">导航到 OrderService 虚拟目录中**连接**窗格。</span><span class="sxs-lookup"><span data-stu-id="aad60-124">Navigate to the OrderService virtual directory in the **Connections** pane.</span></span>  
  
3.  <span data-ttu-id="aad60-125">右击 OrderService 并选择**管理 WCF 和 WF 服务**，**配置...**.</span><span class="sxs-lookup"><span data-stu-id="aad60-125">Right click OrderService and select **Manage WCF and WF Services**, **Configure…**.</span></span> <span data-ttu-id="aad60-126">**为应用程序配置 WCF 和 WF**对话框随即显示。</span><span class="sxs-lookup"><span data-stu-id="aad60-126">The **Configure WCF and WF for Application** dialog box is displayed.</span></span>  
  
4.  <span data-ttu-id="aad60-127">选择**常规**选项卡以显示有关应用程序的常规信息，如下面的屏幕快照中所示。</span><span class="sxs-lookup"><span data-stu-id="aad60-127">Select the **General** tab to display general information about the application as shown in the following screen shot.</span></span>  
  
     <span data-ttu-id="aad60-128">![常规选项卡上的应用程序结构配置对话框](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-general.gif "AppFabricConfiguration-常规")</span><span class="sxs-lookup"><span data-stu-id="aad60-128">![General tab of the App Fabric Configuration dialog](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-general.gif "AppFabricConfiguration-General")</span></span>  
  
5.  <span data-ttu-id="aad60-129">选择**监视**选项卡。这将显示各种监控设置，如下面的屏幕快照所示。</span><span class="sxs-lookup"><span data-stu-id="aad60-129">Select the **Monitoring** tab. This shows various monitoring settings as shown in the following screen shot.</span></span>  
  
     <span data-ttu-id="aad60-130">![应用程序结构配置监视选项卡](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-monitoring.gif "AppFabricConfiguration 监视")</span><span class="sxs-lookup"><span data-stu-id="aad60-130">![App Fabric Configuration Monitoring tab](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-monitoring.gif "AppFabricConfiguration-Monitoring")</span></span>  
  
     <span data-ttu-id="aad60-131">有关配置工作流服务的详细信息中 App Fabric 监视请参阅[配置使用 App Fabric 监视](http://go.microsoft.com/fwlink/?LinkId=193153)。</span><span class="sxs-lookup"><span data-stu-id="aad60-131">For more information about configuring workflow service monitoring in App Fabric see [Configuring monitoring with App Fabric](http://go.microsoft.com/fwlink/?LinkId=193153).</span></span>  
  
6.  <span data-ttu-id="aad60-132">选择**工作流持久性**选项卡。这样，您可以将应用程序配置为使用 App Fabric 的默认暂留提供程序，如下面的屏幕快照所示。</span><span class="sxs-lookup"><span data-stu-id="aad60-132">Select the **Workflow Persistence** tab. This allows you to configure your application to use App Fabric’s default persistence provider as shown in the following screen shot.</span></span>  
  
     <span data-ttu-id="aad60-133">![应用程序结构配置&#45;持久性](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-persistence.gif "AppFabricConfiguration 持久性")</span><span class="sxs-lookup"><span data-stu-id="aad60-133">![App Fabric Configuration &#45; Persistence](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-persistence.gif "AppFabricConfiguration-Persistence")</span></span>  
  
     <span data-ttu-id="aad60-134">有关在 Windows Server App Fabric 中配置工作流持久性的详细信息请参阅[App Fabric 中配置工作流持久性](http://go.microsoft.com/fwlink/?LinkId=193148)。</span><span class="sxs-lookup"><span data-stu-id="aad60-134">For more information about configuring workflow persistence in Windows Server App Fabric see [Configuring Workflow Persistence in App Fabric](http://go.microsoft.com/fwlink/?LinkId=193148).</span></span>  
  
7.  <span data-ttu-id="aad60-135">选择**工作流主机管理**选项卡。这样，您可以指定何时应卸载和暂留空闲的工作流服务实例，如下面的屏幕快照所示。</span><span class="sxs-lookup"><span data-stu-id="aad60-135">Select the **Workflow Host Management** tab. This allows you to specify when idle workflow service instances should be unloaded and persisted as shown in the following screen shot.</span></span>  
  
     <span data-ttu-id="aad60-136">![应用程序结构配置工作流主机管理](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-management.gif "AppFabricConfiguration 管理")</span><span class="sxs-lookup"><span data-stu-id="aad60-136">![App Fabric Configuration  Workflow Host Management](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-management.gif "AppFabricConfiguration-Management")</span></span>  
  
     <span data-ttu-id="aad60-137">有关工作流主机管理配置的详细信息请参阅[App Fabric 中配置工作流主机管理](http://go.microsoft.com/fwlink/?LinkId=193151)。</span><span class="sxs-lookup"><span data-stu-id="aad60-137">For more information about workflow host management configuration see [Configuring Workflow Host Management in App Fabric](http://go.microsoft.com/fwlink/?LinkId=193151).</span></span>  
  
8.  <span data-ttu-id="aad60-138">选择**自动启动**选项卡。这样，您可以为应用程序中的工作流服务指定自动启动设置，如下面的屏幕快照所示。</span><span class="sxs-lookup"><span data-stu-id="aad60-138">Select the **Auto-Start** tab. This allows you to specify auto-start settings for the workflow services in the application as shown in the following screen shot.</span></span>  
  
     <span data-ttu-id="aad60-139">![应用程序结构自动&#45;启动配置](../../../../docs/framework/wcf/feature-details/media/appfabricconfigurationautostart.gif "AppFabricConfigurationAutostart")</span><span class="sxs-lookup"><span data-stu-id="aad60-139">![App Fabric Auto&#45;start configuration](../../../../docs/framework/wcf/feature-details/media/appfabricconfigurationautostart.gif "AppFabricConfigurationAutostart")</span></span>  
  
     <span data-ttu-id="aad60-140">有关配置自动启动的详细信息请参阅[使用 App Fabric 配置的自动启动](http://go.microsoft.com/fwlink/?LinkId=193150)。</span><span class="sxs-lookup"><span data-stu-id="aad60-140">For more information about configuring Auto-Start see [Configuring Auto-Start with App Fabric](http://go.microsoft.com/fwlink/?LinkId=193150).</span></span>  
  
9. <span data-ttu-id="aad60-141">选择**限制**选项卡。这样，您可以为工作流服务配置限制设置，如下面的屏幕快照所示。</span><span class="sxs-lookup"><span data-stu-id="aad60-141">Select the **Throttling** tab. This allows you to configure throttling settings for the workflow service as shown in the following screen shot.</span></span>  
  
     <span data-ttu-id="aad60-142">![应用程序结构配置限制](../../../../docs/framework/wcf/feature-details/media/appfabricconfigurationthrottling.gif "AppFabricConfigurationThrottling")</span><span class="sxs-lookup"><span data-stu-id="aad60-142">![App Fabric configuration throttling](../../../../docs/framework/wcf/feature-details/media/appfabricconfigurationthrottling.gif "AppFabricConfigurationThrottling")</span></span>  
  
     <span data-ttu-id="aad60-143">有关配置限制的详细信息请参阅[配置限制使用 App Fabric](http://go.microsoft.com/fwlink/?LinkId=193149)。</span><span class="sxs-lookup"><span data-stu-id="aad60-143">For more information about configuring throttling see [Configuring Throttling with App Fabric](http://go.microsoft.com/fwlink/?LinkId=193149).</span></span>  
  
10. <span data-ttu-id="aad60-144">选择**安全**选项卡。这样，您可以为应用程序配置安全设置，如下面的屏幕快照所示。</span><span class="sxs-lookup"><span data-stu-id="aad60-144">Select the **Security** tab. This allows you to configure security settings for the application as shown in the following screen shot.</span></span>  
  
     <span data-ttu-id="aad60-145">![应用程序结构安全性配置](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-security.gif "AppFabricConfiguration 安全")</span><span class="sxs-lookup"><span data-stu-id="aad60-145">![App Fabric Security Configuration](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-security.gif "AppFabricConfiguration-Security")</span></span>  
  
     <span data-ttu-id="aad60-146">有关使用 Windows Server App Fabric 中配置安全性的详细信息请参阅[使用 App Fabric 中配置安全性](http://go.microsoft.com/fwlink/?LinkId=193152)。</span><span class="sxs-lookup"><span data-stu-id="aad60-146">For more information about configuring security with Windows Server App Fabric see [Configuring Security with App Fabric](http://go.microsoft.com/fwlink/?LinkId=193152).</span></span>  
  
### <a name="using-windows-server-app-fabric"></a><span data-ttu-id="aad60-147">使用 Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="aad60-147">Using Windows Server App Fabric</span></span>  
  
1.  <span data-ttu-id="aad60-148">生成解决方案以便将所需的文件复制到虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="aad60-148">Build the solution to copy the necessary files to the virtual directory.</span></span>  
  
2.  <span data-ttu-id="aad60-149">右键单击 OrderClient 项目，然后选择**调试**，**启动新实例**以启动客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="aad60-149">Right click the OrderClient project and select **Debug**, **Start New Instance** to launch the client application.</span></span>  
  
3.  <span data-ttu-id="aad60-150">客户端的运行时间以及 Visual Studio 将显示**附加安全警告**对话框中，单击**不附加**按钮。</span><span class="sxs-lookup"><span data-stu-id="aad60-150">The client will run and Visual Studio will display an **Attach Security Warning** dialog box, click the **Don’t Attach** button.</span></span> <span data-ttu-id="aad60-151">这会告知 Visual Studio 不要附加到 IIS 进程进行调试。</span><span class="sxs-lookup"><span data-stu-id="aad60-151">This tells Visual Studio to not attach to the IIS process for debugging.</span></span>  
  
4.  <span data-ttu-id="aad60-152">客户端应用程序将立即调用工作流服务，然后等待。</span><span class="sxs-lookup"><span data-stu-id="aad60-152">The client application will immediately call the Workflow service and then wait.</span></span> <span data-ttu-id="aad60-153">工作流服务将转为空闲暂留状态。</span><span class="sxs-lookup"><span data-stu-id="aad60-153">The workflow service will go idle and be persisted.</span></span> <span data-ttu-id="aad60-154">通过启动 Internet 信息服务 (inetmgr.exe)，在“连接”窗格中导航至 OrderService 并将其选中，可以对此进行验证。</span><span class="sxs-lookup"><span data-stu-id="aad60-154">You can verify this by starting Internet Information Services (inetmgr.exe), navigating to the OrderService in the Connections pane and selecting it.</span></span> <span data-ttu-id="aad60-155">接下来，单击右侧窗格中的“App Fabric 仪表板”图标。</span><span class="sxs-lookup"><span data-stu-id="aad60-155">Next, click the App Fabric Dashboard icon in the right-hand pane.</span></span> <span data-ttu-id="aad60-156">在“暂留的 WF 实例”下，您将看到存在一个暂留的工作流服务实例，如下面的屏幕快照所示。</span><span class="sxs-lookup"><span data-stu-id="aad60-156">Under Persisted WF Instances you will see there is one persisted workflow service instance as shown in the following screen shot.</span></span>  
  
     <span data-ttu-id="aad60-157">![App Fabric 仪表板](../../../../docs/framework/wcf/feature-details/media/appfabricdashboard.gif "AppFabricDashboard")</span><span class="sxs-lookup"><span data-stu-id="aad60-157">![App Fabric Dashboard](../../../../docs/framework/wcf/feature-details/media/appfabricdashboard.gif "AppFabricDashboard")</span></span>  
  
     <span data-ttu-id="aad60-158">**WF 实例历史记录**列出有关工作流服务的工作流服务激活次数、 工作流服务实例的完成数等包含失败操作的工作流实例数的信息。</span><span class="sxs-lookup"><span data-stu-id="aad60-158">The **WF Instance History** lists information about the workflow service such as the number of workflow service activations, the number of workflow service instance completions, and the number of workflow instances with failures.</span></span> <span data-ttu-id="aad60-159">在活动或空闲实例下将显示一个链接，单击此链接将显示更多有关空闲工作流实例的信息，如下面的屏幕快照所示。</span><span class="sxs-lookup"><span data-stu-id="aad60-159">Under Active or Idle instances a link will be displayed, clicking on the link will display more information about the idle workflow instances as shown in the following screen shot.</span></span>  
  
     <span data-ttu-id="aad60-160">![持久化工作流实例详细信息](../../../../docs/framework/wcf/feature-details/media/persisteddetail.gif "PersistedDetail")</span><span class="sxs-lookup"><span data-stu-id="aad60-160">![Persisted Workflow Instance Details](../../../../docs/framework/wcf/feature-details/media/persisteddetail.gif "PersistedDetail")</span></span>  
  
     <span data-ttu-id="aad60-161">有关 Windows Server App Fabric 功能以及如何使用它们查看[Windows Server App Fabric 承载功能](http://go.microsoft.com/fwlink/?LinkID=193143&clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="aad60-161">For more information about Windows Server App Fabric features and how to use them see [Windows Server App Fabric Hosting Features](http://go.microsoft.com/fwlink/?LinkID=193143&clcid=0x409)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aad60-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="aad60-162">See Also</span></span>  
 [<span data-ttu-id="aad60-163">创建长时间运行的工作流服务</span><span class="sxs-lookup"><span data-stu-id="aad60-163">Creating a Long-running Workflow Service</span></span>](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md)  
 [<span data-ttu-id="aad60-164">Windows Server App Fabric 承载功能</span><span class="sxs-lookup"><span data-stu-id="aad60-164">Windows Server App Fabric Hosting Features</span></span>](http://go.microsoft.com/fwlink/?LinkId=193143)  
 [<span data-ttu-id="aad60-165">安装 Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="aad60-165">Installing Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkId=193136)  
 [<span data-ttu-id="aad60-166">Windows Server App Fabric 文档</span><span class="sxs-lookup"><span data-stu-id="aad60-166">Windows Server App Fabric Documentation</span></span>](http://go.microsoft.com/fwlink/?LinkID=193037&clcid=0x409)
