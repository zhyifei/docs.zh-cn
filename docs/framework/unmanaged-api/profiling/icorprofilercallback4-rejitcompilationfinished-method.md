---
title: "ICorProfilerCallback4::ReJITCompilationFinished 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback4.ReJITCompilationFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback4::ReJITCompilationFinished
helpviewer_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished method [.NET Framework profiling]
- ReJITCompilationFinished method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 3b5cff02-2005-44eb-a2bc-50214c4b0e1d
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1aab8fd836da5238fa939b4d20d019f7bd581213
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback4rejitcompilationfinished-method"></a>ICorProfilerCallback4::ReJITCompilationFinished 方法
通知探查器在实时 (JIT) 编译器已完成重新编译函数。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ReJITCompilationFinished(  
    [in] FunctionID functionId,    [in] ReJITID rejitId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a>参数  
 `functionId`  
 [in]已重新编译的函数 ID。  
  
 `rejitId`  
 [in] JIT 重新编译的函数的标识。  
  
 `hrStatus`  
 [in]一个值，该值指示是否已成功 JIT 重新编译。  
  
 `fIsSafeToBlock`  
 [in]`true`以指示阻止可能导致运行时等待从此回调; 中返回调用线程`false`以指示，阻止将不会影响运行时该操作。  
  
 值为`true`不损害运行时，但可能会影响分析结果。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback4 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [JITCompilationStarted 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)  
 [ReJITCompilationStarted 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
