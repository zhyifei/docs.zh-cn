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
ms.openlocfilehash: 774a5d4e48f00ea8c28977f3f685dcd5a8da3199
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440585"
---
# <a name="functionleave-function"></a><span data-ttu-id="ade9a-102">FunctionLeave 函数</span><span class="sxs-lookup"><span data-stu-id="ade9a-102">FunctionLeave Function</span></span>
<span data-ttu-id="ade9a-103">Notifies the profiler that a function is about to return to the caller.</span><span class="sxs-lookup"><span data-stu-id="ade9a-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ade9a-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="ade9a-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="ade9a-105">It will continue to work, but will incur a performance penalty.</span><span class="sxs-lookup"><span data-stu-id="ade9a-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="ade9a-106">Use the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) function instead.</span><span class="sxs-lookup"><span data-stu-id="ade9a-106">Use the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ade9a-107">语法</span><span class="sxs-lookup"><span data-stu-id="ade9a-107">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ade9a-108">参数</span><span class="sxs-lookup"><span data-stu-id="ade9a-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="ade9a-109">[in] The identifier of the function that is returning.</span><span class="sxs-lookup"><span data-stu-id="ade9a-109">[in] The identifier of the function that is returning.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ade9a-110">备注</span><span class="sxs-lookup"><span data-stu-id="ade9a-110">Remarks</span></span>  
 <span data-ttu-id="ade9a-111">The `FunctionLeave` function is a callback; you must implement it.</span><span class="sxs-lookup"><span data-stu-id="ade9a-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="ade9a-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span><span class="sxs-lookup"><span data-stu-id="ade9a-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="ade9a-113">The execution engine does not save any registers before calling this function.</span><span class="sxs-lookup"><span data-stu-id="ade9a-113">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="ade9a-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span><span class="sxs-lookup"><span data-stu-id="ade9a-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="ade9a-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span><span class="sxs-lookup"><span data-stu-id="ade9a-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="ade9a-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span><span class="sxs-lookup"><span data-stu-id="ade9a-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="ade9a-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span><span class="sxs-lookup"><span data-stu-id="ade9a-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="ade9a-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span><span class="sxs-lookup"><span data-stu-id="ade9a-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="ade9a-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span><span class="sxs-lookup"><span data-stu-id="ade9a-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ade9a-120">要求</span><span class="sxs-lookup"><span data-stu-id="ade9a-120">Requirements</span></span>  
 <span data-ttu-id="ade9a-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ade9a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ade9a-122">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="ade9a-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="ade9a-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ade9a-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ade9a-124">**.NET Framework Versions:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="ade9a-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ade9a-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="ade9a-125">See also</span></span>

- [<span data-ttu-id="ade9a-126">FunctionEnter2 函数</span><span class="sxs-lookup"><span data-stu-id="ade9a-126">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="ade9a-127">FunctionLeave2 函数</span><span class="sxs-lookup"><span data-stu-id="ade9a-127">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="ade9a-128">FunctionTailcall2 函数</span><span class="sxs-lookup"><span data-stu-id="ade9a-128">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="ade9a-129">SetEnterLeaveFunctionHooks2 方法</span><span class="sxs-lookup"><span data-stu-id="ade9a-129">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="ade9a-130">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="ade9a-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
