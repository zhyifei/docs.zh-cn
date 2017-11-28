---
title: "ICorProfilerCallback::RuntimeThreadResumed 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RuntimeThreadResumed
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RuntimeThreadResumed
helpviewer_keywords:
- ICorProfilerCallback::RuntimeThreadResumed method [.NET Framework profiling]
- RuntimeThreadResumed method [.NET Framework profiling]
ms.assetid: da984f89-4f53-4ab0-ae6f-3e2ee6085994
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b460f87ead93c5f375c758a5547c0ae0be2b5691
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackruntimethreadresumed-method"></a><span data-ttu-id="1ed54-102">ICorProfilerCallback::RuntimeThreadResumed 方法</span><span class="sxs-lookup"><span data-stu-id="1ed54-102">ICorProfilerCallback::RuntimeThreadResumed Method</span></span>
<span data-ttu-id="1ed54-103">通知探查器在挂起后已恢复指定的线程。</span><span class="sxs-lookup"><span data-stu-id="1ed54-103">Notifies the profiler that the specified thread has resumed after being suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ed54-104">语法</span><span class="sxs-lookup"><span data-stu-id="1ed54-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadResumed(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1ed54-105">参数</span><span class="sxs-lookup"><span data-stu-id="1ed54-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="1ed54-106">[in]已恢复线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="1ed54-106">[in] The ID of the thread that has been resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ed54-107">要求</span><span class="sxs-lookup"><span data-stu-id="1ed54-107">Requirements</span></span>  
 <span data-ttu-id="1ed54-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1ed54-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ed54-109">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1ed54-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1ed54-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ed54-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ed54-111">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ed54-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ed54-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ed54-112">See Also</span></span>  
 [<span data-ttu-id="1ed54-113">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="1ed54-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="1ed54-114">RuntimeThreadSuspended 方法</span><span class="sxs-lookup"><span data-stu-id="1ed54-114">RuntimeThreadSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)
