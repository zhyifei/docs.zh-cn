---
title: "ICLRTask 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask
helpviewer_keywords: ICLRTask interface [.NET Framework hosting]
ms.assetid: b3a44df3-578a-4451-b55e-70c8e7695f5e
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 17c8f798b3c9d6c135bff11cd909fd74d8c9a697
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtask-interface"></a>ICLRTask 接口
提供允许宿主发出请求的公共语言运行时 (CLR)，或者向 CLR 有关关联的任务提供通知的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Abort 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask-abort-method.md)|CLR 中止任务的请求的当前`ICLRTask`实例表示。|  
|[ExitTask 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md)|通知与当前关联的任务的 CLR`ICLRTask`实例即将结束，并尝试正常关闭的任务。|  
|[GetMemStats 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md)|获取表示由当前的任务上使用的内存资源的统计信息`ICLRTask`实例。|  
|[LocksHeld 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask-locksheld-method.md)|获取当前在任务上所持有的锁数。|  
|[NeedsPriorityScheduling 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask-needspriorityscheduling-method.md)|获取一个值，该值指示主机是否应将高优先级分配给重新安排表示由当前的任务`ICLRTask`实例。|  
|[Reset 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask-reset-method.md)|主机已完成一个任务，并使 CLR 重用当前通知 CLR`ICLRTask`实例来表示另一个任务。|  
|[RudeAbort 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask-rudeabort-method.md)|会导致 CLR 中止表示由当前的任务`ICLRTask`实例立即，而无需保证将执行终结器。|  
|[SetTaskIdentifier 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md)|设置为表示由当前的任务的唯一标识符`ICLRTask`实例，用于调试。|  
|[SwitchIn 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchin-method.md)|通知当前所表示任务的 CLR`ICLRTask`实例处于可操作状态。|  
|[SwitchOut 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)|通知当前所表示任务的 CLR`ICLRTask`实例不再处于可操作状态。|  
|[YieldTask 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask-yieldtask-method.md)|请求 CLR 分配处理器时间可供其他任务。 CLR 不保证该任务将被放在它可以产生处理时间的状态。|  
  
## <a name="remarks"></a>备注  
 `ICLRTask`是 CLR 任务的表示形式。 在代码执行过程的任意位置，可以描述一项任务以运行或等待运行的形式。 宿主调用`ICLRTask::SwitchIn`方法来通知 CLR 的任务的当前`ICLRTask`实例所表示现处于可操作状态。 调用了`ICLRTask::SwitchIn`，主机可以在其中运行时需要多个线程关联，通过调用指定的情况下除外安排任何操作系统线程，任务[ihosttaskmanager:: Beginthreadaffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)和[Ihosttaskmanager:: Endthreadaffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)方法。 一段时间后，系统可能会决定从线程中删除任务并将它放在非运行状态。 例如，这可能会发生时任务上同步基元，阻塞，或等待 I/O 操作完成。 宿主调用[SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)通知由当前所表示任务的 CLR`ICLRTask`实例不再处于可操作状态。  
  
 任务通常在执行代码的末尾终止。 此时，主机将调用`ICLRTask::ExitTask`销毁关联`ICLRTask`。 但是，任务还都可以通过调用回收`ICLRTask::Reset`，这样，`ICLRTask`要再次使用实例。 此方法可避免重复创建和销毁实例的开销。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICLRTaskManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask 接口](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [IHostTaskManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [ICLRTask2 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
