---
title: ICLRDebugManager::SetConnectionTasks 方法
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.SetConnectionTasks
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::SetConnectionTasks
helpviewer_keywords:
- SetConnectionTasks method [.NET Framework hosting]
- ICLRDebugManager::SetConnectionTasks method [.NET Framework hosting]
ms.assetid: b38bbc9a-872c-41a9-b8c3-ca011d25456a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85db4247ebe4a488f7907e195bb0f25f72d87e9b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951354"
---
# <a name="iclrdebugmanagersetconnectiontasks-method"></a>ICLRDebugManager::SetConnectionTasks 方法
将[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例列表与标识符和友好名称关联。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetConnectionTasks (  
    [in] CONNID id,  
    [in] DWORD dwCount,  
    [in, size_is(dwCount)] ICLRTask **ppCLRTask  
);  
```  
  
## <a name="parameters"></a>参数  
 `id`  
 中要与`ppCLRTask`数组关联的连接的主机特定标识符。  
  
 `dwCount`  
 中的成员`ppCLRTask`数。 此数字必须大于零。  
  
 `ppCLRTask`  
 中`ICLRTask` 与`id`标识的连接关联的指针数组。 此数组必须至少包含一个成员。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`SetConnectionTasks`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时 (CLR) 未加载到进程中, 或 CLR 处于无法运行托管代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|已阻止的线程或纤程正在等待某个事件时, 该事件被取消。|  
|E_FAIL|发生未知的灾难性故障。 方法返回 E_FAIL 后, CLR 在该进程内将不再可用。 对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
|E_INVALIDARG|尚未使用的`id` `id` `ppCLRTask`此值调用[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) , 或者或为零,或的一个元素为空。`dwCount`|  
  
## <a name="remarks"></a>备注  
 [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)提供了三种`BeginConnection`方法`SetConnectionTasks`:、和[EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), 用于将任务列表与标识符和友好名称关联起来。  
  
> [!IMPORTANT]
> 对于每组任务, 这三种方法都必须按特定的顺序进行调用。 `BeginConnection`首先调用以建立新连接。 `SetConnectionTasks`在旁边调用, 提供要与该连接相关联的一组任务。 `EndConnection`最后调用, 以删除任务列表与标识符和友好名称之间的关联。但是, 可以嵌套不同连接的调用。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **类库**作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICLRControl 接口](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [ICLRDebugManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [BeginConnection 方法](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)
- [EndConnection 方法](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)
- [IHostControl 接口](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
