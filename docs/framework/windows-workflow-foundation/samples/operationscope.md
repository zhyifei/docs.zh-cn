---
title: OperationScope
ms.date: 03/30/2017
ms.assetid: 56206a21-1e63-422d-b92a-e5d8b713e707
ms.openlocfilehash: 562fd9c8ff964cb997012d49600bce73d4441465
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2018
ms.locfileid: "44511206"
---
# <a name="operationscope"></a><span data-ttu-id="178f9-102">OperationScope</span><span class="sxs-lookup"><span data-stu-id="178f9-102">OperationScope</span></span>
<span data-ttu-id="178f9-103">此示例演示如何使用消息传送活动（<xref:System.ServiceModel.Activities.Receive> 和 <xref:System.ServiceModel.Activities.SendReply>），将现有的自定义活动作为工作流服务中的操作公开。</span><span class="sxs-lookup"><span data-stu-id="178f9-103">This sample demonstrates how the messaging activities, <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> can be used to expose an existing custom activity as an operation in a workflow service.</span></span> <span data-ttu-id="178f9-104">此示例包含一个名为 `OperationScope` 的新的自定义活动。</span><span class="sxs-lookup"><span data-stu-id="178f9-104">This sample includes a new custom activity called an `OperationScope`.</span></span> <span data-ttu-id="178f9-105">这样做的目的是，通过允许用户将其操作的主体作为自定义活动单独创作，然后使用 `OperationScope` 活动轻松地将这些活动作为服务操作公开，从而方便工作流服务的开发。</span><span class="sxs-lookup"><span data-stu-id="178f9-105">It is intended to ease the development of a workflow service by allowing users to author the body of their operations separately as custom activities and then easily exposing them as service operations using the `OperationScope` activity.</span></span> <span data-ttu-id="178f9-106">例如，对于一个采用两个 `Add` 参数并返回一个 `in` 参数的自定义 `out` 活动，可以通过将其拖放到 `Add` 中来将其作为工作流服务上的 `OperationScope` 操作公开。</span><span class="sxs-lookup"><span data-stu-id="178f9-106">For example, a custom `Add` activity that takes two `in` arguments and returns one `out` argument could be exposed as an `Add` operation on the workflow service by dropping it into an `OperationScope`.</span></span>  
  
 <span data-ttu-id="178f9-107">范围用于检查作为其主体提供的活动。</span><span class="sxs-lookup"><span data-stu-id="178f9-107">The scope works by inspecting the activity provided as its body.</span></span> <span data-ttu-id="178f9-108">任何未绑定的 `in` 参数都被认为是来自传入消息的输入。</span><span class="sxs-lookup"><span data-stu-id="178f9-108">Any unbound `in` arguments are assumed to be inputs from the incoming message.</span></span> <span data-ttu-id="178f9-109">所有 `out` 参数（无论它们是否已绑定）都被认为是后续回复消息中的输出。</span><span class="sxs-lookup"><span data-stu-id="178f9-109">All `out` arguments, regardless of whether they are bound, are assumed to be outputs in the subsequent reply message.</span></span> <span data-ttu-id="178f9-110">公开的操作名称取自 `OperationScope` 活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="178f9-110">The exposed operation’s name is taken from the display name of the `OperationScope` activity.</span></span> <span data-ttu-id="178f9-111">最终结果是，主体活动包装在 <xref:System.ServiceModel.Activities.Receive> 和 <xref:System.ServiceModel.Activities.SendReply> 中，并且消息中的形参绑定到活动的实参。</span><span class="sxs-lookup"><span data-stu-id="178f9-111">The end result is that the body activity is wrapped in a <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> with the parameters from the messages bound to the arguments of the activity.</span></span>  
  
 <span data-ttu-id="178f9-112">此示例使用 HTTP 终结点公开一个工作流服务。</span><span class="sxs-lookup"><span data-stu-id="178f9-112">This sample exposes a workflow service using HTTP endpoints.</span></span> <span data-ttu-id="178f9-113">若要运行，必须添加合适的 URL ACL。</span><span class="sxs-lookup"><span data-stu-id="178f9-113">To run, proper URL ACLs must be added.</span></span> <span data-ttu-id="178f9-114">有关详细信息，请参阅[配置 HTTP 和 HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353)。</span><span class="sxs-lookup"><span data-stu-id="178f9-114">For more information, see [Configuring HTTP and HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353).</span></span> <span data-ttu-id="178f9-115">执行以下命令在提升的提示符添加适当的 Acl (确保你的域和用户名替换为 %域 %\\%username%)。</span><span class="sxs-lookup"><span data-stu-id="178f9-115">Executing the following command at an elevated prompt adds the appropriate ACLs (ensure that your Domain and Username are substituted for %DOMAIN%\\%UserName%).</span></span>  
  
 <span data-ttu-id="178f9-116">**netsh http add urlacl =http://+:8000/用户 = %域 %\\%username%**</span><span class="sxs-lookup"><span data-stu-id="178f9-116">**netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\\%UserName%**</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="178f9-117">运行示例</span><span class="sxs-lookup"><span data-stu-id="178f9-117">To run the sample</span></span>  
  
1.  <span data-ttu-id="178f9-118">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 OperationScope.sln 解决方案。</span><span class="sxs-lookup"><span data-stu-id="178f9-118">Open the OperationScope.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="178f9-119">右键单击解决方案资源管理器中的解决方案并选择设置多个启动项目**设置启动项目**。</span><span class="sxs-lookup"><span data-stu-id="178f9-119">Set multiple start-up projects by right-clicking the solution in Solution Explorer and selecting **Set Startup Projects**.</span></span> <span data-ttu-id="178f9-120">添加“Scenario”和“Scenario_Client”（按此顺序）作为多个启动项目。</span><span class="sxs-lookup"><span data-stu-id="178f9-120">Add Scenario and Scenario_Client (in that order) as multiple start-up projects.</span></span>  
  
3.  <span data-ttu-id="178f9-121">按 Ctrl+Shift+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="178f9-121">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="178f9-122">由于自定义活动 `OperationScope` 的原因，要求使用此步骤查看 BankService.xaml 工作流。</span><span class="sxs-lookup"><span data-stu-id="178f9-122">This step is required to view the BankService.xaml workflow due to the custom activity `OperationScope`.</span></span>  
  
4.  <span data-ttu-id="178f9-123">按 Ctrl+F5 运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="178f9-123">Press CTRL+F5 to run the application.</span></span> <span data-ttu-id="178f9-124">Scenario_Client 控制台将提示您输入，而对应的输出将显示在 Scenario 控制台中。</span><span class="sxs-lookup"><span data-stu-id="178f9-124">The Scenario_Client console prompts you for inputs and the corresponding output is seen in the Scenario console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="178f9-125">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="178f9-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="178f9-126">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="178f9-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="178f9-127">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="178f9-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="178f9-128">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="178f9-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\OperationScope`