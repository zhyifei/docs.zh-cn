---
title: "ICorProfilerInfo3::GetFunctionLeave3Info 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.GetFunctionLeave3Info Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::GetFunctionLeave3Info
helpviewer_keywords:
- GetFunctionLeave3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionLeave3Info method [.NET Framework profiling]
ms.assetid: df7083d2-fd43-44c7-9ce5-912c25cef0ff
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 04f48562e1ddc07ad1ae166ec44ac7de8afd4312
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3getfunctionleave3info-method"></a><span data-ttu-id="67da6-102">ICorProfilerInfo3::GetFunctionLeave3Info 方法</span><span class="sxs-lookup"><span data-stu-id="67da6-102">ICorProfilerInfo3::GetFunctionLeave3Info Method</span></span>
<span data-ttu-id="67da6-103">提供的堆栈帧和正在向探查器报告的函数的返回值[FunctionLeave3WithInfo 函数](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="67da6-103">Provides the stack frame and return value of the function that is being reported to the profiler by the [FunctionLeave3WithInfo function](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) function.</span></span> <span data-ttu-id="67da6-104">仅在 `FunctionLeave3WithInfo` 回调时可调用此方法。</span><span class="sxs-lookup"><span data-stu-id="67da6-104">This method can be called only during the `FunctionLeave3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67da6-105">语法</span><span class="sxs-lookup"><span data-stu-id="67da6-105">Syntax</span></span>  
  
```  
HRESULT GetFunctionLeave3Info(  
            [in]  FunctionID functionId,  
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [out] COR_PRF_FUNCTION_ARGUMENT_RANGE *pRetvalRange);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67da6-106">参数</span><span class="sxs-lookup"><span data-stu-id="67da6-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="67da6-107">[in]`FunctionID`返回的函数。</span><span class="sxs-lookup"><span data-stu-id="67da6-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="67da6-108">[in] 表示有关给定堆栈帧的信息的不透明的句柄。</span><span class="sxs-lookup"><span data-stu-id="67da6-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="67da6-109">探查器应提供相同`eltInfo`，提供给探查器[FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="67da6-109">The profiler should provide the same `eltInfo` that was given to the profiler by the [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="67da6-110">[out] 表示有关给定堆栈帧的泛型信息的不透明的句柄。</span><span class="sxs-lookup"><span data-stu-id="67da6-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="67da6-111">此句柄仅在探查器调用 `GetFunctionLeave3Info` 方法的 `FunctionLeave3WithInfo` 回调时有效。</span><span class="sxs-lookup"><span data-stu-id="67da6-111">This handle is valid only during the `FunctionLeave3WithInfo` callback in which the profiler called the `GetFunctionLeave3Info` method.</span></span>  
  
 `pRetvalRange`  
 <span data-ttu-id="67da6-112">[out]指向的指针[COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md)结构，其中包含从函数返回的值。</span><span class="sxs-lookup"><span data-stu-id="67da6-112">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structure that contains the value that is returned from the function.</span></span> <span data-ttu-id="67da6-113">若要访问返回值信息`COR_PRF_ENABLE_FUNCTION_RETVAL`必须设置标志。</span><span class="sxs-lookup"><span data-stu-id="67da6-113">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="67da6-114">探查器可以使用[icorprofilerinfo:: Seteventmask 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)设置事件标志。</span><span class="sxs-lookup"><span data-stu-id="67da6-114">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67da6-115">备注</span><span class="sxs-lookup"><span data-stu-id="67da6-115">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67da6-116">要求</span><span class="sxs-lookup"><span data-stu-id="67da6-116">Requirements</span></span>  
 <span data-ttu-id="67da6-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="67da6-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67da6-118">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="67da6-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="67da6-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67da6-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67da6-120">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67da6-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67da6-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67da6-121">See Also</span></span>  
 [<span data-ttu-id="67da6-122">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="67da6-122">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="67da6-123">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="67da6-123">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="67da6-124">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="67da6-124">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="67da6-125">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="67da6-125">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="67da6-126">分析接口</span><span class="sxs-lookup"><span data-stu-id="67da6-126">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="67da6-127">分析</span><span class="sxs-lookup"><span data-stu-id="67da6-127">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
