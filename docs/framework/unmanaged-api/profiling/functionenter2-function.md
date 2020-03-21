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
ms.openlocfilehash: 9aeb7a294beb10f9c2968e6161c72fdc362c4991
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177054"
---
# <a name="functionenter2-function"></a><span data-ttu-id="cef10-102">FunctionEnter2 函数</span><span class="sxs-lookup"><span data-stu-id="cef10-102">FunctionEnter2 Function</span></span>
<span data-ttu-id="cef10-103">通知探查器控件正在传递到函数，并提供有关堆栈帧和函数参数的信息。</span><span class="sxs-lookup"><span data-stu-id="cef10-103">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="cef10-104">此函数取代[函数Enter](functionenter-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="cef10-104">This function supersedes the [FunctionEnter](functionenter-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cef10-105">语法</span><span class="sxs-lookup"><span data-stu-id="cef10-105">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,
    [in]  UINT_PTR                         clientData,
    [in]  COR_PRF_FRAME_INFO               func,
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cef10-106">parameters</span><span class="sxs-lookup"><span data-stu-id="cef10-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="cef10-107">\[in] 传递给控件的函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="cef10-107">\[in] The identifier of the function to which control is passed.</span></span>

- `clientData`

  <span data-ttu-id="cef10-108">\[in] 重新映射的函数标识符，探查器以前使用[函数 IDMapper](functionidmapper-function.md)函数指定该标识符。</span><span class="sxs-lookup"><span data-stu-id="cef10-108">\[in] The remapped function identifier, which the profiler previously specified by using the [FunctionIDMapper](functionidmapper-function.md) function.</span></span>
  
- `func`

  <span data-ttu-id="cef10-109">\[in]`COR_PRF_FRAME_INFO`指向有关堆栈帧的信息的值。</span><span class="sxs-lookup"><span data-stu-id="cef10-109">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>
  
  <span data-ttu-id="cef10-110">探查器应将此视为不透明句柄，可在[ICorProfilerInfo2 中传回执行引擎：：get功能Info2](icorprofilerinfo2-getfunctioninfo2-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="cef10-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
- `argumentInfo`

  <span data-ttu-id="cef10-111">\[in] 指向[COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md)结构的指针，用于指定函数参数的内存中的位置。</span><span class="sxs-lookup"><span data-stu-id="cef10-111">\[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure that specifies the locations in memory of the function's arguments.</span></span>

  <span data-ttu-id="cef10-112">为了访问参数信息，`COR_PRF_ENABLE_FUNCTION_ARGS`必须设置标志。</span><span class="sxs-lookup"><span data-stu-id="cef10-112">In order to access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag must be set.</span></span> <span data-ttu-id="cef10-113">探查器可以使用[ICorProfilerInfo：：SetEventMask](icorprofilerinfo-seteventmask-method.md)方法设置事件标志。</span><span class="sxs-lookup"><span data-stu-id="cef10-113">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>

## <a name="remarks"></a><span data-ttu-id="cef10-114">备注</span><span class="sxs-lookup"><span data-stu-id="cef10-114">Remarks</span></span>  
 <span data-ttu-id="cef10-115">`func`和`argumentInfo`参数的值在`FunctionEnter2`函数返回后无效，因为值可能会更改或被销毁。</span><span class="sxs-lookup"><span data-stu-id="cef10-115">The values of the `func` and `argumentInfo` parameters are not valid after the `FunctionEnter2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="cef10-116">函数`FunctionEnter2`是回调;你必须实现它。</span><span class="sxs-lookup"><span data-stu-id="cef10-116">The `FunctionEnter2` function is a callback; you must implement it.</span></span> <span data-ttu-id="cef10-117">实现必须使用`__declspec`（`naked`） 存储类属性。</span><span class="sxs-lookup"><span data-stu-id="cef10-117">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="cef10-118">在调用此函数之前，执行引擎不会保存任何寄存器。</span><span class="sxs-lookup"><span data-stu-id="cef10-118">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="cef10-119">进入时，必须保存您使用的所有寄存器，包括浮点单元 （FPU） 中的寄存器。</span><span class="sxs-lookup"><span data-stu-id="cef10-119">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="cef10-120">在退出时，必须通过弹出其调用方推送的所有参数来还原堆栈。</span><span class="sxs-lookup"><span data-stu-id="cef10-120">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="cef10-121">的实现不应`FunctionEnter2`阻塞，因为它将延迟垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="cef10-121">The implementation of `FunctionEnter2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="cef10-122">实现不应尝试垃圾回收，因为堆栈可能未处于垃圾回收友好状态。</span><span class="sxs-lookup"><span data-stu-id="cef10-122">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="cef10-123">如果尝试垃圾回收，运行时将阻塞，直到`FunctionEnter2`返回。</span><span class="sxs-lookup"><span data-stu-id="cef10-123">If a garbage collection is attempted, the runtime will block until `FunctionEnter2` returns.</span></span>  
  
 <span data-ttu-id="cef10-124">此外，`FunctionEnter2`该函数不得调用托管代码，或以任何方式导致托管内存分配。</span><span class="sxs-lookup"><span data-stu-id="cef10-124">Also, the `FunctionEnter2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cef10-125">要求</span><span class="sxs-lookup"><span data-stu-id="cef10-125">Requirements</span></span>  
 <span data-ttu-id="cef10-126">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cef10-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cef10-127">**标题：** 科尔普罗普.伊德尔</span><span class="sxs-lookup"><span data-stu-id="cef10-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="cef10-128">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cef10-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cef10-129">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cef10-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cef10-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cef10-130">See also</span></span>

- [<span data-ttu-id="cef10-131">FunctionLeave2 函数</span><span class="sxs-lookup"><span data-stu-id="cef10-131">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="cef10-132">FunctionTailcall2 函数</span><span class="sxs-lookup"><span data-stu-id="cef10-132">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="cef10-133">SetEnterLeaveFunctionHooks2 方法</span><span class="sxs-lookup"><span data-stu-id="cef10-133">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="cef10-134">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="cef10-134">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
