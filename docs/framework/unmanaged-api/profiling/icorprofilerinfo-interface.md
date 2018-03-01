---
title: "ICorProfilerInfo 接口"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 08852b10f59e9c400b60287d78c8eb8eed5f109f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo-interface"></a>ICorProfilerInfo 接口
提供代码探查器与公共语言运行时 (CLR)，以控制事件监视及请求信息进行通信的方法。  
  
> [!NOTE]
>  在每个方法`ICorProfilerInfo`接口返回一个 HRESULT，指示成功或失败。 有关可能的返回代码的列表，请参阅 CorError.h。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[BeginInprocDebugging 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md)|初始化进程内调试支持。 此方法是.NET Framework 2.0 版中过时。|  
|[EndInprocDebugging 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-endinprocdebugging-method.md)|关闭进程内调试会话。 此方法是.NET Framework 2.0 版中过时。|  
|[ForceGC 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md)|强制运行时中执行垃圾回收。|  
|[GetAppDomainInfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getappdomaininfo-method.md)|获取有关指定的应用程序域的信息。|  
|[GetAssemblyInfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getassemblyinfo-method.md)|获取有关指定的程序集的信息。|  
|[GetClassFromObject 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromobject-method.md)|获取`ClassID`的<br /><br /> 给定的对象，其`ObjectID`。|  
|[GetClassFromToken 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromtoken-method.md)|获取给定元数据标记的类 ID。 此方法是.NET Framework 2.0 版中过时。 使用[icorprofilerinfo2:: Getclassfromtokenandtypeargs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)方法相反。|  
|[GetClassIDInfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md)|获取指定的类的父模块和元数据标记。|  
|[GetCodeInfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcodeinfo-method.md)|获取与指定函数 ID 关联的本机代码的范围。 此方法已过时。 使用[icorprofilerinfo2:: Getcodeinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)方法相反。|  
|[GetCurrentThreadID 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcurrentthreadid-method.md)|如果它是一个托管的线程，请获取当前线程的 ID。|  
|[GetEventMask 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)|获取探查器要为其接收来自 CLR 的事件通知的当前事件类别。|  
|[GetFunctionFromIP 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md)|映射到托管的代码指令指针`FunctionID`。|  
|[GetFunctionFromToken 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromtoken-method.md)|获取函数的 ID。 此方法是.NET Framework 2.0 版中过时。 使用[icorprofilerinfo2:: Getfunctionfromtokenandtypeargs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)方法相反。|  
|[GetFunctionInfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctioninfo-method.md)|获取父类和元数据标记指定的函数。|  
|[GetHandleFromThread 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-gethandlefromthread-method.md)|映射到 Win32 线程句柄的线程的 ID。|  
|[GetILFunctionBody 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbody-method.md)|获取一个指针指向方法的正文在 Microsoft 中间语言 (MSIL) 代码中，开始其标头。|  
|[GetILFunctionBodyAllocator 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md)|获取提供的方法来分配内存来用于换出中 MSIL 代码的方法体的接口。|  
|[GetILToNativeMapping 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)|获取从 MSIL 偏移量到本机偏移量指定函数中包含的代码的映射。|  
|[GetInprocInspectionInterface 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getinprocinspectioninterface-method.md)|ICorDebugProcess 接口获取可以查询的对象。 此方法是.NET Framework 2.0 版中过时。|  
|[GetInprocInspectionIThisThread 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getinprocinspectionithisthread-method.md)|ICorDebugThread 接口获取可以查询的对象。 此方法是.NET Framework 2.0 版中过时。|  
|[GetModuleInfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md)|给定模块 ID 后，将返回模块的文件名和模块的父程序集的 ID。|  
|[GetModuleMetaData 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md)|获取映射到指定的模块的元数据接口实例。|  
|[GetObjectSize 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md)|获取指定对象的大小。|  
|[GetThreadContext 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadcontext-method.md)|获取当前与指定的线程关联的上下文标识。|  
|[GetThreadInfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadinfo-method.md)|获取指定线程的当前的 Win32 线程标识。|  
|[GetTokenAndMetadataFromFunction 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-gettokenandmetadatafromfunction-method.md)|获取元数据标记和可用于对标记指定的函数元数据接口的实例。|  
|[IsArrayClass 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-isarrayclass-method.md)|确定指定的类是否是一个数组类。|  
|[SetEnterLeaveFunctionHooks 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md)|指定要在"输入"、"保留"和"tailcall"挂钩托管函数调用的探查器实现的函数。|  
|[SetEventMask 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)|设置一个值，指定的事件探查器要为其接收来自 CLR 的通知类型。|  
|[SetFunctionIDMapper 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)|指定将调用以将 `FunctionID` 值映射至替换值（传递至探查器的输入/退出挂钩）的探查器实现函数。|  
|[SetFunctionReJIT 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionrejit-method.md)|未实现。 请勿使用。|  
|[SetILFunctionBody 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)|替换指定模块中指定的函数的主体。|  
|[SetILInstrumentedCodeMap 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)|指定如何指定的函数的原始 MSIL 的偏移量映射到新的函数的探查器修改 MSIL 偏移量。|  
  
## <a name="remarks"></a>备注  
 探查器中调用一个方法`ICorProfilerInfo`接口与 CLR 以控制事件监视及请求信息进行通信。  
  
 方法`ICorProfilerInfo`由 CLR 使用自由线程模型实现接口。 每个方法均返回一个 HRESULT，指示成功或失败。 有关可能的返回代码的列表，请参阅 CorError.h。  
  
 CLR 通过，通过探查器的实现[icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)、`ICorProfilerInfo`至在初始化过程中每个代码探查器的接口。 然后，代码探查器可以调用的方法`ICorProfilerInfo`接口来获取有关正在 CLR 控件下执行的托管代码的信息。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [Profiling 接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [ICorProfilerInfo2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
