---
title: "IHostControl::SetAppDomainManager 方法"
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
- IHostControl.SetAppDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl::SetAppDomainManager
helpviewer_keywords:
- IHostControl::SetAppDomainManager method [.NET Framework hosting]
- SetAppDomainManager method [.NET Framework hosting]
ms.assetid: 6562bbe7-0d67-4c50-a958-3a18cf680375
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d689a664f5bad19a70a8d635beb1f25f33da6ff6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostcontrolsetappdomainmanager-method"></a>IHostControl::SetAppDomainManager 方法
通知主机应用程序域已创建。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetAppDomainManager (  
    [in] DWORD     dwAppDomainID,  
    [in] IUnknown* pUnkAppDomainManager  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwAppDomainID`  
 [in]所选的数字标识符<xref:System.AppDomain>。  
  
 `pUnkAppDomainManager`  
 [in]指向的指针<xref:System.AppDomainManager>主机实现作为对象`IUnknown`。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`SetAppDomainManager`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用操作已超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|事件已被取消时被阻塞的线程，或者纤程正在等待它。|  
|E_FAIL|出现未知的灾难性故障。 如果某方法返回 E_FAIL，CLR 不再可用进程内。 到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
  
## <a name="remarks"></a>备注  
 <xref:System.AppDomainManager>为宿主提供一种机制，用于引导到托管代码和控制的创建和设置每个<xref:System.AppDomain>。 <xref:System.AppDomainManager>将会加载到每个<xref:System.AppDomain>时，<xref:System.AppDomain>创建。 如果选择，CLR 通知宿主已通过设置的值创建了应用程序域`pUnkAppDomainManager`参数。  
  
 在其实现`SetAppDomainManager`方法，主机可以设置程序集名称和类型的应用程序域管理器。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.AppDomain>  
 <xref:System.AppDomainManager>  
 [IHostControl 接口](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
