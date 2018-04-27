---
title: 如何：启动服务
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows Service applications, starting
- services, starting
ms.assetid: 9ea77955-2d96-4c3d-913c-14db7604cdad
caps.latest.revision: 16
author: ghogen
ms.author: ghogen
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 47e27f579c0ed7d1be0b061bc6e79bba0c060abb
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-start-services"></a><span data-ttu-id="71d7e-102">如何：启动服务</span><span class="sxs-lookup"><span data-stu-id="71d7e-102">How to: Start Services</span></span>
<span data-ttu-id="71d7e-103">安装的服务后，必须启动。</span><span class="sxs-lookup"><span data-stu-id="71d7e-103">After a service is installed, it must be started.</span></span> <span data-ttu-id="71d7e-104">从开始调用<xref:System.ServiceProcess.ServiceBase.OnStart%2A>服务类的方法。</span><span class="sxs-lookup"><span data-stu-id="71d7e-104">Starting calls the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method on the service class.</span></span> <span data-ttu-id="71d7e-105">通常情况下，<xref:System.ServiceProcess.ServiceBase.OnStart%2A>方法定义有用的服务将执行的工作。</span><span class="sxs-lookup"><span data-stu-id="71d7e-105">Usually, the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method defines the useful work the service will perform.</span></span> <span data-ttu-id="71d7e-106">服务启动后，它保持活动状态直到被手动暂停或停止。</span><span class="sxs-lookup"><span data-stu-id="71d7e-106">After a service starts, it remains active until it is manually paused or stopped.</span></span>  
  
 <span data-ttu-id="71d7e-107">服务可以设置自动或手动启动。</span><span class="sxs-lookup"><span data-stu-id="71d7e-107">Services can be set up to start automatically or manually.</span></span> <span data-ttu-id="71d7e-108">重新启动或首次打开在其安装的计算机时，将启动服务，它会自动启动。</span><span class="sxs-lookup"><span data-stu-id="71d7e-108">A service that starts automatically will be started when the computer on which it is installed is rebooted or first turned on.</span></span> <span data-ttu-id="71d7e-109">用户必须启动手动启动服务。</span><span class="sxs-lookup"><span data-stu-id="71d7e-109">A user must start a service that starts manually.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71d7e-110">默认情况下，使用 Visual Studio 创建的服务设置为手动启动。</span><span class="sxs-lookup"><span data-stu-id="71d7e-110">By default, services created with Visual Studio are set to start manually.</span></span>  
  
 <span data-ttu-id="71d7e-111">有几种方法，你可以手动启动服务 — 从**服务器资源管理器**，从**服务控制管理器**，或代码中使用的组件调用<xref:System.ServiceProcess.ServiceController>。</span><span class="sxs-lookup"><span data-stu-id="71d7e-111">There are several ways you can manually start a service — from **Server Explorer**, from the **Services Control Manager**, or from code using a component called the <xref:System.ServiceProcess.ServiceController>.</span></span>  
  
 <span data-ttu-id="71d7e-112">你设置<xref:System.ServiceProcess.ServiceInstaller.StartType%2A>属性<xref:System.ServiceProcess.ServiceInstaller>类以确定是否应手动或自动启动服务。</span><span class="sxs-lookup"><span data-stu-id="71d7e-112">You set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property on the <xref:System.ServiceProcess.ServiceInstaller> class to determine whether a service should be started manually or automatically.</span></span>  
  
### <a name="to-specify-how-a-service-should-start"></a><span data-ttu-id="71d7e-113">若要指定服务应如何启动</span><span class="sxs-lookup"><span data-stu-id="71d7e-113">To specify how a service should start</span></span>  
  
1.  <span data-ttu-id="71d7e-114">创建你的服务之后, 添加为其所必需的安装。</span><span class="sxs-lookup"><span data-stu-id="71d7e-114">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="71d7e-115">有关详细信息，请参阅[如何： 添加到你的服务应用程序的安装程序](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)。</span><span class="sxs-lookup"><span data-stu-id="71d7e-115">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
2.  <span data-ttu-id="71d7e-116">在设计器中，单击的服务安装程序正在使用的服务。</span><span class="sxs-lookup"><span data-stu-id="71d7e-116">In the designer, click the service installer for the service you are working with.</span></span>  
  
