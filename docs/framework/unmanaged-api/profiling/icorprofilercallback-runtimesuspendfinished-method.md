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
ms.openlocfilehash: e6c21e5ec9491e2ccade48a5019b284e333b5ead
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865930"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a><span data-ttu-id="8ff87-102">ICorProfilerCallback::RuntimeSuspendFinished 方法</span><span class="sxs-lookup"><span data-stu-id="8ff87-102">ICorProfilerCallback::RuntimeSuspendFinished Method</span></span>
<span data-ttu-id="8ff87-103">通知探查器运行时已完成所有运行时线程的挂起。</span><span class="sxs-lookup"><span data-stu-id="8ff87-103">Notifies the profiler that the runtime has completed suspension of all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ff87-104">语法</span><span class="sxs-lookup"><span data-stu-id="8ff87-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="8ff87-105">备注</span><span class="sxs-lookup"><span data-stu-id="8ff87-105">Remarks</span></span>  
 <span data-ttu-id="8ff87-106">允许非托管代码中的所有运行时线程继续运行，直到它们尝试重新进入运行时。</span><span class="sxs-lookup"><span data-stu-id="8ff87-106">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="8ff87-107">此时，它们也将被挂起，直到运行时恢复。</span><span class="sxs-lookup"><span data-stu-id="8ff87-107">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="8ff87-108">这也适用于输入运行时的新线程。</span><span class="sxs-lookup"><span data-stu-id="8ff87-108">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="8ff87-109">如果运行时中的所有线程已处于中断的代码中，则会立即将其挂起，或者当它们到达中断的代码时要求它们挂起。</span><span class="sxs-lookup"><span data-stu-id="8ff87-109">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
 <span data-ttu-id="8ff87-110">确保在[ICorProfilerCallback：： RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md)回调的线程上出现 `RuntimeSuspendFinished` 回调。</span><span class="sxs-lookup"><span data-stu-id="8ff87-110">The `RuntimeSuspendFinished` callback is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ff87-111">需求</span><span class="sxs-lookup"><span data-stu-id="8ff87-111">Requirements</span></span>  
 <span data-ttu-id="8ff87-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8ff87-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ff87-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8ff87-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8ff87-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ff87-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ff87-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ff87-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ff87-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ff87-116">See also</span></span>

- [<span data-ttu-id="8ff87-117">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="8ff87-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="8ff87-118">RuntimeSuspendAborted 方法</span><span class="sxs-lookup"><span data-stu-id="8ff87-118">RuntimeSuspendAborted Method</span></span>](icorprofilercallback-runtimesuspendaborted-method.md)
