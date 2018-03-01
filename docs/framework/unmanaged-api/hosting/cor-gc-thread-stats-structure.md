---
title: "COR_GC_THREAD_STATS 结构"
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
- COR_GC_THREAD_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS
helpviewer_keywords:
- COR_GC_THREAD_STATS structure [.NET Framework hosting]
ms.assetid: 01f9a59b-7679-4d42-9ced-4a8981625c3d
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 266352984cf50dc906e77598e8dcc9216526ce17
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corgcthreadstats-structure"></a>COR_GC_THREAD_STATS 结构
包含有关垃圾回收的每个线程统计信息。  
  
## <a name="syntax"></a>语法  
  
```  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`PerThreadAllocation`|与当前关联的线程上分配的内存的字节数`COR_GC_THREAD_STATS`实例。 此数字将清零每次生成零垃圾回收发生时。|  
|`Flags`|提升的字节数为较高代的最新的垃圾回收。|  
  
## <a name="remarks"></a>备注  
 [Iclrtask:: Getmemstats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md)采用类型的输出参数`COR_GC_THREAD_STATS`。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** GCHost.idl  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [承载结构](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [IHostTask 接口](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
