---
title: "ICorProfilerCallback::ExceptionSearchFunctionEnter 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionSearchFunctionEnter
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionSearchFunctionEnter
helpviewer_keywords:
- ExceptionSearchFunctionEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFunctionEnter method [.NET Framework profiling]
ms.assetid: bfd54573-b7e6-4bd1-a184-7f08a8b39fae
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3fc6d1708a6a2daea0d0a9dc815bc07736644b49
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackexceptionsearchfunctionenter-method"></a><span data-ttu-id="31fd8-102">ICorProfilerCallback::ExceptionSearchFunctionEnter 方法</span><span class="sxs-lookup"><span data-stu-id="31fd8-102">ICorProfilerCallback::ExceptionSearchFunctionEnter Method</span></span>
<span data-ttu-id="31fd8-103">通知探查器异常处理的搜索阶段已开始搜索找到的处理程序的当前异常的函数。</span><span class="sxs-lookup"><span data-stu-id="31fd8-103">Notifies the profiler that the search phase of exception handling has begun searching a function to find a handler for the current exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31fd8-104">语法</span><span class="sxs-lookup"><span data-stu-id="31fd8-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="31fd8-105">参数</span><span class="sxs-lookup"><span data-stu-id="31fd8-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="31fd8-106">[in]已输入的函数 ID。</span><span class="sxs-lookup"><span data-stu-id="31fd8-106">[in] The ID of the function that has been entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31fd8-107">要求</span><span class="sxs-lookup"><span data-stu-id="31fd8-107">Requirements</span></span>  
 <span data-ttu-id="31fd8-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="31fd8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31fd8-109">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="31fd8-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="31fd8-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31fd8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31fd8-111">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31fd8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31fd8-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31fd8-112">See Also</span></span>  
 [<span data-ttu-id="31fd8-113">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="31fd8-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="31fd8-114">ExceptionSearchFunctionLeave 方法</span><span class="sxs-lookup"><span data-stu-id="31fd8-114">ExceptionSearchFunctionLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionleave-method.md)
