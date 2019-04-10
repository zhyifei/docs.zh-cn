---
title: ICorProfilerInfo::SetEnterLeaveFunctionHooks 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEnterLeaveFunctionHooks
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEnterLeaveFunctionHooks
helpviewer_keywords:
- SetEnterLeaveFunctionHooks method [.NET Framework profiling]
- ICorProfilerInfo::SetEnterLeaveFunctionHooks method [.NET Framework profiling]
ms.assetid: 72399636-c219-4ffd-8ac8-39432c9d4641
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a2d45e98f3e7b71375b14c43c4bff4929bc79494
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142527"
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a><span data-ttu-id="aae07-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks 方法</span><span class="sxs-lookup"><span data-stu-id="aae07-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks Method</span></span>
<span data-ttu-id="aae07-103">指定要在"输入"、"保留"和"tailcall"挂钩的托管函数调用的探查器实现的函数。</span><span class="sxs-lookup"><span data-stu-id="aae07-103">Specifies profiler-implemented functions to be called on "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aae07-104">语法</span><span class="sxs-lookup"><span data-stu-id="aae07-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aae07-105">参数</span><span class="sxs-lookup"><span data-stu-id="aae07-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="aae07-106">[in]指向实现要用作[FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md)回调。</span><span class="sxs-lookup"><span data-stu-id="aae07-106">[in] A pointer to the implementation to be used as the [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="aae07-107">[in]指向实现要用作[FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md)回调。</span><span class="sxs-lookup"><span data-stu-id="aae07-107">[in] A pointer to the implementation to be used as the [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="aae07-108">[in]指向实现要用作[FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md)回调。</span><span class="sxs-lookup"><span data-stu-id="aae07-108">[in] A pointer to the implementation to be used as the [FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aae07-109">备注</span><span class="sxs-lookup"><span data-stu-id="aae07-109">Remarks</span></span>  
 <span data-ttu-id="aae07-110">在.NET Framework 1.0 版中，每个函数指针可以为 null 可禁用该相应的回调。</span><span class="sxs-lookup"><span data-stu-id="aae07-110">In the .NET Framework version 1.0, each function pointer can be null to disable that corresponding callback.</span></span>  
  
 <span data-ttu-id="aae07-111">一次，只有一组回调可以处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="aae07-111">Only one set of callbacks can be active at a time.</span></span> <span data-ttu-id="aae07-112">因此，如果探查器同时调用`SetEnterLeaveFunctionHooks`并[ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)，然后`SetEnterLeaveFunctionHooks2`优先。</span><span class="sxs-lookup"><span data-stu-id="aae07-112">Thus, if a profiler calls both `SetEnterLeaveFunctionHooks` and [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), then `SetEnterLeaveFunctionHooks2` takes precedence.</span></span>  
  
 <span data-ttu-id="aae07-113">`SetEnterLeaveFunctionHooks`可以仅从探查器的调用方法[icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="aae07-113">The `SetEnterLeaveFunctionHooks` method can be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aae07-114">要求</span><span class="sxs-lookup"><span data-stu-id="aae07-114">Requirements</span></span>  
 <span data-ttu-id="aae07-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="aae07-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aae07-116">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aae07-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aae07-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aae07-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="aae07-118">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="aae07-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="aae07-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="aae07-119">See also</span></span>

- [<span data-ttu-id="aae07-120">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="aae07-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
