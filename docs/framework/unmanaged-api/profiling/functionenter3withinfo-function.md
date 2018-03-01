---
title: "FunctionEnter3WithInfo 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- FunctionEnter3WithInfo
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- FunctionEnter3WithInfo
helpviewer_keywords:
- FunctionEnter3WithInfo function [.NET Framework profiling]
ms.assetid: 277c3344-d0cb-431e-beae-eb1eeeba8eea
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 848ef06f73aa0cce5d6991a7a59a8ce51ab1745a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="functionenter3withinfo-function"></a><span data-ttu-id="7f576-102">FunctionEnter3WithInfo 函数</span><span class="sxs-lookup"><span data-stu-id="7f576-102">FunctionEnter3WithInfo Function</span></span>
<span data-ttu-id="7f576-103">通知探查器正在将控件传递给函数，并提供一个句柄，可以传递给[icorprofilerinfo3:: Getfunctionenter3info 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md)检索堆栈帧和函数自变量。</span><span class="sxs-lookup"><span data-stu-id="7f576-103">Notifies the profiler that control is being passed to a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionEnter3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) to retrieve the stack frame and function arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f576-104">语法</span><span class="sxs-lookup"><span data-stu-id="7f576-104">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7f576-105">参数</span><span class="sxs-lookup"><span data-stu-id="7f576-105">Parameters</span></span>  
 `functionIDOrClientID`  
 <span data-ttu-id="7f576-106">[in]控件传递到函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="7f576-106">[in] The identifier of the function to which control is passed.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="7f576-107">[in] 表示有关给定堆栈帧的信息的不透明的句柄。</span><span class="sxs-lookup"><span data-stu-id="7f576-107">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="7f576-108">此句柄仅在传递到回调过程有效。</span><span class="sxs-lookup"><span data-stu-id="7f576-108">This handle is valid only during the callback to which it is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f576-109">备注</span><span class="sxs-lookup"><span data-stu-id="7f576-109">Remarks</span></span>  
 <span data-ttu-id="7f576-110">`FunctionEnter3WithInfo`回调方法通知探查器，如函数调用，并使探查器使用[icorprofilerinfo3:: Getfunctionenter3info 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md)检查自变量值。</span><span class="sxs-lookup"><span data-stu-id="7f576-110">The `FunctionEnter3WithInfo` callback method notifies the profiler as functions are called, and enables the profiler to use the [ICorProfilerInfo3::GetFunctionEnter3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) to inspect argument values.</span></span> <span data-ttu-id="7f576-111">若要访问参数信息，请`COR_PRF_ENABLE_FUNCTION_ARGS`标志必须设置。</span><span class="sxs-lookup"><span data-stu-id="7f576-111">To access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag has to be set.</span></span> <span data-ttu-id="7f576-112">探查器可以使用[icorprofilerinfo:: Seteventmask 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)设置事件标志，然后使用[icorprofilerinfo3:: Setenterleavefunctionhooks3withinfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)注册你此函数的实现。</span><span class="sxs-lookup"><span data-stu-id="7f576-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="7f576-113">`FunctionEnter3WithInfo`函数为回调; 你必须实现它。</span><span class="sxs-lookup"><span data-stu-id="7f576-113">The `FunctionEnter3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="7f576-114">实现必须使用`__declspec(naked)`存储类特性。</span><span class="sxs-lookup"><span data-stu-id="7f576-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="7f576-115">调用此函数之前，执行引擎不保存任何寄存器。</span><span class="sxs-lookup"><span data-stu-id="7f576-115">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="7f576-116">在进入时，必须保存所有使用，包括浮点单位 (FPU) 中的寄存器。</span><span class="sxs-lookup"><span data-stu-id="7f576-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="7f576-117">在退出时，你必须通过弹出已推送由其调用方的所有参数由还原堆栈。</span><span class="sxs-lookup"><span data-stu-id="7f576-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="7f576-118">实现`FunctionEnter3WithInfo`不应阻止，因为它会将延迟垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="7f576-118">The implementation of `FunctionEnter3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="7f576-119">实现不应尝试的垃圾回收，因为堆栈可能不是在垃圾收集友好状态中。</span><span class="sxs-lookup"><span data-stu-id="7f576-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="7f576-120">如果尝试执行垃圾回收，则运行时将阻塞直到`FunctionEnter3WithInfo`返回。</span><span class="sxs-lookup"><span data-stu-id="7f576-120">If a garbage collection is attempted, the runtime will block until `FunctionEnter3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="7f576-121">`FunctionEnter3WithInfo`函数不得调入托管代码或以任何方式导致托管的内存分配。</span><span class="sxs-lookup"><span data-stu-id="7f576-121">The `FunctionEnter3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f576-122">惠?</span><span class="sxs-lookup"><span data-stu-id="7f576-122">Requirements</span></span>  
 <span data-ttu-id="7f576-123">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7f576-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f576-124">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="7f576-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="7f576-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f576-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f576-126">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f576-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f576-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="7f576-127">See Also</span></span>  
 [<span data-ttu-id="7f576-128">GetFunctionEnter3Info</span><span class="sxs-lookup"><span data-stu-id="7f576-128">GetFunctionEnter3Info</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md)  
 [<span data-ttu-id="7f576-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="7f576-129">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 [<span data-ttu-id="7f576-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="7f576-130">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 [<span data-ttu-id="7f576-131">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="7f576-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
