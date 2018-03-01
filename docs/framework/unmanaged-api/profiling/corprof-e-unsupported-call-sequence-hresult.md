---
title: CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE
helpviewer_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT [.NET Framework profiling]
ms.assetid: f2fc441f-d62e-4f72-a011-354ea13c8c59
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3694e08555df3ad91fbfcc35b6eb385bd24ce3c0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corprofeunsupportedcallsequence-hresult"></a>CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT
.NET Framework 2.0 版中引入了 CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT。 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]以下两种情况返回此 HRESULT:  
  
-   当劫持探查器强制重置线程的时注册上下文在任意时间，以便线程试图访问处于不一致状态的结构。  
  
-   探查器尝试调用触发禁止垃圾回收的回调方法中的垃圾回收的信息性方法时。  
  
 这两个方案以下各节所述。  
  
## <a name="hijacking-profilers"></a>拦截探查器  
 （这种情况下是主要问题劫持探查器，尽管有非劫持探查器在哪里可以看到此 HRESULT 的情况。）  
  
 在此方案中，劫持探查器强制重置线程的寄存器上下文在任意时间，以便线程可以输入探查器代码或重新输入公共语言运行时 (CLR) 通过[ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)方法。  
  
 许多分析 API 提供了用于在 CLR 中的数据结构点的 Id。 许多`ICorProfilerInfo`调用只是读取这些数据结构的信息，并将它们传回。 但是，CLR 可能会更改这些结构中的内容，如运行，并且它可能使用锁若要这样做。 假设 CLR 已保存 （或尝试获取） 时锁定探查器劫持线程。 如果线程重新进入 CLR，并尝试执行更多的锁或检查正被修改的结构，这些结构可能处于不一致状态。 在这种情况下很容易发生死锁和访问冲突。  
  
 一般情况下，执行时非劫持探查器内的代码[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)方法并调用到`ICorProfilerInfo`方法与有效的参数，它不应发生死锁或收到访问冲突。 例如，探查器中运行的代码[icorprofilercallback:: Classloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)方法通过调用可能会要求有关类信息[icorprofilerinfo2:: Getclassidinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)方法。 该代码可能会收到一个 CORPROF_E_DATAINCOMPLETE HRESULT，指示信息不可用;但是，它将不发生死锁或收到访问冲突。 此类调入`ICorProfilerInfo`称为同步，因为它们源自`ICorProfilerCallback`方法。  
  
 但是，托管的线程中执行不在两者之间的代码`ICorProfilerCallback`方法，则认为进行的异步调用。 在.NET Framework 版本 1 中，很难确定中的异步调用可能会发生什么。 调用可能发生死锁、 崩溃，或为提供无效的答案。 .NET Framework 2.0 版引入了一些简单的检查，以帮助你避免此问题。 在.NET Framework 2.0 中，如果调用不安全`ICorProfilerInfo`异步函数，它将失败，CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT。  
  
 一般情况下，异步调用是不安全的。 但是，以下方法是安全的专门支持异步调用：  
  
-   [GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)  
  
-   [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)  
  
-   [GetCurrentThreadID](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcurrentthreadid-method.md)  
  
-   [GetThreadContext](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadcontext-method.md)  
  
-   [GetThreadAppDomain](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadappdomain-method.md)  
  
-   [GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md)  
  
-   [GetFunctionInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctioninfo-method.md)  
  
-   [GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)  
  
-   [GetCodeInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcodeinfo-method.md)  
  
-   [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)  
  
-   [GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md)  
  
-   [GetClassIDInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md)  
  
-   [GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)  
  
-   [IsArrayClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-isarrayclass-method.md)  
  
-   [SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
  
-   [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)  
  
 有关其他信息，请参阅文章[我们使用 CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](http://go.microsoft.com/fwlink/?LinkId=169156) CLR 分析 API 博客中。  
  
## <a name="triggering-garbage-collections"></a>触发垃圾回收  
 此方案涉及到探查器回调方法中运行程序 (例如，一个的`ICorProfilerCallback`方法)，禁止垃圾回收。 如果探查器尝试调用信息性方法 (例如上的方法`ICorProfilerInfo`接口)，可能会触发垃圾回收，信息性的方法将失败，CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT。  
  
 下表显示可能会触发垃圾回收的信息性方法和禁止垃圾回收的回调方法。 如果探查器内列出的回调方法之一执行，并通过调用另外一个列出的信息性方法，该信息性的方法将失败并 CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT。  
  
|禁止垃圾回收的回叫方法|触发垃圾回收的信息性方法|  
|------------------------------------------------------|------------------------------------------------------------|  
|[ThreadAssignedToOSThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md)<br /><br /> [ExceptionUnwindFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)<br /><br /> [ExceptionUnwindFunctionLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)<br /><br /> [ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)<br /><br /> [ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)<br /><br /> [ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)<br /><br /> [RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)<br /><br /> [RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)<br /><br /> [RuntimeSuspendAborted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)<br /><br /> [RuntimeThreadSuspended](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)<br /><br /> [RuntimeThreadResumed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)<br /><br /> [MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)<br /><br /> [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)<br /><br /> [ObjectsAllocatedByClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md)<br /><br /> [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)<br /><br /> [HandleCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md)<br /><br /> [HandleDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md)<br /><br /> [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)<br /><br /> [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)|[GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md)<br /><br /> [SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)<br /><br /> [SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)<br /><br /> [ForceGC](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md)<br /><br /> [GetClassFromToken](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromtoken-method.md)<br /><br /> [GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)<br /><br /> [GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)<br /><br /> [GetAppDomainInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getappdomaininfo-method.md)<br /><br /> [EnumModules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)<br /><br /> [RequestProfilerDetach](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-requestprofilerdetach-method.md)<br /><br /> [GetAppDomainsContainingModule](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getappdomainscontainingmodule-method.md)|  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [ICorProfilerCallback3 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 [ICorProfilerInfo3 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [Profiling 接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [分析](../../../../docs/framework/unmanaged-api/profiling/index.md)
