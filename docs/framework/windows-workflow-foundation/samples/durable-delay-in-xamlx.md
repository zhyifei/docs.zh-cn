---
title: XAMLX 中的持久延迟
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: efc38df4-2d34-453c-8e59-2c21d1307354
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8fa5a9e4287bcbcb490754b84a8b5060d321f779
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
# <a name="durable-delay-in-xamlx"></a><span data-ttu-id="1e634-102">XAMLX 中的持久延迟</span><span class="sxs-lookup"><span data-stu-id="1e634-102">Durable Delay in XAMLX</span></span>
<span data-ttu-id="1e634-103">此示例演示如何使用持久延迟，在持久延迟过程中，将把工作流保留到持久性设备。</span><span class="sxs-lookup"><span data-stu-id="1e634-103">This sample demonstrates how to use a durable delay, which is a delay that persists the workflow to a durable device during the delay.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1e634-104">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="1e634-104">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1e634-105">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="1e634-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1e634-106">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="1e634-106">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1e634-107">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="1e634-107">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlx`  
  
## <a name="discussion"></a><span data-ttu-id="1e634-108">讨论</span><span class="sxs-lookup"><span data-stu-id="1e634-108">Discussion</span></span>  
 <span data-ttu-id="1e634-109">示例工作流包含发往一个本地文件并由延迟分隔的两个消息。</span><span class="sxs-lookup"><span data-stu-id="1e634-109">The sample workflow contains two messages to a local file that are separated by a delay.</span></span> <span data-ttu-id="1e634-110">触发延迟时，工作流会卸载，并在重新加载到内存中之前，在工作流实例存储中等待 5 秒。</span><span class="sxs-lookup"><span data-stu-id="1e634-110">When the delay is triggered, the workflow is unloaded and waits 5 seconds in the workflow instance store before being reloaded in memory.</span></span>  
  
 <span data-ttu-id="1e634-111">.Xamlx 文件是在 Visual Studio 中承载工作流服务。</span><span class="sxs-lookup"><span data-stu-id="1e634-111">The .xamlx file is a workflow service that is hosted in Visual Studio.</span></span> <span data-ttu-id="1e634-112">Visual Studio 使用 Cassini 使用工作流服务主机来承载工作流。</span><span class="sxs-lookup"><span data-stu-id="1e634-112">Visual Studio uses Cassini that uses a workflow service host to host the workflow.</span></span>  
  
 <span data-ttu-id="1e634-113">除了承载工作流之外，工作流服务主机还通过加载和卸载工作流实例来对其进行管理。</span><span class="sxs-lookup"><span data-stu-id="1e634-113">In addition to hosting the workflow, the workflow service host manages the workflow instances by loading and unloading them.</span></span> <span data-ttu-id="1e634-114">若要启动 （在工作流服务主机） 的 Windows Workflow Foundation (WF) 定义的实例，设置发送到的消息的客户端<xref:System.ServiceModel.Activities.Receive>工作流中的活动。</span><span class="sxs-lookup"><span data-stu-id="1e634-114">To start an instance of the Windows Workflow Foundation (WF) definition (on the workflow service host), set a client that sends a message to the <xref:System.ServiceModel.Activities.Receive> activity in the workflow.</span></span> <span data-ttu-id="1e634-115">此 <xref:System.ServiceModel.Activities.Receive> 将自己的 <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> 属性设置为 `true`，从而可以在接收到消息时创建工作流的新实例。</span><span class="sxs-lookup"><span data-stu-id="1e634-115">This <xref:System.ServiceModel.Activities.Receive> has its <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> property set to `true`, enabling it to create a new instance of the workflow once it receives a message.</span></span>  
  
 <span data-ttu-id="1e634-116">初始化过程中，会将一个卸载实例行为添加到配置文件，该行为应在该配置文件指定到的工作流服务主机下，将实例卸载到持久性存储区（数据库）。</span><span class="sxs-lookup"><span data-stu-id="1e634-116">During initialization, an unload instance behavior is added to the configuration file that specifies to the workflow service host under which it should unload an instance to the persistence store (database).</span></span> <span data-ttu-id="1e634-117">对于此示例，它在工作流进入空闲状态后（触发了延迟时）立即卸载实例。</span><span class="sxs-lookup"><span data-stu-id="1e634-117">For this sample, it unloads the instance immediately after the workflow goes idle (when the delay is triggered).</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="1e634-118">使用此示例</span><span class="sxs-lookup"><span data-stu-id="1e634-118">To use this sample</span></span>  
  
1.  <span data-ttu-id="1e634-119">打开一个 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="1e634-119">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="1e634-120">导航到 DurableDelayXamlx\CS 文件夹。</span><span class="sxs-lookup"><span data-stu-id="1e634-120">Navigate to the DurableDelayXamlx\CS folder.</span></span>  
  
3.  <span data-ttu-id="1e634-121">运行 Setup.cmd。</span><span class="sxs-lookup"><span data-stu-id="1e634-121">Run Setup.cmd.</span></span>  
  
4.  <span data-ttu-id="1e634-122">以管理员身份运行 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1e634-122">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] as an administrator.</span></span>  
  
5.  <span data-ttu-id="1e634-123">打开 DurableDelayXamlx.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="1e634-123">Open the DurableDelayXamlx.sln solution file.</span></span>  
  
6.  <span data-ttu-id="1e634-124">在**解决方案资源管理器**，右键单击该解决方案并选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="1e634-124">In **Solution Explorer**, right-click the solution and select **Properties**.</span></span>  
  
7.  <span data-ttu-id="1e634-125">选择**多启动项目**并将这两个项目设置为**启动**。</span><span class="sxs-lookup"><span data-stu-id="1e634-125">Select **Multiple startup projects** and set both projects to **Start**.</span></span>  
  
8.  <span data-ttu-id="1e634-126">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="1e634-126">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
9. <span data-ttu-id="1e634-127">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="1e634-127">To run the solution, press CTRL+F5.</span></span>  
  
#### <a name="to-uninstall-this-sample"></a><span data-ttu-id="1e634-128">卸载此示例</span><span class="sxs-lookup"><span data-stu-id="1e634-128">To uninstall this sample</span></span>  
  
1.  <span data-ttu-id="1e634-129">打开一个 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="1e634-129">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="1e634-130">导航到 DurableDelayXamlx\CS 文件夹。</span><span class="sxs-lookup"><span data-stu-id="1e634-130">Navigate to the DurableDelayXamlx\CS folder.</span></span>  
  
3.  <span data-ttu-id="1e634-131">运行 Cleanup.cmd。</span><span class="sxs-lookup"><span data-stu-id="1e634-131">Run Cleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1e634-132">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="1e634-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1e634-133">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="1e634-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1e634-134">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="1e634-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1e634-135">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="1e634-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlX`
