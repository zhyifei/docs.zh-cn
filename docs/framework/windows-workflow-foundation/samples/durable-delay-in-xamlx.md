---
title: XAMLX 中的持久延迟
ms.date: 03/30/2017
ms.assetid: efc38df4-2d34-453c-8e59-2c21d1307354
ms.openlocfilehash: 1eef9211c67d190ecb5f329c481fa2e3d1763353
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2018
ms.locfileid: "45594086"
---
# <a name="durable-delay-in-xamlx"></a><span data-ttu-id="9dcb5-102">XAMLX 中的持久延迟</span><span class="sxs-lookup"><span data-stu-id="9dcb5-102">Durable Delay in XAMLX</span></span>
<span data-ttu-id="9dcb5-103">此示例演示如何使用持久延迟，在持久延迟过程中，将把工作流保留到持久性设备。</span><span class="sxs-lookup"><span data-stu-id="9dcb5-103">This sample demonstrates how to use a durable delay, which is a delay that persists the workflow to a durable device during the delay.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9dcb5-104">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="9dcb5-104">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9dcb5-105">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="9dcb5-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9dcb5-106">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="9dcb5-106">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9dcb5-107">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="9dcb5-107">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlx`  
  
## <a name="discussion"></a><span data-ttu-id="9dcb5-108">讨论</span><span class="sxs-lookup"><span data-stu-id="9dcb5-108">Discussion</span></span>  
 <span data-ttu-id="9dcb5-109">示例工作流包含发往一个本地文件并由延迟分隔的两个消息。</span><span class="sxs-lookup"><span data-stu-id="9dcb5-109">The sample workflow contains two messages to a local file that are separated by a delay.</span></span> <span data-ttu-id="9dcb5-110">触发延迟时，工作流会卸载，并在重新加载到内存中之前，在工作流实例存储中等待 5 秒。</span><span class="sxs-lookup"><span data-stu-id="9dcb5-110">When the delay is triggered, the workflow is unloaded and waits 5 seconds in the workflow instance store before being reloaded in memory.</span></span>  
  
 <span data-ttu-id="9dcb5-111">.Xamlx 文件是 Visual Studio 中托管的工作流服务。</span><span class="sxs-lookup"><span data-stu-id="9dcb5-111">The .xamlx file is a workflow service that is hosted in Visual Studio.</span></span> <span data-ttu-id="9dcb5-112">Visual Studio 使用 Cassini 使用工作流服务主机来承载工作流。</span><span class="sxs-lookup"><span data-stu-id="9dcb5-112">Visual Studio uses Cassini that uses a workflow service host to host the workflow.</span></span>  
  
 <span data-ttu-id="9dcb5-113">除了承载工作流之外，工作流服务主机还通过加载和卸载工作流实例来对其进行管理。</span><span class="sxs-lookup"><span data-stu-id="9dcb5-113">In addition to hosting the workflow, the workflow service host manages the workflow instances by loading and unloading them.</span></span> <span data-ttu-id="9dcb5-114">若要开始 （在工作流服务主机） 上的 Windows Workflow Foundation (WF) 定义的实例，设置发送到消息的客户端<xref:System.ServiceModel.Activities.Receive>在工作流活动。</span><span class="sxs-lookup"><span data-stu-id="9dcb5-114">To start an instance of the Windows Workflow Foundation (WF) definition (on the workflow service host), set a client that sends a message to the <xref:System.ServiceModel.Activities.Receive> activity in the workflow.</span></span> <span data-ttu-id="9dcb5-115">此 <xref:System.ServiceModel.Activities.Receive> 将自己的 <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> 属性设置为 `true`，从而可以在接收到消息时创建工作流的新实例。</span><span class="sxs-lookup"><span data-stu-id="9dcb5-115">This <xref:System.ServiceModel.Activities.Receive> has its <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> property set to `true`, enabling it to create a new instance of the workflow once it receives a message.</span></span>  
  
 <span data-ttu-id="9dcb5-116">初始化过程中，会将一个卸载实例行为添加到配置文件，该行为应在该配置文件指定到的工作流服务主机下，将实例卸载到持久性存储区（数据库）。</span><span class="sxs-lookup"><span data-stu-id="9dcb5-116">During initialization, an unload instance behavior is added to the configuration file that specifies to the workflow service host under which it should unload an instance to the persistence store (database).</span></span> <span data-ttu-id="9dcb5-117">对于此示例，它在工作流进入空闲状态后（触发了延迟时）立即卸载实例。</span><span class="sxs-lookup"><span data-stu-id="9dcb5-117">For this sample, it unloads the instance immediately after the workflow goes idle (when the delay is triggered).</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="9dcb5-118">使用此示例</span><span class="sxs-lookup"><span data-stu-id="9dcb5-118">To use this sample</span></span>  
  
1.  <span data-ttu-id="9dcb5-119">打开一个 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="9dcb5-119">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="9dcb5-120">导航到 DurableDelayXamlx\CS 文件夹。</span><span class="sxs-lookup"><span data-stu-id="9dcb5-120">Navigate to the DurableDelayXamlx\CS folder.</span></span>  
  
3.  <span data-ttu-id="9dcb5-121">运行 Setup.cmd。</span><span class="sxs-lookup"><span data-stu-id="9dcb5-121">Run Setup.cmd.</span></span>  
  
4.  <span data-ttu-id="9dcb5-122">以管理员身份运行 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9dcb5-122">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] as an administrator.</span></span>  
  
5.  <span data-ttu-id="9dcb5-123">打开 DurableDelayXamlx.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="9dcb5-123">Open the DurableDelayXamlx.sln solution file.</span></span>  
  
6.  <span data-ttu-id="9dcb5-124">在中**解决方案资源管理器**，右键单击解决方案并选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="9dcb5-124">In **Solution Explorer**, right-click the solution and select **Properties**.</span></span>  
  
7.  <span data-ttu-id="9dcb5-125">选择**多个启动项目**并将这两个项目设置为**启动**。</span><span class="sxs-lookup"><span data-stu-id="9dcb5-125">Select **Multiple startup projects** and set both projects to **Start**.</span></span>  
  
8.  <span data-ttu-id="9dcb5-126">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="9dcb5-126">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
9. <span data-ttu-id="9dcb5-127">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="9dcb5-127">To run the solution, press CTRL+F5.</span></span>  
  
#### <a name="to-uninstall-this-sample"></a><span data-ttu-id="9dcb5-128">卸载此示例</span><span class="sxs-lookup"><span data-stu-id="9dcb5-128">To uninstall this sample</span></span>  
  
1.  <span data-ttu-id="9dcb5-129">打开一个 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="9dcb5-129">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="9dcb5-130">导航到 DurableDelayXamlx\CS 文件夹。</span><span class="sxs-lookup"><span data-stu-id="9dcb5-130">Navigate to the DurableDelayXamlx\CS folder.</span></span>  
  
3.  <span data-ttu-id="9dcb5-131">运行 Cleanup.cmd。</span><span class="sxs-lookup"><span data-stu-id="9dcb5-131">Run Cleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9dcb5-132">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="9dcb5-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9dcb5-133">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="9dcb5-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9dcb5-134">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="9dcb5-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9dcb5-135">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="9dcb5-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlX`
