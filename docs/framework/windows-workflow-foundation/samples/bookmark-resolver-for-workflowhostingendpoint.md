---
title: WorkflowHostingEndpoint 的书签解析程序
ms.date: 03/30/2017
ms.assetid: 97fd5816-935e-4625-ad04-e6f6befa07de
ms.openlocfilehash: 4676b3c624a7ba1539a7a12ed38c286f688dcf9f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59344287"
---
# <a name="bookmark-resolver-for-workflowhostingendpoint"></a><span data-ttu-id="65fde-102">WorkflowHostingEndpoint 的书签解析程序</span><span class="sxs-lookup"><span data-stu-id="65fde-102">Bookmark Resolver for WorkflowHostingEndpoint</span></span>
<span data-ttu-id="65fde-103">此示例演示如何将 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> 与 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 一起使用创建工作流实例。</span><span class="sxs-lookup"><span data-stu-id="65fde-103">This sample demonstrates how the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> can be used with <xref:System.ServiceModel.Activities.WorkflowServiceHost> to create workflow instances.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="65fde-104">演示</span><span class="sxs-lookup"><span data-stu-id="65fde-104">Demonstrates</span></span>  
 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint><span data-ttu-id="65fde-105">,</span><span class="sxs-lookup"><span data-stu-id="65fde-105">,</span></span> <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
## <a name="discussion"></a><span data-ttu-id="65fde-106">讨论</span><span class="sxs-lookup"><span data-stu-id="65fde-106">Discussion</span></span>  
 <span data-ttu-id="65fde-107">此示例使用 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> 创建使用 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 承载的工作流实例。</span><span class="sxs-lookup"><span data-stu-id="65fde-107">This sample uses the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> to create workflow instances hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> <span data-ttu-id="65fde-108">是的一个扩展点<xref:System.ServiceModel.Activities.WorkflowServiceHost>可在以下方案：</span><span class="sxs-lookup"><span data-stu-id="65fde-108">is an extensibility point for <xref:System.ServiceModel.Activities.WorkflowServiceHost> that can be used in the following scenarios:</span></span>  
  
-   <span data-ttu-id="65fde-109">创建新的工作流实例。</span><span class="sxs-lookup"><span data-stu-id="65fde-109">Creating new workflow instances.</span></span>  
  
-   <span data-ttu-id="65fde-110">恢复 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 中承载的工作流实例上的书签。</span><span class="sxs-lookup"><span data-stu-id="65fde-110">Resuming bookmarks on workflow instance hosted in a <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="65fde-111">所包含的示例终结点公开一个协定，该协定提供用于创建工作流的操作并返回实例 ID，或创建一个具有特定 ID 的实例。</span><span class="sxs-lookup"><span data-stu-id="65fde-111">The sample endpoint that is included exposes a contract that provides operations to create a workflow and returns the instance ID or creates an instance with a specific ID.</span></span> <span data-ttu-id="65fde-112">示例控制台应用程序创建一个具有工作流定义的 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 实例，并向主机添加一个 `CreationEndpoint`。</span><span class="sxs-lookup"><span data-stu-id="65fde-112">The sample console application creates a <xref:System.ServiceModel.Activities.WorkflowServiceHost> instance with a workflow definition and adds a `CreationEndpoint` to the host.</span></span> <span data-ttu-id="65fde-113">然后它对所添加的终结点调用 `Create` 操作以创建新的工作流实例。</span><span class="sxs-lookup"><span data-stu-id="65fde-113">It then calls the `Create` operation on the endpoint to create a new workflow instance.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="65fde-114">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="65fde-114">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="65fde-115">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="65fde-115">Build the solution.</span></span>  
  
2. <span data-ttu-id="65fde-116">运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="65fde-116">Run the application.</span></span> <span data-ttu-id="65fde-117">当创建工作流实例时，`CreationEndpoint` 控制台会显示一条消息，其中包含该工作流实例 ID。</span><span class="sxs-lookup"><span data-stu-id="65fde-117">The `CreationEndpoint` console shows a message that includes the instance ID when the workflow instance is created.</span></span> <span data-ttu-id="65fde-118">消息"Hello World ！"</span><span class="sxs-lookup"><span data-stu-id="65fde-118">The message "Hello World!"</span></span> <span data-ttu-id="65fde-119">打印工作流实例。</span><span class="sxs-lookup"><span data-stu-id="65fde-119">is printed by the workflow instance.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="65fde-120">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="65fde-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="65fde-121">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="65fde-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="65fde-122">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="65fde-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="65fde-123">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="65fde-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreationEndpoint`
