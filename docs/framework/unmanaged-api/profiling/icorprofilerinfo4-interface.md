---
title: ICorProfilerInfo4 接口
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4
helpviewer_keywords:
- ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 80a5308e-c22f-4201-ba89-31cc8562515b
topic_type:
- apiref
ms.openlocfilehash: cbd7c0d8fff55766a98e727ce22c77dd5214611b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448005"
---
# <a name="icorprofilerinfo4-interface"></a>ICorProfilerInfo4 接口
Provides methods that code profilers use to communicate with the common language runtime (CLR) to control event monitoring and request information. 方法。 The `ICorProfilerInfo4` interface is an extension of the other `ICorProfilerInfo` interfaces. It provides new methods to support just-in-time (JIT) recompilation, added in the .NET Framework 4.5.  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[EnumJITedFunctions2 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)|Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.|  
|[EnumThreads 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumthreads-method.md)|Gets an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.|  
|[GetCodeInfo3 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)|获取本机代码的范围，该代码与指定函数的 JIT 重新编译版本相关联。|  
|[GetFunctionFromIP2 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getfunctionfromip2-method.md)|Maps a managed code instruction pointer to the JIT-recompiled version of a specified function.|  
|[GetILToNativeMapping2 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getiltonativemapping2-method.md)|Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function .|  
|[GetObjectSize2 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md)|Returns the size of a specified object.|  
|[GetReJITIDs 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getrejitids-method.md)|Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.|  
|[InitializeCurrentThread 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-initializecurrentthread-method.md)|Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.|  
|[RequestReJIT 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md)|请求 JIT 重新编译指定函数的所有实例。|  
|[RequestRevert 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)|将指定函数的所有实例还原为其初始版本。|  
  
## <a name="remarks"></a>备注  
 CLR 通过使用自由线程模型实现 `ICorProfilerInfo4` 接口的方法。 每个方法均返回一个 HRESULT，指示成功或失败。 有关可能的返回代码的列表，请参阅 CorError.h 文件。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [Profiling 接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
