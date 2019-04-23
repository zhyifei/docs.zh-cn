---
title: ICorProfilerCallback::RuntimeSuspendStarted 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted method [.NET Framework profiling]
- RuntimeSuspendStarted method [.NET Framework profiling]
ms.assetid: c8461cac-e31b-4efa-ad2c-26598173eb96
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a5606a556dd7aeafe6d7a6408d236f2bee8dc773
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168969"
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a><span data-ttu-id="40f64-102">ICorProfilerCallback::RuntimeSuspendStarted 方法</span><span class="sxs-lookup"><span data-stu-id="40f64-102">ICorProfilerCallback::RuntimeSuspendStarted Method</span></span>
<span data-ttu-id="40f64-103">通知探查器运行时即将挂起运行时的所有线程。</span><span class="sxs-lookup"><span data-stu-id="40f64-103">Notifies the profiler that the runtime is about to suspend all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40f64-104">语法</span><span class="sxs-lookup"><span data-stu-id="40f64-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40f64-105">参数</span><span class="sxs-lookup"><span data-stu-id="40f64-105">Parameters</span></span>  
 `suspendReason`  
 <span data-ttu-id="40f64-106">[in]值为[COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md)指示挂起原因的枚举。</span><span class="sxs-lookup"><span data-stu-id="40f64-106">[in] A value of the [COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md) enumeration that indicates the reason for the suspension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40f64-107">备注</span><span class="sxs-lookup"><span data-stu-id="40f64-107">Remarks</span></span>  
 <span data-ttu-id="40f64-108">允许非托管代码中的所有运行时线程继续运行，直到它们尝试重新输入运行时。</span><span class="sxs-lookup"><span data-stu-id="40f64-108">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="40f64-109">此时，它们还会挂起，直到运行时恢复。</span><span class="sxs-lookup"><span data-stu-id="40f64-109">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="40f64-110">这也适用于输入运行时的新线程。</span><span class="sxs-lookup"><span data-stu-id="40f64-110">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="40f64-111">在运行时中的所有线程都都立即挂起; 如果他们都已在可中断代码中，或系统都将要求其到达不可中断的代码时挂起。</span><span class="sxs-lookup"><span data-stu-id="40f64-111">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40f64-112">要求</span><span class="sxs-lookup"><span data-stu-id="40f64-112">Requirements</span></span>  
 <span data-ttu-id="40f64-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="40f64-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40f64-114">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="40f64-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="40f64-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40f64-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40f64-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40f64-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40f64-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="40f64-117">See also</span></span>

- [<span data-ttu-id="40f64-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="40f64-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="40f64-119">RuntimeSuspendAborted 方法</span><span class="sxs-lookup"><span data-stu-id="40f64-119">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
- [<span data-ttu-id="40f64-120">RuntimeSuspendFinished 方法</span><span class="sxs-lookup"><span data-stu-id="40f64-120">RuntimeSuspendFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)
