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
ms.openlocfilehash: c8645bf828d0ad99bd25c1909cbee3314a11abf9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865865"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a><span data-ttu-id="289cb-102">ICorProfilerCallback::RuntimeThreadSuspended 方法</span><span class="sxs-lookup"><span data-stu-id="289cb-102">ICorProfilerCallback::RuntimeThreadSuspended Method</span></span>
<span data-ttu-id="289cb-103">通知探查器指定的线程已挂起或将要挂起。</span><span class="sxs-lookup"><span data-stu-id="289cb-103">Notifies the profiler that the specified thread has been suspended or is about to be suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="289cb-104">语法</span><span class="sxs-lookup"><span data-stu-id="289cb-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="289cb-105">参数</span><span class="sxs-lookup"><span data-stu-id="289cb-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="289cb-106">中已挂起的线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="289cb-106">[in] The ID of the thread that has been suspended.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="289cb-107">备注</span><span class="sxs-lookup"><span data-stu-id="289cb-107">Remarks</span></span>  
 <span data-ttu-id="289cb-108">在[ICorProfilerCallback：： RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md)与关联的[ICorProfilerCallback：： RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md)回调之间随时会发生 `RuntimeThreadSuspended` 通知。</span><span class="sxs-lookup"><span data-stu-id="289cb-108">The `RuntimeThreadSuspended` notification can occur any time between the [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) and the associated [ICorProfilerCallback::RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span> <span data-ttu-id="289cb-109">在[ICorProfilerCallback：： RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md)和 `RuntimeResumeStarted` 之间发生的通知适用于已在非托管代码中运行并在进入运行时后挂起的线程。</span><span class="sxs-lookup"><span data-stu-id="289cb-109">Notifications that occur between [ICorProfilerCallback::RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) and `RuntimeResumeStarted` are for threads that had been running in unmanaged code and were suspended upon entry to the runtime.</span></span>  
  
 <span data-ttu-id="289cb-110">通常，此回调恰好在挂起线程之后发生。</span><span class="sxs-lookup"><span data-stu-id="289cb-110">Generally, this callback occurs just after a thread is suspended.</span></span> <span data-ttu-id="289cb-111">但是，如果当前正在执行的线程（调用此回调的线程）是正在挂起的线程，则此回调将在线程挂起之前发生。</span><span class="sxs-lookup"><span data-stu-id="289cb-111">However, if the currently executing thread (the thread that called this callback) is the one that is being suspended, this callback will occur just before the thread is suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="289cb-112">需求</span><span class="sxs-lookup"><span data-stu-id="289cb-112">Requirements</span></span>  
 <span data-ttu-id="289cb-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="289cb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="289cb-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="289cb-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="289cb-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="289cb-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="289cb-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="289cb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="289cb-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="289cb-117">See also</span></span>

- [<span data-ttu-id="289cb-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="289cb-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="289cb-119">RuntimeThreadResumed 方法</span><span class="sxs-lookup"><span data-stu-id="289cb-119">RuntimeThreadResumed Method</span></span>](icorprofilercallback-runtimethreadresumed-method.md)
