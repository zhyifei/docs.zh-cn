---
title: "ICorProfilerCallback::RuntimeResumeFinished 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RuntimeResumeFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RuntimeResumeFinished
helpviewer_keywords:
- RuntimeResumeFinished method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeResumeFinished method [.NET Framework profiling]
ms.assetid: 76de0494-dc49-426b-887d-bee98806a982
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0ea3e28a12e4891f9e67beb1ddd705461a95118b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="68c7f-102">ICorProfilerCallback::RuntimeResumeFinished 方法</span><span class="sxs-lookup"><span data-stu-id="68c7f-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>
<span data-ttu-id="68c7f-103">运行时已恢复所有运行时线程，并且已返回到正常操作，请通知探查器。</span><span class="sxs-lookup"><span data-stu-id="68c7f-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68c7f-104">语法</span><span class="sxs-lookup"><span data-stu-id="68c7f-104">Syntax</span></span>  
  
```  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="68c7f-105">备注</span><span class="sxs-lookup"><span data-stu-id="68c7f-105">Remarks</span></span>  
 <span data-ttu-id="68c7f-106">`RuntimeResumeFinished`回调不能保证在同一个线程上发生[icorprofilercallback:: Runtimesuspendstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="68c7f-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="68c7f-107">但是，可以保证在同一个线程上发生[icorprofilercallback:: Runtimeresumestarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="68c7f-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68c7f-108">惠?</span><span class="sxs-lookup"><span data-stu-id="68c7f-108">Requirements</span></span>  
 <span data-ttu-id="68c7f-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="68c7f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68c7f-110">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="68c7f-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="68c7f-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68c7f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68c7f-112">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68c7f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68c7f-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="68c7f-113">See Also</span></span>  
 [<span data-ttu-id="68c7f-114">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="68c7f-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
