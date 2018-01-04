---
title: "FunctionTailcall2 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionTailcall2
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionTailcall2
helpviewer_keywords: FunctionTailcall2 function [.NET Framework profiling]
ms.assetid: 249f9892-b5a9-41e1-b329-28a925904df6
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a9d6ccb08bc09bea2ec9e9a49333c92da8cb5695
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="functiontailcall2-function"></a><span data-ttu-id="ad1e0-102">FunctionTailcall2 函数</span><span class="sxs-lookup"><span data-stu-id="ad1e0-102">FunctionTailcall2 Function</span></span>
<span data-ttu-id="ad1e0-103">当前正在执行的函数，即将执行尾调用给另一个函数，并提供有关堆栈帧的信息，请通知探查器。</span><span class="sxs-lookup"><span data-stu-id="ad1e0-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad1e0-104">语法</span><span class="sxs-lookup"><span data-stu-id="ad1e0-104">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,   
    [in] UINT_PTR           clientData,   
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ad1e0-105">参数</span><span class="sxs-lookup"><span data-stu-id="ad1e0-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="ad1e0-106">[in]当前正在执行即将进行的尾调用的函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="ad1e0-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
 `clientData`  
 <span data-ttu-id="ad1e0-107">[in]重新映射的函数标识符，它通过以前指定探查器[FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)，即将进行的尾调用的当前正在执行函数。</span><span class="sxs-lookup"><span data-stu-id="ad1e0-107">[in] The remapped function identifier, which the profiler previously specified via [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md), of the currently executing function that is about to make a tail call.</span></span>  
  
 `func`  
 <span data-ttu-id="ad1e0-108">[in]A`COR_PRF_FRAME_INFO`值，该值指向有关堆栈帧的信息。</span><span class="sxs-lookup"><span data-stu-id="ad1e0-108">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="ad1e0-109">探查器应将此视为不透明的句柄可以传递回执行引擎[icorprofilerinfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ad1e0-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad1e0-110">备注</span><span class="sxs-lookup"><span data-stu-id="ad1e0-110">Remarks</span></span>  
 <span data-ttu-id="ad1e0-111">尾调用的目标函数将使用当前的堆栈帧，并且将直接向进行尾调用的函数的调用方返回。</span><span class="sxs-lookup"><span data-stu-id="ad1e0-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="ad1e0-112">这意味着， [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)回调将不会颁发目标的尾调用的函数。</span><span class="sxs-lookup"><span data-stu-id="ad1e0-112">This means that a [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="ad1e0-113">值`func`参数不是有效之后`FunctionTailcall2`函数返回，因为值可能会更改或将其销毁。</span><span class="sxs-lookup"><span data-stu-id="ad1e0-113">The value of the `func` parameter is not valid after the `FunctionTailcall2` function returns because the value may change or be destroyed.</span></span>  
  
 <span data-ttu-id="ad1e0-114">`FunctionTailcall2`函数为回调; 你必须实现它。</span><span class="sxs-lookup"><span data-stu-id="ad1e0-114">The `FunctionTailcall2` function is a callback; you must implement it.</span></span> <span data-ttu-id="ad1e0-115">实现必须使用`__declspec`(`naked`) 存储类特性。</span><span class="sxs-lookup"><span data-stu-id="ad1e0-115">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="ad1e0-116">调用此函数之前，执行引擎不保存任何寄存器。</span><span class="sxs-lookup"><span data-stu-id="ad1e0-116">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="ad1e0-117">在进入时，必须保存所有使用，包括浮点单位 (FPU) 中的寄存器。</span><span class="sxs-lookup"><span data-stu-id="ad1e0-117">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="ad1e0-118">在退出时，你必须通过弹出已推送由其调用方的所有参数由还原堆栈。</span><span class="sxs-lookup"><span data-stu-id="ad1e0-118">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="ad1e0-119">实现`FunctionTailcall2`不应阻止，因为它会将延迟垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="ad1e0-119">The implementation of `FunctionTailcall2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="ad1e0-120">实现不应尝试垃圾回收，因为堆栈可能不是在垃圾收集友好状态中。</span><span class="sxs-lookup"><span data-stu-id="ad1e0-120">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="ad1e0-121">如果尝试执行垃圾回收，则运行时将阻塞直到`FunctionTailcall2`返回。</span><span class="sxs-lookup"><span data-stu-id="ad1e0-121">If a garbage collection is attempted, the runtime will block until `FunctionTailcall2` returns.</span></span>  
  
 <span data-ttu-id="ad1e0-122">此外，`FunctionTailcall2`函数不能调用进入托管代码或以任何方式导致托管的内存分配。</span><span class="sxs-lookup"><span data-stu-id="ad1e0-122">Also, the `FunctionTailcall2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad1e0-123">惠?</span><span class="sxs-lookup"><span data-stu-id="ad1e0-123">Requirements</span></span>  
 <span data-ttu-id="ad1e0-124">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ad1e0-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad1e0-125">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="ad1e0-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="ad1e0-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad1e0-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad1e0-127">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad1e0-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad1e0-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad1e0-128">See Also</span></span>  
 [<span data-ttu-id="ad1e0-129">FunctionEnter2 函数</span><span class="sxs-lookup"><span data-stu-id="ad1e0-129">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="ad1e0-130">FunctionLeave2 函数</span><span class="sxs-lookup"><span data-stu-id="ad1e0-130">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="ad1e0-131">SetEnterLeaveFunctionHooks2 方法</span><span class="sxs-lookup"><span data-stu-id="ad1e0-131">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="ad1e0-132">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="ad1e0-132">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
