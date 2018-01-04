---
title: "如何：创建 Windows 服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, creating
- templates, Windows Service
ms.assetid: 0f5e2cbb-d95d-477c-b2b5-4b990e6b86ff
caps.latest.revision: "18"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 7d93f8543b9e6e370827f5a666315d562e28ee76
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-windows-services"></a><span data-ttu-id="3d956-102">如何：创建 Windows 服务</span><span class="sxs-lookup"><span data-stu-id="3d956-102">How to: Create Windows Services</span></span>
<span data-ttu-id="3d956-103">当你创建服务时，你可以使用 Visual Studio 项目模板中，名**Windows 服务**。</span><span class="sxs-lookup"><span data-stu-id="3d956-103">When you create a service, you can use a Visual Studio project template called **Windows Service**.</span></span> <span data-ttu-id="3d956-104">通过引用适当的类和命名空间、为服务设置来自基类的继承和替代你可能想要替代的几个方法，此模板自动为你完成了许多工作。</span><span class="sxs-lookup"><span data-stu-id="3d956-104">This template automatically does much of the work for you by referencing the appropriate classes and namespaces, setting up the inheritance from the base class for services, and overriding several of the methods you're likely to want to override.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="3d956-105">Visual Studio 的速成版中未提供 Windows 服务项目模板。</span><span class="sxs-lookup"><span data-stu-id="3d956-105">The Windows Services project template is not available in the Express edition of Visual Studio.</span></span>  
  
 <span data-ttu-id="3d956-106">要创建功能性服务，你至少必须：</span><span class="sxs-lookup"><span data-stu-id="3d956-106">At a minimum, to create a functional service you must:</span></span>  
  
-   <span data-ttu-id="3d956-107">设置 <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="3d956-107">Set the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property.</span></span>  
  
-   <span data-ttu-id="3d956-108">为你的服务应用程序创建必要的安装程序。</span><span class="sxs-lookup"><span data-stu-id="3d956-108">Create the necessary installers for your service application.</span></span>  
  
-   <span data-ttu-id="3d956-109">替代并指定 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 和 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 方法的代码，以自定义你的服务的行为方式。</span><span class="sxs-lookup"><span data-stu-id="3d956-109">Override and specify code for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> methods to customize the ways in which your service behaves.</span></span>  
  
### <a name="to-create-a-windows-service-application"></a><span data-ttu-id="3d956-110">要创建 Windows 服务应用程序</span><span class="sxs-lookup"><span data-stu-id="3d956-110">To create a Windows Service application</span></span>  
  
1.  <span data-ttu-id="3d956-111">创建**Windows 服务**项目。</span><span class="sxs-lookup"><span data-stu-id="3d956-111">Create a **Windows Service** project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3d956-112">有关不使用模板的情况下编写服务的说明，请参阅[如何： 编写服务以编程方式](../../../docs/framework/windows-services/how-to-write-services-programmatically.md)。</span><span class="sxs-lookup"><span data-stu-id="3d956-112">For instructions on writing a service without using the template, see [How to: Write Services Programmatically](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).</span></span>  
  
2.  <span data-ttu-id="3d956-113">在**属性**窗口中，设置<xref:System.ServiceProcess.ServiceBase.ServiceName%2A>为你的服务的属性。</span><span class="sxs-lookup"><span data-stu-id="3d956-113">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property for your service.</span></span>  
  
     <span data-ttu-id="3d956-114">![设置 ServiceName 属性。] (../../../docs/framework/windows-services/media/windowsservice-servicename.PNG "WindowsService_ServiceName")</span><span class="sxs-lookup"><span data-stu-id="3d956-114">![Set the ServiceName property.](../../../docs/framework/windows-services/media/windowsservice-servicename.PNG "WindowsService_ServiceName")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3d956-115"><xref:System.ServiceProcess.ServiceBase.ServiceName%2A> 属性的值必须始终与记录在安装程序类中的名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="3d956-115">The value of the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property must always match the name recorded in the installer classes.</span></span> <span data-ttu-id="3d956-116">如果更改此属性，你还必须更新安装程序类的 <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="3d956-116">If you change this property, you must update the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property of installer classes as well.</span></span>  
  
