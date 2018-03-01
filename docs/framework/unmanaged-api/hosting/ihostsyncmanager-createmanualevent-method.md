---
title: "IHostSyncManager::CreateManualEvent 方法"
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
- IHostSyncManager.CreateManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateManualEvent
helpviewer_keywords:
- CreateManualEvent method [.NET Framework hosting]
- IHostSyncManager::CreateManualEvent method [.NET Framework hosting]
ms.assetid: 68661fbd-09cf-46dc-890b-e694f8a3880a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 347eaa64b8a5e5b5c9494a779e3d583b10d80052
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a>IHostSyncManager::CreateManualEvent 方法
创建手动重置事件对象。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a>参数  
 `bInitialState`  
 [in]`true`、 的对象是否终止; 否则为`false`。  
  
 `ppEvent`  
 [out]指向的地址的指针[IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)实例，或如果无法创建事件为 null。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`CreateManualEvent`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用操作已超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|事件已被取消时被阻塞的线程，或者纤程正在等待它。|  
|E_FAIL|出现未知的灾难性故障。 如果某方法返回 E_FAIL，CLR 不再可用进程内。 到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
|E_OUTOFMEMORY|没有足够的内存已可用于创建请求的事件对象。|  
  
## <a name="remarks"></a>备注  
 `CreateManualEvent`创建`IHostManualEvent`，需要调用手动重置事件对象[ihostmanualevent:: Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)方法以将其设置为非终止状态。 `CreateManualEvent`镜像 Win32`CreateEvent`函数中使用的值`true`指定的`bManualReset`参数。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICLRSyncManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [IHostManualEvent 接口](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [IHostSyncManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
