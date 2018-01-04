---
title: "分层配置模型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28dcc698-226c-4b77-9e51-8bf45a36216c
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cf8e7b37b6430be1eed9bc037bfa06aeb825b866
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="hierarchical-configuration-model"></a><span data-ttu-id="a6b32-102">分层配置模型</span><span class="sxs-lookup"><span data-stu-id="a6b32-102">Hierarchical Configuration Model</span></span>
<span data-ttu-id="a6b32-103">此示例演示如何实现服务配置文件的层次结构。</span><span class="sxs-lookup"><span data-stu-id="a6b32-103">This sample demonstrates how to implement a hierarchy of configuration files for services.</span></span> <span data-ttu-id="a6b32-104">它还演示如何从层次结构中较高的级别继承绑定、服务行为和终结点行为。</span><span class="sxs-lookup"><span data-stu-id="a6b32-104">It also shows how bindings, service behaviors, and endpoint behaviors are inherited from higher levels in the hierarchy.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="a6b32-105">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="a6b32-105">Sample details</span></span>  
 <span data-ttu-id="a6b32-106">为 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中的 [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] 开发的功能之一是分层配置模型中的改进。</span><span class="sxs-lookup"><span data-stu-id="a6b32-106">One of the features developed for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] is the improvement in the hierarchical configuration model.</span></span> <span data-ttu-id="a6b32-107">分层配置模型的一个示例是通过 Machine.config -> Rootweb.config -> Web.config 定义的模型。在 [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] 中，那些在配置层次结构的较高级别中定义的绑定和行为将添加到没有显式配置的服务中。</span><span class="sxs-lookup"><span data-stu-id="a6b32-107">An example of a hierarchical configuration model would be the one defined by Machine.config -> Rootweb.config -> Web.config. In [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], those bindings and behaviors that are defined in upper levels in the configuration hierarchy are added to your services with no explicit configuration.</span></span> <span data-ttu-id="a6b32-108">此示例演示如何通过依赖于在计算机或应用程序级别定义的配置元素来简化服务配置。</span><span class="sxs-lookup"><span data-stu-id="a6b32-108">This sample shows how it is possible to simplify your service configuration by relying on configuration elements defined at the computer or the application level.</span></span>  
  
 <span data-ttu-id="a6b32-109">此示例包含在层次结构的三个级别中定义的九项服务。</span><span class="sxs-lookup"><span data-stu-id="a6b32-109">This sample consists of nine services, defined in three levels of hierarchy.</span></span> <span data-ttu-id="a6b32-110">`Service1` 位于根目录中。</span><span class="sxs-lookup"><span data-stu-id="a6b32-110">`Service1` is at the root.</span></span> <span data-ttu-id="a6b32-111">`Service2` 和 `Service3` 类继承 `Service1` 中的默认元素。</span><span class="sxs-lookup"><span data-stu-id="a6b32-111">`Service2` and `Service3` inherit the default elements from `Service1`.</span></span> <span data-ttu-id="a6b32-112">`Service4`、`Service5`、 `Service6` 和 `Service7` 在层次结构的第三层定义，继承 `Service3` 中的默认元素。</span><span class="sxs-lookup"><span data-stu-id="a6b32-112">`Service4`, `Service5`, `Service6` and `Service7` are defined at a third level of the hierarchy, inheriting the default elements from `Service3`.</span></span> <span data-ttu-id="a6b32-113">最后，`Service10` 和 `Service11` 位于层次结构的第四层。</span><span class="sxs-lookup"><span data-stu-id="a6b32-113">Finally `Service10` and `Service11` are at a fourth level of the hierarchy.</span></span>  
  
 <span data-ttu-id="a6b32-114">所有这些服务都实现 `IDesc` 协定。</span><span class="sxs-lookup"><span data-stu-id="a6b32-114">All the services implement the `IDesc` contract.</span></span> <span data-ttu-id="a6b32-115">下面是 `IDesc` 接口的定义，它显示了此接口中公开的方法。</span><span class="sxs-lookup"><span data-stu-id="a6b32-115">The following is the definition of the `IDesc` interface that shows the methods exposed in this interface.</span></span> <span data-ttu-id="a6b32-116">`IDesc` 接口在 Service1.cs 中定义。</span><span class="sxs-lookup"><span data-stu-id="a6b32-116">The `IDesc` interface is defined in Service1.cs.</span></span>  
  
