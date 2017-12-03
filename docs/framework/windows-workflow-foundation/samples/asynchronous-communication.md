---
title: "异步通信"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5ea2d705a38ddae1689d212bbd50196920fe73fe
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="asynchronous-communication"></a><span data-ttu-id="b5305-102">异步通信</span><span class="sxs-lookup"><span data-stu-id="b5305-102">Asynchronous Communication</span></span>
<span data-ttu-id="b5305-103">此示例演示默认情况下如何异步执行两个不同的 [!INCLUDE[wf](../../../../includes/wf-md.md)] 服务间的通信。</span><span class="sxs-lookup"><span data-stu-id="b5305-103">This sample demonstrates how the communication between two different [!INCLUDE[wf](../../../../includes/wf-md.md)] services is done asynchronously by default.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="b5305-104">演示</span><span class="sxs-lookup"><span data-stu-id="b5305-104">Demonstrates</span></span>  
 <span data-ttu-id="b5305-105">[!INCLUDE[wf1](../../../../includes/wf1-md.md)] 服务间的异步通信。</span><span class="sxs-lookup"><span data-stu-id="b5305-105">Asynchronous communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] services.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="b5305-106">讨论</span><span class="sxs-lookup"><span data-stu-id="b5305-106">Discussion</span></span>  
 <span data-ttu-id="b5305-107">此示例演示如何使用 .NET Framework 提供的消息传递活动来异步执行 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 应用程序间的通信。</span><span class="sxs-lookup"><span data-stu-id="b5305-107">This sample shows how the communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] applications is done asynchronously by using the messaging activities provided by .NET Framework.</span></span>  
  
 <span data-ttu-id="b5305-108">此示例包含以下三个项目。</span><span class="sxs-lookup"><span data-stu-id="b5305-108">This sample consists of the following three projects.</span></span>  
  
 <span data-ttu-id="b5305-109">CreditCheckService</span><span class="sxs-lookup"><span data-stu-id="b5305-109">CreditCheckService</span></span>  
 <span data-ttu-id="b5305-110">此服务接收特定人员的信用评分或要购买的商品的价值，然后决定是否为该人员提供贷款。</span><span class="sxs-lookup"><span data-stu-id="b5305-110">This service receives the credit score of a particular person or the value of the item to acquire, and then decides whether the credit is given to the person.</span></span>  
  
 <span data-ttu-id="b5305-111">RentalApprovalService</span><span class="sxs-lookup"><span data-stu-id="b5305-111">RentalApprovalService</span></span>  
 <span data-ttu-id="b5305-112">此服务接收来自需要贷款的人员的申请。</span><span class="sxs-lookup"><span data-stu-id="b5305-112">This service receives an application from a person who is in need of some credit.</span></span> <span data-ttu-id="b5305-113">此服务与 `CreditCheckService` 进行异步通信以决定贷款申请是否有效。</span><span class="sxs-lookup"><span data-stu-id="b5305-113">This service communicates asynchronously with the `CreditCheckService` to decide whether the credit application is valid.</span></span>  
  
 <span data-ttu-id="b5305-114">客户端</span><span class="sxs-lookup"><span data-stu-id="b5305-114">Client</span></span>  
 <span data-ttu-id="b5305-115">此客户端与 `RentalApprovalService` 进行同步通信以了解是否已批准贷款。</span><span class="sxs-lookup"><span data-stu-id="b5305-115">The client communicates synchronously with the `RentalApprovalService` to know whether the credit is approved.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b5305-116">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="b5305-116">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="b5305-117">右键单击**AsynchronousCommunication**解决方案并选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="b5305-117">Right-click the **AsynchronousCommunication** solution and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="b5305-118">在**通用属性**，选择**启动项目**，然后选择**多启动项目**。</span><span class="sxs-lookup"><span data-stu-id="b5305-118">In **Common Properties**, select **Startup Project**, and select **Multiple Startup Projects**.</span></span>  
  
3.  <span data-ttu-id="b5305-119">移动**RentalApprovalService**到列表中的第一个位置后, 接**CreditCheckService**后, 跟**客户端**。</span><span class="sxs-lookup"><span data-stu-id="b5305-119">Move **RentalApprovalService** to the first position in the list, followed by **CreditCheckService**, followed by **Client**.</span></span> <span data-ttu-id="b5305-120">设置**启动**上所有三个项目的操作。</span><span class="sxs-lookup"><span data-stu-id="b5305-120">Set the **Start** action on all three projects.</span></span>  
  
4.  <span data-ttu-id="b5305-121">单击**确定**，并按 F5 运行示例。</span><span class="sxs-lookup"><span data-stu-id="b5305-121">Click **OK**, and press F5 to run the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b5305-122">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="b5305-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b5305-123">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="b5305-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b5305-124">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="b5305-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b5305-125">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="b5305-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
