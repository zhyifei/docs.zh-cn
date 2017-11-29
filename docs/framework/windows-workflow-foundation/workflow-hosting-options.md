---
title: "工作流托管选项"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37bcd668-9c5c-4e7c-81da-a1f1b3a16514
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 06d39fc37d40747eef323d83f65426e015099913
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="workflow-hosting-options"></a><span data-ttu-id="f7217-102">工作流托管选项</span><span class="sxs-lookup"><span data-stu-id="f7217-102">Workflow Hosting Options</span></span>
<span data-ttu-id="f7217-103">大多数 [!INCLUDE[wf](../../../includes/wf-md.md)] 示例都使用承载在控制台应用程序中的工作流，但这并非现实世界工作流的实际场景。</span><span class="sxs-lookup"><span data-stu-id="f7217-103">Most of the [!INCLUDE[wf](../../../includes/wf-md.md)] samples use workflows that are hosted in a console application, but this isn't a realistic scenario for real-world workflows.</span></span> <span data-ttu-id="f7217-104">实际业务应用程序中的工作流将会承载在恒定进程中 — 或是由开发人员编写的 Windows 服务，或是诸如 [!INCLUDE[iisver](../../../includes/iisver-md.md)] 或 AppFabric 之类的服务器应用程序。</span><span class="sxs-lookup"><span data-stu-id="f7217-104">Workflows in actual business applications will be hosted in persistent processes- either a Windows service authored by the developer, or a server application such as [!INCLUDE[iisver](../../../includes/iisver-md.md)] or AppFabric.</span></span> <span data-ttu-id="f7217-105">这些方法之间的区别如下。</span><span class="sxs-lookup"><span data-stu-id="f7217-105">The differences between these approaches are as follows.</span></span>  
  
## <a name="hosting-workflows-in-iis-with-windows-appfabric"></a><span data-ttu-id="f7217-106">用配有 Windows AppFabric 的 IIS 承载工作流</span><span class="sxs-lookup"><span data-stu-id="f7217-106">Hosting workflows in IIS with Windows AppFabric</span></span>  
 <span data-ttu-id="f7217-107">用配有 AppFabric 的 IIS 是承载工作流的首选方法。</span><span class="sxs-lookup"><span data-stu-id="f7217-107">Using IIS with AppFabric is the preferred host for workflows.</span></span> <span data-ttu-id="f7217-108">用 AppFabric 来承载工作流的应用程序是 Windows Activation Service，它解除了仅通过 IIS 对 HTTP 的依赖。</span><span class="sxs-lookup"><span data-stu-id="f7217-108">The host application for workflows using AppFabric is Windows Activation Service, which removes the dependency on HTTP over IIS alone.</span></span>  
  
## <a name="hosting-workflows-in-iis-alone"></a><span data-ttu-id="f7217-109">仅用 IIS 来承载工作流</span><span class="sxs-lookup"><span data-stu-id="f7217-109">Hosting workflows in IIS alone</span></span>  
 <span data-ttu-id="f7217-110">不建议仅用 [!INCLUDE[iisver](../../../includes/iisver-md.md)]，因为 AppFabric 有管理和监视工具，便于对运行中的应用程序进行维护。</span><span class="sxs-lookup"><span data-stu-id="f7217-110">Using [!INCLUDE[iisver](../../../includes/iisver-md.md)] alone is not recommended, as there are management and monitoring tools available with AppFabric that facilitate maintenance of running applications.</span></span> <span data-ttu-id="f7217-111">仅当有支持迁移到 AppFabric 的基础结构时，才应将工作流单独承载在 [!INCLUDE[iisver](../../../includes/iisver-md.md)] 中。</span><span class="sxs-lookup"><span data-stu-id="f7217-111">Workflows should only be hosted in [!INCLUDE[iisver](../../../includes/iisver-md.md)] alone if there are infrastructure concerns with moving to AppFabric.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="f7217-112">由于各种原因，[!INCLUDE[iisver](../../../includes/iisver-md.md)] 定期对应用程序池进行回收。</span><span class="sxs-lookup"><span data-stu-id="f7217-112">[!INCLUDE[iisver](../../../includes/iisver-md.md)] recycles application pools periodically for various reasons.</span></span> <span data-ttu-id="f7217-113">当应用程序池被回收时，IIS 即停止接受发给旧应用程序池的消息，并实例化一个新的应用程序池以接受新请求。</span><span class="sxs-lookup"><span data-stu-id="f7217-113">When an application pool is recycled, IIS stops accepting messages to the old pool, and instantiates a new application pool to accept new requests.</span></span> <span data-ttu-id="f7217-114">如果工作流在发出响应后继续运行，则 [!INCLUDE[iisver](../../../includes/iisver-md.md)] 不会知道正在运行的任务，可能会将宿主应用程序池回收掉。</span><span class="sxs-lookup"><span data-stu-id="f7217-114">If a workflow continues working after sending a response, [!INCLUDE[iisver](../../../includes/iisver-md.md)] will not be aware of the work being done, and may recycle the hosting application pool.</span></span> <span data-ttu-id="f7217-115">如果发生这种情况，将中止工作流，并跟踪服务将记录[1004-WorkflowInstanceAborted](../../../docs/framework/windows-workflow-foundation/1004-workflowinstanceaborted.md)使用空的原因字段的消息。</span><span class="sxs-lookup"><span data-stu-id="f7217-115">If this happens, the workflow will abort, and tracking services will record a [1004 - WorkflowInstanceAborted](../../../docs/framework/windows-workflow-foundation/1004-workflowinstanceaborted.md) message with an empty Reason field.</span></span>  
>   
>  <span data-ttu-id="f7217-116">如果使用了持久化机制，则主机必须显式地从上一个持久化点重启被中止的实例。</span><span class="sxs-lookup"><span data-stu-id="f7217-116">If persistence is used, the host must explicitly restart aborted instances from the last persistence point.</span></span>  
>   
>  <span data-ttu-id="f7217-117">如果使用了 AppFabric，则工作流管理服务最终将从上次成功持久化的点恢复工作流（如果使用了持久化机制）。</span><span class="sxs-lookup"><span data-stu-id="f7217-117">If AppFabric is used, the workflow management service will eventually resume the workflow from the last successful persistence point if persistence is used.</span></span> <span data-ttu-id="f7217-118">如果未使用持久化机制，则该工作流执行非“请求/响应”模式的操作，当工作流中止时，数据也将丢失。</span><span class="sxs-lookup"><span data-stu-id="f7217-118">If no persistence is used, and the workflow performs operations outside a Request/Response pattern, data will be lost when the workflow aborts.</span></span>  
  
## <a name="hosting-a-workflow-in-a-custom-windows-service"></a><span data-ttu-id="f7217-119">在自定义 Windows 服务中承载工作流</span><span class="sxs-lookup"><span data-stu-id="f7217-119">Hosting a workflow in a custom Windows Service</span></span>  
 <span data-ttu-id="f7217-120">若要创建自定义工作流服务来承载工作流，要求开发人员复制 AppFabric 自带的许多功能，但允许通过自定义功能实现更大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="f7217-120">Creating a custom workflow service to host the workflow will require the developer to duplicate a lot of the functionality provided out-of-box by AppFabric, but will allow for more flexibility with custom functionality.</span></span> <span data-ttu-id="f7217-121">仅当 AppFabric 经证不合适时，才应考虑这一选项。</span><span class="sxs-lookup"><span data-stu-id="f7217-121">This option should only be considered if AppFabric proves to not be an option.</span></span>
