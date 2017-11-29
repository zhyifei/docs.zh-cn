---
title: "ICorProfilerCallback::RuntimeThreadSuspended 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RuntimeThreadSuspended
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RuntimeThreadSuspended
helpviewer_keywords:
- RuntimeThreadSuspended method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeThreadSuspended method [.NET Framework profiling]
ms.assetid: de830a8b-6ee1-4900-ace3-4237108f6b12
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e4d2ab0244e898a60db8fe392ccbd8c0ebfd5523
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a><span data-ttu-id="28cd0-102">ICorProfilerCallback::RuntimeThreadSuspended 方法</span><span class="sxs-lookup"><span data-stu-id="28cd0-102">ICorProfilerCallback::RuntimeThreadSuspended Method</span></span>
<span data-ttu-id="28cd0-103">指定的线程已挂起或即将被挂起，请通知探查器。</span><span class="sxs-lookup"><span data-stu-id="28cd0-103">Notifies the profiler that the specified thread has been suspended or is about to be suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28cd0-104">语法</span><span class="sxs-lookup"><span data-stu-id="28cd0-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="28cd0-105">参数</span><span class="sxs-lookup"><span data-stu-id="28cd0-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="28cd0-106">[in]已挂起的线程 ID。</span><span class="sxs-lookup"><span data-stu-id="28cd0-106">[in] The ID of the thread that has been suspended.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28cd0-107">备注</span><span class="sxs-lookup"><span data-stu-id="28cd0-107">Remarks</span></span>  
 <span data-ttu-id="28cd0-108">`RuntimeThreadSuspended`通知可以发生之间的任何时间[icorprofilercallback:: Runtimesuspendstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)和关联[icorprofilercallback:: Runtimeresumestarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="28cd0-108">The `RuntimeThreadSuspended` notification can occur any time between the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) and the associated [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span> <span data-ttu-id="28cd0-109">通知之间发生[icorprofilercallback:: Runtimesuspendfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)和`RuntimeResumeStarted`线程必须一直运行在非托管代码，并且已进入运行时挂起。</span><span class="sxs-lookup"><span data-stu-id="28cd0-109">Notifications that occur between [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and `RuntimeResumeStarted` are for threads that had been running in unmanaged code and were suspended upon entry to the runtime.</span></span>  
  
 <span data-ttu-id="28cd0-110">通常情况下，只需后线程处于挂起状态，将发生此回调。</span><span class="sxs-lookup"><span data-stu-id="28cd0-110">Generally, this callback occurs just after a thread is suspended.</span></span> <span data-ttu-id="28cd0-111">但是，如果当前正在执行线程 （调用此回调的线程），正在挂起的一个线程挂起之前，将发生此回调。</span><span class="sxs-lookup"><span data-stu-id="28cd0-111">However, if the currently executing thread (the thread that called this callback) is the one that is being suspended, this callback will occur just before the thread is suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28cd0-112">要求</span><span class="sxs-lookup"><span data-stu-id="28cd0-112">Requirements</span></span>  
 <span data-ttu-id="28cd0-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="28cd0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28cd0-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="28cd0-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="28cd0-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28cd0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28cd0-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28cd0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28cd0-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28cd0-117">See Also</span></span>  
 [<span data-ttu-id="28cd0-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="28cd0-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="28cd0-119">RuntimeThreadResumed 方法</span><span class="sxs-lookup"><span data-stu-id="28cd0-119">RuntimeThreadResumed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)
