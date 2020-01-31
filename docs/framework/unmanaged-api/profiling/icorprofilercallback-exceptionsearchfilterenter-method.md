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
ms.openlocfilehash: 96ca2b926217ced6c88f8890f0facc7346fe10c7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790143"
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a><span data-ttu-id="7068a-102">ICorProfilerCallback::ExceptionSearchFilterEnter 方法</span><span class="sxs-lookup"><span data-stu-id="7068a-102">ICorProfilerCallback::ExceptionSearchFilterEnter Method</span></span>
<span data-ttu-id="7068a-103">通知探查器异常处理的搜索阶段已开始执行用户定义的异常筛选器。</span><span class="sxs-lookup"><span data-stu-id="7068a-103">Notifies the profiler that the search phase of exception handling has begun executing a user-defined exception filter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7068a-104">语法</span><span class="sxs-lookup"><span data-stu-id="7068a-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7068a-105">参数</span><span class="sxs-lookup"><span data-stu-id="7068a-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="7068a-106">\[中] 包含筛选器的函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="7068a-106">\[in] The ID of the function that contains the filter.</span></span>

## <a name="requirements"></a><span data-ttu-id="7068a-107">需求</span><span class="sxs-lookup"><span data-stu-id="7068a-107">Requirements</span></span>  
 <span data-ttu-id="7068a-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7068a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7068a-109">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7068a-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7068a-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7068a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7068a-111">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7068a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7068a-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7068a-112">See also</span></span>

- [<span data-ttu-id="7068a-113">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="7068a-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="7068a-114">ExceptionSearchFilterLeave 方法</span><span class="sxs-lookup"><span data-stu-id="7068a-114">ExceptionSearchFilterLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)
