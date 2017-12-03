---
title: "宿主锁定续订期"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f8ba94fc-27e0-4d8e-8f85-50a6d2a3cd43
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 48a5d2e1d8c5381f322ea1b6ffc9022853683efc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="host-lock-renewal-period"></a><span data-ttu-id="ddb4b-102">宿主锁定续订期</span><span class="sxs-lookup"><span data-stu-id="ddb4b-102">Host Lock Renewal Period</span></span>
<span data-ttu-id="ddb4b-103">**宿主锁定续订期**SQL 工作流实例存储的属性，可以指定宿主在其间续订它对工作流实例的锁定的时间段。</span><span class="sxs-lookup"><span data-stu-id="ddb4b-103">The **Host Lock Renewal Period** property of the SQL Workflow Instance Store lets you specify the time period within which the host renews its lock on a workflow instance.</span></span> <span data-ttu-id="ddb4b-104">锁定在宿主锁定续订期及其后 30 秒内有效。</span><span class="sxs-lookup"><span data-stu-id="ddb4b-104">The lock remains valid for Host Lock Renewal Period + 30 seconds.</span></span> <span data-ttu-id="ddb4b-105">如果宿主未能在此时间段内续订锁定（换句话说，延长租约），则锁定将过期并且持久性提供程序将解除实例锁定。</span><span class="sxs-lookup"><span data-stu-id="ddb4b-105">If the host fails to renew the lock (in other words, extend the lease) within this time period, the lock expires and the persistence provider unlocks the instance.</span></span> <span data-ttu-id="ddb4b-106">此属性的值是类型为 TimeSpan 的窗体"hh: mm:"。</span><span class="sxs-lookup"><span data-stu-id="ddb4b-106">The value for this property is of type TimeSpan of the form "hh:mm:ss".</span></span> <span data-ttu-id="ddb4b-107">允许值的最小为"00: 00:01"（1 秒）。</span><span class="sxs-lookup"><span data-stu-id="ddb4b-107">The minimum permitted value is "00:00:01" (1 second).</span></span> <span data-ttu-id="ddb4b-108">此属性的默认值为"00: 00:30"（30 秒）。</span><span class="sxs-lookup"><span data-stu-id="ddb4b-108">The default value of this property is "00:00:30" (30 seconds).</span></span>  
  
 <span data-ttu-id="ddb4b-109">在工作流服务宿主解除其拥有的工作流服务实例的锁定之前该宿主即失败的情况下，此属性很重要。</span><span class="sxs-lookup"><span data-stu-id="ddb4b-109">This property is significant in scenarios where a workflow service host fails before it can unlock a workflow service instance that it owns.</span></span> <span data-ttu-id="ddb4b-110">在这种情况下，持久性提供程序将在该锁定过期后移除持久性数据库中工作流服务实例上的锁定，以便运行在同一台计算机上或服务器场中的另一台计算机上的另一工作流服务宿主可以获取锁定并将工作流服务实例加载到内存中，从而从该工作流服务实例的最后持久保存状态继续其执行。</span><span class="sxs-lookup"><span data-stu-id="ddb4b-110">In this scenario, the lock on the workflow service instance in the persistence database is removed by the persistence provider after the lock expires so that another workflow service host running on the same computer or another computer in a server farm can acquire the lock and load the workflow service instance into memory to resume its execution from its last persisted state.</span></span>  
  
 <span data-ttu-id="ddb4b-111">将此属性设置为较大的值将使工作流服务实例在持久性数据库中锁定的时间更长，从而延迟该实例从最后一个持久点恢复的时间。</span><span class="sxs-lookup"><span data-stu-id="ddb4b-111">Setting a higher value for this property causes the workflow service instances to be locked in the persistence database for a longer time and therefore delays the recovery of the instance from the last persistence point.</span></span> <span data-ttu-id="ddb4b-112">将此属性设置为较短间隔可使工作流服务宿主的新实例快速选取失败的工作流服务实例，但会导致工作流服务宿主和 SQL Server 数据库的工作负荷增加。</span><span class="sxs-lookup"><span data-stu-id="ddb4b-112">Setting a short interval for this property causes the new instance of the workflow service host to pick up the failed workflow service instance quickly, but causes an increase in workload for the workflow service host and the SQL Server database.</span></span>  
  
 <span data-ttu-id="ddb4b-113">SQL 工作流实例存储运行一个内部任务，该任务将定期苏醒并检测实例上是否有过期锁定。</span><span class="sxs-lookup"><span data-stu-id="ddb4b-113">The SQL Workflow Instance Store runs an internal task that periodically wakes up and detects instances with expired locks on them.</span></span> <span data-ttu-id="ddb4b-114">当它发现有过期锁定的实例时，会将这些实例放在 RunnableInstances 表中，以使工作流宿主可以选取并运行这些实例。</span><span class="sxs-lookup"><span data-stu-id="ddb4b-114">When it finds instances with expired locks, it places the instances in the RunnableInstances table so that a workflow host can pick up and run these instances.</span></span>
