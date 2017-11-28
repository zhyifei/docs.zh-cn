---
title: "COR_HEAPINFO 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_HEAPINFO
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_HEAPINFO
helpviewer_keywords: COR_HEAPINFO structure [.NET Framework debugging]
ms.assetid: bfb2cd39-3e0b-4d51-ba0c-f009755c1456
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e316b964e3e983f50b81228709623e162529b05c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="corheapinfo-structure"></a>COR_HEAPINFO 结构
提供有关垃圾回收堆的常规信息，包括它是否是可枚举的。  
  
## <a name="syntax"></a>语法  
  
```  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;   
    DWORD pointerSize;   
    DWORD numHeaps;  
    BOOL concurrent;   
    CorDebugGCType gcType;   
} COR_HEAPINFO;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`areGCStructuresValid`|`true`如果垃圾回收结构有效，并且可以枚举堆;，否则为`false`。|  
|`pointerSize`|以字节为单位，在目标体系结构的指针的大小。|  
|`numHeaps`|堆中进程的逻辑垃圾回收数。|  
|`concurrent`|`TRUE`如果并发启用 （后台） 垃圾回收;否则为`FALSE`。|  
|`gcType`|成员[CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md)枚举，该值指示是否在工作站或服务器上运行垃圾回收器。|  
  
## <a name="remarks"></a>备注  
 实例`COR_HEAPINFO`结构返回通过调用[icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)方法。  
  
 枚举在垃圾回收堆上的对象之前, 你必须始终检查`areGCStructuresValid`字段以确保堆是可枚举的状态。 有关详细信息，请参阅[icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)方法。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [调试结构](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
