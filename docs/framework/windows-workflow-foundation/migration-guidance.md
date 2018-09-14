---
title: 迁移指南
ms.date: 03/30/2017
ms.assetid: cb65c132-58c9-4028-b3d4-1efc71d5e60e
ms.openlocfilehash: 93d523c51c45f9b6f6235a7645fa126fcb09b6e5
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45520634"
---
# <a name="migration-guidance"></a><span data-ttu-id="90f4d-102">迁移指南</span><span class="sxs-lookup"><span data-stu-id="90f4d-102">Migration Guidance</span></span>
<span data-ttu-id="90f4d-103">在[!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]，Microsoft 正在发布的第二个主要版本的 Windows Workflow Foundation (WF)。</span><span class="sxs-lookup"><span data-stu-id="90f4d-103">In the [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], Microsoft is releasing the second major version of Windows Workflow Foundation (WF).</span></span> [!INCLUDE[wf1](../../../includes/wf1-md.md)]<span data-ttu-id="90f4d-104"> 发布在 [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] 中（包含 System.Workflow.\* 命名空间中的类型；目前称之为 WF3）并在 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 中得到增强。</span><span class="sxs-lookup"><span data-stu-id="90f4d-104"> was released in [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] (this included the types in the System.Workflow.\* namespaces; now referred to as WF3) and enhanced in [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].</span></span> <span data-ttu-id="90f4d-105">WF3 也是属于[!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]，但伴随新工作流技术 (System.Activities。 中的类型\*命名空间，则称为 WF4)。</span><span class="sxs-lookup"><span data-stu-id="90f4d-105">WF3 is also part of the [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], but it exists there alongside new workflow technology (the types in the System.Activities.\* namespaces; referred to as WF4).</span></span> <span data-ttu-id="90f4d-106">考虑何时采用 WF4 时，重要的是首先要认识到您来控制时间安排。</span><span class="sxs-lookup"><span data-stu-id="90f4d-106">When considering when to adopt WF4, it is important to first recognize that you control the timing.</span></span>  
  
-   <span data-ttu-id="90f4d-107">WF3 是 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] 完全支持的部分。</span><span class="sxs-lookup"><span data-stu-id="90f4d-107">WF3 is a fully supported part of the [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].</span></span>  
  
-   <span data-ttu-id="90f4d-108">WF3 应用程序无需修改即可运行于 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] 上并继续受到完全支持。</span><span class="sxs-lookup"><span data-stu-id="90f4d-108">WF3 applications run on the [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] without modification and continue to be fully supported.</span></span>  
  
-   <span data-ttu-id="90f4d-109">在 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 中可以创建新的 WF3 应用程序并且可以编辑现有应用程序，系统完全支持这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="90f4d-109">New WF3 applications can be created and your existing applications can be edited in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] and are fully supported.</span></span>  
  
 <span data-ttu-id="90f4d-110">因此，决定采用.NET Framework 4 脱离你的决定以移到 WF4 （system.activities.\*） 从 WF3 (System.Workflow。\*)。</span><span class="sxs-lookup"><span data-stu-id="90f4d-110">Thus, the decision to adopt the .NET Framework 4 is decoupled from your decision to move to WF4 (System.Activities.\*) from WF3 (System.Workflow.\*).</span></span> <span data-ttu-id="90f4d-111">本主题提供 WF 迁移指南的相关链接，涵盖了使用 WF3 和 WF4 的相关信息。</span><span class="sxs-lookup"><span data-stu-id="90f4d-111">This topic provides links to WF migration guidance that provides information about working with WF3 and WF4.</span></span>  
  
