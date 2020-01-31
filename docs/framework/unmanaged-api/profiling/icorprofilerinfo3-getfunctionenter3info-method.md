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
ms.openlocfilehash: 55411f187e2ef73997633d94b37a7d5d2cfd74c9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868559"
---
# <a name="icorprofilerinfo3getfunctionenter3info-method"></a><span data-ttu-id="75163-102">ICorProfilerInfo3::GetFunctionEnter3Info 方法</span><span class="sxs-lookup"><span data-stu-id="75163-102">ICorProfilerInfo3::GetFunctionEnter3Info Method</span></span>
<span data-ttu-id="75163-103">提供由[FunctionEnter3WithInfo](functionenter3withinfo-function.md)函数向探查器报告的函数的堆栈帧和参数信息。</span><span class="sxs-lookup"><span data-stu-id="75163-103">Provides the stack frame and argument information of the function that is being reported to the profiler by the [FunctionEnter3WithInfo](functionenter3withinfo-function.md) function.</span></span> <span data-ttu-id="75163-104">仅在 `FunctionEnter3WithInfo` 回调时可调用此方法。</span><span class="sxs-lookup"><span data-stu-id="75163-104">This method can be called only during the `FunctionEnter3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75163-105">语法</span><span class="sxs-lookup"><span data-stu-id="75163-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionEnter3Info(  
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [in, out] ULONG *pcbArgumentInfo,  
            [out, size_is(*pcbArgumentInfo)]  
                  COR_PRF_FUNCTION_ARGUMENT_INFO *pArgumentInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75163-106">参数</span><span class="sxs-lookup"><span data-stu-id="75163-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="75163-107">[in] 正在输入的函数的 `FunctionID`。</span><span class="sxs-lookup"><span data-stu-id="75163-107">[in] The `FunctionID` of the function that is being entered.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="75163-108">[in] 表示有关给定堆栈帧的信息的不透明的句柄。</span><span class="sxs-lookup"><span data-stu-id="75163-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="75163-109">探查器应提供[FunctionEnter3WithInfo](functionenter3withinfo-function.md)函数所提供的相同 `eltInfo`。</span><span class="sxs-lookup"><span data-stu-id="75163-109">The profiler should provide the same `eltInfo` that it was given by the [FunctionEnter3WithInfo](functionenter3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="75163-110">[out] 表示有关给定堆栈帧的泛型信息的不透明的句柄。</span><span class="sxs-lookup"><span data-stu-id="75163-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="75163-111">此句柄仅在探查器调用 `GetFunctionEnter3Info` 方法的 `FunctionEnter3WithInfo` 回调时有效。</span><span class="sxs-lookup"><span data-stu-id="75163-111">This handle is valid only during the `FunctionEnter3WithInfo` callback in which the profiler called the `GetFunctionEnter3Info` method.</span></span>  
  
 `pcbArgumentInfo`  
 <span data-ttu-id="75163-112">[in，out]一个指针，它指向[COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md)结构的总大小（以字节为单位）（以及 `pArgumentInfo`所指向的参数范围的任何其他[COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md)结构）。</span><span class="sxs-lookup"><span data-stu-id="75163-112">[in, out] A pointer to the total size, in bytes, of the [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure (plus any additional [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structures for the argument ranges pointed to by `pArgumentInfo`).</span></span> <span data-ttu-id="75163-113">如果指定的大小不足，将返回 ERROR_INSUFFICIENT_BUFFER，并将预期大小存储在 `pcbArgumentInfo` 中。</span><span class="sxs-lookup"><span data-stu-id="75163-113">If the specified size is not enough, ERROR_INSUFFICIENT_BUFFER is returned and the expected size is stored in `pcbArgumentInfo`.</span></span> <span data-ttu-id="75163-114">若仅为检索 `*pcbArgumentInfo` 的预期值而调用 `GetFunctionEnter3Info`，请设置 `*pcbArgumentInfo`=0 和 `pArgumentInfo`=NULL。</span><span class="sxs-lookup"><span data-stu-id="75163-114">To call `GetFunctionEnter3Info` just to retrieve the expected value for `*pcbArgumentInfo`, set `*pcbArgumentInfo`=0 and `pArgumentInfo`=NULL.</span></span>  
  
 `pArgumentInfo`  
 <span data-ttu-id="75163-115">弄指向[COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md)结构的指针，该结构以从左到右的顺序描述函数参数在内存中的位置。</span><span class="sxs-lookup"><span data-stu-id="75163-115">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure that describes the locations of the function's arguments in memory, in left-to-right order.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75163-116">备注</span><span class="sxs-lookup"><span data-stu-id="75163-116">Remarks</span></span>  
 <span data-ttu-id="75163-117">探查器必须为将进行检查的函数的 `COR_PRF_FUNCTION_ARGUMENT_INFO` 结构分配足够的空间，并且必须指示 `pcbArgumentInfo` 参数中的大小。</span><span class="sxs-lookup"><span data-stu-id="75163-117">The profiler must allocate sufficient space for the `COR_PRF_FUNCTION_ARGUMENT_INFO` structure of the function that is being inspected, and must indicate the size in the `pcbArgumentInfo` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75163-118">需求</span><span class="sxs-lookup"><span data-stu-id="75163-118">Requirements</span></span>  
 <span data-ttu-id="75163-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="75163-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75163-120">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="75163-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="75163-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75163-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75163-122">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75163-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75163-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75163-123">See also</span></span>

- [<span data-ttu-id="75163-124">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="75163-124">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="75163-125">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="75163-125">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="75163-126">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="75163-126">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="75163-127">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="75163-127">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="75163-128">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="75163-128">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="75163-129">分析</span><span class="sxs-lookup"><span data-stu-id="75163-129">Profiling</span></span>](index.md)
