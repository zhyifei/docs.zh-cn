---
title: ICorProfilerInfo2::DoStackSnapshot 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.DoStackSnapshot
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::DoStackSnapshot
helpviewer_keywords:
- ICorProfilerInfo2::DoStackSnapshot method [.NET Framework profiling]
- DoStackSnapshot method [.NET Framework profiling]
ms.assetid: 287b11e9-7c52-4a13-ba97-751203fa97f4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 12ef215253ca02048a5a3fc2c7c682823233929f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61779809"
---
# <a name="icorprofilerinfo2dostacksnapshot-method"></a><span data-ttu-id="02d1c-102">ICorProfilerInfo2::DoStackSnapshot 方法</span><span class="sxs-lookup"><span data-stu-id="02d1c-102">ICorProfilerInfo2::DoStackSnapshot Method</span></span>
<span data-ttu-id="02d1c-103">对指定线程的堆栈上指导托管的帧，并将信息发送到通过回调探查器。</span><span class="sxs-lookup"><span data-stu-id="02d1c-103">Walks the managed frames on the stack for the specified thread, and sends information to the profiler through a callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02d1c-104">语法</span><span class="sxs-lookup"><span data-stu-id="02d1c-104">Syntax</span></span>  
  
```  
HRESULT DoStackSnapshot(  
    [in] ThreadID thread,  
    [in] StackSnapshotCallback *callback,  
    [in] ULONG32 infoFlags,  
    [in] void *clientData,  
    [in, size_is(contextSize), length_is(contextSize)] BYTE context[],  
    [in] ULONG32 contextSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02d1c-105">参数</span><span class="sxs-lookup"><span data-stu-id="02d1c-105">Parameters</span></span>  
 `thread`  
 <span data-ttu-id="02d1c-106">[in]目标线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="02d1c-106">[in] The ID of the target thread.</span></span>  
  
 <span data-ttu-id="02d1c-107">传递 null，在`thread`会生成当前线程的快照。</span><span class="sxs-lookup"><span data-stu-id="02d1c-107">Passing null in `thread` yields a snapshot of the current thread.</span></span> <span data-ttu-id="02d1c-108">如果`ThreadID`的传递不同的线程，公共语言运行时 (CLR) 会挂起该线程、 执行快照，并继续。</span><span class="sxs-lookup"><span data-stu-id="02d1c-108">If a `ThreadID` of a different thread is passed, the common language runtime (CLR) suspends that thread, performs the snapshot, and resumes.</span></span>  
  
 `callback`  
 <span data-ttu-id="02d1c-109">[in]实现的指针[StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md)由 CLR 提供有关每个托管的帧和非托管帧的每次运行探查器调用的方法。</span><span class="sxs-lookup"><span data-stu-id="02d1c-109">[in] A pointer to the implementation of the [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) method, which is called by the CLR to provide the profiler with information on each managed frame and each run of unmanaged frames.</span></span>  
  
 <span data-ttu-id="02d1c-110">`StackSnapshotCallback`探查器编写器实现方法。</span><span class="sxs-lookup"><span data-stu-id="02d1c-110">The `StackSnapshotCallback` method is implemented by the profiler writer.</span></span>  
  
 `infoFlags`  
 <span data-ttu-id="02d1c-111">[in]值为[COR_PRF_SNAPSHOT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md)枚举，指定要返回的每个框架中通过传递的数据量`StackSnapshotCallback`。</span><span class="sxs-lookup"><span data-stu-id="02d1c-111">[in] A value of the [COR_PRF_SNAPSHOT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md) enumeration, which specifies the amount of data to be passed back for each frame by `StackSnapshotCallback`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="02d1c-112">[in]指向客户端数据，直接通过传递给`StackSnapshotCallback`回调函数。</span><span class="sxs-lookup"><span data-stu-id="02d1c-112">[in] A pointer to the client data, which is passed straight through to the `StackSnapshotCallback` callback function.</span></span>  
  
 `context`  
 <span data-ttu-id="02d1c-113">[in]一个指向 Win32`CONTEXT`结构，它用于设定种子堆栈遍历。</span><span class="sxs-lookup"><span data-stu-id="02d1c-113">[in] A pointer to a Win32 `CONTEXT` structure, which is used to seed the stack walk.</span></span> <span data-ttu-id="02d1c-114">Win32`CONTEXT`结构包含的 CPU 寄存器的值，表示在特定时刻 CPU 的状态。</span><span class="sxs-lookup"><span data-stu-id="02d1c-114">The Win32 `CONTEXT` structure contains values of the CPU registers and represents the state of the CPU at a particular moment in time.</span></span>  
  
 <span data-ttu-id="02d1c-115">该种子可以帮助 CLR 确定从何处开始堆栈遍历，如果堆栈的顶部为非托管帮助器代码;否则，将忽略种子。</span><span class="sxs-lookup"><span data-stu-id="02d1c-115">The seed helps the CLR determine where to begin the stack walk, if the top of the stack is unmanaged helper code; otherwise, the seed is ignored.</span></span> <span data-ttu-id="02d1c-116">必须提供异步遍历的种子。</span><span class="sxs-lookup"><span data-stu-id="02d1c-116">A seed must be supplied for an asynchronous walk.</span></span> <span data-ttu-id="02d1c-117">如果正在执行是同步遍历，没有种子是必需的。</span><span class="sxs-lookup"><span data-stu-id="02d1c-117">If you are doing a synchronous walk, no seed is necessary.</span></span>  
  
 <span data-ttu-id="02d1c-118">`context`参数才有效，仅当传入的 COR_PRF_SNAPSHOT_CONTEXT 标志`infoFlags`参数。</span><span class="sxs-lookup"><span data-stu-id="02d1c-118">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in the `infoFlags` parameter.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="02d1c-119">[in]大小`CONTEXT`结构，它引用的`context`参数。</span><span class="sxs-lookup"><span data-stu-id="02d1c-119">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02d1c-120">备注</span><span class="sxs-lookup"><span data-stu-id="02d1c-120">Remarks</span></span>  
 <span data-ttu-id="02d1c-121">传递 null`thread`会生成当前线程的快照。</span><span class="sxs-lookup"><span data-stu-id="02d1c-121">Passing null for `thread` yields a snapshot of the current thread.</span></span> <span data-ttu-id="02d1c-122">目标线程挂起时，才可以拍摄快照的其他线程。</span><span class="sxs-lookup"><span data-stu-id="02d1c-122">Snapshots can be taken of other threads only if the target thread is suspended at the time.</span></span>  
  
 <span data-ttu-id="02d1c-123">当探查器要遍历堆栈时，它将调用`DoStackSnapshot`。</span><span class="sxs-lookup"><span data-stu-id="02d1c-123">When the profiler wants to walk the stack, it calls `DoStackSnapshot`.</span></span> <span data-ttu-id="02d1c-124">CLR 从该调用返回之前，它将调用你`StackSnapshotCallback`几次，一次为每个托管帧 （或非托管帧） 在堆栈上。</span><span class="sxs-lookup"><span data-stu-id="02d1c-124">Before the CLR returns from that call, it calls your `StackSnapshotCallback` several times, once for each managed frame (or run of unmanaged frames) on the stack.</span></span> <span data-ttu-id="02d1c-125">遇到非托管的帧时，您必须自己遍历它们。</span><span class="sxs-lookup"><span data-stu-id="02d1c-125">When unmanaged frames are encountered, you must walk them yourself.</span></span>  
  
 <span data-ttu-id="02d1c-126">在其中堆栈被遍历的顺序是如何帧被推入到堆栈的相反： 最后一个叶 （上一次推送） 帧第一个、 主 （第一个推送） 框架。</span><span class="sxs-lookup"><span data-stu-id="02d1c-126">The order in which the stack is walked is the reverse of how the frames were pushed onto the stack: leaf (last-pushed) frame first, main (first-pushed) frame last.</span></span>  
  
 <span data-ttu-id="02d1c-127">有关如何对探查器以审核托管的堆栈的详细信息，请参阅[.NET Framework 2.0 中的 Profiler 堆栈审核：基础和超越](https://go.microsoft.com/fwlink/?LinkId=73638)。</span><span class="sxs-lookup"><span data-stu-id="02d1c-127">For more information about how to program the profiler to walk managed stacks, see [Profiler Stack Walking in the .NET Framework 2.0: Basics and Beyond](https://go.microsoft.com/fwlink/?LinkId=73638).</span></span>  
  
 <span data-ttu-id="02d1c-128">以下各节中所述，可以同步或异步的堆栈遍历。</span><span class="sxs-lookup"><span data-stu-id="02d1c-128">A stack walk can be synchronous or asynchronous, as explained in the following sections.</span></span>  
  
## <a name="synchronous-stack-walk"></a><span data-ttu-id="02d1c-129">同步堆栈遍历</span><span class="sxs-lookup"><span data-stu-id="02d1c-129">Synchronous Stack Walk</span></span>  
 <span data-ttu-id="02d1c-130">同步堆栈遍历涉及对回调的响应中遍历当前线程的堆栈。</span><span class="sxs-lookup"><span data-stu-id="02d1c-130">A synchronous stack walk involves walking the stack of the current thread in response to a callback.</span></span> <span data-ttu-id="02d1c-131">它不需要种子设定或挂起。</span><span class="sxs-lookup"><span data-stu-id="02d1c-131">It does not require seeding or suspending.</span></span>  
  
 <span data-ttu-id="02d1c-132">进行同步时，调用以响应调用的探查器的一个 CLR [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) (或[ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) 方法调用`DoStackSnapshot`要遍历的堆栈当前线程。</span><span class="sxs-lookup"><span data-stu-id="02d1c-132">You make a synchronous call when, in response to the CLR calling one of your profiler's [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) (or [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) methods, you call `DoStackSnapshot` to walk the stack of the current thread.</span></span> <span data-ttu-id="02d1c-133">如果想要查看堆栈的外观在通知等，这是很有用[icorprofilercallback:: Objectallocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)。</span><span class="sxs-lookup"><span data-stu-id="02d1c-133">This is useful when you want to see what the stack looks like at a notification such as [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span></span> <span data-ttu-id="02d1c-134">只需调用`DoStackSnapshot`从你`ICorProfilerCallback`方法，传递 null，在`context`和`thread`参数。</span><span class="sxs-lookup"><span data-stu-id="02d1c-134">You just call `DoStackSnapshot` from within your `ICorProfilerCallback` method, passing null in the `context` and `thread` parameters.</span></span>  
  
## <a name="asynchronous-stack-walk"></a><span data-ttu-id="02d1c-135">异步堆栈遍历</span><span class="sxs-lookup"><span data-stu-id="02d1c-135">Asynchronous Stack Walk</span></span>  
 <span data-ttu-id="02d1c-136">异步堆栈遍历要求遍历不同线程的堆栈或不在响应回调，而通过截取当前线程的指令指针遍历当前线程的堆栈。</span><span class="sxs-lookup"><span data-stu-id="02d1c-136">An asynchronous stack walk entails walking the stack of a different thread, or walking the stack of the current thread, not in response to a callback, but by hijacking the current thread's instruction pointer.</span></span> <span data-ttu-id="02d1c-137">异步遍历需要种子如果堆栈的顶部是不是一个平台的一部分的非托管的代码调用 (PInvoke) 或 COM 调用，但在 CLR 自身中的帮助器代码。</span><span class="sxs-lookup"><span data-stu-id="02d1c-137">An asynchronous walk requires a seed if the top of the stack is unmanaged code that is not part of a platform invoke (PInvoke) or COM call, but helper code in the CLR itself.</span></span> <span data-ttu-id="02d1c-138">例如，执行在实时 (JIT) 编译或垃圾收集的代码是帮助器代码。</span><span class="sxs-lookup"><span data-stu-id="02d1c-138">For example, code that does just-in-time (JIT) compiling or garbage collection is helper code.</span></span>  
  
 <span data-ttu-id="02d1c-139">通过直接挂起目标线程获取种子并自己，直到找到的最顶层的遍历其堆栈托管帧。</span><span class="sxs-lookup"><span data-stu-id="02d1c-139">You obtain a seed by directly suspending the target thread and walking its stack yourself, until you find the topmost managed frame.</span></span> <span data-ttu-id="02d1c-140">挂起目标线程后，获取目标线程的当前寄存器上下文。</span><span class="sxs-lookup"><span data-stu-id="02d1c-140">After the target thread is suspended, get the target thread's current register context.</span></span> <span data-ttu-id="02d1c-141">接下来，确定是否寄存器上下文指向非托管代码通过调用[icorprofilerinfo:: Getfunctionfromip](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md) -如果它返回`FunctionID`等于零，该框架是在非托管的代码。</span><span class="sxs-lookup"><span data-stu-id="02d1c-141">Next, determine whether the register context points to unmanaged code by calling [ICorProfilerInfo::GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md) — if it returns a `FunctionID` equal to zero, the frame is unmanaged code.</span></span> <span data-ttu-id="02d1c-142">现在，遍历堆栈，直到到达第一个托管的帧，然后计算种子上下文基于该范围中寄存器上下文。</span><span class="sxs-lookup"><span data-stu-id="02d1c-142">Now, walk the stack until you reach the first managed frame, and then calculate the seed context based on the register context for that frame.</span></span>  
  
 <span data-ttu-id="02d1c-143">调用`DoStackSnapshot`使用种子上下文开始异步堆栈遍历。</span><span class="sxs-lookup"><span data-stu-id="02d1c-143">Call `DoStackSnapshot` with your seed context to begin the asynchronous stack walk.</span></span> <span data-ttu-id="02d1c-144">如果未提供种子，`DoStackSnapshot`可能会跳过堆栈顶部的托管的帧，因此，将为您提供完整的堆栈审核。</span><span class="sxs-lookup"><span data-stu-id="02d1c-144">If you do not supply a seed, `DoStackSnapshot` might skip managed frames at the top of the stack and, consequently, will give you an incomplete stack walk.</span></span> <span data-ttu-id="02d1c-145">如果你提供种子，则必须指向 JIT 编译或本机映像生成器 (Ngen.exe)-生成的代码;否则为`DoStackSnapshot`返回故障代码，CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX。</span><span class="sxs-lookup"><span data-stu-id="02d1c-145">If you do supply a seed, it must point to JIT-compiled or Native Image Generator (Ngen.exe)-generated code; otherwise, `DoStackSnapshot` returns the failure code, CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX.</span></span>  
  
 <span data-ttu-id="02d1c-146">异步堆栈遍历可轻松地会导致死锁或访问冲突，除非您遵循以下准则：</span><span class="sxs-lookup"><span data-stu-id="02d1c-146">Asynchronous stack walks can easily cause deadlocks or access violations, unless you follow these guidelines:</span></span>  
  
- <span data-ttu-id="02d1c-147">当你直接暂停线程时，请记住只有从未运行过托管的代码的线程才可以挂起另一个线程。</span><span class="sxs-lookup"><span data-stu-id="02d1c-147">When you directly suspend threads, remember that only a thread that has never run managed code can suspend another thread.</span></span>  
  
- <span data-ttu-id="02d1c-148">始终阻止您[icorprofilercallback:: Threaddestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)回调该线程的堆栈遍历直到完成。</span><span class="sxs-lookup"><span data-stu-id="02d1c-148">Always block in your [ICorProfilerCallback::ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md) callback until that thread's stack walk is complete.</span></span>  
  
- <span data-ttu-id="02d1c-149">在分析器调用到可以触发垃圾回收的 CLR 函数时，则不持有锁。</span><span class="sxs-lookup"><span data-stu-id="02d1c-149">Do not hold a lock while your profiler calls into a CLR function that can trigger a garbage collection.</span></span> <span data-ttu-id="02d1c-150">即，如果拥有线程可能会使触发垃圾回收的调用并持有锁。</span><span class="sxs-lookup"><span data-stu-id="02d1c-150">That is, do not hold a lock if the owning thread might make a call that triggers a garbage collection.</span></span>  
  
 <span data-ttu-id="02d1c-151">此外，还有的死锁风险如果调用`DoStackSnapshot`从您的探查器已创建，以便您可以放心离开，单独的目标线程的堆栈的线程。</span><span class="sxs-lookup"><span data-stu-id="02d1c-151">There is also a risk of deadlock if you call `DoStackSnapshot` from a thread that your profiler has created so that you can walk the stack of a separate target thread.</span></span> <span data-ttu-id="02d1c-152">第一次你创建的线程进入某些`ICorProfilerInfo*`方法 (包括`DoStackSnapshot`)，CLR 将执行每个线程，该线程上的特定于 CLR 的初始化。</span><span class="sxs-lookup"><span data-stu-id="02d1c-152">The first time the thread you created enters certain `ICorProfilerInfo*` methods (including `DoStackSnapshot`), the CLR will perform per-thread, CLR-specific initialization on that thread.</span></span> <span data-ttu-id="02d1c-153">如果您的探查器已挂起目标线程想要遍历，其堆栈，并且该目标线程恰巧拥有锁所需执行此每个线程初始化，将发生死锁。</span><span class="sxs-lookup"><span data-stu-id="02d1c-153">If your profiler has suspended the target thread whose stack you are trying to walk, and if that target thread happened to own a lock necessary for performing this per-thread initialization, a deadlock will occur.</span></span> <span data-ttu-id="02d1c-154">若要避免这种死锁，进行初始调用到`DoStackSnapshot`单独从在探查器创建的线程以遍历目标线程，但不是先挂起目标线程。</span><span class="sxs-lookup"><span data-stu-id="02d1c-154">To avoid this deadlock, make an initial call into `DoStackSnapshot` from your profiler-created thread to walk a separate target thread, but do not suspend the target thread first.</span></span> <span data-ttu-id="02d1c-155">此初始调用可确保每个线程初始化可以完成而无需死锁。</span><span class="sxs-lookup"><span data-stu-id="02d1c-155">This initial call ensures that the per-thread initialization can complete without deadlock.</span></span> <span data-ttu-id="02d1c-156">如果`DoStackSnapshot`成功，并且报告至少一个框架，该时间点后，将会挂起任何目标线程和调用该探查器创建线程安全`DoStackSnapshot`来遍历该目标线程的堆栈。</span><span class="sxs-lookup"><span data-stu-id="02d1c-156">If `DoStackSnapshot` succeeds and reports at least one frame, after that point, it will be safe for that profiler-created thread to suspend any target thread and call `DoStackSnapshot` to walk the stack of that target thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02d1c-157">要求</span><span class="sxs-lookup"><span data-stu-id="02d1c-157">Requirements</span></span>  
 <span data-ttu-id="02d1c-158">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="02d1c-158">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02d1c-159">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="02d1c-159">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="02d1c-160">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02d1c-160">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02d1c-161">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02d1c-161">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02d1c-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="02d1c-162">See also</span></span>

- [<span data-ttu-id="02d1c-163">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="02d1c-163">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="02d1c-164">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="02d1c-164">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
