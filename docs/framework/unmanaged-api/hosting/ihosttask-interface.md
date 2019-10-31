---
title: IHostTask 接口
ms.date: 03/30/2017
api_name:
- IHostTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask
helpviewer_keywords:
- IHostTask interface [.NET Framework hosting]
ms.assetid: a71dbbd5-64b8-47eb-9f03-8e8c85fbe2bc
topic_type:
- apiref
ms.openlocfilehash: 18dfee606f3d41229aa58a5b4bb9380b87c4efa5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121391"
---
# <a name="ihosttask-interface"></a>IHostTask 接口
提供允许公共语言运行时（CLR）与宿主通信以管理任务的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Alert 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|请求宿主唤醒当前 `IHostTask` 实例表示的任务，以便可以中止任务。|  
|[GetPriority 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|获取当前 `IHostTask` 实例所表示的任务的线程优先级别。|  
|[Join 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|阻止调用任务，直到当前 `IHostTask` 实例表示的任务完成、已超过指定的时间间隔或调用[IHostTask：： Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) 。|  
|[SetCLRTask 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|将[ICLRTask 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例与当前 `IHostTask` 实例相关联。|  
|[SetPriority 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|请求宿主调整当前 `IHostTask` 实例所表示的任务的线程优先级别。|  
|[Start 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|请求宿主将当前 `IHostTask` 实例表示的任务从挂起状态移动到实时状态，在此状态下可以执行代码。|  
  
## <a name="remarks"></a>备注  
 CLR 调用 `IHostTask` 定义的方法来启动任务、设置其线程优先级别，等等。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICLRTask 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTaskManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
