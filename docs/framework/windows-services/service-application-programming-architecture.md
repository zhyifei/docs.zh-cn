---
title: "服务应用程序编程体系结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ServiceController components, programming architecture
- ServiceBase class, service states
- Windows Service applications, code model
- services, programming architecture
- ServiceController class
- services, states
- ServiceProcessInstaller class, service application code model
- Windows Service applications, states
ms.assetid: 83230026-d068-4174-97ff-e264c896eb2f
caps.latest.revision: "15"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: e9c16f2e603a3ce9bbc59be4e01aa492239d2c63
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="service-application-programming-architecture"></a><span data-ttu-id="4b683-102">服务应用程序编程体系结构</span><span class="sxs-lookup"><span data-stu-id="4b683-102">Service Application Programming Architecture</span></span>
<span data-ttu-id="4b683-103">Windows 服务应用程序都基于从继承的类<xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>类。</span><span class="sxs-lookup"><span data-stu-id="4b683-103">Windows Service applications are based on a class that inherits from the <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="4b683-104">重写此类的方法，并为这些表来确定你的服务的行为方式定义功能。</span><span class="sxs-lookup"><span data-stu-id="4b683-104">You override methods from this class and define functionality for them to determine how your service behaves.</span></span>  
  
 <span data-ttu-id="4b683-105">所涉及的服务创建的主类如下：</span><span class="sxs-lookup"><span data-stu-id="4b683-105">The main classes involved in service creation are:</span></span>  
  
-   <span data-ttu-id="4b683-106"><xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>-您重写方法从<xref:System.ServiceProcess.ServiceBase>类创建服务时，并定义代码，以确定如何在此您服务的函数继承类。</span><span class="sxs-lookup"><span data-stu-id="4b683-106"><xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> — You override methods from the <xref:System.ServiceProcess.ServiceBase> class when creating a service and define the code to determine how your service functions in this inherited class.</span></span>  
  
-   <span data-ttu-id="4b683-107"><xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=nameWithType>和<xref:System.ServiceProcess.ServiceInstaller?displayProperty=nameWithType>-使用这些类用于安装和卸载你的服务。</span><span class="sxs-lookup"><span data-stu-id="4b683-107"><xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=nameWithType> and <xref:System.ServiceProcess.ServiceInstaller?displayProperty=nameWithType> —You use these classes to install and uninstall your service.</span></span>  
  
 <span data-ttu-id="4b683-108">此外，类名为<xref:System.ServiceProcess.ServiceController>可用于操作服务本身。</span><span class="sxs-lookup"><span data-stu-id="4b683-108">In addition, a class named <xref:System.ServiceProcess.ServiceController> can be used to manipulate the service itself.</span></span> <span data-ttu-id="4b683-109">此类不参与创建服务，但可以用于启动和停止该服务，将命令传递到它，并返回一系列的枚举。</span><span class="sxs-lookup"><span data-stu-id="4b683-109">This class is not involved in the creation of a service, but can be used to start and stop the service, pass commands to it, and return a series of enumerations.</span></span>  
  
## <a name="defining-your-services-behavior"></a><span data-ttu-id="4b683-110">定义你的服务行为</span><span class="sxs-lookup"><span data-stu-id="4b683-110">Defining Your Service's Behavior</span></span>  
 <span data-ttu-id="4b683-111">在服务类中，您重写基类函数，以确定你的服务的状态更改服务控制管理器中时，会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="4b683-111">In your service class, you override base class functions that determine what happens when the state of your service is changed in the Services Control Manager.</span></span> <span data-ttu-id="4b683-112"><xref:System.ServiceProcess.ServiceBase>类公开以下方法，可以重写以添加自定义行为。</span><span class="sxs-lookup"><span data-stu-id="4b683-112">The <xref:System.ServiceProcess.ServiceBase> class exposes the following methods, which you can override to add custom behavior.</span></span>  
  
