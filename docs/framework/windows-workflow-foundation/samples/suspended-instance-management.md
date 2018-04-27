---
title: 挂起的实例管理
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f5ca3faa-ba1f-4857-b92c-d927e4b29598
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5f5073e9de217637141d7e3c9d70bb6a0b7a9cd0
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
# <a name="suspended-instance-management"></a><span data-ttu-id="4fb50-102">挂起的实例管理</span><span class="sxs-lookup"><span data-stu-id="4fb50-102">Suspended Instance Management</span></span>
<span data-ttu-id="4fb50-103">此示例演示如何管理已挂起的工作流实例。</span><span class="sxs-lookup"><span data-stu-id="4fb50-103">This sample demonstrates how to manage workflow instances that have been suspended.</span></span>  <span data-ttu-id="4fb50-104"><xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> 的默认操作为 `AbandonAndSuspend`。</span><span class="sxs-lookup"><span data-stu-id="4fb50-104">The default action for <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is `AbandonAndSuspend`.</span></span> <span data-ttu-id="4fb50-105">这意味着，在默认情况下，从 <xref:System.ServiceModel.WorkflowServiceHost> 中承载的某个工作流实例抛出的未处理异常会导致从内存中释放（放弃）该实例，而该实例的持久版本将被标记为已挂起。</span><span class="sxs-lookup"><span data-stu-id="4fb50-105">This means that by default, unhandled exceptions thrown from a workflow instance hosted in the <xref:System.ServiceModel.WorkflowServiceHost> will cause the instance to be disposed from memory (abandoned) and the durable/persisted version of the instance to be marked as suspended.</span></span> <span data-ttu-id="4fb50-106">已挂起的工作流实例在取消挂起之前无法运行。</span><span class="sxs-lookup"><span data-stu-id="4fb50-106">A suspended workflow instance will not be able to run until it has been unsuspended.</span></span>  
  
 <span data-ttu-id="4fb50-107">此示例演示如何实现用于查询已挂起实例的命令行实用工具，以及如何为用户提供恢复或终止实例的选项。</span><span class="sxs-lookup"><span data-stu-id="4fb50-107">The sample shows how a command-line utility can be implemented to query for suspended instances, and how to give the user the option to resume or terminate the instance.</span></span> <span data-ttu-id="4fb50-108">在此示例中，一个工作流服务有意引发异常，从而使该服务挂起。</span><span class="sxs-lookup"><span data-stu-id="4fb50-108">In this sample, a workflow service intentionally throws an exception, causing it to become suspended.</span></span> <span data-ttu-id="4fb50-109">然后可以使用命令行实用工具查询该实例，并随后恢复或终止该实例。</span><span class="sxs-lookup"><span data-stu-id="4fb50-109">The command-line utility can then be used to query for the instance and subsequently resume or terminate the instance.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="4fb50-110">演示</span><span class="sxs-lookup"><span data-stu-id="4fb50-110">Demonstrates</span></span>  
 <span data-ttu-id="4fb50-111"><xref:System.ServiceModel.WorkflowServiceHost> 与<xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>和<xref:System.ServiceModel.Activities.WorkflowControlEndpoint>Windows Workflow Foundation (WF) 中。</span><span class="sxs-lookup"><span data-stu-id="4fb50-111"><xref:System.ServiceModel.WorkflowServiceHost> with <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> and <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> in Windows Workflow Foundation (WF).</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="4fb50-112">讨论</span><span class="sxs-lookup"><span data-stu-id="4fb50-112">Discussion</span></span>  
 <span data-ttu-id="4fb50-113">本示例中实现的命令行实用工具特定于 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] 中附带的 SQL 实例存储区实现。</span><span class="sxs-lookup"><span data-stu-id="4fb50-113">The command-line utility implemented in this sample is specific to the SQL instance store implementation that ships in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span> <span data-ttu-id="4fb50-114">如果您具有该实例存储区的自定义实现，则可以使用特定于您实例存储区的实现替换示例中的 `WorkflowInstanceCommand` 实现，来改编此实用工具。</span><span class="sxs-lookup"><span data-stu-id="4fb50-114">If you have a custom implementation of the instance store, then you can adapt this utility by replacing the `WorkflowInstanceCommand` implementations in the sample with implementations that are specific to your instance store.</span></span>  
  
 <span data-ttu-id="4fb50-115">所提供的实现直接针对 SQL 实例存储区来运行 SQL 命令以列出挂起的实例，并依赖于添加到 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> 的 <xref:System.ServiceModel.WorkflowServiceHost>，以便恢复或终止实例。</span><span class="sxs-lookup"><span data-stu-id="4fb50-115">The provided implementation runs SQL commands against the SQL instance store directly to list suspended instances, and it relies on a <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> added to the <xref:System.ServiceModel.WorkflowServiceHost> in order to resume or terminate the instances.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4fb50-116">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="4fb50-116">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="4fb50-117">此示例要求启用以下 Windows 组件：</span><span class="sxs-lookup"><span data-stu-id="4fb50-117">This sample requires that the following Windows components are enabled:</span></span>  
  
    1.  <span data-ttu-id="4fb50-118">Microsoft Message Queues (MSMQ) Server</span><span class="sxs-lookup"><span data-stu-id="4fb50-118">Microsoft Message Queues (MSMQ) Server</span></span>  
  
    2.  <span data-ttu-id="4fb50-119">SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="4fb50-119">SQL Server Express</span></span>  
  
