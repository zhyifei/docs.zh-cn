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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a731df84af0991f80c560db417df0ffe053a5e2b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59200774"
---
# <a name="functionenter3-function"></a><span data-ttu-id="f0463-102">FunctionEnter3 函数</span><span class="sxs-lookup"><span data-stu-id="f0463-102">FunctionEnter3 Function</span></span>
<span data-ttu-id="f0463-103">通知探查器控件传递给函数。</span><span class="sxs-lookup"><span data-stu-id="f0463-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0463-104">语法</span><span class="sxs-lookup"><span data-stu-id="f0463-104">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0463-105">参数</span><span class="sxs-lookup"><span data-stu-id="f0463-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="f0463-106">[in]控件传递到函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="f0463-106">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0463-107">备注</span><span class="sxs-lookup"><span data-stu-id="f0463-107">Remarks</span></span>  
 <span data-ttu-id="f0463-108">`FunctionEnter3`回调函数通知探查器，因为函数正被调用，但不会不支持参数检查。</span><span class="sxs-lookup"><span data-stu-id="f0463-108">The `FunctionEnter3` callback function notifies the profiler as functions are being called, but does not support argument inspection.</span></span> <span data-ttu-id="f0463-109">使用[ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)注册此函数的实现。</span><span class="sxs-lookup"><span data-stu-id="f0463-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="f0463-110">`FunctionEnter3`函数是一个回调; 必须实现它。</span><span class="sxs-lookup"><span data-stu-id="f0463-110">The `FunctionEnter3` function is a callback; you must implement it.</span></span> <span data-ttu-id="f0463-111">实现必须使用`__declspec(naked)`存储类特性。</span><span class="sxs-lookup"><span data-stu-id="f0463-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="f0463-112">调用此函数之前，执行引擎不会保存任何寄存器。</span><span class="sxs-lookup"><span data-stu-id="f0463-112">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="f0463-113">在进入时，必须保存使用，包括浮点单元 (FPU) 中的所有注册。</span><span class="sxs-lookup"><span data-stu-id="f0463-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="f0463-114">退出时，必须通过弹出已推送到由其调用方的所有参数由还原堆栈。</span><span class="sxs-lookup"><span data-stu-id="f0463-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0463-115">要求</span><span class="sxs-lookup"><span data-stu-id="f0463-115">Requirements</span></span>  
 <span data-ttu-id="f0463-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f0463-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0463-117">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="f0463-117">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="f0463-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0463-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0463-119">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0463-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0463-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="f0463-120">See also</span></span>

- [<span data-ttu-id="f0463-121">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="f0463-121">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="f0463-122">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="f0463-122">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="f0463-123">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f0463-123">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="f0463-124">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f0463-124">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="f0463-125">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f0463-125">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="f0463-126">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="f0463-126">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="f0463-127">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f0463-127">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="f0463-128">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="f0463-128">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="f0463-129">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="f0463-129">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="f0463-130">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="f0463-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
