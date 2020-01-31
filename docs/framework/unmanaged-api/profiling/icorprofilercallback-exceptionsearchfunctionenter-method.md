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
ms.openlocfilehash: a64fe598bd9f50b822edb869fa9efca2a4ff280a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790132"
---
# <a name="icorprofilercallbackexceptionsearchfunctionenter-method"></a><span data-ttu-id="cf1ff-102">ICorProfilerCallback::ExceptionSearchFunctionEnter 方法</span><span class="sxs-lookup"><span data-stu-id="cf1ff-102">ICorProfilerCallback::ExceptionSearchFunctionEnter Method</span></span>
<span data-ttu-id="cf1ff-103">通知探查器，异常处理的搜索阶段已开始搜索函数以查找当前异常的处理程序。</span><span class="sxs-lookup"><span data-stu-id="cf1ff-103">Notifies the profiler that the search phase of exception handling has begun searching a function to find a handler for the current exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf1ff-104">语法</span><span class="sxs-lookup"><span data-stu-id="cf1ff-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf1ff-105">参数</span><span class="sxs-lookup"><span data-stu-id="cf1ff-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="cf1ff-106">\[中] 已输入的函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="cf1ff-106">\[in] The ID of the function that has been entered.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="cf1ff-107">需求</span><span class="sxs-lookup"><span data-stu-id="cf1ff-107">Requirements</span></span>  
 <span data-ttu-id="cf1ff-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cf1ff-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf1ff-109">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cf1ff-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cf1ff-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf1ff-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf1ff-111">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf1ff-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf1ff-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf1ff-112">See also</span></span>

- [<span data-ttu-id="cf1ff-113">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="cf1ff-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="cf1ff-114">ExceptionSearchFunctionLeave 方法</span><span class="sxs-lookup"><span data-stu-id="cf1ff-114">ExceptionSearchFunctionLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionleave-method.md)
