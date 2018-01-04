---
title: "可运行实例的检测周期"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ea5c787-b638-47fd-bfc8-ede8c2898ce6
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 561ef96b6f043956822a1290d4a03a2e7411f6f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="runnable-instances-detection-period"></a><span data-ttu-id="74e28-102">可运行实例的检测周期</span><span class="sxs-lookup"><span data-stu-id="74e28-102">Runnable Instances Detection Period</span></span>
<span data-ttu-id="74e28-103">SQL 工作流实例存储运行一个内部任务，该任务将定期唤醒并检测持久性数据库中是否有可运行或可激活的实例。</span><span class="sxs-lookup"><span data-stu-id="74e28-103">The SQL Workflow Instance Store runs an internal task that periodically wakes up and detects runnable or activatable instances in the persistence database.</span></span> <span data-ttu-id="74e28-104">**可运行实例的检测周期**SQL 工作流实例存储的属性指定的时间段后，SQL 工作流实例存储将运行一个检测任务，以检测任何可运行或可激活的工作流在上一检测周期后持久性数据库中的实例。</span><span class="sxs-lookup"><span data-stu-id="74e28-104">The **Runnable Instances Detection Period** property of the SQL Workflow Instance Store specifies the time period after which the SQL Workflow Instance Store runs a detection task to detect any runnable or activatable workflow instances in the persistence database after the previous detection cycle.</span></span>  
  
 <span data-ttu-id="74e28-105">为此属性设置一个较短的间隔可减少与工作流实例相关联的计时器到期与发出事件信号并在随后加载实例之间的时间。</span><span class="sxs-lookup"><span data-stu-id="74e28-105">Setting a shorter interval for this property reduces the time between the expiration of a timer associated with a workflow instance and the signaling of the event and subsequent loading of the instance.</span></span> <span data-ttu-id="74e28-106">但是，这同时也会增大主机上的处理负载，在很少采用持久性计时器和/或很少发生主机故障的情况下，您可能不希望采用此类设置。</span><span class="sxs-lookup"><span data-stu-id="74e28-106">However, it also increases the processing load on a host and may not be desirable in scenarios where durable timers and/or host failures are rare.</span></span> <span data-ttu-id="74e28-107">该属性的类型为 TimeSpan，其值遵循以下格式：hh:mm:ss。</span><span class="sxs-lookup"><span data-stu-id="74e28-107">The type of the property is TimeSpan and the value of the property follows the format: hh:mm:ss.</span></span> <span data-ttu-id="74e28-108">该属性的最小值为 00:00:01，</span><span class="sxs-lookup"><span data-stu-id="74e28-108">The minimum value for this property is 00:00:01.</span></span> <span data-ttu-id="74e28-109">默认值为 00:00:05。</span><span class="sxs-lookup"><span data-stu-id="74e28-109">The default value for the property is 00:00:05.</span></span>  
  
 <span data-ttu-id="74e28-110">有关详细信息检测和激活可运行且可激活的工作流实例，请参阅[实例激活](../../../docs/framework/windows-workflow-foundation/instance-activation.md)。</span><span class="sxs-lookup"><span data-stu-id="74e28-110">For more information detecting and activating runnable and activatable workflow instances, see [Instance Activation](../../../docs/framework/windows-workflow-foundation/instance-activation.md).</span></span>
