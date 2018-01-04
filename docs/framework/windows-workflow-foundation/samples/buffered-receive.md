---
title: "缓冲接收"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d46d9b9-96c9-4531-9695-ab526b4d704a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7a486d3fbfb520ffe3b32c392566e5147c5dfcc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="buffered-receive"></a><span data-ttu-id="6c7c5-102">缓冲接收</span><span class="sxs-lookup"><span data-stu-id="6c7c5-102">Buffered Receive</span></span>
<span data-ttu-id="6c7c5-103">此示例演示如何在 [!INCLUDE[wf](../../../../includes/wf-md.md)] 中设置和配置缓冲接收功能。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-103">This sample demonstrates how to set up and configure the buffered receive feature in [!INCLUDE[wf](../../../../includes/wf-md.md)].</span></span> <span data-ttu-id="6c7c5-104">利用缓冲接收功能，工作流作者可创建工作流，而无需担心接收消息的顺序。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-104">Buffered receive allows the workflow author to create a workflow without having to worry about the order in which messages are received.</span></span> <span data-ttu-id="6c7c5-105">当工作流准备接收消息时，缓冲接收功能将本地缓冲并传递这些消息。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-105">The buffered receive feature buffers messages locally and delivers them when the workflow is ready to receive them.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="6c7c5-106">演示</span><span class="sxs-lookup"><span data-stu-id="6c7c5-106">Demonstrates</span></span>  
 <span data-ttu-id="6c7c5-107">将缓冲接收与消息传递活动一起使用的无序消息处理。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-107">Out-of-order message processing using buffered receive with messaging activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6c7c5-108">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6c7c5-109">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="6c7c5-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6c7c5-110">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6c7c5-111">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="6c7c5-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`  
  
## <a name="discussion"></a><span data-ttu-id="6c7c5-112">讨论</span><span class="sxs-lookup"><span data-stu-id="6c7c5-112">Discussion</span></span>  
 <span data-ttu-id="6c7c5-113">此示例将使用 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 实现 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 服务并具有一个 <xref:System.ServiceModel.Activities.Receive> 活动序列。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-113">In this sample, a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service is implemented using [!INCLUDE[wf1](../../../../includes/wf1-md.md)] and has a sequence of <xref:System.ServiceModel.Activities.Receive> activities.</span></span> <span data-ttu-id="6c7c5-114">此工作流建立了一个简单的贷款审批过程模型，在此模型中，工作流应会收到与贷款审批相关的三个通知。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-114">This workflow models a simple loan approval process where the workflow expects three notifications for a loan to be approved.</span></span> <span data-ttu-id="6c7c5-115">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 客户端应用程序按照与服务期望的顺序相反的顺序发送三个关联通知。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-115">A [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client application sends three correlated notifications in the reverse order of what the service expects.</span></span> <span data-ttu-id="6c7c5-116">由于已在服务上启用缓冲接收功能，因此在工作流准备好接收消息时，将在服务上对每条无序消息进行缓冲和处理。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-116">Because the buffered receive feature is turned on at the service, each out-of-order message is buffered at the service and processed as the workflow becomes ready to receive it.</span></span>  
  
 <span data-ttu-id="6c7c5-117">缓冲接收功能需要来自绑定的 <xref:System.ServiceModel.Activities.ReceiveContent> 支持，因此服务将使用 <xref:System.ServiceModel.NetMsmqBinding>。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-117">The buffered receive feature requires <xref:System.ServiceModel.Activities.ReceiveContent> support from the binding, therefore the service uses <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="6c7c5-118">由于绑定不需要任何特殊配置，因此将使用默认值。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-118">No special configuration is required for the binding, so the defaults are used.</span></span>  
  
```xml  
<endpoint address ="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                  binding="netMsmqBinding"  
                  contract="ILoanService"/>  
```  
  
 <span data-ttu-id="6c7c5-119">此服务还公开使用 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 的服务的元数据。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-119">The service also exposes metadata for the service using <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span></span>  
  
 <span data-ttu-id="6c7c5-120">同样，也将使用 <xref:System.ServiceModel.NetMsmqBinding> 配置客户端终结点。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-120">Similarly, the client endpoint is configured using <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="6c7c5-121">通过使用生成的客户端代码和配置**添加服务引用**功能[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-121">The client code and configuration is generated by using the **Add Service Reference** feature of [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span> <span data-ttu-id="6c7c5-122">下面的示例是在 App.config 文件中生成的客户端终结点。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-122">The following example is the generated client endpoint in the App.config file.</span></span>  
  
```xml  
<endpoint address="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                binding="netMsmqBinding" bindingConfiguration="NetMsmqBinding_ILoanService"  
                contract="ServiceReference1.ILoanService" name="NetMsmqBinding_ILoanService" />  
```  
  
 <span data-ttu-id="6c7c5-123">此示例要求启用以下 Windows 组件：</span><span class="sxs-lookup"><span data-stu-id="6c7c5-123">This sample requires that the following Windows components are enabled:</span></span>  
  
1.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)]  
  
2.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)]<span data-ttu-id="6c7c5-124"> 管理功能、元数据库和配置兼容性</span><span class="sxs-lookup"><span data-stu-id="6c7c5-124"> Management Compatibility, Metabase, and Configuration Compatibility</span></span>  
  
3.  <span data-ttu-id="6c7c5-125">万维网服务、应用程序开发功能和 ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6c7c5-125">World Wide Web Services, Application Development Features, and ASP.NET</span></span>  
  
