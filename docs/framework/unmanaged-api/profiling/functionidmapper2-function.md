---
title: FunctionIDMapper2 函数
ms.date: 03/30/2017
api_name:
- FunctionIDMapper2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper2
helpviewer_keywords:
- FunctionIDMapper2 function [.NET Framework profiling]
ms.assetid: 466ad51b-8f0c-41d9-81f7-371aac3374cb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1a236dcae29d00afe3b72dce8f81d657fb4fac28
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598917"
---
# <a name="functionidmapper2-function"></a><span data-ttu-id="9e70b-102">FunctionIDMapper2 函数</span><span class="sxs-lookup"><span data-stu-id="9e70b-102">FunctionIDMapper2 Function</span></span>
<span data-ttu-id="9e70b-103">通知探查器函数的给定的标识符可能被重新映射到要在中使用的备用 ID [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)， [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)，和[FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)，或[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)， [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)，并且[FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)该函数的回调。</span><span class="sxs-lookup"><span data-stu-id="9e70b-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md), or[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) callbacks for that function.</span></span> <span data-ttu-id="9e70b-104">`FunctionIDMapper2` 此外还要使探查器指示它是否想要接收该函数的回调。</span><span class="sxs-lookup"><span data-stu-id="9e70b-104">`FunctionIDMapper2` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e70b-105">语法</span><span class="sxs-lookup"><span data-stu-id="9e70b-105">Syntax</span></span>  
  
```  
UINT_PTR __stdcall FunctionIDMapper2 (  
    [in]  FunctionID  funcId,  
    [in]  void * clientData,  
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e70b-106">参数</span><span class="sxs-lookup"><span data-stu-id="9e70b-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="9e70b-107">[in] 要重新映射的函数标识符。</span><span class="sxs-lookup"><span data-stu-id="9e70b-107">[in] The function identifier to be remapped.</span></span>  
  
 `clientData`  
 <span data-ttu-id="9e70b-108">[in] 指向用于消除运行时之间歧义的数据的指针。</span><span class="sxs-lookup"><span data-stu-id="9e70b-108">[in] A pointer to data that is used to disambiguate among runtimes.</span></span>  
  
 `pbHookFunction`  
 <span data-ttu-id="9e70b-109">[out] 指向一个值的指针，如果探查器想要接收 `FunctionEnter3`、`FunctionLeave3`和 `FunctionTailcall3` 或 `FunctionEnter3WithInfo`、`FunctionLeave3WithInfo` 和 `FunctionTailcall3WithInfo` 回调而将该值设置为 `true`； 否则，它会将此值设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="9e70b-109">[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter3`, `FunctionLeave3`, and `FunctionTailcall3`, or `FunctionEnter3WithInfo`, `FunctionLeave3WithInfo`, and `FunctionTailcall3WithInfo` callbacks; otherwise, it sets this value to `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e70b-110">返回值</span><span class="sxs-lookup"><span data-stu-id="9e70b-110">Return Value</span></span>  
 <span data-ttu-id="9e70b-111">探查器返回一个执行引擎用作替代函数标识符的值。</span><span class="sxs-lookup"><span data-stu-id="9e70b-111">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="9e70b-112">返回值不能为 null，除非在 `pbHookFunction` 中返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="9e70b-112">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="9e70b-113">否则为 null 的返回值将产生不可预知的结果，包括可能停止该过程。</span><span class="sxs-lookup"><span data-stu-id="9e70b-113">Otherwise, a null return value produces unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e70b-114">备注</span><span class="sxs-lookup"><span data-stu-id="9e70b-114">Remarks</span></span>  
 <span data-ttu-id="9e70b-115">此方法扩展[FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)用于传递客户端数据的其他参数的函数。</span><span class="sxs-lookup"><span data-stu-id="9e70b-115">This method extends the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function with an additional parameter that is used to pass client data.</span></span> <span data-ttu-id="9e70b-116">客户端数据用于消除运行时之间的歧义。</span><span class="sxs-lookup"><span data-stu-id="9e70b-116">The client data is used to disambiguate among runtimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e70b-117">要求</span><span class="sxs-lookup"><span data-stu-id="9e70b-117">Requirements</span></span>  
 <span data-ttu-id="9e70b-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9e70b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e70b-119">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="9e70b-119">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="9e70b-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e70b-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e70b-121">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e70b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e70b-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e70b-122">See also</span></span>

- [<span data-ttu-id="9e70b-123">ICorProfilerInfo::SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="9e70b-123">ICorProfilerInfo::SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="9e70b-124">ICorProfilerInfo3::SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="9e70b-124">ICorProfilerInfo3::SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="9e70b-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="9e70b-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="9e70b-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="9e70b-126">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="9e70b-127">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="9e70b-127">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="9e70b-128">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="9e70b-128">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="9e70b-129">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="9e70b-129">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="9e70b-130">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="9e70b-130">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="9e70b-131">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="9e70b-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
