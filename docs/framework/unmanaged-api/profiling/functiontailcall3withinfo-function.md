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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c4c3487f39d4f4c667ec9eb4705e17ccf29d9a4c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490380"
---
# <a name="functiontailcall3withinfo-function"></a><span data-ttu-id="c2c9e-102">FunctionTailcall3WithInfo 函数</span><span class="sxs-lookup"><span data-stu-id="c2c9e-102">FunctionTailcall3WithInfo Function</span></span>
<span data-ttu-id="c2c9e-103">通知当前正在执行的函数将执行到另一个函数的结尾调用探查器和提供句柄，可传递给[ICorProfilerInfo3::GetFunctionTailcall3Info 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md)检索堆栈帧。</span><span class="sxs-lookup"><span data-stu-id="c2c9e-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionTailcall3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) to retrieve the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2c9e-104">语法</span><span class="sxs-lookup"><span data-stu-id="c2c9e-104">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2c9e-105">参数</span><span class="sxs-lookup"><span data-stu-id="c2c9e-105">Parameters</span></span>  
 `functionIDOrClientID`  
 <span data-ttu-id="c2c9e-106">[in]当前正在执行即将进行尾调用的函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="c2c9e-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="c2c9e-107">[in] 表示有关给定堆栈帧的信息的不透明的句柄。</span><span class="sxs-lookup"><span data-stu-id="c2c9e-107">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="c2c9e-108">此句柄无效，仅在传递到回调过程。</span><span class="sxs-lookup"><span data-stu-id="c2c9e-108">This handle is valid only during the callback to which it is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2c9e-109">备注</span><span class="sxs-lookup"><span data-stu-id="c2c9e-109">Remarks</span></span>  
 <span data-ttu-id="c2c9e-110">`FunctionTailcall3WithInfo`回调方法通知探查器，如函数调用，并允许探查器以使用[ICorProfilerInfo3::GetFunctionTailcall3Info 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md)检查堆栈帧。</span><span class="sxs-lookup"><span data-stu-id="c2c9e-110">The `FunctionTailcall3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionTailcall3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) to inspect the stack frame.</span></span> <span data-ttu-id="c2c9e-111">若要访问堆栈帧信息`COR_PRF_ENABLE_FRAME_INFO`标志必须设置。</span><span class="sxs-lookup"><span data-stu-id="c2c9e-111">To access stack frame information, the `COR_PRF_ENABLE_FRAME_INFO` flag has to be set.</span></span> <span data-ttu-id="c2c9e-112">可以使用探查器[icorprofilerinfo:: Seteventmask 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)设置的事件标志，然后使用[ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)注册应用此函数的实现。</span><span class="sxs-lookup"><span data-stu-id="c2c9e-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="c2c9e-113">`FunctionTailcall3WithInfo`函数是一个回调; 必须实现它。</span><span class="sxs-lookup"><span data-stu-id="c2c9e-113">The `FunctionTailcall3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="c2c9e-114">实现必须使用`__declspec(naked)`存储类特性。</span><span class="sxs-lookup"><span data-stu-id="c2c9e-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="c2c9e-115">调用此函数之前，执行引擎不会保存任何寄存器。</span><span class="sxs-lookup"><span data-stu-id="c2c9e-115">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="c2c9e-116">在进入时，必须保存使用，包括浮点单元 (FPU) 中的所有注册。</span><span class="sxs-lookup"><span data-stu-id="c2c9e-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="c2c9e-117">退出时，必须通过弹出已推送到由其调用方的所有参数由还原堆栈。</span><span class="sxs-lookup"><span data-stu-id="c2c9e-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="c2c9e-118">实现`FunctionTailcall3WithInfo`不应阻止，因为它会延迟垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="c2c9e-118">The implementation of `FunctionTailcall3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="c2c9e-119">实现不应尝试的垃圾回收，因为堆栈可能不是在垃圾收集友好状态中。</span><span class="sxs-lookup"><span data-stu-id="c2c9e-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="c2c9e-120">如果尝试在垃圾回收，则运行时将阻止直到`FunctionTailcall3WithInfo`返回。</span><span class="sxs-lookup"><span data-stu-id="c2c9e-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="c2c9e-121">此外，FunctionTailcall3WithInfo 函数不得调入托管代码或以任何方式导致托管的内存分配。</span><span class="sxs-lookup"><span data-stu-id="c2c9e-121">Also, the FunctionTailcall3WithInfo function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2c9e-122">要求</span><span class="sxs-lookup"><span data-stu-id="c2c9e-122">Requirements</span></span>  
 <span data-ttu-id="c2c9e-123">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c2c9e-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2c9e-124">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="c2c9e-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="c2c9e-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2c9e-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2c9e-126">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2c9e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2c9e-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="c2c9e-127">See also</span></span>
- [<span data-ttu-id="c2c9e-128">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="c2c9e-128">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="c2c9e-129">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="c2c9e-129">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="c2c9e-130">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="c2c9e-130">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="c2c9e-131">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="c2c9e-131">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="c2c9e-132">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="c2c9e-132">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="c2c9e-133">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="c2c9e-133">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="c2c9e-134">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="c2c9e-134">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="c2c9e-135">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="c2c9e-135">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="c2c9e-136">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="c2c9e-136">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="c2c9e-137">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="c2c9e-137">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
