---
title: "ICorProfilerInfo::SetEnterLeaveFunctionHooks 方法"
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
- ICorProfilerInfo.SetEnterLeaveFunctionHooks
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEnterLeaveFunctionHooks
helpviewer_keywords:
- SetEnterLeaveFunctionHooks method [.NET Framework profiling]
- ICorProfilerInfo::SetEnterLeaveFunctionHooks method [.NET Framework profiling]
ms.assetid: 72399636-c219-4ffd-8ac8-39432c9d4641
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e41fdf02f299d118fce025e2a5a3314feb134971
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a>ICorProfilerInfo::SetEnterLeaveFunctionHooks 方法
指定要在"输入"、"保留"和"tailcall"挂钩托管函数调用的探查器实现的函数。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
#### <a name="parameters"></a>参数  
 `pFuncEnter`  
 [in]指向要用作的实现的[FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md)回调。  
  
 `pFuncLeave`  
 [in]指向要用作的实现的[FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md)回调。  
  
 `pFuncTailcall`  
 [in]指向要用作的实现的[FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md)回调。  
  
## <a name="remarks"></a>备注  
 在.NET Framework 1.0 版中，每个函数指针可以为 null 来禁用该对应的回调。  
  
 一次，只有一组回调可以处于活动状态。 因此，如果探查器同时调用`SetEnterLeaveFunctionHooks`和[icorprofilerinfo2:: Setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)，然后`SetEnterLeaveFunctionHooks2`优先。  
  
 `SetEnterLeaveFunctionHooks`方法可以仅从探查器的调用[icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)回调。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
