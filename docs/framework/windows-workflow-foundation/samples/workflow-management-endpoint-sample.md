---
title: 工作流管理终结点示例
ms.date: 03/30/2017
ms.assetid: 3ac6e08f-c43d-4bb7-83c3-e3890a4dac03
ms.openlocfilehash: 3d99cbef20895381f5e40ee939e1d94a409f1391
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2018
ms.locfileid: "44700750"
---
# <a name="workflow-management-endpoint-sample"></a><span data-ttu-id="eced5-102">工作流管理终结点示例</span><span class="sxs-lookup"><span data-stu-id="eced5-102">Workflow Management Endpoint Sample</span></span>
<span data-ttu-id="eced5-103">此示例演示如何使用工作流控制终结点以本地方式和远程方式创建和运行工作流。</span><span class="sxs-lookup"><span data-stu-id="eced5-103">This sample shows how a workflow control endpoint can be used to create and run workflows both locally and remotely.</span></span> <span data-ttu-id="eced5-104">此示例演示如何承载一个控制终结点并编写调用此控制终结点的客户端，以创建和运行工作流的实例。</span><span class="sxs-lookup"><span data-stu-id="eced5-104">The sample demonstrates how to host a control endpoint and write clients that call the control endpoint to create and run the instance of a workflow.</span></span> <span data-ttu-id="eced5-105">工作流不是服务。</span><span class="sxs-lookup"><span data-stu-id="eced5-105">The workflow is not a service.</span></span>  
  
 <span data-ttu-id="eced5-106">在示例的服务端，使用 WorkflowServiceHost 承载工作流并且添加 WorkflowControlEndpoint，以便客户端可以执行控制操作（暂停、开始等）。</span><span class="sxs-lookup"><span data-stu-id="eced5-106">On the service side of the sample a workflow is hosted with WorkflowServiceHost and a WorkflowControlEndpoint is added so that clients can perform control operations (Suspend, Start, etc).</span></span> <span data-ttu-id="eced5-107">还添加用户定义的 CreationEndpoint，以允许创建工作流。</span><span class="sxs-lookup"><span data-stu-id="eced5-107">A user-defined CreationEndpoint is also added to allow the workflow to be created.</span></span> <span data-ttu-id="eced5-108">然后，该服务使用这些终结点在挂起状态中开始工作流，并且继续工作流。</span><span class="sxs-lookup"><span data-stu-id="eced5-108">The service then uses these endpoints to start the workflow in a suspended state and then resume the workflow.</span></span> <span data-ttu-id="eced5-109">客户端执行相同的操作，但这些操作来自客户端代码。</span><span class="sxs-lookup"><span data-stu-id="eced5-109">The client performs the same operations but from the client code.</span></span> <span data-ttu-id="eced5-110">有关详细信息，有关这些接口，请参阅[流控制终结点](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md)和[如何： 承载非服务工作流在 IIS 中](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)</span><span class="sxs-lookup"><span data-stu-id="eced5-110">For more information about these interfaces see, [Workflow Control Endpoint](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md) and [How to: Host a non-service workflow in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="eced5-111">运行示例</span><span class="sxs-lookup"><span data-stu-id="eced5-111">To run the sample</span></span>  
  
1.  <span data-ttu-id="eced5-112">使用管理员权限运行 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="eced5-112">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with administrator privileges.</span></span>  
  
2.  <span data-ttu-id="eced5-113">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 ManagementEndpoint.sln 解决方案。</span><span class="sxs-lookup"><span data-stu-id="eced5-113">Open the ManagementEndpoint.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
3.  <span data-ttu-id="eced5-114">若要生成解决方案，请按 CTRL + SHIFT + B 或选择**生成解决方案**从**生成**菜单。</span><span class="sxs-lookup"><span data-stu-id="eced5-114">To build the solution, press CTRL+SHIFT+B or select **Build Solution** from the **Build** menu.</span></span>  
  
4.  <span data-ttu-id="eced5-115">启动 ManagementEndpoint.exe 应用程序。</span><span class="sxs-lookup"><span data-stu-id="eced5-115">Start the ManagementEndpoint.exe application.</span></span>  
  
5.  <span data-ttu-id="eced5-116">启动 Client.exe 应用程序。</span><span class="sxs-lookup"><span data-stu-id="eced5-116">Start the Client.exe application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="eced5-117">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="eced5-117">The samples may already be installed on your computer.</span></span> <span data-ttu-id="eced5-118">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="eced5-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="eced5-119">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="eced5-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="eced5-120">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="eced5-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ManagementEndpoint`