---
title: "如何：记录关于服务的信息"
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
- AutoLog property
- services, logging information
- Windows Service applications, logging information about
- event logs, service applications
- application event logs, service applications
- logs, service applications
ms.assetid: c0d8140f-c055-4d8e-a2e0-37358a550116
caps.latest.revision: "17"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 612b983f53f147102ddf7bab03d4ec6783dc4026
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-log-information-about-services"></a><span data-ttu-id="10e16-102">如何：记录关于服务的信息</span><span class="sxs-lookup"><span data-stu-id="10e16-102">How to: Log Information About Services</span></span>
<span data-ttu-id="10e16-103">默认情况下，所有 Windows 服务项目都具有与应用程序事件日志进行交互并向其中写入信息和异常的功能。</span><span class="sxs-lookup"><span data-stu-id="10e16-103">By default, all Windows Service projects have the ability to interact with the Application event log and write information and exceptions to it.</span></span> <span data-ttu-id="10e16-104">使用 <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> 属性可指示是否希望应用程序具有此功能。</span><span class="sxs-lookup"><span data-stu-id="10e16-104">You use the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property to indicate whether you want this functionality in your application.</span></span> <span data-ttu-id="10e16-105">默认情况下，用 Windows 服务项目模板创建的所有服务的记录都是打开的。</span><span class="sxs-lookup"><span data-stu-id="10e16-105">By default, logging is turned on for any service you create with the Windows Service project template.</span></span> <span data-ttu-id="10e16-106">可以使用静态形式的 <xref:System.Diagnostics.EventLog> 类将服务信息写入日志，而无需创建 <xref:System.Diagnostics.EventLog> 组件的实例或手动注册源。</span><span class="sxs-lookup"><span data-stu-id="10e16-106">You can use a static form of the <xref:System.Diagnostics.EventLog> class to write service information to a log without having to create an instance of an <xref:System.Diagnostics.EventLog> component or manually register a source.</span></span>  
  
 <span data-ttu-id="10e16-107">当记录打开时，服务的安装程序自动在安装了服务的计算机上的应用程序日志中，将项目中的每项服务注册为一个有效的事件源。</span><span class="sxs-lookup"><span data-stu-id="10e16-107">The installer for your service automatically registers each service in your project as a valid source of events with the Application log on the computer where the service is installed, when logging is turned on.</span></span> <span data-ttu-id="10e16-108">该服务在服务每次启动、停止、暂停、继续、安装和卸载时记录信息。</span><span class="sxs-lookup"><span data-stu-id="10e16-108">The service logs information each time the service is started, stopped, paused, resumed, installed, or uninstalled.</span></span> <span data-ttu-id="10e16-109">它还记录发生的所有失败。</span><span class="sxs-lookup"><span data-stu-id="10e16-109">It also logs any failures that occur.</span></span> <span data-ttu-id="10e16-110">当使用默认行为时，不需编写任何代码以便将项写入日志；服务自动为你处理此任务。</span><span class="sxs-lookup"><span data-stu-id="10e16-110">You do not need to write any code to write entries to the log when using the default behavior; the service handles this for you automatically.</span></span>  
  
 <span data-ttu-id="10e16-111">如果要向事件日志而不是应用程序日志中写入，则必须将 <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> 属性设置为 `false`，在服务代码内创建自定义事件日志，并将服务注册为该日志的有效项源。</span><span class="sxs-lookup"><span data-stu-id="10e16-111">If you want to write to an event log other than the Application log, you must set the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property to `false`, create your own custom event log within your services code, and register your service as a valid source of entries for that log.</span></span> <span data-ttu-id="10e16-112">然后必须编写代码，以在相关操作发生时将项记入日志。</span><span class="sxs-lookup"><span data-stu-id="10e16-112">You must then write code to record entries to the log whenever an action you're interested in occurs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10e16-113">如果使用一个自定义事件日志并配置服务应用程序写入该日志，则在代码中设置服务的 <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> 属性之前，不要尝试访问该事件日志。</span><span class="sxs-lookup"><span data-stu-id="10e16-113">If you use a custom event log and configure your service application to write to it, you must not attempt to access the event log before setting the service's <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property in your code.</span></span> <span data-ttu-id="10e16-114">事件日志需要此属性的值才可将服务注册为一个有效的事件源。</span><span class="sxs-lookup"><span data-stu-id="10e16-114">The event log needs this property's value to register your service as a valid source of events.</span></span>  
  
### <a name="to-enable-default-event-logging-for-your-service"></a><span data-ttu-id="10e16-115">为服务启用默认事件记录</span><span class="sxs-lookup"><span data-stu-id="10e16-115">To enable default event logging for your service</span></span>  
  
