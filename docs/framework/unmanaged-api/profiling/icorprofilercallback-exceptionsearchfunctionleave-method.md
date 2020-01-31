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
ms.openlocfilehash: bbd4c9e40f257cc66b638ba01ef8e51205922ece
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866385"
---
# <a name="icorprofilercallbackexceptionsearchfunctionleave-method"></a><span data-ttu-id="b5431-102">ICorProfilerCallback::ExceptionSearchFunctionLeave 方法</span><span class="sxs-lookup"><span data-stu-id="b5431-102">ICorProfilerCallback::ExceptionSearchFunctionLeave Method</span></span>
<span data-ttu-id="b5431-103">通知探查器异常处理的搜索阶段已经完成了对函数的搜索。</span><span class="sxs-lookup"><span data-stu-id="b5431-103">Notifies the profiler that the search phase of exception handling has finished searching a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5431-104">语法</span><span class="sxs-lookup"><span data-stu-id="b5431-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFunctionLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="b5431-105">需求</span><span class="sxs-lookup"><span data-stu-id="b5431-105">Requirements</span></span>  
 <span data-ttu-id="b5431-106">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b5431-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5431-107">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b5431-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b5431-108">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5431-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5431-109">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5431-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5431-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5431-110">See also</span></span>

- [<span data-ttu-id="b5431-111">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="b5431-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="b5431-112">ExceptionSearchFunctionEnter 方法</span><span class="sxs-lookup"><span data-stu-id="b5431-112">ExceptionSearchFunctionEnter Method</span></span>](icorprofilercallback-exceptionsearchfunctionenter-method.md)