3.  <span data-ttu-id="71d7e-117">在**属性**窗口中，设置<xref:System.ServiceProcess.ServiceInstaller.StartType%2A>属性设置为以下项之一：</span><span class="sxs-lookup"><span data-stu-id="71d7e-117">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to one of the following:</span></span>  
  
    |<span data-ttu-id="71d7e-118">若要安装服务</span><span class="sxs-lookup"><span data-stu-id="71d7e-118">To have your service install</span></span>|<span data-ttu-id="71d7e-119">将此值设置</span><span class="sxs-lookup"><span data-stu-id="71d7e-119">Set this value</span></span>|  
    |----------------------------------|--------------------|  
    |<span data-ttu-id="71d7e-120">重新启动计算机</span><span class="sxs-lookup"><span data-stu-id="71d7e-120">When the computer is restarted</span></span>|<span data-ttu-id="71d7e-121">**自动**</span><span class="sxs-lookup"><span data-stu-id="71d7e-121">**Automatic**</span></span>|  
    |<span data-ttu-id="71d7e-122">当显式用户操作启动服务</span><span class="sxs-lookup"><span data-stu-id="71d7e-122">When an explicit user action starts the service</span></span>|<span data-ttu-id="71d7e-123">**手动**</span><span class="sxs-lookup"><span data-stu-id="71d7e-123">**Manual**</span></span>|  
  
    > [!TIP]
    >  <span data-ttu-id="71d7e-124">若要防止根本正在启动你的服务，可以设置<xref:System.ServiceProcess.ServiceInstaller.StartType%2A>属性**禁用**。</span><span class="sxs-lookup"><span data-stu-id="71d7e-124">To prevent your service from being started at all, you can set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to **Disabled**.</span></span> <span data-ttu-id="71d7e-125">如果你将多次重新启动服务器，并想要通过阻止通常会启动中启动的服务可以节省时间，你可能需要这样做。</span><span class="sxs-lookup"><span data-stu-id="71d7e-125">You might do this if you are going to reboot a server several times and want to save time by preventing the services that would normally start from starting up.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="71d7e-126">安装你的服务后，可以更改这些属性和其他属性。</span><span class="sxs-lookup"><span data-stu-id="71d7e-126">These and other properties can be changed after your service is installed.</span></span>  
  
     <span data-ttu-id="71d7e-127">有几种方法可以启动服务具有其<xref:System.ServiceProcess.ServiceInstaller.StartType%2A>过程设置为**手动**-从**服务器资源管理器**，从**Windows 服务控制管理器**，或从代码。</span><span class="sxs-lookup"><span data-stu-id="71d7e-127">There are several ways you can start a service that has its <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> process set to **Manual** — from **Server Explorer**, from the **Windows Services Control Manager**, or from code.</span></span> <span data-ttu-id="71d7e-128">务必要注意并非所有这些方法实际的上下文中启动服务**服务控制管理器**;**服务器资源管理器**和启动服务的编程方法实际操作控制器。</span><span class="sxs-lookup"><span data-stu-id="71d7e-128">It is important to note that not all of these methods actually start the service in the context of the **Services Control Manager**; **Server Explorer** and programmatic methods of starting the service actually manipulate the controller.</span></span>  
  
### <a name="to-manually-start-a-service-from-server-explorer"></a><span data-ttu-id="71d7e-129">若要从服务器资源管理器中手动启动服务</span><span class="sxs-lookup"><span data-stu-id="71d7e-129">To manually start a service from Server Explorer</span></span>  
  
1.  <span data-ttu-id="71d7e-130">在**服务器资源管理器**，添加所需如果未列出的服务器。</span><span class="sxs-lookup"><span data-stu-id="71d7e-130">In **Server Explorer**, add the server you want if it is not already listed.</span></span> <span data-ttu-id="71d7e-131">有关详细信息，请参阅如何： 访问和初始化服务器资源管理器数据库资源管理器。</span><span class="sxs-lookup"><span data-stu-id="71d7e-131">For more information, see How to: Access and Initialize Server Explorer-Database Explorer.</span></span>  
  
