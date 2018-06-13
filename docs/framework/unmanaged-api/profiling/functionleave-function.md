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
ms.openlocfilehash: 2614ad988496a22f0e6234c2f3300e22ef548308
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452437"
---
# <a name="functionleave-function"></a><span data-ttu-id="910bc-102">FunctionLeave 函数</span><span class="sxs-lookup"><span data-stu-id="910bc-102">FunctionLeave Function</span></span>
<span data-ttu-id="910bc-103">通知探查器函数以返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="910bc-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="910bc-104">`FunctionLeave`函数已弃用在.NET Framework 2.0。</span><span class="sxs-lookup"><span data-stu-id="910bc-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="910bc-105">它将继续工作，但将会导致性能下降。</span><span class="sxs-lookup"><span data-stu-id="910bc-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="910bc-106">使用[FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="910bc-106">Use the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="910bc-107">语法</span><span class="sxs-lookup"><span data-stu-id="910bc-107">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="910bc-108">参数</span><span class="sxs-lookup"><span data-stu-id="910bc-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="910bc-109">[in]返回的函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="910bc-109">[in] The identifier of the function that is returning.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="910bc-110">备注</span><span class="sxs-lookup"><span data-stu-id="910bc-110">Remarks</span></span>  
 <span data-ttu-id="910bc-111">`FunctionLeave`函数为回调; 你必须实现它。</span><span class="sxs-lookup"><span data-stu-id="910bc-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="910bc-112">实现必须使用`__declspec`(`naked`) 存储类特性。</span><span class="sxs-lookup"><span data-stu-id="910bc-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="910bc-113">调用此函数之前，执行引擎不保存任何寄存器。</span><span class="sxs-lookup"><span data-stu-id="910bc-113">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="910bc-114">在进入时，必须保存所有使用，包括浮点单位 (FPU) 中的寄存器。</span><span class="sxs-lookup"><span data-stu-id="910bc-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="910bc-115">在退出时，你必须通过弹出已推送由其调用方的所有参数由还原堆栈。</span><span class="sxs-lookup"><span data-stu-id="910bc-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="910bc-116">实现`FunctionLeave`不应阻止，因为它会将延迟垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="910bc-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="910bc-117">实现不应尝试垃圾回收，因为堆栈可能不是在垃圾收集友好状态中。</span><span class="sxs-lookup"><span data-stu-id="910bc-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="910bc-118">如果尝试执行垃圾回收，则运行时将阻塞直到`FunctionLeave`返回。</span><span class="sxs-lookup"><span data-stu-id="910bc-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="910bc-119">此外，`FunctionLeave`函数不能调用进入托管代码或以任何方式导致托管的内存分配。</span><span class="sxs-lookup"><span data-stu-id="910bc-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="910bc-120">要求</span><span class="sxs-lookup"><span data-stu-id="910bc-120">Requirements</span></span>  
 <span data-ttu-id="910bc-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="910bc-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="910bc-122">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="910bc-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="910bc-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="910bc-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="910bc-124">**.NET framework 版本：** 1.1、 1.0</span><span class="sxs-lookup"><span data-stu-id="910bc-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="910bc-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="910bc-125">See Also</span></span>  
 [<span data-ttu-id="910bc-126">FunctionEnter2 函数</span><span class="sxs-lookup"><span data-stu-id="910bc-126">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="910bc-127">FunctionLeave2 函数</span><span class="sxs-lookup"><span data-stu-id="910bc-127">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="910bc-128">FunctionTailcall2 函数</span><span class="sxs-lookup"><span data-stu-id="910bc-128">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [<span data-ttu-id="910bc-129">SetEnterLeaveFunctionHooks2 方法</span><span class="sxs-lookup"><span data-stu-id="910bc-129">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="910bc-130">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="910bc-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
