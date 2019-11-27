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
ms.openlocfilehash: ad34592223433f0bf541c390674bcf96839b6ca8
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440813"
---
# <a name="functionenter-function"></a><span data-ttu-id="b06df-102">FunctionEnter 函数</span><span class="sxs-lookup"><span data-stu-id="b06df-102">FunctionEnter Function</span></span>
<span data-ttu-id="b06df-103">通知探查器控制正在传递到函数。</span><span class="sxs-lookup"><span data-stu-id="b06df-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b06df-104">`FunctionEnter` 函数在 .NET Framework 版本2.0 中已弃用，其使用将导致性能下降。</span><span class="sxs-lookup"><span data-stu-id="b06df-104">The `FunctionEnter` function is deprecated in the .NET Framework version 2.0, and its use will incur a performance penalty.</span></span> <span data-ttu-id="b06df-105">改为使用[FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="b06df-105">Use the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b06df-106">语法</span><span class="sxs-lookup"><span data-stu-id="b06df-106">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b06df-107">参数</span><span class="sxs-lookup"><span data-stu-id="b06df-107">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="b06df-108">中要传递控制的函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="b06df-108">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b06df-109">备注</span><span class="sxs-lookup"><span data-stu-id="b06df-109">Remarks</span></span>  
 <span data-ttu-id="b06df-110">`FunctionEnter` 函数是回调;必须实现此方法。</span><span class="sxs-lookup"><span data-stu-id="b06df-110">The `FunctionEnter` function is a callback; you must implement it.</span></span> <span data-ttu-id="b06df-111">实现必须使用 `__declspec`（`naked`）存储类特性。</span><span class="sxs-lookup"><span data-stu-id="b06df-111">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="b06df-112">在调用此函数之前，执行引擎不会保存任何注册。</span><span class="sxs-lookup"><span data-stu-id="b06df-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="b06df-113">进入时，必须保存使用的所有寄存器，包括浮点单元（FPU）中的所有寄存器。</span><span class="sxs-lookup"><span data-stu-id="b06df-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="b06df-114">退出时，必须通过弹出由其调用方推送的所有参数来还原堆栈。</span><span class="sxs-lookup"><span data-stu-id="b06df-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="b06df-115">`FunctionEnter` 的实现不应被阻止，因为它将延迟垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="b06df-115">The implementation of `FunctionEnter` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="b06df-116">实现不应尝试垃圾回收，因为堆栈可能不处于垃圾回收友好状态。</span><span class="sxs-lookup"><span data-stu-id="b06df-116">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="b06df-117">如果尝试垃圾回收，则运行时将被阻止，直到 `FunctionEnter` 返回。</span><span class="sxs-lookup"><span data-stu-id="b06df-117">If a garbage collection is attempted, the runtime will block until `FunctionEnter` returns.</span></span>  
  
 <span data-ttu-id="b06df-118">此外，`FunctionEnter` 函数不得调入托管代码或以任何方式导致托管的内存分配。</span><span class="sxs-lookup"><span data-stu-id="b06df-118">Also, the `FunctionEnter` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b06df-119">要求</span><span class="sxs-lookup"><span data-stu-id="b06df-119">Requirements</span></span>  
 <span data-ttu-id="b06df-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b06df-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b06df-121">**标头：** Corprof.idl .idl</span><span class="sxs-lookup"><span data-stu-id="b06df-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="b06df-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b06df-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b06df-123">**.NET Framework 版本：** 1.1、1。0</span><span class="sxs-lookup"><span data-stu-id="b06df-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b06df-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b06df-124">See also</span></span>

- [<span data-ttu-id="b06df-125">FunctionEnter2 函数</span><span class="sxs-lookup"><span data-stu-id="b06df-125">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="b06df-126">FunctionLeave2 函数</span><span class="sxs-lookup"><span data-stu-id="b06df-126">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="b06df-127">FunctionTailcall2 函数</span><span class="sxs-lookup"><span data-stu-id="b06df-127">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="b06df-128">SetEnterLeaveFunctionHooks2 方法</span><span class="sxs-lookup"><span data-stu-id="b06df-128">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="b06df-129">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="b06df-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
