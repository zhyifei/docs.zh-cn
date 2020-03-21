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
ms.openlocfilehash: 0cf2014d7007593c51868eff0b488fdab136e362
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175169"
---
# <a name="functionidmapper-function"></a><span data-ttu-id="5135a-102">FunctionIDMapper 函数</span><span class="sxs-lookup"><span data-stu-id="5135a-102">FunctionIDMapper Function</span></span>
<span data-ttu-id="5135a-103">通知探查器，函数的给定标识符可以重新映射到要用于该函数[的函数Enter2、](functionenter2-function.md)[函数Leave2](functionleave2-function.md)和[函数尾声2](functiontailcall2-function.md)回调中使用的替代 ID。</span><span class="sxs-lookup"><span data-stu-id="5135a-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), and [FunctionTailcall2](functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="5135a-104">`FunctionIDMapper` 此外还要使探查器指示它是否想要接收该函数的回调。</span><span class="sxs-lookup"><span data-stu-id="5135a-104">`FunctionIDMapper` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5135a-105">语法</span><span class="sxs-lookup"><span data-stu-id="5135a-105">Syntax</span></span>  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5135a-106">parameters</span><span class="sxs-lookup"><span data-stu-id="5135a-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="5135a-107">\[in] 要重新映射的函数标识符。</span><span class="sxs-lookup"><span data-stu-id="5135a-107">\[in] The function identifier to be remapped.</span></span>

