---
title: ICorProfilerCallback::ExceptionUnwindFunctionLeave 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionLeave method [.NET Framework profiling]
- ExceptionUnwindFunctionLeave method [.NET Framework profiling]
ms.assetid: ebaad1d5-ee0a-4cb0-96bc-8ba5d371b747
topic_type:
- apiref
ms.openlocfilehash: 9d3e39cd910240b965896f1b866b0c21de616a57
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866331"
---
# <a name="icorprofilercallbackexceptionunwindfunctionleave-method"></a>ICorProfilerCallback::ExceptionUnwindFunctionLeave 方法
通知探查器异常处理的展开阶段已完成展开某个函数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ExceptionUnwindFunctionLeave();  
```  
  
## <a name="remarks"></a>备注  
 调用 `ExceptionUnwindFunctionLeave` 方法时，将从堆栈中移除函数实例及其堆栈数据。  
  
 探查器不应在此调用期间被阻止，因为堆栈可能不处于允许垃圾回收的状态，因此无法启用抢先垃圾回收。 如果探查器在此处阻止并且试图进行垃圾回收，则运行时将被阻止，直到此回调返回。  
  
 此外，在此调用期间，探查器不得调入托管代码或以任何方式导致托管内存分配。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerCallback 接口](icorprofilercallback-interface.md)
- [ExceptionUnwindFunctionEnter 方法](icorprofilercallback-exceptionunwindfunctionenter-method.md)
