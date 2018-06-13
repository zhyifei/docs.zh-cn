---
title: ICorProfilerCallback::ExceptionSearchFilterEnter 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFilterEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFilterEnter
helpviewer_keywords:
- ExceptionSearchFilterEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFilterEnter method [.NET Framework profiling]
ms.assetid: acc239ce-3eef-418c-b1df-c5a6dd8e8a4c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 08ac7eddf96ac54ce16696355f7d5bb5694f872b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450978"
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a><span data-ttu-id="ce144-102">ICorProfilerCallback::ExceptionSearchFilterEnter 方法</span><span class="sxs-lookup"><span data-stu-id="ce144-102">ICorProfilerCallback::ExceptionSearchFilterEnter Method</span></span>
<span data-ttu-id="ce144-103">通知探查器异常处理的搜索阶段已开始执行用户定义的异常筛选器。</span><span class="sxs-lookup"><span data-stu-id="ce144-103">Notifies the profiler that the search phase of exception handling has begun executing a user-defined exception filter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce144-104">语法</span><span class="sxs-lookup"><span data-stu-id="ce144-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce144-105">参数</span><span class="sxs-lookup"><span data-stu-id="ce144-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="ce144-106">[in]包含的筛选器函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="ce144-106">[in] The ID of the function that contains the filter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce144-107">要求</span><span class="sxs-lookup"><span data-stu-id="ce144-107">Requirements</span></span>  
 <span data-ttu-id="ce144-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ce144-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce144-109">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ce144-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ce144-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce144-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce144-111">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce144-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce144-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="ce144-112">See Also</span></span>  
 [<span data-ttu-id="ce144-113">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="ce144-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="ce144-114">ExceptionSearchFilterLeave 方法</span><span class="sxs-lookup"><span data-stu-id="ce144-114">ExceptionSearchFilterLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)
