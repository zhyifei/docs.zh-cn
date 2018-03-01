---
title: "IHostCrst::SetSpinCount 方法"
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
- IHostCrst.SetSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::SetSpinCount
helpviewer_keywords:
- IHostCrst::SetSpinCount method [.NET Framework hosting]
- SetSpinCount method [.NET Framework hosting]
ms.assetid: 863fc8ce-9b8a-477e-8dd8-75c8544bb43a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 76a3091102a43d17f543010be0c505157d593d2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostcrstsetspincount-method"></a>IHostCrst::SetSpinCount 方法
设置当前的旋转计数[IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)实例。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwSpinCount`  
 [in]当前的新旋转计数`IHostCrst`实例。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`SetSpinCount`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用操作已超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|事件已被取消时被阻塞的线程，或者纤程正在等待它。|  
|E_FAIL|出现未知的灾难性故障。 如果某方法返回 E_FAIL，CLR 不再可用进程内。 到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
  
## <a name="remarks"></a>备注  
 在多处理器系统中，如果由当前的临界区表示`IHostCrst`实例不可用，则调用线程旋转`dwSpinCount`在调用之前的时间[ihostsemaphore:: Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md)上关联的信号量与关键部分。 如果数值调节钮操作期间，临界区变得可用，调用线程可避免等待操作。  
  
 使用情况`dwSpinCount`等同于 Win32 中的相同名称的参数的使用情况`InitializeCriticalSectionAndSpinCount`函数。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICLRSyncManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [IHostCrst 接口](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [IHostSyncManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
