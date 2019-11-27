---
title: ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.SetEnterLeaveFunctionHooks2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2
helpviewer_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
- SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
ms.assetid: 3c26b3e7-f72b-48a5-bf8c-edc122523a4b
topic_type:
- apiref
ms.openlocfilehash: 4068c8fee13a6086bc6b48bcc6d4117357062747
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449785"
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a>ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 方法
指定要在已更新版本的托管函数 "enter"、"leave" 和 "tailcall" 挂钩上调用的探查器实现函数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
## <a name="parameters"></a>参数  
 `pFuncEnter`  
 中指向要用作[FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)回调的实现的指针。  
  
 `pFuncLeave`  
 中指向要用作[FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)回调的实现的指针。  
  
 `pFuncTailcall`  
 中指向要用作[FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)回调的实现的指针。  
  
## <a name="remarks"></a>备注  
 `SetEnterLeaveFunctionHooks2` 方法类似于[ICorProfilerInfo：： SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md)方法。 使用前者来指定要用作输入/保留/tailcall 回调的较新版本的函数，并使用后者来指定要用作较早版本的 enter/leave/tailcall 回调的函数。  
  
 一次只能有一个回调集处于活动状态。 因此，如果探查器同时调用 `ICorProfilerInfo::SetEnterLeaveFunctionHooks` 和 `SetEnterLeaveFunctionHooks2`，将使用 `SetEnterLeaveFunctionHooks2`。  
  
 只能从探查器的[ICorProfilerCallback：： Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)回调调用 `SetEnterLeaveFunctionHooks2` 方法。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
