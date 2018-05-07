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
ms.openlocfilehash: c6a218b58ed2ab40505204768f7d6071dea6db5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallback2-interface"></a>ICorProfilerCallback2 接口
提供公共语言运行时 (CLR) 用于探查器已订阅的事件发生时通知代码探查器的方法。 `ICorProfilerCallback2`接口是的扩展[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)接口。 也就是说，它提供了.NET Framework 2.0 版中引入的新回调。  
  
> [!NOTE]
>  每个方法实现必须返回一个 HRESULT，则为 S_OK 成功则 E_FAIL 失败的值。 目前，CLR 将忽略除每个回调返回的 HRESULT [icorprofilercallback:: Objectreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[FinalizeableObjectQueued 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md)|通知代码探查器已排队具有终结器的对象发送至终结器线程的执行其`Finalize`方法。|  
|[GarbageCollectionFinished 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)|通知探查器，垃圾回收已完成，并为其颁发的所有垃圾回收回调。|  
|[GarbageCollectionStarted 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)|通知代码探查器垃圾回收已启动。|  
|[HandleCreated 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md)|通知代码探查器已创建了垃圾回收句柄。|  
|[HandleDestroyed 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md)|通知垃圾回收句柄已销毁代码探查器。|  
|[RootReferences2 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)|垃圾回收发生后，请通知有关根引用探查器。 此方法是扩展的[icorprofilercallback:: Rootreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)方法。|  
|[SurvivingReferences 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md)|通知探查器有关垃圾回收中幸存的对象引用。|  
|[ThreadNameChanged 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-threadnamechanged-method.md)|通知代码探查器线程的名称已更改。|  
  
## <a name="remarks"></a>备注  
 CLR 中调用一个方法`ICorProfilerCallback`(或`ICorProfilerCallback2`) 通知探查器必须订阅该事件时探查器接口时发生。 这是通过该 CLR 代码探查器与进行通信的主回调接口。  
  
 代码探查器必须实现的方法`ICorProfilerCallback`接口。 对于.NET Framework 2.0 和更高版本，探查器还必须实现`ICorProfilerCallback2`方法。 每个方法实现必须返回一个 HRESULT，则为 S_OK 成功则 E_FAIL 失败的值。 目前，CLR 将忽略除每个回调返回的 HRESULT [icorprofilercallback:: Objectreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)。  
  
 代码探查器必须注册在 Microsoft Windows 注册表中，其实现的 COM 对象`ICorProfilerCallback`和`ICorProfilerCallback2`接口。 代码探查器订阅它想要通过调用接收通知的事件[icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)。 这通常是在探查器的实现中的[icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)。 探查器然后就能够从运行时接收通知，事件即将发生或正在执行的运行时进程中只出现时。  
  
> [!NOTE]
>  探查器注册的单个 COM 对象。 如果探查器面向.NET Framework 版本 1.0 或 1.1，该 COM 对象仅需要实现的方法`ICorProfilerCallback`。 如果针对.NET Framework 2.0 版和更高版本，COM 对象还必须实现的方法`ICorProfilerCallback2`。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [Profiling 接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback3 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 [ICorProfilerCallback4 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
