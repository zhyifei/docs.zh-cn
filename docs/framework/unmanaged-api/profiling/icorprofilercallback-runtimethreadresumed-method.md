---
title: ICorProfilerCallback::RuntimeThreadResumed 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeThreadResumed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadResumed
helpviewer_keywords:
- ICorProfilerCallback::RuntimeThreadResumed method [.NET Framework profiling]
- RuntimeThreadResumed method [.NET Framework profiling]
ms.assetid: da984f89-4f53-4ab0-ae6f-3e2ee6085994
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4f971c5175307c1e1df6890c136b306860e54d23
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452704"
---
# <a name="icorprofilercallbackruntimethreadresumed-method"></a><span data-ttu-id="ae995-102">ICorProfilerCallback::RuntimeThreadResumed 方法</span><span class="sxs-lookup"><span data-stu-id="ae995-102">ICorProfilerCallback::RuntimeThreadResumed Method</span></span>
<span data-ttu-id="ae995-103">通知探查器在挂起后已恢复指定的线程。</span><span class="sxs-lookup"><span data-stu-id="ae995-103">Notifies the profiler that the specified thread has resumed after being suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae995-104">语法</span><span class="sxs-lookup"><span data-stu-id="ae995-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadResumed(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae995-105">参数</span><span class="sxs-lookup"><span data-stu-id="ae995-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="ae995-106">[in]已恢复线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="ae995-106">[in] The ID of the thread that has been resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae995-107">要求</span><span class="sxs-lookup"><span data-stu-id="ae995-107">Requirements</span></span>  
 <span data-ttu-id="ae995-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ae995-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae995-109">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ae995-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ae995-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae995-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae995-111">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae995-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae995-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae995-112">See Also</span></span>  
 [<span data-ttu-id="ae995-113">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="ae995-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="ae995-114">RuntimeThreadSuspended 方法</span><span class="sxs-lookup"><span data-stu-id="ae995-114">RuntimeThreadSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)
