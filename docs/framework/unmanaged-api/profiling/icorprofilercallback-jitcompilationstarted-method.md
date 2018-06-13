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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1fa1081afc77c8116d8858c187401555409b4dcd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453976"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a>ICorProfilerCallback::JITCompilationStarted 方法
通知探查器已开始在实时 (JIT) 编译器将函数编译。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a>参数  
 `functionId`  
 [in]正在为其启动编译的函数 ID。  
  
 `fIsSafeToBlock`  
 [in]一个值，该值向探查器阻止是否会影响运行时的操作。 值是`true`如果阻止可能导致运行时，等待调用的线程，以返回从此回调; 否则为`false`。  
  
 尽管值`true`不会造成损害运行时、 但可能会扭曲分析结果。  
  
## <a name="remarks"></a>备注  
 可以接收多个对`JITCompilationStarted`和[icorprofilercallback:: Jitcompilationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)调用为每个函数由于的方式运行时句柄类构造函数。 例如，运行时开始对方法 A JIT 编译，但类 B 的类构造函数需要运行。 因此，运行时 JIT 编译类 B 的构造函数和运行它。 在运行时构造函数，它将调用方法 A，从而导致方法 A 再次进行 JIT 编译。 在此方案中，将停止的方法的第一个的 JIT 编译。 但是，对 JIT 编译方法 A 两次尝试使用 JIT 编译事件报告。 如果探查器打算通过调用替换方法的 Microsoft 中间语言 (MSIL) 代码[icorprofilerinfo:: Setilfunctionbody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)方法，它必须执行此操作两个`JITCompilationStarted`事件，但它可能使用相同的 MSIL 块有关两者。  
  
 在两个线程同时执行回调的情况下，探查器必须支持 JIT 回调的序列。 例如，调用线程 A `JITCompilationStarted`。 但是，在线程的调用之前`JITCompilationFinished`，线程 B 调用[icorprofilercallback:: Exceptionsearchfunctionenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md)从线程 A 的函数 id`JITCompilationStarted`回调。 它可能会出现，函数 ID 尚未有效期不应由于调用`JITCompilationFinished`具有尚未收到探查器。 但是，在与此类似情况下，该函数 ID 是有效的。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [JITCompilationFinished 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
