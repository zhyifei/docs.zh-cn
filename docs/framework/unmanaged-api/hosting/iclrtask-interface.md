---
title: ICLRTask 接口
ms.date: 03/30/2017
api_name:
- ICLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask
helpviewer_keywords:
- ICLRTask interface [.NET Framework hosting]
ms.assetid: b3a44df3-578a-4451-b55e-70c8e7695f5e
topic_type:
- apiref
ms.openlocfilehash: c4f27a73022b0495b2772c0485c14a1b007dc883
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132646"
---
# <a name="iclrtask-interface"></a>ICLRTask 接口
提供允许宿主向公共语言运行时（CLR）发出请求，或向 CLR 提供有关关联任务的通知的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Abort 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask-abort-method.md)|请求 CLR 中止当前 `ICLRTask` 实例表示的任务。|  
|[ExitTask 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md)|通知 CLR 与当前 `ICLRTask` 实例关联的任务正在结束，并尝试正常关闭任务。|  
|[GetMemStats 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md)|获取有关当前 `ICLRTask` 实例所表示的任务使用内存资源的统计信息。|  
|[LocksHeld 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask-locksheld-method.md)|获取任务当前持有的锁的数目。|  
|[NeedsPriorityScheduling 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask-needspriorityscheduling-method.md)|获取一个值，该值指示宿主是否应分配高优先级来重新安排当前 `ICLRTask` 实例所表示的任务。|  
|[Reset 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask-reset-method.md)|通知 CLR 宿主已经完成了一个任务，并使 CLR 能够重复使用当前 `ICLRTask` 实例来表示其他任务。|  
|[RudeAbort 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask-rudeabort-method.md)|使 CLR 立即中止当前 `ICLRTask` 实例表示的任务，而不保证将执行终结器。|  
|[SetTaskIdentifier 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md)|为当前 `ICLRTask` 实例所表示的任务设置唯一标识符，以便在调试时使用。|  
|[SwitchIn 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchin-method.md)|向 CLR 通知当前 `ICLRTask` 实例表示的任务处于可使用状态。|  
|[SwitchOut 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)|通知 CLR 当前 `ICLRTask` 实例表示的任务不再处于可使用状态。|  
|[YieldTask 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask-yieldtask-method.md)|请求 CLR 使处理器时间可供其他任务使用。 CLR 不保证任务将处于可产生处理时间的状态。|  
  
## <a name="remarks"></a>备注  
 `ICLRTask` 是 CLR 任务的表示形式。 在代码执行过程中的任意时刻，都可以将任务描述为正在运行或等待运行。 宿主调用 `ICLRTask::SwitchIn` 方法，通知 CLR 当前 `ICLRTask` 实例表示的任务现在处于可调用状态。 调用 `ICLRTask::SwitchIn`之后，主机可以在任何操作系统线程上计划任务，但运行时需要线程关联的情况除外，如[IHostTaskManager：： BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)和[IHostTaskManager：：EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)方法。 稍后，操作系统可能决定从线程中删除任务并将其置于非运行状态。 例如，每当任务阻止同步基元或等待 i/o 操作完成时，就会发生这种情况。 主机调用[SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)来通知 CLR 当前 `ICLRTask` 实例表示的任务不再处于可使用状态。  
  
 任务通常在代码执行结束时终止。 当时，主机调用 `ICLRTask::ExitTask` 来销毁关联的 `ICLRTask`。 但是，还可以使用对 `ICLRTask::Reset`的调用来回收任务，这样就可以再次使用 `ICLRTask` 实例。 此方法可防止重复创建和销毁实例的系统开销。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICLRTaskManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask 接口](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [ICLRTask2 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
