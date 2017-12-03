---
title: "承载工作流服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2d55217e-8697-4113-94ce-10b60863342e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1bf0b63d3de750b5ec2aea41dcb6bb700385663a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="hosting-workflow-services"></a><span data-ttu-id="fd4a8-102">承载工作流服务</span><span class="sxs-lookup"><span data-stu-id="fd4a8-102">Hosting Workflow Services</span></span>
<span data-ttu-id="fd4a8-103">工作流服务在承载后才能对传入消息做出响应。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-103">A workflow service must be hosted for it to respond to incoming messages.</span></span> <span data-ttu-id="fd4a8-104">工作流服务使用的是 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 消息传递基础结构，因此承载的方式也类似。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-104">Workflow services use the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] messaging infrastructure and are therefore hosted in similar ways.</span></span> <span data-ttu-id="fd4a8-105">工作流服务与 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务类似，可以承载于任何托管应用程序、Internet 信息服务 (IIS) 或 Windows 进程激活服务 (WAS)。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-105">Like [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services, workflow services can be hosted in any managed application, under Internet Information Services (IIS), or under Windows Process Activation Services (WAS).</span></span> <span data-ttu-id="fd4a8-106">此外，工作流服务还可以承载于 Windows Server App Fabric 下。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-106">In addition workflow services can be hosted under Windows Server App Fabric.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="fd4a8-107">Windows Server App Fabric，请参阅[Windows Server App Fabric 文档](http://go.microsoft.com/fwlink/?LinkId=193037)， [AppFabric 承载功能](http://go.microsoft.com/fwlink/?LinkId=196494)，和[AppFabric 承载概念](http://go.microsoft.com/fwlink/?LinkId=196495)。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-107"> Windows Server App Fabric see [Windows Server App Fabric documentation](http://go.microsoft.com/fwlink/?LinkId=193037), [AppFabric Hosting Features](http://go.microsoft.com/fwlink/?LinkId=196494), and [AppFabric Hosting Concepts](http://go.microsoft.com/fwlink/?LinkId=196495).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="fd4a8-108">为主机的各种方式[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]服务，请参阅[托管服务](../../../../docs/framework/wcf/hosting-services.md)。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-108"> the various ways to host [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services see [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="hosting-in-a-managed-application"></a><span data-ttu-id="fd4a8-109">在托管应用程序中承载</span><span class="sxs-lookup"><span data-stu-id="fd4a8-109">Hosting in a managed application</span></span>  
 <span data-ttu-id="fd4a8-110">若要在托管应用程序中承载工作流服务，请使用 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 类。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-110">To host a workflow service in a managed application, use the <xref:System.ServiceModel.Activities.WorkflowServiceHost> class.</span></span> <span data-ttu-id="fd4a8-111"><xref:System.ServiceModel.Activities.WorkflowServiceHost> 构造函数可用于指定单一工作流服务实例、工作流服务定义或使用工作流消息传递活动的活动。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-111">The <xref:System.ServiceModel.Activities.WorkflowServiceHost> constructor allows you to specify a singleton workflow service instance, a workflow service definition, or an activity that uses the workflow messaging activities.</span></span> <span data-ttu-id="fd4a8-112">调用 <<!--zz xref:System.ServiceModel.Activities.WorkflowServiceHost.Open%2A--> `System.ServiceModel.Activities.WorkflowServiceHost.Open`> 会导致服务开始侦听传入消息。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-112">Calling <<!--zz xref:System.ServiceModel.Activities.WorkflowServiceHost.Open%2A--> `System.ServiceModel.Activities.WorkflowServiceHost.Open`> causes the service to start listening for incoming messages.</span></span>  
  
## <a name="hosting-under-iis-or-was"></a><span data-ttu-id="fd4a8-113">在 IIS 或 WAS 下承载</span><span class="sxs-lookup"><span data-stu-id="fd4a8-113">Hosting under IIS or WAS</span></span>  
 <span data-ttu-id="fd4a8-114">在 IIS 或 WAS 下承载工作流服务时，涉及到创建虚拟目录以及将定义服务及其行为的文件放在该虚拟目录中。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-114">Hosting a workflow service under IIS or WAS involves creating a virtual directory and placing files in the virtual directory that define the service and its behavior.</span></span> <span data-ttu-id="fd4a8-115">此时可能出现以下几种情况：</span><span class="sxs-lookup"><span data-stu-id="fd4a8-115">When hosting a workflow service under IIS or WAS there are several possibilities:</span></span>  
  
-   <span data-ttu-id="fd4a8-116">将定义工作流服务的 .xamlx 文件放在 IIS/WAS 虚拟目录中，同时放入指定服务行为、终结点和其他配置元素的 Web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-116">Place a .xamlx file that defines the workflow service in an IIS/WAS virtual directory along with a Web.config file that specifies the service behaviors, endpoints, and other configuration elements.</span></span>  
  
-   <span data-ttu-id="fd4a8-117">将定义工作流服务的 .xamlx 文件放在一个 IIS/WAS 虚拟目录中。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-117">Place a .xamlx file that defines the workflow service in an IIS/WAS virtual directory.</span></span> <span data-ttu-id="fd4a8-118">.xamlx 文件指定要公开的终结点。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-118">The .xamlx file specifies the endpoints to expose.</span></span> <span data-ttu-id="fd4a8-119">终结点将在 `WorkflowService.Endpoints` 元素中指定，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-119">Endpoints are specified in a `WorkflowService.Endpoints` element as shown in the following example.</span></span>  
  
    ```xml  
    <WorkflowService xmlns="http://schemas.microsoft.com/netfx/2009/xaml/servicemodel"  xmlns:p1="http://schemas.microsoft.com/netfx/2009/xaml/activities" xmlns:sad="clr-namespace:System.Activities.Debugger;assembly=System.Activities" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
      <WorkflowService.Endpoints>  
        <Endpoint ServiceContractName="IWorkFlowEchoService" AddressUri="">  
          <Endpoint.Binding>  
            <BasicHttpBinding />  
          </Endpoint.Binding>  
        </Endpoint>  
      </WorkflowService.Endpoints>  
    <!-- ... -->  
    </WorkflowService>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="fd4a8-120">不能在 .xamlx 文件中指定行为，因此，如果需要指定行为设置，则必须使用 Web.config。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-120">Behaviors cannot be specified in a .xamlx file, so you must use a Web.config if you need to specify behavior settings.</span></span>  
  
-   <span data-ttu-id="fd4a8-121">将定义工作流服务的 .xamlx 文件放在一个 IIS/WAS 虚拟目录中。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-121">Place a .xamlx file that defines the workflow service in an IIS/WAS virtual directory.</span></span> <span data-ttu-id="fd4a8-122">另外，将一个 .svc 文件放在该虚拟目录中。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-122">In addition, place a .svc file in the virtual directory.</span></span> <span data-ttu-id="fd4a8-123">使用 .svc 文件可以指定自定义 Web 服务主机工厂、应用自定义行为或者从自定义位置加载配置。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-123">The .svc file allows you to specify a custom Web service host factory, apply custom behavior, or load configuration from a custom location.</span></span>  
  
-   <span data-ttu-id="fd4a8-124">将一个程序集放在 IIS/WAS 虚拟目录中，该程序集包含一个使用 WCF 消息传递活动的活动。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-124">Place an assembly in the IIS/WAS virtual directory that contains an activity that uses the WCF messaging activities.</span></span>  
  
 <span data-ttu-id="fd4a8-125">定义工作流服务的.xamlx 文件必须包含 <`Service`> 根元素或包含派生自任何类型的根元素<xref:System.Workflow.ComponentModel.Activity>。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-125">A .xamlx file that defines a workflow service must contain a <`Service`> root element or a root element that contains any type derived from <xref:System.Workflow.ComponentModel.Activity>.</span></span> <span data-ttu-id="fd4a8-126">使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 活动模板时将创建 .xamlx 文件，</span><span class="sxs-lookup"><span data-stu-id="fd4a8-126">When using the [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Activity template a .xamlx file is created.</span></span> <span data-ttu-id="fd4a8-127">使用 WCF 工作流服务模板时将创建 .xamlx 文件。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-127">When using the WCF Workflow Service template a .xamlx file is created.</span></span>  
  
## <a name="hosting-workflow-services-under-windows-server-app-fabric"></a><span data-ttu-id="fd4a8-128">在 Windows Server App Fabric 下承载工作流服务</span><span class="sxs-lookup"><span data-stu-id="fd4a8-128">Hosting Workflow Services under Windows Server App Fabric</span></span>  
 <span data-ttu-id="fd4a8-129">在 Windows Server App Fabric 下承载工作流服务的方式与在 IIS/WAS 下的承载方式相同。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-129">Hosting a workflow service under Windows Server App Fabric is done in the same way as hosting under IIS/WAS.</span></span> <span data-ttu-id="fd4a8-130">唯一区别在于会安装 Windows Server App Fabric。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-130">The only difference is the fact that Windows Server App Fabric is installed.</span></span> <span data-ttu-id="fd4a8-131">Windows Server App Fabric 提供了添加到 Internet 信息服务管理器的工具，以及 powershell commandlets。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-131">Windows Server App Fabric provides tools that are added to Internet Information Services Manager, as well as powershell commandlets.</span></span> <span data-ttu-id="fd4a8-132">这些工具可简化工作流服务和 WCF 服务的部署、管理和跟踪。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-132">These tools simplify deploying, managing, and tracking of workflow services and WCF services.</span></span> <span data-ttu-id="fd4a8-133">.</span><span class="sxs-lookup"><span data-stu-id="fd4a8-133">.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="fd4a8-134">Windows Server App Fabric，请参阅[Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=193037)</span><span class="sxs-lookup"><span data-stu-id="fd4a8-134"> Windows Server App Fabric see [Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=193037)</span></span>  
  
## <a name="referencing-custom-activities"></a><span data-ttu-id="fd4a8-135">引用自定义活动</span><span class="sxs-lookup"><span data-stu-id="fd4a8-135">Referencing Custom Activities</span></span>  
 <span data-ttu-id="fd4a8-136">对自定义活动的引用必须添加到 <`Assemblies`> 部分中的 <`System.Web.Compilation`> 以便加载到应用程序域，并且 XAML 反序列化程序能够找到类型。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-136">References to custom activities must be added to the <`Assemblies`> section under <`System.Web.Compilation`> so that they are loaded into the Application Domain and the XAML deserializer is able to locate the types.</span></span> <span data-ttu-id="fd4a8-137">可以在应用程序级别进行这些设置；如果要将这些设置应用于计算机上的所有应用程序，则可在根 Web.config 中进行这些设置。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-137">These settings can be made at the application level or in the root Web.config if the settings should be applied to all applications on the machine.</span></span>  
  
## <a name="deployment"></a><span data-ttu-id="fd4a8-138">部署</span><span class="sxs-lookup"><span data-stu-id="fd4a8-138">Deployment</span></span>  
 <span data-ttu-id="fd4a8-139">系统中已经创建 Web 部署工具，以方便部署作业。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-139">The Web Deployment tool has been created to make the job of deployment easier.</span></span> <span data-ttu-id="fd4a8-140">通过使用该工具，可以在 IIS 6.0 和 IIS 7.0 之间迁移应用程序，同步服务器场，并打包、存档和部署 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="fd4a8-140">The tool allows you to migrate applications between IIS 6.0 and IIS 7.0, synchronize server farms, and package, archive and deploy Web applications.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="fd4a8-141">[MS 部署工具](http://go.microsoft.com/fwlink/?LinkId=178690)</span><span class="sxs-lookup"><span data-stu-id="fd4a8-141"> [MS Deployment Tool](http://go.microsoft.com/fwlink/?LinkId=178690)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd4a8-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd4a8-142">See Also</span></span>  
 [<span data-ttu-id="fd4a8-143">工作流服务主机内部机制</span><span class="sxs-lookup"><span data-stu-id="fd4a8-143">Workflow Service Host Internals</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)  
 [<span data-ttu-id="fd4a8-144">配置 WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="fd4a8-144">Configuring WorkflowServiceHost</span></span>](../../../../docs/framework/wcf/feature-details/configuring-workflowservicehost.md)