4.  <span data-ttu-id="6c7c5-126">Microsoft Message Queues (MSMQ) Server</span><span class="sxs-lookup"><span data-stu-id="6c7c5-126">Microsoft Message Queues (MSMQ) Server</span></span>  
  
#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="6c7c5-127">设置和生成示例</span><span class="sxs-lookup"><span data-stu-id="6c7c5-127">To set up, and build the sample</span></span>  
  
1.  <span data-ttu-id="6c7c5-128">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示符下，通过键入 `aspnet_regiis –I` 并按 Enter 来注册 ASP.NET。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-128">At a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt, register ASP.NET by typing `aspnet_regiis –I` and press ENTER.</span></span>  
  
2.  <span data-ttu-id="6c7c5-129">以管理员身份运行 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-129">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] as an Administrator.</span></span>  
  
3.  <span data-ttu-id="6c7c5-130">打开 LoanService.sln。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-130">Open LoanService.sln.</span></span>  
  
4.  <span data-ttu-id="6c7c5-131">当系统询问你是否要创建的虚拟目录为 LoanService 项目，选择**是**。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-131">When asked if you would like to create the virtual directories for the LoanService project, select **Yes**.</span></span>  
  
#### <a name="to-set-up-the-service-queues"></a><span data-ttu-id="6c7c5-132">设置服务队列</span><span class="sxs-lookup"><span data-stu-id="6c7c5-132">To set up the service queues</span></span>  
  
1.  <span data-ttu-id="6c7c5-133">按 F5 运行 LoanClient 应用程序，这将创建队列并激活 Service1.xamlx 中定义的服务。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-133">Press F5 to run the LoanClient application that creates the queues and activates the service defined in Service1.xamlx.</span></span>  
  
2.  <span data-ttu-id="6c7c5-134">打开**计算机管理**通过在命令提示符下运行 Compmgmt.msc 的控制台。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-134">Open the **Computer Management** console by running Compmgmt.msc from a command prompt.</span></span>  
  
3.  <span data-ttu-id="6c7c5-135">在**计算机管理**控制台中，展开**服务**，**应用程序**，**消息队列**，**专用队列**.</span><span class="sxs-lookup"><span data-stu-id="6c7c5-135">In the **Computer Management** console, expand **Service**, **Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
4.  <span data-ttu-id="6c7c5-136">右击 loanservice/service1.xamlx 队列并选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-136">Right-click the loanservice/service1.xamlx queue and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="6c7c5-137">选择**安全**选项卡，并添加**每个人接收邮件**，**扫视消息**和**发送消息**权限。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-137">Select the **Security** tab, and add **Everyone Receives Message**, **Peek Message** and **Send Message** permissions.</span></span>  
  
6.  <span data-ttu-id="6c7c5-138">打开 [!INCLUDE[iis60](../../../../includes/iis60-md.md)] 管理器。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-138">Open the [!INCLUDE[iis60](../../../../includes/iis60-md.md)] Manager.</span></span>  
  
7.  <span data-ttu-id="6c7c5-139">浏览到**服务器**，**站点**， **Default Web site**，**私有**， **LoanService**和选择**高级的选项**</span><span class="sxs-lookup"><span data-stu-id="6c7c5-139">Browse to **Server**, **Sites**, **Default Web site**, **Private**, **LoanService** and select **Advanced Options**</span></span>  
  
8.  <span data-ttu-id="6c7c5-140">更改**启用的协议**要**http**， **net.msmq**。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-140">Change the **Enabled Protocols** to be **http**, **net.msmq**.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="6c7c5-141">运行示例</span><span class="sxs-lookup"><span data-stu-id="6c7c5-141">To run the sample</span></span>  
  
1.  <span data-ttu-id="6c7c5-142">浏览到 http://localhost/private/loanservice/service1.xamlx 以确保服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-142">Browse to http://localhost/private/loanservice/service1.xamlx to ensure that the service is running.</span></span>  
  
2.  <span data-ttu-id="6c7c5-143">按 F5 运行 LoanClient 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-143">Press F5 to run the LoanClient application.</span></span> <span data-ttu-id="6c7c5-144">在工作流完成后，应会将一个 out.txt 文件保存到包含消息交换结果的 C:\Inbox 中。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-144">Once the workflow is complete, an out.txt file should be saved to C:\Inbox that contains the result of the message exchange.</span></span>  
  
#### <a name="to-clean-up"></a><span data-ttu-id="6c7c5-145">清理</span><span class="sxs-lookup"><span data-stu-id="6c7c5-145">To clean up</span></span>  
  
1.  <span data-ttu-id="6c7c5-146">打开**计算机管理**通过在命令提示符下运行 Compmgmt.msc 的控制台。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-146">Open the **Computer Management** console by running Compmgmt.msc from a command prompt.</span></span>  
  
2.  <span data-ttu-id="6c7c5-147">展开**服务**和**应用程序**，**消息队列**，**专用队列**。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-147">Expand **Service** and **Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
3.  <span data-ttu-id="6c7c5-148">删除 loanservice/service1.xamlx 队列。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-148">Delete the loanservice/service1.xamlx queue.</span></span>  
  
4.  <span data-ttu-id="6c7c5-149">移除 C:\Inbox 目录。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-149">Remove the C:\Inbox directory.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6c7c5-150">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-150">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6c7c5-151">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="6c7c5-151">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6c7c5-152">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="6c7c5-152">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6c7c5-153">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="6c7c5-153">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`
