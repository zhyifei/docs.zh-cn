---
title: CorDebugStepReason 枚举
ms.date: 03/30/2017
api_name:
- CorDebugStepReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugStepReason
helpviewer_keywords:
- CorDebugStepReason enumeration [.NET Framework debugging]
ms.assetid: fe248069-b33c-48e1-a777-06ac9b239c54
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ce2b23306e7e38f3982f8d5a4b377aa2f9547c4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186246"
---
# <a name="cordebugstepreason-enumeration"></a>CorDebugStepReason 枚举
指示一个单步执行的结果。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum CorDebugStepReason {  
    STEP_NORMAL,  
    STEP_RETURN,  
    STEP_CALL,  
    STEP_EXCEPTION_FILTER,  
    STEP_EXCEPTION_HANDLER,  
    STEP_INTERCEPT,  
    STEP_EXIT  
} CorDebugStepReason;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`STEP_NORMAL`|单步执行已完成正常情况下，同一函数中。|  
|`STEP_RETURN`|继续单步执行通常情况下，该函数返回后。|  
|`STEP_CALL`|新被调用函数的开头通常情况下，继续单步执行。|  
|`STEP_EXCEPTION_FILTER`|生成了异常，控制已传递给异常筛选器。|  
|`STEP_EXCEPTION_HANDLER`|生成了异常，控制已传递到异常处理程序。|  
|`STEP_INTERCEPT`|控件传递到侦听器。|  
|`STEP_EXIT`|线程退出之前完成该步骤。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [StepComplete 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)
- [调试枚举](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
