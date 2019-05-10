---
title: FunctionLeave2 函数
ms.date: 03/30/2017
api_name:
- FunctionLeave2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave2
helpviewer_keywords:
- FunctionLeave2 function [.NET Framework profiling]
ms.assetid: 8cdac941-8b94-4497-b874-4e571785f3fe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8bde206d56bc7e8c930e1e428512232caccfb940
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586826"
---
# <a name="functionleave2-function"></a><span data-ttu-id="5bbaa-102">FunctionLeave2 函数</span><span class="sxs-lookup"><span data-stu-id="5bbaa-102">FunctionLeave2 Function</span></span>
<span data-ttu-id="5bbaa-103">函数即将返回给调用方，并提供有关堆栈帧和函数返回值的信息，请通知探查器。</span><span class="sxs-lookup"><span data-stu-id="5bbaa-103">Notifies the profiler that a function is about to return to the caller and provides information about the stack frame and function return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bbaa-104">语法</span><span class="sxs-lookup"><span data-stu-id="5bbaa-104">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave2 (  
    [in]  FunctionID                        funcId,  
    [in]  UINT_PTR                          clientData,  
    [in]  COR_PRF_FRAME_INFO                func,  
    [in]  COR_PRF_FUNCTION_ARGUMENT_RANGE  *retvalRange  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bbaa-105">参数</span><span class="sxs-lookup"><span data-stu-id="5bbaa-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="5bbaa-106">[in]函数返回的标识符。</span><span class="sxs-lookup"><span data-stu-id="5bbaa-106">[in] The identifier of the function that is returning.</span></span>  
  
 `clientData`  
 <span data-ttu-id="5bbaa-107">[in]通过探查器之前指定的重新映射的函数标识符[FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="5bbaa-107">[in] The remapped function identifier, which the profiler previously specified via the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function.</span></span>  
  
 `func`  
 <span data-ttu-id="5bbaa-108">[in]一个`COR_PRF_FRAME_INFO`值，该值指向有关堆栈帧的信息。</span><span class="sxs-lookup"><span data-stu-id="5bbaa-108">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="5bbaa-109">探查器应将此视为可以传递回执行引擎的不透明句柄[ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5bbaa-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
 `retvalRange`  
 <span data-ttu-id="5bbaa-110">[in]一个指向[COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md)结构，它指定函数的返回值的内存位置。</span><span class="sxs-lookup"><span data-stu-id="5bbaa-110">[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structure that specifies the memory location of the function's return value.</span></span>  
  
 <span data-ttu-id="5bbaa-111">若要访问返回值信息`COR_PRF_ENABLE_FUNCTION_RETVAL`标志必须设置。</span><span class="sxs-lookup"><span data-stu-id="5bbaa-111">In order to access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="5bbaa-112">可以使用探查器[icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)方法设置的事件标志。</span><span class="sxs-lookup"><span data-stu-id="5bbaa-112">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bbaa-113">备注</span><span class="sxs-lookup"><span data-stu-id="5bbaa-113">Remarks</span></span>  
 <span data-ttu-id="5bbaa-114">值`func`并`retvalRange`参数都不是有效后`FunctionLeave2`函数返回，因为这些值可能会更改或已损坏。</span><span class="sxs-lookup"><span data-stu-id="5bbaa-114">The values of the `func` and `retvalRange` parameters are not valid after the `FunctionLeave2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="5bbaa-115">`FunctionLeave2`函数是一个回调; 必须实现它。</span><span class="sxs-lookup"><span data-stu-id="5bbaa-115">The `FunctionLeave2` function is a callback; you must implement it.</span></span> <span data-ttu-id="5bbaa-116">实现必须使用`__declspec`(`naked`) 存储类特性。</span><span class="sxs-lookup"><span data-stu-id="5bbaa-116">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="5bbaa-117">调用此函数之前，执行引擎不会保存任何寄存器。</span><span class="sxs-lookup"><span data-stu-id="5bbaa-117">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="5bbaa-118">在进入时，必须保存使用，包括浮点单元 (FPU) 中的所有注册。</span><span class="sxs-lookup"><span data-stu-id="5bbaa-118">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="5bbaa-119">退出时，必须通过弹出已推送到由其调用方的所有参数由还原堆栈。</span><span class="sxs-lookup"><span data-stu-id="5bbaa-119">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="5bbaa-120">实现`FunctionLeave2`不应阻止，因为它会延迟垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="5bbaa-120">The implementation of `FunctionLeave2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="5bbaa-121">实现不应尝试垃圾回收，因为堆栈可能不是在垃圾收集友好状态中。</span><span class="sxs-lookup"><span data-stu-id="5bbaa-121">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="5bbaa-122">如果尝试在垃圾回收，则运行时将阻止直到`FunctionLeave2`返回。</span><span class="sxs-lookup"><span data-stu-id="5bbaa-122">If a garbage collection is attempted, the runtime will block until `FunctionLeave2` returns.</span></span>  
  
 <span data-ttu-id="5bbaa-123">此外，`FunctionLeave2`函数不能调用到托管代码中或以任何方式导致托管的内存分配。</span><span class="sxs-lookup"><span data-stu-id="5bbaa-123">Also, the `FunctionLeave2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bbaa-124">要求</span><span class="sxs-lookup"><span data-stu-id="5bbaa-124">Requirements</span></span>  
 <span data-ttu-id="5bbaa-125">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5bbaa-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bbaa-126">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="5bbaa-126">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="5bbaa-127">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5bbaa-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5bbaa-128">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bbaa-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bbaa-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="5bbaa-129">See also</span></span>

- [<span data-ttu-id="5bbaa-130">FunctionEnter2 函数</span><span class="sxs-lookup"><span data-stu-id="5bbaa-130">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="5bbaa-131">FunctionTailcall2 函数</span><span class="sxs-lookup"><span data-stu-id="5bbaa-131">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="5bbaa-132">SetEnterLeaveFunctionHooks2 方法</span><span class="sxs-lookup"><span data-stu-id="5bbaa-132">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="5bbaa-133">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="5bbaa-133">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
