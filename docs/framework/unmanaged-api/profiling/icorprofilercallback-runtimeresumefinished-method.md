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
ms.openlocfilehash: f6b983db7da258fb94f941d01914ece0f7b1359f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453297"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="a52bd-102">ICorProfilerCallback::RuntimeResumeFinished 方法</span><span class="sxs-lookup"><span data-stu-id="a52bd-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>
<span data-ttu-id="a52bd-103">运行时已恢复所有运行时线程，并且已返回到正常操作，请通知探查器。</span><span class="sxs-lookup"><span data-stu-id="a52bd-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a52bd-104">语法</span><span class="sxs-lookup"><span data-stu-id="a52bd-104">Syntax</span></span>  
  
```  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="a52bd-105">备注</span><span class="sxs-lookup"><span data-stu-id="a52bd-105">Remarks</span></span>  
 <span data-ttu-id="a52bd-106">`RuntimeResumeFinished`回调不能保证在同一个线程上发生[icorprofilercallback:: Runtimesuspendstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="a52bd-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="a52bd-107">但是，可以保证在同一个线程上发生[icorprofilercallback:: Runtimeresumestarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="a52bd-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a52bd-108">要求</span><span class="sxs-lookup"><span data-stu-id="a52bd-108">Requirements</span></span>  
 <span data-ttu-id="a52bd-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a52bd-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a52bd-110">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a52bd-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a52bd-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a52bd-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a52bd-112">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a52bd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a52bd-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="a52bd-113">See Also</span></span>  
 [<span data-ttu-id="a52bd-114">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="a52bd-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
