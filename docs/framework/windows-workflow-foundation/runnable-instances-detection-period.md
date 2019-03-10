---
title: 可运行实例的检测周期
ms.date: 03/30/2017
ms.assetid: 4ea5c787-b638-47fd-bfc8-ede8c2898ce6
ms.openlocfilehash: 9652dd811f64e5324219b8aa0700ab8219edeeb0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709696"
---
# <a name="runnable-instances-detection-period"></a><span data-ttu-id="c9295-102">可运行实例的检测周期</span><span class="sxs-lookup"><span data-stu-id="c9295-102">Runnable Instances Detection Period</span></span>
<span data-ttu-id="c9295-103">SQL 工作流实例存储运行一个内部任务，该任务将定期唤醒并检测持久性数据库中是否有可运行或可激活的实例。</span><span class="sxs-lookup"><span data-stu-id="c9295-103">The SQL Workflow Instance Store runs an internal task that periodically wakes up and detects runnable or activatable instances in the persistence database.</span></span> <span data-ttu-id="c9295-104">**可运行实例的检测周期**SQL 工作流实例存储的属性指定的时间段后将 SQL 工作流实例存储运行一个检测任务，以检测任何可运行或可激活的工作流上一检测周期后持久性数据库中的实例。</span><span class="sxs-lookup"><span data-stu-id="c9295-104">The **Runnable Instances Detection Period** property of the SQL Workflow Instance Store specifies the time period after which the SQL Workflow Instance Store runs a detection task to detect any runnable or activatable workflow instances in the persistence database after the previous detection cycle.</span></span>  
  
 <span data-ttu-id="c9295-105">为此属性设置一个较短的间隔可减少与工作流实例相关联的计时器到期与发出事件信号并在随后加载实例之间的时间。</span><span class="sxs-lookup"><span data-stu-id="c9295-105">Setting a shorter interval for this property reduces the time between the expiration of a timer associated with a workflow instance and the signaling of the event and subsequent loading of the instance.</span></span> <span data-ttu-id="c9295-106">但是，这同时也会增大主机上的处理负载，在很少采用持久性计时器和/或很少发生主机故障的情况下，您可能不希望采用此类设置。</span><span class="sxs-lookup"><span data-stu-id="c9295-106">However, it also increases the processing load on a host and may not be desirable in scenarios where durable timers and/or host failures are rare.</span></span> <span data-ttu-id="c9295-107">该属性的类型为 TimeSpan，其值遵循以下格式：hh:mm:ss。</span><span class="sxs-lookup"><span data-stu-id="c9295-107">The type of the property is TimeSpan and the value of the property follows the format: hh:mm:ss.</span></span> <span data-ttu-id="c9295-108">该属性的最小值为 00:00:01，</span><span class="sxs-lookup"><span data-stu-id="c9295-108">The minimum value for this property is 00:00:01.</span></span> <span data-ttu-id="c9295-109">默认值为 00:00:05。</span><span class="sxs-lookup"><span data-stu-id="c9295-109">The default value for the property is 00:00:05.</span></span>  
  
 <span data-ttu-id="c9295-110">有关详细信息检测和激活可运行且可激活的工作流实例，请参阅[实例激活](instance-activation.md)。</span><span class="sxs-lookup"><span data-stu-id="c9295-110">For more information detecting and activating runnable and activatable workflow instances, see [Instance Activation](instance-activation.md).</span></span>
