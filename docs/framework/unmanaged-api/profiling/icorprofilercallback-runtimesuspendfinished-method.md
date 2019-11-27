---
title: ICorProfilerCallback::RuntimeSuspendFinished 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished method [.NET Framework profiling]
- RuntimeSuspendFinished method [.NET Framework profiling]
ms.assetid: b7723f58-c55c-4399-9972-1bbf3b866694
topic_type:
- apiref
ms.openlocfilehash: 8bad09ddb2b821d0e02d43c1e3d1585b3473ec98
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446973"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a><span data-ttu-id="12517-102">ICorProfilerCallback::RuntimeSuspendFinished 方法</span><span class="sxs-lookup"><span data-stu-id="12517-102">ICorProfilerCallback::RuntimeSuspendFinished Method</span></span>
<span data-ttu-id="12517-103">通知探查器运行时已完成所有运行时线程的挂起。</span><span class="sxs-lookup"><span data-stu-id="12517-103">Notifies the profiler that the runtime has completed suspension of all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12517-104">语法</span><span class="sxs-lookup"><span data-stu-id="12517-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="12517-105">备注</span><span class="sxs-lookup"><span data-stu-id="12517-105">Remarks</span></span>  
 <span data-ttu-id="12517-106">允许非托管代码中的所有运行时线程继续运行，直到它们尝试重新进入运行时。</span><span class="sxs-lookup"><span data-stu-id="12517-106">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="12517-107">此时，它们也将被挂起，直到运行时恢复。</span><span class="sxs-lookup"><span data-stu-id="12517-107">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="12517-108">这也适用于输入运行时的新线程。</span><span class="sxs-lookup"><span data-stu-id="12517-108">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="12517-109">如果运行时中的所有线程已处于中断的代码中，则会立即将其挂起，或者当它们到达中断的代码时要求它们挂起。</span><span class="sxs-lookup"><span data-stu-id="12517-109">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
 <span data-ttu-id="12517-110">确保在[ICorProfilerCallback：： RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)回调的线程上出现 `RuntimeSuspendFinished` 回调。</span><span class="sxs-lookup"><span data-stu-id="12517-110">The `RuntimeSuspendFinished` callback is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12517-111">要求</span><span class="sxs-lookup"><span data-stu-id="12517-111">Requirements</span></span>  
 <span data-ttu-id="12517-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="12517-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12517-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="12517-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="12517-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12517-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12517-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12517-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12517-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12517-116">See also</span></span>

- [<span data-ttu-id="12517-117">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="12517-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="12517-118">RuntimeSuspendAborted 方法</span><span class="sxs-lookup"><span data-stu-id="12517-118">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