|<span data-ttu-id="4b683-113">方法</span><span class="sxs-lookup"><span data-stu-id="4b683-113">Method</span></span>|<span data-ttu-id="4b683-114">重写到</span><span class="sxs-lookup"><span data-stu-id="4b683-114">Override to</span></span>|  
|------------|-----------------|  
|<xref:System.ServiceProcess.ServiceBase.OnStart%2A>|<span data-ttu-id="4b683-115">指示在你的服务开始运行时，应采取哪些措施。</span><span class="sxs-lookup"><span data-stu-id="4b683-115">Indicate what actions should be taken when your service starts running.</span></span> <span data-ttu-id="4b683-116">在此过程中为你的服务以执行有用的工作，必须编写代码。</span><span class="sxs-lookup"><span data-stu-id="4b683-116">You must write code in this procedure for your service to perform useful work.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnPause%2A>|<span data-ttu-id="4b683-117">指示当你的服务已暂停时应发生。</span><span class="sxs-lookup"><span data-stu-id="4b683-117">Indicate what should happen when your service is paused.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnStop%2A>|<span data-ttu-id="4b683-118">指示当你的服务停止运行时应发生。</span><span class="sxs-lookup"><span data-stu-id="4b683-118">Indicate what should happen when your service stops running.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>|<span data-ttu-id="4b683-119">指示当你的服务后继续正常工作正在暂停时应发生。</span><span class="sxs-lookup"><span data-stu-id="4b683-119">Indicate what should happen when your service resumes normal functioning after being paused.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>|<span data-ttu-id="4b683-120">指示应发生之前你的系统关闭，如果你的服务运行在该时间。</span><span class="sxs-lookup"><span data-stu-id="4b683-120">Indicate what should happen just prior to your system shutting down, if your service is running at that time.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnCustomCommand%2A>|<span data-ttu-id="4b683-121">指示当你的服务接收自定义命令时应发生。</span><span class="sxs-lookup"><span data-stu-id="4b683-121">Indicate what should happen when your service receives a custom command.</span></span> <span data-ttu-id="4b683-122">自定义命令的详细信息，请参阅 MSDN 联机。</span><span class="sxs-lookup"><span data-stu-id="4b683-122">For more information on custom commands, see MSDN online.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnPowerEvent%2A>|<span data-ttu-id="4b683-123">指示服务应如何响应收到电源管理事件时，如电池电量不足或挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="4b683-123">Indicate how the service should respond when a power management event is received, such as a low battery or suspended operation.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="4b683-124">这些方法表示在其生存期内; 通过将移动的服务的状态服务从一个状态转换到下一步。</span><span class="sxs-lookup"><span data-stu-id="4b683-124">These methods represent states that the service moves through in its lifetime; the service transitions from one state to the next.</span></span> <span data-ttu-id="4b683-125">例如，你将永远不会使服务正常响应<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>命令之前<xref:System.ServiceProcess.ServiceBase.OnStart%2A>已调用。</span><span class="sxs-lookup"><span data-stu-id="4b683-125">For example, you will never get the service to respond to an <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> command before <xref:System.ServiceProcess.ServiceBase.OnStart%2A> has been called.</span></span>  
  
 <span data-ttu-id="4b683-126">有几个其他属性和方法所感兴趣。</span><span class="sxs-lookup"><span data-stu-id="4b683-126">There are several other properties and methods that are of interest.</span></span> <span data-ttu-id="4b683-127">这些方法包括：</span><span class="sxs-lookup"><span data-stu-id="4b683-127">These include:</span></span>  
  
