---
title: ICorProfilerCallback::RuntimeSuspendStarted 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted method [.NET Framework profiling]
- RuntimeSuspendStarted method [.NET Framework profiling]
ms.assetid: c8461cac-e31b-4efa-ad2c-26598173eb96
topic_type:
- apiref
ms.openlocfilehash: e88f6356c2e29a1d8a9e49527c5921e8155c3ce4
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865878"
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a>ICorProfilerCallback::RuntimeSuspendStarted 方法
通知探查器运行时将要挂起所有运行时线程。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
## <a name="parameters"></a>参数  
 `suspendReason`  
 中一个[COR_PRF_SUSPEND_REASON](cor-prf-suspend-reason-enumeration.md)枚举的值，该值指示挂起的原因。  
  
## <a name="remarks"></a>备注  
 允许非托管代码中的所有运行时线程继续运行，直到它们尝试重新进入运行时。 此时，它们也将被挂起，直到运行时恢复。 这也适用于输入运行时的新线程。 如果运行时中的所有线程已处于中断的代码中，则会立即将其挂起，或者当它们到达中断的代码时要求它们挂起。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerCallback 接口](icorprofilercallback-interface.md)
- [RuntimeSuspendAborted 方法](icorprofilercallback-runtimesuspendaborted-method.md)
- [RuntimeSuspendFinished 方法](icorprofilercallback-runtimesuspendfinished-method.md)
