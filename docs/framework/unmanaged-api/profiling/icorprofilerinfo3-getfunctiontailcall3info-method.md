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
ms.openlocfilehash: add89fe81fccbd5e6f5ad5d27f0ab3ace489963e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868520"
---
# <a name="icorprofilerinfo3getfunctiontailcall3info-method"></a><span data-ttu-id="79a95-102">ICorProfilerInfo3::GetFunctionTailcall3Info 方法</span><span class="sxs-lookup"><span data-stu-id="79a95-102">ICorProfilerInfo3::GetFunctionTailcall3Info Method</span></span>
<span data-ttu-id="79a95-103">提供由[FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)函数向探查器报告的函数的堆栈帧。</span><span class="sxs-lookup"><span data-stu-id="79a95-103">Provides the stack frame of the function that is being reported to the profiler by the [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) function.</span></span> <span data-ttu-id="79a95-104">仅在 `FunctionTailcall3WithInfo` 回调时可调用此方法。</span><span class="sxs-lookup"><span data-stu-id="79a95-104">This method can be called only during the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79a95-105">语法</span><span class="sxs-lookup"><span data-stu-id="79a95-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionTailcall3Info(   
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79a95-106">参数</span><span class="sxs-lookup"><span data-stu-id="79a95-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="79a95-107">中返回的函数的 `FunctionID`。</span><span class="sxs-lookup"><span data-stu-id="79a95-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="79a95-108">[in] 表示有关给定堆栈帧的信息的不透明的句柄。</span><span class="sxs-lookup"><span data-stu-id="79a95-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="79a95-109">探查器应提供 `FunctionTailcall3WithInfo` 函数为探查器提供的相同 `eltInfo`。</span><span class="sxs-lookup"><span data-stu-id="79a95-109">The profiler should provide the same `eltInfo` that was given to the profiler by the `FunctionTailcall3WithInfo` function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="79a95-110">[out] 表示有关给定堆栈帧的泛型信息的不透明的句柄。</span><span class="sxs-lookup"><span data-stu-id="79a95-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="79a95-111">此句柄仅在探查器调用 `GetFunctionTailcall3Info` 方法的 `FunctionTailcall3WithInfo` 回调时有效。</span><span class="sxs-lookup"><span data-stu-id="79a95-111">This handle is valid only during the `FunctionTailcall3WithInfo` callback in which the profiler called the `GetFunctionTailcall3Info` method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79a95-112">备注</span><span class="sxs-lookup"><span data-stu-id="79a95-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79a95-113">需求</span><span class="sxs-lookup"><span data-stu-id="79a95-113">Requirements</span></span>  
 <span data-ttu-id="79a95-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="79a95-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79a95-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="79a95-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="79a95-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79a95-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79a95-117">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79a95-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79a95-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79a95-118">See also</span></span>

- [<span data-ttu-id="79a95-119">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="79a95-119">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="79a95-120">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="79a95-120">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="79a95-121">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="79a95-121">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="79a95-122">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="79a95-122">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="79a95-123">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="79a95-123">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="79a95-124">分析</span><span class="sxs-lookup"><span data-stu-id="79a95-124">Profiling</span></span>](index.md)
