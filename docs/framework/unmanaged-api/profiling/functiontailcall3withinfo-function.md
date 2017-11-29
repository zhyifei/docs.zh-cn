---
title: "FunctionTailcall3WithInfo 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionTailcall3WithInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionTailcall3WithInfo
helpviewer_keywords: FunctionTailcall3WithInfo function [.NET Framework profiling]
ms.assetid: 46380fcc-0198-43ae-a1f5-2d4939425886
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c22f00678f707df04a69104fedef87aa6d5e3d7c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="functiontailcall3withinfo-function"></a><span data-ttu-id="0c021-102">FunctionTailcall3WithInfo 函数</span><span class="sxs-lookup"><span data-stu-id="0c021-102">FunctionTailcall3WithInfo Function</span></span>
<span data-ttu-id="0c021-103">通知探查器当前正在执行的函数即将执行尾调用给另一个函数，并提供一个句柄，可以传递给[icorprofilerinfo3:: Getfunctiontailcall3info 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md)检索堆栈帧。</span><span class="sxs-lookup"><span data-stu-id="0c021-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionTailcall3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) to retrieve the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c021-104">语法</span><span class="sxs-lookup"><span data-stu-id="0c021-104">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0c021-105">参数</span><span class="sxs-lookup"><span data-stu-id="0c021-105">Parameters</span></span>  
 `functionIDOrClientID`  
 <span data-ttu-id="0c021-106">[in]当前正在执行即将进行的尾调用的函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="0c021-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="0c021-107">[in] 表示有关给定堆栈帧的信息的不透明的句柄。</span><span class="sxs-lookup"><span data-stu-id="0c021-107">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="0c021-108">此句柄仅在传递到回调过程有效。</span><span class="sxs-lookup"><span data-stu-id="0c021-108">This handle is valid only during the callback to which it is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c021-109">备注</span><span class="sxs-lookup"><span data-stu-id="0c021-109">Remarks</span></span>  
 <span data-ttu-id="0c021-110">`FunctionTailcall3WithInfo`回调方法通知探查器，如函数调用，并允许探查器使用[icorprofilerinfo3:: Getfunctiontailcall3info 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md)检查堆栈帧。</span><span class="sxs-lookup"><span data-stu-id="0c021-110">The `FunctionTailcall3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionTailcall3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) to inspect the stack frame.</span></span> <span data-ttu-id="0c021-111">若要访问堆栈帧信息`COR_PRF_ENABLE_FRAME_INFO`标志必须设置。</span><span class="sxs-lookup"><span data-stu-id="0c021-111">To access stack frame information, the `COR_PRF_ENABLE_FRAME_INFO` flag has to be set.</span></span> <span data-ttu-id="0c021-112">探查器可以使用[icorprofilerinfo:: Seteventmask 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)设置事件标志，然后使用[icorprofilerinfo3:: Setenterleavefunctionhooks3withinfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)注册你此函数的实现。</span><span class="sxs-lookup"><span data-stu-id="0c021-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="0c021-113">`FunctionTailcall3WithInfo`函数为回调; 你必须实现它。</span><span class="sxs-lookup"><span data-stu-id="0c021-113">The `FunctionTailcall3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="0c021-114">实现必须使用`__declspec(naked)`存储类特性。</span><span class="sxs-lookup"><span data-stu-id="0c021-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="0c021-115">调用此函数之前，执行引擎不保存任何寄存器。</span><span class="sxs-lookup"><span data-stu-id="0c021-115">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="0c021-116">在进入时，必须保存所有使用，包括浮点单位 (FPU) 中的寄存器。</span><span class="sxs-lookup"><span data-stu-id="0c021-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="0c021-117">在退出时，你必须通过弹出已推送由其调用方的所有参数由还原堆栈。</span><span class="sxs-lookup"><span data-stu-id="0c021-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="0c021-118">实现`FunctionTailcall3WithInfo`不应阻止，因为它会将延迟垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="0c021-118">The implementation of `FunctionTailcall3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="0c021-119">实现不应尝试的垃圾回收，因为堆栈可能不是在垃圾收集友好状态中。</span><span class="sxs-lookup"><span data-stu-id="0c021-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="0c021-120">如果尝试执行垃圾回收，则运行时将阻塞直到`FunctionTailcall3WithInfo`返回。</span><span class="sxs-lookup"><span data-stu-id="0c021-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="0c021-121">此外，FunctionTailcall3WithInfo 函数不得调入托管代码或以任何方式导致托管的内存分配。</span><span class="sxs-lookup"><span data-stu-id="0c021-121">Also, the FunctionTailcall3WithInfo function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c021-122">要求</span><span class="sxs-lookup"><span data-stu-id="0c021-122">Requirements</span></span>  
 <span data-ttu-id="0c021-123">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0c021-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c021-124">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="0c021-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="0c021-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c021-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c021-126">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c021-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c021-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c021-127">See Also</span></span>  
 [<span data-ttu-id="0c021-128">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="0c021-128">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 [<span data-ttu-id="0c021-129">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="0c021-129">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 [<span data-ttu-id="0c021-130">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="0c021-130">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 [<span data-ttu-id="0c021-131">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="0c021-131">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 [<span data-ttu-id="0c021-132">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="0c021-132">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="0c021-133">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="0c021-133">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)  
 [<span data-ttu-id="0c021-134">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="0c021-134">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)  
 [<span data-ttu-id="0c021-135">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="0c021-135">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [<span data-ttu-id="0c021-136">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="0c021-136">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)  
 [<span data-ttu-id="0c021-137">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="0c021-137">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
