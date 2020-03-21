---
title: ICorProfilerCallback4::ReJITCompilationStarted 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationStarted
helpviewer_keywords:
- ReJITCompilationStarted method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITCompilationStarted method [.NET Framework profiling]
ms.assetid: 512fdd00-262a-4456-a075-365ef4133c4d
topic_type:
- apiref
ms.openlocfilehash: be257930ca0fad658afa75d6efa4573d4f888a2b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177080"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a><span data-ttu-id="4540f-102">ICorProfilerCallback4::ReJITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="4540f-102">ICorProfilerCallback4::ReJITCompilationStarted Method</span></span>
<span data-ttu-id="4540f-103">通知探查器及时 （JIT） 编译器已开始重新编译函数。</span><span class="sxs-lookup"><span data-stu-id="4540f-103">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4540f-104">语法</span><span class="sxs-lookup"><span data-stu-id="4540f-104">Syntax</span></span>  
  
```cpp  
HRESULT ReJITCompilationStarted(
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4540f-105">parameters</span><span class="sxs-lookup"><span data-stu-id="4540f-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="4540f-106">[在]JIT 编译器已开始重新编译的函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="4540f-106">[in] The ID of the function that the JIT compiler has started to recompile.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="4540f-107">[在]函数的新版本的重新编译 ID。</span><span class="sxs-lookup"><span data-stu-id="4540f-107">[in] The recompilation ID of the new version of the function.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="4540f-108">[在]`true`指示阻塞可能导致运行时等待调用线程从此回调返回;`false`指示阻塞不会影响运行时的操作。</span><span class="sxs-lookup"><span data-stu-id="4540f-108">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span> <span data-ttu-id="4540f-109">值`true`不会损害运行时，但可能会影响分析结果。</span><span class="sxs-lookup"><span data-stu-id="4540f-109">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4540f-110">备注</span><span class="sxs-lookup"><span data-stu-id="4540f-110">Remarks</span></span>  
 <span data-ttu-id="4540f-111">由于运行时处理类构造函数的方式，可以为每个`ReJITCompilationStarted`函数接收多对和[ReJIT 编译完成](icorprofilercallback4-rejitcompilationfinished-method.md)方法调用。</span><span class="sxs-lookup"><span data-stu-id="4540f-111">It is possible to receive more than one pair of `ReJITCompilationStarted` and [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) method calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="4540f-112">例如，运行时开始重新编译方法 A，但需要运行类 B 的类构造函数。</span><span class="sxs-lookup"><span data-stu-id="4540f-112">For example, the runtime starts to recompile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="4540f-113">因此，运行时重新编译类 B 的构造函数并运行它。</span><span class="sxs-lookup"><span data-stu-id="4540f-113">Therefore, the runtime recompiles the constructor for class B and runs it.</span></span> <span data-ttu-id="4540f-114">当构造函数运行时，它会调用方法 A，这将导致方法 A 再次重新编译。</span><span class="sxs-lookup"><span data-stu-id="4540f-114">While the constructor is running, it makes a call to method A, which causes method A to be recompiled again.</span></span> <span data-ttu-id="4540f-115">在这种情况下，方法 A 的第一次重新编译将停止。</span><span class="sxs-lookup"><span data-stu-id="4540f-115">In this scenario, the first recompilation of method A is halted.</span></span> <span data-ttu-id="4540f-116">但是，使用 JIT 重新编译事件报告重新编译方法 A 的尝试。</span><span class="sxs-lookup"><span data-stu-id="4540f-116">However, both attempts to recompile method A are reported with JIT recompilation events.</span></span>  
  
 <span data-ttu-id="4540f-117">在两个线程同时进行回调的情况下，探查器必须支持 JIT 重新编译回调的顺序。</span><span class="sxs-lookup"><span data-stu-id="4540f-117">Profilers must support the sequence of JIT recompilation callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="4540f-118">例如，线程 A`ReJITCompilationStarted`调用 ;但是，在线程 A 调用[ReJIT 编译完成](icorprofilercallback4-rejitcompilationfinished-method.md)之前，线程 B 调用[ICorProfiler 回调：：异常搜索功能Enter](icorprofilercallback-exceptionsearchfunctionenter-method.md)与线程 A 回调中的`ReJITCompilationStarted`函数 ID。似乎函数 ID 尚未有效，因为探查器尚未收到对[ReJIT 编译完成的](icorprofilercallback4-rejitcompilationfinished-method.md)调用。</span><span class="sxs-lookup"><span data-stu-id="4540f-118">For example, thread A calls `ReJITCompilationStarted`; however, before thread A calls [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md), thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from the `ReJITCompilationStarted` callback for thread A. It might appear that the function ID should not yet be valid because a call to [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) had not yet been received by the profiler.</span></span> <span data-ttu-id="4540f-119">但是，在这种情况下，函数 ID 有效。</span><span class="sxs-lookup"><span data-stu-id="4540f-119">However, in this case, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4540f-120">要求</span><span class="sxs-lookup"><span data-stu-id="4540f-120">Requirements</span></span>  
 <span data-ttu-id="4540f-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4540f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4540f-122">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4540f-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4540f-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4540f-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4540f-124">**.NET 框架版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4540f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4540f-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4540f-125">See also</span></span>

- [<span data-ttu-id="4540f-126">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="4540f-126">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="4540f-127">ICorProfilerCallback4 接口</span><span class="sxs-lookup"><span data-stu-id="4540f-127">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="4540f-128">JITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="4540f-128">JITCompilationFinished Method</span></span>](icorprofilercallback-jitcompilationfinished-method.md)
- [<span data-ttu-id="4540f-129">ReJITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="4540f-129">ReJITCompilationFinished Method</span></span>](icorprofilercallback4-rejitcompilationfinished-method.md)
