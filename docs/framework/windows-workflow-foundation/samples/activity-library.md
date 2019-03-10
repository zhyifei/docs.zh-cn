---
title: 活动库
ms.date: 03/30/2017
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
ms.openlocfilehash: b701d382c25644181b23f3c0f0cd8e019b8d37d1
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709830"
---
# <a name="activity-library"></a><span data-ttu-id="c7438-102">活动库</span><span class="sxs-lookup"><span data-stu-id="c7438-102">Activity Library</span></span>
<span data-ttu-id="c7438-103">本节包含演示高级自定义活动在 Windows Workflow Foundation (WF) 的示例。</span><span class="sxs-lookup"><span data-stu-id="c7438-103">This section contains samples that demonstrate advanced custom activities in Windows Workflow Foundation (WF).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c7438-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="c7438-104">In This Section</span></span>

 [<span data-ttu-id="c7438-105">SendMail 自定义活动</span><span class="sxs-lookup"><span data-stu-id="c7438-105">SendMail Custom Activity</span></span>](sendmail-custom-activity.md)  
 <span data-ttu-id="c7438-106">演示如何创建派生自 <xref:System.Activities.AsyncCodeActivity> 的自定义活动，以使用 SMTP 发送邮件供在工作流应用程序内使用。</span><span class="sxs-lookup"><span data-stu-id="c7438-106">Demonstrates how to create a custom activity that derives from <xref:System.Activities.AsyncCodeActivity> to send mail using SMTP for use within a workflow application.</span></span>  
  
 [<span data-ttu-id="c7438-107">限制并行 ForEach</span><span class="sxs-lookup"><span data-stu-id="c7438-107">Throttled Parallel ForEach</span></span>](throttled-parallel-foreach.md)  
 <span data-ttu-id="c7438-108">演示 `ThrottleParallelForEach` 活动与 <xref:System.Activities.Statements.ParallelForEach%601> 活动的相似之处，二者的不同之处在于，前者允许设置一个并发因子来限制要同时执行的分支的数量。</span><span class="sxs-lookup"><span data-stu-id="c7438-108">Demonstrates how the `ThrottleParallelForEach` activity is similar to the <xref:System.Activities.Statements.ParallelForEach%601> activity with the one exception that it allows setting a concurrency factor to restrict the number of simultaneous branches to execute.</span></span>
  
 [<span data-ttu-id="c7438-109">数据库访问活动</span><span class="sxs-lookup"><span data-stu-id="c7438-109">Database Access Activities</span></span>](database-access-activities.md)  
 <span data-ttu-id="c7438-110">演示如何创建可以访问数据库以检索或修改信息并使用活动[ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081)来访问数据库。</span><span class="sxs-lookup"><span data-stu-id="c7438-110">Demonstrates how to create activities that allow accessing databases to retrieve or modify information and use [ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081) to access the database.</span></span>  
  
 [<span data-ttu-id="c7438-111">.NET Framework 4.5 中的外部化策略活动</span><span class="sxs-lookup"><span data-stu-id="c7438-111">Externalized Policy Activity in .NET Framework 4.5</span></span>](externalized-policy-activity-in-net-framework-4-5.md)  
 <span data-ttu-id="c7438-112">演示 ExternalizedPolicy4 活动如何允许执行中的现有 Windows Workflow Foundation [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF 3.5)<xref:System.Workflow.Activities.Rules.RuleSet>中的 Windows Workflow Foundation 中的对象[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)](WF 4.5) 直接通过使用规则引擎，它是在 WF 3.5 中提供。</span><span class="sxs-lookup"><span data-stu-id="c7438-112">Demonstrates how the ExternalizedPolicy4 activity allows executing existing Windows Workflow Foundation in [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> objects in Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) directly by using the rules engine that is shipped in WF 3.5.</span></span> 
  
 [<span data-ttu-id="c7438-113">非泛型 ForEach</span><span class="sxs-lookup"><span data-stu-id="c7438-113">Non-Generic ForEach</span></span>](non-generic-foreach.md)  
 <span data-ttu-id="c7438-114">演示了如何创建非泛型版本的 <xref:System.Activities.Statements.ForEach%601> 活动。</span><span class="sxs-lookup"><span data-stu-id="c7438-114">Demonstrates how to create a non-generic version of the <xref:System.Activities.Statements.ForEach%601> activity.</span></span>  
  
 [<span data-ttu-id="c7438-115">非泛型 ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="c7438-115">Non-Generic ParallelForEach</span></span>](non-generic-parallelforeach.md)  
 <span data-ttu-id="c7438-116">演示了如何创建非泛型版本的 <xref:System.Activities.Statements.ParallelForEach%601> 活动。</span><span class="sxs-lookup"><span data-stu-id="c7438-116">Demonstrates how to create a non-generic version of the <xref:System.Activities.Statements.ParallelForEach%601> activity.</span></span>  
  
 [<span data-ttu-id="c7438-117">获取 WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="c7438-117">Get WorkflowInstanceId</span></span>](get-workflowinstanceid.md)  
 <span data-ttu-id="c7438-118">演示如何使用自定义活动 `GetWorkflowInstanceId` 返回工作流实例 ID。</span><span class="sxs-lookup"><span data-stu-id="c7438-118">Demonstrates how to use the custom activity, `GetWorkflowInstanceId`, to return the workflow instance ID.</span></span>
