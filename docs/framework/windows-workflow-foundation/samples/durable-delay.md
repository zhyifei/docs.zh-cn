---
title: "持久延迟"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 220ec240-b958-430c-81ff-b734a6aa97ae
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b0e679b91bd342ed5105fba7b916a8ed0070d0da
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="durable-delay"></a><span data-ttu-id="faebb-102">持久延迟</span><span class="sxs-lookup"><span data-stu-id="faebb-102">Durable Delay</span></span>
<span data-ttu-id="faebb-103">此示例演示如何使用持久延迟，在持久延迟过程中，将把工作流保留到持久性设备。</span><span class="sxs-lookup"><span data-stu-id="faebb-103">This sample demonstrates how to use a durable delay, which is a delay that persists the workflow to a durable device during the delay.</span></span> <span data-ttu-id="faebb-104">示例工作流包含发送到控制台并由延迟分隔的两个消息。</span><span class="sxs-lookup"><span data-stu-id="faebb-104">The sample workflow contains two messages to the console that are separated by a delay.</span></span> <span data-ttu-id="faebb-105">触发延迟时，工作流会卸载，并在重新加载到内存中之前，在工作流实例存储中等待 5 秒。</span><span class="sxs-lookup"><span data-stu-id="faebb-105">When the delay is triggered, the workflow is unloaded and waits 5 seconds in the workflow instance store before being reloaded in memory.</span></span>  
  
## <a name="workflow-details"></a><span data-ttu-id="faebb-106">工作流详细信息</span><span class="sxs-lookup"><span data-stu-id="faebb-106">Workflow Details</span></span>  
 <span data-ttu-id="faebb-107">工作流服务主机承载工作流，并通过加载和卸载工作流实例来对其进行管理。</span><span class="sxs-lookup"><span data-stu-id="faebb-107">The workflow service host hosts the workflow and manages the workflow instances by loading and unloading them.</span></span> <span data-ttu-id="faebb-108">为了启动工作流定义的实例，此示例设置了一个代理，用于向工作流中的 <xref:System.ServiceModel.Activities.Receive> 活动发送消息。</span><span class="sxs-lookup"><span data-stu-id="faebb-108">To start an instance of the workflow definition, the sample sets a proxy that sends a message to the <xref:System.ServiceModel.Activities.Receive> activity in the workflow.</span></span> <span data-ttu-id="faebb-109"><xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> 属性设置为 `true`，从而可以在接收到消息时创建工作流的新实例。</span><span class="sxs-lookup"><span data-stu-id="faebb-109">The <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> property is set to `true`, enabling it to create a new instance of the workflow once it receives a message.</span></span>  
  
 <span data-ttu-id="faebb-110">下面的列表详细介绍初始化过程中工作流服务主机进行的设置。</span><span class="sxs-lookup"><span data-stu-id="faebb-110">The following list details the set-up by the workflow service host during initialization.</span></span>  
  
