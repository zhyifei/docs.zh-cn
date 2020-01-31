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
ms.openlocfilehash: c7b52954a6be449de0c3633f0ac648980c6d13f6
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865917"
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="def9a-102">ICorProfilerCallback::RuntimeResumeStarted 方法</span><span class="sxs-lookup"><span data-stu-id="def9a-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>
<span data-ttu-id="def9a-103">通知探查器运行时正在恢复所有运行时线程。</span><span class="sxs-lookup"><span data-stu-id="def9a-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="def9a-104">语法</span><span class="sxs-lookup"><span data-stu-id="def9a-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="def9a-105">需求</span><span class="sxs-lookup"><span data-stu-id="def9a-105">Requirements</span></span>  
 <span data-ttu-id="def9a-106">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="def9a-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="def9a-107">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="def9a-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="def9a-108">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="def9a-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="def9a-109">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="def9a-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="def9a-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="def9a-110">See also</span></span>

- [<span data-ttu-id="def9a-111">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="def9a-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="def9a-112">RuntimeResumeFinished 方法</span><span class="sxs-lookup"><span data-stu-id="def9a-112">RuntimeResumeFinished Method</span></span>](icorprofilercallback-runtimeresumefinished-method.md)
