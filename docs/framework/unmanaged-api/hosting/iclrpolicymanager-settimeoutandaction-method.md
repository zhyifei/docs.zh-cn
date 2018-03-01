---
title: "ICLRPolicyManager::SetTimeoutAndAction 方法"
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
- ICLRPolicyManager.SetTimeoutAndAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeoutAndAction
helpviewer_keywords:
- ICLRPolicyManager::SetTimeoutAndAction method [.NET Framework hosting]
- SetTimeoutAndAction method [.NET Framework hosting]
ms.assetid: 60454f91-d855-4ddf-bb6d-60a02f5eabab
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b67150b7544f1d8d25532c564800404b634cae99
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrpolicymanagersettimeoutandaction-method"></a>ICLRPolicyManager::SetTimeoutAndAction 方法
设置一个超时值对于指定的操作，并指定该操作发生时，应执行公共语言运行时 (CLR) 的策略操作。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetTimeoutAndAction (  
    [in] EClrOperation operation,  
    [in] DWORD dwMilliseconds,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a>参数  
 `operation`  
 [in]之一[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)值，指示为其设置的超时和策略操作`action`。 支持以下值：  
  
-   OPR_AppDomainUnload  
  
-   OPR_ProcessExit  
  
-   OPR_ThreadRudeAbortInCriticalRegion  
  
-   OPR_ThreadRudeAbortInNonCriticalRegion  
  
 `dwMilliseconds`  
 [in]新超时值，以毫秒为单位。 值为无限原因`operation`永远不会到超时。  
  
 `action`  
 [in]之一[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)值，指示 CLR 应执行时指定的策略操作`operation`时发生。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`SetTimeoutAndAction`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用操作已超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|事件已被取消时被阻塞的线程，或者纤程正在等待它。|  
|E_FAIL|出现未知的灾难性故障。 方法返回 E_FAIL 后，CLR 不再进程内中使用。 到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
|E_INVALIDARG|超时不能设置为指定`operation`，或为提供的无效值`action`。|  
  
## <a name="remarks"></a>备注  
 `SetTimeoutAndAction`封装的功能[iclrpolicymanager:: Settimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)和[iclrpolicymanager:: Setactionontimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)方法，并可以替代这两种方法对的顺序调用调用。  
  
> [!IMPORTANT]
>  并非所有策略操作值可以都指定为 CLR 操作的超时行为。 请参阅有关有效值的这两种方法的主题的备注部分。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [EClrOperation 枚举](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [EPolicyAction 枚举](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [ICLRPolicyManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [SetActionOnTimeout 方法](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)  
 [Iclrpolicymanager:: Settimeoutandaction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)
