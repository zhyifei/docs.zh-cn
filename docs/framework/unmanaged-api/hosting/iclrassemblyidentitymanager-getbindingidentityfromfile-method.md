---
title: ICLRAssemblyIdentityManager::GetBindingIdentityFromFile 方法
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
helpviewer_keywords:
- GetBindingIdentityFromFile method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentifyFromFile method [.NET Framework hosting]
ms.assetid: 7797562d-7b4c-4bd9-8b93-f35e0e2869e4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28e97289eda5949e6d124426eb58105e2e3ad33e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435037"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a>ICLRAssemblyIdentityManager::GetBindingIdentityFromFile 方法
获取在指定的文件路径的程序集的绑定数据的程序集标识。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pwzFilePath`  
 [in]要进行求值的文件路径。  
  
 `dwFlags`  
 [in]值为[ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md)枚举，指示程序集的标识类型。 提供以用于将来扩展。 CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT 是公共语言运行时 (CLR) 2.0 版支持的唯一值。  
  
 `pwzBuffer`  
 [out]包含的不透明的程序集标识数据的缓冲区。  
  
 `pcchBufferSize`  
 [在中，out]指向的大小的`pwzBuffer`。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该方法返回成功。|  
|E_INVALIDARG|提供`pwzFilePath`为 null。|  
|ERROR_INSUFFICIENT_BUFFER|大小`pwzBuffer`太小。|  
|HOST_E_CLRNOTAVAILABLE|CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用操作已超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|事件已被取消时被阻塞的线程，或者纤程正在等待它。|  
|E_FAIL|出现未知的灾难性故障。 如果某方法返回 E_FAIL，CLR 不再可用进程内。 到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
  
## <a name="remarks"></a>备注  
 `GetBindingIdentityFromFile` 通常称为两次。 第一个调用提供的 null 值`pwzBuffer`，并且该方法返回的适当大小以`pcchBufferSize`。 第二个调用提供适当分配的缓冲区，并且该方法返回与实际缓冲区完成后的数据。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** 作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICLRAssemblyIdentityManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [ICLRAssemblyReferenceList 接口](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [ICLRHostBindingPolicyManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
