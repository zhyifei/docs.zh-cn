---
title: "WorkflowHostingEndpoint 恢复书签"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a708064f-50b0-4751-b44e-d5410d08d451
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 140ff5282447c2a2307dee325645fc1f3f0497fe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="workflowhostingendpoint-resume-bookmark"></a><span data-ttu-id="3051e-102">WorkflowHostingEndpoint 恢复书签</span><span class="sxs-lookup"><span data-stu-id="3051e-102">WorkflowHostingEndpoint Resume Bookmark</span></span>
<span data-ttu-id="3051e-103">此示例演示如何将 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> 与 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 一起使用创建工作流实例。</span><span class="sxs-lookup"><span data-stu-id="3051e-103">This sample demonstrates how the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> can be used with <xref:System.ServiceModel.Activities.WorkflowServiceHost> to create workflow instances.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="3051e-104">演示</span><span class="sxs-lookup"><span data-stu-id="3051e-104">Demonstrates</span></span>  
 <span data-ttu-id="3051e-105"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost></span><span class="sxs-lookup"><span data-stu-id="3051e-105"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="3051e-106">讨论</span><span class="sxs-lookup"><span data-stu-id="3051e-106">Discussion</span></span>  
 <span data-ttu-id="3051e-107">此示例使用 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> 创建使用 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 承载的工作流实例。</span><span class="sxs-lookup"><span data-stu-id="3051e-107">This sample uses the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> to create a workflow instance hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="3051e-108"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> 是可用于以下方案的 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 的扩展点：</span><span class="sxs-lookup"><span data-stu-id="3051e-108"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> is an extensibility point for <xref:System.ServiceModel.Activities.WorkflowServiceHost> that can be used in the following scenarios:</span></span>  
  
-   <span data-ttu-id="3051e-109">创建新的工作流实例。</span><span class="sxs-lookup"><span data-stu-id="3051e-109">Creating new workflow instances.</span></span>  
  
-   <span data-ttu-id="3051e-110">恢复 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 中承载的工作流实例上的书签。</span><span class="sxs-lookup"><span data-stu-id="3051e-110">Resuming bookmarks on a workflow instance hosted in a <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="3051e-111">所包含的示例终结点将公开一个协定，该协定提供用于创建工作流并返回实例 ID 或使用特定 ID 创建实例的操作。</span><span class="sxs-lookup"><span data-stu-id="3051e-111">The sample endpoint that is included exposes a contract that provides operations to create a workflow and return an instance ID, or to create an instance with a specific ID.</span></span> <span data-ttu-id="3051e-112">示例控制台应用程序使用一个基本工作流定义创建 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 实例，并将 `CreationEndpoint` 添加到主机。</span><span class="sxs-lookup"><span data-stu-id="3051e-112">The sample console application creates a <xref:System.ServiceModel.Activities.WorkflowServiceHost> instance with a basic workflow definition, and adds a `CreationEndpoint` to the host.</span></span> <span data-ttu-id="3051e-113">然后它对所添加的终结点调用 `Create` 操作以创建新的工作流实例。</span><span class="sxs-lookup"><span data-stu-id="3051e-113">It then calls the `Create` operation on the endpoint to create a new workflow instance.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3051e-114">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="3051e-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="3051e-115">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="3051e-115">Build the solution.</span></span>  
  
2.  <span data-ttu-id="3051e-116">运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="3051e-116">Run the application.</span></span> <span data-ttu-id="3051e-117">当创建工作流实例时，`CreationEndpoint` 控制台会显示一条消息，其中包含该工作流实例 ID。</span><span class="sxs-lookup"><span data-stu-id="3051e-117">The `CreationEndpoint` console shows a message that includes the instance ID when the workflow instance is created.</span></span> <span data-ttu-id="3051e-118">消息"Hello World ！"</span><span class="sxs-lookup"><span data-stu-id="3051e-118">The message "Hello World!"</span></span> <span data-ttu-id="3051e-119">将打印成功恢复书签，工作流。</span><span class="sxs-lookup"><span data-stu-id="3051e-119">is printed by the workflow on successful resumption of the bookmark.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3051e-120">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="3051e-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3051e-121">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="3051e-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3051e-122">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="3051e-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3051e-123">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="3051e-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ResumeBookmarkEndpoint`
