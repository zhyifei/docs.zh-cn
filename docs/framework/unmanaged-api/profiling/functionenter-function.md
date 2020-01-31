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
ms.openlocfilehash: caea1d3d526017c0118f95bb138ee4ac45d2c137
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866991"
---
# <a name="functionenter-function"></a><span data-ttu-id="2dc16-102">FunctionEnter 函数</span><span class="sxs-lookup"><span data-stu-id="2dc16-102">FunctionEnter Function</span></span>
<span data-ttu-id="2dc16-103">通知探查器控制正在传递到函数。</span><span class="sxs-lookup"><span data-stu-id="2dc16-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2dc16-104">`FunctionEnter` 函数在 .NET Framework 版本2.0 中已弃用，其使用将导致性能下降。</span><span class="sxs-lookup"><span data-stu-id="2dc16-104">The `FunctionEnter` function is deprecated in the .NET Framework version 2.0, and its use will incur a performance penalty.</span></span> <span data-ttu-id="2dc16-105">改为使用[FunctionEnter2](functionenter2-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="2dc16-105">Use the [FunctionEnter2](functionenter2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dc16-106">语法</span><span class="sxs-lookup"><span data-stu-id="2dc16-106">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2dc16-107">参数</span><span class="sxs-lookup"><span data-stu-id="2dc16-107">Parameters</span></span>

- `funcID`

  <span data-ttu-id="2dc16-108">\[中] 控制传递到的函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="2dc16-108">\[in] The identifier of the function to which control is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="2dc16-109">备注</span><span class="sxs-lookup"><span data-stu-id="2dc16-109">Remarks</span></span>  
 <span data-ttu-id="2dc16-110">`FunctionEnter` 函数是回调;必须实现此方法。</span><span class="sxs-lookup"><span data-stu-id="2dc16-110">The `FunctionEnter` function is a callback; you must implement it.</span></span> <span data-ttu-id="2dc16-111">实现必须使用 `__declspec`（`naked`）存储类特性。</span><span class="sxs-lookup"><span data-stu-id="2dc16-111">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="2dc16-112">在调用此函数之前，执行引擎不会保存任何注册。</span><span class="sxs-lookup"><span data-stu-id="2dc16-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="2dc16-113">进入时，必须保存使用的所有寄存器，包括浮点单元（FPU）中的所有寄存器。</span><span class="sxs-lookup"><span data-stu-id="2dc16-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="2dc16-114">退出时，必须通过弹出由其调用方推送的所有参数来还原堆栈。</span><span class="sxs-lookup"><span data-stu-id="2dc16-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="2dc16-115">`FunctionEnter` 的实现不应被阻止，因为它将延迟垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="2dc16-115">The implementation of `FunctionEnter` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="2dc16-116">实现不应尝试垃圾回收，因为堆栈可能不处于垃圾回收友好状态。</span><span class="sxs-lookup"><span data-stu-id="2dc16-116">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="2dc16-117">如果尝试垃圾回收，则运行时将被阻止，直到 `FunctionEnter` 返回。</span><span class="sxs-lookup"><span data-stu-id="2dc16-117">If a garbage collection is attempted, the runtime will block until `FunctionEnter` returns.</span></span>  
  
 <span data-ttu-id="2dc16-118">此外，`FunctionEnter` 函数不得调入托管代码或以任何方式导致托管的内存分配。</span><span class="sxs-lookup"><span data-stu-id="2dc16-118">Also, the `FunctionEnter` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dc16-119">需求</span><span class="sxs-lookup"><span data-stu-id="2dc16-119">Requirements</span></span>  
 <span data-ttu-id="2dc16-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2dc16-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2dc16-121">**标头：** Corprof.idl .idl</span><span class="sxs-lookup"><span data-stu-id="2dc16-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="2dc16-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2dc16-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2dc16-123">**.NET Framework 版本：** 1.1、1.0</span><span class="sxs-lookup"><span data-stu-id="2dc16-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dc16-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2dc16-124">See also</span></span>

- [<span data-ttu-id="2dc16-125">FunctionEnter2 函数</span><span class="sxs-lookup"><span data-stu-id="2dc16-125">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="2dc16-126">FunctionLeave2 函数</span><span class="sxs-lookup"><span data-stu-id="2dc16-126">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="2dc16-127">FunctionTailcall2 函数</span><span class="sxs-lookup"><span data-stu-id="2dc16-127">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="2dc16-128">SetEnterLeaveFunctionHooks2 方法</span><span class="sxs-lookup"><span data-stu-id="2dc16-128">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="2dc16-129">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="2dc16-129">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
