---
title: "FunctionEnter 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionEnter
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionEnter
helpviewer_keywords: FunctionEnter function [.NET Framework profiling]
ms.assetid: bf4ffa50-4506-4dd4-aa13-a0457b47ca74
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0cd98e6db0f400d022fe0af4e96336616cbb7183
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="functionenter-function"></a><span data-ttu-id="6393f-102">FunctionEnter 函数</span><span class="sxs-lookup"><span data-stu-id="6393f-102">FunctionEnter Function</span></span>
<span data-ttu-id="6393f-103">通知探查器控件传递给函数。</span><span class="sxs-lookup"><span data-stu-id="6393f-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6393f-104">`FunctionEnter`函数已弃用在.NET Framework 2.0 版中，并将会导致性能下降，其用途。</span><span class="sxs-lookup"><span data-stu-id="6393f-104">The `FunctionEnter` function is deprecated in the .NET Framework version 2.0, and its use will incur a performance penalty.</span></span> <span data-ttu-id="6393f-105">使用[FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="6393f-105">Use the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6393f-106">语法</span><span class="sxs-lookup"><span data-stu-id="6393f-106">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6393f-107">参数</span><span class="sxs-lookup"><span data-stu-id="6393f-107">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="6393f-108">[in]控件传递到函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="6393f-108">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6393f-109">备注</span><span class="sxs-lookup"><span data-stu-id="6393f-109">Remarks</span></span>  
 <span data-ttu-id="6393f-110">`FunctionEnter`函数为回调; 你必须实现它。</span><span class="sxs-lookup"><span data-stu-id="6393f-110">The `FunctionEnter` function is a callback; you must implement it.</span></span> <span data-ttu-id="6393f-111">实现必须使用`__declspec`(`naked`) 存储类特性。</span><span class="sxs-lookup"><span data-stu-id="6393f-111">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="6393f-112">调用此函数之前，执行引擎不保存任何寄存器。</span><span class="sxs-lookup"><span data-stu-id="6393f-112">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="6393f-113">在进入时，必须保存所有使用，包括浮点单位 (FPU) 中的寄存器。</span><span class="sxs-lookup"><span data-stu-id="6393f-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="6393f-114">在退出时，你必须通过弹出已推送由其调用方的所有参数由还原堆栈。</span><span class="sxs-lookup"><span data-stu-id="6393f-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="6393f-115">实现`FunctionEnter`不应阻止，因为它会将延迟垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="6393f-115">The implementation of `FunctionEnter` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="6393f-116">实现不应尝试垃圾回收，因为堆栈可能不是在垃圾收集友好状态中。</span><span class="sxs-lookup"><span data-stu-id="6393f-116">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="6393f-117">如果尝试执行垃圾回收，则运行时将阻塞直到`FunctionEnter`返回。</span><span class="sxs-lookup"><span data-stu-id="6393f-117">If a garbage collection is attempted, the runtime will block until `FunctionEnter` returns.</span></span>  
  
 <span data-ttu-id="6393f-118">此外，`FunctionEnter`函数不能调用进入托管代码或以任何方式导致托管的内存分配。</span><span class="sxs-lookup"><span data-stu-id="6393f-118">Also, the `FunctionEnter` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6393f-119">要求</span><span class="sxs-lookup"><span data-stu-id="6393f-119">Requirements</span></span>  
 <span data-ttu-id="6393f-120">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6393f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6393f-121">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="6393f-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="6393f-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6393f-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6393f-123">**.NET framework 版本：** 1.1、 1.0</span><span class="sxs-lookup"><span data-stu-id="6393f-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6393f-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6393f-124">See Also</span></span>  
 [<span data-ttu-id="6393f-125">FunctionEnter2 函数</span><span class="sxs-lookup"><span data-stu-id="6393f-125">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="6393f-126">FunctionLeave2 函数</span><span class="sxs-lookup"><span data-stu-id="6393f-126">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="6393f-127">FunctionTailcall2 函数</span><span class="sxs-lookup"><span data-stu-id="6393f-127">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [<span data-ttu-id="6393f-128">SetEnterLeaveFunctionHooks2 方法</span><span class="sxs-lookup"><span data-stu-id="6393f-128">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="6393f-129">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="6393f-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
