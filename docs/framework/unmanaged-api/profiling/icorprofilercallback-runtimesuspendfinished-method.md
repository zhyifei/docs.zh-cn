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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0b243c507171a4d907ef4594ae0c715a074c965a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452213"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a><span data-ttu-id="51f6c-102">ICorProfilerCallback::RuntimeSuspendFinished 方法</span><span class="sxs-lookup"><span data-stu-id="51f6c-102">ICorProfilerCallback::RuntimeSuspendFinished Method</span></span>
<span data-ttu-id="51f6c-103">通知探查器运行时已完成的所有运行时线程的挂起。</span><span class="sxs-lookup"><span data-stu-id="51f6c-103">Notifies the profiler that the runtime has completed suspension of all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51f6c-104">语法</span><span class="sxs-lookup"><span data-stu-id="51f6c-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="51f6c-105">备注</span><span class="sxs-lookup"><span data-stu-id="51f6c-105">Remarks</span></span>  
 <span data-ttu-id="51f6c-106">允许非托管代码中的所有运行时线程继续运行，直到它们尝试重新输入运行时。</span><span class="sxs-lookup"><span data-stu-id="51f6c-106">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="51f6c-107">此时，它们也会挂起，直到运行时恢复。</span><span class="sxs-lookup"><span data-stu-id="51f6c-107">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="51f6c-108">这也适用于输入运行时的新线程。</span><span class="sxs-lookup"><span data-stu-id="51f6c-108">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="51f6c-109">在运行时中的所有线程都都立即挂起; 如果它们已都处于可中断的代码，或都将要求他们到达可中断的代码时挂起。</span><span class="sxs-lookup"><span data-stu-id="51f6c-109">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
 <span data-ttu-id="51f6c-110">`RuntimeSuspendFinished`回调保证在同一线程上才会出现[icorprofilercallback:: Runtimesuspendstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="51f6c-110">The `RuntimeSuspendFinished` callback is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51f6c-111">要求</span><span class="sxs-lookup"><span data-stu-id="51f6c-111">Requirements</span></span>  
 <span data-ttu-id="51f6c-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="51f6c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51f6c-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="51f6c-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="51f6c-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51f6c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51f6c-115">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51f6c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51f6c-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="51f6c-116">See Also</span></span>  
 [<span data-ttu-id="51f6c-117">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="51f6c-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="51f6c-118">RuntimeSuspendAborted 方法</span><span class="sxs-lookup"><span data-stu-id="51f6c-118">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
