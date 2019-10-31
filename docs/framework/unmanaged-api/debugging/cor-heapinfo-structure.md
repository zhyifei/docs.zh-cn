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
ms.openlocfilehash: b6fd3682290c9752125aed7b9663c6704ade25de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132324"
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
  
## <a name="members"></a>Members  
  
|成员|描述|  
|------------|-----------------|  
|`areGCStructuresValid`|`true` 如果垃圾回收结构有效并且可以枚举堆，则为;否则，`false`。|  
|`pointerSize`|目标体系结构上指针的大小（以字节为单位）。|  
|`numHeaps`|进程中逻辑垃圾回收堆的数目。|  
|`concurrent`|`TRUE` 如果启用了并发（后台）垃圾回收，则为;否则，`FALSE`。|  
|`gcType`|[CorDebugGCType](cordebuggctype-enumeration.md)枚举的成员，它指示垃圾回收器是在工作站上运行还是在服务器上运行。|  
  
## <a name="remarks"></a>备注  
 通过调用[ICorDebugProcess5：： GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md)方法返回 `COR_HEAPINFO` 结构的实例。  
  
 枚举垃圾回收堆上的对象之前，必须始终检查 `areGCStructuresValid` 字段，以确保堆处于可枚举状态。 有关详细信息，请参阅[ICorDebugProcess5：： GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md)方法。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试结构](debugging-structures.md)
- [调试](index.md)
