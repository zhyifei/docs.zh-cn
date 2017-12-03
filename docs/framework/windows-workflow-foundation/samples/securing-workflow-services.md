---
title: "保护工作流服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53f84ad5-1ed1-4114-8d0d-b12e8a021c6e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7cd7620186ed51110a32e251d5239c85bb90e0f0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="securing-workflow-services"></a><span data-ttu-id="d7fb0-102">保护工作流服务</span><span class="sxs-lookup"><span data-stu-id="d7fb0-102">Securing Workflow Services</span></span>
<span data-ttu-id="d7fb0-103">安全工作流服务示例演示以下过程：</span><span class="sxs-lookup"><span data-stu-id="d7fb0-103">The Secured Workflow Service sample shows the following procedures:</span></span>  
  
-   <span data-ttu-id="d7fb0-104">使用 <xref:System.ServiceModel.Activities.Receive> 和 <xref:System.ServiceModel.Activities.SendReply> 活动创建基本工作流服务。</span><span class="sxs-lookup"><span data-stu-id="d7fb0-104">Creating a basic workflow service using the <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> activities.</span></span>  
  
-   <span data-ttu-id="d7fb0-105">使用 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 配置定义供工作流服务使用的安全终结点。</span><span class="sxs-lookup"><span data-stu-id="d7fb0-105">Using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] configuration to define secure endpoints for use by the workflow service.</span></span>  
  
