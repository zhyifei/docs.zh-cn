---
title: ICorProfilerCallback::RuntimeThreadSuspended 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeThreadSuspended
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadSuspended
helpviewer_keywords:
- RuntimeThreadSuspended method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeThreadSuspended method [.NET Framework profiling]
ms.assetid: de830a8b-6ee1-4900-ace3-4237108f6b12
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bb93dbf35501d44bb21d3d689aebeba3acd19f79
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616794"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a><span data-ttu-id="2919e-102">ICorProfilerCallback::RuntimeThreadSuspended 方法</span><span class="sxs-lookup"><span data-stu-id="2919e-102">ICorProfilerCallback::RuntimeThreadSuspended Method</span></span>
<span data-ttu-id="2919e-103">指定的线程已挂起或即将挂起通知探查器。</span><span class="sxs-lookup"><span data-stu-id="2919e-103">Notifies the profiler that the specified thread has been suspended or is about to be suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2919e-104">语法</span><span class="sxs-lookup"><span data-stu-id="2919e-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2919e-105">参数</span><span class="sxs-lookup"><span data-stu-id="2919e-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="2919e-106">[in]已挂起的线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="2919e-106">[in] The ID of the thread that has been suspended.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2919e-107">备注</span><span class="sxs-lookup"><span data-stu-id="2919e-107">Remarks</span></span>  
 <span data-ttu-id="2919e-108">`RuntimeThreadSuspended`通知可随时之间发生[icorprofilercallback:: Runtimesuspendstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)和关联[icorprofilercallback:: Runtimeresumestarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="2919e-108">The `RuntimeThreadSuspended` notification can occur any time between the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) and the associated [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span> <span data-ttu-id="2919e-109">通知之间发生[icorprofilercallback:: Runtimesuspendfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)和`RuntimeResumeStarted`是线程中运行非托管代码和已挂起到运行时在输入时。</span><span class="sxs-lookup"><span data-stu-id="2919e-109">Notifications that occur between [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and `RuntimeResumeStarted` are for threads that had been running in unmanaged code and were suspended upon entry to the runtime.</span></span>  
  
 <span data-ttu-id="2919e-110">通常情况下，只是后一个线程被挂起，将发生此回调。</span><span class="sxs-lookup"><span data-stu-id="2919e-110">Generally, this callback occurs just after a thread is suspended.</span></span> <span data-ttu-id="2919e-111">但是，如果当前正在执行的线程 （调用此回调的线程） 是指被挂起，线程被挂起之前，将发生此回调。</span><span class="sxs-lookup"><span data-stu-id="2919e-111">However, if the currently executing thread (the thread that called this callback) is the one that is being suspended, this callback will occur just before the thread is suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2919e-112">要求</span><span class="sxs-lookup"><span data-stu-id="2919e-112">Requirements</span></span>  
 <span data-ttu-id="2919e-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2919e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2919e-114">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2919e-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2919e-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2919e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2919e-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2919e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2919e-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="2919e-117">See also</span></span>
- [<span data-ttu-id="2919e-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="2919e-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="2919e-119">RuntimeThreadResumed 方法</span><span class="sxs-lookup"><span data-stu-id="2919e-119">RuntimeThreadResumed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)
