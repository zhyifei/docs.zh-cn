---
title: "ICorProfilerCallback::JITCachedFunctionSearchFinished 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITCachedFunctionSearchFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITCachedFunctionSearchFinished
helpviewer_keywords:
- JITCachedFunctionSearchFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchFinished method [.NET Framework profiling]
ms.assetid: 3c325c82-cddd-4b00-b3da-e450c36abf62
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 830d790426dd53de100784f585a6733e278a9569
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackjitcachedfunctionsearchfinished-method"></a><span data-ttu-id="ff0fe-102">ICorProfilerCallback::JITCachedFunctionSearchFinished 方法</span><span class="sxs-lookup"><span data-stu-id="ff0fe-102">ICorProfilerCallback::JITCachedFunctionSearchFinished Method</span></span>
<span data-ttu-id="ff0fe-103">通知探查器搜索已完成以前使用本机映像生成器 (NGen.exe) 编译的函数。</span><span class="sxs-lookup"><span data-stu-id="ff0fe-103">Notifies the profiler that a search has finished for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff0fe-104">语法</span><span class="sxs-lookup"><span data-stu-id="ff0fe-104">Syntax</span></span>  
  
```  
HRESULT JITCachedFunctionSearchFinished(  
    [in] FunctionID        functionId,  
    [in] COR_PRF_JIT_CACHE result);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff0fe-105">参数</span><span class="sxs-lookup"><span data-stu-id="ff0fe-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="ff0fe-106">[in]为其执行搜索的函数 ID。</span><span class="sxs-lookup"><span data-stu-id="ff0fe-106">[in] The ID of the function for which the search was performed.</span></span>  
  
 `result`  
 <span data-ttu-id="ff0fe-107">[in]值为[COR_PRF_JIT_CACHE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md)枚举，指示搜索结果。</span><span class="sxs-lookup"><span data-stu-id="ff0fe-107">[in] A value of the [COR_PRF_JIT_CACHE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md) enumeration that indicates the result of the search.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff0fe-108">备注</span><span class="sxs-lookup"><span data-stu-id="ff0fe-108">Remarks</span></span>  
 <span data-ttu-id="ff0fe-109">在.NET Framework 2.0 版中， [icorprofilercallback:: Jitcachedfunctionsearchstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md)和`JITCachedFunctionSearchFinished`回调将不会执行常规 NGen 映像中的所有功能。</span><span class="sxs-lookup"><span data-stu-id="ff0fe-109">In the .NET Framework version 2.0, the [ICorProfilerCallback::JITCachedFunctionSearchStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md) and `JITCachedFunctionSearchFinished` callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="ff0fe-110">仅针对探查器进行了优化的 NGen 映像将映像中生成的所有函数的回调。</span><span class="sxs-lookup"><span data-stu-id="ff0fe-110">Only NGen images optimized for a profiler will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="ff0fe-111">但是，由于的额外开销，探查器应请求探查器优化 NGen 映像仅当它想使用这些回调来强制对函数进行编译的实时 (JIT)。</span><span class="sxs-lookup"><span data-stu-id="ff0fe-111">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="ff0fe-112">否则，探查器应使用迟缓策略来收集函数信息。</span><span class="sxs-lookup"><span data-stu-id="ff0fe-112">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff0fe-113">惠?</span><span class="sxs-lookup"><span data-stu-id="ff0fe-113">Requirements</span></span>  
 <span data-ttu-id="ff0fe-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ff0fe-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff0fe-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ff0fe-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ff0fe-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff0fe-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff0fe-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff0fe-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff0fe-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff0fe-118">See Also</span></span>  
 [<span data-ttu-id="ff0fe-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="ff0fe-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
