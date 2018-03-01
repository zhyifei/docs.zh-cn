---
title: "IHostSyncManager 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager
helpviewer_keywords:
- IHostSyncManager interface [.NET Framework hosting]
ms.assetid: 2e081a37-6a28-4c93-b7ab-1c96a464637c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b51e1dd9219c30eb4918bf1e331c96585f7c03ac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsyncmanager-interface"></a>IHostSyncManager 接口
提供允许公共语言运行时 (CLR) 以通过调用而不是使用 Win32 同步函数主机创建同步基元的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[CreateAutoEvent 方法](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|创建一个自动重置事件对象。|  
|[CreateCrst 方法](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|创建同步的关键部分对象。|  
|[CreateCrstWithSpinCount 方法](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|创建具有同步的重试次数的关键部分对象。|  
|[CreateManualEvent 方法](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|创建手动重置事件对象。|  
|[CreateMonitorEvent 方法](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|创建监视的自动重置事件对象。|  
|[CreateRWLockReaderEvent 方法](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|为创建一个手动重置事件对象将读线程锁的实现。|  
|[CreateRWLockWriterEvent 方法](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|创建用于实现的编写器锁的自动重置事件对象。|  
|[CreateSemaphore 方法](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|创建[IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) CLR 用作等待事件信号量的对象。|  
|[SetCLRSyncManager 方法](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|集[ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)实例要与当前关联`IHostSyncManager`实例。|  
  
## <a name="remarks"></a>备注  
 CLR 发现主机的实现`IHostSyncManager`通过调用[ihostcontrol:: Gethostmanager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)方法替换`IID`IID_IHostSyncManager。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICLRSyncManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
