---
title: ICorProfilerCallback::ExceptionSearchCatcherFound 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchCatcherFound
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchCatcherFound
helpviewer_keywords:
- ExceptionSearchCatcherFound method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchCatcherFound method [.NET Framework profiling]
ms.assetid: 190f424d-5e37-4163-a191-0895686e9476
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e41378b314b91f42fca9d1039d3011b5eaafe502
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074295"
---
# <a name="icorprofilercallbackexceptionsearchcatcherfound-method"></a><span data-ttu-id="ed084-102">ICorProfilerCallback::ExceptionSearchCatcherFound 方法</span><span class="sxs-lookup"><span data-stu-id="ed084-102">ICorProfilerCallback::ExceptionSearchCatcherFound Method</span></span>
<span data-ttu-id="ed084-103">通知探查器的异常处理的搜索阶段已找到的处理程序引发的异常。</span><span class="sxs-lookup"><span data-stu-id="ed084-103">Notifies the profiler that the search phase of exception handling has located a handler for the exception that was thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed084-104">语法</span><span class="sxs-lookup"><span data-stu-id="ed084-104">Syntax</span></span>  
  
```  
RESULT ExceptionSearchCatcherFound(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed084-105">参数</span><span class="sxs-lookup"><span data-stu-id="ed084-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="ed084-106">[in]包含异常处理程序函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="ed084-106">[in] The ID of the function that contains the exception handler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed084-107">要求</span><span class="sxs-lookup"><span data-stu-id="ed084-107">Requirements</span></span>  
 <span data-ttu-id="ed084-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ed084-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed084-109">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ed084-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ed084-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed084-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed084-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed084-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed084-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="ed084-112">See also</span></span>

- [<span data-ttu-id="ed084-113">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="ed084-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
