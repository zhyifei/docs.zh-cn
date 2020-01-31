---
title: FunctionEnter2 函数
ms.date: 03/30/2017
api_name:
- FunctionEnter2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter2
helpviewer_keywords:
- FunctionEnter2 function [.NET Framework profiling]
ms.assetid: ce7a21f9-0ca3-4b92-bc4b-bb803cae3f51
topic_type:
- apiref
ms.openlocfilehash: 6cd35c180b8a322b3402b050c6d6840073010b1f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866978"
---
# <a name="functionenter2-function"></a><span data-ttu-id="137ba-102">FunctionEnter2 函数</span><span class="sxs-lookup"><span data-stu-id="137ba-102">FunctionEnter2 Function</span></span>
<span data-ttu-id="137ba-103">通知探查器控制正在传递到函数，并提供有关堆栈帧和函数参数的信息。</span><span class="sxs-lookup"><span data-stu-id="137ba-103">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="137ba-104">此函数取代了[FunctionEnter](functionenter-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="137ba-104">This function supersedes the [FunctionEnter](functionenter-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="137ba-105">语法</span><span class="sxs-lookup"><span data-stu-id="137ba-105">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,   
    [in]  UINT_PTR                         clientData,   
    [in]  COR_PRF_FRAME_INFO               func,   
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="137ba-106">参数</span><span class="sxs-lookup"><span data-stu-id="137ba-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="137ba-107">\[中] 控制传递到的函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="137ba-107">\[in] The identifier of the function to which control is passed.</span></span>

- `clientData`

  <span data-ttu-id="137ba-108">中 \[] 重新映射的函数标识符，探查器以前使用[FunctionIDMapper](functionidmapper-function.md)函数指定了它。</span><span class="sxs-lookup"><span data-stu-id="137ba-108">\[in] The remapped function identifier, which the profiler previously specified by using the [FunctionIDMapper](functionidmapper-function.md) function.</span></span>
  
- `func`

  <span data-ttu-id="137ba-109">\[中的] `COR_PRF_FRAME_INFO` 值，该值指向有关堆栈帧的信息。</span><span class="sxs-lookup"><span data-stu-id="137ba-109">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>
  
  <span data-ttu-id="137ba-110">探查器应将此视为不透明的句柄，该句柄可传递回[ICorProfilerInfo2：： GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md)方法中的执行引擎。</span><span class="sxs-lookup"><span data-stu-id="137ba-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
- `argumentInfo`

  <span data-ttu-id="137ba-111">\[中的）指向[COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md)结构的指针，该结构指定函数参数在内存中的位置。</span><span class="sxs-lookup"><span data-stu-id="137ba-111">\[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure that specifies the locations in memory of the function's arguments.</span></span>

  <span data-ttu-id="137ba-112">为了访问参数信息，必须设置 `COR_PRF_ENABLE_FUNCTION_ARGS` 标志。</span><span class="sxs-lookup"><span data-stu-id="137ba-112">In order to access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag must be set.</span></span> <span data-ttu-id="137ba-113">探查器可以使用[ICorProfilerInfo：： SetEventMask](icorprofilerinfo-seteventmask-method.md)方法来设置事件标志。</span><span class="sxs-lookup"><span data-stu-id="137ba-113">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>

## <a name="remarks"></a><span data-ttu-id="137ba-114">备注</span><span class="sxs-lookup"><span data-stu-id="137ba-114">Remarks</span></span>  
 <span data-ttu-id="137ba-115">`FunctionEnter2` 函数返回后，`func` 和 `argumentInfo` 参数的值无效，因为值可能会更改或被销毁。</span><span class="sxs-lookup"><span data-stu-id="137ba-115">The values of the `func` and `argumentInfo` parameters are not valid after the `FunctionEnter2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="137ba-116">`FunctionEnter2` 函数是回调;必须实现此方法。</span><span class="sxs-lookup"><span data-stu-id="137ba-116">The `FunctionEnter2` function is a callback; you must implement it.</span></span> <span data-ttu-id="137ba-117">实现必须使用 `__declspec`（`naked`）存储类特性。</span><span class="sxs-lookup"><span data-stu-id="137ba-117">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="137ba-118">在调用此函数之前，执行引擎不会保存任何注册。</span><span class="sxs-lookup"><span data-stu-id="137ba-118">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="137ba-119">进入时，必须保存使用的所有寄存器，包括浮点单元（FPU）中的所有寄存器。</span><span class="sxs-lookup"><span data-stu-id="137ba-119">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="137ba-120">退出时，必须通过弹出由其调用方推送的所有参数来还原堆栈。</span><span class="sxs-lookup"><span data-stu-id="137ba-120">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="137ba-121">`FunctionEnter2` 的实现不应被阻止，因为它将延迟垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="137ba-121">The implementation of `FunctionEnter2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="137ba-122">实现不应尝试垃圾回收，因为堆栈可能不处于垃圾回收友好状态。</span><span class="sxs-lookup"><span data-stu-id="137ba-122">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="137ba-123">如果尝试垃圾回收，则运行时将被阻止，直到 `FunctionEnter2` 返回。</span><span class="sxs-lookup"><span data-stu-id="137ba-123">If a garbage collection is attempted, the runtime will block until `FunctionEnter2` returns.</span></span>  
  
 <span data-ttu-id="137ba-124">此外，`FunctionEnter2` 函数不得调入托管代码或以任何方式导致托管的内存分配。</span><span class="sxs-lookup"><span data-stu-id="137ba-124">Also, the `FunctionEnter2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="137ba-125">需求</span><span class="sxs-lookup"><span data-stu-id="137ba-125">Requirements</span></span>  
 <span data-ttu-id="137ba-126">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="137ba-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="137ba-127">**标头：** Corprof.idl .idl</span><span class="sxs-lookup"><span data-stu-id="137ba-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="137ba-128">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="137ba-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="137ba-129">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="137ba-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="137ba-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="137ba-130">See also</span></span>

- [<span data-ttu-id="137ba-131">FunctionLeave2 函数</span><span class="sxs-lookup"><span data-stu-id="137ba-131">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="137ba-132">FunctionTailcall2 函数</span><span class="sxs-lookup"><span data-stu-id="137ba-132">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="137ba-133">SetEnterLeaveFunctionHooks2 方法</span><span class="sxs-lookup"><span data-stu-id="137ba-133">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="137ba-134">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="137ba-134">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
