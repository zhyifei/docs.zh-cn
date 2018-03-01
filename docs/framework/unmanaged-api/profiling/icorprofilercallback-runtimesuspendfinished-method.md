---
title: "ICorProfilerCallback::RuntimeSuspendFinished 方法"
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
- ICorProfilerCallback.RuntimeSuspendFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished method [.NET Framework profiling]
- RuntimeSuspendFinished method [.NET Framework profiling]
ms.assetid: b7723f58-c55c-4399-9972-1bbf3b866694
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d6127d0c5f3b193dad1586cdaf92beb8d8734376
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a>ICorProfilerCallback::RuntimeSuspendFinished 方法
通知探查器运行时已完成的所有运行时线程的挂起。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a>备注  
 允许非托管代码中的所有运行时线程继续运行，直到它们尝试重新输入运行时。 此时，它们也会挂起，直到运行时恢复。 这也适用于输入运行时的新线程。 在运行时中的所有线程都都立即挂起; 如果它们已都处于可中断的代码，或都将要求他们到达可中断的代码时挂起。  
  
 `RuntimeSuspendFinished`回调保证在同一线程上才会出现[icorprofilercallback:: Runtimesuspendstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)回调。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [RuntimeSuspendAborted 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
