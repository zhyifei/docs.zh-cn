---
title: "WF 中的事务活动"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb33378e-82c6-4ea0-870f-76dc77e7f0fe
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e6c72a54d596468e1ae6948ff9f177e026458628
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="transaction-activities-in-wf"></a><span data-ttu-id="ae882-102">WF 中的事务活动</span><span class="sxs-lookup"><span data-stu-id="ae882-102">Transaction Activities in WF</span></span>
<span data-ttu-id="ae882-103">[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]包含几个系统提供的活动，它们用于对事务、补偿和取消进行建模。</span><span class="sxs-lookup"><span data-stu-id="ae882-103">The [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] has several system-provided activities for modeling transactions, compensation, and cancellation.</span></span> <span data-ttu-id="ae882-104">通过这些编程模型，工作流可以在业务逻辑和错误处理中发生更改时继续向前推进。</span><span class="sxs-lookup"><span data-stu-id="ae882-104">These programming models allow the workflow to continue forward progress in the event of changes in business logic and error handling.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="ae882-105">事务、 补偿和取消，请参阅[事务](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md)，[补偿](../../../docs/framework/windows-workflow-foundation/compensation.md)，和[取消](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md)。</span><span class="sxs-lookup"><span data-stu-id="ae882-105"> transactions, compensation, and cancellation, see [Transactions](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md), [Compensation](../../../docs/framework/windows-workflow-foundation/compensation.md), and [Cancellation](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md).</span></span>  
  
## <a name="transaction-activities"></a><span data-ttu-id="ae882-106">事务活动</span><span class="sxs-lookup"><span data-stu-id="ae882-106">Transaction Activities</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.CancellationScope>|<span data-ttu-id="ae882-107">将活动形式的取消逻辑与执行的主要路径（也表示为活动）相关联。</span><span class="sxs-lookup"><span data-stu-id="ae882-107">Associates cancellation logic, in the form of an activity, with a main path of execution, also expressed as an activity.</span></span>|  
|<xref:System.Activities.Statements.CompensableActivity>|<span data-ttu-id="ae882-108">支持对其子活动的补偿。</span><span class="sxs-lookup"><span data-stu-id="ae882-108">Supports compensation of its child activities.</span></span>|  
|<xref:System.Activities.Statements.Compensate>|<span data-ttu-id="ae882-109">显式调用 <xref:System.Activities.Statements.CompensableActivity> 的补偿处理程序。</span><span class="sxs-lookup"><span data-stu-id="ae882-109">Explicitly invokes the compensation handler of a <xref:System.Activities.Statements.CompensableActivity>.</span></span>|  
|<xref:System.Activities.Statements.Confirm>|<span data-ttu-id="ae882-110">显式调用 <xref:System.Activities.Statements.CompensableActivity> 的确认处理程序。</span><span class="sxs-lookup"><span data-stu-id="ae882-110">Explicitly invokes the confirmation handler of a <xref:System.Activities.Statements.CompensableActivity>.</span></span>|  
|<xref:System.Activities.Statements.TransactionScope>|<span data-ttu-id="ae882-111">划分事务边界。</span><span class="sxs-lookup"><span data-stu-id="ae882-111">Demarcates a transaction boundary.</span></span>|  
|<xref:System.ServiceModel.Activities.TransactedReceiveScope>|<span data-ttu-id="ae882-112">确定接收的消息启动的事务的生存期范围。</span><span class="sxs-lookup"><span data-stu-id="ae882-112">Scopes the lifetime of a transaction that is initiated by a received message.</span></span> <span data-ttu-id="ae882-113">事务可以流入发起消息的工作流中，也可以在收到消息时由调度程序创建。</span><span class="sxs-lookup"><span data-stu-id="ae882-113">The transaction may be flowed into the workflow on the initiating message, or created by the dispatcher when the message is received.</span></span> <span data-ttu-id="ae882-114">**注意：** <xref:System.ServiceModel.Activities.TransactedReceiveScope>位于**消息**部分**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="ae882-114">**Note:**  The <xref:System.ServiceModel.Activities.TransactedReceiveScope> is located in the **Messaging** section of the **Toolbox**.</span></span>|
