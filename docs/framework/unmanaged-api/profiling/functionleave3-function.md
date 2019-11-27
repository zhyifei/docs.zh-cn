---
title: FunctionLeave3 函数
ms.date: 03/30/2017
api_name:
- FunctionLeave3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave3
helpviewer_keywords:
- FunctionLeave3 function [.NET Framework profiling]
ms.assetid: 5d798088-7992-48a0-ae55-d2a7ee31913f
topic_type:
- apiref
ms.openlocfilehash: 104a6c3c42c310513040cb45db7f51ffe729c19d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427447"
---
# <a name="functionleave3-function"></a><span data-ttu-id="d5150-102">FunctionLeave3 函数</span><span class="sxs-lookup"><span data-stu-id="d5150-102">FunctionLeave3 Function</span></span>
<span data-ttu-id="d5150-103">通知探查器控制正在从函数返回。</span><span class="sxs-lookup"><span data-stu-id="d5150-103">Notifies the profiler that control is being returned from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5150-104">语法</span><span class="sxs-lookup"><span data-stu-id="d5150-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5150-105">参数</span><span class="sxs-lookup"><span data-stu-id="d5150-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="d5150-106">中从中返回控件的函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="d5150-106">[in] The identifier of the function from which control is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5150-107">备注</span><span class="sxs-lookup"><span data-stu-id="d5150-107">Remarks</span></span>  
 <span data-ttu-id="d5150-108">`FunctionLeave3` 回调函数将在调用函数时通知探查器，但不支持返回值检查。</span><span class="sxs-lookup"><span data-stu-id="d5150-108">The `FunctionLeave3` callback function notifies the profiler as functions are being called, but does not support return value inspection.</span></span> <span data-ttu-id="d5150-109">使用[ICorProfilerInfo3：： SetEnterLeaveFunctionHooks3 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)注册此函数的实现。</span><span class="sxs-lookup"><span data-stu-id="d5150-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="d5150-110">`FunctionLeave3` 函数是回调;必须实现此方法。</span><span class="sxs-lookup"><span data-stu-id="d5150-110">The `FunctionLeave3` function is a callback; you must implement it.</span></span> <span data-ttu-id="d5150-111">实现必须使用 `__declspec(naked)` 存储类特性。</span><span class="sxs-lookup"><span data-stu-id="d5150-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="d5150-112">在调用此函数之前，执行引擎不会保存任何注册。</span><span class="sxs-lookup"><span data-stu-id="d5150-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="d5150-113">进入时，必须保存使用的所有寄存器，包括浮点单元（FPU）中的所有寄存器。</span><span class="sxs-lookup"><span data-stu-id="d5150-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="d5150-114">退出时，必须通过弹出由其调用方推送的所有参数来还原堆栈。</span><span class="sxs-lookup"><span data-stu-id="d5150-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="d5150-115">`FunctionLeave3` 的实现不应阻塞，因为它将延迟垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="d5150-115">The implementation of `FunctionLeave3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="d5150-116">实现不应尝试垃圾回收，因为堆栈可能不处于垃圾回收友好状态。</span><span class="sxs-lookup"><span data-stu-id="d5150-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="d5150-117">如果尝试垃圾回收，则运行时将被阻止，直到 `FunctionLeave3` 返回。</span><span class="sxs-lookup"><span data-stu-id="d5150-117">If a garbage collection is attempted, the runtime will block until `FunctionLeave3` returns.</span></span>  
  
 <span data-ttu-id="d5150-118">`FunctionLeave3` 函数不得调入托管代码或以任何方式导致托管内存分配。</span><span class="sxs-lookup"><span data-stu-id="d5150-118">The `FunctionLeave3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5150-119">要求</span><span class="sxs-lookup"><span data-stu-id="d5150-119">Requirements</span></span>  
 <span data-ttu-id="d5150-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d5150-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5150-121">**标头：** Corprof.idl .idl</span><span class="sxs-lookup"><span data-stu-id="d5150-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="d5150-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5150-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5150-123">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5150-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5150-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5150-124">See also</span></span>

- [<span data-ttu-id="d5150-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="d5150-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="d5150-126">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="d5150-126">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="d5150-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="d5150-127">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="d5150-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="d5150-128">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="d5150-129">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="d5150-129">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="d5150-130">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="d5150-130">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="d5150-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="d5150-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="d5150-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="d5150-132">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="d5150-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="d5150-133">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="d5150-134">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="d5150-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
