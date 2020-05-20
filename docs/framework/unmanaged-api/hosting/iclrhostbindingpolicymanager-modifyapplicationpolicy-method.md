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
ms.openlocfilehash: e32714bba2403752f1ac2551ab182f2655f1fa75
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703852"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a>ICLRHostBindingPolicyManager::ModifyApplicationPolicy 方法
修改指定程序集的绑定策略，并创建该策略的新版本。  
  
## <a name="syntax"></a>语法  
  
```cpp  
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
  
## <a name="parameters"></a>参数  
 `pwzSourceAssemblyIdentity`  
 中要修改的程序集的标识。  
  
 `pwzTargetAssemblyIdentity`  
 中已修改的程序集的新标识。  
  
 `pbApplicationPolicy`  
 中指向包含要修改的程序集的绑定策略数据的缓冲区的指针。  
  
 `cbAppPolicySize`  
 中要替换的绑定策略的大小。  
  
 `dwPolicyModifyFlags`  
 中[EHostBindingPolicyModifyFlags](ehostbindingpolicymodifyflags-enumeration.md)值的逻辑或组合，指示对重定向的控制。  
  
 `pbNewApplicationPolicy`  
 弄指向包含新绑定策略数据的缓冲区的指针。  
  
 `pcbNewAppPolicySize`  
 [in，out]指向新绑定策略缓冲区的大小的指针。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|说明|  
|-------------|-----------------|  
|S_OK|已成功修改策略。|  
|E_INVALIDARG|`pwzSourceAssemblyIdentity`或为 `pwzTargetAssemblyIdentity` 空引用。|  
|ERROR_INSUFFICIENT_BUFFER|`pbNewApplicationPolicy` 太小。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|已阻止的线程或纤程正在等待某个事件时，该事件被取消。|  
|E_FAIL|发生未知的灾难性故障。 方法返回 E_FAIL 后，CLR 在该进程内将不再可用。 对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
  
## <a name="remarks"></a>备注  
 `ModifyApplicationPolicy`可以调用方法两次。 第一次调用应为参数提供 null 值 `pbNewApplicationPolicy` 。 此调用将返回，并具有的必需值 `pcbNewAppPolicySize` 。 第二次调用应为提供此值 `pcbNewAppPolicySize` ，并指向该大小的缓冲区 `pbNewApplicationPolicy` 。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICLRHostBindingPolicyManager 接口](iclrhostbindingpolicymanager-interface.md)
