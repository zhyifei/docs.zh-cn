---
title: "发送和处理错误"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98e8e04d-2ac9-4a33-ae08-462f757a7a14
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc91b431123ff8776910550151a7783b2690d383
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="sending-and-handling-faults"></a><span data-ttu-id="5c257-102">发送和处理错误</span><span class="sxs-lookup"><span data-stu-id="5c257-102">Sending and Handling Faults</span></span>
<span data-ttu-id="5c257-103">此示例演示如何使用 <xref:System.ServiceModel.Activities.SendReply> 和 <xref:System.ServiceModel.Activities.ReceiveReply> 消息传递活动来发送和接收预期的和意外的错误。</span><span class="sxs-lookup"><span data-stu-id="5c257-103">This sample demonstrates how to use the <xref:System.ServiceModel.Activities.SendReply> and <xref:System.ServiceModel.Activities.ReceiveReply> messaging activities to send and receive expected and unexpected faults.</span></span> <span data-ttu-id="5c257-104">在此方案中，第一个客户端请求导致已包含在其 <xref:System.ServiceModel.Activities.Send.KnownTypes%2A> 集合中的预期错误。</span><span class="sxs-lookup"><span data-stu-id="5c257-104">In this scenario, the first client request results in an expected fault that has been included in its <xref:System.ServiceModel.Activities.Send.KnownTypes%2A> collection.</span></span> <span data-ttu-id="5c257-105">在最终请求成功之前，接下来的几个客户端请求会导致接收意外错误。</span><span class="sxs-lookup"><span data-stu-id="5c257-105">The next few client requests result in receiving unexpected faults, before the final request succeeds.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="5c257-106">使用此示例</span><span class="sxs-lookup"><span data-stu-id="5c257-106">To use this sample</span></span>  
  
1.  <span data-ttu-id="5c257-107">打开[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]使用提升的权限，通过右键单击[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]图标并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="5c257-107">Open [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with elevated permissions, by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="5c257-108">打开 Faults.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="5c257-108">Open the Faults.sln solution file.</span></span>  
  
3.  <span data-ttu-id="5c257-109">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="5c257-109">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="5c257-110">运行服务项目。</span><span class="sxs-lookup"><span data-stu-id="5c257-110">Run the service project.</span></span>  
  
    1.  <span data-ttu-id="5c257-111">在**解决方案资源管理器**，右键单击`FaultService`项目，然后选择**设为启动项目**。</span><span class="sxs-lookup"><span data-stu-id="5c257-111">In **Solution Explorer**, right-click the `FaultService` project and select **Set as StartUp Project**.</span></span>  
  
    2.  <span data-ttu-id="5c257-112">按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="5c257-112">Press CTRL+F5.</span></span>  
  
5.  <span data-ttu-id="5c257-113">打开的另一个副本[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]使用提升的权限，通过右键单击[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]图标并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="5c257-113">Open another copy of [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with elevated permissions, by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
6.  <span data-ttu-id="5c257-114">打开 Faults.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="5c257-114">Open the Faults.sln solution file.</span></span>  
  
7.  <span data-ttu-id="5c257-115">运行客户端项目。</span><span class="sxs-lookup"><span data-stu-id="5c257-115">Run the client project.</span></span>  
  
    1.  <span data-ttu-id="5c257-116">在**解决方案资源管理器**，右键单击`FaultClient`项目，然后选择**设为启动项目**。</span><span class="sxs-lookup"><span data-stu-id="5c257-116">In **Solution Explorer**, right-click the `FaultClient` project and select **Set as StartUp Project**.</span></span>  
  
    2.  <span data-ttu-id="5c257-117">按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="5c257-117">Press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5c257-118">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="5c257-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5c257-119">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="5c257-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5c257-120">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="5c257-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5c257-121">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="5c257-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Faults`