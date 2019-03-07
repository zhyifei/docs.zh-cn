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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 83caaa04481b4ed92407294584512b38553710b4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501482"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a><span data-ttu-id="44b4b-102">ICorProfilerCallback4::ReJITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="44b4b-102">ICorProfilerCallback4::ReJITCompilationStarted Method</span></span>
<span data-ttu-id="44b4b-103">通知探查器在实时 (JIT) 编译器已开始重新编译函数。</span><span class="sxs-lookup"><span data-stu-id="44b4b-103">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44b4b-104">语法</span><span class="sxs-lookup"><span data-stu-id="44b4b-104">Syntax</span></span>  
  
```  
HRESULT ReJITCompilationStarted(   
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44b4b-105">参数</span><span class="sxs-lookup"><span data-stu-id="44b4b-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="44b4b-106">[in]JIT 编译器已开始重新编译函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="44b4b-106">[in] The ID of the function that the JIT compiler has started to recompile.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="44b4b-107">[in]重新编译函数的新版本的 ID。</span><span class="sxs-lookup"><span data-stu-id="44b4b-107">[in] The recompilation ID of the new version of the function.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="44b4b-108">[in]`true`以指示，阻止可能会导致运行时等待调用的线程返回从此回调;`false`以指示，阻止不会影响运行时的操作。</span><span class="sxs-lookup"><span data-stu-id="44b4b-108">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span> <span data-ttu-id="44b4b-109">值为`true`不会损害了运行时，但可能会影响分析结果。</span><span class="sxs-lookup"><span data-stu-id="44b4b-109">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44b4b-110">备注</span><span class="sxs-lookup"><span data-stu-id="44b4b-110">Remarks</span></span>  
 <span data-ttu-id="44b4b-111">可以接收多个对`ReJITCompilationStarted`并[ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)方法调用每个函数的方式运行时句柄类构造函数。</span><span class="sxs-lookup"><span data-stu-id="44b4b-111">It is possible to receive more than one pair of `ReJITCompilationStarted` and [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) method calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="44b4b-112">例如，在运行时开始重新编译方法，但类 B 的类构造函数需要运行。</span><span class="sxs-lookup"><span data-stu-id="44b4b-112">For example, the runtime starts to recompile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="44b4b-113">因此，在运行时重新编译类 B 的构造函数，并运行它。</span><span class="sxs-lookup"><span data-stu-id="44b4b-113">Therefore, the runtime recompiles the constructor for class B and runs it.</span></span> <span data-ttu-id="44b4b-114">构造函数正在运行，但可以对一个，这会导致方法 A 再次重新编译方法的调用。</span><span class="sxs-lookup"><span data-stu-id="44b4b-114">While the constructor is running, it makes a call to method A, which causes method A to be recompiled again.</span></span> <span data-ttu-id="44b4b-115">在此方案中，将停止方法 A 首次重新编译。</span><span class="sxs-lookup"><span data-stu-id="44b4b-115">In this scenario, the first recompilation of method A is halted.</span></span> <span data-ttu-id="44b4b-116">但是，将同时尝试重新编译的方法是使用 JIT 重新编译事件报告。</span><span class="sxs-lookup"><span data-stu-id="44b4b-116">However, both attempts to recompile method A are reported with JIT recompilation events.</span></span>  
  
 <span data-ttu-id="44b4b-117">在两个线程同时执行回调的情况下，探查器必须支持 JIT 重新编译回调的序列。</span><span class="sxs-lookup"><span data-stu-id="44b4b-117">Profilers must support the sequence of JIT recompilation callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="44b4b-118">例如，一个线程调用`ReJITCompilationStarted`; 但是，在线程 A 调用之前[ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)，线程 B 调用[icorprofilercallback:: Exceptionsearchfunctionenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md)函数 id从`ReJITCompilationStarted`回调线程 a。它可能显示的函数 ID 尚未有效期不应因为调用[ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)有尚未收到事件探查器。</span><span class="sxs-lookup"><span data-stu-id="44b4b-118">For example, thread A calls `ReJITCompilationStarted`; however, before thread A calls [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from the `ReJITCompilationStarted` callback for thread A. It might appear that the function ID should not yet be valid because a call to [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) had not yet been received by the profiler.</span></span> <span data-ttu-id="44b4b-119">但是，在这种情况下，函数 ID 无效。</span><span class="sxs-lookup"><span data-stu-id="44b4b-119">However, in this case, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44b4b-120">要求</span><span class="sxs-lookup"><span data-stu-id="44b4b-120">Requirements</span></span>  
 <span data-ttu-id="44b4b-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="44b4b-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44b4b-122">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="44b4b-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="44b4b-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44b4b-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44b4b-124">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44b4b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44b4b-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="44b4b-125">See also</span></span>
- [<span data-ttu-id="44b4b-126">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="44b4b-126">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="44b4b-127">ICorProfilerCallback4 接口</span><span class="sxs-lookup"><span data-stu-id="44b4b-127">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [<span data-ttu-id="44b4b-128">JITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="44b4b-128">JITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
- [<span data-ttu-id="44b4b-129">ReJITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="44b4b-129">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)
