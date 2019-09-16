---
title: ICorProfilerCallback2 接口
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2
helpviewer_keywords:
- ICorProfilerCallback2 interface [.NET Framework profiling]
ms.assetid: 4a261dba-450d-4f1f-8d98-865b58bfc992
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d36d8ef3bfdbd6a1acf787a91003e2ff3139a4d9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963966"
---
# <a name="icorprofilercallback2-interface"></a>ICorProfilerCallback2 接口
提供公共语言运行时（CLR）用于在探查器订阅的事件发生时通知代码探查器的方法。 `ICorProfilerCallback2` 接口是 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) 接口的扩展。 也就是说，它提供 .NET Framework 版本2.0 中引入的新回调。  
  
> [!NOTE]
> 如果成功，则每个方法实现都必须返回值为 S_OK 的 HRESULT，否则返回 E_FAIL。 目前，CLR 将忽略每个回调返回的 HRESULT （ [ICorProfilerCallback：： ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)除外）。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[FinalizeableObjectQueued 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md)|通知代码探查器，具有终结器的对象已排入终结器线程，以执行其`Finalize`方法。|  
|[GarbageCollectionFinished 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)|通知探查器垃圾回收已完成，并为其发出了所有垃圾回收回调。|  
|[GarbageCollectionStarted 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)|通知代码探查器已开始垃圾回收。|  
|[HandleCreated 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md)|通知代码探查器已创建垃圾回收句柄。|  
|[HandleDestroyed 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md)|通知代码探查器垃圾回收句柄已销毁。|  
|[RootReferences2 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)|发生垃圾回收后，通知探查器有关根引用的信息。 此方法是[ICorProfilerCallback：： RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)方法的扩展。|  
|[SurvivingReferences 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md)|通知探查器有关垃圾回收已保留下来的对象引用。|  
|[ThreadNameChanged 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-threadnamechanged-method.md)|通知代码探查器线程的名称已更改。|  
  
## <a name="remarks"></a>备注  
 CLR 调用`ICorProfilerCallback` （或`ICorProfilerCallback2`）接口中的方法，以便在探查器已订阅的事件发生时通知探查器。 这是 CLR 与代码探查器进行通信时所使用的主回调接口。  
  
 代码探查器必须实现`ICorProfilerCallback`接口的方法。 对于 .NET Framework 2.0 及更高版本，探查器还必须实现`ICorProfilerCallback2`方法。 如果成功，则每个方法实现都必须返回值为 S_OK 的 HRESULT，否则返回 E_FAIL。 目前，CLR 将忽略每个回调返回的 HRESULT （ [ICorProfilerCallback：： ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)除外）。  
  
 代码探查器必须在 Microsoft Windows 注册表中注册，它是实现`ICorProfilerCallback`和`ICorProfilerCallback2`接口的 COM 对象。 代码探查器通过调用[ICorProfilerInfo：： SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)订阅要接收通知的事件。 通常在探查器的[ICorProfilerCallback：： Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)实现中完成此操作。 然后，探查器可以在事件即将发生或刚刚发生在正在执行的运行时进程中时接收来自运行时的通知。  
  
> [!NOTE]
> 探查器将注册一个 COM 对象。 如果探查器的目标 .NET Framework 版本1.0 或1.1，则该 COM 对象只需实现的方法`ICorProfilerCallback`。 如果目标 .NET Framework 版本2.0 及更高版本，则 COM 对象还必须实现的`ICorProfilerCallback2`方法。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Corprof.idl，Corprof.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [Profiling 接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ICorProfilerCallback3 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)
- [ICorProfilerCallback4 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
