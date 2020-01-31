---
title: FunctionTailcall2 函数
ms.date: 03/30/2017
api_name:
- FunctionTailcall2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall2
helpviewer_keywords:
- FunctionTailcall2 function [.NET Framework profiling]
ms.assetid: 249f9892-b5a9-41e1-b329-28a925904df6
topic_type:
- apiref
ms.openlocfilehash: 7f6ef2c410d49e2e63b88d6f47c33c211f2a8dd8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790285"
---
# <a name="functiontailcall2-function"></a><span data-ttu-id="ffcb4-102">FunctionTailcall2 函数</span><span class="sxs-lookup"><span data-stu-id="ffcb4-102">FunctionTailcall2 Function</span></span>
<span data-ttu-id="ffcb4-103">通知探查器，当前正在执行的函数即将对另一个函数执行尾调用，并提供有关堆栈帧的信息。</span><span class="sxs-lookup"><span data-stu-id="ffcb4-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffcb4-104">语法</span><span class="sxs-lookup"><span data-stu-id="ffcb4-104">Syntax</span></span>  
  
```cpp
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,   
    [in] UINT_PTR           clientData,   
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ffcb4-105">参数</span><span class="sxs-lookup"><span data-stu-id="ffcb4-105">Parameters</span></span>

- `funcId`

  <span data-ttu-id="ffcb4-106">\[中的]：要进行尾调用的当前正在执行的函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="ffcb4-106">\[in] The identifier of the currently executing function that is about to make a tail call.</span></span>

- `clientData`

  <span data-ttu-id="ffcb4-107">\[）中的重新映射函数标识符，该标识符之前通过[FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)指定的探查器将进行尾调用。</span><span class="sxs-lookup"><span data-stu-id="ffcb4-107">\[in] The remapped function identifier, which the profiler previously specified via [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md), of the currently executing function that is about to make a tail call.</span></span>
  
- `func`

  <span data-ttu-id="ffcb4-108">\[中的] `COR_PRF_FRAME_INFO` 值，该值指向有关堆栈帧的信息。</span><span class="sxs-lookup"><span data-stu-id="ffcb4-108">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>

  <span data-ttu-id="ffcb4-109">探查器应将此视为不透明的句柄，该句柄可传递回[ICorProfilerInfo2：： GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)方法中的执行引擎。</span><span class="sxs-lookup"><span data-stu-id="ffcb4-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>

## <a name="remarks"></a><span data-ttu-id="ffcb4-110">备注</span><span class="sxs-lookup"><span data-stu-id="ffcb4-110">Remarks</span></span>  
 <span data-ttu-id="ffcb4-111">尾调用的目标函数将使用当前堆栈帧，并将直接返回到进行尾调用的函数的调用方。</span><span class="sxs-lookup"><span data-stu-id="ffcb4-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="ffcb4-112">这意味着将不会为作为尾调用目标的函数发出[FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)回调。</span><span class="sxs-lookup"><span data-stu-id="ffcb4-112">This means that a [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="ffcb4-113">`FunctionTailcall2` 函数返回后，`func` 参数的值无效，因为该值可能会更改或被销毁。</span><span class="sxs-lookup"><span data-stu-id="ffcb4-113">The value of the `func` parameter is not valid after the `FunctionTailcall2` function returns because the value may change or be destroyed.</span></span>  
  
 <span data-ttu-id="ffcb4-114">`FunctionTailcall2` 函数是回调;必须实现此方法。</span><span class="sxs-lookup"><span data-stu-id="ffcb4-114">The `FunctionTailcall2` function is a callback; you must implement it.</span></span> <span data-ttu-id="ffcb4-115">实现必须使用 `__declspec`（`naked`）存储类特性。</span><span class="sxs-lookup"><span data-stu-id="ffcb4-115">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="ffcb4-116">在调用此函数之前，执行引擎不会保存任何注册。</span><span class="sxs-lookup"><span data-stu-id="ffcb4-116">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="ffcb4-117">进入时，必须保存使用的所有寄存器，包括浮点单元（FPU）中的所有寄存器。</span><span class="sxs-lookup"><span data-stu-id="ffcb4-117">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="ffcb4-118">退出时，必须通过弹出由其调用方推送的所有参数来还原堆栈。</span><span class="sxs-lookup"><span data-stu-id="ffcb4-118">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="ffcb4-119">`FunctionTailcall2` 的实现不应被阻止，因为它将延迟垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="ffcb4-119">The implementation of `FunctionTailcall2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="ffcb4-120">实现不应尝试垃圾回收，因为堆栈可能不处于垃圾回收友好状态。</span><span class="sxs-lookup"><span data-stu-id="ffcb4-120">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="ffcb4-121">如果尝试垃圾回收，则运行时将被阻止，直到 `FunctionTailcall2` 返回。</span><span class="sxs-lookup"><span data-stu-id="ffcb4-121">If a garbage collection is attempted, the runtime will block until `FunctionTailcall2` returns.</span></span>  
  
 <span data-ttu-id="ffcb4-122">此外，`FunctionTailcall2` 函数不得调入托管代码或以任何方式导致托管的内存分配。</span><span class="sxs-lookup"><span data-stu-id="ffcb4-122">Also, the `FunctionTailcall2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffcb4-123">需求</span><span class="sxs-lookup"><span data-stu-id="ffcb4-123">Requirements</span></span>  
 <span data-ttu-id="ffcb4-124">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ffcb4-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffcb4-125">**标头：** Corprof.idl .idl</span><span class="sxs-lookup"><span data-stu-id="ffcb4-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="ffcb4-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ffcb4-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ffcb4-127">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffcb4-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffcb4-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ffcb4-128">See also</span></span>

- [<span data-ttu-id="ffcb4-129">FunctionEnter2 函数</span><span class="sxs-lookup"><span data-stu-id="ffcb4-129">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="ffcb4-130">FunctionLeave2 函数</span><span class="sxs-lookup"><span data-stu-id="ffcb4-130">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="ffcb4-131">SetEnterLeaveFunctionHooks2 方法</span><span class="sxs-lookup"><span data-stu-id="ffcb4-131">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="ffcb4-132">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="ffcb4-132">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
