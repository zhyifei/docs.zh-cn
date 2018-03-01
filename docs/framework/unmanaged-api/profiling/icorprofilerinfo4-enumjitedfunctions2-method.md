---
title: "ICorProfilerInfo4::EnumJITedFunctions2 方法"
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
- ICorProfilerInfo4.EnumJITedFunctions2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::EnumJITedFunctions2
helpviewer_keywords:
- EnumJITedFunctions2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::EnumJITedFunctions2 method [.NET Framework profiling]
ms.assetid: 40e9a1be-9bd2-4fad-9921-34a84b61c1e3
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b7dc381848307ea0606f6989d6946c11aa5ef9a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a>ICorProfilerInfo4::EnumJITedFunctions2 方法
返回所有先前 JIT 编译和 JIT 重新编译的函数的枚举数。 此方法将替换[icorprofilerinfo3:: Enumjitedfunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)方法，不会枚举 JIT 重新编译的 Id。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
#### <a name="parameters"></a>参数  
 `ppEnum`  
 [out]指向的指针[ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)枚举器。  
  
## <a name="remarks"></a>备注  
 此方法可能会与重叠`JITCompilation`如回调[icorprofilercallback:: Jitcompilationstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)方法。 返回的枚举包括值`COR_PRF_FUNCTION::reJitId`字段。 [Icorprofilerinfo3:: Enumjitedfunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)方法，此方法取代，不会枚举 JIT 重新编译的 Id，因为`COR_PRF_FUNCTION::reJitId`字段始终设置为 0。 `ICorProfilerInfo4::EnumJITedFunctions`方法枚举 JIT 重新编译的 Id，因为`COR_PRF_FUNCTION::reJitId`字段已正确设置。 请注意， [icorprofilerinfo4:: Enumjitedfunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)方法可以触发垃圾回收，而[icorprofilerinfo3:: Enumjitedfunctions 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)将不会。  有关详细信息，请参阅[CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md)。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [EnumJITedFunctions 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)  
 [ICorProfilerInfo4 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [Profiling 接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [分析](../../../../docs/framework/unmanaged-api/profiling/index.md)
