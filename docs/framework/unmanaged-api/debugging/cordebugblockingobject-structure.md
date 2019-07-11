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
ms.openlocfilehash: 83dac3b9b2ac396cdef19695fcce0f7e20485a50
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740392"
---
# <a name="cordebugblockingobject-structure"></a>CorDebugBlockingObject 结构
定义一个阻塞线程的线程被阻塞的具体原因的对象。  
  
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
|`pBlockingObject`|在其阻止线程对象。 此对象的有效期仅为当前同步状态的持续时间。 如果两个线程要阻止在相同的同步状态中对同一个对象，会按预期[icordebugvalue:: Getaddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)方法以返回相同的值。 但是，接口可能也可能不是等效的指针。|  
|`dwTimeout`|阻止操作之前的毫秒数将超时时间，或者值为无穷大，这表示它将不会超时。超时值指定时间阻止操作，而不是仍剩余的时间的总长度。|  
|`blockingReason`|线程此对象上阻塞的原因。|  
  
## <a name="remarks"></a>备注  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试结构](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
