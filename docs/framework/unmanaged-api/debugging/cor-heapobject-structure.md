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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c59ddec655f3127e8dab8d8c41543f03a896cf63
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274039"
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
  
|成员|描述|  
|------------|-----------------|  
|`address`|内存中的对象的地址。|  
|`size`|对象的总大小（以字节为单位）。|  
|`type`|表示对象类型的[COR_TYPEID](cor-typeid-structure.md)标记。|  
  
## <a name="remarks"></a>备注  
 `COR_HEAPOBJECT`可以通过枚举通过调用[ICorDebugProcess5：： EnumerateHeap](icordebugprocess5-enumerateheap-method.md)方法填充的[ICorDebugHeapEnum](icordebugheapenum-interface.md)接口对象来检索实例。  
  
 `COR_HEAPOBJECT`实例提供有关托管堆上的活动对象的信息，或有关对象的信息，该对象不是由任何对象的根，但垃圾回收器尚未收集。  
  
 为了获得更好的`COR_HEAPOBJECT.address`性能，该`CORDB_ADDRESS`字段是一个值，而不是大部分调试 API 中使用的 ICorDebugValue 接口值。 若要获取给定对象地址的 ICorDebugValue 对象，可以将`CORDB_ADDRESS`值传递给[ICorDebugProcess5：： GetObject](icordebugprocess5-getobject-method.md)方法。  
  
 为了获得更好的`COR_HEAPOBJECT.type`性能，该`COR_TYPEID`字段是一个值，而不是大部分调试 API 中使用的 ICorDebugType 接口值。 若要获取给定类型 ID 的 ICorDebugType 对象，可以将`COR_TYPEID`值传递给[ICorDebugProcess5：： GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md)方法。  
  
 `COR_HEAPOBJECT`结构包含引用计数的 COM 接口。 如果通过调用`COR_HEAPOBJECT` [ICorDebugHeapEnum：： Next](icordebugheapenum-next-method.md)方法检索枚举器中的实例，则必须随后释放该引用。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl，Cordebug.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试结构](debugging-structures.md)
- [调试](index.md)
