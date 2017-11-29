---
title: "FunctionIDMapper2 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionIDMapper2
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionIDMapper2
helpviewer_keywords: FunctionIDMapper2 function [.NET Framework profiling]
ms.assetid: 466ad51b-8f0c-41d9-81f7-371aac3374cb
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5da0acdd7622ad06879b57d8d4b2a9faeba10ca9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="functionidmapper2-function"></a><span data-ttu-id="2d09c-102">FunctionIDMapper2 函数</span><span class="sxs-lookup"><span data-stu-id="2d09c-102">FunctionIDMapper2 Function</span></span>
<span data-ttu-id="2d09c-103">通知探查器函数的给定的标识符可能被重新映射到要在中使用的备用 ID [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)， [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)，和[FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)，或[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)， [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)，和[FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)该函数的回调。</span><span class="sxs-lookup"><span data-stu-id="2d09c-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md), or[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) callbacks for that function.</span></span> <span data-ttu-id="2d09c-104">`FunctionIDMapper2` 此外还要使探查器指示它是否想要接收该函数的回调。</span><span class="sxs-lookup"><span data-stu-id="2d09c-104">`FunctionIDMapper2` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d09c-105">语法</span><span class="sxs-lookup"><span data-stu-id="2d09c-105">Syntax</span></span>  
  
```  
UINT_PTR __stdcall FunctionIDMapper2 (  
    [in]  FunctionID  funcId,  
    [in]  void * clientData,  
    [out] BOOL       *pbHookFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2d09c-106">参数</span><span class="sxs-lookup"><span data-stu-id="2d09c-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="2d09c-107">[in] 要重新映射的函数标识符。</span><span class="sxs-lookup"><span data-stu-id="2d09c-107">[in] The function identifier to be remapped.</span></span>  
  
 `clientData`  
 <span data-ttu-id="2d09c-108">[in] 指向用于消除运行时之间歧义的数据的指针。</span><span class="sxs-lookup"><span data-stu-id="2d09c-108">[in] A pointer to data that is used to disambiguate among runtimes.</span></span>  
  
 `pbHookFunction`  
 <span data-ttu-id="2d09c-109">[out] 指向一个值的指针，如果探查器想要接收 `FunctionEnter3`、`FunctionLeave3`和 `FunctionTailcall3` 或 `FunctionEnter3WithInfo`、`FunctionLeave3WithInfo` 和 `FunctionTailcall3WithInfo` 回调而将该值设置为 `true`； 否则，它会将此值设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="2d09c-109">[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter3`, `FunctionLeave3`, and `FunctionTailcall3`, or `FunctionEnter3WithInfo`, `FunctionLeave3WithInfo`, and `FunctionTailcall3WithInfo` callbacks; otherwise, it sets this value to `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d09c-110">返回值</span><span class="sxs-lookup"><span data-stu-id="2d09c-110">Return Value</span></span>  
 <span data-ttu-id="2d09c-111">探查器返回一个执行引擎用作替代函数标识符的值。</span><span class="sxs-lookup"><span data-stu-id="2d09c-111">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="2d09c-112">返回值不能为 null，除非在 `pbHookFunction` 中返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="2d09c-112">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="2d09c-113">否则为 null 的返回值将产生不可预知的结果，包括可能停止该过程。</span><span class="sxs-lookup"><span data-stu-id="2d09c-113">Otherwise, a null return value produces unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d09c-114">备注</span><span class="sxs-lookup"><span data-stu-id="2d09c-114">Remarks</span></span>  
 <span data-ttu-id="2d09c-115">此方法扩展[FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)用于传递客户端数据的其他参数的函数。</span><span class="sxs-lookup"><span data-stu-id="2d09c-115">This method extends the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function with an additional parameter that is used to pass client data.</span></span> <span data-ttu-id="2d09c-116">客户端数据用于消除运行时之间的歧义。</span><span class="sxs-lookup"><span data-stu-id="2d09c-116">The client data is used to disambiguate among runtimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d09c-117">要求</span><span class="sxs-lookup"><span data-stu-id="2d09c-117">Requirements</span></span>  
 <span data-ttu-id="2d09c-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2d09c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d09c-119">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="2d09c-119">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="2d09c-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d09c-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d09c-121">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d09c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d09c-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d09c-122">See Also</span></span>  
 [<span data-ttu-id="2d09c-123">Icorprofilerinfo:: Setfunctionidmapper</span><span class="sxs-lookup"><span data-stu-id="2d09c-123">ICorProfilerInfo::SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [<span data-ttu-id="2d09c-124">Icorprofilerinfo3:: Setfunctionidmapper2</span><span class="sxs-lookup"><span data-stu-id="2d09c-124">ICorProfilerInfo3::SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)  
 [<span data-ttu-id="2d09c-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="2d09c-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 [<span data-ttu-id="2d09c-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="2d09c-126">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 [<span data-ttu-id="2d09c-127">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="2d09c-127">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 [<span data-ttu-id="2d09c-128">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="2d09c-128">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="2d09c-129">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="2d09c-129">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="2d09c-130">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="2d09c-130">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="2d09c-131">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="2d09c-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
