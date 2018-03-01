---
title: "ICorProfilerCallback::ExceptionSearchFunctionEnter 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback.ExceptionSearchFunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFunctionEnter
helpviewer_keywords:
- ExceptionSearchFunctionEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFunctionEnter method [.NET Framework profiling]
ms.assetid: bfd54573-b7e6-4bd1-a184-7f08a8b39fae
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d410d6ef47dfb0ad33c2a6a03f80d05810182a3b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptionsearchfunctionenter-method"></a><span data-ttu-id="9e1d3-102">ICorProfilerCallback::ExceptionSearchFunctionEnter 方法</span><span class="sxs-lookup"><span data-stu-id="9e1d3-102">ICorProfilerCallback::ExceptionSearchFunctionEnter Method</span></span>
<span data-ttu-id="9e1d3-103">通知探查器异常处理的搜索阶段已开始搜索找到的处理程序的当前异常的函数。</span><span class="sxs-lookup"><span data-stu-id="9e1d3-103">Notifies the profiler that the search phase of exception handling has begun searching a function to find a handler for the current exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e1d3-104">语法</span><span class="sxs-lookup"><span data-stu-id="9e1d3-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9e1d3-105">参数</span><span class="sxs-lookup"><span data-stu-id="9e1d3-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="9e1d3-106">[in]已输入的函数 ID。</span><span class="sxs-lookup"><span data-stu-id="9e1d3-106">[in] The ID of the function that has been entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e1d3-107">惠?</span><span class="sxs-lookup"><span data-stu-id="9e1d3-107">Requirements</span></span>  
 <span data-ttu-id="9e1d3-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9e1d3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e1d3-109">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9e1d3-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9e1d3-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e1d3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e1d3-111">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e1d3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e1d3-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e1d3-112">See Also</span></span>  
 [<span data-ttu-id="9e1d3-113">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="9e1d3-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="9e1d3-114">ExceptionSearchFunctionLeave 方法</span><span class="sxs-lookup"><span data-stu-id="9e1d3-114">ExceptionSearchFunctionLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionleave-method.md)