-   <span data-ttu-id="4b683-128"><xref:System.ServiceProcess.ServiceBase.Run%2A>方法<xref:System.ServiceProcess.ServiceBase>类。</span><span class="sxs-lookup"><span data-stu-id="4b683-128">The <xref:System.ServiceProcess.ServiceBase.Run%2A> method on the <xref:System.ServiceProcess.ServiceBase> class.</span></span> <span data-ttu-id="4b683-129">这是服务的主入口点。</span><span class="sxs-lookup"><span data-stu-id="4b683-129">This is the main entry point for the service.</span></span> <span data-ttu-id="4b683-130">当你创建使用 Windows 服务模板的服务时，在你的应用程序中插入代码`Main`方法以运行服务。</span><span class="sxs-lookup"><span data-stu-id="4b683-130">When you create a service using the Windows Service template, code is inserted in your application's `Main` method to run the service.</span></span> <span data-ttu-id="4b683-131">此代码类似如下所示：</span><span class="sxs-lookup"><span data-stu-id="4b683-131">This code looks like this:</span></span>  
  
     [!code-csharp[VbRadconService#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#6)]
     [!code-vb[VbRadconService#6](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#6)]  
  
    > [!NOTE]
    >  <span data-ttu-id="4b683-132">这些示例使用类型的数组<xref:System.ServiceProcess.ServiceBase>、 在其中可以添加你的应用程序包含每个服务，并随后的所有服务可以运行在一起。</span><span class="sxs-lookup"><span data-stu-id="4b683-132">These examples use an array of type <xref:System.ServiceProcess.ServiceBase>, into which each service your application contains can be added, and then all of the services can be run together.</span></span> <span data-ttu-id="4b683-133">如果你仅创建单一服务，但是，你可以选择不使用数组而只是声明新对象继承自<xref:System.ServiceProcess.ServiceBase>，然后运行它。</span><span class="sxs-lookup"><span data-stu-id="4b683-133">If you are only creating a single service, however, you might choose not to use the array and simply declare a new object inheriting from <xref:System.ServiceProcess.ServiceBase> and then run it.</span></span> <span data-ttu-id="4b683-134">有关示例，请参阅[如何： 编写服务以编程方式](../../../docs/framework/windows-services/how-to-write-services-programmatically.md)。</span><span class="sxs-lookup"><span data-stu-id="4b683-134">For an example, see [How to: Write Services Programmatically](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).</span></span>  
  
-   <span data-ttu-id="4b683-135">上的属性的一系列<xref:System.ServiceProcess.ServiceBase>类。</span><span class="sxs-lookup"><span data-stu-id="4b683-135">A series of properties on the <xref:System.ServiceProcess.ServiceBase> class.</span></span> <span data-ttu-id="4b683-136">这些文件确定何种方法可以在服务上调用。</span><span class="sxs-lookup"><span data-stu-id="4b683-136">These determine what methods can be called on your service.</span></span> <span data-ttu-id="4b683-137">例如，当<xref:System.ServiceProcess.ServiceBase.CanStop%2A>属性设置为`true`、<xref:System.ServiceProcess.ServiceBase.OnStop%2A>可以调用在服务上的方法。</span><span class="sxs-lookup"><span data-stu-id="4b683-137">For example, when the <xref:System.ServiceProcess.ServiceBase.CanStop%2A> property is set to `true`, the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method on your service can be called.</span></span> <span data-ttu-id="4b683-138">当<xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A>属性设置为`true`、<xref:System.ServiceProcess.ServiceBase.OnPause%2A>和<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>方法可以调用。</span><span class="sxs-lookup"><span data-stu-id="4b683-138">When the <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> property is set to `true`, the <xref:System.ServiceProcess.ServiceBase.OnPause%2A> and <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> methods can be called.</span></span> <span data-ttu-id="4b683-139">当你将设置到这些属性之一`true`，然后应重写，并为关联的方法定义处理。</span><span class="sxs-lookup"><span data-stu-id="4b683-139">When you set one of these properties to `true`, you should then override and define processing for the associated methods.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4b683-140">你的服务必须重写至少<xref:System.ServiceProcess.ServiceBase.OnStart%2A>和<xref:System.ServiceProcess.ServiceBase.OnStop%2A>才有用。</span><span class="sxs-lookup"><span data-stu-id="4b683-140">Your service must override at least <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> to be useful.</span></span>  
  
 <span data-ttu-id="4b683-141">你还可以使用名为的组件<xref:System.ServiceProcess.ServiceController>与进行通信并控制现有服务的行为。</span><span class="sxs-lookup"><span data-stu-id="4b683-141">You can also use a component called the <xref:System.ServiceProcess.ServiceController> to communicate with and control the behavior of an existing service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b683-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b683-142">See Also</span></span>  
 [<span data-ttu-id="4b683-143">Windows 服务应用程序简介</span><span class="sxs-lookup"><span data-stu-id="4b683-143">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="4b683-144">如何： 创建 Windows 服务</span><span class="sxs-lookup"><span data-stu-id="4b683-144">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)
