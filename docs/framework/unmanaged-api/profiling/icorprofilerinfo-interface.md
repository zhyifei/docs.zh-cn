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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3b82d9ac610cb393696ef94fb797a48b737b0231
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965748"
---
# <a name="icorprofilerinfo-interface"></a>ICorProfilerInfo 接口
提供代码探查器用于与公共语言运行时 (CLR) 进行通信以控制事件监视和请求信息的方法。  
  
> [!NOTE]
> 接口中的`ICorProfilerInfo`每个方法都返回 HRESULT, 以指示成功或失败。 有关可能的返回代码的列表, 请参阅 CorError。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[BeginInprocDebugging 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md)|初始化进程内调试支持。 此方法在 .NET Framework 版本2.0 中已过时。|  
|[EndInprocDebugging 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-endinprocdebugging-method.md)|关闭进程内调试会话。 此方法在 .NET Framework 版本2.0 中已过时。|  
|[ForceGC 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md)|强制在运行时内发生垃圾回收。|  
|[GetAppDomainInfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getappdomaininfo-method.md)|获取有关指定应用程序域的信息。|  
|[GetAssemblyInfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getassemblyinfo-method.md)|获取有关指定程序集的信息。|  
|[GetClassFromObject 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromobject-method.md)|`ClassID`获取的<br /><br /> `ObjectID`对象。|  
|[GetClassFromToken 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromtoken-method.md)|给定元数据标记, 获取类的 ID。 此方法在 .NET Framework 版本2.0 中已过时。 改为使用[ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)方法。|  
|[GetClassIDInfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md)|获取指定类的父模块和元数据标记。|  
|[GetCodeInfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcodeinfo-method.md)|获取与指定函数 ID 关联的本机代码的范围。 此方法已过时。 改为使用[ICorProfilerInfo2:: GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)方法。|  
|[GetCurrentThreadID 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcurrentthreadid-method.md)|获取当前线程的 ID (如果它是托管线程)。|  
|[GetEventMask 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)|获取探查器要从 CLR 接收事件通知的当前事件类别。|  
|[GetFunctionFromIP 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md)|将托管代码指令指针映射到`FunctionID`。|  
|[GetFunctionFromToken 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromtoken-method.md)|获取函数的 ID。 此方法在 .NET Framework 版本2.0 中已过时。 改为使用[ICorProfilerInfo2:: GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)方法。|  
|[GetFunctionInfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctioninfo-method.md)|获取指定函数的父类和元数据标记。|  
|[GetHandleFromThread 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-gethandlefromthread-method.md)|将线程的 ID 映射到 Win32 线程句柄。|  
|[GetILFunctionBody 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbody-method.md)|获取一个指针, 该指针指向 Microsoft 中间语言 (MSIL) 代码中的方法的正文 (从其标头开始)。|  
|[GetILFunctionBodyAllocator 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md)|获取一个接口, 该接口提供一个方法, 用于分配用于在 MSIL 代码中交换方法的主体的内存。|  
|[GetILToNativeMapping 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)|获取指定函数中包含的代码的从 MSIL 偏移量到本机偏移量的映射。|  
|[GetInprocInspectionInterface 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getinprocinspectioninterface-method.md)|获取一个对象, 该对象可用于查询 ICorDebugProcess 接口。 此方法在 .NET Framework 版本2.0 中已过时。|  
|[GetInprocInspectionIThisThread 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getinprocinspectionithisthread-method.md)|获取一个对象, 该对象可查询 ICorDebugThread 接口。 此方法在 .NET Framework 版本2.0 中已过时。|  
|[GetModuleInfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md)|给定模块 ID 后，将返回模块的文件名和模块的父程序集的 ID。|  
|[GetModuleMetaData 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md)|获取映射到指定模块的元数据接口实例。|  
|[GetObjectSize 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md)|获取指定对象的大小。|  
|[GetThreadContext 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadcontext-method.md)|获取当前与指定线程关联的上下文标识。|  
|[GetThreadInfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadinfo-method.md)|获取指定线程的当前 Win32 线程标识。|  
|[GetTokenAndMetadataFromFunction 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-gettokenandmetadatafromfunction-method.md)|获取可用于指定函数的标记的元数据标记和元数据接口的实例。|  
|[IsArrayClass 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-isarrayclass-method.md)|确定指定的类是否为数组类。|  
|[SetEnterLeaveFunctionHooks 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md)|指定在托管函数的 "enter"、"leave" 和 "tailcall" 挂钩上调用的探查器实现函数。|  
|[SetEventMask 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)|设置一个值, 该值指定探查器要从 CLR 接收通知的事件类型。|  
|[SetFunctionIDMapper 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)|指定将调用以将 `FunctionID` 值映射至替换值（传递至探查器的输入/退出挂钩）的探查器实现函数。|  
|[SetFunctionReJIT 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionrejit-method.md)|未实现。 请勿使用。|  
|[SetILFunctionBody 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)|替换指定模块中指定函数的主体。|  
|[SetILInstrumentedCodeMap 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)|指定指定函数的原始 MSIL 的偏移量如何映射到该函数的探查器修改后的新偏移量。|  
  
## <a name="remarks"></a>备注  
 探查器调用`ICorProfilerInfo`接口中的方法, 以便与 CLR 通信以控制事件监视和请求信息。  
  
 `ICorProfilerInfo`接口的方法由 CLR 使用自由线程模型实现。 每个方法均返回一个 HRESULT，指示成功或失败。 有关可能的返回代码的列表, 请参阅 CorError。  
  
 CLR 通过探查器的[ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)实现, `ICorProfilerInfo`在初始化期间每个代码探查器的接口传递。 然后, 代码探查器可以调用`ICorProfilerInfo`接口的方法, 以获取有关在 CLR 控制下执行的托管代码的信息。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Corprof.idl, Corprof.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [Profiling 接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [ICorProfilerInfo2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
