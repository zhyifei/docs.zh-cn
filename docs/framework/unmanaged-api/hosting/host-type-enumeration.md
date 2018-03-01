---
title: "HOST_TYPE 枚举"
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
- HOST_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- HOST_TYPE
helpviewer_keywords:
- HOST_TYPE enumeration [.NET Framework hosting]
ms.assetid: 51f848be-84c5-4036-9839-c762c576bbf5
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a8c910dd06109a8a69f29517812737d4b4dcef21
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="hosttype-enumeration"></a>HOST_TYPE 枚举
包含指定的启动应用程序的宿主类型的值。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|启动从 AppLaunch.exe 应用程序。<br /><br /> 部分受信任的应用程序使用此值。|  
|`HOST_TYPE_CORFLAG`|直接启动应用程序。 也就是说，启动应用程序从其自己的.exe 文件。<br /><br /> 完全受信任的应用程序使用此值。|  
|`HOST_TYPE_DEFAULT`|HOST_TYPE_APPLAUNCH 相同。|  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [承载枚举](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
