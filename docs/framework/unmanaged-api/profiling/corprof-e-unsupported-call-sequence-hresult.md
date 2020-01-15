---
title: CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT
ms.date: 03/30/2017
f1_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE
helpviewer_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT [.NET Framework profiling]
ms.assetid: f2fc441f-d62e-4f72-a011-354ea13c8c59
ms.openlocfilehash: a0b117949190bcaffc334c208fff6e04a6a2c5bf
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964504"
---
# <a name="corprof_e_unsupported_call_sequence-hresult"></a>CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT
CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT 是在 .NET Framework 版本2.0 中引入的。 在两个方案中，.NET Framework 4 返回此 HRESULT：  
  
- 当劫持探查器随时强行重置线程的注册上下文时，使该线程尝试访问处于不一致状态的结构。  
  
- 当探查器尝试调用一个信息性方法，该方法从禁止垃圾回收的回调方法触发垃圾回收。  
  
 以下各节将讨论这两种情况。  
  
## <a name="hijacking-profilers"></a>劫持探查器  
 （此方案主要是劫持探查器的问题，不过，在某些情况下，非劫持探查器可以看到此 HRESULT。）  
  
 在这种情况下，劫持探查器会在任意时间强制重置线程的注册上下文，以便线程可以输入探查器代码或通过[ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)方法重新输入公共语言运行时（CLR）。  
  
 许多 Id 分析 API 提供的指向 CLR 中的数据结构。 许多 `ICorProfilerInfo` 调用只是从这些数据结构中读取信息，然后再将其传递回来。 但是，CLR 可能会在运行时更改这些结构中的某些组件，并且它可能会使用锁来执行此操作。 假设在探查器截获线程时，CLR 已经持有（或尝试获取）锁定。 如果线程重新进入 CLR 并尝试使用更多锁或检查正在修改的结构，则这些结构可能处于不一致的状态。 在这种情况下，可能很容易发生死锁和访问冲突。  
  
 通常，当非劫持探查器在[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)方法中执行代码，并使用有效参数调用 `ICorProfilerInfo` 方法时，它不应死锁或收到访问冲突。 例如，在[ICorProfilerCallback：： ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)方法内运行的探查器代码可以通过调用[ICorProfilerInfo2：： GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)方法来请求有关类的信息。 该代码可能会收到 CORPROF_E_DATAINCOMPLETE HRESULT，以指示该信息不可用;但是，它不会死锁或收到访问冲突。 此类调用 `ICorProfilerInfo` 称为同步，因为它们是通过 `ICorProfilerCallback` 方法进行的。  
  
 但是，执行不在 `ICorProfilerCallback` 方法中的代码的托管线程被视为进行异步调用。 在 .NET Framework 版本1中，很难确定异步调用中可能会发生的情况。 此调用可能会死锁、崩溃或发出无效的答案。 .NET Framework 版本2.0 引入了一些简单的检查，以帮助避免此问题。 在 .NET Framework 2.0 中，如果异步调用 unsafe `ICorProfilerInfo` 函数，则会失败，并 CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT。  
  
 通常，异步调用是不安全的。 但是，以下方法是安全的，并且专门支持异步调用：  
  
- [GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)  
  
- [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)  
  
- [GetCurrentThreadID](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcurrentthreadid-method.md)  
  
- [GetThreadContext](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadcontext-method.md)  
  
- [GetThreadAppDomain](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadappdomain-method.md)  
  
- [GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md)  
  
- [GetFunctionInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctioninfo-method.md)  
  
- [GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)  
  
- [GetCodeInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcodeinfo-method.md)  
  
- [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)  
  
- [GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md)  
  
- [GetClassIDInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md)  
  
- [GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)  
  
- [IsArrayClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-isarrayclass-method.md)  
  
- [SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
  
- [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)  
  
 有关其他信息，请参阅 CLR 分析 API 博客中的[CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](https://docs.microsoft.com/archive/blogs/davbr/why-we-have-corprof_e_unsupported_call_sequence)条目。  
  
## <a name="triggering-garbage-collections"></a>触发垃圾回收  
 此方案涉及一个在回调方法（例如 `ICorProfilerCallback` 方法之一）内运行的探查器，该方法禁止垃圾回收。 如果探查器尝试调用信息方法（例如，`ICorProfilerInfo` 接口上的方法），该方法可能会触发垃圾回收，则信息性方法将失败，并出现 CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT。  
  
 下表显示了禁止垃圾回收的回调方法，以及可能触发垃圾回收的信息性方法。 如果探查器在列出的回调方法之一内执行并调用列出的信息性方法之一，则该信息性方法将失败，并 CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT。  
  
|禁止垃圾回收的回调方法|触发垃圾回收的信息性方法|  
|------------------------------------------------------|------------------------------------------------------------|  
|[ThreadAssignedToOSThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md)<br /><br /> [ExceptionUnwindFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)<br /><br /> [ExceptionUnwindFunctionLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)<br /><br /> [ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)<br /><br /> [ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)<br /><br /> [ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)<br /><br /> [RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)<br /><br /> [RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)<br /><br /> [RuntimeSuspendAborted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)<br /><br /> [RuntimeThreadSuspended](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)<br /><br /> [RuntimeThreadResumed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)<br /><br /> [MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)<br /><br /> [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)<br /><br /> [ObjectsAllocatedByClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md)<br /><br /> [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)<br /><br /> [HandleCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md)<br /><br /> [HandleDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md)<br /><br /> [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)<br /><br /> [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)|[GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md)<br /><br /> [SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)<br /><br /> [SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)<br /><br /> [ForceGC](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md)<br /><br /> [GetClassFromToken](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromtoken-method.md)<br /><br /> [GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)<br /><br /> [GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)<br /><br /> [GetAppDomainInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getappdomaininfo-method.md)<br /><br /> [EnumModules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)<br /><br /> [RequestProfilerDetach](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-requestprofilerdetach-method.md)<br /><br /> [GetAppDomainsContainingModule](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getappdomainscontainingmodule-method.md)|  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ICorProfilerCallback2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [ICorProfilerCallback3 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)
- [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
- [ICorProfilerInfo3 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [Profiling 接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [分析](../../../../docs/framework/unmanaged-api/profiling/index.md)
