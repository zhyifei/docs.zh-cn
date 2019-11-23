---
title: ICorProfilerInfo 接口
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo
helpviewer_keywords:
- ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: eb4e4ce0-06e7-4469-bbc4-edc2eb5da4b1
topic_type:
- apiref
ms.openlocfilehash: 0af990930e8c30307e9da3b586621ca8ddb95d0c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438748"
---
# <a name="icorprofilerinfo-interface"></a>ICorProfilerInfo 接口
Provides methods for use by code profilers to communicate with the common language runtime (CLR) to control event monitoring and request information.  
  
> [!NOTE]
> Each method in the `ICorProfilerInfo` interface returns an HRESULT to indicate success or failure. See CorError.h for a list of possible return codes.  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[BeginInprocDebugging 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md)|Initializes in-process debugging support. This method is obsolete in the .NET Framework version 2.0.|  
|[EndInprocDebugging 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-endinprocdebugging-method.md)|Shuts down an in-process debugging session. This method is obsolete in the .NET Framework version 2.0.|  
|[ForceGC 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md)|Forces garbage collection to occur within the runtime.|  
|[GetAppDomainInfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getappdomaininfo-method.md)|Gets information about the specified application domain.|  
|[GetAssemblyInfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getassemblyinfo-method.md)|Gets information about the specified assembly.|  
|[GetClassFromObject 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromobject-method.md)|Gets the `ClassID` of an<br /><br /> object, given its `ObjectID`.|  
|[GetClassFromToken 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromtoken-method.md)|Gets the ID of the class, given the metadata token. This method is obsolete in the .NET Framework version 2.0. Use the [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) method instead.|  
|[GetClassIDInfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md)|Gets the parent module and the metadata token for the specified class.|  
|[GetCodeInfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcodeinfo-method.md)|获取与指定函数 ID 关联的本机代码的范围。 此方法已过时。 Use the [ICorProfilerInfo2::GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) method instead.|  
|[GetCurrentThreadID 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcurrentthreadid-method.md)|Gets the ID of the current thread, if it is a managed thread.|  
|[GetEventMask 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)|Gets the current event categories for which the profiler wants to receive event notifications from the CLR.|  
|[GetFunctionFromIP 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md)|Maps a managed code instruction pointer to a `FunctionID`.|  
|[GetFunctionFromToken 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromtoken-method.md)|Gets the ID of a function. This method is obsolete in the .NET Framework version 2.0. Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.|  
|[GetFunctionInfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctioninfo-method.md)|Gets the parent class and metadata token for the specified function.|  
|[GetHandleFromThread 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-gethandlefromthread-method.md)|Maps the ID of a thread to a Win32 thread handle.|  
|[GetILFunctionBody 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbody-method.md)|Gets a pointer to the body of a method in Microsoft intermediate language (MSIL) code, starting at its header.|  
|[GetILFunctionBodyAllocator 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md)|Gets an interface that provides a method to allocate memory to be used for swapping out the body of a method in MSIL code.|  
|[GetILToNativeMapping 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)|Gets a map from MSIL offsets to native offsets for the code contained in the specified function.|  
|[GetInprocInspectionInterface 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getinprocinspectioninterface-method.md)|Gets an object that can be queried for an ICorDebugProcess interface. This method is obsolete in the .NET Framework version 2.0.|  
|[GetInprocInspectionIThisThread 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getinprocinspectionithisthread-method.md)|Gets an object that can be queried for the ICorDebugThread interface. This method is obsolete in the .NET Framework version 2.0.|  
|[GetModuleInfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md)|给定模块 ID 后，将返回模块的文件名和模块的父程序集的 ID。|  
|[GetModuleMetaData 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md)|Gets a metadata interface instance that maps to the specified module.|  
|[GetObjectSize 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md)|Gets the size of a specified object.|  
|[GetThreadContext 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadcontext-method.md)|Gets the context identity currently associated with the specified thread.|  
|[GetThreadInfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadinfo-method.md)|Gets the current Win32 thread identity for the specified thread.|  
|[GetTokenAndMetadataFromFunction 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-gettokenandmetadatafromfunction-method.md)|Gets the metadata token and an instance of the metadata interface that can be used against the token for the specified function.|  
|[IsArrayClass 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-isarrayclass-method.md)|Determines whether the specified class is an array class.|  
|[SetEnterLeaveFunctionHooks 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md)|Specifies profiler-implemented functions to be called on "enter", "leave", and "tailcall" hooks of managed functions.|  
|[SetEventMask 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)|Sets a value that specifies the types of events for which the profiler wants to receive notification from the CLR.|  
|[SetFunctionIDMapper 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)|指定将调用以将 `FunctionID` 值映射至替换值（传递至探查器的输入/退出挂钩）的探查器实现函数。|  
|[SetFunctionReJIT 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionrejit-method.md)|未实现。 请勿使用。|  
|[SetILFunctionBody 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)|Replaces the body of the specified function in the specified module.|  
|[SetILInstrumentedCodeMap 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)|Specifies how the offsets of a specified function's original MSIL map to the new offsets of the function's profiler-modified MSIL.|  
  
## <a name="remarks"></a>备注  
 A profiler calls a method in the `ICorProfilerInfo` interface to communicate with the CLR to control event monitoring and request information.  
  
 The methods of the `ICorProfilerInfo` interface are implemented by the CLR using the free-threaded model. 每个方法均返回一个 HRESULT，指示成功或失败。 See CorError.h for a list of possible return codes.  
  
 The CLR passes, via the profiler's implementation of [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md), an `ICorProfilerInfo` interface to each code profiler during initialization. A code profiler can then call methods of the `ICorProfilerInfo` interface to get information about managed code being executed under the control of the CLR.  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [Profiling 接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [ICorProfilerInfo2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
