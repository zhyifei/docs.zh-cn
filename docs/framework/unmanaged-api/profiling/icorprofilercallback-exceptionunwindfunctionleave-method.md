---
title: "ICorProfilerCallback::ExceptionUnwindFunctionLeave 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eba7f6e5123108a7040bd2185eb57fc703c72c30
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptionunwindfunctionleave-method"></a>ICorProfilerCallback::ExceptionUnwindFunctionLeave 方法
通知探查器的异常处理在展开阶段已完成展开函数。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ExceptionUnwindFunctionLeave();  
```  
  
## <a name="remarks"></a>备注  
 当`ExceptionUnwindFunctionLeave`方法调用，因此函数实例和其堆栈数据从堆栈中移除。  
  
 探查器在此调用期间不应进行阻止，因为堆栈可能未处于允许垃圾回收的状态，因此无法启用 preemptive 垃圾回收。 如果尝试此处的探查器块和垃圾回收，则运行时将阻止，直到此回调返回。  
  
 此外，在此调用后，探查器必须调用进入托管代码或以任何方式导致托管内存分配。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ExceptionUnwindFunctionEnter 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)
