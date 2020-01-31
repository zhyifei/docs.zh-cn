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
ms.openlocfilehash: 07041d06668d474a3d30968fb623854a24ebf0eb
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865813"
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="86dd4-102">ICorProfilerCallback::ThreadDestroyed 方法</span><span class="sxs-lookup"><span data-stu-id="86dd4-102">ICorProfilerCallback::ThreadDestroyed Method</span></span>
<span data-ttu-id="86dd4-103">通知探查器线程已销毁。</span><span class="sxs-lookup"><span data-stu-id="86dd4-103">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86dd4-104">语法</span><span class="sxs-lookup"><span data-stu-id="86dd4-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86dd4-105">参数</span><span class="sxs-lookup"><span data-stu-id="86dd4-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="86dd4-106">中已销毁的线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="86dd4-106">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86dd4-107">备注</span><span class="sxs-lookup"><span data-stu-id="86dd4-107">Remarks</span></span>  
 <span data-ttu-id="86dd4-108">此调用时，`threadId` 值不再有效。</span><span class="sxs-lookup"><span data-stu-id="86dd4-108">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86dd4-109">需求</span><span class="sxs-lookup"><span data-stu-id="86dd4-109">Requirements</span></span>  
 <span data-ttu-id="86dd4-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="86dd4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86dd4-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="86dd4-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="86dd4-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86dd4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86dd4-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86dd4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86dd4-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86dd4-114">See also</span></span>

- [<span data-ttu-id="86dd4-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="86dd4-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="86dd4-116">ThreadCreated 方法</span><span class="sxs-lookup"><span data-stu-id="86dd4-116">ThreadCreated Method</span></span>](icorprofilercallback-threadcreated-method.md)
