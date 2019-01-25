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
ms.openlocfilehash: 71bde7534e391872fe85c2a22142cbc3dc2725e2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680943"
---
# <a name="functionidmapper2-function"></a><span data-ttu-id="c622a-102">FunctionIDMapper2 函数</span><span class="sxs-lookup"><span data-stu-id="c622a-102">FunctionIDMapper2 Function</span></span>
<span data-ttu-id="c622a-103">通知探查器函数的给定的标识符可能被重新映射到要在中使用的备用 ID [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)， [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)，和[FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)，或[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)， [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)，并且[FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)该函数的回调。</span><span class="sxs-lookup"><span data-stu-id="c622a-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md), or[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) callbacks for that function.</span></span> <span data-ttu-id="c622a-104">`FunctionIDMapper2` 此外还要使探查器指示它是否想要接收该函数的回调。</span><span class="sxs-lookup"><span data-stu-id="c622a-104">`FunctionIDMapper2` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c622a-105">语法</span><span class="sxs-lookup"><span data-stu-id="c622a-105">Syntax</span></span>  
  
```  
UINT_PTR __stdcall FunctionIDMapper2 (  
    [in]  FunctionID  funcId,  
    [in]  void * clientData,  
    [out] BOOL       *pbHookFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c622a-106">参数</span><span class="sxs-lookup"><span data-stu-id="c622a-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="c622a-107">[in] 要重新映射的函数标识符。</span><span class="sxs-lookup"><span data-stu-id="c622a-107">[in] The function identifier to be remapped.</span></span>  
  
 `clientData`  
 <span data-ttu-id="c622a-108">[in] 指向用于消除运行时之间歧义的数据的指针。</span><span class="sxs-lookup"><span data-stu-id="c622a-108">[in] A pointer to data that is used to disambiguate among runtimes.</span></span>  
  
 `pbHookFunction`  
 <span data-ttu-id="c622a-109">[out] 指向一个值的指针，如果探查器想要接收 `FunctionEnter3`、`FunctionLeave3`和 `FunctionTailcall3` 或 `FunctionEnter3WithInfo`、`FunctionLeave3WithInfo` 和 `FunctionTailcall3WithInfo` 回调而将该值设置为 `true`； 否则，它会将此值设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="c622a-109">[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter3`, `FunctionLeave3`, and `FunctionTailcall3`, or `FunctionEnter3WithInfo`, `FunctionLeave3WithInfo`, and `FunctionTailcall3WithInfo` callbacks; otherwise, it sets this value to `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c622a-110">返回值</span><span class="sxs-lookup"><span data-stu-id="c622a-110">Return Value</span></span>  
 <span data-ttu-id="c622a-111">探查器返回一个执行引擎用作替代函数标识符的值。</span><span class="sxs-lookup"><span data-stu-id="c622a-111">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="c622a-112">返回值不能为 null，除非在 `pbHookFunction` 中返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="c622a-112">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="c622a-113">否则为 null 的返回值将产生不可预知的结果，包括可能停止该过程。</span><span class="sxs-lookup"><span data-stu-id="c622a-113">Otherwise, a null return value produces unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c622a-114">备注</span><span class="sxs-lookup"><span data-stu-id="c622a-114">Remarks</span></span>  
 <span data-ttu-id="c622a-115">此方法扩展[FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)用于传递客户端数据的其他参数的函数。</span><span class="sxs-lookup"><span data-stu-id="c622a-115">This method extends the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function with an additional parameter that is used to pass client data.</span></span> <span data-ttu-id="c622a-116">客户端数据用于消除运行时之间的歧义。</span><span class="sxs-lookup"><span data-stu-id="c622a-116">The client data is used to disambiguate among runtimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c622a-117">要求</span><span class="sxs-lookup"><span data-stu-id="c622a-117">Requirements</span></span>  
 <span data-ttu-id="c622a-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c622a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c622a-119">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="c622a-119">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="c622a-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c622a-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c622a-121">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c622a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c622a-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="c622a-122">See also</span></span>
- [<span data-ttu-id="c622a-123">ICorProfilerInfo::SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="c622a-123">ICorProfilerInfo::SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="c622a-124">ICorProfilerInfo3::SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="c622a-124">ICorProfilerInfo3::SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="c622a-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="c622a-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="c622a-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="c622a-126">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="c622a-127">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="c622a-127">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="c622a-128">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="c622a-128">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="c622a-129">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="c622a-129">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="c622a-130">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="c622a-130">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="c622a-131">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="c622a-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