## <a name="wf-migration-whitepapers-and-cookbooks"></a><span data-ttu-id="90f4d-112">WF 迁移白皮书和实用手册</span><span class="sxs-lookup"><span data-stu-id="90f4d-112">WF Migration Whitepapers and Cookbooks</span></span>  
 <span data-ttu-id="90f4d-113">[WF 迁移概述](https://go.microsoft.com/fwlink/?LinkId=153873)主题提供了 WF3 与 WF4 和迁移策略之间的关系的广泛概述。</span><span class="sxs-lookup"><span data-stu-id="90f4d-113">The [WF Migration Overview](https://go.microsoft.com/fwlink/?LinkId=153873) topic provides a broad overview of the relationship between WF3 and WF4 and migration strategies.</span></span> <span data-ttu-id="90f4d-114">关联的主题深入探讨特定主题。</span><span class="sxs-lookup"><span data-stu-id="90f4d-114">Companion topics drill into specific topics.</span></span>  
  
 [<span data-ttu-id="90f4d-115">WF 迁移概述</span><span class="sxs-lookup"><span data-stu-id="90f4d-115">WF Migration Overview</span></span>](https://go.microsoft.com/fwlink/?LinkId=153873)  
 <span data-ttu-id="90f4d-116">描述 WF3 与 WF4 之间的关系，以及作为 .NET 4 中工作流技术的用户或潜在用户所拥有的选择。</span><span class="sxs-lookup"><span data-stu-id="90f4d-116">Describes the relationship between WF3 and WF4, and the choices you have as a user or a potential user of workflow technology in .NET 4.</span></span>  
  
 [<span data-ttu-id="90f4d-117">WF 迁移： WF3 开发的最佳做法</span><span class="sxs-lookup"><span data-stu-id="90f4d-117">WF Migration: Best Practices for WF3 Development</span></span>](https://go.microsoft.com/fwlink/?LinkId=153852)  
 <span data-ttu-id="90f4d-118">讨论如何设计 WF3 项目以便可以更轻松地迁移至 WF4。</span><span class="sxs-lookup"><span data-stu-id="90f4d-118">Discusses how to design WF3 artifacts so they can be more easily migrated to WF4.</span></span>  
  
 [<span data-ttu-id="90f4d-119">WF 指南： 规则</span><span class="sxs-lookup"><span data-stu-id="90f4d-119">WF Guidance: Rules</span></span>](https://go.microsoft.com/fwlink/?LinkId=153854)  
 <span data-ttu-id="90f4d-120">讨论如何将规则相关的投资引入 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] 解决方案。</span><span class="sxs-lookup"><span data-stu-id="90f4d-120">Discusses how to bring rules-related investments forward into [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] solutions.</span></span>  
  
 [<span data-ttu-id="90f4d-121">WF 指南： 状态机</span><span class="sxs-lookup"><span data-stu-id="90f4d-121">WF Guidance: State Machine</span></span>](https://go.microsoft.com/fwlink/?LinkId=153855)  
 <span data-ttu-id="90f4d-122">讨论在缺乏状态机活动下的 WF4 控制流建模。</span><span class="sxs-lookup"><span data-stu-id="90f4d-122">Discusses WF4 control flow modeling in the absence of a State-Machine activity.</span></span>  
  
 <span data-ttu-id="90f4d-123">请注意，本指南仅适用于面向 .NET Framework 4 的工作流项目。</span><span class="sxs-lookup"><span data-stu-id="90f4d-123">Note that this guidance only applies to workflow projects that target .NET Framework 4.</span></span> <span data-ttu-id="90f4d-124">状态机工作流在 .NET 4.0.1 中是通过发布 Platform Update 1 加入的，是 .NET Framework 4.5 的组成部分。</span><span class="sxs-lookup"><span data-stu-id="90f4d-124">State Machine workflows were added in .NET 4.0.1 with the release of Platform Update 1, and were included as part of .NET Framework 4.5.</span></span> <span data-ttu-id="90f4d-125">有关在.NET 4.0.1-4.0.3 和.NET Framework 4.5 中的状态机工作流的详细信息请参阅[4.0.1 版更新 Microsoft.NET Framework 4 功能](https://msdn.microsoft.com/library/de3297bd-c3e1-4126-95be-2ed7fe2a98fc)并[状态机工作流](../../../docs/framework/windows-workflow-foundation/state-machine-workflows.md)。</span><span class="sxs-lookup"><span data-stu-id="90f4d-125">For more information about state machine workflows in .NET 4.0.1 - 4.0.3 and .NET Framework 4.5, see [Update 4.0.1 for Microsoft .NET Framework 4 Features](https://msdn.microsoft.com/library/de3297bd-c3e1-4126-95be-2ed7fe2a98fc) and [State Machine Workflows](../../../docs/framework/windows-workflow-foundation/state-machine-workflows.md).</span></span>  
  
 [<span data-ttu-id="90f4d-126">WF 迁移实用手册： 自定义活动</span><span class="sxs-lookup"><span data-stu-id="90f4d-126">WF Migration Cookbook: Custom Activities</span></span>](https://go.microsoft.com/fwlink/?LinkId=153856)  
 <span data-ttu-id="90f4d-127">提供用于在 WF4 上重新设计 WF3 自定义活动的示例和说明。</span><span class="sxs-lookup"><span data-stu-id="90f4d-127">Provides examples and instructions for redesigning WF3 custom activities on WF4.</span></span>  
  
 [<span data-ttu-id="90f4d-128">WF 迁移实用手册： 高级自定义活动</span><span class="sxs-lookup"><span data-stu-id="90f4d-128">WF Migration Cookbook: Advanced Custom Activities</span></span>](https://go.microsoft.com/fwlink/?LinkId=275560)  
 <span data-ttu-id="90f4d-129">提供将使用 WF3 队列和对子活动进行排程的高级 WF3 自定义活动重新设计为 WF4 自定义活动的指南。</span><span class="sxs-lookup"><span data-stu-id="90f4d-129">Provides guidance for redesigning advanced WF3 custom activities that use WF3 queues and schedule child activities as WF4 custom activities.</span></span>  
  
 [<span data-ttu-id="90f4d-130">WF 迁移实用手册： 工作流</span><span class="sxs-lookup"><span data-stu-id="90f4d-130">WF Migration Cookbook: Workflows</span></span>](https://go.microsoft.com/fwlink/?LinkId=153858)  
 <span data-ttu-id="90f4d-131">提供用于在 WF4 上重新设计 WF3 工作流的示例和说明。</span><span class="sxs-lookup"><span data-stu-id="90f4d-131">Provides examples and instructions for redesigning WF3 workflows on WF4.</span></span>  
  
 [<span data-ttu-id="90f4d-132">WF 迁移实用手册： 工作流承载</span><span class="sxs-lookup"><span data-stu-id="90f4d-132">WF Migration Cookbook: Workflow Hosting</span></span>](https://go.microsoft.com/fwlink/?LinkId=275561)  
 <span data-ttu-id="90f4d-133">提供将 WF3 承载代码重新设计为 WF4 承载代码的指南。</span><span class="sxs-lookup"><span data-stu-id="90f4d-133">Provides guidance for redesigning WF3 hosting code as WF4 hosting code.</span></span> <span data-ttu-id="90f4d-134">目标是介绍 WF3 和 WF4 在工作流承载上的关键差异。</span><span class="sxs-lookup"><span data-stu-id="90f4d-134">The goal is to cover the key differences in workflow hosting between WF3 and WF4.</span></span>  
  
 [<span data-ttu-id="90f4d-135">WF 迁移实用手册： 工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="90f4d-135">WF Migration Cookbook: Workflow Tracking</span></span>](https://go.microsoft.com/fwlink/?LinkId=275562)  
 <span data-ttu-id="90f4d-136">提供用等价 WF4 跟踪代码和配置来重新设计 WF3 跟踪代码和配置的指南。</span><span class="sxs-lookup"><span data-stu-id="90f4d-136">Provides guidance for redesigning WF3 tracking code and configuration using equivalent WF4 tracking code and configuration.</span></span>  
  
 [<span data-ttu-id="90f4d-137">WF 指南： 工作流服务</span><span class="sxs-lookup"><span data-stu-id="90f4d-137">WF Guidance: Workflow Services</span></span>](https://go.microsoft.com/fwlink/?LinkId=275564)  
 <span data-ttu-id="90f4d-138">提供面向示例的分步说明，针对现成活动的一般方案，将在 WF3 中创建、实现 Windows Communication Foundation (WCF) Web 服务（通常称为工作流服务）的工作流重新设计为使用 WF4。</span><span class="sxs-lookup"><span data-stu-id="90f4d-138">Provides example-oriented step-by-step instructions for redesigning workflows that implement Windows Communication Foundation (WCF) web services (commonly referred to as workflow services) created in WF3 to use WF4, for common scenarios for out-of-box activities.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90f4d-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="90f4d-139">See Also</span></span>  
 <xref:System.Activities.Statements.Interop>
