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
ms.openlocfilehash: 9d38c32c4ed938de4a517009c5a76310df6d39fb
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586756"
---
# <a name="functionenter-function"></a><span data-ttu-id="3026e-102">FunctionEnter 函数</span><span class="sxs-lookup"><span data-stu-id="3026e-102">FunctionEnter Function</span></span>
<span data-ttu-id="3026e-103">通知探查器控件传递给函数。</span><span class="sxs-lookup"><span data-stu-id="3026e-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3026e-104">`FunctionEnter`函数被弃用，在.NET Framework 2.0 版中，并且它的使用将会产生对性能产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="3026e-104">The `FunctionEnter` function is deprecated in the .NET Framework version 2.0, and its use will incur a performance penalty.</span></span> <span data-ttu-id="3026e-105">使用[FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="3026e-105">Use the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3026e-106">语法</span><span class="sxs-lookup"><span data-stu-id="3026e-106">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3026e-107">参数</span><span class="sxs-lookup"><span data-stu-id="3026e-107">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="3026e-108">[in]控件传递到函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="3026e-108">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3026e-109">备注</span><span class="sxs-lookup"><span data-stu-id="3026e-109">Remarks</span></span>  
 <span data-ttu-id="3026e-110">`FunctionEnter`函数是一个回调; 必须实现它。</span><span class="sxs-lookup"><span data-stu-id="3026e-110">The `FunctionEnter` function is a callback; you must implement it.</span></span> <span data-ttu-id="3026e-111">实现必须使用`__declspec`(`naked`) 存储类特性。</span><span class="sxs-lookup"><span data-stu-id="3026e-111">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="3026e-112">调用此函数之前，执行引擎不会保存任何寄存器。</span><span class="sxs-lookup"><span data-stu-id="3026e-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="3026e-113">在进入时，必须保存使用，包括浮点单元 (FPU) 中的所有注册。</span><span class="sxs-lookup"><span data-stu-id="3026e-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="3026e-114">退出时，必须通过弹出已推送到由其调用方的所有参数由还原堆栈。</span><span class="sxs-lookup"><span data-stu-id="3026e-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="3026e-115">实现`FunctionEnter`不应阻止，因为它会延迟垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="3026e-115">The implementation of `FunctionEnter` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="3026e-116">实现不应尝试垃圾回收，因为堆栈可能不是在垃圾收集友好状态中。</span><span class="sxs-lookup"><span data-stu-id="3026e-116">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="3026e-117">如果尝试在垃圾回收，则运行时将阻止直到`FunctionEnter`返回。</span><span class="sxs-lookup"><span data-stu-id="3026e-117">If a garbage collection is attempted, the runtime will block until `FunctionEnter` returns.</span></span>  
  
 <span data-ttu-id="3026e-118">此外，`FunctionEnter`函数不能调用到托管代码中或以任何方式导致托管的内存分配。</span><span class="sxs-lookup"><span data-stu-id="3026e-118">Also, the `FunctionEnter` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3026e-119">要求</span><span class="sxs-lookup"><span data-stu-id="3026e-119">Requirements</span></span>  
 <span data-ttu-id="3026e-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3026e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3026e-121">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="3026e-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="3026e-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3026e-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3026e-123">**.NET framework 版本：** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="3026e-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3026e-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="3026e-124">See also</span></span>

- [<span data-ttu-id="3026e-125">FunctionEnter2 函数</span><span class="sxs-lookup"><span data-stu-id="3026e-125">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="3026e-126">FunctionLeave2 函数</span><span class="sxs-lookup"><span data-stu-id="3026e-126">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="3026e-127">FunctionTailcall2 函数</span><span class="sxs-lookup"><span data-stu-id="3026e-127">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="3026e-128">SetEnterLeaveFunctionHooks2 方法</span><span class="sxs-lookup"><span data-stu-id="3026e-128">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="3026e-129">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="3026e-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
