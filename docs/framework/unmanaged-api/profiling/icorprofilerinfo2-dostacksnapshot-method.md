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
ms.openlocfilehash: 338120932b0bcbe390332515856aaeaa3bc34a56
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461693"
---
# <a name="icorprofilerinfo2dostacksnapshot-method"></a><span data-ttu-id="90c0c-102">ICorProfilerInfo2::DoStackSnapshot 方法</span><span class="sxs-lookup"><span data-stu-id="90c0c-102">ICorProfilerInfo2::DoStackSnapshot Method</span></span>
<span data-ttu-id="90c0c-103">上的指定线程的堆栈遍历托管的帧并将信息发送到通过回调探查器。</span><span class="sxs-lookup"><span data-stu-id="90c0c-103">Walks the managed frames on the stack for the specified thread, and sends information to the profiler through a callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90c0c-104">语法</span><span class="sxs-lookup"><span data-stu-id="90c0c-104">Syntax</span></span>  
  
```  
HRESULT DoStackSnapshot(  
    [in] ThreadID thread,  
    [in] StackSnapshotCallback *callback,  
    [in] ULONG32 infoFlags,  
    [in] void *clientData,  
    [in, size_is(contextSize), length_is(contextSize)] BYTE context[],  
    [in] ULONG32 contextSize);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="90c0c-105">参数</span><span class="sxs-lookup"><span data-stu-id="90c0c-105">Parameters</span></span>  
 `thread`  
 <span data-ttu-id="90c0c-106">[in]目标线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="90c0c-106">[in] The ID of the target thread.</span></span>  
  
 <span data-ttu-id="90c0c-107">传入 null`thread`会生成当前线程的快照。</span><span class="sxs-lookup"><span data-stu-id="90c0c-107">Passing null in `thread` yields a snapshot of the current thread.</span></span> <span data-ttu-id="90c0c-108">如果`ThreadID`的传递不同的线程，公共语言运行时 (CLR) 将该线程挂起、 执行快照，并恢复。</span><span class="sxs-lookup"><span data-stu-id="90c0c-108">If a `ThreadID` of a different thread is passed, the common language runtime (CLR) suspends that thread, performs the snapshot, and resumes.</span></span>  
  
 `callback`  
 <span data-ttu-id="90c0c-109">[in]指向的实现的[StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md)方法，由 CLR 探查器提供每个托管的帧和每次运行的非托管帧的信息。</span><span class="sxs-lookup"><span data-stu-id="90c0c-109">[in] A pointer to the implementation of the [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) method, which is called by the CLR to provide the profiler with information on each managed frame and each run of unmanaged frames.</span></span>  
  
 <span data-ttu-id="90c0c-110">`StackSnapshotCallback`方法由探查器编写器实现。</span><span class="sxs-lookup"><span data-stu-id="90c0c-110">The `StackSnapshotCallback` method is implemented by the profiler writer.</span></span>  
  
 `infoFlags`  
 <span data-ttu-id="90c0c-111">[in]值为[COR_PRF_SNAPSHOT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md)枚举，指定要返回为每个帧传递的数据量`StackSnapshotCallback`。</span><span class="sxs-lookup"><span data-stu-id="90c0c-111">[in] A value of the [COR_PRF_SNAPSHOT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md) enumeration, which specifies the amount of data to be passed back for each frame by `StackSnapshotCallback`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="90c0c-112">[in]指向客户端数据，这直接通过传递给`StackSnapshotCallback`回调函数。</span><span class="sxs-lookup"><span data-stu-id="90c0c-112">[in] A pointer to the client data, which is passed straight through to the `StackSnapshotCallback` callback function.</span></span>  
  
 `context`  
 <span data-ttu-id="90c0c-113">[in]一个指向 Win32`CONTEXT`结构，用于设定种子堆栈审核。</span><span class="sxs-lookup"><span data-stu-id="90c0c-113">[in] A pointer to a Win32 `CONTEXT` structure, which is used to seed the stack walk.</span></span> <span data-ttu-id="90c0c-114">Win32`CONTEXT`结构包含的 CPU 寄存器的值，表示在特定时刻的 CPU 的状态。</span><span class="sxs-lookup"><span data-stu-id="90c0c-114">The Win32 `CONTEXT` structure contains values of the CPU registers and represents the state of the CPU at a particular moment in time.</span></span>  
  
 <span data-ttu-id="90c0c-115">种子可帮助确定从何处着手堆栈审核，堆栈的顶部是非托管帮助器代码; 如果 CLR否则，将忽略种子。</span><span class="sxs-lookup"><span data-stu-id="90c0c-115">The seed helps the CLR determine where to begin the stack walk, if the top of the stack is unmanaged helper code; otherwise, the seed is ignored.</span></span> <span data-ttu-id="90c0c-116">必须为异步审核提供种子。</span><span class="sxs-lookup"><span data-stu-id="90c0c-116">A seed must be supplied for an asynchronous walk.</span></span> <span data-ttu-id="90c0c-117">如果你正在进行同步的审核，没有种子是必需的。</span><span class="sxs-lookup"><span data-stu-id="90c0c-117">If you are doing a synchronous walk, no seed is necessary.</span></span>  
  
 <span data-ttu-id="90c0c-118">`context`参数才有效仅当传入的 COR_PRF_SNAPSHOT_CONTEXT 标志`infoFlags`参数。</span><span class="sxs-lookup"><span data-stu-id="90c0c-118">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in the `infoFlags` parameter.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="90c0c-119">[in]大小`CONTEXT`结构，这通过引用`context`参数。</span><span class="sxs-lookup"><span data-stu-id="90c0c-119">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90c0c-120">备注</span><span class="sxs-lookup"><span data-stu-id="90c0c-120">Remarks</span></span>  
 <span data-ttu-id="90c0c-121">传递 null`thread`会生成当前线程的快照。</span><span class="sxs-lookup"><span data-stu-id="90c0c-121">Passing null for `thread` yields a snapshot of the current thread.</span></span> <span data-ttu-id="90c0c-122">仅当目标线程挂起时，可以其他线程拍摄快照。</span><span class="sxs-lookup"><span data-stu-id="90c0c-122">Snapshots can be taken of other threads only if the target thread is suspended at the time.</span></span>  
  
 <span data-ttu-id="90c0c-123">当探查器想要遍历堆栈时，它将调用`DoStackSnapshot`。</span><span class="sxs-lookup"><span data-stu-id="90c0c-123">When the profiler wants to walk the stack, it calls `DoStackSnapshot`.</span></span> <span data-ttu-id="90c0c-124">从该调用中返回 CLR 之前，它将调用你`StackSnapshotCallback`几次，一次每个托管帧 （或运行非托管帧） 堆栈上。</span><span class="sxs-lookup"><span data-stu-id="90c0c-124">Before the CLR returns from that call, it calls your `StackSnapshotCallback` several times, once for each managed frame (or run of unmanaged frames) on the stack.</span></span> <span data-ttu-id="90c0c-125">当遇到非托管的帧时，你必须自己逐步它们。</span><span class="sxs-lookup"><span data-stu-id="90c0c-125">When unmanaged frames are encountered, you must walk them yourself.</span></span>  
  
 <span data-ttu-id="90c0c-126">在其中遍历堆栈的顺序是如何帧已推送到堆栈上的反向： 上次叶 （上一次推送） 首先，主要 （第一个推送） 框架。</span><span class="sxs-lookup"><span data-stu-id="90c0c-126">The order in which the stack is walked is the reverse of how the frames were pushed onto the stack: leaf (last-pushed) frame first, main (first-pushed) frame last.</span></span>  
  
 <span data-ttu-id="90c0c-127">有关如何进行编程以审核托管的堆栈探查器的详细信息，请参阅[.NET Framework 2.0 中的探查器堆栈审核： 基础知识和扩展](http://go.microsoft.com/fwlink/?LinkId=73638)。</span><span class="sxs-lookup"><span data-stu-id="90c0c-127">For more information about how to program the profiler to walk managed stacks, see [Profiler Stack Walking in the .NET Framework 2.0: Basics and Beyond](http://go.microsoft.com/fwlink/?LinkId=73638).</span></span>  
  
 <span data-ttu-id="90c0c-128">下列部分中所述，可以同步或异步，堆栈审核。</span><span class="sxs-lookup"><span data-stu-id="90c0c-128">A stack walk can be synchronous or asynchronous, as explained in the following sections.</span></span>  
  
## <a name="synchronous-stack-walk"></a><span data-ttu-id="90c0c-129">同步堆栈审核</span><span class="sxs-lookup"><span data-stu-id="90c0c-129">Synchronous Stack Walk</span></span>  
 <span data-ttu-id="90c0c-130">同步堆栈审核涉及对回调的响应中的审核当前线程的堆栈。</span><span class="sxs-lookup"><span data-stu-id="90c0c-130">A synchronous stack walk involves walking the stack of the current thread in response to a callback.</span></span> <span data-ttu-id="90c0c-131">它不需要设置种子或挂起。</span><span class="sxs-lookup"><span data-stu-id="90c0c-131">It does not require seeding or suspending.</span></span>  
  
 <span data-ttu-id="90c0c-132">你进行同步时，调用以响应调用的探查器的某个 CLR [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) (或[ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) 调用的方法，`DoStackSnapshot`遍历的堆栈当前线程。</span><span class="sxs-lookup"><span data-stu-id="90c0c-132">You make a synchronous call when, in response to the CLR calling one of your profiler's [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) (or [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) methods, you call `DoStackSnapshot` to walk the stack of the current thread.</span></span> <span data-ttu-id="90c0c-133">这是有用的当你想要查看堆栈如下所示在通知如[icorprofilercallback:: Objectallocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)。</span><span class="sxs-lookup"><span data-stu-id="90c0c-133">This is useful when you want to see what the stack looks like at a notification such as [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span></span> <span data-ttu-id="90c0c-134">你只需调用`DoStackSnapshot`中你`ICorProfilerCallback`方法，传入 null`context`和`thread`参数。</span><span class="sxs-lookup"><span data-stu-id="90c0c-134">You just call `DoStackSnapshot` from within your `ICorProfilerCallback` method, passing null in the `context` and `thread` parameters.</span></span>  
  
## <a name="asynchronous-stack-walk"></a><span data-ttu-id="90c0c-135">异步堆栈审核</span><span class="sxs-lookup"><span data-stu-id="90c0c-135">Asynchronous Stack Walk</span></span>  
 <span data-ttu-id="90c0c-136">异步堆栈审核要求审核的另一个线程，堆栈或不在响应回调，但通过劫持当前线程的指令指针步行当前线程的堆栈。</span><span class="sxs-lookup"><span data-stu-id="90c0c-136">An asynchronous stack walk entails walking the stack of a different thread, or walking the stack of the current thread, not in response to a callback, but by hijacking the current thread's instruction pointer.</span></span> <span data-ttu-id="90c0c-137">异步审核要求的种子如果堆栈的顶部是不是一个平台的一部分的非托管的代码调用 (PInvoke) 或 COM 调用，但在 CLR 自行的帮助器代码。</span><span class="sxs-lookup"><span data-stu-id="90c0c-137">An asynchronous walk requires a seed if the top of the stack is unmanaged code that is not part of a platform invoke (PInvoke) or COM call, but helper code in the CLR itself.</span></span> <span data-ttu-id="90c0c-138">例如，执行在实时 (JIT) 编译或垃圾收集的代码是帮助器代码。</span><span class="sxs-lookup"><span data-stu-id="90c0c-138">For example, code that does just-in-time (JIT) compiling or garbage collection is helper code.</span></span>  
  
 <span data-ttu-id="90c0c-139">通过直接停用此目标线程获取种子和你自己，直到你找到的最顶层的遍历其堆栈托管帧。</span><span class="sxs-lookup"><span data-stu-id="90c0c-139">You obtain a seed by directly suspending the target thread and walking its stack yourself, until you find the topmost managed frame.</span></span> <span data-ttu-id="90c0c-140">此目标线程已挂起后，获取目标线程的当前寄存器上下文。</span><span class="sxs-lookup"><span data-stu-id="90c0c-140">After the target thread is suspended, get the target thread's current register context.</span></span> <span data-ttu-id="90c0c-141">接下来，确定是否寄存器上下文指向非托管代码通过调用[icorprofilerinfo:: Getfunctionfromip](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md) -如果它返回`FunctionID`等于零，框架的非托管的代码。</span><span class="sxs-lookup"><span data-stu-id="90c0c-141">Next, determine whether the register context points to unmanaged code by calling [ICorProfilerInfo::GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md) — if it returns a `FunctionID` equal to zero, the frame is unmanaged code.</span></span> <span data-ttu-id="90c0c-142">现在，遍历堆栈，直到到达第一个托管的帧，然后计算基于该框架的寄存器上下文在种子上下文。</span><span class="sxs-lookup"><span data-stu-id="90c0c-142">Now, walk the stack until you reach the first managed frame, and then calculate the seed context based on the register context for that frame.</span></span>  
  
 <span data-ttu-id="90c0c-143">调用`DoStackSnapshot`与你的种子上下文开始异步堆栈审核。</span><span class="sxs-lookup"><span data-stu-id="90c0c-143">Call `DoStackSnapshot` with your seed context to begin the asynchronous stack walk.</span></span> <span data-ttu-id="90c0c-144">如果未提供种子，`DoStackSnapshot`可能会跳过堆栈顶部的托管的帧，因此，将为你提供完整的堆栈审核。</span><span class="sxs-lookup"><span data-stu-id="90c0c-144">If you do not supply a seed, `DoStackSnapshot` might skip managed frames at the top of the stack and, consequently, will give you an incomplete stack walk.</span></span> <span data-ttu-id="90c0c-145">如果你提供种子，则它必须指向 JIT 编译或本机映像生成器 (Ngen.exe)-生成的代码;否则为`DoStackSnapshot`返回失败代码，CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX。</span><span class="sxs-lookup"><span data-stu-id="90c0c-145">If you do supply a seed, it must point to JIT-compiled or Native Image Generator (Ngen.exe)-generated code; otherwise, `DoStackSnapshot` returns the failure code, CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX.</span></span>  
  
 <span data-ttu-id="90c0c-146">异步堆栈审核可轻松会导致死锁或访问冲突，除非您遵循这些指导原则：</span><span class="sxs-lookup"><span data-stu-id="90c0c-146">Asynchronous stack walks can easily cause deadlocks or access violations, unless you follow these guidelines:</span></span>  
  
-   <span data-ttu-id="90c0c-147">直接挂起线程时，请记住仅从未运行托管的代码的线程可以挂起另一个线程。</span><span class="sxs-lookup"><span data-stu-id="90c0c-147">When you directly suspend threads, remember that only a thread that has never run managed code can suspend another thread.</span></span>  
  
-   <span data-ttu-id="90c0c-148">始终块中，在你[icorprofilercallback:: Threaddestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)回调完成此线程的堆栈审核之前。</span><span class="sxs-lookup"><span data-stu-id="90c0c-148">Always block in your [ICorProfilerCallback::ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md) callback until that thread's stack walk is complete.</span></span>  
  
-   <span data-ttu-id="90c0c-149">不保持锁定，而你的探查器调入可以触发垃圾回收的 CLR 函数。</span><span class="sxs-lookup"><span data-stu-id="90c0c-149">Do not hold a lock while your profiler calls into a CLR function that can trigger a garbage collection.</span></span> <span data-ttu-id="90c0c-150">如果拥有的线程可能会使触发垃圾回收的调用，即，并持有锁。</span><span class="sxs-lookup"><span data-stu-id="90c0c-150">That is, do not hold a lock if the owning thread might make a call that triggers a garbage collection.</span></span>  
  
 <span data-ttu-id="90c0c-151">此外，还有死锁风险如果调用`DoStackSnapshot`从你的探查器已创建，以便你可以遍历的单独目标线程堆栈的线程。</span><span class="sxs-lookup"><span data-stu-id="90c0c-151">There is also a risk of deadlock if you call `DoStackSnapshot` from a thread that your profiler has created so that you can walk the stack of a separate target thread.</span></span> <span data-ttu-id="90c0c-152">第一次你创建的线程进入某些`ICorProfilerInfo*`方法 (包括`DoStackSnapshot`)，CLR 将执行每个线程，该线程上的特定于 CLR 的初始化。</span><span class="sxs-lookup"><span data-stu-id="90c0c-152">The first time the thread you created enters certain `ICorProfilerInfo*` methods (including `DoStackSnapshot`), the CLR will perform per-thread, CLR-specific initialization on that thread.</span></span> <span data-ttu-id="90c0c-153">如果你的探查器已暂停目标线程尝试引导，其堆栈和该目标线程发生拥有锁所需执行此每个线程初始化，将发生死锁。</span><span class="sxs-lookup"><span data-stu-id="90c0c-153">If your profiler has suspended the target thread whose stack you are trying to walk, and if that target thread happened to own a lock necessary for performing this per-thread initialization, a deadlock will occur.</span></span> <span data-ttu-id="90c0c-154">若要避免这种死锁，进行初始调用`DoStackSnapshot`从您探查器创建的线程遍历单独目标线程，但首先未挂起此目标线程。</span><span class="sxs-lookup"><span data-stu-id="90c0c-154">To avoid this deadlock, make an initial call into `DoStackSnapshot` from your profiler-created thread to walk a separate target thread, but do not suspend the target thread first.</span></span> <span data-ttu-id="90c0c-155">此初始调用可确保每个线程初始化，可以在不死锁的情况下完成。</span><span class="sxs-lookup"><span data-stu-id="90c0c-155">This initial call ensures that the per-thread initialization can complete without deadlock.</span></span> <span data-ttu-id="90c0c-156">如果`DoStackSnapshot`成功，并且报告至少一个帧，此后，它将该探查器创建线程在可以挂起任何目标线程和调用安全`DoStackSnapshot`遍历该目标线程的堆栈。</span><span class="sxs-lookup"><span data-stu-id="90c0c-156">If `DoStackSnapshot` succeeds and reports at least one frame, after that point, it will be safe for that profiler-created thread to suspend any target thread and call `DoStackSnapshot` to walk the stack of that target thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90c0c-157">要求</span><span class="sxs-lookup"><span data-stu-id="90c0c-157">Requirements</span></span>  
 <span data-ttu-id="90c0c-158">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="90c0c-158">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90c0c-159">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="90c0c-159">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="90c0c-160">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90c0c-160">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90c0c-161">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90c0c-161">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90c0c-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="90c0c-162">See Also</span></span>  
 [<span data-ttu-id="90c0c-163">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="90c0c-163">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="90c0c-164">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="90c0c-164">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
