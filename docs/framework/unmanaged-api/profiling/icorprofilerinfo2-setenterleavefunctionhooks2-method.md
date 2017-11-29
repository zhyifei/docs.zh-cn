---
title: "ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.SetEnterLeaveFunctionHooks2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::SetEnterLeaveFunctionHooks2
helpviewer_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
- SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
ms.assetid: 3c26b3e7-f72b-48a5-bf8c-edc122523a4b
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bea9be4db2730a67485ef9a504bbc69c096e76c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a><span data-ttu-id="5c978-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 方法</span><span class="sxs-lookup"><span data-stu-id="5c978-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 Method</span></span>
<span data-ttu-id="5c978-103">指定要在"输入"、"保留"和"tailcall"挂钩托管函数的更新版本上调用的探查器实现的函数。</span><span class="sxs-lookup"><span data-stu-id="5c978-103">Specifies profiler-implemented functions to be called on the updated versions of the "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c978-104">语法</span><span class="sxs-lookup"><span data-stu-id="5c978-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5c978-105">参数</span><span class="sxs-lookup"><span data-stu-id="5c978-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="5c978-106">[in]指向要用作的实现的[FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)回调。</span><span class="sxs-lookup"><span data-stu-id="5c978-106">[in] A pointer to the implementation to be used as the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="5c978-107">[in]指向要用作的实现的[FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)回调。</span><span class="sxs-lookup"><span data-stu-id="5c978-107">[in] A pointer to the implementation to be used as the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="5c978-108">[in]指向要用作的实现的[FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)回调。</span><span class="sxs-lookup"><span data-stu-id="5c978-108">[in] A pointer to the implementation to be used as the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c978-109">备注</span><span class="sxs-lookup"><span data-stu-id="5c978-109">Remarks</span></span>  
 <span data-ttu-id="5c978-110">`SetEnterLeaveFunctionHooks2`方法类似于是[icorprofilerinfo:: Setenterleavefunctionhooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5c978-110">The `SetEnterLeaveFunctionHooks2` method is similar to the [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) method.</span></span> <span data-ttu-id="5c978-111">前者用于指定要用作较新版本的 enter/保留/tailcall 回调，而后者来指定要用作 enter/保留/tailcall 回调的较旧版本的函数的函数。</span><span class="sxs-lookup"><span data-stu-id="5c978-111">Use the former to specify functions to be used as the newer versions of the enter/leave/tailcall callbacks, and the latter to specify functions to be used as the older versions of the enter/leave/tailcall callbacks.</span></span>  
  
 <span data-ttu-id="5c978-112">一次，只有一组回调可能处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="5c978-112">Only one set of callbacks may be active at a time.</span></span> <span data-ttu-id="5c978-113">因此，如果探查器同时调用`ICorProfilerInfo::SetEnterLeaveFunctionHooks`和`SetEnterLeaveFunctionHooks2`，`SetEnterLeaveFunctionHooks2`使用。</span><span class="sxs-lookup"><span data-stu-id="5c978-113">Thus, if a profiler calls both `ICorProfilerInfo::SetEnterLeaveFunctionHooks` and `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` is used.</span></span>  
  
 <span data-ttu-id="5c978-114">`SetEnterLeaveFunctionHooks2`可能仅从探查器的调用方法[icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="5c978-114">The `SetEnterLeaveFunctionHooks2` method may be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c978-115">要求</span><span class="sxs-lookup"><span data-stu-id="5c978-115">Requirements</span></span>  
 <span data-ttu-id="5c978-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5c978-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c978-117">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5c978-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5c978-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c978-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c978-119">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c978-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c978-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c978-120">See Also</span></span>  
 [<span data-ttu-id="5c978-121">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="5c978-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="5c978-122">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="5c978-122">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
