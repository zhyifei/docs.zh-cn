---
title: ICorProfilerCallback::RuntimeResumeStarted 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeResumeStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeResumeStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeResumeStarted method [.NET Framework profiling]
- RuntimeResumeStarted method [.NET Framework profiling]
ms.assetid: 5854bfb2-c568-4f19-904a-7c9d41e7b995
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2b163d41280c8ea49554cecb845c4be757f55dfc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168085"
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="2cd72-102">ICorProfilerCallback::RuntimeResumeStarted 方法</span><span class="sxs-lookup"><span data-stu-id="2cd72-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>
<span data-ttu-id="2cd72-103">通知探查器运行时继续运行时的所有线程。</span><span class="sxs-lookup"><span data-stu-id="2cd72-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cd72-104">语法</span><span class="sxs-lookup"><span data-stu-id="2cd72-104">Syntax</span></span>  
  
```  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="2cd72-105">要求</span><span class="sxs-lookup"><span data-stu-id="2cd72-105">Requirements</span></span>  
 <span data-ttu-id="2cd72-106">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2cd72-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cd72-107">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2cd72-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2cd72-108">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2cd72-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2cd72-109">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cd72-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cd72-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="2cd72-110">See also</span></span>

- [<span data-ttu-id="2cd72-111">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="2cd72-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="2cd72-112">RuntimeResumeFinished 方法</span><span class="sxs-lookup"><span data-stu-id="2cd72-112">RuntimeResumeFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)
