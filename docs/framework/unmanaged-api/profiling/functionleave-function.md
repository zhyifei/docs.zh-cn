---
title: FunctionLeave 函数
ms.date: 03/30/2017
api_name:
- FunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave
helpviewer_keywords:
- FunctionLeave function [.NET Framework profiling]
ms.assetid: 18e89f45-e068-426a-be16-9f53a4346860
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b84b4b7ba96d39693abe238427983da086e62b1f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634839"
---
# <a name="functionleave-function"></a><span data-ttu-id="54d1d-102">FunctionLeave 函数</span><span class="sxs-lookup"><span data-stu-id="54d1d-102">FunctionLeave Function</span></span>
<span data-ttu-id="54d1d-103">通知探查器函数以返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="54d1d-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54d1d-104">`FunctionLeave`函数在.NET Framework 2.0 中已弃用。</span><span class="sxs-lookup"><span data-stu-id="54d1d-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="54d1d-105">它将继续工作，但将会产生对性能产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="54d1d-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="54d1d-106">使用[FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="54d1d-106">Use the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54d1d-107">语法</span><span class="sxs-lookup"><span data-stu-id="54d1d-107">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="54d1d-108">参数</span><span class="sxs-lookup"><span data-stu-id="54d1d-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="54d1d-109">[in]函数返回的标识符。</span><span class="sxs-lookup"><span data-stu-id="54d1d-109">[in] The identifier of the function that is returning.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54d1d-110">备注</span><span class="sxs-lookup"><span data-stu-id="54d1d-110">Remarks</span></span>  
 <span data-ttu-id="54d1d-111">`FunctionLeave`函数是一个回调; 必须实现它。</span><span class="sxs-lookup"><span data-stu-id="54d1d-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="54d1d-112">实现必须使用`__declspec`(`naked`) 存储类特性。</span><span class="sxs-lookup"><span data-stu-id="54d1d-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="54d1d-113">调用此函数之前，执行引擎不会保存任何寄存器。</span><span class="sxs-lookup"><span data-stu-id="54d1d-113">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="54d1d-114">在进入时，必须保存使用，包括浮点单元 (FPU) 中的所有注册。</span><span class="sxs-lookup"><span data-stu-id="54d1d-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="54d1d-115">退出时，必须通过弹出已推送到由其调用方的所有参数由还原堆栈。</span><span class="sxs-lookup"><span data-stu-id="54d1d-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="54d1d-116">实现`FunctionLeave`不应阻止，因为它会延迟垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="54d1d-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="54d1d-117">实现不应尝试垃圾回收，因为堆栈可能不是在垃圾收集友好状态中。</span><span class="sxs-lookup"><span data-stu-id="54d1d-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="54d1d-118">如果尝试在垃圾回收，则运行时将阻止直到`FunctionLeave`返回。</span><span class="sxs-lookup"><span data-stu-id="54d1d-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="54d1d-119">此外，`FunctionLeave`函数不能调用到托管代码中或以任何方式导致托管的内存分配。</span><span class="sxs-lookup"><span data-stu-id="54d1d-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54d1d-120">要求</span><span class="sxs-lookup"><span data-stu-id="54d1d-120">Requirements</span></span>  
 <span data-ttu-id="54d1d-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="54d1d-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54d1d-122">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="54d1d-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="54d1d-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54d1d-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54d1d-124">**.NET framework 版本：** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="54d1d-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54d1d-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="54d1d-125">See also</span></span>
- [<span data-ttu-id="54d1d-126">FunctionEnter2 函数</span><span class="sxs-lookup"><span data-stu-id="54d1d-126">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="54d1d-127">FunctionLeave2 函数</span><span class="sxs-lookup"><span data-stu-id="54d1d-127">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="54d1d-128">FunctionTailcall2 函数</span><span class="sxs-lookup"><span data-stu-id="54d1d-128">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="54d1d-129">SetEnterLeaveFunctionHooks2 方法</span><span class="sxs-lookup"><span data-stu-id="54d1d-129">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="54d1d-130">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="54d1d-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
