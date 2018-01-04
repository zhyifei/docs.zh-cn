---
title: "承载工作流服务概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19f3704f-06bf-4eeb-8724-5224e02d7ead
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 06012da95660fb4dc20d034c2d1691afad12037a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="hosting-workflow-services-overview"></a><span data-ttu-id="b6842-102">承载工作流服务概述</span><span class="sxs-lookup"><span data-stu-id="b6842-102">Hosting Workflow Services Overview</span></span>
<span data-ttu-id="b6842-103">工作流服务必须进行承载才能执行。</span><span class="sxs-lookup"><span data-stu-id="b6842-103">Workflow services must be hosted to execute.</span></span> <span data-ttu-id="b6842-104"><xref:System.ServiceModel.WorkflowServiceHost> 是现成的工作流主机，可支持多个实例、配置和 WCF 消息传递（虽然工作流无需使用消息传递即可进行承载）。</span><span class="sxs-lookup"><span data-stu-id="b6842-104">The <xref:System.ServiceModel.WorkflowServiceHost> is the out-of-the-box workflow host that supports multiple instances, configuration, and WCF messaging (although the workflows aren’t required to use messaging in order to be hosted).</span></span>  <span data-ttu-id="b6842-105">它还通过一组服务行为集成了持久性、跟踪和实例控件。</span><span class="sxs-lookup"><span data-stu-id="b6842-105">It also integrates with persistence, tracking, and instance control through a set of service behaviors.</span></span>  <span data-ttu-id="b6842-106">正如 WCF 的 <xref:System.ServiceModel.ServiceHost> 一样，<xref:System.ServiceModel.WorkflowServiceHost> 可以在任何托管 .NET 应用程序中自承载，或是在 IIS/WAS 中进行 Web 承载（作为 .xamlx 文件）。</span><span class="sxs-lookup"><span data-stu-id="b6842-106">Just like WCF’s <xref:System.ServiceModel.ServiceHost>, the <xref:System.ServiceModel.WorkflowServiceHost> can be self-hosted in any managed .NET application, or web-hosted (as a .xamlx file) in IIS / WAS.</span></span>  <span data-ttu-id="b6842-107">本节中的主题描述如何承载工作流服务。</span><span class="sxs-lookup"><span data-stu-id="b6842-107">Topics in this section describe how to host a workflow service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b6842-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="b6842-108">In This Section</span></span>  
 [<span data-ttu-id="b6842-109">承载工作流服务</span><span class="sxs-lookup"><span data-stu-id="b6842-109">Hosting Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-workflow-services.md)  
 <span data-ttu-id="b6842-110">描述承载工作流服务。</span><span class="sxs-lookup"><span data-stu-id="b6842-110">Describes hosting workflow services.</span></span>  
  
 [<span data-ttu-id="b6842-111">工作流服务主机内部机制</span><span class="sxs-lookup"><span data-stu-id="b6842-111">Workflow Service Host Internals</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)  
 <span data-ttu-id="b6842-112">描述 <xref:System.ServiceModel.WorkflowServiceHost> 如何处理传入消息。</span><span class="sxs-lookup"><span data-stu-id="b6842-112">Describes how <xref:System.ServiceModel.WorkflowServiceHost> processes incoming messages.</span></span>  
  
 [<span data-ttu-id="b6842-113">工作流服务主机扩展性</span><span class="sxs-lookup"><span data-stu-id="b6842-113">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 <span data-ttu-id="b6842-114">描述如何扩展工作流服务主机的功能。</span><span class="sxs-lookup"><span data-stu-id="b6842-114">Describes how to extend the functionality of the workflow service host.</span></span>  
  
 [<span data-ttu-id="b6842-115">工作流控制终结点</span><span class="sxs-lookup"><span data-stu-id="b6842-115">Workflow Control Endpoint</span></span>](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md)  
 <span data-ttu-id="b6842-116">描述如何定义使您可以创建工作流实例的终结点。</span><span class="sxs-lookup"><span data-stu-id="b6842-116">Describes how to define an endpoint that allows you to create workflow instances.</span></span>  
  
 [<span data-ttu-id="b6842-117">如何：在 IIS 中承载非服务工作流</span><span class="sxs-lookup"><span data-stu-id="b6842-117">How to: Host a non-service workflow in IIS</span></span>](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)  
 <span data-ttu-id="b6842-118">演示在 IIS 中承载不是工作流服务的工作流。</span><span class="sxs-lookup"><span data-stu-id="b6842-118">Demonstrates hosting a workflow that is not a workflow service in IIS.</span></span>  
  
 [<span data-ttu-id="b6842-119">如何：使用 Windows Server App Fabric 承载工作流服务</span><span class="sxs-lookup"><span data-stu-id="b6842-119">How to: Host a Workflow Service with Windows Server App Fabric</span></span>](../../../../docs/framework/wcf/feature-details/how-to-host-a-workflow-service-with-windows-server-app-fabric.md)  
 <span data-ttu-id="b6842-120">演示如何在 Windows Server App Fabric 中承载现有工作流服务。</span><span class="sxs-lookup"><span data-stu-id="b6842-120">Demonstrates how to host an existing workflow service in Windows Server App Fabric.</span></span>  
  
 [<span data-ttu-id="b6842-121">配置 WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="b6842-121">Configuring WorkflowServiceHost</span></span>](../../../../docs/framework/wcf/feature-details/configuring-workflowservicehost.md)  
 <span data-ttu-id="b6842-122">描述如何控制持久性、跟踪、空闲和未经处理的异常行为。</span><span class="sxs-lookup"><span data-stu-id="b6842-122">Describes how to control persistence, tracking, idle, and unhandled exception behavior.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b6842-123">参考</span><span class="sxs-lookup"><span data-stu-id="b6842-123">Reference</span></span>  
 <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
 <xref:System.ServiceModel.Activities.WorkflowService>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactory>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>  
  
 <xref:System.ServiceModel.Activation.WorkflowServiceHostFactory>  
  
## <a name="related-sections"></a><span data-ttu-id="b6842-124">相关章节</span><span class="sxs-lookup"><span data-stu-id="b6842-124">Related Sections</span></span>  
 [<span data-ttu-id="b6842-125">工作流服务</span><span class="sxs-lookup"><span data-stu-id="b6842-125">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
