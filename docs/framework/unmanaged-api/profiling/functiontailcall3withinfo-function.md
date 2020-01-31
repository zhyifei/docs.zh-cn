---
title: FunctionTailcall3WithInfo 函数
ms.date: 03/30/2017
api_name:
- FunctionTailcall3WithInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall3WithInfo
helpviewer_keywords:
- FunctionTailcall3WithInfo function [.NET Framework profiling]
ms.assetid: 46380fcc-0198-43ae-a1f5-2d4939425886
topic_type:
- apiref
ms.openlocfilehash: 0aa43954c3e10d04524bf976d0dd3b29d2bc724c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866802"
---
# <a name="functiontailcall3withinfo-function"></a><span data-ttu-id="6e6f8-102">FunctionTailcall3WithInfo 函数</span><span class="sxs-lookup"><span data-stu-id="6e6f8-102">FunctionTailcall3WithInfo Function</span></span>
<span data-ttu-id="6e6f8-103">通知探查器，当前正在执行的函数即将对另一个函数执行尾调用，并提供一个可传递给[ICorProfilerInfo3：： GetFunctionTailcall3Info 方法](icorprofilerinfo3-getfunctiontailcall3info-method.md)以检索堆栈帧的句柄。</span><span class="sxs-lookup"><span data-stu-id="6e6f8-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionTailcall3Info method](icorprofilerinfo3-getfunctiontailcall3info-method.md) to retrieve the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e6f8-104">语法</span><span class="sxs-lookup"><span data-stu-id="6e6f8-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionTailcall3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e6f8-105">参数</span><span class="sxs-lookup"><span data-stu-id="6e6f8-105">Parameters</span></span>  

- `functionIDOrClientID`

  <span data-ttu-id="6e6f8-106">\[中的]：要进行尾调用的当前正在执行的函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="6e6f8-106">\[in] The identifier of the currently executing function that is about to make a tail call.</span></span>

- `eltInfo`

  <span data-ttu-id="6e6f8-107">\[中] 表示有关给定堆栈帧的信息的不透明的句柄。</span><span class="sxs-lookup"><span data-stu-id="6e6f8-107">\[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="6e6f8-108">此句柄仅在其传递到的回调期间有效。</span><span class="sxs-lookup"><span data-stu-id="6e6f8-108">This handle is valid only during the callback to which it is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="6e6f8-109">备注</span><span class="sxs-lookup"><span data-stu-id="6e6f8-109">Remarks</span></span>  
 <span data-ttu-id="6e6f8-110">`FunctionTailcall3WithInfo` 回调方法会在调用函数时通知探查器，并允许探查器使用[ICorProfilerInfo3：： GetFunctionTailcall3Info 方法](icorprofilerinfo3-getfunctiontailcall3info-method.md)来检查堆栈帧。</span><span class="sxs-lookup"><span data-stu-id="6e6f8-110">The `FunctionTailcall3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionTailcall3Info method](icorprofilerinfo3-getfunctiontailcall3info-method.md) to inspect the stack frame.</span></span> <span data-ttu-id="6e6f8-111">若要访问 stack 帧信息，必须设置 `COR_PRF_ENABLE_FRAME_INFO` 标志。</span><span class="sxs-lookup"><span data-stu-id="6e6f8-111">To access stack frame information, the `COR_PRF_ENABLE_FRAME_INFO` flag has to be set.</span></span> <span data-ttu-id="6e6f8-112">探查器可以使用[ICorProfilerInfo：： SetEventMask 方法](icorprofilerinfo-seteventmask-method.md)来设置事件标志，然后使用[ICorProfilerInfo3：： SetEnterLeaveFunctionHooks3WithInfo 方法](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)来注册此函数的实现。</span><span class="sxs-lookup"><span data-stu-id="6e6f8-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="6e6f8-113">`FunctionTailcall3WithInfo` 函数是回调;必须实现此方法。</span><span class="sxs-lookup"><span data-stu-id="6e6f8-113">The `FunctionTailcall3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="6e6f8-114">实现必须使用 `__declspec(naked)` 存储类特性。</span><span class="sxs-lookup"><span data-stu-id="6e6f8-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="6e6f8-115">在调用此函数之前，执行引擎不会保存任何注册。</span><span class="sxs-lookup"><span data-stu-id="6e6f8-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="6e6f8-116">进入时，必须保存使用的所有寄存器，包括浮点单元（FPU）中的所有寄存器。</span><span class="sxs-lookup"><span data-stu-id="6e6f8-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="6e6f8-117">退出时，必须通过弹出由其调用方推送的所有参数来还原堆栈。</span><span class="sxs-lookup"><span data-stu-id="6e6f8-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="6e6f8-118">`FunctionTailcall3WithInfo` 的实现不应阻塞，因为它将延迟垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="6e6f8-118">The implementation of `FunctionTailcall3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="6e6f8-119">实现不应尝试垃圾回收，因为堆栈可能不处于垃圾回收友好状态。</span><span class="sxs-lookup"><span data-stu-id="6e6f8-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="6e6f8-120">如果尝试垃圾回收，则运行时将被阻止，直到 `FunctionTailcall3WithInfo` 返回。</span><span class="sxs-lookup"><span data-stu-id="6e6f8-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="6e6f8-121">此外，FunctionTailcall3WithInfo 函数不得调入托管代码或以任何方式引发托管内存分配。</span><span class="sxs-lookup"><span data-stu-id="6e6f8-121">Also, the FunctionTailcall3WithInfo function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e6f8-122">需求</span><span class="sxs-lookup"><span data-stu-id="6e6f8-122">Requirements</span></span>  
 <span data-ttu-id="6e6f8-123">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6e6f8-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e6f8-124">**标头：** Corprof.idl .idl</span><span class="sxs-lookup"><span data-stu-id="6e6f8-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="6e6f8-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e6f8-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e6f8-126">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e6f8-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e6f8-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e6f8-127">See also</span></span>

- [<span data-ttu-id="6e6f8-128">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="6e6f8-128">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="6e6f8-129">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="6e6f8-129">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="6e6f8-130">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="6e6f8-130">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="6e6f8-131">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="6e6f8-131">FunctionEnter3WithInfo</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="6e6f8-132">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="6e6f8-132">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="6e6f8-133">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="6e6f8-133">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="6e6f8-134">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="6e6f8-134">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="6e6f8-135">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="6e6f8-135">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="6e6f8-136">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="6e6f8-136">SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="6e6f8-137">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="6e6f8-137">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
