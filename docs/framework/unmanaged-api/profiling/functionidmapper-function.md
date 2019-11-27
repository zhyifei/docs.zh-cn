---
title: FunctionIDMapper 函数
ms.date: 03/30/2017
api_name:
- FunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper
helpviewer_keywords:
- FunctionIDMapper function [.NET Framework profiling]
ms.assetid: b8205b60-1893-4303-8cff-7ac5a00892aa
topic_type:
- apiref
ms.openlocfilehash: 23c6f0a29160b6e1dc194cf360c07374c565522b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440701"
---
# <a name="functionidmapper-function"></a>FunctionIDMapper 函数
通知探查器可能会将函数的给定标识符重新映射到备用 ID，以在该函数的[FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)、 [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)和[FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)回调中使用。 `FunctionIDMapper` 还允许探查器指示是否要接收该函数的回调。  
  
## <a name="syntax"></a>语法  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,   
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a>参数  
 `funcId`  
 [in] 要重新映射的函数标识符。  
  
 `pbHookFunction`  
 弄指向一个值的指针，如果探查器要接收 `FunctionEnter2`、`FunctionLeave2`和 `FunctionTailcall2` 回调，则该值将设置为 `true`;否则，它会将此值设置为 `false`。  
  
## <a name="return-value"></a>返回值  
 探查器返回一个执行引擎用作替代函数标识符的值。 返回值不能为 null，除非在 `false` 中返回 `pbHookFunction`。 否则，空返回值将产生不可预知的结果，包括可能停止进程。  
  
## <a name="remarks"></a>备注  
 `FunctionIDMapper` 函数是回调。 它由探查器实现，用于将函数 ID 重新映射到其他更适用于探查器的标识符。 `FunctionIDMapper` 返回要用于任何给定函数的备用 ID。 然后，执行引擎通过将此备用 ID （除了传统函数 ID）传递回探查器的请求，将此备用 ID 传递回 `FunctionEnter2`、`FunctionLeave2`和 `FunctionTailcall2` 挂钩的 `clientData` 参数中的探查器，以标识正在为其调用挂钩的函数。  
  
 您可以使用[ICorProfilerInfo：： SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)方法指定 `FunctionIDMapper` 函数的实现。 只能调用一次 `ICorProfilerInfo::SetFunctionIDMapper` 方法，我们建议在[ICorProfilerCallback：： Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)回调中执行此操作。  
  
 默认情况下，假定探查器通过使用[ICorProfilerInfo：： SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)设置 COR_PRF_MONITOR_ENTERLEAVE 标志，并通过[ICorProfilerInfo：： SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md)或[ICorProfilerInfo2：： SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)设置挂钩，应接收每个函数的 `FunctionEnter2`、`FunctionLeave2`和 `FunctionTailcall2` 回调。 但是，探查器可能会实现 `FunctionIDMapper` 通过将 `pbHookFunction` 设置为 `false`来有选择地避免为某些函数接收这些回调。  
  
 在分析的应用程序的多个线程同时调用相同的方法/函数的情况下，探查器应该是一种容错方法。 在这种情况下，探查器可能会收到同一 `FunctionID`的多个 `FunctionIDMapper` 回调。 如果多次用相同的 `FunctionID`调用，则探查器应确保从此回调返回相同的值。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Corprof.idl .idl  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [SetFunctionIDMapper 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [FunctionIDMapper2 函数](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)
- [FunctionEnter2 函数](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [FunctionLeave2 函数](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [FunctionTailcall2 函数](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [分析全局静态函数](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
