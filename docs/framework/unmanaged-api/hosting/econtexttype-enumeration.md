---
title: "EContextType 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EContextType
api_location: mscoree.dll
api_type: COM
f1_keywords: EContextType
helpviewer_keywords: EContextType enumeration [.NET Framework hosting]
ms.assetid: 92b926a9-b87e-408a-9036-df7b752c9492
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fd068816c5a642a7a8230fc14045e3f43980936c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="econtexttype-enumeration"></a>EContextType 枚举
描述当前正在执行的线程的安全上下文。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`eCurrentContext`|在公共语言运行时 (CLR) 调用时指示当前线程上的上下文[ihostsecuritymanager:: Getsecuritycontext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)方法或请求的对的调用中 CLR 的上下文[Ihostsecuritymanager:: Setsecuritycontext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)方法。|  
|`eRestrictedContext`|指示通过该主机具有较低的权限，如垃圾回收器或类或模块的构造函数的上下文。|  
  
## <a name="remarks"></a>备注  
 CLR 提供了之一`EContextType`值对的调用中的参数值作为`IHostSecurityManager::GetSecurityContext`和`IHostSecurityManager::SetSecurityContext`方法。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IHostSecurityContext 接口](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [IHostSecurityManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [承载枚举](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
