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
ms.openlocfilehash: a9ab8c81c995bbec41db217c904e03dd70351aee
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866879"
---
# <a name="functionleave-function"></a><span data-ttu-id="66e92-102">FunctionLeave 函数</span><span class="sxs-lookup"><span data-stu-id="66e92-102">FunctionLeave Function</span></span>
<span data-ttu-id="66e92-103">通知探查器某个函数将要返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="66e92-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="66e92-104">`FunctionLeave` 函数在 .NET Framework 2.0 中已弃用。</span><span class="sxs-lookup"><span data-stu-id="66e92-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="66e92-105">它将继续运行，但会导致性能下降。</span><span class="sxs-lookup"><span data-stu-id="66e92-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="66e92-106">改为使用[FunctionLeave2](functionleave2-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="66e92-106">Use the [FunctionLeave2](functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66e92-107">语法</span><span class="sxs-lookup"><span data-stu-id="66e92-107">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66e92-108">参数</span><span class="sxs-lookup"><span data-stu-id="66e92-108">Parameters</span></span>

- `funcID`

  <span data-ttu-id="66e92-109">\[中] 返回的函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="66e92-109">\[in] The identifier of the function that is returning.</span></span>

## <a name="remarks"></a><span data-ttu-id="66e92-110">备注</span><span class="sxs-lookup"><span data-stu-id="66e92-110">Remarks</span></span>  
 <span data-ttu-id="66e92-111">`FunctionLeave` 函数是回调;必须实现此方法。</span><span class="sxs-lookup"><span data-stu-id="66e92-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="66e92-112">实现必须使用 `__declspec`（`naked`）存储类特性。</span><span class="sxs-lookup"><span data-stu-id="66e92-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="66e92-113">在调用此函数之前，执行引擎不会保存任何注册。</span><span class="sxs-lookup"><span data-stu-id="66e92-113">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="66e92-114">进入时，必须保存使用的所有寄存器，包括浮点单元（FPU）中的所有寄存器。</span><span class="sxs-lookup"><span data-stu-id="66e92-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="66e92-115">退出时，必须通过弹出由其调用方推送的所有参数来还原堆栈。</span><span class="sxs-lookup"><span data-stu-id="66e92-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="66e92-116">`FunctionLeave` 的实现不应被阻止，因为它将延迟垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="66e92-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="66e92-117">实现不应尝试垃圾回收，因为堆栈可能不处于垃圾回收友好状态。</span><span class="sxs-lookup"><span data-stu-id="66e92-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="66e92-118">如果尝试垃圾回收，则运行时将被阻止，直到 `FunctionLeave` 返回。</span><span class="sxs-lookup"><span data-stu-id="66e92-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="66e92-119">此外，`FunctionLeave` 函数不得调入托管代码或以任何方式导致托管的内存分配。</span><span class="sxs-lookup"><span data-stu-id="66e92-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66e92-120">需求</span><span class="sxs-lookup"><span data-stu-id="66e92-120">Requirements</span></span>  
 <span data-ttu-id="66e92-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="66e92-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66e92-122">**标头：** Corprof.idl .idl</span><span class="sxs-lookup"><span data-stu-id="66e92-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="66e92-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66e92-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66e92-124">**.NET Framework 版本：** 1.1、1.0</span><span class="sxs-lookup"><span data-stu-id="66e92-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66e92-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66e92-125">See also</span></span>

- [<span data-ttu-id="66e92-126">FunctionEnter2 函数</span><span class="sxs-lookup"><span data-stu-id="66e92-126">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="66e92-127">FunctionLeave2 函数</span><span class="sxs-lookup"><span data-stu-id="66e92-127">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="66e92-128">FunctionTailcall2 函数</span><span class="sxs-lookup"><span data-stu-id="66e92-128">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="66e92-129">SetEnterLeaveFunctionHooks2 方法</span><span class="sxs-lookup"><span data-stu-id="66e92-129">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="66e92-130">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="66e92-130">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
