---
title: ICorProfilerCallback::ThreadCreated 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadCreated
helpviewer_keywords:
- ICorProfilerCallback::ThreadCreated method [.NET Framework profiling]
- ThreadCreated method [.NET Framework profiling]
ms.assetid: cca0f799-09b8-4689-a33c-6d6537943a9b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5f8eca3e8eb755e31e704e557ae614a6e5c1f534
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59107765"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="b9f64-102">ICorProfilerCallback::ThreadCreated 方法</span><span class="sxs-lookup"><span data-stu-id="b9f64-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="b9f64-103">通知探查器已创建一个线程。</span><span class="sxs-lookup"><span data-stu-id="b9f64-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9f64-104">语法</span><span class="sxs-lookup"><span data-stu-id="b9f64-104">Syntax</span></span>  
  
```  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="b9f64-105">参数</span><span class="sxs-lookup"><span data-stu-id="b9f64-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="b9f64-106">[in]已创建的线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="b9f64-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9f64-107">备注</span><span class="sxs-lookup"><span data-stu-id="b9f64-107">Remarks</span></span>  
 <span data-ttu-id="b9f64-108">`threadId`值是否立即有效。</span><span class="sxs-lookup"><span data-stu-id="b9f64-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9f64-109">要求</span><span class="sxs-lookup"><span data-stu-id="b9f64-109">Requirements</span></span>  
 <span data-ttu-id="b9f64-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b9f64-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9f64-111">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b9f64-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b9f64-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9f64-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9f64-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9f64-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9f64-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9f64-114">See also</span></span>

- [<span data-ttu-id="b9f64-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="b9f64-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="b9f64-116">ThreadDestroyed 方法</span><span class="sxs-lookup"><span data-stu-id="b9f64-116">ThreadDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)
