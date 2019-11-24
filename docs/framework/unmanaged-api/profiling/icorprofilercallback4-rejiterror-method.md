---
title: ICorProfilerCallback4::ReJITError 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITError
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITError
helpviewer_keywords:
- ReJITError method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITError method [.NET Framework profiling]
ms.assetid: d7888aa9-dfaa-420f-9f99-e06ab35ca482
topic_type:
- apiref
ms.openlocfilehash: 6ea9dee6e83870d1f2e0fdccffa53f16e6f18dba
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430106"
---
# <a name="icorprofilercallback4rejiterror-method"></a>ICorProfilerCallback4::ReJITError 方法
Notifies the profiler that the just-in-time (JIT) compiler encountered an error in the recompilation process.  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a>参数  
 `moduleID`  
 [in] The `ModuleID` in which the failed recompilation attempt was made.  
  
 `methodId`  
 [in] The `MethodDef` of the method on which the failed recompilation attempt was made.  
  
 `functionId`  
 [in] The function instance that is being recompiled or marked for recompilation. This value may be `NULL` if the failure occurred on a per-method basis instead of a per-instantiation basis (for example, if the profiler specified an invalid metadata token for the method to be recompiled).  
  
 `hrStatus`  
 [in] An HRESULT that indicates the nature of the failure. See the Status HRESULTS section for a list of values.  
  
## <a name="return-value"></a>返回值  
 将忽略此回调的返回值。  
  
## <a name="status-hresults"></a>状态 HRESULTS  
  
|状态数组 HRESULT|描述|  
|--------------------------|-----------------|  
|E_INVALIDARG|The `moduleID` or `methodDef` token is `NULL`.|  
|CORPROF_E_DATAINCOMPLETE|该模块尚未完全加载，或正在被卸载。|  
|CORPROF_E_MODULE_IS_DYNAMIC|The specified module was dynamically generated (for example, by `Reflection.Emit`), and is thus not supported by this method.|  
|CORPROF_E_FUNCTION_IS_COLLECTIBLE|The method is instantiated into a collectible assembly, and is therefore not able to be recompiled. Note that types and functions defined in a non-reflection context (for example, `List<MyCollectibleStruct>`) can be instantiated into a collectible assembly.|  
|E_OUTOFMEMORY|The CLR ran out of memory while trying to mark the specified method for JIT recompilation.|  
|其他|操作系统返回了 CLR 控件范围之外的失败。 For example, if a system call to change the access protection of a page of memory fails, the operating system error is displayed.|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ICorProfilerCallback4 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
