---
title: "ICLRDebugManager::IsDebuggerAttached 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager.IsDebuggerAttached
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager::IsDebuggerAttached
helpviewer_keywords:
- IsDebuggerAttached method, ICLRDebugManager interface [.NET Framework hosting]
- ICLRDebugManager::IsDebuggerAttached method [.NET Framework hosting]
ms.assetid: 2f105fe0-f52d-49c5-bda5-583fb27e3aa6
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 986c9ab7853324d1a2f0fc104399141068ae9a09
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebugmanagerisdebuggerattached-method"></a>ICLRDebugManager::IsDebuggerAttached 方法
获取一个值，它指示调试器是否已附加到进程。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pbAttached`  
 [out]`true`如果调试程序附加到进程; 否则为`false`。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`IsDebuggerAttached`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用操作已超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|事件已被取消时被阻塞的线程，或者纤程正在等待它。|  
|E_FAIL|出现未知的灾难性故障。 方法返回 E_FAIL 后，CLR 不再进程内中使用。 到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
  
## <a name="remarks"></a>备注  
 `IsDebuggerAttached`允许宿主查询 CLR，以确定是否将调试器附加到进程。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICLRControl 接口](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [ICLRDebugManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [IHostControl 接口](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
