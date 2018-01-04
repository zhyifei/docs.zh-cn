---
title: "FunctionEnter3 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionEnter3
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionEnter3
helpviewer_keywords: FunctionEnter3 function [.NET Framework profiling]
ms.assetid: ef782c53-dae7-4990-b4ad-fddb1e690d4e
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4bbdfa608f1ea60462dc432a7c2b98cafe66d7be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="functionenter3-function"></a><span data-ttu-id="a7fb0-102">FunctionEnter3 函数</span><span class="sxs-lookup"><span data-stu-id="a7fb0-102">FunctionEnter3 Function</span></span>
<span data-ttu-id="a7fb0-103">通知探查器控件传递给函数。</span><span class="sxs-lookup"><span data-stu-id="a7fb0-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7fb0-104">语法</span><span class="sxs-lookup"><span data-stu-id="a7fb0-104">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7fb0-105">参数</span><span class="sxs-lookup"><span data-stu-id="a7fb0-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="a7fb0-106">[in]控件传递到函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="a7fb0-106">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7fb0-107">备注</span><span class="sxs-lookup"><span data-stu-id="a7fb0-107">Remarks</span></span>  
 <span data-ttu-id="a7fb0-108">`FunctionEnter3`回调函数向发出你通知探查器函数正被调用，但不是支持参数检查。</span><span class="sxs-lookup"><span data-stu-id="a7fb0-108">The `FunctionEnter3` callback function notifies the profiler as functions are being called, but does not support argument inspection.</span></span> <span data-ttu-id="a7fb0-109">使用[icorprofilerinfo3:: Setenterleavefunctionhooks3 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)注册此函数的实现。</span><span class="sxs-lookup"><span data-stu-id="a7fb0-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="a7fb0-110">`FunctionEnter3`函数为回调; 你必须实现它。</span><span class="sxs-lookup"><span data-stu-id="a7fb0-110">The `FunctionEnter3` function is a callback; you must implement it.</span></span> <span data-ttu-id="a7fb0-111">实现必须使用`__declspec(naked)`存储类特性。</span><span class="sxs-lookup"><span data-stu-id="a7fb0-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="a7fb0-112">调用此函数之前，执行引擎不保存任何寄存器。</span><span class="sxs-lookup"><span data-stu-id="a7fb0-112">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="a7fb0-113">在进入时，必须保存所有使用，包括浮点单位 (FPU) 中的寄存器。</span><span class="sxs-lookup"><span data-stu-id="a7fb0-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="a7fb0-114">在退出时，你必须通过弹出已推送由其调用方的所有参数由还原堆栈。</span><span class="sxs-lookup"><span data-stu-id="a7fb0-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7fb0-115">惠?</span><span class="sxs-lookup"><span data-stu-id="a7fb0-115">Requirements</span></span>  
 <span data-ttu-id="a7fb0-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a7fb0-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7fb0-117">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="a7fb0-117">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="a7fb0-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7fb0-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7fb0-119">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7fb0-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7fb0-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7fb0-120">See Also</span></span>  
 [<span data-ttu-id="a7fb0-121">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="a7fb0-121">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 [<span data-ttu-id="a7fb0-122">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="a7fb0-122">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 [<span data-ttu-id="a7fb0-123">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a7fb0-123">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="a7fb0-124">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a7fb0-124">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="a7fb0-125">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a7fb0-125">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="a7fb0-126">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="a7fb0-126">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)  
 [<span data-ttu-id="a7fb0-127">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a7fb0-127">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)  
 [<span data-ttu-id="a7fb0-128">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="a7fb0-128">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [<span data-ttu-id="a7fb0-129">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="a7fb0-129">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)  
 [<span data-ttu-id="a7fb0-130">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="a7fb0-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
