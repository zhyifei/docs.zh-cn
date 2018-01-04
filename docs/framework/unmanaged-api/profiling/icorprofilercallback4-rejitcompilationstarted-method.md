---
title: "ICorProfilerCallback4::ReJITCompilationStarted 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback4.ReJITCompilationStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback4::ReJITCompilationStarted
helpviewer_keywords:
- ReJITCompilationStarted method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITCompilationStarted method [.NET Framework profiling]
ms.assetid: 512fdd00-262a-4456-a075-365ef4133c4d
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 903db06089f7c68843b503c94483087ff9fce636
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a>ICorProfilerCallback4::ReJITCompilationStarted 方法
通知探查器在实时 (JIT) 编译器已开始重新编译函数。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ReJITCompilationStarted(    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a>参数  
 `functionId`  
 [in]JIT 编译器已开始重新编译的函数 ID。  
  
 `rejitId`  
 [in]函数的新版本重新编译 ID。  
  
 `fIsSafeToBlock`  
 [in]`true`以指示阻止可能导致运行时等待从此回调; 中返回调用线程`false`以指示，阻止将不会影响运行时该操作。 值为`true`不损害运行时，但可能会影响分析结果。  
  
## <a name="remarks"></a>备注  
 可以接收多个对`ReJITCompilationStarted`和[ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)方法调用每个函数由于的方式运行时句柄类构造函数。 例如，运行时将开始重新编译方法 A，但类 B 的类构造函数需要运行。 因此，运行时重新编译类 B 的构造函数，并运行它。 在运行时构造函数，它将调用方法 A，从而导致方法 A 再次重新编译。 在此方案中，将停止的方法的第一个重新编译。 但是，同时尝试重新编译 a 中报告的 JIT 重新编译事件的方法。  
  
 在两个线程同时执行回调的情况下，探查器必须支持 JIT 重新编译回调的序列。 例如，调用线程 A `ReJITCompilationStarted`; 但是，在线程的调用之前[ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)，线程 B 调用[icorprofilercallback:: Exceptionsearchfunctionenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md)函数 id从`ReJITCompilationStarted`回调线程 a。它可能会出现，函数 ID 尚未有效期不应由于调用[ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)具有尚未收到探查器。 但是，在这种情况下，函数 ID 有效。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback4 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [JITCompilationFinished 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)  
 [ReJITCompilationFinished 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)
