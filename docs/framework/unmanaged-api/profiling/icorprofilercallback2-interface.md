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
ms.openlocfilehash: c565d0fe37a091095b18a6d59308f159fe7b4554
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865735"
---
# <a name="icorprofilercallback2-interface"></a><span data-ttu-id="b5bdb-102">ICorProfilerCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="b5bdb-102">ICorProfilerCallback2 Interface</span></span>
<span data-ttu-id="b5bdb-103">提供公共语言运行时（CLR）用于在探查器订阅的事件发生时通知代码探查器的方法。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-103">Provides methods that are used by the common language runtime (CLR) to notify a code profiler when the events to which the profiler has subscribed occur.</span></span> <span data-ttu-id="b5bdb-104">`ICorProfilerCallback2` 接口是 [ICorProfilerCallback](icorprofilercallback-interface.md) 接口的扩展。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-104">The `ICorProfilerCallback2` interface is an extension of the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span> <span data-ttu-id="b5bdb-105">也就是说，它提供 .NET Framework 版本2.0 中引入的新回调。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-105">That is, it provides new callbacks introduced in the .NET Framework version 2.0.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b5bdb-106">每个方法实现都必须返回 HRESULT 的值 S_OK 为 "成功" 或 "E_FAIL 失败时"。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-106">Each method implementation must return an HRESULT having a value of S_OK on success or E_FAIL on failure.</span></span> <span data-ttu-id="b5bdb-107">目前，CLR 将忽略每个回调返回的 HRESULT （ [ICorProfilerCallback：： ObjectReferences](icorprofilercallback-objectreferences-method.md)除外）。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-107">Currently, the CLR ignores the HRESULT that is returned by each callback except [ICorProfilerCallback::ObjectReferences](icorprofilercallback-objectreferences-method.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b5bdb-108">方法</span><span class="sxs-lookup"><span data-stu-id="b5bdb-108">Methods</span></span>  
  
|<span data-ttu-id="b5bdb-109">方法</span><span class="sxs-lookup"><span data-stu-id="b5bdb-109">Method</span></span>|<span data-ttu-id="b5bdb-110">描述</span><span class="sxs-lookup"><span data-stu-id="b5bdb-110">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b5bdb-111">FinalizeableObjectQueued 方法</span><span class="sxs-lookup"><span data-stu-id="b5bdb-111">FinalizeableObjectQueued Method</span></span>](icorprofilercallback2-finalizeableobjectqueued-method.md)|<span data-ttu-id="b5bdb-112">通知代码探查器，具有终结器的对象已排入终结器线程，以执行其 `Finalize` 方法。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-112">Notifies the code profiler that an object with a finalizer has been queued to the finalizer thread for execution of its `Finalize` method.</span></span>|  
|[<span data-ttu-id="b5bdb-113">GarbageCollectionFinished 方法</span><span class="sxs-lookup"><span data-stu-id="b5bdb-113">GarbageCollectionFinished Method</span></span>](icorprofilercallback2-garbagecollectionfinished-method.md)|<span data-ttu-id="b5bdb-114">通知探查器垃圾回收已完成，并为其发出了所有垃圾回收回调。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-114">Notifies the profiler that a garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>|  
|[<span data-ttu-id="b5bdb-115">GarbageCollectionStarted 方法</span><span class="sxs-lookup"><span data-stu-id="b5bdb-115">GarbageCollectionStarted Method</span></span>](icorprofilercallback2-garbagecollectionstarted-method.md)|<span data-ttu-id="b5bdb-116">通知代码探查器已开始垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-116">Notifies the code profiler that a garbage collection has started.</span></span>|  
|[<span data-ttu-id="b5bdb-117">HandleCreated 方法</span><span class="sxs-lookup"><span data-stu-id="b5bdb-117">HandleCreated Method</span></span>](icorprofilercallback2-handlecreated-method.md)|<span data-ttu-id="b5bdb-118">通知代码探查器已创建垃圾回收句柄。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-118">Notifies the code profiler that a garbage collection handle has been created.</span></span>|  
|[<span data-ttu-id="b5bdb-119">HandleDestroyed 方法</span><span class="sxs-lookup"><span data-stu-id="b5bdb-119">HandleDestroyed Method</span></span>](icorprofilercallback2-handledestroyed-method.md)|<span data-ttu-id="b5bdb-120">通知代码探查器垃圾回收句柄已销毁。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-120">Notifies the code profiler that a garbage collection handle has been destroyed.</span></span>|  
|[<span data-ttu-id="b5bdb-121">RootReferences2 方法</span><span class="sxs-lookup"><span data-stu-id="b5bdb-121">RootReferences2 Method</span></span>](icorprofilercallback2-rootreferences2-method.md)|<span data-ttu-id="b5bdb-122">发生垃圾回收后，通知探查器有关根引用的信息。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-122">Notifies the profiler about root references after a garbage collection has occurred.</span></span> <span data-ttu-id="b5bdb-123">此方法是[ICorProfilerCallback：： RootReferences](icorprofilercallback-rootreferences-method.md)方法的扩展。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-123">This method is an extension of the [ICorProfilerCallback::RootReferences](icorprofilercallback-rootreferences-method.md) method.</span></span>|  
|[<span data-ttu-id="b5bdb-124">SurvivingReferences 方法</span><span class="sxs-lookup"><span data-stu-id="b5bdb-124">SurvivingReferences Method</span></span>](icorprofilercallback2-survivingreferences-method.md)|<span data-ttu-id="b5bdb-125">通知探查器有关垃圾回收已保留下来的对象引用。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-125">Notifies the profiler about object references that have survived a garbage collection.</span></span>|  
|[<span data-ttu-id="b5bdb-126">ThreadNameChanged 方法</span><span class="sxs-lookup"><span data-stu-id="b5bdb-126">ThreadNameChanged Method</span></span>](icorprofilercallback2-threadnamechanged-method.md)|<span data-ttu-id="b5bdb-127">通知代码探查器线程的名称已更改。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-127">Notifies the code profiler that the name of a thread has changed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5bdb-128">备注</span><span class="sxs-lookup"><span data-stu-id="b5bdb-128">Remarks</span></span>  
 <span data-ttu-id="b5bdb-129">CLR 在 `ICorProfilerCallback` （或 `ICorProfilerCallback2`）接口中调用方法，以便在探查器已订阅的事件发生时通知探查器。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-129">The CLR calls a method in the `ICorProfilerCallback` (or `ICorProfilerCallback2`) interface to notify the profiler when an event, to which the profiler had subscribed, occurs.</span></span> <span data-ttu-id="b5bdb-130">这是 CLR 与代码探查器进行通信时所使用的主回调接口。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-130">This is the primary callback interface through which the CLR communicates with the code profiler.</span></span>  
  
 <span data-ttu-id="b5bdb-131">代码探查器必须实现 `ICorProfilerCallback` 接口的方法。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-131">A code profiler must implement the methods of the `ICorProfilerCallback` interface.</span></span> <span data-ttu-id="b5bdb-132">对于 .NET Framework 2.0 及更高版本，探查器还必须实现 `ICorProfilerCallback2` 方法。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-132">For the .NET Framework 2.0 and later versions, the profiler must also implement the `ICorProfilerCallback2` methods.</span></span> <span data-ttu-id="b5bdb-133">每个方法实现都必须返回 HRESULT 的值 S_OK 为 "成功" 或 "E_FAIL 失败时"。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-133">Each method implementation must return an HRESULT having a value of S_OK on success or E_FAIL on failure.</span></span> <span data-ttu-id="b5bdb-134">目前，CLR 将忽略每个回调返回的 HRESULT （ [ICorProfilerCallback：： ObjectReferences](icorprofilercallback-objectreferences-method.md)除外）。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-134">Currently, the CLR ignores the HRESULT that is returned by each callback except [ICorProfilerCallback::ObjectReferences](icorprofilercallback-objectreferences-method.md).</span></span>  
  
 <span data-ttu-id="b5bdb-135">代码探查器必须在 Microsoft Windows 注册表中注册，它是实现 `ICorProfilerCallback` 和 `ICorProfilerCallback2` 接口的 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-135">A code profiler must register in the Microsoft Windows registry, its COM object that implements the `ICorProfilerCallback` and `ICorProfilerCallback2` interfaces.</span></span> <span data-ttu-id="b5bdb-136">代码探查器通过调用[ICorProfilerInfo：： SetEventMask](icorprofilerinfo-seteventmask-method.md)订阅要接收通知的事件。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-136">A code profiler subscribes to the events for which it wants to receive notification by calling [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md).</span></span> <span data-ttu-id="b5bdb-137">通常在探查器的[ICorProfilerCallback：： Initialize](icorprofilercallback-initialize-method.md)实现中完成此操作。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-137">This is usually done in the profiler's implementation of [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md).</span></span> <span data-ttu-id="b5bdb-138">然后，探查器可以在事件即将发生或刚刚发生在正在执行的运行时进程中时接收来自运行时的通知。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-138">The profiler is then able to receive notification from the runtime when an event is about to occur or has just occurred in an executing runtime process.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b5bdb-139">探查器将注册一个 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-139">The profiler registers a single COM object.</span></span> <span data-ttu-id="b5bdb-140">如果探查器的目标 .NET Framework 版本1.0 或1.1，则该 COM 对象只需实现 `ICorProfilerCallback`的方法。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-140">If the profiler is targeting .NET Framework version 1.0 or 1.1, that COM object need only implement the methods of `ICorProfilerCallback`.</span></span> <span data-ttu-id="b5bdb-141">如果目标 .NET Framework 版本2.0 及更高版本，则 COM 对象还必须实现 `ICorProfilerCallback2`的方法。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-141">If it is targeting .NET Framework version 2.0 and later, the COM object must also implement the methods of `ICorProfilerCallback2`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5bdb-142">需求</span><span class="sxs-lookup"><span data-stu-id="b5bdb-142">Requirements</span></span>  
 <span data-ttu-id="b5bdb-143">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b5bdb-143">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5bdb-144">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b5bdb-144">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b5bdb-145">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5bdb-145">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5bdb-146">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5bdb-146">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5bdb-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5bdb-147">See also</span></span>

- [<span data-ttu-id="b5bdb-148">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="b5bdb-148">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="b5bdb-149">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="b5bdb-149">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="b5bdb-150">ICorProfilerCallback3 接口</span><span class="sxs-lookup"><span data-stu-id="b5bdb-150">ICorProfilerCallback3 Interface</span></span>](icorprofilercallback3-interface.md)
- [<span data-ttu-id="b5bdb-151">ICorProfilerCallback4 接口</span><span class="sxs-lookup"><span data-stu-id="b5bdb-151">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
