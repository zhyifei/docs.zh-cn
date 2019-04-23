---
title: ICorProfilerCallback::ExceptionSearchFunctionEnter 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3633665a3fcac0ca1d90ac562056b8b380ab2ca9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072527"
---
# <a name="icorprofilercallbackexceptionsearchfunctionenter-method"></a><span data-ttu-id="dac23-102">ICorProfilerCallback::ExceptionSearchFunctionEnter 方法</span><span class="sxs-lookup"><span data-stu-id="dac23-102">ICorProfilerCallback::ExceptionSearchFunctionEnter Method</span></span>
<span data-ttu-id="dac23-103">通知探查器的异常处理的搜索阶段已开始搜索函数，以便找到当前异常的处理程序。</span><span class="sxs-lookup"><span data-stu-id="dac23-103">Notifies the profiler that the search phase of exception handling has begun searching a function to find a handler for the current exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dac23-104">语法</span><span class="sxs-lookup"><span data-stu-id="dac23-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dac23-105">参数</span><span class="sxs-lookup"><span data-stu-id="dac23-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="dac23-106">[in]已输入的函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="dac23-106">[in] The ID of the function that has been entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dac23-107">要求</span><span class="sxs-lookup"><span data-stu-id="dac23-107">Requirements</span></span>  
 <span data-ttu-id="dac23-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dac23-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dac23-109">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dac23-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dac23-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dac23-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dac23-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dac23-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dac23-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="dac23-112">See also</span></span>

- [<span data-ttu-id="dac23-113">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="dac23-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="dac23-114">ExceptionSearchFunctionLeave 方法</span><span class="sxs-lookup"><span data-stu-id="dac23-114">ExceptionSearchFunctionLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionleave-method.md)
