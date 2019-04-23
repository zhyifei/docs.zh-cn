---
title: ICorProfilerCallback::ExceptionSearchFunctionLeave 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFunctionLeave
helpviewer_keywords:
- ExceptionSearchFunctionLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFunctionLeave method [.NET Framework profiling]
ms.assetid: 01de7ac6-0aad-42ef-bf93-50737667b0a4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bdea3b0cc5b21cd881fe0ff3e0278444a22d083d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59117191"
---
# <a name="icorprofilercallbackexceptionsearchfunctionleave-method"></a><span data-ttu-id="f770b-102">ICorProfilerCallback::ExceptionSearchFunctionLeave 方法</span><span class="sxs-lookup"><span data-stu-id="f770b-102">ICorProfilerCallback::ExceptionSearchFunctionLeave Method</span></span>
<span data-ttu-id="f770b-103">通知探查器的异常处理的搜索阶段已完成搜索函数。</span><span class="sxs-lookup"><span data-stu-id="f770b-103">Notifies the profiler that the search phase of exception handling has finished searching a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f770b-104">语法</span><span class="sxs-lookup"><span data-stu-id="f770b-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFunctionLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="f770b-105">要求</span><span class="sxs-lookup"><span data-stu-id="f770b-105">Requirements</span></span>  
 <span data-ttu-id="f770b-106">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f770b-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f770b-107">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f770b-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f770b-108">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f770b-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f770b-109">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f770b-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f770b-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="f770b-110">See also</span></span>

- [<span data-ttu-id="f770b-111">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="f770b-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="f770b-112">ExceptionSearchFunctionEnter 方法</span><span class="sxs-lookup"><span data-stu-id="f770b-112">ExceptionSearchFunctionEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md)
