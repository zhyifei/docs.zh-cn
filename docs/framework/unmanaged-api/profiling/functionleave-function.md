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
ms.openlocfilehash: 238a5f19bd8cbd89a5537b2b9297bfa9e1f54613
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952876"
---
# <a name="functionleave-function"></a><span data-ttu-id="58f9b-102">FunctionLeave 函数</span><span class="sxs-lookup"><span data-stu-id="58f9b-102">FunctionLeave Function</span></span>
<span data-ttu-id="58f9b-103">通知探查器某个函数将要返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="58f9b-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="58f9b-104">.NET Framework `FunctionLeave` 2.0 中不推荐使用该函数。</span><span class="sxs-lookup"><span data-stu-id="58f9b-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="58f9b-105">它将继续运行, 但会导致性能下降。</span><span class="sxs-lookup"><span data-stu-id="58f9b-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="58f9b-106">改为使用[FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="58f9b-106">Use the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58f9b-107">语法</span><span class="sxs-lookup"><span data-stu-id="58f9b-107">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58f9b-108">参数</span><span class="sxs-lookup"><span data-stu-id="58f9b-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="58f9b-109">中返回的函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="58f9b-109">[in] The identifier of the function that is returning.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58f9b-110">备注</span><span class="sxs-lookup"><span data-stu-id="58f9b-110">Remarks</span></span>  
 <span data-ttu-id="58f9b-111">`FunctionLeave`函数是回调; 必须实现它。</span><span class="sxs-lookup"><span data-stu-id="58f9b-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="58f9b-112">实现必须使用`__declspec`(`naked`) 存储类特性。</span><span class="sxs-lookup"><span data-stu-id="58f9b-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="58f9b-113">在调用此函数之前, 执行引擎不会保存任何注册。</span><span class="sxs-lookup"><span data-stu-id="58f9b-113">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="58f9b-114">进入时, 必须保存使用的所有寄存器, 包括浮点单元 (FPU) 中的所有寄存器。</span><span class="sxs-lookup"><span data-stu-id="58f9b-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="58f9b-115">退出时, 必须通过弹出由其调用方推送的所有参数来还原堆栈。</span><span class="sxs-lookup"><span data-stu-id="58f9b-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="58f9b-116">的`FunctionLeave`实现不应被阻止, 因为它将延迟垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="58f9b-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="58f9b-117">实现不应尝试垃圾回收, 因为堆栈可能不处于垃圾回收友好状态。</span><span class="sxs-lookup"><span data-stu-id="58f9b-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="58f9b-118">如果尝试垃圾回收, 则运行时将被阻止, `FunctionLeave`直到返回。</span><span class="sxs-lookup"><span data-stu-id="58f9b-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="58f9b-119">此外, 该`FunctionLeave`函数不得调入托管代码或以任何方式导致托管的内存分配。</span><span class="sxs-lookup"><span data-stu-id="58f9b-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58f9b-120">要求</span><span class="sxs-lookup"><span data-stu-id="58f9b-120">Requirements</span></span>  
 <span data-ttu-id="58f9b-121">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="58f9b-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58f9b-122">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="58f9b-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="58f9b-123">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58f9b-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58f9b-124">**.NET Framework 版本:** 1.1、1。0</span><span class="sxs-lookup"><span data-stu-id="58f9b-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58f9b-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="58f9b-125">See also</span></span>

- [<span data-ttu-id="58f9b-126">FunctionEnter2 函数</span><span class="sxs-lookup"><span data-stu-id="58f9b-126">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="58f9b-127">FunctionLeave2 函数</span><span class="sxs-lookup"><span data-stu-id="58f9b-127">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="58f9b-128">FunctionTailcall2 函数</span><span class="sxs-lookup"><span data-stu-id="58f9b-128">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="58f9b-129">SetEnterLeaveFunctionHooks2 方法</span><span class="sxs-lookup"><span data-stu-id="58f9b-129">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="58f9b-130">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="58f9b-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
