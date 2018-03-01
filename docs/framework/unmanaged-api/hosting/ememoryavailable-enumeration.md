---
title: "EMemoryAvailable 枚举"
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
- EMemoryAvailable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryAvailable
helpviewer_keywords:
- EMemoryAvailable enumeration [.NET Framework hosting]
ms.assetid: 38e72a06-dbed-473b-a59b-7e0b3ea4f2af
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 596b174fa4ebac7e54e2f6b5f3ed044686fa515f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ememoryavailable-enumeration"></a>EMemoryAvailable 枚举
包含表示在计算机上的可用物理内存量的值。 这些值以逻辑方式映射的事件的内存从返回的上限和下限`CreateMemoryResourceNotification`Win32 API 中的函数。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|很多物理内存才可用。|  
|`eMemoryAvailableLow`|很少的物理内存不可用。|  
|`eMemoryAvailableNeutral`|可用的物理内存为中性。|  
  
## <a name="remarks"></a>备注  
 此值由传递到公共语言运行时 (CLR) 由主机调用[iclrmemorynotificationcallback:: Onmemorynotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)方法。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [承载枚举](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
