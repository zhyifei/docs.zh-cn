---
title: ICorProfilerCallback::RuntimeResumeFinished 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeResumeFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeResumeFinished
helpviewer_keywords:
- RuntimeResumeFinished method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeResumeFinished method [.NET Framework profiling]
ms.assetid: 76de0494-dc49-426b-887d-bee98806a982
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1c7b3c3ea5e976645c265b34327caa38ef6a28fd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59226984"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="cc3e5-102">ICorProfilerCallback::RuntimeResumeFinished 方法</span><span class="sxs-lookup"><span data-stu-id="cc3e5-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>
<span data-ttu-id="cc3e5-103">通知探查器运行时已恢复运行时的所有线程，并已返回到正常操作。</span><span class="sxs-lookup"><span data-stu-id="cc3e5-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc3e5-104">语法</span><span class="sxs-lookup"><span data-stu-id="cc3e5-104">Syntax</span></span>  
  
```  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="cc3e5-105">备注</span><span class="sxs-lookup"><span data-stu-id="cc3e5-105">Remarks</span></span>  
 <span data-ttu-id="cc3e5-106">`RuntimeResumeFinished`回叫不能保证在相同的线程上发生[icorprofilercallback:: Runtimesuspendstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="cc3e5-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="cc3e5-107">但是，可以保证在相同的线程上发生[icorprofilercallback:: Runtimeresumestarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="cc3e5-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc3e5-108">要求</span><span class="sxs-lookup"><span data-stu-id="cc3e5-108">Requirements</span></span>  
 <span data-ttu-id="cc3e5-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cc3e5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc3e5-110">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cc3e5-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cc3e5-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc3e5-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc3e5-112">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc3e5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc3e5-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc3e5-113">See also</span></span>

- [<span data-ttu-id="cc3e5-114">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="cc3e5-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
