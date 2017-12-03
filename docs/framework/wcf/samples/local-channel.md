---
title: "本地通道"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa1917a4-f701-4e82-a439-14a16282c7cc
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5bf10b872d484f8b4b40de7c332f80280e2ac912
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="local-channel"></a><span data-ttu-id="a48a4-102">本地通道</span><span class="sxs-lookup"><span data-stu-id="a48a4-102">Local Channel</span></span>
<span data-ttu-id="a48a4-103">本地通道是用于在相同应用程序域内进行通信的 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 传输通道。</span><span class="sxs-lookup"><span data-stu-id="a48a4-103">Local Channel is a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] transport channel that is used for communication within the same application domain.</span></span> <span data-ttu-id="a48a4-104">对于客户端和服务在相同应用程序域内运行，并且必须避免典型 WCF 通道堆栈（消息的序列化和反序列化）开销的方案，这十分有用。</span><span class="sxs-lookup"><span data-stu-id="a48a4-104">This is useful for scenarios where the client and the service are running in the same application domain and the overhead of the typical WCF channel stack (serialization and deserialization of messages) must be avoided.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="a48a4-105">演示</span><span class="sxs-lookup"><span data-stu-id="a48a4-105">Demonstrates</span></span>  
 <span data-ttu-id="a48a4-106">本地通道</span><span class="sxs-lookup"><span data-stu-id="a48a4-106">Local Channel</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="a48a4-107">讨论</span><span class="sxs-lookup"><span data-stu-id="a48a4-107">Discussion</span></span>  
 <span data-ttu-id="a48a4-108">示例由两个项目文件组成：</span><span class="sxs-lookup"><span data-stu-id="a48a4-108">The sample consists of two project files:</span></span>  
  
-   <span data-ttu-id="a48a4-109">**LocalChannel**： 的编程表示形式中当前的应用程序域的本地通道。</span><span class="sxs-lookup"><span data-stu-id="a48a4-109">**LocalChannel**: The programmatic representation of the local channel within the current application domain.</span></span> <span data-ttu-id="a48a4-110">在此项目中，发送组件将消息放置在内存中队列中，接收组件将消息从队列中取出以进行接收。</span><span class="sxs-lookup"><span data-stu-id="a48a4-110">In this project, the sending component places the message in an in-memory queue and the receiving component de-queues the message to receive it.</span></span>  
  
-   <span data-ttu-id="a48a4-111">**ClientAndService**： 此项目承载控制台应用程序中的服务，然后运行客户端相同的应用程序域中调用中的服务。</span><span class="sxs-lookup"><span data-stu-id="a48a4-111">**ClientAndService**: This project hosts a service in a console application and then runs a client to call the service from within the same application domain.</span></span>  
  
 <span data-ttu-id="a48a4-112">本地通道设计跳过通道堆栈和序列化过程以提高速度。</span><span class="sxs-lookup"><span data-stu-id="a48a4-112">The local channel design skips both the channel stack and the serialization process to increase speed.</span></span> <span data-ttu-id="a48a4-113">本地传输通道使用队列实现，以将服务调用从客户端传输到服务并将值返回到客户端。</span><span class="sxs-lookup"><span data-stu-id="a48a4-113">The local transport channel is implemented using a queue to transport service calls from the client to the service and to return back the value to the client.</span></span> <span data-ttu-id="a48a4-114">示例复制对象，而不是对参数和返回值进行序列化。</span><span class="sxs-lookup"><span data-stu-id="a48a4-114">Rather than serializing parameters and return values, the sample copies the objects.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a48a4-115">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="a48a4-115">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="a48a4-116">生成并运行 LocalChannel 解决方案。</span><span class="sxs-lookup"><span data-stu-id="a48a4-116">Build and run the LocalChannel solution.</span></span>  
  
2.  <span data-ttu-id="a48a4-117">服务主机启动，客户端使用本地通道调用服务。</span><span class="sxs-lookup"><span data-stu-id="a48a4-117">The service host is started and the client calls the service using the local channel.</span></span> <span data-ttu-id="a48a4-118">出现控制台窗口，以显示服务调用的结果。</span><span class="sxs-lookup"><span data-stu-id="a48a4-118">A console window appears to display the results of the service call.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a48a4-119">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="a48a4-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a48a4-120">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="a48a4-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a48a4-121">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="a48a4-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a48a4-122">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="a48a4-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\LocalChannel`
