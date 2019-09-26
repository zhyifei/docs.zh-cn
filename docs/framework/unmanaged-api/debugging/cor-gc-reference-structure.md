---
title: COR_GC_REFERENCE 结构
ms.date: 03/30/2017
api_name:
- COR_GC_REFERENCE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_GC_REFERENCE
helpviewer_keywords:
- COR_GC_REFERENCE structure [.NET Framework debugging]
ms.assetid: 162e8179-0cd4-4110-8f06-5f387698bd62
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc0b67621f77c0741e0b63b84ab1794530d6280b
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274229"
---
# <a name="cor_gc_reference-structure"></a>COR_GC_REFERENCE 结构
包含有关要进行垃圾回收的对象的信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;   
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`domain`|指向句柄或对象所属的应用程序域的指针。 其值可以是`null`。|  
|`location`|与要进行垃圾回收的对象相对应的 ICorDebugValue 或 ICorDebugReferenceValue 接口。|  
|`type`|一个[CorGCReferenceType](corgcreferencetype-enumeration.md)枚举值，该值指示根的来源。 有关详细信息，请参阅“备注”部分。|  
|`extraData`|有关要进行垃圾回收的对象的其他数据。 此信息取决于对象的源，如`type`字段所示。 有关详细信息，请参阅“备注”部分。|  
  
## <a name="remarks"></a>备注  
 该`type`字段是一个[CorGCReferenceType](corgcreferencetype-enumeration.md)枚举值，该值指示引用来自何处。 特定`COR_GC_REFERENCE`值可以反映以下任意一种类型的托管对象：  
  
- 所有托管堆栈（`CorGCReferenceType.CorReferenceStack`）中的对象。 这包括托管代码中的实时引用以及由公共语言运行时创建的对象。  
  
- 来自句柄表（`CorGCReferenceType.CorHandle*`）的对象。 这包括模块中的`HNDTYPE_STRONG`强`HNDTYPE_REFCOUNT`引用（和）和静态变量。  
  
- 终结器队列（`CorGCReferenceType.CorReferenceFinalizer`）中的对象。 终结器队列根对象，直到终结器运行。  
  
 `extraData`字段包含额外的数据，具体取决于引用的源（或类型）。 可能的值有：  
  
- `DependentSource`。 `type`如果为`CorGCREferenceType.CorHandleStrongDependent`，则此字段为对象，如果为，则此字段为要在其上`COR_GC_REFERENCE.Location`进行垃圾回收的对象的根。  
  
- `RefCount`。 `type`如果为`CorGCREferenceType.CorHandleStrongRefCount`，则此字段是句柄的引用计数。  
  
- `Size`。 `type`如果为`CorGCREferenceType.CorHandleStrongSizedByref`，则此字段是垃圾回收器为其计算对象根的对象树的最后一个大小。 请注意，此计算不一定是最新的。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl，Cordebug.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试结构](debugging-structures.md)
- [调试](index.md)
