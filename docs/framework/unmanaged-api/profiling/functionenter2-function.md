---
title: FunctionEnter2 函数
ms.date: 03/30/2017
api_name:
- FunctionEnter2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter2
helpviewer_keywords:
- FunctionEnter2 function [.NET Framework profiling]
ms.assetid: ce7a21f9-0ca3-4b92-bc4b-bb803cae3f51
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f01117d52ba49012120546db5095ccad8baa6e73
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54531618"
---
# <a name="functionenter2-function"></a><span data-ttu-id="2ba47-102">FunctionEnter2 函数</span><span class="sxs-lookup"><span data-stu-id="2ba47-102">FunctionEnter2 Function</span></span>
<span data-ttu-id="2ba47-103">通知探查器，控制被传递给函数，并介绍有关堆栈帧和函数参数。</span><span class="sxs-lookup"><span data-stu-id="2ba47-103">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="2ba47-104">此函数取代[FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="2ba47-104">This function supersedes the [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ba47-105">语法</span><span class="sxs-lookup"><span data-stu-id="2ba47-105">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,   
    [in]  UINT_PTR                         clientData,   
    [in]  COR_PRF_FRAME_INFO               func,   
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2ba47-106">参数</span><span class="sxs-lookup"><span data-stu-id="2ba47-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="2ba47-107">[in]控件传递到函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="2ba47-107">[in] The identifier of the function to which control is passed.</span></span>  
  
 `clientData`  
 <span data-ttu-id="2ba47-108">[in]通过使用以前指定探查器的重新映射的函数标识符[FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="2ba47-108">[in] The remapped function identifier, which the profiler previously specified by using the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function.</span></span>  
  
 `func`  
 <span data-ttu-id="2ba47-109">[in]一个`COR_PRF_FRAME_INFO`值，该值指向有关堆栈帧的信息。</span><span class="sxs-lookup"><span data-stu-id="2ba47-109">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="2ba47-110">探查器应将此视为可以传递回执行引擎的不透明句柄[ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="2ba47-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
 `argumentInfo`  
 <span data-ttu-id="2ba47-111">[in]一个指向[COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md)结构，它在内存中的函数的参数指定的位置。</span><span class="sxs-lookup"><span data-stu-id="2ba47-111">[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure that specifies the locations in memory of the function's arguments.</span></span>  
  
 <span data-ttu-id="2ba47-112">若要访问参数的信息，`COR_PRF_ENABLE_FUNCTION_ARGS`标志必须设置。</span><span class="sxs-lookup"><span data-stu-id="2ba47-112">In order to access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag must be set.</span></span> <span data-ttu-id="2ba47-113">可以使用探查器[icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)方法设置的事件标志。</span><span class="sxs-lookup"><span data-stu-id="2ba47-113">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ba47-114">备注</span><span class="sxs-lookup"><span data-stu-id="2ba47-114">Remarks</span></span>  
 <span data-ttu-id="2ba47-115">值`func`并`argumentInfo`参数都不是有效后`FunctionEnter2`函数返回，因为这些值可能会更改或已损坏。</span><span class="sxs-lookup"><span data-stu-id="2ba47-115">The values of the `func` and `argumentInfo` parameters are not valid after the `FunctionEnter2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="2ba47-116">`FunctionEnter2`函数是一个回调; 必须实现它。</span><span class="sxs-lookup"><span data-stu-id="2ba47-116">The `FunctionEnter2` function is a callback; you must implement it.</span></span> <span data-ttu-id="2ba47-117">实现必须使用`__declspec`(`naked`) 存储类特性。</span><span class="sxs-lookup"><span data-stu-id="2ba47-117">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="2ba47-118">调用此函数之前，执行引擎不会保存任何寄存器。</span><span class="sxs-lookup"><span data-stu-id="2ba47-118">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="2ba47-119">在进入时，必须保存使用，包括浮点单元 (FPU) 中的所有注册。</span><span class="sxs-lookup"><span data-stu-id="2ba47-119">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="2ba47-120">退出时，必须通过弹出已推送到由其调用方的所有参数由还原堆栈。</span><span class="sxs-lookup"><span data-stu-id="2ba47-120">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="2ba47-121">实现`FunctionEnter2`不应阻止，因为它会延迟垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="2ba47-121">The implementation of `FunctionEnter2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="2ba47-122">实现不应尝试垃圾回收，因为堆栈可能不是在垃圾收集友好状态中。</span><span class="sxs-lookup"><span data-stu-id="2ba47-122">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="2ba47-123">如果尝试在垃圾回收，则运行时将阻止直到`FunctionEnter2`返回。</span><span class="sxs-lookup"><span data-stu-id="2ba47-123">If a garbage collection is attempted, the runtime will block until `FunctionEnter2` returns.</span></span>  
  
 <span data-ttu-id="2ba47-124">此外，`FunctionEnter2`函数不能调用到托管代码中或以任何方式导致托管的内存分配。</span><span class="sxs-lookup"><span data-stu-id="2ba47-124">Also, the `FunctionEnter2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ba47-125">要求</span><span class="sxs-lookup"><span data-stu-id="2ba47-125">Requirements</span></span>  
 <span data-ttu-id="2ba47-126">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2ba47-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ba47-127">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="2ba47-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="2ba47-128">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ba47-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ba47-129">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ba47-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ba47-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="2ba47-130">See also</span></span>
- [<span data-ttu-id="2ba47-131">FunctionLeave2 函数</span><span class="sxs-lookup"><span data-stu-id="2ba47-131">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="2ba47-132">FunctionTailcall2 函数</span><span class="sxs-lookup"><span data-stu-id="2ba47-132">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="2ba47-133">SetEnterLeaveFunctionHooks2 方法</span><span class="sxs-lookup"><span data-stu-id="2ba47-133">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="2ba47-134">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="2ba47-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
