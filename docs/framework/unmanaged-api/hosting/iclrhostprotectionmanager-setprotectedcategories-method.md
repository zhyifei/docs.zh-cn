---
title: "ICLRHostProtectionManager::SetProtectedCategories 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRHostProtectionManager.SetProtectedCategories
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRHostProtectionManager::SetProtectedCategories
helpviewer_keywords:
- SetProtectedCategories method [.NET Framework hosting]
- ICLRHostProtectionManager::SetProtectedCategories method [.NET Framework hosting]
ms.assetid: fa21dc7b-5da7-440b-b59e-9180e5181f9d
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 984a88a9b75a03f421f1dd3f834665fee932876a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a>ICLRHostProtectionManager::SetProtectedCategories 方法
指定的托管的类型和成员的类别应禁止在部分受信任的代码中运行。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
#### <a name="parameters"></a>参数  
 `categories`  
 [in]组合[EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)值，指示哪些类别的托管的类型和成员应禁止在部分受信任的代码中运行。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`SetProtectedCategories`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用操作已超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|事件已被取消时被阻塞的线程，或者纤程正在等待它。|  
|E_FAIL|出现未知的灾难性故障。 方法返回 E_FAIL 后，CLR 不再进程内中使用。 到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
  
## <a name="remarks"></a>备注  
 每个`EApiCategories`值参考了托管的类型和成员的列表。 `EApiCategories`枚举和`SetProtectedCategories`方法直接相关于托管<xref:System.Security.Permissions.HostProtectionAttribute>类，用于将标记公开对应于所描述的类别的功能的托管的类型和成员`EApiCategories`。 有关详细信息，请参阅<xref:System.Security.Permissions.HostProtectionAttribute>和<xref:System.Security.Permissions.HostProtectionResource>枚举，直接对应于`EApiCategories`。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
 <xref:System.Security.Permissions.HostProtectionResource>  
 [EApiCategories 枚举](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)  
 [ICLRControl 接口](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [ICLRHostProtectionManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
