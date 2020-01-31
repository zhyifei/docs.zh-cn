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
ms.openlocfilehash: 5cafbca75992a5fe8a7d3d95628e0018f1a2e8fa
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865943"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="cff4f-102">ICorProfilerCallback::RuntimeResumeFinished 方法</span><span class="sxs-lookup"><span data-stu-id="cff4f-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>
<span data-ttu-id="cff4f-103">通知探查器运行时已恢复所有运行时线程并返回到正常操作。</span><span class="sxs-lookup"><span data-stu-id="cff4f-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cff4f-104">语法</span><span class="sxs-lookup"><span data-stu-id="cff4f-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="cff4f-105">备注</span><span class="sxs-lookup"><span data-stu-id="cff4f-105">Remarks</span></span>  
 <span data-ttu-id="cff4f-106">不保证在[ICorProfilerCallback：： RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md)回调的同一线程上出现 `RuntimeResumeFinished` 回调。</span><span class="sxs-lookup"><span data-stu-id="cff4f-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="cff4f-107">但是，它可以保证在与[ICorProfilerCallback：： RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md)回调相同的线程上发生。</span><span class="sxs-lookup"><span data-stu-id="cff4f-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cff4f-108">需求</span><span class="sxs-lookup"><span data-stu-id="cff4f-108">Requirements</span></span>  
 <span data-ttu-id="cff4f-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cff4f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cff4f-110">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cff4f-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cff4f-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cff4f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cff4f-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cff4f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cff4f-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cff4f-113">See also</span></span>

- [<span data-ttu-id="cff4f-114">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="cff4f-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
