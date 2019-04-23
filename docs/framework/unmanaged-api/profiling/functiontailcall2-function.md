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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 06dd3b028f4f43ca8681c80a5caa4716104068dd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080886"
---
# <a name="functiontailcall2-function"></a><span data-ttu-id="d7025-102">FunctionTailcall2 函数</span><span class="sxs-lookup"><span data-stu-id="d7025-102">FunctionTailcall2 Function</span></span>
<span data-ttu-id="d7025-103">通知探查器当前正在执行的函数将要执行到另一个函数的结尾调用并提供有关堆栈帧的信息。</span><span class="sxs-lookup"><span data-stu-id="d7025-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7025-104">语法</span><span class="sxs-lookup"><span data-stu-id="d7025-104">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,   
    [in] UINT_PTR           clientData,   
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7025-105">参数</span><span class="sxs-lookup"><span data-stu-id="d7025-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="d7025-106">[in]当前正在执行即将进行尾调用的函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="d7025-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
 `clientData`  
 <span data-ttu-id="d7025-107">[in]通过探查器之前指定的重新映射的函数标识符[FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)，当前正在执行即将进行尾调用的函数。</span><span class="sxs-lookup"><span data-stu-id="d7025-107">[in] The remapped function identifier, which the profiler previously specified via [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md), of the currently executing function that is about to make a tail call.</span></span>  
  
 `func`  
 <span data-ttu-id="d7025-108">[in]一个`COR_PRF_FRAME_INFO`值，该值指向有关堆栈帧的信息。</span><span class="sxs-lookup"><span data-stu-id="d7025-108">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="d7025-109">探查器应将此视为可以传递回执行引擎的不透明句柄[ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d7025-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7025-110">备注</span><span class="sxs-lookup"><span data-stu-id="d7025-110">Remarks</span></span>  
 <span data-ttu-id="d7025-111">尾调用的目标函数将使用当前堆栈帧，并将返回直接向进行尾调用的函数的调用方。</span><span class="sxs-lookup"><span data-stu-id="d7025-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="d7025-112">这意味着[FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)回调不会发出有关目标的尾调用的函数。</span><span class="sxs-lookup"><span data-stu-id="d7025-112">This means that a [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="d7025-113">值`func`参数不是有效后`FunctionTailcall2`函数返回，因为值可能会更改或已损坏。</span><span class="sxs-lookup"><span data-stu-id="d7025-113">The value of the `func` parameter is not valid after the `FunctionTailcall2` function returns because the value may change or be destroyed.</span></span>  
  
 <span data-ttu-id="d7025-114">`FunctionTailcall2`函数是一个回调; 必须实现它。</span><span class="sxs-lookup"><span data-stu-id="d7025-114">The `FunctionTailcall2` function is a callback; you must implement it.</span></span> <span data-ttu-id="d7025-115">实现必须使用`__declspec`(`naked`) 存储类特性。</span><span class="sxs-lookup"><span data-stu-id="d7025-115">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="d7025-116">调用此函数之前，执行引擎不会保存任何寄存器。</span><span class="sxs-lookup"><span data-stu-id="d7025-116">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="d7025-117">在进入时，必须保存使用，包括浮点单元 (FPU) 中的所有注册。</span><span class="sxs-lookup"><span data-stu-id="d7025-117">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="d7025-118">退出时，必须通过弹出已推送到由其调用方的所有参数由还原堆栈。</span><span class="sxs-lookup"><span data-stu-id="d7025-118">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="d7025-119">实现`FunctionTailcall2`不应阻止，因为它会延迟垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="d7025-119">The implementation of `FunctionTailcall2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="d7025-120">实现不应尝试垃圾回收，因为堆栈可能不是在垃圾收集友好状态中。</span><span class="sxs-lookup"><span data-stu-id="d7025-120">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="d7025-121">如果尝试在垃圾回收，则运行时将阻止直到`FunctionTailcall2`返回。</span><span class="sxs-lookup"><span data-stu-id="d7025-121">If a garbage collection is attempted, the runtime will block until `FunctionTailcall2` returns.</span></span>  
  
 <span data-ttu-id="d7025-122">此外，`FunctionTailcall2`函数不能调用到托管代码中或以任何方式导致托管的内存分配。</span><span class="sxs-lookup"><span data-stu-id="d7025-122">Also, the `FunctionTailcall2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7025-123">要求</span><span class="sxs-lookup"><span data-stu-id="d7025-123">Requirements</span></span>  
 <span data-ttu-id="d7025-124">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d7025-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7025-125">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="d7025-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="d7025-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7025-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7025-127">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7025-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7025-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7025-128">See also</span></span>

- [<span data-ttu-id="d7025-129">FunctionEnter2 函数</span><span class="sxs-lookup"><span data-stu-id="d7025-129">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="d7025-130">FunctionLeave2 函数</span><span class="sxs-lookup"><span data-stu-id="d7025-130">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="d7025-131">SetEnterLeaveFunctionHooks2 方法</span><span class="sxs-lookup"><span data-stu-id="d7025-131">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="d7025-132">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="d7025-132">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
