---
title: ICorProfilerInfo3::GetFunctionEnter3Info 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionEnter3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionEnter3Info
helpviewer_keywords:
- GetFunctionEnter3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionEnter3Info method [.NET Framework profiling]
ms.assetid: 542c7c65-dd56-4651-b76f-5db2465e4a15
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8df3700c6002e7a181d4882c4afd8542c6b6c93a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164822"
---
# <a name="icorprofilerinfo3getfunctionenter3info-method"></a><span data-ttu-id="d51b8-102">ICorProfilerInfo3::GetFunctionEnter3Info 方法</span><span class="sxs-lookup"><span data-stu-id="d51b8-102">ICorProfilerInfo3::GetFunctionEnter3Info Method</span></span>
<span data-ttu-id="d51b8-103">提供了正在向探查器报告的函数的堆栈帧和参数信息[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="d51b8-103">Provides the stack frame and argument information of the function that is being reported to the profiler by the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) function.</span></span> <span data-ttu-id="d51b8-104">仅在 `FunctionEnter3WithInfo` 回调时可调用此方法。</span><span class="sxs-lookup"><span data-stu-id="d51b8-104">This method can be called only during the `FunctionEnter3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d51b8-105">语法</span><span class="sxs-lookup"><span data-stu-id="d51b8-105">Syntax</span></span>  
  
```  
HRESULT GetFunctionEnter3Info(  
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [in, out] ULONG *pcbArgumentInfo,  
            [out, size_is(*pcbArgumentInfo)]  
                  COR_PRF_FUNCTION_ARGUMENT_INFO *pArgumentInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d51b8-106">参数</span><span class="sxs-lookup"><span data-stu-id="d51b8-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="d51b8-107">[in] 正在输入的函数的 `FunctionID`。</span><span class="sxs-lookup"><span data-stu-id="d51b8-107">[in] The `FunctionID` of the function that is being entered.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="d51b8-108">[in] 表示有关给定堆栈帧的信息的不透明的句柄。</span><span class="sxs-lookup"><span data-stu-id="d51b8-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="d51b8-109">探查器应提供相同`eltInfo`通过提供[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="d51b8-109">The profiler should provide the same `eltInfo` that it was given by the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="d51b8-110">[out] 表示有关给定堆栈帧的泛型信息的不透明的句柄。</span><span class="sxs-lookup"><span data-stu-id="d51b8-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="d51b8-111">此句柄仅在探查器调用 `GetFunctionEnter3Info` 方法的 `FunctionEnter3WithInfo` 回调时有效。</span><span class="sxs-lookup"><span data-stu-id="d51b8-111">This handle is valid only during the `FunctionEnter3WithInfo` callback in which the profiler called the `GetFunctionEnter3Info` method.</span></span>  
  
 `pcbArgumentInfo`  
 <span data-ttu-id="d51b8-112">[in、 out]总大小 （字节），一个指向的[COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md)结构 (以及任何其他[COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) 由指向该参数范围中的结构`pArgumentInfo`).</span><span class="sxs-lookup"><span data-stu-id="d51b8-112">[in, out] A pointer to the total size, in bytes, of the [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure (plus any additional [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structures for the argument ranges pointed to by `pArgumentInfo`).</span></span> <span data-ttu-id="d51b8-113">如果指定的大小不足，将返回 ERROR_INSUFFICIENT_BUFFER，并将预期大小存储在 `pcbArgumentInfo` 中。</span><span class="sxs-lookup"><span data-stu-id="d51b8-113">If the specified size is not enough, ERROR_INSUFFICIENT_BUFFER is returned and the expected size is stored in `pcbArgumentInfo`.</span></span> <span data-ttu-id="d51b8-114">若仅为检索 `*pcbArgumentInfo` 的预期值而调用 `GetFunctionEnter3Info`，请设置 `*pcbArgumentInfo`=0 和 `pArgumentInfo`=NULL。</span><span class="sxs-lookup"><span data-stu-id="d51b8-114">To call `GetFunctionEnter3Info` just to retrieve the expected value for `*pcbArgumentInfo`, set `*pcbArgumentInfo`=0 and `pArgumentInfo`=NULL.</span></span>  
  
 `pArgumentInfo`  
 <span data-ttu-id="d51b8-115">[out]一个指向[COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md)结构，它描述了在内存中，从左到右的顺序的函数的参数的位置。</span><span class="sxs-lookup"><span data-stu-id="d51b8-115">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure that describes the locations of the function's arguments in memory, in left-to-right order.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d51b8-116">备注</span><span class="sxs-lookup"><span data-stu-id="d51b8-116">Remarks</span></span>  
 <span data-ttu-id="d51b8-117">探查器必须为将进行检查的函数的 `COR_PRF_FUNCTION_ARGUMENT_INFO` 结构分配足够的空间，并且必须指示 `pcbArgumentInfo` 参数中的大小。</span><span class="sxs-lookup"><span data-stu-id="d51b8-117">The profiler must allocate sufficient space for the `COR_PRF_FUNCTION_ARGUMENT_INFO` structure of the function that is being inspected, and must indicate the size in the `pcbArgumentInfo` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d51b8-118">要求</span><span class="sxs-lookup"><span data-stu-id="d51b8-118">Requirements</span></span>  
 <span data-ttu-id="d51b8-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d51b8-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d51b8-120">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d51b8-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d51b8-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d51b8-121">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d51b8-122">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="d51b8-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d51b8-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="d51b8-123">See also</span></span>

- [<span data-ttu-id="d51b8-124">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="d51b8-124">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="d51b8-125">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="d51b8-125">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="d51b8-126">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="d51b8-126">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="d51b8-127">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="d51b8-127">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="d51b8-128">分析接口</span><span class="sxs-lookup"><span data-stu-id="d51b8-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="d51b8-129">分析</span><span class="sxs-lookup"><span data-stu-id="d51b8-129">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
