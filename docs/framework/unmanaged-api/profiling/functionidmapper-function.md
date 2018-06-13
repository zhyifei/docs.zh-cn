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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 151b790afaf6a251ba5d8d8932f44a503cde853a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458593"
---
# <a name="functionidmapper-function"></a><span data-ttu-id="8fd88-102">FunctionIDMapper 函数</span><span class="sxs-lookup"><span data-stu-id="8fd88-102">FunctionIDMapper Function</span></span>
<span data-ttu-id="8fd88-103">通知探查器函数的给定的标识符可能被重新映射到要在中使用的备用 ID [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)， [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)，和[FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)该函数的回调。</span><span class="sxs-lookup"><span data-stu-id="8fd88-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), and [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="8fd88-104">`FunctionIDMapper` 此外还要使探查器指示它是否想要接收该函数的回调。</span><span class="sxs-lookup"><span data-stu-id="8fd88-104">`FunctionIDMapper` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fd88-105">语法</span><span class="sxs-lookup"><span data-stu-id="8fd88-105">Syntax</span></span>  
  
```  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,   
    [out] BOOL       *pbHookFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8fd88-106">参数</span><span class="sxs-lookup"><span data-stu-id="8fd88-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="8fd88-107">[in] 要重新映射的函数标识符。</span><span class="sxs-lookup"><span data-stu-id="8fd88-107">[in] The function identifier to be remapped.</span></span>  
  
 `pbHookFunction`  
 <span data-ttu-id="8fd88-108">[out]指向一个值，探查器将设置为`true`如果想要接收`FunctionEnter2`， `FunctionLeave2`，和`FunctionTailcall2`回调; 否则，它将此值设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="8fd88-108">[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks; otherwise, it sets this value to `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8fd88-109">返回值</span><span class="sxs-lookup"><span data-stu-id="8fd88-109">Return Value</span></span>  
 <span data-ttu-id="8fd88-110">探查器返回一个执行引擎用作替代函数标识符的值。</span><span class="sxs-lookup"><span data-stu-id="8fd88-110">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="8fd88-111">返回值不能为 null，除非在 `pbHookFunction` 中返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="8fd88-111">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="8fd88-112">否则，返回值为 null 会产生不可预知的结果，包括可能停止该过程。</span><span class="sxs-lookup"><span data-stu-id="8fd88-112">Otherwise, a null return value will produce unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8fd88-113">备注</span><span class="sxs-lookup"><span data-stu-id="8fd88-113">Remarks</span></span>  
 <span data-ttu-id="8fd88-114">`FunctionIDMapper`函数为回调。</span><span class="sxs-lookup"><span data-stu-id="8fd88-114">The `FunctionIDMapper` function is a callback.</span></span> <span data-ttu-id="8fd88-115">它由探查器，若要重新映射到探查器更为有用的某个其他标识符的函数 ID 来实现。</span><span class="sxs-lookup"><span data-stu-id="8fd88-115">It is implemented by the profiler to remap a function ID to some other identifier that is more useful for the profiler.</span></span> <span data-ttu-id="8fd88-116">`FunctionIDMapper`返回要用于任何给定函数的备用 ID。</span><span class="sxs-lookup"><span data-stu-id="8fd88-116">The `FunctionIDMapper` returns the alternate ID to be used for any given function.</span></span> <span data-ttu-id="8fd88-117">执行引擎然后遵循探查器的请求将此备用 ID，除了传统的函数 ID 传递回中的探查器`clientData`参数`FunctionEnter2`， `FunctionLeave2`，和`FunctionTailcall2`挂钩，以标识为其调用挂钩函数。</span><span class="sxs-lookup"><span data-stu-id="8fd88-117">The execution engine then honors the profiler's request by passing this alternate ID, in addition to the traditional function ID, back to the profiler in the `clientData` parameter of the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` hooks, to identify the function for which the hook is being called.</span></span>  
  
 <span data-ttu-id="8fd88-118">你可以使用[icorprofilerinfo:: Setfunctionidmapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)方法，以指定的实现`FunctionIDMapper`函数。</span><span class="sxs-lookup"><span data-stu-id="8fd88-118">You can use the [ICorProfilerInfo::SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) method to specify the implementation of the `FunctionIDMapper` function.</span></span> <span data-ttu-id="8fd88-119">你可以调用`ICorProfilerInfo::SetFunctionIDMapper`方法一次，我们建议你在执行[icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="8fd88-119">You can call the `ICorProfilerInfo::SetFunctionIDMapper` method only once, and we recommend that you do so in the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
 <span data-ttu-id="8fd88-120">默认情况下，假定，探查器，设置 COR_PRF_MONITOR_ENTERLEAVE 标志使用[icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)，和用于设置通过挂钩[icorprofilerinfo:: Setenterleavefunctionhooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md)或[icorprofilerinfo2:: Setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)，应该会收到`FunctionEnter2`， `FunctionLeave2`，和`FunctionTailcall2`每个函数的回调。</span><span class="sxs-lookup"><span data-stu-id="8fd88-120">By default, it is assumed that a profiler that sets the COR_PRF_MONITOR_ENTERLEAVE flag by using [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md), and which sets hooks via [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) or [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), should receive the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks for every function.</span></span> <span data-ttu-id="8fd88-121">但是，探查器可以实现`FunctionIDMapper`要有选择地避免某些接收这些回调函数通过设置`pbHookFunction`到`false`。</span><span class="sxs-lookup"><span data-stu-id="8fd88-121">However, profilers may implement `FunctionIDMapper` to selectively avoid receiving these callbacks for certain functions by setting `pbHookFunction` to `false`.</span></span>  
  
 <span data-ttu-id="8fd88-122">探查器应容许所分析应用程序的多个线程同时调用每个函数的方法相同的情况。</span><span class="sxs-lookup"><span data-stu-id="8fd88-122">Profilers should be tolerant of cases where multiple threads of a profiled application are calling the same method/function simultaneously.</span></span> <span data-ttu-id="8fd88-123">在这种情况下，探查器可能会收到多个`FunctionIDMapper`相同的回调`FunctionID`。</span><span class="sxs-lookup"><span data-stu-id="8fd88-123">In such cases, the profiler may receive multiple `FunctionIDMapper` callbacks for the same `FunctionID`.</span></span> <span data-ttu-id="8fd88-124">探查器应请务必从此回调返回相同的值，它具有相同调用多次时`FunctionID`。</span><span class="sxs-lookup"><span data-stu-id="8fd88-124">The profiler should be certain to return the same values from this callback when it is called multiple times with the same `FunctionID`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fd88-125">要求</span><span class="sxs-lookup"><span data-stu-id="8fd88-125">Requirements</span></span>  
 <span data-ttu-id="8fd88-126">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8fd88-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fd88-127">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="8fd88-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="8fd88-128">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8fd88-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8fd88-129">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fd88-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fd88-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="8fd88-130">See Also</span></span>  
 [<span data-ttu-id="8fd88-131">SetFunctionIDMapper 方法</span><span class="sxs-lookup"><span data-stu-id="8fd88-131">SetFunctionIDMapper Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [<span data-ttu-id="8fd88-132">FunctionIDMapper2 函数</span><span class="sxs-lookup"><span data-stu-id="8fd88-132">FunctionIDMapper2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)  
 [<span data-ttu-id="8fd88-133">FunctionEnter2 函数</span><span class="sxs-lookup"><span data-stu-id="8fd88-133">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="8fd88-134">FunctionLeave2 函数</span><span class="sxs-lookup"><span data-stu-id="8fd88-134">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="8fd88-135">FunctionTailcall2 函数</span><span class="sxs-lookup"><span data-stu-id="8fd88-135">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [<span data-ttu-id="8fd88-136">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="8fd88-136">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
