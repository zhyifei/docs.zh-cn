---
title: "COR_GC_STAT_TYPES 枚举"
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
- COR_GC_STAT_TYPES
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_STAT_TYPES
helpviewer_keywords:
- COR_GC_STAT_TYPES enumeration [.NET Framework hosting]
ms.assetid: fc51d6db-f7f8-408b-b93d-c166fc712c99
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 86d0ce931518fa50dbd3b0d6d7f2755d19042eca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corgcstattypes-enumeration"></a>COR_GC_STAT_TYPES 枚举
指定要记录垃圾回收的统计信息。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a>备注  
 此枚举指定中的哪些统计信息[COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)结构不是由设置[iclrgcmanager:: Getstats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)方法。  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`COR_GC_COUNTS`|记录为每一代执行垃圾回收次数。|  
|`COR_GC_MEMORYUSAGE`|记录内存使用情况和垃圾回收量统计信息。|  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** GCHost.idl、 GCHost.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [COR_GC_STATS 结构](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [承载枚举](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
