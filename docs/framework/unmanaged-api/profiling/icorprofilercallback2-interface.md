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
ms.openlocfilehash: 83c72704ccb01baf68a3cacb6252367e07909fa8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178992"
---
# <a name="icorprofilercallback2-interface"></a><span data-ttu-id="b3d21-102">ICorProfilerCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="b3d21-102">ICorProfilerCallback2 Interface</span></span>
<span data-ttu-id="b3d21-103">提供了公共语言运行时 (CLR) 用于探查器已订阅的事件发生时通知代码探查器的方法。</span><span class="sxs-lookup"><span data-stu-id="b3d21-103">Provides methods that are used by the common language runtime (CLR) to notify a code profiler when the events to which the profiler has subscribed occur.</span></span> <span data-ttu-id="b3d21-104">`ICorProfilerCallback2`接口是的扩展[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="b3d21-104">The `ICorProfilerCallback2` interface is an extension of the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span> <span data-ttu-id="b3d21-105">也就是说，它提供了.NET Framework 2.0 版中引入的新回调。</span><span class="sxs-lookup"><span data-stu-id="b3d21-105">That is, it provides new callbacks introduced in the .NET Framework version 2.0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3d21-106">每个方法的实现必须返回一个值，则为 S_OK 成功则 E_FAIL 失败的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="b3d21-106">Each method implementation must return an HRESULT having a value of S_OK on success or E_FAIL on failure.</span></span> <span data-ttu-id="b3d21-107">目前，CLR 将忽略除每个回调返回的 HRESULT [icorprofilercallback:: Objectreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)。</span><span class="sxs-lookup"><span data-stu-id="b3d21-107">Currently, the CLR ignores the HRESULT that is returned by each callback except [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b3d21-108">方法</span><span class="sxs-lookup"><span data-stu-id="b3d21-108">Methods</span></span>  
  
|<span data-ttu-id="b3d21-109">方法</span><span class="sxs-lookup"><span data-stu-id="b3d21-109">Method</span></span>|<span data-ttu-id="b3d21-110">描述</span><span class="sxs-lookup"><span data-stu-id="b3d21-110">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b3d21-111">FinalizeableObjectQueued 方法</span><span class="sxs-lookup"><span data-stu-id="b3d21-111">FinalizeableObjectQueued Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md)|<span data-ttu-id="b3d21-112">通知代码探查器已列入执行终结器线程上具有终结器的对象及其`Finalize`方法。</span><span class="sxs-lookup"><span data-stu-id="b3d21-112">Notifies the code profiler that an object with a finalizer has been queued to the finalizer thread for execution of its `Finalize` method.</span></span>|  
|[<span data-ttu-id="b3d21-113">GarbageCollectionFinished 方法</span><span class="sxs-lookup"><span data-stu-id="b3d21-113">GarbageCollectionFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)|<span data-ttu-id="b3d21-114">通知探查器，垃圾回收已完成并已对它发出所有垃圾回收回调。</span><span class="sxs-lookup"><span data-stu-id="b3d21-114">Notifies the profiler that a garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>|  
|[<span data-ttu-id="b3d21-115">GarbageCollectionStarted 方法</span><span class="sxs-lookup"><span data-stu-id="b3d21-115">GarbageCollectionStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)|<span data-ttu-id="b3d21-116">通知垃圾回收已启动代码探查器。</span><span class="sxs-lookup"><span data-stu-id="b3d21-116">Notifies the code profiler that a garbage collection has started.</span></span>|  
|[<span data-ttu-id="b3d21-117">HandleCreated 方法</span><span class="sxs-lookup"><span data-stu-id="b3d21-117">HandleCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md)|<span data-ttu-id="b3d21-118">通知代码探查器已创建了垃圾回收句柄。</span><span class="sxs-lookup"><span data-stu-id="b3d21-118">Notifies the code profiler that a garbage collection handle has been created.</span></span>|  
|[<span data-ttu-id="b3d21-119">HandleDestroyed 方法</span><span class="sxs-lookup"><span data-stu-id="b3d21-119">HandleDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md)|<span data-ttu-id="b3d21-120">通知垃圾回收句柄已被销毁代码探查器。</span><span class="sxs-lookup"><span data-stu-id="b3d21-120">Notifies the code profiler that a garbage collection handle has been destroyed.</span></span>|  
|[<span data-ttu-id="b3d21-121">RootReferences2 方法</span><span class="sxs-lookup"><span data-stu-id="b3d21-121">RootReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)|<span data-ttu-id="b3d21-122">在发生垃圾回收后，请通知有关根引用探查器。</span><span class="sxs-lookup"><span data-stu-id="b3d21-122">Notifies the profiler about root references after a garbage collection has occurred.</span></span> <span data-ttu-id="b3d21-123">此方法是的扩展[icorprofilercallback:: Rootreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b3d21-123">This method is an extension of the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) method.</span></span>|  
|[<span data-ttu-id="b3d21-124">SurvivingReferences 方法</span><span class="sxs-lookup"><span data-stu-id="b3d21-124">SurvivingReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md)|<span data-ttu-id="b3d21-125">通知垃圾回收中幸存的对象引用有关探查器。</span><span class="sxs-lookup"><span data-stu-id="b3d21-125">Notifies the profiler about object references that have survived a garbage collection.</span></span>|  
|[<span data-ttu-id="b3d21-126">ThreadNameChanged 方法</span><span class="sxs-lookup"><span data-stu-id="b3d21-126">ThreadNameChanged Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-threadnamechanged-method.md)|<span data-ttu-id="b3d21-127">通知代码探查器线程的名称已更改。</span><span class="sxs-lookup"><span data-stu-id="b3d21-127">Notifies the code profiler that the name of a thread has changed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3d21-128">备注</span><span class="sxs-lookup"><span data-stu-id="b3d21-128">Remarks</span></span>  
 <span data-ttu-id="b3d21-129">CLR 调用中的方法`ICorProfilerCallback`(或`ICorProfilerCallback2`) 接口以通知探查器在某一事件，探查器已订阅的会发生。</span><span class="sxs-lookup"><span data-stu-id="b3d21-129">The CLR calls a method in the `ICorProfilerCallback` (or `ICorProfilerCallback2`) interface to notify the profiler when an event, to which the profiler had subscribed, occurs.</span></span> <span data-ttu-id="b3d21-130">这是通过其 CLR 代码探查器与进行通信的主回调接口。</span><span class="sxs-lookup"><span data-stu-id="b3d21-130">This is the primary callback interface through which the CLR communicates with the code profiler.</span></span>  
  
 <span data-ttu-id="b3d21-131">代码探查器必须实现的方法`ICorProfilerCallback`接口。</span><span class="sxs-lookup"><span data-stu-id="b3d21-131">A code profiler must implement the methods of the `ICorProfilerCallback` interface.</span></span> <span data-ttu-id="b3d21-132">有关.NET Framework 2.0 和更高版本中，探查器还必须实现`ICorProfilerCallback2`方法。</span><span class="sxs-lookup"><span data-stu-id="b3d21-132">For the .NET Framework 2.0 and later versions, the profiler must also implement the `ICorProfilerCallback2` methods.</span></span> <span data-ttu-id="b3d21-133">每个方法的实现必须返回一个值，则为 S_OK 成功则 E_FAIL 失败的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="b3d21-133">Each method implementation must return an HRESULT having a value of S_OK on success or E_FAIL on failure.</span></span> <span data-ttu-id="b3d21-134">目前，CLR 将忽略除每个回调返回的 HRESULT [icorprofilercallback:: Objectreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)。</span><span class="sxs-lookup"><span data-stu-id="b3d21-134">Currently, the CLR ignores the HRESULT that is returned by each callback except [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md).</span></span>  
  
 <span data-ttu-id="b3d21-135">代码探查器必须注册在 Microsoft Windows 注册表中，其 COM 对象，它实现`ICorProfilerCallback`和`ICorProfilerCallback2`接口。</span><span class="sxs-lookup"><span data-stu-id="b3d21-135">A code profiler must register in the Microsoft Windows registry, its COM object that implements the `ICorProfilerCallback` and `ICorProfilerCallback2` interfaces.</span></span> <span data-ttu-id="b3d21-136">代码探查器订阅它需要通过调用接收通知的事件[icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)。</span><span class="sxs-lookup"><span data-stu-id="b3d21-136">A code profiler subscribes to the events for which it wants to receive notification by calling [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md).</span></span> <span data-ttu-id="b3d21-137">这通常是在探查器的实现中的[icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)。</span><span class="sxs-lookup"><span data-stu-id="b3d21-137">This is usually done in the profiler's implementation of [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md).</span></span> <span data-ttu-id="b3d21-138">然后，探查器是能够从运行时接收通知事件即将发生或正在执行的运行时进程中只发生时。</span><span class="sxs-lookup"><span data-stu-id="b3d21-138">The profiler is then able to receive notification from the runtime when an event is about to occur or has just occurred in an executing runtime process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3d21-139">探查器注册的单个 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="b3d21-139">The profiler registers a single COM object.</span></span> <span data-ttu-id="b3d21-140">如果探查器面向.NET Framework 版本 1.0 或 1.1，该 COM 对象只需要实现的方法`ICorProfilerCallback`。</span><span class="sxs-lookup"><span data-stu-id="b3d21-140">If the profiler is targeting .NET Framework version 1.0 or 1.1, that COM object need only implement the methods of `ICorProfilerCallback`.</span></span> <span data-ttu-id="b3d21-141">如果它面向.NET Framework 2.0 版和更高版本，COM 对象还必须实现的方法`ICorProfilerCallback2`。</span><span class="sxs-lookup"><span data-stu-id="b3d21-141">If it is targeting .NET Framework version 2.0 and later, the COM object must also implement the methods of `ICorProfilerCallback2`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3d21-142">要求</span><span class="sxs-lookup"><span data-stu-id="b3d21-142">Requirements</span></span>  
 <span data-ttu-id="b3d21-143">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b3d21-143">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3d21-144">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b3d21-144">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b3d21-145">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3d21-145">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b3d21-146">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="b3d21-146">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b3d21-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="b3d21-147">See also</span></span>

- [<span data-ttu-id="b3d21-148">分析接口</span><span class="sxs-lookup"><span data-stu-id="b3d21-148">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="b3d21-149">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="b3d21-149">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="b3d21-150">ICorProfilerCallback3 接口</span><span class="sxs-lookup"><span data-stu-id="b3d21-150">ICorProfilerCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)
- [<span data-ttu-id="b3d21-151">ICorProfilerCallback4 接口</span><span class="sxs-lookup"><span data-stu-id="b3d21-151">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
