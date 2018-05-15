---
title: 持久延迟
ms.date: 03/30/2017
ms.assetid: 220ec240-b958-430c-81ff-b734a6aa97ae
ms.openlocfilehash: 5307b8144e17f91cd3ba8c2e385492f86c167820
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="durable-delay"></a><span data-ttu-id="fa1e9-102">持久延迟</span><span class="sxs-lookup"><span data-stu-id="fa1e9-102">Durable Delay</span></span>
<span data-ttu-id="fa1e9-103">此示例演示如何使用持久延迟，在持久延迟过程中，将把工作流保留到持久性设备。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-103">This sample demonstrates how to use a durable delay, which is a delay that persists the workflow to a durable device during the delay.</span></span> <span data-ttu-id="fa1e9-104">示例工作流包含发送到控制台并由延迟分隔的两个消息。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-104">The sample workflow contains two messages to the console that are separated by a delay.</span></span> <span data-ttu-id="fa1e9-105">触发延迟时，工作流会卸载，并在重新加载到内存中之前，在工作流实例存储中等待 5 秒。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-105">When the delay is triggered, the workflow is unloaded and waits 5 seconds in the workflow instance store before being reloaded in memory.</span></span>  
  
## <a name="workflow-details"></a><span data-ttu-id="fa1e9-106">工作流详细信息</span><span class="sxs-lookup"><span data-stu-id="fa1e9-106">Workflow Details</span></span>  
 <span data-ttu-id="fa1e9-107">工作流服务主机承载工作流，并通过加载和卸载工作流实例来对其进行管理。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-107">The workflow service host hosts the workflow and manages the workflow instances by loading and unloading them.</span></span> <span data-ttu-id="fa1e9-108">为了启动工作流定义的实例，此示例设置了一个代理，用于向工作流中的 <xref:System.ServiceModel.Activities.Receive> 活动发送消息。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-108">To start an instance of the workflow definition, the sample sets a proxy that sends a message to the <xref:System.ServiceModel.Activities.Receive> activity in the workflow.</span></span> <span data-ttu-id="fa1e9-109"><xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> 属性设置为 `true`，从而可以在接收到消息时创建工作流的新实例。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-109">The <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> property is set to `true`, enabling it to create a new instance of the workflow once it receives a message.</span></span>  
  
 <span data-ttu-id="fa1e9-110">下面的列表详细介绍初始化过程中工作流服务主机进行的设置。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-110">The following list details the set-up by the workflow service host during initialization.</span></span>  
  
1.  <span data-ttu-id="fa1e9-111">创建一个地址的服务主机 (http://localhost:8080/Client)。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-111">Creates a service host with an address (http://localhost:8080/Client).</span></span>  
  
2.  <span data-ttu-id="fa1e9-112">在该服务主机中创建一个终结点，以便与工作流内的 <xref:System.ServiceModel.Activities.Receive> 活动进行通信。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-112">Creates an endpoint in the service host to enable communication with the <xref:System.ServiceModel.Activities.Receive> activity inside the workflow.</span></span>  
  
3.  <span data-ttu-id="fa1e9-113">设置 SQL 实例存储区。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-113">Sets up a SQL instance store.</span></span>  
  
4.  <span data-ttu-id="fa1e9-114">添加一个卸载实例行为，指定工作流服务主机在什么条件下应将工作流实例卸载到 SQL 持久性存储区。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-114">Adds an unload instance behavior that specifies the conditions under which the workflow service host should unload a workflow instance to the SQL persistence store.</span></span> <span data-ttu-id="fa1e9-115">对于此示例，它在工作流进入空闲状态后（触发了延迟时）立即卸载实例。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-115">For this sample, it unloads the instance immediately after the workflow goes idle (when the delay is triggered).</span></span>  
  
5.  <span data-ttu-id="fa1e9-116">创建向工作流中的 <xref:System.ServiceModel.Activities.Receive> 活动发送消息的代理。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-116">Creates the proxy that sends a message to the <xref:System.ServiceModel.Activities.Receive> activity in the workflow.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="fa1e9-117">使用此示例</span><span class="sxs-lookup"><span data-stu-id="fa1e9-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="fa1e9-118">设置持久性数据库。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-118">Set up the persistence database.</span></span>  
  
    1.  <span data-ttu-id="fa1e9-119">打开一个 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-119">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
    2.  <span data-ttu-id="fa1e9-120">导航到[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]目录 (C:\Windows\Microsoft.NET\Framework\v4。X\\)。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-120">Navigate to the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] directory (C:\Windows\Microsoft.NET\Framework\v4.X\\).</span></span>  
  
    3.  <span data-ttu-id="fa1e9-121">编辑 WorkflowManagementService.exe.config 文件，将以下连接字符串添加到 <`database`> 元素内。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-121">Edit the WorkflowManagementService.exe.config file and add the following connection string inside the <`database`> element.</span></span>  
  
        ```xml  
        <database connectionString="Data Source=localhost\SQLEXPRESS;Initial Catalog=DefaultSampleStore;Integrated Security=True;Asynchronous Processing=True" />  
        ```  
  
    4.  <span data-ttu-id="fa1e9-122">导航到 DurableDelay\CS 目录。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-122">Navigate to the DurableDelay\CS directory.</span></span>  
  
    5.  <span data-ttu-id="fa1e9-123">运行 Setup.cmd。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-123">Run Setup.cmd.</span></span>  
  
2.  <span data-ttu-id="fa1e9-124">运行[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]使用提升的权限，请右键单击[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]图标并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-124">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] using elevated permissions by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
3.  <span data-ttu-id="fa1e9-125">打开 Delay.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-125">Open the Delay.sln solution file.</span></span>  
  
4.  <span data-ttu-id="fa1e9-126">按 Ctrl+Shift+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-126">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
5.  <span data-ttu-id="fa1e9-127">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-127">Press CTRL+F5 to run the solution.</span></span>  
  
#### <a name="to-uninstall-this-sample"></a><span data-ttu-id="fa1e9-128">卸载此示例</span><span class="sxs-lookup"><span data-stu-id="fa1e9-128">To uninstall this sample</span></span>  
  
1.  <span data-ttu-id="fa1e9-129">打开一个 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-129">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="fa1e9-130">导航到 DurableDelay\CS 目录。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-130">Navigate to the DurableDelay\CS directory.</span></span>  
  
3.  <span data-ttu-id="fa1e9-131">运行 Cleanup.cmd。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-131">Run Cleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fa1e9-132">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="fa1e9-133">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="fa1e9-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="fa1e9-134">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="fa1e9-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fa1e9-135">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="fa1e9-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelay`