---
title: "ICLRDebugManager::EndConnection 方法"
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
- ICLRDebugManager.EndConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::EndConnection
helpviewer_keywords:
- ICLRDebugManager::EndConnection method [.NET Framework hosting]
- EndConnection method [.NET Framework hosting]
ms.assetid: 89dc7363-2f29-4eb2-8f23-fccdda6a76a6
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 210226b697eb3dffe574bd842ca31e83948891a4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebugmanagerendconnection-method"></a>ICLRDebugManager::EndConnection 方法
删除的任务列表和标识符和友好名称之间的关联。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwConnectionId`  
 [in]连接和关联的公共语言运行时 (CLR) 任务列表的特定于宿主的标识符。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`EndConnection`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用操作已超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|事件已被取消时被阻塞的线程，或者纤程正在等待它。|  
|E_FAIL|出现未知的灾难性故障。 方法返回 E_FAIL 后，CLR 不再进程内中使用。 到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
|E_INVALIDARG|[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)永远不会使用调用`dwConnectionId`，或`dwConnectionId`为零。|  
  
## <a name="remarks"></a>备注  
 [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)提供三种方法， `BeginConnection`， [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)，和`EndConnection`，将任务列表标识符和友好名称与相关联。  
  
> [!IMPORTANT]
>  必须按特定顺序为每一组任务调用这三种方法。 `BeginConnection`都会首先调用来建立新连接。 `SetConnectionTasks`调用下一步可提供的任务与该连接关联集。 `EndConnection`调用上一次可删除任务列表的标识符和友好名称之间的关联。但是，可以嵌套不同连接的调用。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICLRControl 接口](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [ICLRDebugManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [BeginConnection 方法](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)  
 [SetConnectionTasks 方法](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)  
 [IHostControl 接口](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
