---
title: "ICLRDebugManager::GetDacl 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager.GetDacl
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager::GetDacl
helpviewer_keywords:
- GetDacl method [.NET Framework hosting]
- ICLRDebugManager::GetDacl method [.NET Framework hosting]
ms.assetid: 7115e920-aaff-440a-824e-39497139c6f6
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d21e95b24133cf0320c0e7bfb223d6bf1a7cf1b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebugmanagergetdacl-method"></a>ICLRDebugManager::GetDacl 方法
未实现此方法。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetDacl (  
    [out] PACL* ppacl  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppacl`  
 [out]接口指针到访问控制列表 (ACL)。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|E_NOTIMPL|未实现方法。|  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICLRControl 接口](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [ICLRDebugManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [SetDacl 方法](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)  
 [IHostControl 接口](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
