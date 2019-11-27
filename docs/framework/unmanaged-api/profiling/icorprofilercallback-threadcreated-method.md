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
ms.openlocfilehash: 1d8aa231f65bad88806ee9b1d3c5df978c9740a2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446925"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="a842f-102">ICorProfilerCallback::ThreadCreated 方法</span><span class="sxs-lookup"><span data-stu-id="a842f-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="a842f-103">通知探查器已创建一个线程。</span><span class="sxs-lookup"><span data-stu-id="a842f-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a842f-104">语法</span><span class="sxs-lookup"><span data-stu-id="a842f-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="a842f-105">参数</span><span class="sxs-lookup"><span data-stu-id="a842f-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="a842f-106">中已创建的线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="a842f-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a842f-107">备注</span><span class="sxs-lookup"><span data-stu-id="a842f-107">Remarks</span></span>  
 <span data-ttu-id="a842f-108">`threadId` 值立即有效。</span><span class="sxs-lookup"><span data-stu-id="a842f-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a842f-109">要求</span><span class="sxs-lookup"><span data-stu-id="a842f-109">Requirements</span></span>  
 <span data-ttu-id="a842f-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a842f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a842f-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a842f-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a842f-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a842f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a842f-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a842f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a842f-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a842f-114">See also</span></span>

- [<span data-ttu-id="a842f-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="a842f-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="a842f-116">ThreadDestroyed 方法</span><span class="sxs-lookup"><span data-stu-id="a842f-116">ThreadDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)
