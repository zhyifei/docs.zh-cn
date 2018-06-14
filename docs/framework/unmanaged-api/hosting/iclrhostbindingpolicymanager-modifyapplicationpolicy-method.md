---
title: ICLRHostBindingPolicyManager::ModifyApplicationPolicy 方法
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.ModifyApplicationPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy method [.NET Framework hosting]
- ModifyApplicationPolicy method [.NET Framework hosting]
ms.assetid: d82d633e-cce6-427c-8b02-8227e34e12ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a221b286ada97c3c03387556cb30ee6ddd2c453
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436249"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a>ICLRHostBindingPolicyManager::ModifyApplicationPolicy 方法
修改指定的程序集绑定策略，并创建新版本的策略。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT  ModifyApplicationPolicy (  
    [in] LPCWSTR     pwzSourceAssemblyIdentity,   
    [in] LPCWSTR     pwzTargetAssemblyIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [in] DWORD       dwPolicyModifyFlags,  
    [out, size_is(*pcbNewAppPolicySize)] BYTE *pbNewApplicationPolicy,   
    [in, out] DWORD *pcbNewAppPolicySize  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pwzSourceAssemblyIdentity`  
 [in]要修改的程序集标识。  
  
 `pwzTargetAssemblyIdentity`  
 [in]修改后的程序集的新标识。  
  
 `pbApplicationPolicy`  
 [in]指向包含要修改的程序集绑定策略数据的缓冲区的指针。  
  
 `cbAppPolicySize`  
 [in]要替换的绑定策略的大小。  
  
 `dwPolicyModifyFlags`  
 [in]逻辑或组合[EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md)值，表明控制的重定向。  
  
 `pbNewApplicationPolicy`  
 [out]指向包含新的绑定策略数据的缓冲区的指针。  
  
 `pcbNewAppPolicySize`  
 [在中，out]指向新的绑定策略缓冲区的大小的指针。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|已成功修改策略。|  
|E_INVALIDARG|`pwzSourceAssemblyIdentity` 或`pwzTargetAssemblyIdentity`是 null 引用。|  
|ERROR_INSUFFICIENT_BUFFER|`pbNewApplicationPolicy` 对于太小。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用操作已超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|事件已被取消时被阻塞的线程，或者纤程正在等待它。|  
|E_FAIL|出现未知的灾难性故障。 方法返回 E_FAIL 后，CLR 不再进程内中使用。 到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
  
## <a name="remarks"></a>备注  
 `ModifyApplicationPolicy`两次调用方法。 第一次调用应提供的 null 值`pbNewApplicationPolicy`参数。 此调用将返回包含必需的值的`pcbNewAppPolicySize`。 第二个调用应提供此值`pcbNewAppPolicySize`，并指向该大小的缓冲区`pbNewApplicationPolicy`。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** 作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICLRHostBindingPolicyManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
