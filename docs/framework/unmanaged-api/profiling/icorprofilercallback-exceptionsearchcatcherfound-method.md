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
ms.openlocfilehash: 12f16b9bc87ea65e2699ec902d717b08d3155b95
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756180"
---
# <a name="icorprofilercallbackexceptionsearchcatcherfound-method"></a><span data-ttu-id="a056a-102">ICorProfilerCallback::ExceptionSearchCatcherFound 方法</span><span class="sxs-lookup"><span data-stu-id="a056a-102">ICorProfilerCallback::ExceptionSearchCatcherFound Method</span></span>
<span data-ttu-id="a056a-103">通知探查器的异常处理的搜索阶段已找到的处理程序引发的异常。</span><span class="sxs-lookup"><span data-stu-id="a056a-103">Notifies the profiler that the search phase of exception handling has located a handler for the exception that was thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a056a-104">语法</span><span class="sxs-lookup"><span data-stu-id="a056a-104">Syntax</span></span>  
  
```cpp  
RESULT ExceptionSearchCatcherFound(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a056a-105">参数</span><span class="sxs-lookup"><span data-stu-id="a056a-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="a056a-106">[in]包含异常处理程序函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="a056a-106">[in] The ID of the function that contains the exception handler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a056a-107">要求</span><span class="sxs-lookup"><span data-stu-id="a056a-107">Requirements</span></span>  
 <span data-ttu-id="a056a-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a056a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a056a-109">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a056a-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a056a-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a056a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a056a-111">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a056a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a056a-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="a056a-112">See also</span></span>

- [<span data-ttu-id="a056a-113">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="a056a-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
