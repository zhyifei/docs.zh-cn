---
title: CorDebugExceptionCallbackType 枚举
ms.date: 03/30/2017
api_name:
- CorDebugExceptionCallbackType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionCallbackType
helpviewer_keywords:
- CorDebugExceptionCallbackType enumeration [.NET Framework debugging]
ms.assetid: 4d946ad4-3c19-42cb-bec9-8633325ba769
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b712ee0bb8e67f448b7ea2bee3c092367181abad
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740213"
---
# <a name="cordebugexceptioncallbacktype-enumeration"></a>CorDebugExceptionCallbackType 枚举
指示从进行回调的类型[ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)事件。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum CorDebugExceptionCallbackType {  
    DEBUG_EXCEPTION_FIRST_CHANCE         = 1,  
    DEBUG_EXCEPTION_USER_FIRST_CHANCE    = 2,  
    DEBUG_EXCEPTION_CATCH_HANDLER_FOUND  = 3,  
    DEBUG_EXCEPTION_UNHANDLED            = 4  
} CorDebugExceptionCallbackType;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_FIRST_CHANCE`|引发了异常。|  
|`DEBUG_EXCEPTION_USER_FIRST_CHANCE`|异常终结进程进入用户代码。|  
|`DEBUG_EXCEPTION_CATCH_HANDLER_FOUND`|找到异常终结进程`catch`阻止在用户代码中。|  
|`DEBUG_EXCEPTION_UNHANDLED`|未处理异常。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试枚举](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
