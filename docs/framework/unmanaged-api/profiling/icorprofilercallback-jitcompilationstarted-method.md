---
title: ICorProfilerCallback::JITCompilationStarted 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationStarted
helpviewer_keywords:
- JITCompilationStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationStarted method [.NET Framework profiling]
ms.assetid: 31782b36-d311-4518-8f45-25f65385af5b
topic_type:
- apiref
ms.openlocfilehash: 96ab77a36c0a0bddda0fca342433666dd19082d3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426193"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a>ICorProfilerCallback::JITCompilationStarted 方法
通知探查器实时（JIT）编译器已开始编译函数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>参数  
 `functionId`  
 中要开始编译的函数的 ID。  
  
 `fIsSafeToBlock`  
 中指示探查器是否会影响运行时的操作的值。 如果阻止可能导致运行时等待调用线程从此回调返回，则值为 `true`;否则，`false`。  
  
 尽管 `true` 的值不会损坏运行时，但它可能会使分析结果变形。  
  
## <a name="remarks"></a>备注  
 由于运行时处理类构造函数的方式，每个函数可以接收多对 `JITCompilationStarted` 和[ICorProfilerCallback：： JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)调用。 例如，运行时开始 JIT 编译方法 A，但类 B 的类构造函数需要运行。 因此，运行时 JIT 编译类 B 的构造函数并运行它。 当构造函数正在运行时，它会调用方法 A，这将导致再次 JIT 编译方法 A。 在此方案中，方法 A 的第一次 JIT 编译将暂停。 但是，将使用 JIT 编译事件来报告 JIT 编译方法 A 的两种尝试。 如果探查器将通过调用[ICorProfilerInfo：： SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)方法替换方法 A 的 Microsoft 中间语言（MSIL）代码，则它必须为这两 `JITCompilationStarted` 个事件都使用同一 MSIL 块。  
  
 当两个线程同时进行回调时，探查器必须支持 JIT 回调的序列。 例如，线程 A 调用 `JITCompilationStarted`。 但是，在线程 A 调用 `JITCompilationFinished`之前，线程 B 使用线程 A 的 `JITCompilationStarted` 回调中的函数 ID 调用[ICorProfilerCallback：： ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) 。 由于探查器尚未收到对 `JITCompilationFinished` 的调用，因此函数 ID 似乎不应有效。 但是，在这种情况下，函数 ID 有效。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [JITCompilationFinished 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
