---
title: ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode 方法
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
ms.openlocfilehash: 2c0da899b3f6f3c229c6f5e5b4cafe48fdc19742
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792168"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a>ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode 方法
[.NET Framework 4.6 及更高版本中支持]  
  
 启用或禁用某些类型的[ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)异常回调。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a>参数  
 `enableExceptionsOutsideOfJMC`  
 [in]  
  
## <a name="remarks"></a>备注  
 如果 `enableExceptionsOutsideOfJMC` 的值是 `false`：  
  
- DEBUG_EXCEPTION_FIRST_CHANCE 异常将不会导致回调到调试器。  
  
- 如果异常不会转义到用户代码（即从异常源到异常处理程序的路径没有被标记为 JustMyCode 或 JMC 的方法），则 DEBUG_EXCEPTION_CATCH_HANDLER_FOUND 异常不会导致回调到调试器。  
  
 `enableExceptionsOutsideOfJMC` 的默认值为 `true`。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebugProcess8 接口](icordebugprocess8-interface.md)
- [调试接口](debugging-interfaces.md)
