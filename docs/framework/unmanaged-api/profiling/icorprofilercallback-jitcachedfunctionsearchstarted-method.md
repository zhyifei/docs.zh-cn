---
title: "ICorProfilerCallback::JITCachedFunctionSearchStarted 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d2208a1a1637b3bb8dd7d7963ab806aeae7921dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a><span data-ttu-id="4e389-102">ICorProfilerCallback::JITCachedFunctionSearchStarted 方法</span><span class="sxs-lookup"><span data-stu-id="4e389-102">ICorProfilerCallback::JITCachedFunctionSearchStarted Method</span></span>
<span data-ttu-id="4e389-103">通知探查器以前使用本机映像生成器 (NGen.exe) 编译的函数已开始搜索。</span><span class="sxs-lookup"><span data-stu-id="4e389-103">Notifies the profiler that a search has started for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e389-104">语法</span><span class="sxs-lookup"><span data-stu-id="4e389-104">Syntax</span></span>  
  
```  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4e389-105">参数</span><span class="sxs-lookup"><span data-stu-id="4e389-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="4e389-106">[in]为其执行搜索的函数 ID。</span><span class="sxs-lookup"><span data-stu-id="4e389-106">[in] The ID of the function for which the search is being performed.</span></span>  
  
 `pbUseCachedFunction`  
 <span data-ttu-id="4e389-107">[out]`true`如果执行引擎应使用缓存的版本的函数 （如果可用）; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="4e389-107">[out] `true` if the execution engine should use the cached version of a function (if available); otherwise `false`.</span></span> <span data-ttu-id="4e389-108">如果值为`false`，执行引擎 JIT 编译的函数而不是使用不是 JIT 编译的版本。</span><span class="sxs-lookup"><span data-stu-id="4e389-108">If the value is `false`, the execution engine JIT-compiles the function instead of using a version that is not JIT-compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e389-109">备注</span><span class="sxs-lookup"><span data-stu-id="4e389-109">Remarks</span></span>  
 <span data-ttu-id="4e389-110">在.NET Framework 2.0 版中，`JITCachedFunctionSearchStarted`和[icorprofilercallback:: Jitcachedfunctionsearchfinished 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md)回调将不会执行常规 NGen 映像中的所有功能。</span><span class="sxs-lookup"><span data-stu-id="4e389-110">In the .NET Framework version 2.0, the `JITCachedFunctionSearchStarted` and [ICorProfilerCallback::JITCachedFunctionSearchFinished Method](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="4e389-111">仅为配置文件优化的 NGen 映像将映像中生成的所有函数的回调。</span><span class="sxs-lookup"><span data-stu-id="4e389-111">Only NGen images optimized for a profile will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="4e389-112">但是，由于的额外开销，探查器应请求探查器优化 NGen 映像仅当它想使用这些回调来强制对函数进行编译的实时 (JIT)。</span><span class="sxs-lookup"><span data-stu-id="4e389-112">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="4e389-113">否则，探查器应使用迟缓策略来收集函数信息。</span><span class="sxs-lookup"><span data-stu-id="4e389-113">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
 <span data-ttu-id="4e389-114">探查器必须支持的分析的应用程序的多个线程同时调用同一方法的情况。</span><span class="sxs-lookup"><span data-stu-id="4e389-114">Profilers must support cases where multiple threads of a profiled application are calling the same method simultaneously.</span></span> <span data-ttu-id="4e389-115">例如，调用线程 A`JITCachedFunctionSearchStarted`和探查器响应通过设置*pbUseCachedFunction*为 FALSE 可强制 JIT 编译。</span><span class="sxs-lookup"><span data-stu-id="4e389-115">For example, thread A calls `JITCachedFunctionSearchStarted` and the profiler responds by setting *pbUseCachedFunction*to FALSE to force JIT compilation.</span></span> <span data-ttu-id="4e389-116">随后将调用的线程[icorprofilercallback:: Jitcompilationstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)和[icorprofilercallback:: Jitcompilationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)。</span><span class="sxs-lookup"><span data-stu-id="4e389-116">Thread A then calls [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) and [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md).</span></span>  
  
 <span data-ttu-id="4e389-117">现在，线程 B 调用`JITCachedFunctionSearchStarted`同一函数的。</span><span class="sxs-lookup"><span data-stu-id="4e389-117">Now thread B calls `JITCachedFunctionSearchStarted` for the same function.</span></span> <span data-ttu-id="4e389-118">即使探查器已声明其意图对 JIT 编译的函数，在探查器接收第二个回调，因为线程 B 之前探查器已响应线程的调用会将发送回调`JITCachedFunctionSearchStarted`。</span><span class="sxs-lookup"><span data-stu-id="4e389-118">Even though the profiler has stated its intention to JIT-compile the function, the profiler receives the second callback because thread B sends the callback before the profiler has responded to thread A's call to `JITCachedFunctionSearchStarted`.</span></span> <span data-ttu-id="4e389-119">在其中线程进行调用的顺序取决于所计划的线程的方式。</span><span class="sxs-lookup"><span data-stu-id="4e389-119">The order in which the threads make calls depends on how the threads are scheduled.</span></span>  
  
 <span data-ttu-id="4e389-120">在探查器收到重复的回调，它必须由引用的值会设置`pbUseCachedFunction`为相同的值的所有重复的回调。</span><span class="sxs-lookup"><span data-stu-id="4e389-120">When the profiler receives duplicate callbacks, it must set the value referenced by `pbUseCachedFunction` to the same value for all the duplicate callbacks.</span></span> <span data-ttu-id="4e389-121">也就是说，当`JITCachedFunctionSearchStarted`多次调用了具有相同`functionId`值，探查器必须响应相同每次。</span><span class="sxs-lookup"><span data-stu-id="4e389-121">That is, when `JITCachedFunctionSearchStarted` is called multiple times with the same `functionId` value, the profiler must respond the same each time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e389-122">惠?</span><span class="sxs-lookup"><span data-stu-id="4e389-122">Requirements</span></span>  
 <span data-ttu-id="4e389-123">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4e389-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e389-124">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4e389-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4e389-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e389-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e389-126">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e389-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e389-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e389-127">See Also</span></span>  
 [<span data-ttu-id="4e389-128">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="4e389-128">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
