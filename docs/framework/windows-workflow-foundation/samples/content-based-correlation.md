---
title: "基于内容的相关"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8638b5d6-1d59-456d-8acd-179a5b39b260
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b5fea83ff6ac73fc26c419d9f7d5e8c5fe571135
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="content-based-correlation"></a><span data-ttu-id="3a351-102">基于内容的相关</span><span class="sxs-lookup"><span data-stu-id="3a351-102">Content-Based Correlation</span></span>
<span data-ttu-id="3a351-103">此示例演示消息传递活动（<xref:System.ServiceModel.Activities.Send>、<xref:System.ServiceModel.Activities.Receive>、<xref:System.ServiceModel.Activities.SendReply> 和 <xref:System.ServiceModel.Activities.ReceiveReply>）如何用于多个基于内容的相关性和一个基于内容的相关性。</span><span class="sxs-lookup"><span data-stu-id="3a351-103">This sample demonstrates how the messaging activities (<xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply>) can be used with multiple content-based correlations.and content-based correlation.</span></span> <span data-ttu-id="3a351-104">在此方案中，首先基于订单 ID 初始化一个相关性，然后基于客户 ID 创建另一个相关性。</span><span class="sxs-lookup"><span data-stu-id="3a351-104">In this scenario, a correlation is first initialized based on a purchase order ID, and then another correlation is created later based on the customer ID.</span></span> <span data-ttu-id="3a351-105">这将演示 <xref:System.ServiceModel.Activities.Receive> 活动如何基于相同的传入消息，遵循现有相关性并初始化新的相关性。</span><span class="sxs-lookup"><span data-stu-id="3a351-105">This shows how a <xref:System.ServiceModel.Activities.Receive> activity can both follow an existing correlation and initialize a new correlation based on the same incoming message.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="3a351-106">演示</span><span class="sxs-lookup"><span data-stu-id="3a351-106">Demonstrates</span></span>  
 <span data-ttu-id="3a351-107">消息传递活动和基于内容的相关性</span><span class="sxs-lookup"><span data-stu-id="3a351-107">Messaging activities and content-based correlation</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="3a351-108">讨论</span><span class="sxs-lookup"><span data-stu-id="3a351-108">Discussion</span></span>  
 <span data-ttu-id="3a351-109">本示例演示如何使用多个基于内容的相关性。</span><span class="sxs-lookup"><span data-stu-id="3a351-109">This sample shows how to use multiple content-based correlations.</span></span>  <span data-ttu-id="3a351-110">在此方案中，首先基于订单 ID 初始化一个相关性，然后基于客户 ID 创建另一个相关性。</span><span class="sxs-lookup"><span data-stu-id="3a351-110">In this scenario, a correlation is first initialized based on a purchase order ID, and then another correlation is created later based on the customer ID.</span></span>  <span data-ttu-id="3a351-111">使用 <xref:System.ServiceModel.Activities.Receive> 活动级联这些相关性，该活动基于相同的传入消息遵循现有相关性 (PurchaseOrderId) 并初始化新的相关性 (CustomerId)。</span><span class="sxs-lookup"><span data-stu-id="3a351-111">The correlations are cascaded using a <xref:System.ServiceModel.Activities.Receive> activity that both follows an existing correlation (PurchaseOrderId) and initializes a new correlation (CustomerId) based on the same incoming message.</span></span>  <span data-ttu-id="3a351-112">为实现此目的，<xref:System.ServiceModel.Activities.Receive> 活动使用 <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>、<xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A> 和 <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="3a351-112">To accomplish this, the <xref:System.ServiceModel.Activities.Receive> activity uses the <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>, <xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A> and <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> properties.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="3a351-113">使用此示例</span><span class="sxs-lookup"><span data-stu-id="3a351-113">To use this sample</span></span>  
  
1.  <span data-ttu-id="3a351-114">打开[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]使用提升的权限，通过右键单击[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]图标并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="3a351-114">Open [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with elevated permissions, by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="3a351-115">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 CascadingCorrelation.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="3a351-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the CascadingCorrelation.sln solution file.</span></span>  
  
3.  <span data-ttu-id="3a351-116">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="3a351-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="3a351-117">若要运行服务器，请按 F5。</span><span class="sxs-lookup"><span data-stu-id="3a351-117">To run the server, press F5.</span></span>  
  
5.  <span data-ttu-id="3a351-118">在服务准备就绪并开始侦听消息之后，在“解决方案资源管理器”中右击“Client”项目，并运行它。</span><span class="sxs-lookup"><span data-stu-id="3a351-118">Once the service is ready and listening for messages, in Solution Explorer, right-click the Client project and run it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3a351-119">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="3a351-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3a351-120">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="3a351-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3a351-121">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="3a351-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3a351-122">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="3a351-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\ContentBasedCorrelation`