-   <span data-ttu-id="10e16-116">将组件的 <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="10e16-116">Set the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property for your component to `true`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="10e16-117">默认情况下，此属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="10e16-117">By default, this property is set to `true`.</span></span> <span data-ttu-id="10e16-118">不需要显式设置此属性，除非正在生成更复杂的处理，如计算一个条件然后根据该条件的结果设置 <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="10e16-118">You do not need to set this explicitly unless you are building more complex processing, such as evaluating a condition and then setting the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property based on the result of that condition.</span></span>  
  
### <a name="to-disable-event-logging-for-your-service"></a><span data-ttu-id="10e16-119">为服务禁用默认事件记录</span><span class="sxs-lookup"><span data-stu-id="10e16-119">To disable event logging for your service</span></span>  
  
-   <span data-ttu-id="10e16-120">将组件的 <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> 属性设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="10e16-120">Set the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property for your component to `false`.</span></span>  
  
     [!code-csharp[VbRadconService#17](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#17)]
     [!code-vb[VbRadconService#17](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#17)]  
  
### <a name="to-set-up-logging-to-a-custom-log"></a><span data-ttu-id="10e16-121">将记录设置为自定义日志</span><span class="sxs-lookup"><span data-stu-id="10e16-121">To set up logging to a custom log</span></span>  
  
1.  <span data-ttu-id="10e16-122">将 <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> 属性设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="10e16-122">Set the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property to `false`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="10e16-123">若要使用自定义日志，必须将 <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> 设置为 false 。</span><span class="sxs-lookup"><span data-stu-id="10e16-123">You must set <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> to false in order to use a custom log.</span></span>  
  
2.  <span data-ttu-id="10e16-124">在 Windows 服务应用程序中设置 <xref:System.Diagnostics.EventLog> 组件的一个实例。</span><span class="sxs-lookup"><span data-stu-id="10e16-124">Set up an instance of an <xref:System.Diagnostics.EventLog> component in your Windows Service application.</span></span>  
  
3.  <span data-ttu-id="10e16-125">通过调用 <xref:System.Diagnostics.EventLog.CreateEventSource%2A> 方法，并指定源字符串和要创建的日志文件的名称，创建一个自定义日志。</span><span class="sxs-lookup"><span data-stu-id="10e16-125">Create a custom log by calling the <xref:System.Diagnostics.EventLog.CreateEventSource%2A> method and specifying the source string and the name of the log file you want to create.</span></span>  
  
4.  <span data-ttu-id="10e16-126">将 <xref:System.Diagnostics.EventLog.Source%2A> 组件实例上的 <xref:System.Diagnostics.EventLog> 属性设置为在步骤 3 中创建的源字符串。</span><span class="sxs-lookup"><span data-stu-id="10e16-126">Set the <xref:System.Diagnostics.EventLog.Source%2A> property on the <xref:System.Diagnostics.EventLog> component instance to the source string you created in step 3.</span></span>  
  
5.  <span data-ttu-id="10e16-127">通过访问 <xref:System.Diagnostics.EventLog.WriteEntry%2A> 组件实例上的 <xref:System.Diagnostics.EventLog> 方法来编写项。</span><span class="sxs-lookup"><span data-stu-id="10e16-127">Write your entries by accessing the <xref:System.Diagnostics.EventLog.WriteEntry%2A> method on the <xref:System.Diagnostics.EventLog> component instance.</span></span>  
  
     <span data-ttu-id="10e16-128">下面的代码演示如何将记录设置为自定义日志。</span><span class="sxs-lookup"><span data-stu-id="10e16-128">The following code shows how to set up logging to a custom log.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="10e16-129">在此代码示例中，一个 <xref:System.Diagnostics.EventLog> 组件实例命名为 `eventLog1` （在 Visual Basic 中为`EventLog1` ）。</span><span class="sxs-lookup"><span data-stu-id="10e16-129">In this code example, an instance of an <xref:System.Diagnostics.EventLog> component is named `eventLog1` (`EventLog1` in Visual Basic).</span></span> <span data-ttu-id="10e16-130">如果在步骤 2 中创建具有另一名称的实例，请相应地更改代码。</span><span class="sxs-lookup"><span data-stu-id="10e16-130">If you created an instance with another name in step 2, change the code accordingly.</span></span>  
  
     [!code-csharp[VbRadconService#14](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#14)]
     [!code-vb[VbRadconService#14](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#14)]  
    [!code-csharp[VbRadconService#15](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#15)]
    [!code-vb[VbRadconService#15](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="10e16-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10e16-131">See Also</span></span>  
 [<span data-ttu-id="10e16-132">Windows 服务应用程序简介</span><span class="sxs-lookup"><span data-stu-id="10e16-132">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
