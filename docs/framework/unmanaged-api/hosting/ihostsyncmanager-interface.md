---
title: IHostSyncManager 接口
ms.date: 03/30/2017
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
ms.openlocfilehash: 02a59b8ef63f7e866e419db4e3232da7eec19558
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132633"
---
# <a name="ihostsyncmanager-interface"></a>IHostSyncManager 接口
提供一些方法，使公共语言运行时（CLR）可以通过调用主机而不是使用 Win32 同步函数来创建同步基元。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[CreateAutoEvent 方法](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|创建自动重置事件对象。|  
|[CreateCrst 方法](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|创建用于同步的临界区对象。|  
|[CreateCrstWithSpinCount 方法](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|使用自旋计数为同步创建一个临界区对象。|  
|[CreateManualEvent 方法](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|创建手动重置的事件对象。|  
|[CreateMonitorEvent 方法](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|创建监视的自动重置事件对象。|  
|[CreateRWLockReaderEvent 方法](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|创建手动重置的事件对象，以便实现读取器锁。|  
|[CreateRWLockWriterEvent 方法](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|创建自动重置事件对象，以便实现编写器锁。|  
|[CreateSemaphore 方法](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|为 CLR 创建一个[IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)对象，以用作等待事件的信号量。|  
|[SetCLRSyncManager 方法](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|设置要与当前 `IHostSyncManager` 实例关联的[ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)实例。|  
  
## <a name="remarks"></a>备注  
 CLR 通过使用 `IID` IID_IHostSyncManager 调用[IHostControl：： GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)方法来发现主机的 `IHostSyncManager` 实现。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICLRSyncManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
