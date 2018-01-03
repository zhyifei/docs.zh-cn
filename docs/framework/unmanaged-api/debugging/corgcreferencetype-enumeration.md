---
title: "CorGCReferenceType 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorGCReferenceType
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorGCReferenceType
helpviewer_keywords: CorGCReferenceType
ms.assetid: d9f16439-5a36-4474-8ffd-4f0b2c2bb686
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b314580f7628eca68a3996aaafb362081c6ed705
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corgcreferencetype-enumeration"></a>CorGCReferenceType 枚举
标识要进行垃圾回收的对象的源。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum {  
    CorHandleStrong = 1,  
    CorHandleStrongPinning = 2,  
    CorHandleWeakShort = 4,  
    CorHandleWeakRefCount = 8,  
    CorHandleStrongRefCount = 32,  
    CorHandleStrongDependent = 64,  
    CorHandleStrongAsyncPinned = 128,  
    CorHandleStrongSizedByref = 256,  
  
    CorReferenceStack = 0x80000001,  
    CorReferenceFinalizer = 0x80000002,  
  
    CorHandleStrongOnly = 0x1E3,  
    CorHandleWeakOnly = 0xC,  
    CorHandleAll = 0x7FFFFFFF  
} CorGCReferenceType  
```  
  
## <a name="members"></a>成员  
  
|成员名称|描述|  
|-----------------|-----------------|  
|`CorHandleStrong`|来自对象句柄表的强引用的句柄。|  
|`CorHandleStrongPinning`|来自对象句柄表的固定强引用句柄。|  
|`CorHandleWeakShort`|来自对象句柄表的弱引用句柄。|  
|`CorHandleWeakRefCount`|来自对象句柄表的弱引用计数对象句柄。|  
|`CorHandleStrongRefCount`|来自对象句柄表的引用计数对象句柄。|  
|`CorHandleStrongDependent`|来自对象句柄表的依赖对象句柄。|  
|`CorHandleStrongAsyncPinned`|来自对象句柄表的异步固定对象。|  
|`CorHandleStrongSizedByref`|在垃圾回收时间保留所有对象和对象根的集体闭合的近似大小的强句柄。|  
|`CorReferenceStack`|托管堆栈中的引用。|  
|`CorReferenceFinalizer`|终结器队列中的引用。|  
|CorHandleStrongOnly|从句柄表返回仅强引用。 使用此值[icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)仅限方法。|  
|`CorHandleWeakOnly`|从句柄表返回仅弱引用。 使用此值[icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)仅限方法。|  
|`CorHandleAll`|返回句柄表中的所有引用。 使用此值[icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)仅限方法。|  
  
## <a name="remarks"></a>备注  
 `CorGCReferenceType`枚举的使用方式如下：  
  
-   值作为`type`字段[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)结构，它指示根源的引用或句柄。  
  
-   作为`types`参数[icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)方法，它指定的句柄要包含在枚举中的类型。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试枚举](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
