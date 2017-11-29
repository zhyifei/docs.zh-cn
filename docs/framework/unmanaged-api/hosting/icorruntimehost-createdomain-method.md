---
title: "ICorRuntimeHost::CreateDomain 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.CreateDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::CreateDomain
helpviewer_keywords:
- CreateDomain method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
ms.assetid: b96c5ef3-a9df-4c7c-9952-432d3272cb5c
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0da99f05b09d44338a5f4d695fb2a4114f0e1f30
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorruntimehostcreatedomain-method"></a>ICorRuntimeHost::CreateDomain 方法
创建应用程序域。 调用方会收到类型的接口指针<xref:System._AppDomain>到类型的实例<xref:System.AppDomain?displayProperty=nameWithType>。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CreateDomain (  
    [in] LPWSTR    pwzFriendlyName,  
    [in] IUnknown* pIdentityArray,  
    [out] void   **pAppDomain  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pwzFriendlyName`  
 [in]一个可选参数，用于为域友好名称。 此友好名称，可以显示在用户界面，例如调试器以标识域。  
  
 `pIdentityArray`  
 [in]指向的指针的可选数组`IIdentity`表示映射通过安全策略，以建立权限集的证据的实例。 `IIdentity`可以通过调用获取对象[CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)方法。  
  
 `pAppDomain`  
 [out]类型的接口指针<xref:System._AppDomain>到实例<xref:System.AppDomain?displayProperty=nameWithType>可以用于进一步控制域。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该操作成功。|  
|S_FALSE|操作无法完成。|  
|E_FAIL|发生了未知的灾难性故障。 如果某方法返回 E_FAIL，公共语言运行时 (CLR) 不再可用进程中。 对任何托管 Api 的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
|HOST_E_CLRNOTAVAILABLE|CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** 1.0、 1.1  
  
## <a name="see-also"></a>另请参阅  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [ICorRuntimeHost 接口](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
