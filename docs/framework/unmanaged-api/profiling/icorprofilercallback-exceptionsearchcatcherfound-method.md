---
title: "ICorProfilerCallback::ExceptionSearchCatcherFound 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionSearchCatcherFound
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionSearchCatcherFound
helpviewer_keywords:
- ExceptionSearchCatcherFound method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchCatcherFound method [.NET Framework profiling]
ms.assetid: 190f424d-5e37-4163-a191-0895686e9476
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 434af3fb6201aefac40795ffed7781a72a97b729
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackexceptionsearchcatcherfound-method"></a><span data-ttu-id="da4b3-102">ICorProfilerCallback::ExceptionSearchCatcherFound 方法</span><span class="sxs-lookup"><span data-stu-id="da4b3-102">ICorProfilerCallback::ExceptionSearchCatcherFound Method</span></span>
<span data-ttu-id="da4b3-103">通知探查器异常处理的搜索阶段已找到的处理程序已引发的异常。</span><span class="sxs-lookup"><span data-stu-id="da4b3-103">Notifies the profiler that the search phase of exception handling has located a handler for the exception that was thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da4b3-104">语法</span><span class="sxs-lookup"><span data-stu-id="da4b3-104">Syntax</span></span>  
  
```  
RESULT ExceptionSearchCatcherFound(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="da4b3-105">参数</span><span class="sxs-lookup"><span data-stu-id="da4b3-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="da4b3-106">[in]包含异常处理程序函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="da4b3-106">[in] The ID of the function that contains the exception handler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da4b3-107">要求</span><span class="sxs-lookup"><span data-stu-id="da4b3-107">Requirements</span></span>  
 <span data-ttu-id="da4b3-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="da4b3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da4b3-109">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="da4b3-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="da4b3-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da4b3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da4b3-111">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da4b3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da4b3-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da4b3-112">See Also</span></span>  
 [<span data-ttu-id="da4b3-113">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="da4b3-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
