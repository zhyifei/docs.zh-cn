---
title: CorDebugBlockingObject 结构
ms.date: 03/30/2017
api_name:
- CorDebugBlockingObject Structure
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingObject
helpviewer_keywords:
- CorDebugBlockingObject structure [.NET Framework debugging]
ms.assetid: 5944edd1-0914-4efa-aba0-d5a277c38b1a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57de11c1c40c05befcf3c99c31c2e07e1ecaec5a
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2019
ms.locfileid: "71273972"
---
# <a name="cordebugblockingobject-structure"></a>CorDebugBlockingObject 结构
定义一个对象，该对象阻止线程，并且该线程被阻止的特定原因。  
  
## <a name="syntax"></a>语法  
  
```cpp  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`pBlockingObject`|线程要阻止的对象。 此对象仅在当前已同步状态的持续时间内有效。 如果两个线程在同一对象处于相同的同步状态，则可能需要[ICorDebugValue：： GetAddress](icordebugvalue-getaddress-method.md)方法返回相同的值。 但是，接口可能与指针等效。|  
|`dwTimeout`|阻止操作超时前等待的毫秒数，或值无限，这表示不会超时。超时值指定阻止操作的总时间长度，而不是剩余时间。|  
|`blockingReason`|此对象上阻塞线程的原因。|  
  
## <a name="remarks"></a>备注  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试结构](debugging-structures.md)
- [调试](index.md)