3.  <span data-ttu-id="3d956-117">设置下列任何一个属性，确定你的服务的运行方式。</span><span class="sxs-lookup"><span data-stu-id="3d956-117">Set any of the following properties to determine how your service will function.</span></span>  
  
    |<span data-ttu-id="3d956-118">属性</span><span class="sxs-lookup"><span data-stu-id="3d956-118">Property</span></span>|<span data-ttu-id="3d956-119">设置</span><span class="sxs-lookup"><span data-stu-id="3d956-119">Setting</span></span>|  
    |--------------|-------------|  
    |<xref:System.ServiceProcess.ServiceBase.CanStop%2A>|<span data-ttu-id="3d956-120">`True` 表示服务将接受请求停止运行；`false` 将阻止服务被停止。</span><span class="sxs-lookup"><span data-stu-id="3d956-120">`True` to indicate that the service will accept requests to stop running; `false` to prevent the service from being stopped.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.CanShutdown%2A>|<span data-ttu-id="3d956-121">`True` 表示当服务所在的计算机关机时服务需要接受通知，启用它来调用 <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> 过程。</span><span class="sxs-lookup"><span data-stu-id="3d956-121">`True` to indicate that the service wants to receive notification when the computer on which it lives shuts down, enabling it to call the <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> procedure.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A>|<span data-ttu-id="3d956-122">`True` 表示服务将接受请求暂停或恢复运行；`false` 将阻止服务被暂停或恢复。</span><span class="sxs-lookup"><span data-stu-id="3d956-122">`True` to indicate that the service will accept requests to pause or to resume running; `false` to prevent the service from being paused and resumed.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.CanHandlePowerEvent%2A>|<span data-ttu-id="3d956-123">`True`若要指示服务可处理的计算机的电源状态; 的更改通知`false`以防止该服务正在通知这些更改。</span><span class="sxs-lookup"><span data-stu-id="3d956-123">`True` to indicate that the service can handle notification of changes to the computer's power status; `false` to prevent the service from being notified of these changes.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.AutoLog%2A>|<span data-ttu-id="3d956-124">`True` 将在你的服务执行操作时向应用程序事件日志写入信息条目；`false` 将禁用该功能。</span><span class="sxs-lookup"><span data-stu-id="3d956-124">`True` to write informational entries to the Application event log when your service performs an action; `false` to disable this functionality.</span></span> <span data-ttu-id="3d956-125">有关详细信息，请参阅[How to： 日志信息关于服务](../../../docs/framework/windows-services/how-to-log-information-about-services.md)。</span><span class="sxs-lookup"><span data-stu-id="3d956-125">For more information, see [How to: Log Information About Services](../../../docs/framework/windows-services/how-to-log-information-about-services.md).</span></span> <span data-ttu-id="3d956-126">**注意：**默认情况下，<xref:System.ServiceProcess.ServiceBase.AutoLog%2A>设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="3d956-126">**Note:**  By default, <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> is set to `true`.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="3d956-127">当<xref:System.ServiceProcess.ServiceBase.CanStop%2A>或<xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A>设置为`false`、**服务控制管理器**将禁用相应的菜单选项，来停止、 暂停或继续服务。</span><span class="sxs-lookup"><span data-stu-id="3d956-127">When <xref:System.ServiceProcess.ServiceBase.CanStop%2A> or <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> are set to `false`, the **Service Control Manager** will disable the corresponding menu options to stop, pause, or continue the service.</span></span>  
  
4.  <span data-ttu-id="3d956-128">访问代码编辑器，并填写你想要对 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 和 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 过程的处理。</span><span class="sxs-lookup"><span data-stu-id="3d956-128">Access the Code Editor and fill in the processing you want for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> procedures.</span></span>  
  
5.  <span data-ttu-id="3d956-129">替代你想要定义功能的任何其他方法。</span><span class="sxs-lookup"><span data-stu-id="3d956-129">Override any other methods for which you want to define functionality.</span></span>  
  
6.  <span data-ttu-id="3d956-130">添加服务应用程序所必需的安装程序。</span><span class="sxs-lookup"><span data-stu-id="3d956-130">Add the necessary installers for your service application.</span></span> <span data-ttu-id="3d956-131">有关详细信息，请参阅[如何： 添加到你的服务应用程序的安装程序](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)。</span><span class="sxs-lookup"><span data-stu-id="3d956-131">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
7.  <span data-ttu-id="3d956-132">通过选择生成你的项目**生成解决方案**从**生成**菜单。</span><span class="sxs-lookup"><span data-stu-id="3d956-132">Build your project by selecting **Build Solution** from the **Build** menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3d956-133">不要通过按 F5 来运行你的项目 — 你无法通过这种方式运行服务项目。</span><span class="sxs-lookup"><span data-stu-id="3d956-133">Do not press F5 to run your project — you cannot run a service project in this way.</span></span>  
  
8.  <span data-ttu-id="3d956-134">安装服务。</span><span class="sxs-lookup"><span data-stu-id="3d956-134">Install the service.</span></span> <span data-ttu-id="3d956-135">有关更多信息，请参见 [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)。</span><span class="sxs-lookup"><span data-stu-id="3d956-135">For more information, see [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d956-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d956-136">See Also</span></span>  
 [<span data-ttu-id="3d956-137">Windows 服务应用程序介绍</span><span class="sxs-lookup"><span data-stu-id="3d956-137">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="3d956-138">如何：以编程方式编写服务</span><span class="sxs-lookup"><span data-stu-id="3d956-138">How to: Write Services Programmatically</span></span>](../../../docs/framework/windows-services/how-to-write-services-programmatically.md)  
 [<span data-ttu-id="3d956-139">如何：将安装程序添加到服务应用程序</span><span class="sxs-lookup"><span data-stu-id="3d956-139">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [<span data-ttu-id="3d956-140">如何：记录关于服务的信息</span><span class="sxs-lookup"><span data-stu-id="3d956-140">How to: Log Information About Services</span></span>](../../../docs/framework/windows-services/how-to-log-information-about-services.md)  
 [<span data-ttu-id="3d956-141">如何：启动服务</span><span class="sxs-lookup"><span data-stu-id="3d956-141">How to: Start Services</span></span>](../../../docs/framework/windows-services/how-to-start-services.md)  
 [<span data-ttu-id="3d956-142">如何：为服务指定安全上下文</span><span class="sxs-lookup"><span data-stu-id="3d956-142">How to: Specify the Security Context for Services</span></span>](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)  
 [<span data-ttu-id="3d956-143">如何：安装和卸载服务</span><span class="sxs-lookup"><span data-stu-id="3d956-143">How to: Install and Uninstall Services</span></span>](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [<span data-ttu-id="3d956-144">演练：在组件设计器中创建 Windows 服务应用程序</span><span class="sxs-lookup"><span data-stu-id="3d956-144">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
