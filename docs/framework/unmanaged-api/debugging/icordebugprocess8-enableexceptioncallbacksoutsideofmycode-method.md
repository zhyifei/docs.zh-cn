---
title: "ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f13236c865f9a57d77ebf83ab48e010f06ef08e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a>ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode 方法
[支持版本：[!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] 及更高版本]  
  
 启用或禁用某些类型的[ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)异常回调。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
#### <a name="parameters"></a>参数  
 `enableExceptionsOutsideOfJMC`  
 [in]  
  
## <a name="remarks"></a>备注  
 如果 `enableExceptionsOutsideOfJMC` 的值是 `false`：  
  
-   DEBUG_EXCEPTION_FIRST_CHANCE 异常不会导致回调到调试器。  
  
-   DEBUG_EXCEPTION_CATCH_HANDLER_FOUND 异常不会导致回调到调试器如果异常不会转义到用户代码 （即，从异常源到异常处理程序的路径具有标记为 JustMyCode 或 jmc 的方法没有方法）。  
  
 `enableExceptionsOutsideOfJMC` 的默认值为 `true`。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugProcess8 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