2.  <span data-ttu-id="4fb50-120">设置 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="4fb50-120">Set up the SQL Server database.</span></span>  
  
    1.  <span data-ttu-id="4fb50-121">从[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]命令提示符下，运行 SuspendedInstanceManagement 示例目录中，执行以下从的"setup.cmd":</span><span class="sxs-lookup"><span data-stu-id="4fb50-121">From a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt, run "setup.cmd" from the SuspendedInstanceManagement sample directory, which does the following:</span></span>  
  
        1.  <span data-ttu-id="4fb50-122">使用 SQL Server Express 创建持久性数据库。</span><span class="sxs-lookup"><span data-stu-id="4fb50-122">Creates a persistence database using SQL Server Express.</span></span> <span data-ttu-id="4fb50-123">如果持久性数据库已存在，则删除该数据库并重新创建一个</span><span class="sxs-lookup"><span data-stu-id="4fb50-123">If the persistence database already exists, then it is dropped and re-created</span></span>  
  
        2.  <span data-ttu-id="4fb50-124">设置持久性数据库。</span><span class="sxs-lookup"><span data-stu-id="4fb50-124">Sets up the database for persistence.</span></span>  
  
        3.  <span data-ttu-id="4fb50-125">将 IIS APPPOOL\DefaultAppPool 和 NT AUTHORITY\Network Service 添加到设置持久性数据库时定义的 InstanceStoreUsers 角色。</span><span class="sxs-lookup"><span data-stu-id="4fb50-125">Adds IIS APPPOOL\DefaultAppPool and NT AUTHORITY\Network Service to the InstanceStoreUsers role that was defined when setting up the database for persistence.</span></span>  
  
3.  <span data-ttu-id="4fb50-126">设置服务队列。</span><span class="sxs-lookup"><span data-stu-id="4fb50-126">Set up the service queue.</span></span>  
  
    1.  <span data-ttu-id="4fb50-127">在[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]，右键单击**SampleWorkflowApp**项目，然后单击**设为启动项目**。</span><span class="sxs-lookup"><span data-stu-id="4fb50-127">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], right-click the **SampleWorkflowApp** project and click **Set as Startup Project**.</span></span>  
  
    2.  <span data-ttu-id="4fb50-128">编译和运行 SampleWorkflowApp 按**F5**。</span><span class="sxs-lookup"><span data-stu-id="4fb50-128">Compile and run the SampleWorkflowApp by pressing **F5**.</span></span> <span data-ttu-id="4fb50-129">这将创建所需队列。</span><span class="sxs-lookup"><span data-stu-id="4fb50-129">This will create the required queue.</span></span>  
  
    3.  <span data-ttu-id="4fb50-130">按**Enter**停止 SampleWorkflowApp。</span><span class="sxs-lookup"><span data-stu-id="4fb50-130">Press **Enter** to stop the SampleWorkflowApp.</span></span>  
  
    4.  <span data-ttu-id="4fb50-131">通过在命令提示符下运行 Compmgmt.msc 来打开计算机管理控制台。</span><span class="sxs-lookup"><span data-stu-id="4fb50-131">Open the Computer Management console by running Compmgmt.msc from a command prompt.</span></span>  
  
    5.  <span data-ttu-id="4fb50-132">展开**服务和应用程序**，**消息队列**，**专用队列**。</span><span class="sxs-lookup"><span data-stu-id="4fb50-132">Expand **Service and Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
    6.  <span data-ttu-id="4fb50-133">右键单击**ReceiveTx**队列，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="4fb50-133">Right click the **ReceiveTx** queue and select **Properties**.</span></span>  
  
    7.  <span data-ttu-id="4fb50-134">选择**安全**选项卡上，并允许**Everyone**对具有权限**接收消息**，**扫视消息**，和**发送消息**。</span><span class="sxs-lookup"><span data-stu-id="4fb50-134">Select the **Security** tab and allow **Everyone** to have permissions to **Receive Message**, **Peek Message**, and **Send Message**.</span></span>  
  
