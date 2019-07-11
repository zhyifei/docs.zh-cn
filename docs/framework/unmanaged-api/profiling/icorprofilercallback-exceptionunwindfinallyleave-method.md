---
title: ICorProfilerCallback::ExceptionUnwindFinallyLeave 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFinallyLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave method [.NET Framework profiling]
- ExceptionUnwindFinallyLeave method [.NET Framework profiling]
ms.assetid: 2350351e-f253-4c0c-a191-f952bc5700e6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0a6b754e6ceef0c451c38055078d403c0601ce45
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755940"
---
# <a name="icorprofilercallbackexceptionunwindfinallyleave-method"></a><span data-ttu-id="44f7f-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave 方法</span><span class="sxs-lookup"><span data-stu-id="44f7f-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave Method</span></span>
<span data-ttu-id="44f7f-103">通知探查器的异常展开阶段处理已离开`finally`子句。</span><span class="sxs-lookup"><span data-stu-id="44f7f-103">Notifies the profiler that the unwind phase of exception handling has left a `finally` clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44f7f-104">语法</span><span class="sxs-lookup"><span data-stu-id="44f7f-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFinallyLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="44f7f-105">备注</span><span class="sxs-lookup"><span data-stu-id="44f7f-105">Remarks</span></span>  
 <span data-ttu-id="44f7f-106">探查器在此调用期间不应进行阻止，因为堆栈可能未处于允许垃圾回收的状态，因此不能启用抢先式垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="44f7f-106">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="44f7f-107">如果尝试进行事件探查器阻止和垃圾回收，直到此回调返回，将阻止运行时。</span><span class="sxs-lookup"><span data-stu-id="44f7f-107">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="44f7f-108">此外，在此调用过程探查器必须调入托管代码或以任何方式导致托管内存分配。</span><span class="sxs-lookup"><span data-stu-id="44f7f-108">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44f7f-109">要求</span><span class="sxs-lookup"><span data-stu-id="44f7f-109">Requirements</span></span>  
 <span data-ttu-id="44f7f-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="44f7f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44f7f-111">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="44f7f-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="44f7f-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44f7f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44f7f-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44f7f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44f7f-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="44f7f-114">See also</span></span>

- [<span data-ttu-id="44f7f-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="44f7f-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="44f7f-116">ExceptionUnwindFinallyEnter 方法</span><span class="sxs-lookup"><span data-stu-id="44f7f-116">ExceptionUnwindFinallyEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)