```  
// Define a service contract  
[ServiceContract(Namespace="http://Microsoft.Samples.ConfigHierarchicalModel")]  
public interface IDesc  
{  
    [OperationContract]  
    List<string> ListEndpoints();  
    [OperationContract]  
    List<string> ListServiceBehaviors();  
    [OperationContract]  
    List<string> ListEndpointBehaviors();  
}  
```  
  
 <span data-ttu-id="a6b32-117">这些服务对方法的实现是很简单直接的。</span><span class="sxs-lookup"><span data-stu-id="a6b32-117">The implementation of these methods by the services is straightforward.</span></span> <span data-ttu-id="a6b32-118">`ListEndpoints` 循环访问所有服务终结点，并返回该服务具有的所有终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="a6b32-118">`ListEndpoints` iterates through all the service endpoints and returns a list of all the endpoints that the service has.</span></span> <span data-ttu-id="a6b32-119">`ListServiceBehaviors` 循环访问所有添加到服务的行为，并返回与服务相关联的所有服务行为的列表。</span><span class="sxs-lookup"><span data-stu-id="a6b32-119">`ListServiceBehaviors` iterates through all the behaviors added to the service and returns the list of all the service behaviors associated with the service.</span></span> <span data-ttu-id="a6b32-120">`ListEndpointBehaviors` 的行为方式类似于 `ListServiceBehaviors`，但它返回的是终结点行为的列表。</span><span class="sxs-lookup"><span data-stu-id="a6b32-120">`ListEndpointBehaviors` behaves in a similar way to `ListServiceBehaviors`, but it returns the list of endpoint behaviors instead.</span></span>  
  
 <span data-ttu-id="a6b32-121">通过此实现，客户端可以知道服务公开了多少终结点，以及哪些服务行为和终结点行为已添加到该服务中。</span><span class="sxs-lookup"><span data-stu-id="a6b32-121">This implementation allows the client to know how many endpoints the service is exposing and which service behaviors and endpoint behaviors have been added to the service.</span></span> <span data-ttu-id="a6b32-122">已作为该示例的一部分实现的客户端在该解决方案中添加一个对所有服务的服务引用，并为每个服务显示这些元素。</span><span class="sxs-lookup"><span data-stu-id="a6b32-122">The client that has been implemented as part of the sample adds a service reference to all the services in the solution and shows these elements for each one of the services.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="a6b32-123">使用此示例</span><span class="sxs-lookup"><span data-stu-id="a6b32-123">To use this sample</span></span>  
  
#### <a name="to-run-the-client"></a><span data-ttu-id="a6b32-124">运行客户端</span><span class="sxs-lookup"><span data-stu-id="a6b32-124">To run the client</span></span>  
  
1.  <span data-ttu-id="a6b32-125">使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 ConfigHierarchicalModel.sln 文件。</span><span class="sxs-lookup"><span data-stu-id="a6b32-125">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the ConfigHierarchicalModel.sln file.</span></span>  
  
2.  <span data-ttu-id="a6b32-126">客户端项目尚未设置为启动项目，请执行下列步骤。</span><span class="sxs-lookup"><span data-stu-id="a6b32-126">The client project is not already set up as the start-up project, follow these steps.</span></span>  
  
    1.  <span data-ttu-id="a6b32-127">在**解决方案资源管理器**，右键单击该解决方案，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="a6b32-127">In **Solution Explorer**, right-click the solution and then select **Properties**.</span></span>  
  
    2.  <span data-ttu-id="a6b32-128">在**通用属性**，选择**启动项目**，然后单击**单启动项目**。</span><span class="sxs-lookup"><span data-stu-id="a6b32-128">In **Common Properties**, select **Startup Project**, and then click **Single startup project**.</span></span>  
  
    3.  <span data-ttu-id="a6b32-129">从**单启动项目**下拉列表中，选择**客户端**。</span><span class="sxs-lookup"><span data-stu-id="a6b32-129">From the **Single startup project** drop-down, select **Client**.</span></span>  
  
    4.  <span data-ttu-id="a6b32-130">单击**确定**关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="a6b32-130">Click **OK** to close the dialog.</span></span>  
  
3.  <span data-ttu-id="a6b32-131">要生成此示例，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="a6b32-131">To build the sample, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="a6b32-132">若要运行客户端，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="a6b32-132">To run the client, press Ctrl+F5.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a6b32-133">如果这些步骤不起作用，则通过以下步骤来确保已正确设置环境。</span><span class="sxs-lookup"><span data-stu-id="a6b32-133">If these steps do not work, then make sure that your environment has been properly set up, using the following steps.</span></span>  
>   
>  1.  <span data-ttu-id="a6b32-134">确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="a6b32-134">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
> 2.  <span data-ttu-id="a6b32-135">若要生成解决方案，请按照中的说明[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="a6b32-135">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
> 3.  <span data-ttu-id="a6b32-136">若要在一个或多个计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="a6b32-136">To run the sample in a single or multiple computer configurations, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a6b32-137">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="a6b32-137">The samples may already be installed on your computer.</span></span> <span data-ttu-id="a6b32-138">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="a6b32-138">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a6b32-139">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="a6b32-139">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a6b32-140">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="a6b32-140">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigHierarchicalModel`  
  
## <a name="see-also"></a><span data-ttu-id="a6b32-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6b32-141">See Also</span></span>  
 [<span data-ttu-id="a6b32-142">AppFabric 管理示例</span><span class="sxs-lookup"><span data-stu-id="a6b32-142">AppFabric Management Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193960)
