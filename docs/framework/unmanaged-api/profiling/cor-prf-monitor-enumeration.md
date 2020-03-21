---
title: COR_PRF_MONITOR 枚举
ms.date: 03/30/2017
api_name:
- COR_PRF_MONITOR
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MONITOR
helpviewer_keywords:
- COR_PRF_MONITOR enumeration [.NET Framework profiling]
ms.assetid: 9294d702-b4e5-441c-a930-e63d27b86bfd
topic_type:
- apiref
ms.openlocfilehash: b6c3dc78b9c503747c7a2d404706eb797790b931
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175195"
---
# <a name="cor_prf_monitor-enumeration"></a>COR_PRF_MONITOR 枚举
包含用于指定探查器希望订阅的行为、功能或事件的值。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum {  
    COR_PRF_MONITOR_NONE                = 0x00000000,  
    COR_PRF_MONITOR_FUNCTION_UNLOADS    = 0x00000001,  
    COR_PRF_MONITOR_CLASS_LOADS         = 0x00000002,  
    COR_PRF_MONITOR_MODULE_LOADS        = 0x00000004,  
    COR_PRF_MONITOR_ASSEMBLY_LOADS      = 0x00000008,  
    COR_PRF_MONITOR_APPDOMAIN_LOADS     = 0x00000010,  
    COR_PRF_MONITOR_JIT_COMPILATION     = 0x00000020,  
    COR_PRF_MONITOR_EXCEPTIONS          = 0x00000040,  
    COR_PRF_MONITOR_GC                  = 0x00000080,  
    COR_PRF_MONITOR_OBJECT_ALLOCATED    = 0x00000100,  
    COR_PRF_MONITOR_THREADS             = 0x00000200,  
    COR_PRF_MONITOR_REMOTING            = 0x00000400,  
    COR_PRF_MONITOR_CODE_TRANSITIONS    = 0x00000800,  
    COR_PRF_MONITOR_ENTERLEAVE          = 0x00001000,  
    COR_PRF_MONITOR_CCW                 = 0x00002000,  
    COR_PRF_MONITOR_REMOTING_COOKIE     = 0x00004000 |
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_REMOTING_ASYNC      = 0x00008000 |
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_SUSPENDS            = 0x00010000,  
    COR_PRF_MONITOR_CACHE_SEARCHES      = 0x00020000,  
    COR_PRF_ENABLE_REJIT                = 0x00040000,  
    COR_PRF_ENABLE_INPROC_DEBUGGING     = 0x00080000,  
    COR_PRF_ENABLE_JIT_MAPS             = 0x00100000,  
    COR_PRF_DISABLE_INLINING            = 0x00200000,  
    COR_PRF_DISABLE_OPTIMIZATIONS       = 0x00400000,  
    COR_PRF_ENABLE_OBJECT_ALLOCATED     = 0x00800000,  
    COR_PRF_MONITOR_CLR_EXCEPTIONS      = 0x01000000,  
    COR_PRF_MONITOR_ALL                 = 0x0107FFFF,  
    COR_PRF_ENABLE_FUNCTION_ARGS        = 0X02000000,  
    COR_PRF_ENABLE_FUNCTION_RETVAL      = 0X04000000,  
    COR_PRF_ENABLE_FRAME_INFO           = 0X08000000,  
    COR_PRF_ENABLE_STACK_SNAPSHOT       = 0X10000000,  
    COR_PRF_USE_PROFILE_IMAGES          = 0x20000000,  
    COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST  
                                        = 0x40000000,  
    COR_PRF_DISABLE_ALL_NGEN_IMAGES     = 0x80000000,  
    COR_PRF_ALL                         = 0x8FFFFFFF,  
    COR_PRF_REQUIRE_PROFILE_IMAGE       = COR_PRF_USE_PROFILE_IMAGES |
                                          COR_PRF_MONITOR_CODE_TRANSITIONS |
                                          COR_PRF_MONITOR_ENTERLEAVE,  
    COR_PRF_ALLOWABLE_AFTER_ATTACH      = COR_PRF_MONITOR_THREADS |  
                                          COR_PRF_MONITOR_MODULE_LOADS |  
                                          COR_PRF_MONITOR_ASSEMBLY_LOADS |  
                                          COR_PRF_MONITOR_APPDOMAIN_LOADS |  
                                          COR_PRF_ENABLE_STACK_SNAPSHOT |  
                                          COR_PRF_MONITOR_GC |  
                                          COR_PRF_MONITOR_SUSPENDS |  
                                          COR_PRF_MONITOR_CLASS_LOADS |  
                                          COR_PRF_MONITOR_JIT_COMPILATION,  
    COR_PRF_MONITOR_IMMUTABLE           = COR_PRF_MONITOR_CODE_TRANSITIONS |  
                                          COR_PRF_MONITOR_REMOTING |  
                                          COR_PRF_MONITOR_REMOTING_COOKIE |  
                                          COR_PRF_MONITOR_REMOTING_ASYNC |  
                                          COR_PRF_ENABLE_REJIT |  
                                          COR_PRF_ENABLE_INPROC_DEBUGGING |  
                                          COR_PRF_ENABLE_JIT_MAPS |  
                                          COR_PRF_DISABLE_OPTIMIZATIONS |  
                                          COR_PRF_DISABLE_INLINING |  
                                          COR_PRF_ENABLE_OBJECT_ALLOCATED |  
                                          COR_PRF_ENABLE_FUNCTION_ARGS |  
                                          COR_PRF_ENABLE_FUNCTION_RETVAL |  
                                          COR_PRF_ENABLE_FRAME_INFO |  
                                          COR_PRF_USE_PROFILE_IMAGES |  
                     COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST |  
                                          COR_PRF_DISABLE_ALL_NGEN_IMAGES  
} COR_PRF_MONITOR;  
```  
  
## <a name="members"></a>成员  
 以下各节按`COR_PRF_MONITOR`类别列出枚举成员。 类别包括：  
  
- [未设置标志](#None)  
  
- [回调标志](#Callback)  
  
- [功能启用标志](#Feature)  
  
- [配置标志](#Config)  
  
- [复合标志](#Composite)  
  
<a name="None"></a>
### <a name="no-flags-set"></a>未设置标志  
  
|成员|说明|  
|------------|-----------------|  
|`COR_PRF_MONITOR_NONE`|不设置任何标志。|  
  
<a name="Callback"></a>
### <a name="callback-flags"></a>回调标志  
  
|成员|说明|  
|------------|-----------------|  
|`COR_PRF_MONITOR_ALL`|启用所有回调事件。|  
|`COR_PRF_MONITOR_APPDOMAIN_LOADS`|控制`AppDomainCreation*`[ICorProfiler 回调](icorprofilercallback-interface.md)接口中的 和`AppDomainShutdown*`回调。|  
|`COR_PRF_MONITOR_ASSEMBLY_LOADS`|控制`AssemblyLoad*`[ICorProfiler 回调](icorprofilercallback-interface.md)接口中的 和`AssemblyUnload*`回调。|  
|`COR_PRF_MONITOR_CACHE_SEARCHES`|`JITCachedFunctionSearch*`控制[ICorProfiler 回调](icorprofilercallback-interface.md)接口中的回调。<br /><br /> 此标志的行为在 .NET Framework 版本 2.0 中发生了变化。|  
|`COR_PRF_MONITOR_CCW`|`COMClassicVTable*`控制[ICorProfiler 回调](icorprofilercallback-interface.md)接口中的回调。|  
|`COR_PRF_MONITOR_CLASS_LOADS`|控制`ClassLoad*`[ICorProfiler 回调](icorprofilercallback-interface.md)接口中的 和`ClassUnload*`回调。|  
|`COR_PRF_MONITOR_CLR_EXCEPTIONS`|`ExceptionCLRCatcher*`控制[ICorProfiler 回调](icorprofilercallback-interface.md)接口中的回调。|  
|`COR_PRF_MONITOR_CODE_TRANSITIONS`|在[ICorProfiler 回调](icorprofilercallback-interface.md)接口中控制[非托管到托管转换](icorprofilercallback-unmanagedtomanagedtransition-method.md)和[托管到非托管转换](icorprofilercallback-managedtounmanagedtransition-method.md)回调|  
|`COR_PRF_MONITOR_ENTERLEAVE`|控制`FunctionEnter*`、 `FunctionLeave*``FunctionTailCall*`[和分析全局静态函数](profiling-global-static-functions.md)。|  
|`COR_PRF_MONITOR_EXCEPTIONS`|在[ICorProfiler](icorprofilercallback-interface.md)回调`ExceptionSearch*`接口`ExceptionOSHandler*`中`ExceptionUnwind*`控制[异常引发](icorprofilercallback-exceptionthrown-method.md)回调和 、 、 和`ExceptionCatcher*`回调。|  
|`COR_PRF_MONITOR_FUNCTION_UNLOADS`|在[ICorProfiler 回调](icorprofilercallback-interface.md)接口中控制[函数未加载启动](icorprofilercallback-functionunloadstarted-method.md)回调。|  
|`COR_PRF_MONITOR_GC`|`ICorProfilerCallback*`控制在接口中[启动的垃圾回收](icorprofilercallback2-garbagecollectionstarted-method.md)、[垃圾回收完成](icorprofilercallback2-garbagecollectionfinished-method.md)、[移动引用](icorprofilercallback-movedreferences-method.md)、[移动引用 2、](icorprofilercallback4-movedreferences2-method.md)[幸存引用](icorprofilercallback2-survivingreferences-method.md)、[幸存引用 2、](icorprofilercallback4-survivingreferences2-method.md)[对象引用](icorprofilercallback-objectreferences-method.md)、[对象分配、](icorprofilercallback-objectsallocatedbyclass-method.md)[根引用](icorprofilercallback-rootreferences-method.md)、[根引用 2、](icorprofilercallback2-rootreferences2-method.md)[句柄已创建](icorprofilercallback2-handlecreated-method.md)、[句柄销毁](icorprofilercallback2-handledestroyed-method.md)和[可最终对象排队](icorprofilercallback2-finalizeableobjectqueued-method.md)回调。 分配`COR_PRF_MONITOR_GC`后，并发垃圾回收将被关闭。|  
|`COR_PRF_MONITOR_JIT_COMPILATION`|控制`JITCompilation*`[ICorProfiler 回调](icorprofilercallback-interface.md)接口中的[.JIT功能音调](icorprofilercallback-jitfunctionpitched-method.md)和[JITInlining](icorprofilercallback-jitinlining-method.md)回调。|  
|`COR_PRF_MONITOR_MODULE_LOADS`|控制`ModuleLoad*`[ICorProfiler 回调](icorprofilercallback-interface.md)接口中的 、`ModuleUnload*`和[模块附加组件](icorprofilercallback-moduleattachedtoassembly-method.md)回调。|  
|`COR_PRF_MONITOR_OBJECT_ALLOCATED`|在[ICorProfiler 回调](icorprofilercallback-interface.md)接口中控制[对象分配](icorprofilercallback-objectallocated-method.md)回调。|  
|`COR_PRF_MONITOR_REMOTING`|`Remoting*`控制[ICorProfiler 回调](icorprofilercallback-interface.md)接口中的回调。|  
|`COR_PRF_MONITOR_REMOTING_ASYNC`|控制 `Remoting*` 回调是否将监视异步事件。|  
|`COR_PRF_MONITOR_REMOTING_COOKIE`|控制是否向 `Remoting*` 回调传递 Cookie。|  
|`COR_PRF_MONITOR_SUSPENDS`|在`RuntimeSuspend*`[ICorProfiler 回调](icorprofilercallback-interface.md)接口中控制`RuntimeResume*`[、、运行时线程挂起](icorprofilercallback-runtimethreadsuspended-method.md)和[运行时线程恢复](icorprofilercallback-runtimethreadresumed-method.md)回调。|  
|`COR_PRF_MONITOR_THREADS`|在[ICorProfiler 回调](icorprofilercallback-interface.md)和[ICorProfilerCallback2](icorprofilercallback2-interface.md)接口中控制[线程创建](icorprofilercallback-threadcreated-method.md)、[线程销毁](icorprofilercallback-threaddestroyed-method.md)、[线程分配到 OS 线程](icorprofilercallback-threadassignedtoosthread-method.md)和[线程名称更改](icorprofilercallback2-threadnamechanged-method.md)回调。|  
  
<a name="Feature"></a>
### <a name="feature-enabling-flags"></a>功能启用标志  
  
|成员|说明|  
|------------|-----------------|  
|`COR_PRF_ENABLE_FRAME_INFO`|通过调用[GetEinfo2](icorprofilerinfo2-getfunctioninfo2-method.md)方法，使用`COR_PRF_FRAME_INFO`[函数Enter2](functionenter2-function.md)回调返回的值，启用对泛型函数的精确`ClassID`检索。|  
|`COR_PRF_ENABLE_FUNCTION_ARGS`|使用[函数Enter2](functionenter2-function.md)回调或[函数Enter3与Info](functionenter3withinfo-function.md)回调和[GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md)方法启用参数跟踪。|  
|`COR_PRF_ENABLE_FUNCTION_RETVAL`|通过使用[函数Leave2](functionleave2-function.md)回调或[函数Leave3Info](functionleave3withinfo-function.md)回调和[Get功能Leave3Info](icorprofilerinfo3-getfunctionleave3info-method.md)方法，启用返回值的跟踪。|  
|`COR_PRF_ENABLE_INPROC_DEBUGGING`|已弃用。<br /><br /> 不支持进程内调试。 此标志无效。|  
|`COR_PRF_ENABLE_JIT_MAPS`|已弃用。<br /><br /> 允许探查器使用[GetILToNativemap](icorprofilerinfo-getiltonativemapping-method.md)获取 IL 到本机映射。 从 .NET Framework 2.0 开始，运行时始终跟踪从 IL 到本机代码的映射；因此，始终认为要设置此标志。|  
|`COR_PRF_ENABLE_OBJECT_ALLOCATED`|通知运行时：探查器可能需要对象分配通知。 在初始化期间必须设置此标志。 它允许探查器随后使用`COR_PRF_MONITOR_OBJECT_ALLOCATED`标志接收[对象分配的](icorprofilercallback-objectallocated-method.md)回调。|  
|`COR_PRF_ENABLE_REJIT`|启用对请求[ReJIT](icorprofilerinfo4-requestrejit-method.md)和[请求还原方法的](icorprofilerinfo4-requestrevert-method.md)调用。 探查器必须在启动时设置此标志。  如果探查器指定此标志，它还必须指定 `COR_PRF_DISABLE_ALL_NGEN_IMAGES`。|  
|`COR_PRF_ENABLE_STACK_SNAPSHOT`|启用对[DoStack 快照](icorprofilerinfo2-dostacksnapshot-method.md)方法的调用。|  
  
<a name="Config"></a>
### <a name="configuration-flags"></a>配置标志  
  
|成员|说明|  
|------------|-----------------|  
|`COR_PRF_DISABLE_ALL_NGEN_IMAGES`|阻止所有本机映像（包括增强型探查器映像）进行加载。  如果此标志和 `COR_PRF_USE_PROFILE_IMAGES` 标志都已指定，将使用 `COR_PRF_DISABLE_ALL_NGEN_IMAGES`。|  
|`COR_PRF_DISABLE_INLINING`|禁用所有内联。|  
|`COR_PRF_DISABLE_OPTIMIZATIONS`|禁用所有代码优化。|  
|`COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST`|禁用正常情况下在实时 (JIT) 编译和完全信任程序集类加载过程中完成的安全透明度检查。 这可以使某些检测更容易执行。|  
|`COR_PRF_USE_PROFILE_IMAGES`|导致执行本机映像搜索，以查找增强型探查器映像。 对于给定程序集，如果找不到增强型探查器映像，则公共语言运行时将回退到该程序集的 JIT。 如果此标志和 `COR_PRF_DISABLE_ALL_NGEN_IMAGES` 标志都已指定，将使用 `COR_PRF_DISABLE_ALL_NGEN_IMAGES`。|  
  
<a name="Composite"></a>
### <a name="composite-flags"></a>复合标志  
  
|成员|说明|  
|------------|-----------------|  
|`COR_PRF_ALL`|表示所有 `COR_PRF_MONITOR` 标志值。|  
|`COR_PRF_ALLOWABLE_AFTER_ATTACH`|表示可以在将探查器附加到运行中的应用之后进行设置的所有 `COR_PRF_MONITOR` 标志。 语法部分指示此位掩码中存在的各个标志。|  
|`COR_PRF_MONITOR_ALL`|启用所有回调事件。|  
|`COR_PRF_MONITOR_IMMUTABLE`|表示只能在初始化过程中进行设置的所有 `COR_PRF_MONITOR` 标志。 如果在初始化后尝试更改这些标志中的任一标志，则会返回一个指示失败的 `HRESULT` 值。|  
|`COR_PRF_REQUIRE_PROFILE_IMAGE`|表示需要配置增强的映像的所有 `COR_PRF_MONITOR` 标志。|  
  
## <a name="remarks"></a>备注  
 值`COR_PRF_MONITOR`与[ICorProfilerInfo：：GetEventMask](icorprofilerinfo-geteventmask-method.md)和[ICorProfilerInfo：setEventMask](icorprofilerinfo-seteventmask-method.md)方法一起使用，用于定义通用语言运行时对探查器的事件通知。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [分析枚举](profiling-enumerations.md)
- [GetEventMask 方法](icorprofilerinfo-geteventmask-method.md)
- [SetEventMask 方法](icorprofilerinfo-seteventmask-method.md)
