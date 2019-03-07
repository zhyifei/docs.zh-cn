---
title: ICorProfilerInfo3::GetFunctionTailcall3Info 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionTailcall3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info
helpviewer_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info method [.NET Framework profiling]
- GetFunctionTailcall3Info method [.NET Framework profiling]
ms.assetid: afdb5ac9-5bf5-4b91-b7cb-f81db23d7da3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b3d5d3808f51f921bd3e0c94942a1fb07a35d876
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487806"
---
# <a name="icorprofilerinfo3getfunctiontailcall3info-method"></a><span data-ttu-id="97b61-102">ICorProfilerInfo3::GetFunctionTailcall3Info 方法</span><span class="sxs-lookup"><span data-stu-id="97b61-102">ICorProfilerInfo3::GetFunctionTailcall3Info Method</span></span>
<span data-ttu-id="97b61-103">提供了正在向探查器报告的函数的堆栈帧[FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="97b61-103">Provides the stack frame of the function that is being reported to the profiler by the [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) function.</span></span> <span data-ttu-id="97b61-104">仅在 `FunctionTailcall3WithInfo` 回调时可调用此方法。</span><span class="sxs-lookup"><span data-stu-id="97b61-104">This method can be called only during the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97b61-105">语法</span><span class="sxs-lookup"><span data-stu-id="97b61-105">Syntax</span></span>  
  
```  
HRESULT GetFunctionTailcall3Info(   
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97b61-106">参数</span><span class="sxs-lookup"><span data-stu-id="97b61-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="97b61-107">[in]`FunctionID`返回的函数。</span><span class="sxs-lookup"><span data-stu-id="97b61-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="97b61-108">[in] 表示有关给定堆栈帧的信息的不透明的句柄。</span><span class="sxs-lookup"><span data-stu-id="97b61-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="97b61-109">探查器应提供相同`eltInfo`，提供给探查器`FunctionTailcall3WithInfo`函数。</span><span class="sxs-lookup"><span data-stu-id="97b61-109">The profiler should provide the same `eltInfo` that was given to the profiler by the `FunctionTailcall3WithInfo` function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="97b61-110">[out] 表示有关给定堆栈帧的泛型信息的不透明的句柄。</span><span class="sxs-lookup"><span data-stu-id="97b61-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="97b61-111">此句柄仅在探查器调用 `GetFunctionTailcall3Info` 方法的 `FunctionTailcall3WithInfo` 回调时有效。</span><span class="sxs-lookup"><span data-stu-id="97b61-111">This handle is valid only during the `FunctionTailcall3WithInfo` callback in which the profiler called the `GetFunctionTailcall3Info` method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97b61-112">备注</span><span class="sxs-lookup"><span data-stu-id="97b61-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97b61-113">要求</span><span class="sxs-lookup"><span data-stu-id="97b61-113">Requirements</span></span>  
 <span data-ttu-id="97b61-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="97b61-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97b61-115">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="97b61-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="97b61-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97b61-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97b61-117">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97b61-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97b61-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="97b61-118">See also</span></span>
- [<span data-ttu-id="97b61-119">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="97b61-119">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="97b61-120">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="97b61-120">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="97b61-121">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="97b61-121">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="97b61-122">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="97b61-122">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="97b61-123">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="97b61-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="97b61-124">分析</span><span class="sxs-lookup"><span data-stu-id="97b61-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
