---
title: COR_TYPEID 结构
ms.date: 03/30/2017
api_name:
- COR_TYPEID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPEID
helpviewer_keywords:
- COR_TYPEID structure [.NET Framework debugging]
ms.assetid: 1e172b14-ee22-4943-b3b8-3740e7bdcd2e
topic_type:
- apiref
ms.openlocfilehash: 4f6dbe8c17bd6a91078b87a87c1055fbf4977a88
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132299"
---
# <a name="cor_typeid-structure"></a>COR_TYPEID 结构
包含类型标识符。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a>Members  
  
|成员|描述|  
|------------|-----------------|  
|`token1`|第一个标记。|  
|`token2`|第二个标记。|  
  
## <a name="remarks"></a>备注  
 `COR_TYPEID` 结构由若干调试方法返回，这些方法提供有关要进行垃圾回收的对象的信息。 然后，可以将其作为参数传递给其他调试方法，这些方法提供了有关该项的附加信息。 例如，通过枚举[ICorDebugHeapEnum](icordebugheapenum-interface.md)对象，您可以检索单个[COR_HEAPOBJECT](cor-heapobject-structure.md)对象，这些对象表示托管堆上的单个对象。 然后，你可以将 `COR_TYPEID` 值从 `COR_HEAPOBJECT.type` 字段传递给[ICorDebugProcess5：： GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md)方法，以便检索提供有关对象的类型信息的 ICorDebugType 对象。  
  
 `COR_TYPEID` 的对象应是不透明的。 不应访问或操作其各个字段。 其唯一用途是作为方法调用中作为 `out` 参数提供的标识符，而后者又可传递给其他方法以提供其他信息。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试结构](debugging-structures.md)
- [调试](index.md)
