---
title: 承载工作流服务概述
ms.date: 03/30/2017
ms.assetid: 19f3704f-06bf-4eeb-8724-5224e02d7ead
ms.openlocfilehash: dbe271e30e9c4e98a52c01ffaa21de25c127c7ff
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47208409"
---
# <a name="hosting-workflow-services-overview"></a><span data-ttu-id="2dba6-102">承载工作流服务概述</span><span class="sxs-lookup"><span data-stu-id="2dba6-102">Hosting Workflow Services Overview</span></span>
<span data-ttu-id="2dba6-103">工作流服务必须进行承载才能执行。</span><span class="sxs-lookup"><span data-stu-id="2dba6-103">Workflow services must be hosted to execute.</span></span> <span data-ttu-id="2dba6-104"><xref:System.ServiceModel.WorkflowServiceHost> 是现成的工作流主机，可支持多个实例、配置和 WCF 消息传递（虽然工作流无需使用消息传递即可进行承载）。</span><span class="sxs-lookup"><span data-stu-id="2dba6-104">The <xref:System.ServiceModel.WorkflowServiceHost> is the out-of-the-box workflow host that supports multiple instances, configuration, and WCF messaging (although the workflows aren’t required to use messaging in order to be hosted).</span></span>  <span data-ttu-id="2dba6-105">它还通过一组服务行为集成了持久性、跟踪和实例控件。</span><span class="sxs-lookup"><span data-stu-id="2dba6-105">It also integrates with persistence, tracking, and instance control through a set of service behaviors.</span></span>  <span data-ttu-id="2dba6-106">正如 WCF 的 <xref:System.ServiceModel.ServiceHost> 一样，<xref:System.ServiceModel.WorkflowServiceHost> 可以在任何托管 .NET 应用程序中自承载，或是在 IIS/WAS 中进行 Web 承载（作为 .xamlx 文件）。</span><span class="sxs-lookup"><span data-stu-id="2dba6-106">Just like WCF’s <xref:System.ServiceModel.ServiceHost>, the <xref:System.ServiceModel.WorkflowServiceHost> can be self-hosted in any managed .NET application, or web-hosted (as a .xamlx file) in IIS / WAS.</span></span>  <span data-ttu-id="2dba6-107">本节中的主题描述如何承载工作流服务。</span><span class="sxs-lookup"><span data-stu-id="2dba6-107">Topics in this section describe how to host a workflow service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2dba6-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="2dba6-108">In This Section</span></span>  
 [<span data-ttu-id="2dba6-109">承载工作流服务</span><span class="sxs-lookup"><span data-stu-id="2dba6-109">Hosting Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-workflow-services.md)  
 <span data-ttu-id="2dba6-110">描述承载工作流服务。</span><span class="sxs-lookup"><span data-stu-id="2dba6-110">Describes hosting workflow services.</span></span>  
  
 [<span data-ttu-id="2dba6-111">工作流服务主机内部机制</span><span class="sxs-lookup"><span data-stu-id="2dba6-111">Workflow Service Host Internals</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)  
 <span data-ttu-id="2dba6-112">描述 <xref:System.ServiceModel.WorkflowServiceHost> 如何处理传入消息。</span><span class="sxs-lookup"><span data-stu-id="2dba6-112">Describes how <xref:System.ServiceModel.WorkflowServiceHost> processes incoming messages.</span></span>  
  
 [<span data-ttu-id="2dba6-113">工作流服务主机扩展性</span><span class="sxs-lookup"><span data-stu-id="2dba6-113">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 <span data-ttu-id="2dba6-114">描述如何扩展工作流服务主机的功能。</span><span class="sxs-lookup"><span data-stu-id="2dba6-114">Describes how to extend the functionality of the workflow service host.</span></span>  
  
 [<span data-ttu-id="2dba6-115">工作流控制终结点</span><span class="sxs-lookup"><span data-stu-id="2dba6-115">Workflow Control Endpoint</span></span>](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md)  
 <span data-ttu-id="2dba6-116">描述如何定义使您可以创建工作流实例的终结点。</span><span class="sxs-lookup"><span data-stu-id="2dba6-116">Describes how to define an endpoint that allows you to create workflow instances.</span></span>
  
 [<span data-ttu-id="2dba6-117">如何：使用 Windows Server App Fabric 承载工作流服务</span><span class="sxs-lookup"><span data-stu-id="2dba6-117">How to: Host a Workflow Service with Windows Server App Fabric</span></span>](../../../../docs/framework/wcf/feature-details/how-to-host-a-workflow-service-with-windows-server-app-fabric.md)  
 <span data-ttu-id="2dba6-118">演示如何在 Windows Server App Fabric 中承载现有工作流服务。</span><span class="sxs-lookup"><span data-stu-id="2dba6-118">Demonstrates how to host an existing workflow service in Windows Server App Fabric.</span></span>  
  
 [<span data-ttu-id="2dba6-119">配置 WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="2dba6-119">Configuring WorkflowServiceHost</span></span>](../../../../docs/framework/wcf/feature-details/configuring-workflowservicehost.md)  
 <span data-ttu-id="2dba6-120">描述如何控制持久性、跟踪、空闲和未经处理的异常行为。</span><span class="sxs-lookup"><span data-stu-id="2dba6-120">Describes how to control persistence, tracking, idle, and unhandled exception behavior.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2dba6-121">参考</span><span class="sxs-lookup"><span data-stu-id="2dba6-121">Reference</span></span>  
 <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
 <xref:System.ServiceModel.Activities.WorkflowService>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactory>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>  
  
 <xref:System.ServiceModel.Activation.WorkflowServiceHostFactory>  
  
## <a name="related-sections"></a><span data-ttu-id="2dba6-122">相关章节</span><span class="sxs-lookup"><span data-stu-id="2dba6-122">Related Sections</span></span>  
 [<span data-ttu-id="2dba6-123">工作流服务</span><span class="sxs-lookup"><span data-stu-id="2dba6-123">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