- `pbHookFunction`

  <span data-ttu-id="5135a-108">\[out_ 指向探查器`true`在要接收`FunctionEnter2`时`FunctionLeave2`设置的值的指针， `FunctionTailcall2`否则，它将此值设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="5135a-108">\[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks; otherwise, it sets this value to `false`.</span></span>

## <a name="return-value"></a><span data-ttu-id="5135a-109">返回值</span><span class="sxs-lookup"><span data-stu-id="5135a-109">Return Value</span></span>  
 <span data-ttu-id="5135a-110">探查器返回一个执行引擎用作替代函数标识符的值。</span><span class="sxs-lookup"><span data-stu-id="5135a-110">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="5135a-111">返回值不能为 null，除非在 `pbHookFunction` 中返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="5135a-111">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="5135a-112">否则，空返回值将生成不可预知的结果，包括可能停止该过程。</span><span class="sxs-lookup"><span data-stu-id="5135a-112">Otherwise, a null return value will produce unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5135a-113">备注</span><span class="sxs-lookup"><span data-stu-id="5135a-113">Remarks</span></span>  
 <span data-ttu-id="5135a-114">该`FunctionIDMapper`函数是回调。</span><span class="sxs-lookup"><span data-stu-id="5135a-114">The `FunctionIDMapper` function is a callback.</span></span> <span data-ttu-id="5135a-115">探查器实现了它将函数 ID 重新映射到对探查器更有用的其他标识符。</span><span class="sxs-lookup"><span data-stu-id="5135a-115">It is implemented by the profiler to remap a function ID to some other identifier that is more useful for the profiler.</span></span> <span data-ttu-id="5135a-116">返回`FunctionIDMapper`用于任何给定函数的备用 ID。</span><span class="sxs-lookup"><span data-stu-id="5135a-116">The `FunctionIDMapper` returns the alternate ID to be used for any given function.</span></span> <span data-ttu-id="5135a-117">然后，执行引擎通过将此备用 ID（除了传统的函数`clientData`ID）传递给`FunctionEnter2`、`FunctionLeave2`和`FunctionTailcall2`挂钩参数中的探查器来标识为其调用挂钩的功能来响应探查器的请求。</span><span class="sxs-lookup"><span data-stu-id="5135a-117">The execution engine then honors the profiler's request by passing this alternate ID, in addition to the traditional function ID, back to the profiler in the `clientData` parameter of the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` hooks, to identify the function for which the hook is being called.</span></span>  
  
 <span data-ttu-id="5135a-118">您可以使用[ICorProfilerInfo：：Set功能IDMapper](icorprofilerinfo-setfunctionidmapper-method.md)方法来指定`FunctionIDMapper`函数的实现。</span><span class="sxs-lookup"><span data-stu-id="5135a-118">You can use the [ICorProfilerInfo::SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) method to specify the implementation of the `FunctionIDMapper` function.</span></span> <span data-ttu-id="5135a-119">您只能调用该方法`ICorProfilerInfo::SetFunctionIDMapper`一次，我们建议您在[ICorProfiler 回调：：初始化](icorprofilercallback-initialize-method.md)回调中调用该方法。</span><span class="sxs-lookup"><span data-stu-id="5135a-119">You can call the `ICorProfilerInfo::SetFunctionIDMapper` method only once, and we recommend that you do so in the [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
 <span data-ttu-id="5135a-120">默认情况下，假定使用[ICorProfilerInfo：：setEventMask](icorprofilerinfo-seteventmask-method.md)设置COR_PRF_MONITOR_ENTERLEAVE标志的探查器，并且通过[ICorProfilerInfo 设置挂钩：设置EnterLeave函数Hooks](icorprofilerinfo-setenterleavefunctionhooks-method.md)或[ICorProfilerInfo2：SetEnterLeave函数Hooks2，](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)应接收 每个函数的`FunctionEnter2`、`FunctionLeave2`和`FunctionTailcall2`回调。</span><span class="sxs-lookup"><span data-stu-id="5135a-120">By default, it is assumed that a profiler that sets the COR_PRF_MONITOR_ENTERLEAVE flag by using [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md), and which sets hooks via [ICorProfilerInfo::SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) or [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), should receive the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks for every function.</span></span> <span data-ttu-id="5135a-121">但是，探查器可以通过`FunctionIDMapper`设置为`pbHookFunction`有选择地避免接收某些函数的回调`false`。</span><span class="sxs-lookup"><span data-stu-id="5135a-121">However, profilers may implement `FunctionIDMapper` to selectively avoid receiving these callbacks for certain functions by setting `pbHookFunction` to `false`.</span></span>  
  
 <span data-ttu-id="5135a-122">探查器应容忍配置文件应用程序的多个线程同时调用同一方法/函数的情况。</span><span class="sxs-lookup"><span data-stu-id="5135a-122">Profilers should be tolerant of cases where multiple threads of a profiled application are calling the same method/function simultaneously.</span></span> <span data-ttu-id="5135a-123">在这种情况下，探查器可能会收到同`FunctionIDMapper``FunctionID`一的多个回调。</span><span class="sxs-lookup"><span data-stu-id="5135a-123">In such cases, the profiler may receive multiple `FunctionIDMapper` callbacks for the same `FunctionID`.</span></span> <span data-ttu-id="5135a-124">当同调用多次回调时，探查器应确定应从此回调返回相同的`FunctionID`值。</span><span class="sxs-lookup"><span data-stu-id="5135a-124">The profiler should be certain to return the same values from this callback when it is called multiple times with the same `FunctionID`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5135a-125">要求</span><span class="sxs-lookup"><span data-stu-id="5135a-125">Requirements</span></span>  
 <span data-ttu-id="5135a-126">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5135a-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5135a-127">**标题：** 科尔普罗普.伊德尔</span><span class="sxs-lookup"><span data-stu-id="5135a-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="5135a-128">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5135a-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5135a-129">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5135a-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5135a-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5135a-130">See also</span></span>

- [<span data-ttu-id="5135a-131">SetFunctionIDMapper 方法</span><span class="sxs-lookup"><span data-stu-id="5135a-131">SetFunctionIDMapper Method</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="5135a-132">FunctionIDMapper2 函数</span><span class="sxs-lookup"><span data-stu-id="5135a-132">FunctionIDMapper2 Function</span></span>](functionidmapper2-function.md)
- [<span data-ttu-id="5135a-133">FunctionEnter2 函数</span><span class="sxs-lookup"><span data-stu-id="5135a-133">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="5135a-134">FunctionLeave2 函数</span><span class="sxs-lookup"><span data-stu-id="5135a-134">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="5135a-135">FunctionTailcall2 函数</span><span class="sxs-lookup"><span data-stu-id="5135a-135">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="5135a-136">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="5135a-136">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
