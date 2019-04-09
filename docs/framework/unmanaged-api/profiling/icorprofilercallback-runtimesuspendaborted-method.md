---
title: ICorProfilerCallback::RuntimeSuspendAborted 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendAborted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted method [.NET Framework profiling]
- RuntimeSuspendAborted method [.NET Framework profiling]
ms.assetid: 5a8a4277-345b-448b-a028-fc8cff9998aa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e9aaf7325b8e7e65aa98904513cc7efe94e35087
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180554"
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a><span data-ttu-id="f1a53-102">ICorProfilerCallback::RuntimeSuspendAborted 方法</span><span class="sxs-lookup"><span data-stu-id="f1a53-102">ICorProfilerCallback::RuntimeSuspendAborted Method</span></span>
<span data-ttu-id="f1a53-103">通知探查器运行时已中止已发生的运行时挂起。</span><span class="sxs-lookup"><span data-stu-id="f1a53-103">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1a53-104">语法</span><span class="sxs-lookup"><span data-stu-id="f1a53-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="f1a53-105">备注</span><span class="sxs-lookup"><span data-stu-id="f1a53-105">Remarks</span></span>  
 <span data-ttu-id="f1a53-106">如果两个线程同时尝试挂起运行时，可能会被中止的运行时挂起。</span><span class="sxs-lookup"><span data-stu-id="f1a53-106">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span></span>  
  
 <span data-ttu-id="f1a53-107">任一[icorprofilercallback:: Runtimesuspendfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)回调或`RuntimeSuspendAborted`回调将在单个线程以下发生[icorprofilercallback:: Runtimesuspendstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="f1a53-107">Either the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
 <span data-ttu-id="f1a53-108">`RuntimeSuspendAborted`回调可以保证在相同的线程上发生`RuntimeSuspendStarted`回调。</span><span class="sxs-lookup"><span data-stu-id="f1a53-108">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1a53-109">要求</span><span class="sxs-lookup"><span data-stu-id="f1a53-109">Requirements</span></span>  
 <span data-ttu-id="f1a53-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f1a53-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1a53-111">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f1a53-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f1a53-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1a53-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f1a53-113">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="f1a53-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f1a53-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1a53-114">See also</span></span>

- [<span data-ttu-id="f1a53-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="f1a53-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
