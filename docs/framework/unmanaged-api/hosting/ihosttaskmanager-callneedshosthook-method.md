---
title: IHostTaskManager::CallNeedsHostHook 方法
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CallNeedsHostHook
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CallNeedsHostHook
helpviewer_keywords:
- CallNeedsHostHook method [.NET Framework hosting]
- IHostTaskManager::CallNeedsHostHook method [.NET Framework hosting]
ms.assetid: b60f1f59-9825-4b57-961f-d2979518e6a7
topic_type:
- apiref
ms.openlocfilehash: 8b8b8521a09fa54a105e8263a471ab0467fb6ccc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176287"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a>IHostTaskManager::CallNeedsHostHook 方法
使主机能够指定通用语言运行时 （CLR） 是否可以将指定的调用内联到非托管函数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a>parameters  
 `target`  
 [在]要调用的非托管函数的映射的可移植可执行 （PE） 文件中的地址。  
  
 `pbCallNeedsHostHook`  
 [出]指向布尔值的指针，指示主机是否需要挂接调用。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|说明|  
|-------------|-----------------|  
|S_OK|`CallNeedsHostHook`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|CLR 尚未加载到进程中，或者 CLR 处于无法成功运行托管代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|呼叫超时。|  
|HOST_E_NOT_OWNER|调用方不拥有锁。|  
|HOST_E_ABANDONED|当阻塞的线程或光纤等待事件时，事件已被取消。|  
|E_FAIL|发生了未知的灾难性故障。 当方法返回E_FAIL时，CLR 在进程中不再可用。 对托管方法的后续调用返回HOST_E_CLRNOTAVAILABLE。|  
  
## <a name="remarks"></a>备注  
 为了帮助优化代码执行，CLR 在编译期间对每个平台调用调用执行分析，以确定调用是否可以内联。 `CallNeedsHostHook`使主机通过要求对非托管函数的调用进行挂接来覆盖该决策。 如果主机需要挂钩，则运行时不会内联呼叫。  
  
 主机通常需要一个挂钩，它必须调整浮点状态，或在收到通知时，呼叫正在进入一个状态，其中主机无法跟踪运行时的内存请求或获取的任何锁。 当主机要求挂接调用时，运行时通过使用对[EnterRuntime、](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)[离开运行时](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)、[反向EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)和[反向LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)的调用来通知主机与托管代码转换。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** MSCorEE.h  
  
 **库：** 作为资源包含在 MSCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICLRTask 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask 接口](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
