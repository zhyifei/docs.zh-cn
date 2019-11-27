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
ms.openlocfilehash: 509d6cd2e65c2eb8c92f6d79deae9e01e75298f6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433442"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a><span data-ttu-id="1eecf-102">ICorProfilerCallback::RuntimeThreadSuspended 方法</span><span class="sxs-lookup"><span data-stu-id="1eecf-102">ICorProfilerCallback::RuntimeThreadSuspended Method</span></span>
<span data-ttu-id="1eecf-103">通知探查器指定的线程已挂起或将要挂起。</span><span class="sxs-lookup"><span data-stu-id="1eecf-103">Notifies the profiler that the specified thread has been suspended or is about to be suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1eecf-104">语法</span><span class="sxs-lookup"><span data-stu-id="1eecf-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1eecf-105">参数</span><span class="sxs-lookup"><span data-stu-id="1eecf-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="1eecf-106">中已挂起的线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="1eecf-106">[in] The ID of the thread that has been suspended.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1eecf-107">备注</span><span class="sxs-lookup"><span data-stu-id="1eecf-107">Remarks</span></span>  
 <span data-ttu-id="1eecf-108">在[ICorProfilerCallback：： RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)与关联的[ICorProfilerCallback：： RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md)回调之间随时会发生 `RuntimeThreadSuspended` 通知。</span><span class="sxs-lookup"><span data-stu-id="1eecf-108">The `RuntimeThreadSuspended` notification can occur any time between the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) and the associated [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span> <span data-ttu-id="1eecf-109">在[ICorProfilerCallback：： RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)和 `RuntimeResumeStarted` 之间发生的通知适用于已在非托管代码中运行并在进入运行时后挂起的线程。</span><span class="sxs-lookup"><span data-stu-id="1eecf-109">Notifications that occur between [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and `RuntimeResumeStarted` are for threads that had been running in unmanaged code and were suspended upon entry to the runtime.</span></span>  
  
 <span data-ttu-id="1eecf-110">通常，此回调恰好在挂起线程之后发生。</span><span class="sxs-lookup"><span data-stu-id="1eecf-110">Generally, this callback occurs just after a thread is suspended.</span></span> <span data-ttu-id="1eecf-111">但是，如果当前正在执行的线程（调用此回调的线程）是正在挂起的线程，则此回调将在线程挂起之前发生。</span><span class="sxs-lookup"><span data-stu-id="1eecf-111">However, if the currently executing thread (the thread that called this callback) is the one that is being suspended, this callback will occur just before the thread is suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1eecf-112">要求</span><span class="sxs-lookup"><span data-stu-id="1eecf-112">Requirements</span></span>  
 <span data-ttu-id="1eecf-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1eecf-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1eecf-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1eecf-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1eecf-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1eecf-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1eecf-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1eecf-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eecf-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1eecf-117">See also</span></span>

- [<span data-ttu-id="1eecf-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="1eecf-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="1eecf-119">RuntimeThreadResumed 方法</span><span class="sxs-lookup"><span data-stu-id="1eecf-119">RuntimeThreadResumed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)
