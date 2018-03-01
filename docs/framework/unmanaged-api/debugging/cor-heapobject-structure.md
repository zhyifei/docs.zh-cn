---
title: "COR_HEAPOBJECT 结构"
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
- COR_HEAPOBJECT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPOBJECT
helpviewer_keywords:
- COR_HEAPOBJECT structure [.NET Framework debugging]
ms.assetid: a92fdf95-492b-49ae-a741-2186e5c1d7c5
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 476d9dcb1c6700833b0a113028bdaaf0c5a375c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corheapobject-structure"></a>COR_HEAPOBJECT 结构
提供有关托管堆上的对象的信息。  
  
## <a name="syntax"></a>语法  
  
```  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;    
    ULONG64 size;             
    COR_TYPEID type;          
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`address`|在内存中对象的地址。|  
|`size`|对象，以字节为单位的总大小。|  
|`type`|A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)表示的对象类型的令牌。|  
  
## <a name="remarks"></a>备注  
 `COR_HEAPOBJECT`可以通过枚举来检索实例[ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)填充通过调用的接口对象[icordebugprocess5:: Enumerateheap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md)方法。  
  
 A`COR_HEAPOBJECT`实例提供有关在托管堆上的实时对象或有关的对象的任何对象不根路径，但尚未被垃圾回收器回收的信息。  
  
 为了提高性能，`COR_HEAPOBJECT.address`字段是`CORDB_ADDRESS`值，而不是 ICorDebugValue 接口在很多调试 API 中使用的值。 若要获取给定的对象地址的 ICorDebugValue 对象，你可以传递`CORDB_ADDRESS`值赋给[icordebugprocess5:: Getobject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md)方法。  
  
 为了提高性能，`COR_HEAPOBJECT.type`字段是`COR_TYPEID`值，而不是 ICorDebugType 接口在很多调试 API 中使用的值。 若要获取给定的类型 ID ICorDebugType 对象，你可以传递`COR_TYPEID`值赋给[icordebugprocess5:: Gettypefortypeid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md)方法。  
  
 `COR_HEAPOBJECT`结构包含引用计数 COM 接口。 如果你检索`COR_HEAPOBJECT`从通过调用枚举器实例[icordebugheapenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md)方法，你随后必须释放该引用。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试结构](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
