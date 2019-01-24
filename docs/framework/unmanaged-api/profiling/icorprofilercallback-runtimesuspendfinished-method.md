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
ms.openlocfilehash: 6f69c39938384c7feca28ae40aba3e80a0ba28ed
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706649"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a><span data-ttu-id="2c62f-102">ICorProfilerCallback::RuntimeSuspendFinished 方法</span><span class="sxs-lookup"><span data-stu-id="2c62f-102">ICorProfilerCallback::RuntimeSuspendFinished Method</span></span>
<span data-ttu-id="2c62f-103">通知探查器运行时已完成的运行时的所有线程挂起。</span><span class="sxs-lookup"><span data-stu-id="2c62f-103">Notifies the profiler that the runtime has completed suspension of all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c62f-104">语法</span><span class="sxs-lookup"><span data-stu-id="2c62f-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="2c62f-105">备注</span><span class="sxs-lookup"><span data-stu-id="2c62f-105">Remarks</span></span>  
 <span data-ttu-id="2c62f-106">允许非托管代码中的所有运行时线程继续运行，直到它们尝试重新输入运行时。</span><span class="sxs-lookup"><span data-stu-id="2c62f-106">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="2c62f-107">此时，它们还会挂起，直到运行时恢复。</span><span class="sxs-lookup"><span data-stu-id="2c62f-107">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="2c62f-108">这也适用于输入运行时的新线程。</span><span class="sxs-lookup"><span data-stu-id="2c62f-108">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="2c62f-109">在运行时中的所有线程都都立即挂起; 如果他们都已在可中断代码中，或系统都将要求其到达不可中断的代码时挂起。</span><span class="sxs-lookup"><span data-stu-id="2c62f-109">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
 <span data-ttu-id="2c62f-110">`RuntimeSuspendFinished`回调可以保证在相同的线程上发生[icorprofilercallback:: Runtimesuspendstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="2c62f-110">The `RuntimeSuspendFinished` callback is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c62f-111">要求</span><span class="sxs-lookup"><span data-stu-id="2c62f-111">Requirements</span></span>  
 <span data-ttu-id="2c62f-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2c62f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c62f-113">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2c62f-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2c62f-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c62f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c62f-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c62f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c62f-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c62f-116">See also</span></span>
- [<span data-ttu-id="2c62f-117">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="2c62f-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="2c62f-118">RuntimeSuspendAborted 方法</span><span class="sxs-lookup"><span data-stu-id="2c62f-118">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
