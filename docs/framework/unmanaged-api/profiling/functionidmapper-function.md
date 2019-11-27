---
title: FunctionIDMapper 函数
ms.date: 03/30/2017
api_name:
- FunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper
helpviewer_keywords:
- FunctionIDMapper function [.NET Framework profiling]
ms.assetid: b8205b60-1893-4303-8cff-7ac5a00892aa
topic_type:
- apiref
ms.openlocfilehash: 23c6f0a29160b6e1dc194cf360c07374c565522b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440701"
---
# <a name="functionidmapper-function"></a><span data-ttu-id="10f1a-102">FunctionIDMapper 函数</span><span class="sxs-lookup"><span data-stu-id="10f1a-102">FunctionIDMapper Function</span></span>
<span data-ttu-id="10f1a-103">通知探查器可能会将函数的给定标识符重新映射到备用 ID，以在该函数的[FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)、 [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)和[FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)回调中使用。</span><span class="sxs-lookup"><span data-stu-id="10f1a-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), and [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="10f1a-104">`FunctionIDMapper` 还允许探查器指示是否要接收该函数的回调。</span><span class="sxs-lookup"><span data-stu-id="10f1a-104">`FunctionIDMapper` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10f1a-105">语法</span><span class="sxs-lookup"><span data-stu-id="10f1a-105">Syntax</span></span>  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,   
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10f1a-106">参数</span><span class="sxs-lookup"><span data-stu-id="10f1a-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="10f1a-107">[in] 要重新映射的函数标识符。</span><span class="sxs-lookup"><span data-stu-id="10f1a-107">[in] The function identifier to be remapped.</span></span>  
  
 `pbHookFunction`  
 <span data-ttu-id="10f1a-108">弄指向一个值的指针，如果探查器要接收 `FunctionEnter2`、`FunctionLeave2`和 `FunctionTailcall2` 回调，则该值将设置为 `true`;否则，它会将此值设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="10f1a-108">[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks; otherwise, it sets this value to `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10f1a-109">返回值</span><span class="sxs-lookup"><span data-stu-id="10f1a-109">Return Value</span></span>  
 <span data-ttu-id="10f1a-110">探查器返回一个执行引擎用作替代函数标识符的值。</span><span class="sxs-lookup"><span data-stu-id="10f1a-110">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="10f1a-111">返回值不能为 null，除非在 `false` 中返回 `pbHookFunction`。</span><span class="sxs-lookup"><span data-stu-id="10f1a-111">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="10f1a-112">否则，空返回值将产生不可预知的结果，包括可能停止进程。</span><span class="sxs-lookup"><span data-stu-id="10f1a-112">Otherwise, a null return value will produce unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10f1a-113">备注</span><span class="sxs-lookup"><span data-stu-id="10f1a-113">Remarks</span></span>  
 <span data-ttu-id="10f1a-114">`FunctionIDMapper` 函数是回调。</span><span class="sxs-lookup"><span data-stu-id="10f1a-114">The `FunctionIDMapper` function is a callback.</span></span> <span data-ttu-id="10f1a-115">它由探查器实现，用于将函数 ID 重新映射到其他更适用于探查器的标识符。</span><span class="sxs-lookup"><span data-stu-id="10f1a-115">It is implemented by the profiler to remap a function ID to some other identifier that is more useful for the profiler.</span></span> <span data-ttu-id="10f1a-116">`FunctionIDMapper` 返回要用于任何给定函数的备用 ID。</span><span class="sxs-lookup"><span data-stu-id="10f1a-116">The `FunctionIDMapper` returns the alternate ID to be used for any given function.</span></span> <span data-ttu-id="10f1a-117">然后，执行引擎通过将此备用 ID （除了传统函数 ID）传递回探查器的请求，将此备用 ID 传递回 `FunctionEnter2`、`FunctionLeave2`和 `FunctionTailcall2` 挂钩的 `clientData` 参数中的探查器，以标识正在为其调用挂钩的函数。</span><span class="sxs-lookup"><span data-stu-id="10f1a-117">The execution engine then honors the profiler's request by passing this alternate ID, in addition to the traditional function ID, back to the profiler in the `clientData` parameter of the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` hooks, to identify the function for which the hook is being called.</span></span>  
  
 <span data-ttu-id="10f1a-118">您可以使用[ICorProfilerInfo：： SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)方法指定 `FunctionIDMapper` 函数的实现。</span><span class="sxs-lookup"><span data-stu-id="10f1a-118">You can use the [ICorProfilerInfo::SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) method to specify the implementation of the `FunctionIDMapper` function.</span></span> <span data-ttu-id="10f1a-119">只能调用一次 `ICorProfilerInfo::SetFunctionIDMapper` 方法，我们建议在[ICorProfilerCallback：： Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)回调中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="10f1a-119">You can call the `ICorProfilerInfo::SetFunctionIDMapper` method only once, and we recommend that you do so in the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
 <span data-ttu-id="10f1a-120">默认情况下，假定探查器通过使用[ICorProfilerInfo：： SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)设置 COR_PRF_MONITOR_ENTERLEAVE 标志，并通过[ICorProfilerInfo：： SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md)或[ICorProfilerInfo2：： SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)设置挂钩，应接收每个函数的 `FunctionEnter2`、`FunctionLeave2`和 `FunctionTailcall2` 回调。</span><span class="sxs-lookup"><span data-stu-id="10f1a-120">By default, it is assumed that a profiler that sets the COR_PRF_MONITOR_ENTERLEAVE flag by using [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md), and which sets hooks via [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) or [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), should receive the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks for every function.</span></span> <span data-ttu-id="10f1a-121">但是，探查器可能会实现 `FunctionIDMapper` 通过将 `pbHookFunction` 设置为 `false`来有选择地避免为某些函数接收这些回调。</span><span class="sxs-lookup"><span data-stu-id="10f1a-121">However, profilers may implement `FunctionIDMapper` to selectively avoid receiving these callbacks for certain functions by setting `pbHookFunction` to `false`.</span></span>  
  
 <span data-ttu-id="10f1a-122">在分析的应用程序的多个线程同时调用相同的方法/函数的情况下，探查器应该是一种容错方法。</span><span class="sxs-lookup"><span data-stu-id="10f1a-122">Profilers should be tolerant of cases where multiple threads of a profiled application are calling the same method/function simultaneously.</span></span> <span data-ttu-id="10f1a-123">在这种情况下，探查器可能会收到同一 `FunctionID`的多个 `FunctionIDMapper` 回调。</span><span class="sxs-lookup"><span data-stu-id="10f1a-123">In such cases, the profiler may receive multiple `FunctionIDMapper` callbacks for the same `FunctionID`.</span></span> <span data-ttu-id="10f1a-124">如果多次用相同的 `FunctionID`调用，则探查器应确保从此回调返回相同的值。</span><span class="sxs-lookup"><span data-stu-id="10f1a-124">The profiler should be certain to return the same values from this callback when it is called multiple times with the same `FunctionID`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10f1a-125">要求</span><span class="sxs-lookup"><span data-stu-id="10f1a-125">Requirements</span></span>  
 <span data-ttu-id="10f1a-126">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="10f1a-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10f1a-127">**标头：** Corprof.idl .idl</span><span class="sxs-lookup"><span data-stu-id="10f1a-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="10f1a-128">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10f1a-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10f1a-129">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10f1a-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10f1a-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10f1a-130">See also</span></span>

- [<span data-ttu-id="10f1a-131">SetFunctionIDMapper 方法</span><span class="sxs-lookup"><span data-stu-id="10f1a-131">SetFunctionIDMapper Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="10f1a-132">FunctionIDMapper2 函数</span><span class="sxs-lookup"><span data-stu-id="10f1a-132">FunctionIDMapper2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)
- [<span data-ttu-id="10f1a-133">FunctionEnter2 函数</span><span class="sxs-lookup"><span data-stu-id="10f1a-133">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="10f1a-134">FunctionLeave2 函数</span><span class="sxs-lookup"><span data-stu-id="10f1a-134">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="10f1a-135">FunctionTailcall2 函数</span><span class="sxs-lookup"><span data-stu-id="10f1a-135">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="10f1a-136">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="10f1a-136">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
