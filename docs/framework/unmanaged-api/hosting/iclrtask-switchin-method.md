---
title: "ICLRTask::SwitchIn 方法"
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
- ICLRTask.SwitchIn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchIn
helpviewer_keywords:
- ICLRTask::SwitchIn method [.NET Framework hosting]
- SwitchIn method [.NET Framework hosting]
ms.assetid: 3d37ce20-aa65-4043-8f13-7c728b5d8a52
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e99fc43dea70d456bbaab9bba63e5a018e9e9201
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskswitchin-method"></a>ICLRTask::SwitchIn 方法
通知公共语言运行时 (CLR)，该任务的当前[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例所表示现处于可操作状态。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
#### <a name="parameters"></a>参数  
 `threadHandle`  
 [in]在其由当前的所表示任务的物理线程的句柄`ICLRTask`实例正在执行。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`SwitchIn`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用操作已超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|事件已被取消时被阻塞的线程，或者纤程正在等待它。|  
|E_FAIL|出现未知的灾难性故障。 如果某方法返回 E_FAIL，CLR 不再可用进程内。 到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
|HOST_E_INVALIDOPERATION|`SwitchIn`已调用以前调用[SwitchOut 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)。|  
  
## <a name="remarks"></a>备注  
 `threadHandle`参数表示在其由当前的所表示任务的操作系统线程的句柄`ICLRTask`计划实例。 如果该线程上已发生模拟，则必须调用[ihostsecuritymanager:: Reverttoself](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)之前在任务中切换。  
  
> [!NOTE]
>  调用`SwitchIn`而无需以前调用`SwitchOut`失败，出现 HOST_E_INVALIDOPERATION 的 HRESULT 值。  
  
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
