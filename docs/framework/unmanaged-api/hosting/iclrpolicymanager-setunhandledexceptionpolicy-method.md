---
title: "ICLRPolicyManager::SetUnhandledExceptionPolicy 方法"
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
- ICLRPolicyManager.SetUnhandledExceptionPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy
helpviewer_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy method [.NET Framework hosting]
- SetUnhandledExceptionPolicy method [.NET Framework hosting]
ms.assetid: 5268480e-280a-4931-b7a3-dc3ffdf7f78f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9ad287fedbc06768dd683c254292e0c28760d59a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrpolicymanagersetunhandledexceptionpolicy-method"></a>ICLRPolicyManager::SetUnhandledExceptionPolicy 方法
发生未处理的异常时，请指定公共语言运行时 (CLR) 的行为。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetUnhandledExceptionPolicy (  
    [in] EClrUnhandledExceptionPolicy policy  
);  
```  
  
#### <a name="parameters"></a>参数  
 `policy`  
 [in]之一[EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) ，该值指示是否通过 CLR 或主机设置行为的值。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`SetUnhandledExceptionPolicy`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用操作已超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|事件已被取消时被阻塞的线程，或者纤程正在等待它。|  
|E_FAIL|出现未知的灾难性故障。 方法返回 E_FAIL 后，CLR 不再进程内中使用。 到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
  
## <a name="remarks"></a>备注  
 默认情况下，CLR 的最后一个处理程序所有未经处理的异常，并且其默认行为是关闭进程。 主机可以更改此行为，通过设置`policy`eHostDeterminedPolicy 的值。 此值允许宿主实现其自己的默认行为，与早期版本的 CLR。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [EClrUnhandledException 枚举](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md)  
 [ICLRControl 接口](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [ICLRPolicyManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [IHostPolicyManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
