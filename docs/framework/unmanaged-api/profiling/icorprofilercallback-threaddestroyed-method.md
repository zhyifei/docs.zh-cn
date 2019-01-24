---
title: ICorProfilerCallback::ThreadDestroyed 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadDestroyed
helpviewer_keywords:
- ThreadDestroyed method [.NET Framework profiling]
- ICorProfilerCallback::ThreadDestroyed method [.NET Framework profiling]
ms.assetid: 4c2b66fd-0595-40a3-8931-f9c4fff97ac8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 40bbde940538d7b06aa74ab55986da2dca3ec225
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54599499"
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="410e5-102">ICorProfilerCallback::ThreadDestroyed 方法</span><span class="sxs-lookup"><span data-stu-id="410e5-102">ICorProfilerCallback::ThreadDestroyed Method</span></span>
<span data-ttu-id="410e5-103">通知探查器线程已销毁。</span><span class="sxs-lookup"><span data-stu-id="410e5-103">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="410e5-104">语法</span><span class="sxs-lookup"><span data-stu-id="410e5-104">Syntax</span></span>  
  
```  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="410e5-105">参数</span><span class="sxs-lookup"><span data-stu-id="410e5-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="410e5-106">[in]已被销毁线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="410e5-106">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="410e5-107">备注</span><span class="sxs-lookup"><span data-stu-id="410e5-107">Remarks</span></span>  
 <span data-ttu-id="410e5-108">`threadId`值不再有效时的此调用。</span><span class="sxs-lookup"><span data-stu-id="410e5-108">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="410e5-109">要求</span><span class="sxs-lookup"><span data-stu-id="410e5-109">Requirements</span></span>  
 <span data-ttu-id="410e5-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="410e5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="410e5-111">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="410e5-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="410e5-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="410e5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="410e5-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="410e5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="410e5-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="410e5-114">See also</span></span>
- [<span data-ttu-id="410e5-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="410e5-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="410e5-116">ThreadCreated 方法</span><span class="sxs-lookup"><span data-stu-id="410e5-116">ThreadCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)