4.  <span data-ttu-id="4fb50-135">现在运行示例。</span><span class="sxs-lookup"><span data-stu-id="4fb50-135">Now, run the sample.</span></span>  
  
    1.  <span data-ttu-id="4fb50-136">在[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]，再次运行 SampleWorkflowApp 项目而不进行调试按**Ctrl + F5**。</span><span class="sxs-lookup"><span data-stu-id="4fb50-136">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], run the SampleWorkflowApp project again without debugging by pressing **Ctrl+F5**.</span></span> <span data-ttu-id="4fb50-137">将在控制台窗口中输出两个终结点地址：一个用于应用程序终结点，另一个来自 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>。</span><span class="sxs-lookup"><span data-stu-id="4fb50-137">Two endpoint addresses will be printed in the console window: one for the application endpoint and then other from the <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>.</span></span> <span data-ttu-id="4fb50-138">随后会创建一个工作流实例，该实例的跟踪记录会出现在控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="4fb50-138">A workflow instance is then created, and tracking records for that instance will appear in the console window.</span></span> <span data-ttu-id="4fb50-139">该工作流实例会引发异常，从而导致该实例挂起或中止。</span><span class="sxs-lookup"><span data-stu-id="4fb50-139">The workflow instance will throw an exception causing the instance to be suspended and aborted.</span></span>  
  
    2.  <span data-ttu-id="4fb50-140">随后可以使用命令行实用工具对这些实例中的任何一个进行进一步操作。</span><span class="sxs-lookup"><span data-stu-id="4fb50-140">The command-line utility can then be used to take further action on any of these instances.</span></span> <span data-ttu-id="4fb50-141">命令行自变量的语法如下：</span><span class="sxs-lookup"><span data-stu-id="4fb50-141">The syntax for command line arguments is as follows::</span></span>  
  
         `SuspendedInstanceManagement -Command:[CommandName] -Server:[ServerName] -Database:[DatabaseName] -InstanceId:[InstanceId]`  
  
         <span data-ttu-id="4fb50-142">支持的命令为：`Query`、`Resume` 和 `Terminate`。</span><span class="sxs-lookup"><span data-stu-id="4fb50-142">The supported commands are: `Query`, `Resume`, and `Terminate`.</span></span>  <span data-ttu-id="4fb50-143">只有 `Resume` 和 `Terminate` 才需要 InstanceId 开关。</span><span class="sxs-lookup"><span data-stu-id="4fb50-143">The InstanceId switch is only required for `Resume` and `Terminate` operations.</span></span>  
  
#### <a name="to-cleanup-optional"></a><span data-ttu-id="4fb50-144">清理（可选）</span><span class="sxs-lookup"><span data-stu-id="4fb50-144">To cleanup (Optional)</span></span>  
  
1.  <span data-ttu-id="4fb50-145">通过在 `vs2010` 命令提示符下运行 Compmgmt.msc 来打开计算机管理控制台。</span><span class="sxs-lookup"><span data-stu-id="4fb50-145">Open the Computer Management console by running Compmgmt.msc from a `vs2010` command prompt.</span></span>  
  
2.  <span data-ttu-id="4fb50-146">展开**服务和应用程序**，**消息队列**，**专用队列**。</span><span class="sxs-lookup"><span data-stu-id="4fb50-146">Expand **Service and Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
3.  <span data-ttu-id="4fb50-147">删除**ReceiveTx**队列。</span><span class="sxs-lookup"><span data-stu-id="4fb50-147">Delete the **ReceiveTx** queue.</span></span>  
  
4.  <span data-ttu-id="4fb50-148">若要删除持久性数据库，请运行 cleanup.cmd。</span><span class="sxs-lookup"><span data-stu-id="4fb50-148">To remove the persistence database, run cleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4fb50-149">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="4fb50-149">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4fb50-150">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="4fb50-150">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4fb50-151">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="4fb50-151">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4fb50-152">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="4fb50-152">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Application\SuspendedInstanceManagement`
