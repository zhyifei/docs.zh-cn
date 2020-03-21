---
title: COR_HEAPINFO 结构
ms.date: 03/30/2017
api_name:
- COR_HEAPINFO
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPINFO
helpviewer_keywords:
- COR_HEAPINFO structure [.NET Framework debugging]
ms.assetid: bfb2cd39-3e0b-4d51-ba0c-f009755c1456
topic_type:
- apiref
ms.openlocfilehash: 37659262695b63a6dd6390c62c4bb7e04fdadca4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179311"
---
# <a name="cor_heapinfo-structure"></a>COR_HEAPINFO 结构
提供有关垃圾回收堆的常规信息，包括它是否是可枚举的。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;
    DWORD pointerSize;
    DWORD numHeaps;  
    BOOL concurrent;
    CorDebugGCType gcType;
} COR_HEAPINFO;  
```  
  
## <a name="members"></a>成员  
  
|成员|说明|  
|------------|-----------------|  
|`areGCStructuresValid`|`true`如果垃圾回收结构有效，并且可以枚举堆;如果垃圾回收结构有效，则为堆。否则， `false`.|  
|`pointerSize`|目标体系结构上指针的大小（以字节为单位）。|  
|`numHeaps`|进程中的逻辑垃圾回收堆数。|  
|`concurrent`|`TRUE`如果启用并发（后台）垃圾回收;如果启用了并发（后台）垃圾回收;否则， `FALSE`.|  
|`gcType`|[CorDebugGCType](cordebuggctype-enumeration.md)枚举的成员，用于指示垃圾回收器是在工作站上运行还是服务器上运行。|  
  
## <a name="remarks"></a>备注  
 结构的`COR_HEAPINFO`实例通过调用[ICorDebugProcess5：：：getGCHeap信息](icordebugprocess5-getgcheapinformation-method.md)方法返回。  
  
 在枚举垃圾回收堆上的对象之前，必须始终检查该`areGCStructuresValid`字段以确保堆处于枚举状态。 有关详细信息，请参阅[ICorDebugProcess5：：getGCHeap信息](icordebugprocess5-getgcheapinformation-method.md)方法。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试结构](debugging-structures.md)
- [调试](index.md)
