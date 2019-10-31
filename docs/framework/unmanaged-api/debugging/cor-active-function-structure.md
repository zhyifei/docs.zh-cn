---
title: COR_ACTIVE_FUNCTION 结构
ms.date: 03/30/2017
api_name:
- COR_ACTIVE_FUNCTION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ACTIVE_FUNCTION
helpviewer_keywords:
- COR_ACTIVE_FUNCTION structure [.NET Framework debugging]
ms.assetid: ed86185f-2152-459c-961f-10c06d62e83f
topic_type:
- apiref
ms.openlocfilehash: cbc272070e9eb6810b34ec1f3fdc9e944c624cd3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132385"
---
# <a name="cor_active_function-structure"></a>COR_ACTIVE_FUNCTION 结构
包含有关在线程框架中当前处于活动状态的函数的信息。 此结构由[ICorDebugThread2：： GetActiveFunctions](icordebugthread2-getactivefunctions-method.md)方法使用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct  _COR_ACTIVE_FUNCTION {  
    ICorDebugAppDomain   *pAppDomain;  
    ICorDebugModule      *pModule;  
    ICorDebugFunction2   *pFunction;  
    ULONG32              ilOffset;  
    ULONG32              flags;  
} COR_ACTIVE_FUNCTION;  
```  
  
## <a name="members"></a>Members  
  
|成员|描述|  
|------------|-----------------|  
|`pAppDomain`|指向 `ilOffset` 字段的应用程序域所有者的指针。|  
|`pModule`|指向 `ilOffset` 字段的模块所有者的指针。|  
|`pFunction`|指向 `ilOffset` 字段的函数所有者的指针。|  
|`ilOffset`|帧的 Microsoft 中间语言（MSIL）偏移量。|  
|`flags`|保留以供将来进行扩展。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl .idl  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试结构](debugging-structures.md)
- [调试](index.md)
