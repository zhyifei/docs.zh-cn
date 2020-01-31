---
title: FunctionEnter3 函数
ms.date: 03/30/2017
api_name:
- FunctionEnter3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter3
helpviewer_keywords:
- FunctionEnter3 function [.NET Framework profiling]
ms.assetid: ef782c53-dae7-4990-b4ad-fddb1e690d4e
topic_type:
- apiref
ms.openlocfilehash: 0ed7a0619816caab64361d7922d28b18c60ed453
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790270"
---
# <a name="functionenter3-function"></a><span data-ttu-id="b39a6-102">FunctionEnter3 函数</span><span class="sxs-lookup"><span data-stu-id="b39a6-102">FunctionEnter3 Function</span></span>
<span data-ttu-id="b39a6-103">通知探查器控制正在传递到函数。</span><span class="sxs-lookup"><span data-stu-id="b39a6-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b39a6-104">语法</span><span class="sxs-lookup"><span data-stu-id="b39a6-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b39a6-105">参数</span><span class="sxs-lookup"><span data-stu-id="b39a6-105">Parameters</span></span>

- `functionOrRemappedID`

  <span data-ttu-id="b39a6-106">\[中] 控制传递到的函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="b39a6-106">\[in] The identifier of the function to which control is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="b39a6-107">备注</span><span class="sxs-lookup"><span data-stu-id="b39a6-107">Remarks</span></span>  
 <span data-ttu-id="b39a6-108">`FunctionEnter3` 回调函数将在调用函数时通知探查器，但不支持参数检查。</span><span class="sxs-lookup"><span data-stu-id="b39a6-108">The `FunctionEnter3` callback function notifies the profiler as functions are being called, but does not support argument inspection.</span></span> <span data-ttu-id="b39a6-109">使用[ICorProfilerInfo3：： SetEnterLeaveFunctionHooks3 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)注册此函数的实现。</span><span class="sxs-lookup"><span data-stu-id="b39a6-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="b39a6-110">`FunctionEnter3` 函数是回调;必须实现此方法。</span><span class="sxs-lookup"><span data-stu-id="b39a6-110">The `FunctionEnter3` function is a callback; you must implement it.</span></span> <span data-ttu-id="b39a6-111">实现必须使用 `__declspec(naked)` 存储类特性。</span><span class="sxs-lookup"><span data-stu-id="b39a6-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="b39a6-112">在调用此函数之前，执行引擎不会保存任何注册。</span><span class="sxs-lookup"><span data-stu-id="b39a6-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="b39a6-113">进入时，必须保存使用的所有寄存器，包括浮点单元（FPU）中的所有寄存器。</span><span class="sxs-lookup"><span data-stu-id="b39a6-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="b39a6-114">退出时，必须通过弹出由其调用方推送的所有参数来还原堆栈。</span><span class="sxs-lookup"><span data-stu-id="b39a6-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b39a6-115">需求</span><span class="sxs-lookup"><span data-stu-id="b39a6-115">Requirements</span></span>  
 <span data-ttu-id="b39a6-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b39a6-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b39a6-117">**标头：** Corprof.idl .idl</span><span class="sxs-lookup"><span data-stu-id="b39a6-117">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="b39a6-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b39a6-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b39a6-119">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b39a6-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b39a6-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b39a6-120">See also</span></span>

- [<span data-ttu-id="b39a6-121">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="b39a6-121">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="b39a6-122">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="b39a6-122">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="b39a6-123">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b39a6-123">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="b39a6-124">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b39a6-124">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="b39a6-125">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b39a6-125">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="b39a6-126">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="b39a6-126">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="b39a6-127">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b39a6-127">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="b39a6-128">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="b39a6-128">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="b39a6-129">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="b39a6-129">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="b39a6-130">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="b39a6-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
