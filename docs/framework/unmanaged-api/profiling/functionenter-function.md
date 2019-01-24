---
title: FunctionEnter 函数
ms.date: 03/30/2017
api_name:
- FunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter
helpviewer_keywords:
- FunctionEnter function [.NET Framework profiling]
ms.assetid: bf4ffa50-4506-4dd4-aa13-a0457b47ca74
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: be144ac8250adf803ddb1f20ea55be09cb3e81d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54687383"
---
# <a name="functionenter-function"></a><span data-ttu-id="ac019-102">FunctionEnter 函数</span><span class="sxs-lookup"><span data-stu-id="ac019-102">FunctionEnter Function</span></span>
<span data-ttu-id="ac019-103">通知探查器控件传递给函数。</span><span class="sxs-lookup"><span data-stu-id="ac019-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac019-104">`FunctionEnter`函数被弃用，在.NET Framework 2.0 版中，并且它的使用将会产生对性能产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="ac019-104">The `FunctionEnter` function is deprecated in the .NET Framework version 2.0, and its use will incur a performance penalty.</span></span> <span data-ttu-id="ac019-105">使用[FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="ac019-105">Use the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac019-106">语法</span><span class="sxs-lookup"><span data-stu-id="ac019-106">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac019-107">参数</span><span class="sxs-lookup"><span data-stu-id="ac019-107">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="ac019-108">[in]控件传递到函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="ac019-108">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac019-109">备注</span><span class="sxs-lookup"><span data-stu-id="ac019-109">Remarks</span></span>  
 <span data-ttu-id="ac019-110">`FunctionEnter`函数是一个回调; 必须实现它。</span><span class="sxs-lookup"><span data-stu-id="ac019-110">The `FunctionEnter` function is a callback; you must implement it.</span></span> <span data-ttu-id="ac019-111">实现必须使用`__declspec`(`naked`) 存储类特性。</span><span class="sxs-lookup"><span data-stu-id="ac019-111">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="ac019-112">调用此函数之前，执行引擎不会保存任何寄存器。</span><span class="sxs-lookup"><span data-stu-id="ac019-112">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="ac019-113">在进入时，必须保存使用，包括浮点单元 (FPU) 中的所有注册。</span><span class="sxs-lookup"><span data-stu-id="ac019-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="ac019-114">退出时，必须通过弹出已推送到由其调用方的所有参数由还原堆栈。</span><span class="sxs-lookup"><span data-stu-id="ac019-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="ac019-115">实现`FunctionEnter`不应阻止，因为它会延迟垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="ac019-115">The implementation of `FunctionEnter` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="ac019-116">实现不应尝试垃圾回收，因为堆栈可能不是在垃圾收集友好状态中。</span><span class="sxs-lookup"><span data-stu-id="ac019-116">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="ac019-117">如果尝试在垃圾回收，则运行时将阻止直到`FunctionEnter`返回。</span><span class="sxs-lookup"><span data-stu-id="ac019-117">If a garbage collection is attempted, the runtime will block until `FunctionEnter` returns.</span></span>  
  
 <span data-ttu-id="ac019-118">此外，`FunctionEnter`函数不能调用到托管代码中或以任何方式导致托管的内存分配。</span><span class="sxs-lookup"><span data-stu-id="ac019-118">Also, the `FunctionEnter` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac019-119">要求</span><span class="sxs-lookup"><span data-stu-id="ac019-119">Requirements</span></span>  
 <span data-ttu-id="ac019-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ac019-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac019-121">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="ac019-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="ac019-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac019-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac019-123">**.NET framework 版本：** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="ac019-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac019-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="ac019-124">See also</span></span>
- [<span data-ttu-id="ac019-125">FunctionEnter2 函数</span><span class="sxs-lookup"><span data-stu-id="ac019-125">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="ac019-126">FunctionLeave2 函数</span><span class="sxs-lookup"><span data-stu-id="ac019-126">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="ac019-127">FunctionTailcall2 函数</span><span class="sxs-lookup"><span data-stu-id="ac019-127">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="ac019-128">SetEnterLeaveFunctionHooks2 方法</span><span class="sxs-lookup"><span data-stu-id="ac019-128">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="ac019-129">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="ac019-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
