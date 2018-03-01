---
title: "IHostTaskManager::LeaveRuntime 方法"
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
- IHostTaskManager.LeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::LeaveRuntime
helpviewer_keywords:
- IHostTaskManager::LeaveRuntime method [.NET Framework hosting]
- LeaveRuntime method [.NET Framework hosting]
ms.assetid: 43689cc4-e48e-46e5-a22d-bafd768b8759
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a4c168cffba44a21d6705e8abd921ecbf8a9da6b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagerleaveruntime-method"></a>IHostTaskManager::LeaveRuntime 方法
通知主机当前正在执行的任务来保持公共语言运行时 (CLR)，然后输入非托管的代码。  
  
> [!IMPORTANT]
>  相应地调用[ihosttaskmanager:: Enterruntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)通知主机当前正在执行的任务重新进入托管的代码。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
#### <a name="parameters"></a>参数  
 `target`  
 [in]要调用的非托管函数的映射可移植可执行文件内的地址。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`LeaveRuntime`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用操作已超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|事件已被取消时被阻塞的线程，或者纤程正在等待它。|  
|E_FAIL|出现未知的灾难性故障。 如果某方法返回 E_FAIL，CLR 不再可用进程内。 到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
|E_OUTOFMEMORY|没有足够的内存是可用于完成所请求的分配。|  
  
## <a name="remarks"></a>备注  
 可以嵌套到和从非托管代码的调用序列。 例如，下面的列表描述的假设的情况下，在其中对的调用序列`LeaveRuntime`， [ihosttaskmanager:: Reverseenterruntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)， [ihosttaskmanager:: Reverseleaveruntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)，和`IHostTaskManager::EnterRuntime`允许宿主确定嵌套的层。  
  
|操作|相应的方法调用|  
|------------|-------------------------------|  
|托管的 Visual Basic 可执行文件调用在 C 中编写通过使用平台非托管的函数调用。|`IHostTaskManager::LeaveRuntime`|  
|非托管的 C 函数在 C# 中编写的托管 DLL 中调用的方法。|`IHostTaskManager::ReverseEnterRuntime`|  
|托管的 C# 函数调用在 C 中编写的其他非托管的函数，还使用平台调用。|`IHostTaskManager::LeaveRuntime`|  
|第二个非托管的函数将执行返回给 C# 函数。|`IHostTaskManager::EnterRuntime`|  
|C# 函数将执行返回给第一个非托管函数。|`IHostTaskManager::ReverseLeaveRuntime`|  
|第一个非托管的函数将执行返回到 Visual Basic 程序。|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICLRTask 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [ICLRTaskManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask 接口](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [IHostTaskManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
