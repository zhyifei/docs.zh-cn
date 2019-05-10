---
title: FunctionTailcall 函数
ms.date: 03/30/2017
api_name:
- FunctionTailcall
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall
helpviewer_keywords:
- FunctionTailcall function [.NET Framework profiling]
ms.assetid: 66347e03-9a97-41e8-8f9d-89b80803f7b5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4686710c105ef002fe30f8b6e167d760088913ce
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586997"
---
# <a name="functiontailcall-function"></a><span data-ttu-id="d7f41-102">FunctionTailcall 函数</span><span class="sxs-lookup"><span data-stu-id="d7f41-102">FunctionTailcall Function</span></span>
<span data-ttu-id="d7f41-103">通知探查器当前正在执行的函数将要执行到另一个函数的结尾调用。</span><span class="sxs-lookup"><span data-stu-id="d7f41-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7f41-104">`FunctionTailcall`函数在.NET Framework 2.0 版中已弃用。</span><span class="sxs-lookup"><span data-stu-id="d7f41-104">The `FunctionTailcall` function is deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="d7f41-105">它将继续工作，但将会产生对性能产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="d7f41-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="d7f41-106">使用[FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="d7f41-106">Use the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7f41-107">语法</span><span class="sxs-lookup"><span data-stu-id="d7f41-107">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7f41-108">参数</span><span class="sxs-lookup"><span data-stu-id="d7f41-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="d7f41-109">[in]当前正在执行即将进行尾调用的函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="d7f41-109">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7f41-110">备注</span><span class="sxs-lookup"><span data-stu-id="d7f41-110">Remarks</span></span>  
 <span data-ttu-id="d7f41-111">尾调用的目标函数将使用当前堆栈帧，并将返回直接向进行尾调用的函数的调用方。</span><span class="sxs-lookup"><span data-stu-id="d7f41-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="d7f41-112">这意味着[FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md)回调不会发出有关目标的尾调用的函数。</span><span class="sxs-lookup"><span data-stu-id="d7f41-112">This means that a [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="d7f41-113">`FunctionTailcall`函数是一个回调; 必须实现它。</span><span class="sxs-lookup"><span data-stu-id="d7f41-113">The `FunctionTailcall` function is a callback; you must implement it.</span></span> <span data-ttu-id="d7f41-114">实现必须使用`__declspec`(`naked`) 存储类特性。</span><span class="sxs-lookup"><span data-stu-id="d7f41-114">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="d7f41-115">调用此函数之前，执行引擎不会保存任何寄存器。</span><span class="sxs-lookup"><span data-stu-id="d7f41-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="d7f41-116">在进入时，必须保存使用，包括浮点单元 (FPU) 中的所有注册。</span><span class="sxs-lookup"><span data-stu-id="d7f41-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="d7f41-117">退出时，必须通过弹出已推送到由其调用方的所有参数由还原堆栈。</span><span class="sxs-lookup"><span data-stu-id="d7f41-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="d7f41-118">实现`FunctionTailcall`不应阻止，因为它会延迟垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="d7f41-118">The implementation of `FunctionTailcall` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="d7f41-119">实现不应尝试垃圾回收，因为堆栈可能不是在垃圾收集友好状态中。</span><span class="sxs-lookup"><span data-stu-id="d7f41-119">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="d7f41-120">如果尝试在垃圾回收，则运行时将阻止直到`FunctionTailcall`返回。</span><span class="sxs-lookup"><span data-stu-id="d7f41-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall` returns.</span></span>  
  
 <span data-ttu-id="d7f41-121">此外，`FunctionTailcall`函数不能调用到托管代码中或以任何方式导致托管的内存分配。</span><span class="sxs-lookup"><span data-stu-id="d7f41-121">Also, the `FunctionTailcall` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7f41-122">要求</span><span class="sxs-lookup"><span data-stu-id="d7f41-122">Requirements</span></span>  
 <span data-ttu-id="d7f41-123">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d7f41-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7f41-124">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="d7f41-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="d7f41-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7f41-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7f41-126">**.NET framework 版本：** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="d7f41-126">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7f41-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7f41-127">See also</span></span>

- [<span data-ttu-id="d7f41-128">FunctionEnter2 函数</span><span class="sxs-lookup"><span data-stu-id="d7f41-128">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="d7f41-129">FunctionLeave2 函数</span><span class="sxs-lookup"><span data-stu-id="d7f41-129">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="d7f41-130">SetEnterLeaveFunctionHooks2 方法</span><span class="sxs-lookup"><span data-stu-id="d7f41-130">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="d7f41-131">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="d7f41-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
