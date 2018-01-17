---
title: "COR_PRF_SUSPEND_REASON 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_SUSPEND_REASON
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_SUSPEND_REASON
helpviewer_keywords: COR_PRF_SUSPEND_REASON enumeration [.NET Framework profiling]
ms.assetid: 75594833-bed3-47b2-a426-b75c5fe6fbcf
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 713360b3cdc30ce7bca3e0df115016d66e59b0df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corprfsuspendreason-enumeration"></a>COR_PRF_SUSPEND_REASON 枚举
指示运行时挂起的原因。  
  
## <a name="syntax"></a>语法  
  
```  
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
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`COR_PRF_FIELD_SUSPEND_OTHER`|运行时挂起，原因不明。|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|运行时挂起，以便垃圾回收请求提供服务。<br /><br /> 垃圾回收集合相关回调之间发生[icorprofilercallback:: Runtimesuspendfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)和[icorprofilercallback:: Runtimeresumestarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md)回调。|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|运行时挂起，以便`AppDomain`可以关闭。<br /><br /> 当挂起时运行时，运行时将确定哪些线程正在`AppDomain`，它是被关闭，然后将它们设置为继续时中止。 有没有`AppDomain`-此挂起期间的特定回调。|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|运行时挂起，这样代码间距调整才能发生。<br /><br /> 代码间距调整时，才会仅在实时 (JIT) 编译器处于活动状态时使用代码间距调整启用。 代码间距调整回调之间发生`ICorProfilerCallback::RuntimeSuspendFinished`和`ICorProfilerCallback::RuntimeResumeStarted`回调。 **注意：** CLR JIT 不推广函数在.NET Framework 2.0 版中，以便在 2.0 中不使用此值。|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|运行时挂起，以便它可以关闭。 它必须挂起所有线程以完成该操作。|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|运行时已挂起，进程内调试。|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|运行时挂起来准备垃圾回收。|  
|`COR_PRF_SUSPEND_FOR_REJIT`|已挂起运行时，JIT 重新编译。|  
  
## <a name="remarks"></a>备注  
 非托管代码中的所有运行时线程可以继续运行，直到它们尝试重新输入运行时，此时它们也会挂起，直到运行时恢复。 这也适用于输入运行时的新线程。 运行时中的所有线程立即挂起; 如果它们是在可中断的代码中，连接，或者需要挂起时它们到达可中断的代码。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [分析枚举](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
