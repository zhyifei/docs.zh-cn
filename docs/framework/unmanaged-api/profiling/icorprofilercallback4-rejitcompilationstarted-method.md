---
title: ICorProfilerCallback4::ReJITCompilationStarted 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationStarted
helpviewer_keywords:
- ReJITCompilationStarted method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITCompilationStarted method [.NET Framework profiling]
ms.assetid: 512fdd00-262a-4456-a075-365ef4133c4d
topic_type:
- apiref
ms.openlocfilehash: be257930ca0fad658afa75d6efa4573d4f888a2b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177080"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a>ICorProfilerCallback4::ReJITCompilationStarted 方法
通知探查器及时 （JIT） 编译器已开始重新编译函数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ReJITCompilationStarted(
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>parameters  
 `functionId`  
 [在]JIT 编译器已开始重新编译的函数的 ID。  
  
 `rejitId`  
 [在]函数的新版本的重新编译 ID。  
  
 `fIsSafeToBlock`  
 [在]`true`指示阻塞可能导致运行时等待调用线程从此回调返回;`false`指示阻塞不会影响运行时的操作。 值`true`不会损害运行时，但可能会影响分析结果。  
  
## <a name="remarks"></a>备注  
 由于运行时处理类构造函数的方式，可以为每个`ReJITCompilationStarted`函数接收多对和[ReJIT 编译完成](icorprofilercallback4-rejitcompilationfinished-method.md)方法调用。 例如，运行时开始重新编译方法 A，但需要运行类 B 的类构造函数。 因此，运行时重新编译类 B 的构造函数并运行它。 当构造函数运行时，它会调用方法 A，这将导致方法 A 再次重新编译。 在这种情况下，方法 A 的第一次重新编译将停止。 但是，使用 JIT 重新编译事件报告重新编译方法 A 的尝试。  
  
 在两个线程同时进行回调的情况下，探查器必须支持 JIT 重新编译回调的顺序。 例如，线程 A`ReJITCompilationStarted`调用 ;但是，在线程 A 调用[ReJIT 编译完成](icorprofilercallback4-rejitcompilationfinished-method.md)之前，线程 B 调用[ICorProfiler 回调：：异常搜索功能Enter](icorprofilercallback-exceptionsearchfunctionenter-method.md)与线程 A 回调中的`ReJITCompilationStarted`函数 ID。似乎函数 ID 尚未有效，因为探查器尚未收到对[ReJIT 编译完成的](icorprofilercallback4-rejitcompilationfinished-method.md)调用。 但是，在这种情况下，函数 ID 有效。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerCallback 接口](icorprofilercallback-interface.md)
- [ICorProfilerCallback4 接口](icorprofilercallback4-interface.md)
- [JITCompilationFinished 方法](icorprofilercallback-jitcompilationfinished-method.md)
- [ReJITCompilationFinished 方法](icorprofilercallback4-rejitcompilationfinished-method.md)
