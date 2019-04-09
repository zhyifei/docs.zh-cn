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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b31c3045b021bd3b00d2b2e42bf7a118110305b1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099880"
---
# <a name="functionleave3-function"></a><span data-ttu-id="592f5-102">FunctionLeave3 函数</span><span class="sxs-lookup"><span data-stu-id="592f5-102">FunctionLeave3 Function</span></span>
<span data-ttu-id="592f5-103">通知探查器从函数返回控制。</span><span class="sxs-lookup"><span data-stu-id="592f5-103">Notifies the profiler that control is being returned from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="592f5-104">语法</span><span class="sxs-lookup"><span data-stu-id="592f5-104">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="592f5-105">参数</span><span class="sxs-lookup"><span data-stu-id="592f5-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="592f5-106">[in]函数从其返回控件的标识符。</span><span class="sxs-lookup"><span data-stu-id="592f5-106">[in] The identifier of the function from which control is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="592f5-107">备注</span><span class="sxs-lookup"><span data-stu-id="592f5-107">Remarks</span></span>  
 <span data-ttu-id="592f5-108">`FunctionLeave3`回调函数通知探查器，如函数正被调用，但不支持返回值检查。</span><span class="sxs-lookup"><span data-stu-id="592f5-108">The `FunctionLeave3` callback function notifies the profiler as functions are being called, but does not support return value inspection.</span></span> <span data-ttu-id="592f5-109">使用[ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)注册此函数的实现。</span><span class="sxs-lookup"><span data-stu-id="592f5-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="592f5-110">`FunctionLeave3`函数是一个回调; 必须实现它。</span><span class="sxs-lookup"><span data-stu-id="592f5-110">The `FunctionLeave3` function is a callback; you must implement it.</span></span> <span data-ttu-id="592f5-111">实现必须使用`__declspec(naked)`存储类特性。</span><span class="sxs-lookup"><span data-stu-id="592f5-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="592f5-112">调用此函数之前，执行引擎不会保存任何寄存器。</span><span class="sxs-lookup"><span data-stu-id="592f5-112">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="592f5-113">在进入时，必须保存使用，包括浮点单元 (FPU) 中的所有注册。</span><span class="sxs-lookup"><span data-stu-id="592f5-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="592f5-114">退出时，必须通过弹出已推送到由其调用方的所有参数由还原堆栈。</span><span class="sxs-lookup"><span data-stu-id="592f5-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="592f5-115">实现`FunctionLeave3`不应阻止，因为它会延迟垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="592f5-115">The implementation of `FunctionLeave3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="592f5-116">实现不应尝试的垃圾回收，因为堆栈可能不是在垃圾收集友好状态中。</span><span class="sxs-lookup"><span data-stu-id="592f5-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="592f5-117">如果尝试在垃圾回收，则运行时将阻止直到`FunctionLeave3`返回。</span><span class="sxs-lookup"><span data-stu-id="592f5-117">If a garbage collection is attempted, the runtime will block until `FunctionLeave3` returns.</span></span>  
  
 <span data-ttu-id="592f5-118">`FunctionLeave3`函数不得调入托管代码或以任何方式导致托管的内存分配。</span><span class="sxs-lookup"><span data-stu-id="592f5-118">The `FunctionLeave3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="592f5-119">要求</span><span class="sxs-lookup"><span data-stu-id="592f5-119">Requirements</span></span>  
 <span data-ttu-id="592f5-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="592f5-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="592f5-121">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="592f5-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="592f5-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="592f5-122">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="592f5-123">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="592f5-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="592f5-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="592f5-124">See also</span></span>

- [<span data-ttu-id="592f5-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="592f5-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="592f5-126">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="592f5-126">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="592f5-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="592f5-127">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="592f5-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="592f5-128">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="592f5-129">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="592f5-129">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="592f5-130">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="592f5-130">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="592f5-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="592f5-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="592f5-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="592f5-132">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="592f5-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="592f5-133">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="592f5-134">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="592f5-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
