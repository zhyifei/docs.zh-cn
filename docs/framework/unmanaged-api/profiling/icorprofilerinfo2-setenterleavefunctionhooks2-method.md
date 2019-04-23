---
title: ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.SetEnterLeaveFunctionHooks2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2
helpviewer_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
- SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
ms.assetid: 3c26b3e7-f72b-48a5-bf8c-edc122523a4b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b9f95a404ce7124a76ee527cdc70ccccf103838b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59076791"
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a><span data-ttu-id="8b3dc-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 方法</span><span class="sxs-lookup"><span data-stu-id="8b3dc-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 Method</span></span>
<span data-ttu-id="8b3dc-103">指定要在"输入"、"保留"和"tailcall"挂钩的托管函数的更新版本上调用的探查器实现的函数。</span><span class="sxs-lookup"><span data-stu-id="8b3dc-103">Specifies profiler-implemented functions to be called on the updated versions of the "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b3dc-104">语法</span><span class="sxs-lookup"><span data-stu-id="8b3dc-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b3dc-105">参数</span><span class="sxs-lookup"><span data-stu-id="8b3dc-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="8b3dc-106">[in]指向实现要用作[FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)回调。</span><span class="sxs-lookup"><span data-stu-id="8b3dc-106">[in] A pointer to the implementation to be used as the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="8b3dc-107">[in]指向实现要用作[FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)回调。</span><span class="sxs-lookup"><span data-stu-id="8b3dc-107">[in] A pointer to the implementation to be used as the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="8b3dc-108">[in]指向实现要用作[FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)回调。</span><span class="sxs-lookup"><span data-stu-id="8b3dc-108">[in] A pointer to the implementation to be used as the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b3dc-109">备注</span><span class="sxs-lookup"><span data-stu-id="8b3dc-109">Remarks</span></span>  
 <span data-ttu-id="8b3dc-110">`SetEnterLeaveFunctionHooks2`方法是类似于[icorprofilerinfo:: Setenterleavefunctionhooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="8b3dc-110">The `SetEnterLeaveFunctionHooks2` method is similar to the [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) method.</span></span> <span data-ttu-id="8b3dc-111">前者用于指定要用作 enter/leave/tailcall 回调，而后者的较新版本可以指定要用作 enter/leave/tailcall 回调的较旧版本的函数的函数。</span><span class="sxs-lookup"><span data-stu-id="8b3dc-111">Use the former to specify functions to be used as the newer versions of the enter/leave/tailcall callbacks, and the latter to specify functions to be used as the older versions of the enter/leave/tailcall callbacks.</span></span>  
  
 <span data-ttu-id="8b3dc-112">只能一次，一组回调可能会处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="8b3dc-112">Only one set of callbacks may be active at a time.</span></span> <span data-ttu-id="8b3dc-113">因此，如果探查器同时调用`ICorProfilerInfo::SetEnterLeaveFunctionHooks`并`SetEnterLeaveFunctionHooks2`，`SetEnterLeaveFunctionHooks2`使用。</span><span class="sxs-lookup"><span data-stu-id="8b3dc-113">Thus, if a profiler calls both `ICorProfilerInfo::SetEnterLeaveFunctionHooks` and `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` is used.</span></span>  
  
 <span data-ttu-id="8b3dc-114">`SetEnterLeaveFunctionHooks2`可能仅从探查器的调用方法[icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="8b3dc-114">The `SetEnterLeaveFunctionHooks2` method may be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b3dc-115">要求</span><span class="sxs-lookup"><span data-stu-id="8b3dc-115">Requirements</span></span>  
 <span data-ttu-id="8b3dc-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8b3dc-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b3dc-117">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8b3dc-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8b3dc-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b3dc-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b3dc-119">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b3dc-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b3dc-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b3dc-120">See also</span></span>

- [<span data-ttu-id="8b3dc-121">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="8b3dc-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="8b3dc-122">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="8b3dc-122">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
