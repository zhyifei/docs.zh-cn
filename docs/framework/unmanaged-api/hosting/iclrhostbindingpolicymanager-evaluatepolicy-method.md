---
title: "ICLRHostBindingPolicyManager::EvaluatePolicy 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRHostBindingPolicyManager.EvaluatePolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRHostBindingPolicyManager::EvaluatePolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy method [.NET Framework hosting]
- EvaluatePolicy method [.NET Framework hosting]
ms.assetid: 3a3a9446-7a4e-4836-9b27-5c536c15993d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 14f4db56529fbbb08f8f3d9adde0d4dc7a8ce045
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a>ICLRHostBindingPolicyManager::EvaluatePolicy 方法
代表主机的计算结果绑定策略。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT EvaluatePolicy (  
    [in] LPCWSTR     pwzReferenceIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [out, size_is(*pcchPostPolicyReferenceIdentity)] LPWSTR pwzPostPolicyReferenceIdentity,  
    [in, out] DWORD *pcchPostPolicyReferenceIdentity,  
    [out] DWORD     *pdwPoliciesApplied  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pwzReferenceIdentity`  
 [in]对策略评估前的程序集的引用。  
  
 `pbApplicationPolicy`  
 [in]指向包含策略数据的缓冲区的指针。  
  
 `cbAppPolicySize`  
 [in]大小`pbApplicationPolicy`缓冲区。  
  
 `pwzPostPolicyReferenceIdentity`  
 [out]对新的策略数据的计算后的程序集的引用。  
  
 `pcchPostPolicyReferenceIdentity`  
 [在中，out]指向新的策略数据的计算后的程序集标识引用缓冲区大小的指针。  
  
 `pdwPoliciesApplied`  
 [out]逻辑或组合的指针[EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md)值，指示已应用哪些策略。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|计算已成功完成。|  
|E_INVALIDARG|请`pwzReferenceIdentity`或`pbApplicationPolicy`为空引用。|  
|ERROR_INSUFFICIENT_BUFFER|`cbAppPolicySize`对于太小。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用操作已超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|事件已被取消时被阻塞的线程，或者纤程正在等待它。|  
|E_FAIL|出现未知的灾难性故障。 方法返回 E_FAIL 后，CLR 不再进程内中使用。 到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
  
## <a name="remarks"></a>备注  
 `EvaluatePolicy`方法允许宿主影响绑定策略，以维持特定于宿主的程序集版本控制要求。 策略引擎本身仍保留在 CLR 内。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICLRHostBindingPolicyManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
