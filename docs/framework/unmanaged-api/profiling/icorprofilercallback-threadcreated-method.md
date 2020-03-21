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
ms.openlocfilehash: 7fb58c0eb2446253bd658434fc9d68bb857fe0e6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175117"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="9e940-102">ICorProfilerCallback::ThreadCreated 方法</span><span class="sxs-lookup"><span data-stu-id="9e940-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="9e940-103">通知探查器已创建线程。</span><span class="sxs-lookup"><span data-stu-id="9e940-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e940-104">语法</span><span class="sxs-lookup"><span data-stu-id="9e940-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);
```  
  
## <a name="parameters"></a><span data-ttu-id="9e940-105">parameters</span><span class="sxs-lookup"><span data-stu-id="9e940-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="9e940-106">[在]已创建的线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="9e940-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e940-107">备注</span><span class="sxs-lookup"><span data-stu-id="9e940-107">Remarks</span></span>  
 <span data-ttu-id="9e940-108">该`threadId`值立即有效。</span><span class="sxs-lookup"><span data-stu-id="9e940-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e940-109">要求</span><span class="sxs-lookup"><span data-stu-id="9e940-109">Requirements</span></span>  
 <span data-ttu-id="9e940-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9e940-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e940-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9e940-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9e940-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e940-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e940-113">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e940-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e940-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e940-114">See also</span></span>

- [<span data-ttu-id="9e940-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="9e940-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="9e940-116">ThreadDestroyed 方法</span><span class="sxs-lookup"><span data-stu-id="9e940-116">ThreadDestroyed Method</span></span>](icorprofilercallback-threaddestroyed-method.md)
