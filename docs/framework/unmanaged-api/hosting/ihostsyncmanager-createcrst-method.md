---
title: IHostSyncManager::CreateCrst 方法
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateCrst
helpviewer_keywords:
- CreateCrst method [.NET Framework hosting]
- IHostSyncManager::CreateCrst method [.NET Framework hosting]
ms.assetid: ac278cc8-2540-4a6c-b5c6-b90c3970b4f4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 101a652aa77e587003fb7e773e00ba9b77461a06
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441888"
---
# <a name="ihostsyncmanagercreatecrst-method"></a>IHostSyncManager::CreateCrst 方法
创建同步的关键部分对象。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CreateCrst (  
    [out] IHostCrst** ppCrst  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppCrst`  
 [out]指向的地址的指针[IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)实例实现的主机，或者，如果无法创建关键部分。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`CreateCrst` 已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用操作已超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|事件已被取消时被阻塞的线程，或者纤程正在等待它。|  
|E_FAIL|出现未知的灾难性故障。 如果某方法返回 E_FAIL，CLR 不再可用进程内。 到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
|E_OUTOFMEMORY|没有足够的内存已可用于创建请求的关键部分。|  
  
## <a name="remarks"></a>备注  
 关键部分对象提供类似于所提供的 mutex 对象、 同步，只不过可以仅由单一进程的线程使用临界区。 `CreateCrst` 镜像 Win32`InitializeCriticalSection`函数。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** 作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICLRSyncManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [IHostCrst 接口](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [IHostSyncManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [IHostSemaphore 接口](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [Mutex](../../../../docs/standard/threading/mutexes.md)  
 [Semaphore 和 SemaphoreSlim](../../../../docs/standard/threading/semaphore-and-semaphoreslim.md)
