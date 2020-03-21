---
title: COR_HEAPOBJECT 结构
ms.date: 03/30/2017
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
ms.openlocfilehash: efb3d913e1d8ef0c486d7e5e1d9777ae7d88bc71
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179339"
---
# <a name="cor_heapobject-structure"></a>COR_HEAPOBJECT 结构
提供有关托管堆上的对象的信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;
    ULONG64 size;
    COR_TYPEID type;
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a>成员  
  
|成员|说明|  
|------------|-----------------|  
|`address`|内存中对象的地址。|  
|`size`|对象的总大小（以字节为单位）。|  
|`type`|表示对象类型的[COR_TYPEID](cor-typeid-structure.md)令牌。|  
  
## <a name="remarks"></a>备注  
 `COR_HEAPOBJECT`可以通过枚举[ICorDebugHeapEnum](icordebugheapenum-interface.md)接口对象来检索实例，该接口对象通过调用[ICorDebugProcess5：：：枚举堆](icordebugprocess5-enumerateheap-method.md)方法填充。  
  
 实例`COR_HEAPOBJECT`提供有关托管堆上的实时对象的信息，或者提供有关未由任何对象扎根但尚未由垃圾回收器收集的对象的信息。  
  
 为了更好的性能，该`COR_HEAPOBJECT.address`字段是一`CORDB_ADDRESS`个值，而不是许多调试 API 中使用的 ICorDebugValue 接口值。 要获取给定对象地址的 ICorDebugValue 对象，可以将`CORDB_ADDRESS`该值传递给[ICorDebugProcess5：：：getObject](icordebugprocess5-getobject-method.md)方法。  
  
 为了更好的性能，该`COR_HEAPOBJECT.type`字段是一`COR_TYPEID`个值，而不是许多调试 API 中使用的 ICorDebugType 接口值。 要获取给定类型 ID 的 ICorDebugType 对象，可以将`COR_TYPEID`该值传递给[ICorDebugProcess5：：getTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md)方法。  
  
 该`COR_HEAPOBJECT`结构包括一个引用计数的COM接口。 如果通过调用`COR_HEAPOBJECT`[ICorDebugHeapEnum：Next](icordebugheapenum-next-method.md)方法从枚举器检索实例，则必须随后释放引用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试结构](debugging-structures.md)
- [调试](index.md)
