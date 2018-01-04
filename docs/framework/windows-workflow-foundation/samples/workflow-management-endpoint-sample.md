---
title: "工作流管理终结点示例"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ac6e08f-c43d-4bb7-83c3-e3890a4dac03
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e516d41a9f9736877fb3974774ddaf4b3bddb198
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="workflow-management-endpoint-sample"></a><span data-ttu-id="5cb57-102">工作流管理终结点示例</span><span class="sxs-lookup"><span data-stu-id="5cb57-102">Workflow Management Endpoint Sample</span></span>
<span data-ttu-id="5cb57-103">此示例演示如何使用工作流控制终结点以本地方式和远程方式创建和运行工作流。</span><span class="sxs-lookup"><span data-stu-id="5cb57-103">This sample shows how a workflow control endpoint can be used to create and run workflows both locally and remotely.</span></span> <span data-ttu-id="5cb57-104">此示例演示如何承载一个控制终结点并编写调用此控制终结点的客户端，以创建和运行工作流的实例。</span><span class="sxs-lookup"><span data-stu-id="5cb57-104">The sample demonstrates how to host a control endpoint and write clients that call the control endpoint to create and run the instance of a workflow.</span></span> <span data-ttu-id="5cb57-105">工作流不是服务。</span><span class="sxs-lookup"><span data-stu-id="5cb57-105">The workflow is not a service.</span></span>  
  
 <span data-ttu-id="5cb57-106">在示例的服务端，使用 WorkflowServiceHost 承载工作流并且添加 WorkflowControlEndpoint，以便客户端可以执行控制操作（暂停、开始等）。</span><span class="sxs-lookup"><span data-stu-id="5cb57-106">On the service side of the sample a workflow is hosted with WorkflowServiceHost and a WorkflowControlEndpoint is added so that clients can perform control operations (Suspend, Start, etc).</span></span> <span data-ttu-id="5cb57-107">还添加用户定义的 CreationEndpoint，以允许创建工作流。</span><span class="sxs-lookup"><span data-stu-id="5cb57-107">A user-defined CreationEndpoint is also added to allow the workflow to be created.</span></span> <span data-ttu-id="5cb57-108">然后，该服务使用这些终结点在挂起状态中开始工作流，并且继续工作流。</span><span class="sxs-lookup"><span data-stu-id="5cb57-108">The service then uses these endpoints to start the workflow in a suspended state and then resume the workflow.</span></span> <span data-ttu-id="5cb57-109">客户端执行相同的操作，但这些操作来自客户端代码。</span><span class="sxs-lookup"><span data-stu-id="5cb57-109">The client performs the same operations but from the client code.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="5cb57-110">请参阅这些接口，[流控制终结点](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md)和[如何： 承载非服务工作流在 IIS 中](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)</span><span class="sxs-lookup"><span data-stu-id="5cb57-110"> these interfaces see, [Workflow Control Endpoint](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md) and [How to: Host a non-service workflow in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="5cb57-111">运行示例</span><span class="sxs-lookup"><span data-stu-id="5cb57-111">To run the sample</span></span>  
  
1.  <span data-ttu-id="5cb57-112">使用管理员权限运行 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5cb57-112">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with administrator privileges.</span></span>  
  
2.  <span data-ttu-id="5cb57-113">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 ManagementEndpoint.sln 解决方案。</span><span class="sxs-lookup"><span data-stu-id="5cb57-113">Open the ManagementEndpoint.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
3.  <span data-ttu-id="5cb57-114">若要生成解决方案，按 CTRL + SHIFT + B 或选择**生成解决方案**从**生成**菜单。</span><span class="sxs-lookup"><span data-stu-id="5cb57-114">To build the solution, press CTRL+SHIFT+B or select **Build Solution** from the **Build** menu.</span></span>  
  
4.  <span data-ttu-id="5cb57-115">启动 ManagementEndpoint.exe 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5cb57-115">Start the ManagementEndpoint.exe application.</span></span>  
  
5.  <span data-ttu-id="5cb57-116">启动 Client.exe 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5cb57-116">Start the Client.exe application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5cb57-117">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="5cb57-117">The samples may already be installed on your computer.</span></span> <span data-ttu-id="5cb57-118">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="5cb57-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5cb57-119">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="5cb57-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5cb57-120">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="5cb57-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ManagementEndpoint`