2.  <span data-ttu-id="71d7e-132">展开**服务**节点，然后找到你想要启动的服务。</span><span class="sxs-lookup"><span data-stu-id="71d7e-132">Expand the **Services** node, and then locate the service you want to start.</span></span>  
  
3.  <span data-ttu-id="71d7e-133">右键单击服务名称，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="71d7e-133">Right-click the name of the service, and click **Start**.</span></span>  
  
### <a name="to-manually-start-a-service-from-services-control-manager"></a><span data-ttu-id="71d7e-134">若要手动启动服务从服务控制管理器</span><span class="sxs-lookup"><span data-stu-id="71d7e-134">To manually start a service from Services Control Manager</span></span>  
  
1.  <span data-ttu-id="71d7e-135">打开**服务控制管理器**通过执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="71d7e-135">Open the **Services Control Manager** by doing one of the following:</span></span>  
  
    -   <span data-ttu-id="71d7e-136">在 Windows XP 和 2000 Professional 中，右键单击**我的电脑**桌面，，然后单击**管理**。</span><span class="sxs-lookup"><span data-stu-id="71d7e-136">In Windows XP and 2000 Professional, right-click **My Computer** on the desktop, and then click **Manage**.</span></span> <span data-ttu-id="71d7e-137">在显示的对话框中，展开**服务和应用程序**节点。</span><span class="sxs-lookup"><span data-stu-id="71d7e-137">In the dialog box that appears, expand the **Services and Applications** node.</span></span>  
  
         <span data-ttu-id="71d7e-138">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="71d7e-138">\- or -</span></span>  
  
    -   <span data-ttu-id="71d7e-139">在 Windows Server 2003 和 Windows 2000 Server 中，单击**启动**，指向**程序**，单击**管理工具**，然后单击**服务**.</span><span class="sxs-lookup"><span data-stu-id="71d7e-139">In Windows Server 2003 and Windows 2000 Server, click **Start**, point to **Programs**, click **Administrative Tools**, and then click **Services**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="71d7e-140">在 Windows NT 4.0 版中，你可以打开此对话框中，从**控制面板**。</span><span class="sxs-lookup"><span data-stu-id="71d7e-140">In Windows NT version 4.0, you can open this dialog box from **Control Panel**.</span></span>  
  
     <span data-ttu-id="71d7e-141">现在，你应看到您的服务列在**服务**窗口部分。</span><span class="sxs-lookup"><span data-stu-id="71d7e-141">You should now see your service listed in the **Services** section of the window.</span></span>  
  
2.  <span data-ttu-id="71d7e-142">选择你的服务列表中，右键单击它，，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="71d7e-142">Select your service in the list, right-click it, and then click **Start**.</span></span>  
  
### <a name="to-manually-start-a-service-from-code"></a><span data-ttu-id="71d7e-143">若要从代码中手动启动服务</span><span class="sxs-lookup"><span data-stu-id="71d7e-143">To manually start a service from code</span></span>  
  
1.  <span data-ttu-id="71d7e-144">创建的实例<xref:System.ServiceProcess.ServiceController>类，并将其配置为与你想要管理的服务进行交互。</span><span class="sxs-lookup"><span data-stu-id="71d7e-144">Create an instance of the <xref:System.ServiceProcess.ServiceController> class, and configure it to interact with the service you want to administer.</span></span>  
  
2.  <span data-ttu-id="71d7e-145">调用 <xref:System.ServiceProcess.ServiceController.Start%2A> 方法以启动该服务。</span><span class="sxs-lookup"><span data-stu-id="71d7e-145">Call the <xref:System.ServiceProcess.ServiceController.Start%2A> method to start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71d7e-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="71d7e-146">See Also</span></span>  
 [<span data-ttu-id="71d7e-147">Windows 服务应用程序介绍</span><span class="sxs-lookup"><span data-stu-id="71d7e-147">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="71d7e-148">如何：创建 Windows 服务</span><span class="sxs-lookup"><span data-stu-id="71d7e-148">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [<span data-ttu-id="71d7e-149">如何：将安装程序添加到服务应用程序</span><span class="sxs-lookup"><span data-stu-id="71d7e-149">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)
