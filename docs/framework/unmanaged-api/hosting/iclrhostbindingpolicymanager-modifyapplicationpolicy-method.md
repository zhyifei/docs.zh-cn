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
ms.openlocfilehash: d8df78e3d5cebe5378dfba11dc0ea93cc8e346eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178104"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a>ICLRHostBindingPolicyManager::ModifyApplicationPolicy 方法
修改指定程序集的绑定策略，并创建策略的新版本。  
  
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
  
## <a name="parameters"></a>parameters  
 `pwzSourceAssemblyIdentity`  
 [在]要修改的程序集的标识。  
  
 `pwzTargetAssemblyIdentity`  
 [在]修改程序集的新标识。  
  
 `pbApplicationPolicy`  
 [在]指向缓冲区的指针，其中包含要修改的绑定策略数据。  
  
 `cbAppPolicySize`  
 [在]要替换的绑定策略的大小。  
  
 `dwPolicyModifyFlags`  
 [在][EHostBindingPolicy修改标志](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md)值的逻辑 OR 组合，指示重定向的控制。  
  
 `pbNewApplicationPolicy`  
 [出]指向包含新绑定策略数据的缓冲区的指针。  
  
 `pcbNewAppPolicySize`  
 [进出]指向新绑定策略缓冲区大小的指针。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|说明|  
|-------------|-----------------|  
|S_OK|已成功修改策略。|  
|E_INVALIDARG|`pwzSourceAssemblyIdentity`或`pwzTargetAssemblyIdentity`为空引用。|  
|ERROR_INSUFFICIENT_BUFFER|`pbNewApplicationPolicy` 太小。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时 （CLR） 尚未加载到进程中，或者 CLR 处于无法运行托管代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|呼叫超时。|  
|HOST_E_NOT_OWNER|调用方不拥有锁。|  
|HOST_E_ABANDONED|当阻塞的线程或光纤等待事件时，事件已被取消。|  
|E_FAIL|发生了未知的灾难性故障。 方法返回E_FAIL后，CLR 在进程中不再可用。 对托管方法的后续调用返回HOST_E_CLRNOTAVAILABLE。|  
  
## <a name="remarks"></a>备注  
 该方法`ModifyApplicationPolicy`可以调用两次。 第一个调用应为`pbNewApplicationPolicy`参数提供 null 值。 此调用将返回，并带有`pcbNewAppPolicySize`所需的值。 第二个调用应为`pcbNewAppPolicySize`提供此值，并指向 该大小的缓冲区。 `pbNewApplicationPolicy`  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** MSCorEE.h  
  
 **库：** 作为资源包含在 MSCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICLRHostBindingPolicyManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
