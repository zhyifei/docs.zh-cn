---
title: COR_PRF_GC_ROOT_FLAGS 枚举
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_FLAGS
helpviewer_keywords:
- COR_PRF_GC_ROOT_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 4611ee6f-0f05-4d84-91e1-e83d5e7dd7e4
topic_type:
- apiref
ms.openlocfilehash: 174486a88192bd5ff11074930d5ad3375603f8a5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449468"
---
# <a name="cor_prf_gc_root_flags-enumeration"></a>COR_PRF_GC_ROOT_FLAGS 枚举
指示垃圾回收根的属性。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a>Members  
  
|成员|说明|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|根禁止垃圾回收移动对象。|  
|`COR_PRF_GC_ROOT_WEAKREF`|根不会阻止垃圾回收。|  
|`COR_PRF_GC_ROOT_INTERIOR`|根引用的是对象的字段，而不是对象本身。|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|如果对象的引用计数为特定值，则根禁止垃圾回收。|  
  
## <a name="remarks"></a>备注  
 `COR_PRF_GC_ROOT_FLAGS` 是一个位掩码，提供有关特殊根的附加信息。 但是，并非所有的根都是特殊的。 例如，某些根不是弱引用、内部指针、固定或引用计数的。 对于这类根，没有要传达的标志。 因此，使用此枚举的方法（如[ICorProfilerCallback2：： RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)方法）为标志位掩码发送0，指示所有标志都处于关闭状态。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [分析枚举](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
