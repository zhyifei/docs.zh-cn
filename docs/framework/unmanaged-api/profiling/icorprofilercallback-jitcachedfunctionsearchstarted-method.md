---
title: ICorProfilerCallback::JITCachedFunctionSearchStarted 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchStarted
helpviewer_keywords:
- JITCachedFunctionSearchStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchStarted method [.NET Framework profiling]
ms.assetid: 5cba642c-0d80-48ee-889d-198c5044d821
topic_type:
- apiref
ms.openlocfilehash: 964ea11b8e8c8f494066249f7da2057970d7e8f4
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866255"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a>ICorProfilerCallback::JITCachedFunctionSearchStarted 方法
通知探查器搜索已开始使用本机映像生成器（Ngen.exe）编译的函数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
## <a name="parameters"></a>参数

- `functionId`

  \[中] 要执行搜索的函数的 ID。

- `pbUseCachedFunction`

  \[out] `true` 是否应使用函数的缓存版本（如果可用）;否则 `false`。 如果 `false`值，则执行引擎将对函数进行 JIT 编译，而不是使用 JIT 编译的版本。

## <a name="remarks"></a>备注  
 在 .NET Framework 版本2.0 中，将不会对常规 NGen 映像中的所有函数执行 `JITCachedFunctionSearchStarted` 和[ICorProfilerCallback：： JITCachedFunctionSearchFinished 方法](icorprofilercallback-jitcachedfunctionsearchfinished-method.md)回调。 只有针对配置文件优化的 NGen 映像将为映像中的所有函数生成回调。 但是，由于额外的开销，如果探查器打算使用这些回调来强制实时（JIT）编译函数，则它应请求探查器优化的 NGen 映像。 否则，探查器应使用延迟策略来收集函数信息。  
  
 探查器必须支持分析的应用程序的多个线程同时调用同一方法的情况。 例如，线程 A 调用 `JITCachedFunctionSearchStarted` 并且探查器通过将*pbUseCachedFunction*设置为 FALSE 来做出响应，以强制 JIT 编译。 然后，线程 A 调用[ICorProfilerCallback：： JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md)和[ICorProfilerCallback：： JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md)。  
  
 现在，线程 B 为同一函数调用 `JITCachedFunctionSearchStarted`。 即使探查器已经说明了 JIT 编译函数的意图，探查器仍会收到第二次回调，因为在探查器响应线程 A 对 `JITCachedFunctionSearchStarted`的调用之前，线程 B 会发送回调。 线程发出调用的顺序取决于线程的计划方式。  
  
 当探查器收到重复的回调时，它必须将 `pbUseCachedFunction` 引用的值设置为所有重复回调的相同值。 也就是说，当用相同的 `functionId` 值多次调用 `JITCachedFunctionSearchStarted` 时，探查器每次都必须响应相同的值。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerCallback 接口](icorprofilercallback-interface.md)
