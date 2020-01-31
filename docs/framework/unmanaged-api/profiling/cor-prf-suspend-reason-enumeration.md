---
title: COR_PRF_SUSPEND_REASON 枚举
ms.date: 03/30/2017
api_name:
- COR_PRF_SUSPEND_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SUSPEND_REASON
helpviewer_keywords:
- COR_PRF_SUSPEND_REASON enumeration [.NET Framework profiling]
ms.assetid: 75594833-bed3-47b2-a426-b75c5fe6fbcf
topic_type:
- apiref
ms.openlocfilehash: 1036ecbdb735b95c0ad6897c1545e3bd8cb6c3a9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867067"
---
# <a name="cor_prf_suspend_reason-enumeration"></a>COR_PRF_SUSPEND_REASON 枚举
指示运行时挂起的原因。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum {  
    COR_PRF_SUSPEND_OTHER                   = 0x00,  
    COR_PRF_SUSPEND_FOR_GC                  = 0x01,  
    COR_PRF_SUSPEND_FOR_APPDOMAIN_SHUTDOWN  = 0x02,  
    COR_PRF_SUSPEND_FOR_CODE_PITCHING       = 0x03,  
    COR_PRF_SUSPEND_FOR_SHUTDOWN            = 0x04,  
    COR_PRF_SUSPEND_FOR_INPROC_DEBUGGER     = 0x06,  
    COR_PRF_SUSPEND_FOR_GC_PREP             = 0x07,    COR_PRF_SUSPEND_FOR_REJIT               = 8  
} COR_PRF_SUSPEND_REASON;  
```  
  
## <a name="members"></a>Members  
  
|成员|描述|  
|------------|-----------------|  
|`COR_PRF_FIELD_SUSPEND_OTHER`|由于未指定的原因，运行时处于挂起状态。|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|运行时挂起，可为垃圾回收请求服务。<br /><br /> 与垃圾回收相关的回调发生在[ICorProfilerCallback：： RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md)和[ICorProfilerCallback：： RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md)回调之间。|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|运行时处于挂起状态，以便可以关闭 `AppDomain`。<br /><br /> 当运行时挂起时，运行时将确定正在关闭的 `AppDomain` 中的线程，并将其设置为在恢复时中止。 此挂起期间没有特定于 `AppDomain`的回调。|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|运行时将挂起，以便代码间距调整可以出现。<br /><br /> 仅当实时（JIT）编译器处于活动状态且启用了代码间距调整时，才间距调整可以代码。 在 `ICorProfilerCallback::RuntimeSuspendFinished` 和 `ICorProfilerCallback::RuntimeResumeStarted` 回调之间发生代码间距调整回调。 **注意：** CLR JIT 不会对 .NET Framework 版本2.0 中的函数进行螺距，因此不会在2.0 中使用此值。|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|运行时处于挂起状态，以使其可以关闭。 它必须挂起所有线程才能完成此操作。|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|运行时正在进行进程内调试。|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|运行时挂起，以便准备垃圾回收。|  
|`COR_PRF_SUSPEND_FOR_REJIT`|运行时将被挂起，以便进行 JIT 重新编译。|  
  
## <a name="remarks"></a>备注  
 在非托管代码中的所有运行时线程都允许继续运行，直到它们尝试重新进入运行时为止，此时它们也将挂起，直到运行时恢复。 这也适用于输入运行时的新线程。 如果运行时中的所有线程都处于中断的代码中，或者在它们确实到达中断的代码时要求挂起，则该线程会立即挂起。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [分析枚举](profiling-enumerations.md)
