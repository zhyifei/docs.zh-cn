---
title: ICorProfilerCallback::JITCachedFunctionSearchStarted 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchStarted
helpviewer_keywords:
- JITCachedFunctionSearchStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchStarted method [.NET Framework profiling]
ms.assetid: 5cba642c-0d80-48ee-889d-198c5044d821
topic_type:
- apiref
ms.openlocfilehash: 5d3fe6691a2d9989de002bad09c2e8f66a094f56
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448430"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a><span data-ttu-id="b12a1-102">ICorProfilerCallback::JITCachedFunctionSearchStarted 方法</span><span class="sxs-lookup"><span data-stu-id="b12a1-102">ICorProfilerCallback::JITCachedFunctionSearchStarted Method</span></span>
<span data-ttu-id="b12a1-103">通知探查器搜索已开始使用本机映像生成器（Ngen.exe）编译的函数。</span><span class="sxs-lookup"><span data-stu-id="b12a1-103">Notifies the profiler that a search has started for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b12a1-104">语法</span><span class="sxs-lookup"><span data-stu-id="b12a1-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b12a1-105">参数</span><span class="sxs-lookup"><span data-stu-id="b12a1-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="b12a1-106">中正在为其执行搜索的函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="b12a1-106">[in] The ID of the function for which the search is being performed.</span></span>  
  
 `pbUseCachedFunction`  
 <span data-ttu-id="b12a1-107">[out] 如果执行引擎应使用函数的缓存版本（如果可用），则 `true`;否则 `false`。</span><span class="sxs-lookup"><span data-stu-id="b12a1-107">[out] `true` if the execution engine should use the cached version of a function (if available); otherwise `false`.</span></span> <span data-ttu-id="b12a1-108">如果 `false`值，则执行引擎将对函数进行 JIT 编译，而不是使用 JIT 编译的版本。</span><span class="sxs-lookup"><span data-stu-id="b12a1-108">If the value is `false`, the execution engine JIT-compiles the function instead of using a version that is not JIT-compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b12a1-109">备注</span><span class="sxs-lookup"><span data-stu-id="b12a1-109">Remarks</span></span>  
 <span data-ttu-id="b12a1-110">在 .NET Framework 版本2.0 中，将不会对常规 NGen 映像中的所有函数执行 `JITCachedFunctionSearchStarted` 和[ICorProfilerCallback：： JITCachedFunctionSearchFinished 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="b12a1-110">In the .NET Framework version 2.0, the `JITCachedFunctionSearchStarted` and [ICorProfilerCallback::JITCachedFunctionSearchFinished Method](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="b12a1-111">只有针对配置文件优化的 NGen 映像将为映像中的所有函数生成回调。</span><span class="sxs-lookup"><span data-stu-id="b12a1-111">Only NGen images optimized for a profile will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="b12a1-112">但是，由于额外的开销，如果探查器打算使用这些回调来强制实时（JIT）编译函数，则它应请求探查器优化的 NGen 映像。</span><span class="sxs-lookup"><span data-stu-id="b12a1-112">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="b12a1-113">否则，探查器应使用延迟策略来收集函数信息。</span><span class="sxs-lookup"><span data-stu-id="b12a1-113">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
 <span data-ttu-id="b12a1-114">探查器必须支持分析的应用程序的多个线程同时调用同一方法的情况。</span><span class="sxs-lookup"><span data-stu-id="b12a1-114">Profilers must support cases where multiple threads of a profiled application are calling the same method simultaneously.</span></span> <span data-ttu-id="b12a1-115">例如，线程 A 调用 `JITCachedFunctionSearchStarted` 并且探查器通过将*pbUseCachedFunction*设置为 FALSE 来做出响应，以强制 JIT 编译。</span><span class="sxs-lookup"><span data-stu-id="b12a1-115">For example, thread A calls `JITCachedFunctionSearchStarted` and the profiler responds by setting *pbUseCachedFunction*to FALSE to force JIT compilation.</span></span> <span data-ttu-id="b12a1-116">然后，线程 A 调用[ICorProfilerCallback：： JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)和[ICorProfilerCallback：： JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)。</span><span class="sxs-lookup"><span data-stu-id="b12a1-116">Thread A then calls [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) and [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md).</span></span>  
  
 <span data-ttu-id="b12a1-117">现在，线程 B 为同一函数调用 `JITCachedFunctionSearchStarted`。</span><span class="sxs-lookup"><span data-stu-id="b12a1-117">Now thread B calls `JITCachedFunctionSearchStarted` for the same function.</span></span> <span data-ttu-id="b12a1-118">即使探查器已经说明了 JIT 编译函数的意图，探查器仍会收到第二次回调，因为在探查器响应线程 A 对 `JITCachedFunctionSearchStarted`的调用之前，线程 B 会发送回调。</span><span class="sxs-lookup"><span data-stu-id="b12a1-118">Even though the profiler has stated its intention to JIT-compile the function, the profiler receives the second callback because thread B sends the callback before the profiler has responded to thread A's call to `JITCachedFunctionSearchStarted`.</span></span> <span data-ttu-id="b12a1-119">线程发出调用的顺序取决于线程的计划方式。</span><span class="sxs-lookup"><span data-stu-id="b12a1-119">The order in which the threads make calls depends on how the threads are scheduled.</span></span>  
  
 <span data-ttu-id="b12a1-120">当探查器收到重复的回调时，它必须将 `pbUseCachedFunction` 引用的值设置为所有重复回调的相同值。</span><span class="sxs-lookup"><span data-stu-id="b12a1-120">When the profiler receives duplicate callbacks, it must set the value referenced by `pbUseCachedFunction` to the same value for all the duplicate callbacks.</span></span> <span data-ttu-id="b12a1-121">也就是说，当用相同的 `functionId` 值多次调用 `JITCachedFunctionSearchStarted` 时，探查器每次都必须响应相同的值。</span><span class="sxs-lookup"><span data-stu-id="b12a1-121">That is, when `JITCachedFunctionSearchStarted` is called multiple times with the same `functionId` value, the profiler must respond the same each time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b12a1-122">要求</span><span class="sxs-lookup"><span data-stu-id="b12a1-122">Requirements</span></span>  
 <span data-ttu-id="b12a1-123">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b12a1-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b12a1-124">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b12a1-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b12a1-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b12a1-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b12a1-126">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b12a1-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b12a1-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b12a1-127">See also</span></span>

- [<span data-ttu-id="b12a1-128">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="b12a1-128">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
