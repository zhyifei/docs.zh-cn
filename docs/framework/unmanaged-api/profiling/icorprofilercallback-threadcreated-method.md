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
ms.openlocfilehash: c7cd897237539be9bd832a793ad623cf7f31c4b9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747129"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="e3194-102">ICorProfilerCallback::ThreadCreated 方法</span><span class="sxs-lookup"><span data-stu-id="e3194-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="e3194-103">通知探查器已创建一个线程。</span><span class="sxs-lookup"><span data-stu-id="e3194-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3194-104">语法</span><span class="sxs-lookup"><span data-stu-id="e3194-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="e3194-105">参数</span><span class="sxs-lookup"><span data-stu-id="e3194-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="e3194-106">[in]已创建的线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="e3194-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3194-107">备注</span><span class="sxs-lookup"><span data-stu-id="e3194-107">Remarks</span></span>  
 <span data-ttu-id="e3194-108">`threadId`值是否立即有效。</span><span class="sxs-lookup"><span data-stu-id="e3194-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3194-109">要求</span><span class="sxs-lookup"><span data-stu-id="e3194-109">Requirements</span></span>  
 <span data-ttu-id="e3194-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e3194-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3194-111">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e3194-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e3194-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3194-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3194-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3194-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3194-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="e3194-114">See also</span></span>

- [<span data-ttu-id="e3194-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="e3194-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="e3194-116">ThreadDestroyed 方法</span><span class="sxs-lookup"><span data-stu-id="e3194-116">ThreadDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)