-   <span data-ttu-id="d7fb0-106">创建自定义策略内的声明并使用 <xref:System.ServiceModel.ServiceAuthorizationManager> 验证声明。</span><span class="sxs-lookup"><span data-stu-id="d7fb0-106">Creating claims inside a custom policy and using the <xref:System.ServiceModel.ServiceAuthorizationManager> to validate claims.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="d7fb0-107">演示</span><span class="sxs-lookup"><span data-stu-id="d7fb0-107">Demonstrates</span></span>  
 <span data-ttu-id="d7fb0-108">使用 WCF 安全保护客户端和工作流服务（基于声明的授权）之间的通信</span><span class="sxs-lookup"><span data-stu-id="d7fb0-108">Using WCF security to secure communication between client and Workflow service, Claims based authorization</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="d7fb0-109">讨论</span><span class="sxs-lookup"><span data-stu-id="d7fb0-109">Discussion</span></span>  
 <span data-ttu-id="d7fb0-110">此示例演示如何使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 安全基础结构来像保护正常的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务一样保护工作流服务。</span><span class="sxs-lookup"><span data-stu-id="d7fb0-110">This sample demonstrates the use of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security infrastructure to secure a workflow service just like you would with a normal [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="d7fb0-111">具体来说，它使用自定义声明进行授权。</span><span class="sxs-lookup"><span data-stu-id="d7fb0-111">Specifically, it uses a custom claim for authorization.</span></span> <span data-ttu-id="d7fb0-112">在此例中，它将 <xref:System.ServiceModel.WSHttpBinding> 和消息模式安全与 Windows 凭据一起使用。</span><span class="sxs-lookup"><span data-stu-id="d7fb0-112">In this case, it uses <xref:System.ServiceModel.WSHttpBinding> and message mode security with Windows credentials.</span></span>  
  
 <span data-ttu-id="d7fb0-113">自定义 <xref:System.IdentityModel.Policy.IAuthorizationPolicy> (`CustomNameCheckerPolicy`) 检查客户端的 Windows 用户名中是否存在特定的字符。</span><span class="sxs-lookup"><span data-stu-id="d7fb0-113">The custom <xref:System.IdentityModel.Policy.IAuthorizationPolicy> (`CustomNameCheckerPolicy`) checks the client's Windows username and for a specific character.</span></span> <span data-ttu-id="d7fb0-114">如果存在该字符，则它创建声明并将其添加到 <xref:System.IdentityModel.Policy.EvaluationContext>。</span><span class="sxs-lookup"><span data-stu-id="d7fb0-114">If that character is present, it creates and adds the claim to the <xref:System.IdentityModel.Policy.EvaluationContext>.</span></span> <span data-ttu-id="d7fb0-115">通过执行此操作，自定义策略将声明，客户端在用户名中包含该字符。</span><span class="sxs-lookup"><span data-stu-id="d7fb0-115">By doing this, the custom policy is making the statement that the client has this character in the username.</span></span> <span data-ttu-id="d7fb0-116">可以在整个调用的生存期查询此声明。</span><span class="sxs-lookup"><span data-stu-id="d7fb0-116">This claim can be queried throughout the lifetime of the call.</span></span> <span data-ttu-id="d7fb0-117">可以在 `Constants.cs` 中查找该字符。</span><span class="sxs-lookup"><span data-stu-id="d7fb0-117">You can find that character in `Constants.cs`.</span></span>  
  
 <span data-ttu-id="d7fb0-118">授权策略在 `SecureWorkFlowAuthZManager` 内查找此声明。</span><span class="sxs-lookup"><span data-stu-id="d7fb0-118">The authorization policy looks for the claim inside the `SecureWorkFlowAuthZManager`.</span></span> <span data-ttu-id="d7fb0-119">如果它找到此声明，则返回 `true` 并允许工作流继续。</span><span class="sxs-lookup"><span data-stu-id="d7fb0-119">If it finds it, it returns `true` and allow the workflow to proceed.</span></span> <span data-ttu-id="d7fb0-120">否则，它返回 `false`，这将导致将“访问被拒绝”消息返回给客户端。</span><span class="sxs-lookup"><span data-stu-id="d7fb0-120">Otherwise, it returns `false`, which causes an 'Access Denied' message to be returned to the client.</span></span> <span data-ttu-id="d7fb0-121">其他声明存在于上下文中并且也可以在 `SecureWorkFlowAuthZManager` 内部进行检查。</span><span class="sxs-lookup"><span data-stu-id="d7fb0-121">Other claims are present in the context and can be examined as well inside the `SecureWorkFlowAuthZManager`.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="d7fb0-122">运行此示例</span><span class="sxs-lookup"><span data-stu-id="d7fb0-122">To run this sample</span></span>  
  
1.  <span data-ttu-id="d7fb0-123">使用管理员权限运行 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d7fb0-123">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with administrator privileges.</span></span>  
  
2.  <span data-ttu-id="d7fb0-124">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中加载 SecuringWorkflowServices.sln。</span><span class="sxs-lookup"><span data-stu-id="d7fb0-124">Load SecuringWorkflowServices.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
3.  <span data-ttu-id="d7fb0-125">按 CTRL+SHIFT+B 编译解决方案。</span><span class="sxs-lookup"><span data-stu-id="d7fb0-125">Press CTRL+SHIFT+B to compile the solution.</span></span>  
  
4.  <span data-ttu-id="d7fb0-126">将 Service 项目设置为解决方案的启动项目。</span><span class="sxs-lookup"><span data-stu-id="d7fb0-126">Set the Service project as the start-up project for the solution.</span></span>  
  
5.  <span data-ttu-id="d7fb0-127">按 Ctrl+F5 启动服务而不进行调试。</span><span class="sxs-lookup"><span data-stu-id="d7fb0-127">Press CTRL+F5 to start the service without debugging.</span></span>  
  
6.  <span data-ttu-id="d7fb0-128">将 Client 项目设置为解决方案的启动项目。</span><span class="sxs-lookup"><span data-stu-id="d7fb0-128">Set the Client project as the start-up project for the solution.</span></span>  
  
7.  <span data-ttu-id="d7fb0-129">按 Ctrl+F5 启动客户端而不进行调试。</span><span class="sxs-lookup"><span data-stu-id="d7fb0-129">Press CTRL+F5 to start the client without debugging.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d7fb0-130">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="d7fb0-130">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d7fb0-131">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="d7fb0-131">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d7fb0-132">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="d7fb0-132">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d7fb0-133">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="d7fb0-133">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\SecuringWorkflowServices`