1.  <span data-ttu-id="faebb-111">创建一个地址为 (http://localhost:8080/Client) 的服务主机。</span><span class="sxs-lookup"><span data-stu-id="faebb-111">Creates a service host with an address (http://localhost:8080/Client).</span></span>  
  
2.  <span data-ttu-id="faebb-112">在该服务主机中创建一个终结点，以便与工作流内的 <xref:System.ServiceModel.Activities.Receive> 活动进行通信。</span><span class="sxs-lookup"><span data-stu-id="faebb-112">Creates an endpoint in the service host to enable communication with the <xref:System.ServiceModel.Activities.Receive> activity inside the workflow.</span></span>  
  
3.  <span data-ttu-id="faebb-113">设置 SQL 实例存储区。</span><span class="sxs-lookup"><span data-stu-id="faebb-113">Sets up a SQL instance store.</span></span>  
  
4.  <span data-ttu-id="faebb-114">添加一个卸载实例行为，指定工作流服务主机在什么条件下应将工作流实例卸载到 SQL 持久性存储区。</span><span class="sxs-lookup"><span data-stu-id="faebb-114">Adds an unload instance behavior that specifies the conditions under which the workflow service host should unload a workflow instance to the SQL persistence store.</span></span> <span data-ttu-id="faebb-115">对于此示例，它在工作流进入空闲状态后（触发了延迟时）立即卸载实例。</span><span class="sxs-lookup"><span data-stu-id="faebb-115">For this sample, it unloads the instance immediately after the workflow goes idle (when the delay is triggered).</span></span>  
  
5.  <span data-ttu-id="faebb-116">创建向工作流中的 <xref:System.ServiceModel.Activities.Receive> 活动发送消息的代理。</span><span class="sxs-lookup"><span data-stu-id="faebb-116">Creates the proxy that sends a message to the <xref:System.ServiceModel.Activities.Receive> activity in the workflow.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="faebb-117">使用此示例</span><span class="sxs-lookup"><span data-stu-id="faebb-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="faebb-118">设置持久性数据库。</span><span class="sxs-lookup"><span data-stu-id="faebb-118">Set up the persistence database.</span></span>  
  
    1.  <span data-ttu-id="faebb-119">打开一个 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="faebb-119">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
    2.  <span data-ttu-id="faebb-120">导航到[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]目录 (C:\Windows\Microsoft.NET\Framework\v4。X\\)。</span><span class="sxs-lookup"><span data-stu-id="faebb-120">Navigate to the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] directory (C:\Windows\Microsoft.NET\Framework\v4.X\\).</span></span>  
  
    3.  <span data-ttu-id="faebb-121">编辑 WorkflowManagementService.exe.config 文件，将以下连接字符串添加到 <`database`> 元素内。</span><span class="sxs-lookup"><span data-stu-id="faebb-121">Edit the WorkflowManagementService.exe.config file and add the following connection string inside the <`database`> element.</span></span>  
  
        ```xml  
        <database connectionString="Data Source=localhost\SQLEXPRESS;Initial Catalog=DefaultSampleStore;Integrated Security=True;Asynchronous Processing=True" />  
        ```  
  
    4.  <span data-ttu-id="faebb-122">导航到 DurableDelay\CS 目录。</span><span class="sxs-lookup"><span data-stu-id="faebb-122">Navigate to the DurableDelay\CS directory.</span></span>  
  
    5.  <span data-ttu-id="faebb-123">运行 Setup.cmd。</span><span class="sxs-lookup"><span data-stu-id="faebb-123">Run Setup.cmd.</span></span>  
  
2.  <span data-ttu-id="faebb-124">运行[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]使用提升的权限，请右键单击[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]图标并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="faebb-124">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] using elevated permissions by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
3.  <span data-ttu-id="faebb-125">打开 Delay.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="faebb-125">Open the Delay.sln solution file.</span></span>  
  
4.  <span data-ttu-id="faebb-126">按 Ctrl+Shift+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="faebb-126">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
5.  <span data-ttu-id="faebb-127">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="faebb-127">Press CTRL+F5 to run the solution.</span></span>  
  
#### <a name="to-uninstall-this-sample"></a><span data-ttu-id="faebb-128">卸载此示例</span><span class="sxs-lookup"><span data-stu-id="faebb-128">To uninstall this sample</span></span>  
  
1.  <span data-ttu-id="faebb-129">打开一个 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="faebb-129">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="faebb-130">导航到 DurableDelay\CS 目录。</span><span class="sxs-lookup"><span data-stu-id="faebb-130">Navigate to the DurableDelay\CS directory.</span></span>  
  
3.  <span data-ttu-id="faebb-131">运行 Cleanup.cmd。</span><span class="sxs-lookup"><span data-stu-id="faebb-131">Run Cleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="faebb-132">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="faebb-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="faebb-133">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="faebb-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="faebb-134">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="faebb-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="faebb-135">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="faebb-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelay`