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
ms.openlocfilehash: e7a25fce945504cff0d07f499ae4bb79378e9f3a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449699"
---
# <a name="icorprofilerinfo3getfunctiontailcall3info-method"></a><span data-ttu-id="f441c-102">ICorProfilerInfo3::GetFunctionTailcall3Info 方法</span><span class="sxs-lookup"><span data-stu-id="f441c-102">ICorProfilerInfo3::GetFunctionTailcall3Info Method</span></span>
<span data-ttu-id="f441c-103">提供由[FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)函数向探查器报告的函数的堆栈帧。</span><span class="sxs-lookup"><span data-stu-id="f441c-103">Provides the stack frame of the function that is being reported to the profiler by the [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) function.</span></span> <span data-ttu-id="f441c-104">仅在 `FunctionTailcall3WithInfo` 回调时可调用此方法。</span><span class="sxs-lookup"><span data-stu-id="f441c-104">This method can be called only during the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f441c-105">语法</span><span class="sxs-lookup"><span data-stu-id="f441c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionTailcall3Info(   
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f441c-106">参数</span><span class="sxs-lookup"><span data-stu-id="f441c-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="f441c-107">中返回的函数的 `FunctionID`。</span><span class="sxs-lookup"><span data-stu-id="f441c-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="f441c-108">[in] 表示有关给定堆栈帧的信息的不透明的句柄。</span><span class="sxs-lookup"><span data-stu-id="f441c-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="f441c-109">探查器应提供 `FunctionTailcall3WithInfo` 函数为探查器提供的相同 `eltInfo`。</span><span class="sxs-lookup"><span data-stu-id="f441c-109">The profiler should provide the same `eltInfo` that was given to the profiler by the `FunctionTailcall3WithInfo` function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="f441c-110">[out] 表示有关给定堆栈帧的泛型信息的不透明的句柄。</span><span class="sxs-lookup"><span data-stu-id="f441c-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="f441c-111">此句柄仅在探查器调用 `FunctionTailcall3WithInfo` 方法的 `GetFunctionTailcall3Info` 回调时有效。</span><span class="sxs-lookup"><span data-stu-id="f441c-111">This handle is valid only during the `FunctionTailcall3WithInfo` callback in which the profiler called the `GetFunctionTailcall3Info` method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f441c-112">备注</span><span class="sxs-lookup"><span data-stu-id="f441c-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f441c-113">要求</span><span class="sxs-lookup"><span data-stu-id="f441c-113">Requirements</span></span>  
 <span data-ttu-id="f441c-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f441c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f441c-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f441c-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f441c-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f441c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f441c-117">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f441c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f441c-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f441c-118">See also</span></span>

- [<span data-ttu-id="f441c-119">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f441c-119">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="f441c-120">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f441c-120">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="f441c-121">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f441c-121">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="f441c-122">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="f441c-122">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="f441c-123">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="f441c-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="f441c-124">分析</span><span class="sxs-lookup"><span data-stu-id="f441c-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
